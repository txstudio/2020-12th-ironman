# 設定 Windows Failover Cluster

接下來將使用 Failover Cluster Manager 將 TXSTUDIO056DB 與 TXSTUDIO057DB 電腦設定為 Windows Failover Cluster

根據先前規劃設定如下

```
Cluster Name
TXSTUDIO053SRV

IP Address
192.168.0.53
```

設定為 Windows Failover Cluster 電腦

```
TXSTUDIO056DB
TXSTUDIO057DB
```

## 驗證 Failover Cluster 設定

在 Server Manager 的 Tools 開啟 Failover Cluster Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-01.png)

在 Failover Cluster Manager 點選 Validate Configuration...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-02.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-03.png)

輸入要建立 Failover Cluster 的主機名稱 TXSTUDIO056DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-04.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-05.png)

輸入主機名稱 TXSTUDIO057DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-06.png)

勾選 Run all tests (recommanded)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-07.png)

確認要測試的主機清單

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-08.png)

就會開始進行 Failover Cluster 的驗證

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-09.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-10.png)

勾選 Create the cluster now using the validated nodes... 並點選 Finish 開啟 Create Cluster Wizard

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-11.png)

## 建立 Failover Cluster

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-12.png)

輸入 Cluster 名稱，並指定 IP 位址

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-13.png)

確認要建立的伺服器清單後點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-14.png)

就會開始 Failover Cluster 建立作業

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-15.png)

建立完成點選 Finish 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-16.png)

## 檢視設定完成的 Windows Failover Cluster

使用 Failover Cluster Manager 就可以檢視目前 Failover Cluster 狀態

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-17.png)

點選 Nodes 檢視節點伺服器清單

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-18.png)

Networks 顯示目前使用的網路介面卡，一個是 HeartBeat 使用

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-19.png)

Disks 為掛載的磁碟資訊

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-20.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-21.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-22.png)

TXSTUDIO056DB 沒有掛載 iSCSI 磁碟

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-23.png)

TXSTUDIO057DB 的 iSCSI 磁碟已經掛載上去

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-24.png)

開啟 Failover Cluster Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-25.png)

可以看到目前者主要結點為 TXSTUDIO057DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/14/screenshot-26.png)

## 下一步

設定完成後，就要來驗證結果是否正確