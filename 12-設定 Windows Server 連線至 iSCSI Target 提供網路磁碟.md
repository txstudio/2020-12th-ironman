
# 設定 Windows Server 連線至 iSCSI Target 提供的網路磁碟

要安裝 SQL Server Failover Cluster 的電腦要連線到相同的 iSCSI 網路磁碟

當節點轉移時就網路磁碟會自動掛載到另外一台提供服務的節點

依規劃要掛載的電腦為

- TXSTUDIO056DB
- TXSTUDIO057DB

iSCSI Target 資訊

```
Server IP Address
192.168.0.51

iSCSI Target Name
sqlservertarget

CHAP
enable
```

掛載好磁碟後還要初始化才可以當一般的磁碟區操作

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/connect-to-iscsi-target.gif)

## 將 TXSTUDIO056DB 電腦連線到 iSCSI 伺服器

在 Server Manager 的 Tools 開啟 iSCSI Initiator

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-01.png)

點選 Yes 開啟 Microsoft iSCSI 服務

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-02.png)

在 iSCSI Initiator Properties 屬性的 Target 輸入 iSCSI 伺服器名稱 192.168.0.51 點選 Quick Connect...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-03.png)

點選 Done 連線至 iSCSI Target

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-04.png)

點選 Connect

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-05.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-06.png)

在 Connect to Target 視窗點選 Advanced...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-07.png)

在 Advanced Settings 勾選 Enable CHAP log on 輸入 Name 與 Target secret

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-08.png)

點選 OK 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-09.png)

點選 OK 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-10.png)

點選 OK 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-11.png)

## 初始化 iSCSI 磁碟區

回到 Server Manager 在 Tools 開啟 Computer Management

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-12.png)

在 Storage > Disk Management 就可以看到掛載上去的硬碟

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-13.png)

選擇 Disk 1 點選右鍵點選 Online

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-14.png)

選擇 Disk 2 點選右鍵點選 Online

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-15.png)

回到 Disk 1 點選右鍵點選 Initialize Disk

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-16.png)

使用預設點選 OK

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-17.png)

在 Disk 1 右鍵點選 New Simple Volume...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-18.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-19.png)

預設會使用所有空間

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-20.png)

磁碟槽選擇 F

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-21.png)

輸入 Volume label 名稱

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-22.png)

點選 Finish 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-23.png)

在 Disk 2 右鍵點選 New Simple Volume...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-24.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-25.png)

預設會使用所有空間

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-26.png)

磁碟槽選擇 Q

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-27.png)

輸入 Volume label 名稱

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-28.png)

點選 Finish 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-29.png)

F 與 Q 磁碟槽初始化完成

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-30.png)

## 將 TXSTUDIO057DB 電腦連線到 iSCSI 伺服器

因為 TXSTUDIO056DB 已經掛載好 iSCSI 磁碟區，此動作完成後磁碟區會處於 Offline 狀態並不需要再做初始化

在 Server Manager 的 Tools 開啟 iSCSI Initiator

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-31.png)

點選 Yes 開啟 Microsoft iSCSI 服務

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-32.png)

在 iSCSI Initiator Properties 屬性的 Target 輸入 iSCSI 伺服器名稱 192.168.0.51 點選 Quick Connect...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-33.png)

點選 Done 連線至 iSCSI Target

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-34.png)

點選 Connect

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-35.png)

在 Connect to Target 視窗點選 Advanced...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-36.png)

在 Advanced Settings 勾選 Enable CHAP log on 輸入 Name 與 Target secret

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-37.png)

點選 OK 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-38.png)

點選 OK 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-39.png)

回到 Server Manager 在 Tools 開啟 Computer Management

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-40.png)

在 Storage > Disk Management 就可以看到掛載上去的硬碟並處於 Offline 狀態

> 因為掛載於 TXSTUDIO056DB 電腦

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/12/screenshot-41.png)

## 下一步

iSCSI 硬碟掛載完成後，接下來就要設定 Windows Failover Cluster 容錯轉移叢集



