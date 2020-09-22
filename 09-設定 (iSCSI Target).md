
# 設定 iSCSI Server

角色安裝完成後，接下來要設定 iSCSI Target

提供 iSCSI 儲存空間給 Failover Cluster 使用

根據先前規劃 iSCSI 設定如下

- iSCSI target 名稱 sqlservertarget

允許存取 IP 位址

- 192.168.0.56
- 192.168.0.57
- 192.168.0.58

虛擬磁碟資訊

|名稱|路徑|空間|備註|
|--|--|--|--|
|SQLServerCluster|D:\iSCSIVirtualDisks\SQLServerCluster.vhdx|40GB|資料檔案使用|
|Quorum|D:\iSCSIVirtualDisks\Quorum.vhdx|500MB|仲裁磁碟|

## 設定資料庫與 Failover Clustering 使用的 iSCSI Target

在 Server Manager 點選 File and Storage Services

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-01.png)

開啟 iSCSI

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-02.png)

點選 To create and iSCSI virtual disk, start the New iSCSI virtual Disk Wizard

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-03.png)

選擇要建立 Virtual Disk 的磁碟

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-04.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-05.png)

輸入 Virtual Disk 名稱

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-06.png)

指定空間 40 GB 並選擇 Fixed Size (固定大小)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-07.png)

勾選 New iSCSI target 建立新的 iSCSI 目標

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-08.png)

輸入 target 名稱

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-09.png)

點選 Add... 加入允許存取的伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-10.png)

輸入允取存取的 IP 位址 192.168.0.56

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-11.png)

依序加入 IP 位址

- 192.168.0.56
- 192.168.0.57
- 192.168.0.58

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-12.png)

勾選 Enable CHAP 並輸入 User name 與 password

> 連線時要通過驗證才可以存取

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-13.png)

點選 Create 開啟建立作業

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-14.png)

完成後點選 Close 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-15.png)

此時會開始初始化 Virtual Disk

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-16.png)

## 設定 Quorum 使用的 iSCSI Target

在 iSCSI 點選右鍵 New iSCSI Virtual Disk...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-17.png)

選擇要建立 Virtual Disk 的磁碟區

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-18.png)

輸入名稱 Quorum

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-19.png)

輸入大小 500MB 與 Fixed Size (固定大小)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-20.png)

勾選 Existing iSCSI target 使用先前已建立的 iSCSI Target

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-21.png)

點選 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-22.png)

初始化完成後就可以透過 iSCSI 連線到此 Storage

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/09/screenshot-23.png)

## 下一步

網域控制站 (Domain Controller) 與檔案伺服器 (iSCSI Server ) 都設定完成後

接下來要來將電腦加入網域並掛載 iSCSI Server 提供的磁碟


