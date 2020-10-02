
# 驗證 SQL Server Failover Cluster 功能

安裝並設定好 SQL Server Failover Cluster 後

接下來要透過重新啟動節點伺服器的方式來驗證 SQL Server Failover Cluster 是否建置成功

> 如同 Windows Failover Cluster 的模擬方式

這次將使用 SQL Server Management Studio 來確認 SQL Server Failover Cluster 服務的節點狀態

## 使用工作電腦進行操作

使用資料庫管理員帳號 txstudio\sqladmin 

連線至 Windows 10 作業系統電腦 TXSTUDIO059WG

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-01.png)

開啟 Microsoft SQL Server Management Studio

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-02.png)

使用 Windows 登入連線至伺服器 SQL2017SSFC

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-03.png)

使用下列查詢確認伺服器名稱

```
SELECT @@SERVERNAME
```

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-04.png)

預先建立一個資料庫與資料表內容

```
CREATE DATABASE [ClusterDatabase]
GO

USE [ClusterDatabase]
GO

CREATE TABLE [dbo].[Table]
(
	[Id]	INT IDENTITY(1,1),
	[Name]	NVARCHAR(50),
	
	CONSTRAINT [PK_Table]
		PRIMARY KEY CLUSTERED([Id])
)
GO
```

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-05.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-06.png)

執行並建立資料庫與資料表物件

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-07.png)

使用 sys.dm_os_cluster_nodes 確認集節點狀態

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-08.png)

接下來重新啟動 TXSTUDIO056DB 伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-09.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-10.png)

持續查詢 sys.dm_os_cluster_nodes 物件

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-11.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-12.png)

可以看到 TXSTUDIO057DB 是正在提供服務的節點，TXSTUDIO056DB 處於關閉狀態

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-13.png)

目前 TXSTUDIO056DB 正在重新啟動中

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-14.png)

TXSTUDIO056DB 尚未開啟完成

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-15.png)

TXSTUDIO056DB 正在加入叢集

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-16.png)

TXSTUDIO056DB 開啟完成並重新加入叢集並處於備援狀態

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/19/screenshot-17.png)

從上述步驟可以看到在主要節點停止服務的時候

節點間轉移的狀態

可以發現在資料庫轉移時服務還是會有受到些許影響

## 下一步

SQL Server Failover Cluster 安裝就到此結束

接下來就要進行 SQL Server Always On 的環境與指定資料庫做 Always On 設定
