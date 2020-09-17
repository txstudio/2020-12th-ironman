# SQL Server Failover Cluster 簡介

SQL Server Failover Cluster 可保持 SQL Server 持續提供服務不中斷

## 沒有 Failover Cluster

若 SQL Server 資料庫要做軟體更新（Windows Update）重新開機時

在重新開機完畢前資料庫是停止服務的狀態

## 有了 Failover Cluster

當主要節點要做軟體更新（Windows Update）重新開機時

次要節點就可以接續主要節點任務並持續提供 SQL Server 資料庫服務

建立 SQL Server Failover Cluster 時要額外設定服務名稱與叢集IP位址

應用程式統一由叢集IP位址連線至資料庫服務

當然

在節點切換當下還是會有延遲時間

還是建議於離峰時進行

## 圖示說明

今天節點一是主要節點提供服務

節點二就是處於啟用但服務都是由節點一提供

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/04/current-node-1.gif)

當節點一無法提供服務的時候

節點二就會接替節點一繼續提供服務

保持資料庫服務不中斷

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/04/current-node-2.gif)

> 最上方箭頭代表資料庫連線都是連線至上面的服務名稱與叢集IP位址

## 網路介面卡

建立 Failover Cluster 機器需要多一個網路介面卡作為 HeartBeat

> HeartBeat: 心跳

透過此介面卡來判斷每一個 Failover Cluster 節點是否還健康

HeartBeat 網路介面卡與主要網路介面卡可不需要在同一個網段

在此範例中，使用 Hyper-V 內部網路虛擬交換器作為 HeartBeat 的網路介面卡

## 下一步

在開始設定前，要來先規劃如電腦名稱、IP位址、帳號與服務名稱等設定