
# 啟用所有 SQL Server 資料庫服務的 Always On Availability Group 功能

預設情況下 SQL Server Always On Availability Group 功能是被關閉的，需從組態管理員開啟

在 SQL Server Failover Cluster 會驗證節點轉移後此功能是否有正確被開啟

## 開啟 SQL Server Failover Cluster 的 AlwaysOn High Availability 功能

前往 TXSTUDIO058DB 伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-01.png)

在功能選單開啟 SQL Server 2017 Configuration Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-02.png)

選擇 SQL Server Service 並在 SQL Server (MSSQLSERVER) 點選右鍵開啟 Proerties 視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-03.png)

切換至 AlwaysOn High Availability 功能並勾選 Enable AlwaysOn Availability Group 並選擇 Apply

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-04.png)

會提示要重新啟動服務才會生效

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-05.png)

在 SQL Server (MSSQLSERVER) 點選右鍵點選 Restart

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-06.png)

等待 SQL Server 服務重新開啟

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-07.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-08.png)

SQL Server 服務重新啟動後，Always On 功能就會被啟用

## 驗證叢集節點變更後功能是否還是啟用狀態

重新開啟目前服務中的 SQL Server Failover Cluster 伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-09.png)

將 TXSTUDIO057DB 重新開機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-10.png)

進入 TXSTUDIO056DB 的 SQL Server Configuration Manager

> 因為目前提供服務的節點是 TXSTUDIO057DB 故一開始 SQL Server 相關服務是停用的

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-11.png)

SQL Server 服務因為節點轉換被開啟

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-12.png)

點選 SQL Server (MSSQLSERVER) 右鍵開啟 Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-13.png)

AlwaysOn High Availability 的 Enable AlwaysOn High Availability Groups 功能有被啟用

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-14.png)

當 SQL Server Failover Cluster 做節點轉換時，Always On 還是可以持續作用

## 開啟獨立 SQL Server 資料庫服務的 Always On High Availability 功能

前往 TXSTUDIO058DB 伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-15.png)

在功能選單開啟 SQL Server 2017 Configuration Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-16.png)

選擇 SQL Server Service 並在 SQL Server (SQLSERVERBK) 點選右鍵開啟 Proerties 視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-17.png)

切換至 AlwaysOn High Availability 功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-18.png)

勾選 Enable AlwaysOn Availability Group 並選擇 Apply

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-19.png)

會提示需要重新啟動 SQL Server 異動才會生效

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-20.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-21.png)

點選 SQL Server (SQLSERVERBK) 點選 Restart 重新啟動 SQL Server 服務

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-22.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-23.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-24.png)

SQL Server (SQLSERVERBK) 重新啟動後 AlwaysOn High Availability 功能就會生效

## 開啟 SQL Server Agent 功能

選擇 SQL Server Agent 服務點選右鍵選擇 Start 開啟服務

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-25.png)

再選擇 Proerties 開啟屬性視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-26.png)

選擇 Service 頁簽在 Start Mode 選擇 Automatic

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-27.png)

點選 OK 關閉設定

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/24/screenshot-28.png)

## 下一步

啟用所有 SQL Server 服務的 Always On Availability Group 後，還要允許指定連接埠的防火牆存取

接下來要來設定所有 SQL Server 電腦的防火牆
