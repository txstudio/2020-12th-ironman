# 驗證 Windows Failover Cluster

設定好 Windows Failover Cluster 後

透過重新啟動的方式模擬節點機器進行 Windows Update 更新時

主要節點的轉換與 iSCSI 的掛載狀態

## 確認目前 Failover Cluster 主要節點

進入 TXSTUDIO057DB 的 Server Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-01.png)

目前 File (F:) 與 Quorum (Q:) 磁碟槽皆掛載在此機器上

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-02.png)

然後從 TXSTUDIO056DB 的 This PC 可以看到只有系統磁碟與光碟機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-03.png)

在 TXSTUDIO056DB 開啟 Failover Cluster Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-04.png)

目前的 Current Host Server 是 TXSTUDIO057DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-05.png)

## 透過重新啟動確認 Failover Cluster 狀態

接下來重新啟動 TXSTUDIO057DB 

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-06.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-07.png)

連線到 TXSTUDIO056DB 並進入 Failover Cluster Manager 與 This PC 確認狀態

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-08.png)

Failover Cluster Manager 的 Current Host Server 已經變更為 TXSTUDIO056DB

Quorum (Q:) 磁碟槽已掛載到 TXSTUDIO056DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-09.png)

File (F:) 磁碟槽也已掛載到 TXSTUDIO056DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/16/screenshot-10.png)

透過上述步驟模擬主要節點機器進行 Windows Update 重新啟動後 Failover Cluster 節點間的轉換過程

## 下一步

Windows Failover Cluster 驗證完成後

就可以來安裝 SQL Server Failover Cluster 

