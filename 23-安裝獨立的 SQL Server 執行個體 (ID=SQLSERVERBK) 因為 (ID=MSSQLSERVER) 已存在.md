
# 進行獨立 SQL Server 執行個體安裝

SQL Server Always On 與 SQL Server Failover Cluster 不同

是以資料庫進行同步，故安裝要做獨立 SQL Server 執行個體的安裝

服務帳戶與資料庫最高管理員與 SQL Server Failover Cluster 設定相同

```
txstudio\sqlsvc		SQL Server Engine Service 與 SQL Agent 服務帳號
txstudio\sqladmin	最高管理員帳號
```

因為 MSSQLSERVER 執行個體名稱已經存在，安裝時要額外指定執行個體名稱避免衝突

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/architechture-install-standalone-sql-server.gif)

## 進行獨立 SQL Server 執行個體安裝

前往 TXSTUDIO058DB 伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-01.png)

進入 SQL Server 資料庫安裝磁碟槽

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-02.png)

在 Setup 點選右鍵選擇 Open 開啟安裝精靈

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-03.png)

點選 Installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-04.png)

點選 New SQL Server stand-alone installation or add features to an existing installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-05.png)

選擇 Developer 版本

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-06.png)

勾選 I accept the license terms

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-07.png)

驗證完成後點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-08.png)

先忽略安裝 Microsoft Update

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-09.png)

此時會有 Windows Firewall 警告，請先忽略

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-10.png)

在 Feature Selection 選擇 Database Engine Services 與 SQL Server Replication 功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-11.png)

因為預設 Instance 名稱 MSSQLSERVER 已在 Failover Cluster 指定，故變更 Named instance 為 SQLSERVERBK

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-12.png)

此時要輸入 SQL Server Agent 與 SQL Server Database Engine 服務的 Windows 帳號與密碼 txstudio\sqlsvc

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-13.png)

在 Server Configuration 選擇 Mixed Mode 並輸入 SA 帳號的登入密碼

並點選 Add 加入 txstudio\sqladmin 作為資料庫服務的最高管理者 Windows 帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-14.png)

會開始進行驗證作業

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-15.png)

點選 Install 開始安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-16.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-17.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-18.png)

安裝完成後點選 Close 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-19.png)

## 驗證 SQL Server 獨立安裝結果

輸入 service.msc 開啟服務視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-20.png)

可以看到 SQL Server 服務有括號標註 instance 名稱 SQLSERVERBK

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/23/screenshot-21.png)

## 下一步

SQL Server 資料庫安裝完成後，接下來要啟用 SQL Server 服務的 Always On Availability Group 功能

才可以進行 SQL Server Always On 設定


