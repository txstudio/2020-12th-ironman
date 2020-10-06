
# 將 SQL Server Always On 機器加入至既有 Windows Failover Cluster

加入網域後，接下來要來安裝 Windows Failover Clustering 功能並加入至現有叢集

## 安裝 Windows Failover Clustering 功能

進入 TXSTUDIO058DB 的 Server Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-01.png)

點選 Manage 開啟 Add Roles and Features

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-02.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-03.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-04.png)

預設是安裝在本機伺服器，點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-05.png)

Server Role 不需要選擇，點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-06.png)

在 Features 功能勾選 Failover Clustering 功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-07.png)

點選 Add Features

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-08.png)

點選 Next 確認安裝資訊

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-09.png)

點選 Install 開始安裝 Failover Clustering 功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-10.png)

安裝完畢點選 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-11.png)

# 加入至既有 Windows Failover Cluster 叢集

安裝好 Windows Failover Cluster 功能後，接下來要 Server 加入至既有的 Failover Cluster

前往 TXSTUDIO058DB 伺服器，開啟 Server Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-12.png)

點選 Tools 開啟 Failover Cluster Manager 工具

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-13.png)

點選 Connect to Cluster

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-14.png)

輸入叢集名稱 TXSTUDIO053SRV

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-15.png)

點選 Add Node 增加節點

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-16.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-17.png)

輸入 server name TXSTUDIO058DB 點選 Add 將伺服器加入至叢集

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-18.png)

會自動帶出完整 Server 名稱，點選 Next 

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-19.png)

勾選 Yes 進行測試

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-20.png)

勾選 Run all tests 進行所有項目測試

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-21.png)

會列入叢集之後的伺服器清單點選 Next 開始測試

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-22.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-23.png)

驗證完畢後點選 Finish 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-24.png)

勾選 Add all eligible storage to the cluster 並點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-25.png)

就會開始將 TXSTUDIO058DB 加入至叢集

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-26.png)

## 驗證 Windows Failover Cluster

在 Failover Cluster Manager 開啟 Nodes

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-27.png)

可以看到目前 Failover Cluster 有三台 Server

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/22/screenshot-28.png)

## 下一步

設定好 TXSTUDIO058DB 機器環境完成後

就可以進行獨立 SQL Server 執行個體的安裝作業