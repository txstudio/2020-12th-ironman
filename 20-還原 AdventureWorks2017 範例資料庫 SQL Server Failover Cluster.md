
# 在 SQL Server Failover Cluster 還原 AdventureWorks2017 範例資料庫

SQL Server Always On 是指定資料庫做設定

先在架設好的 SQL Server Failover Cluster 還原 AdventureWorks2017 範例資料庫

在用此資料庫作為 Always On 的可用性群組資料庫

## 準備 AdventureWorks2017 備份資料檔案

請先到微軟網站下載 AdventureWorks2017 範例資料庫的備份檔案

https://docs.microsoft.com/zh-tw/sql/samples/adventureworks-install-configure?view=sql-server-ver15&tabs=ssms

> 這裡使用的是 AdventureWorks2017.bak

在 Failover Cluster Manager 確認提供服務主機為 TXSTUDIO057DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-01-a.png)

將 AdventureWorks2017 的備份資料庫檔案放在 F 磁碟槽

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-02.png)

## 進行資料庫還原

將備份檔放到資料庫伺服器的指定位置後

使用 Microsoft SQL Server Management Studio 進行資料庫還原作業

使用資料庫管理員帳號帳號登入 TXSTUDIO059WG 

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-03.png)

開啟 Microsoft SQL Server Management Studio

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-04.png)

在「連線」選擇「資料庫引擎」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-05.png)

連線到叢集資料庫伺服器 SQL2017SSFC

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-06.png)

點選「資料庫」右鍵「還原資料庫」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-07.png)

在裝置點選「...」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-08.png)

點選「加入」選擇資料庫備份檔案位置

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-09.png)

選擇輸入 F: 槽位置並選擇檔案 AdventureWorks2017.bak

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-10.png)

點選「確定」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-11.png)

點選「確定」就會開始還原資料庫

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-12.png)

AdventureWorks2017 資料庫還原成功

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-13.png)

## 驗證 AdventureWorks2017 資料庫

在物件總管可以看到 AdventureWorks2017 資料庫

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-14.png)

點選「資料表」可以看到 AdventureWorks2017 的資料表清單

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-15.png)

點選「新增查詢」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-16.png)

查詢目前資料庫的 index 清單
```
SELECT * FROM sys.indexes
```

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-17.png)

查詢目前資料庫的 table 清單

```
SELECT * FROM sys.tables
```

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/20/screenshot-18.png)

## 下一步

還原好資料庫後，接下來將要設定 SQL Server Always On 的機器

- 加入網域環境
- 設定與加入 Windows Failover Cluster

再來安裝 SQL Server 資料庫




