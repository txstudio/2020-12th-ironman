# 安裝 SQL Server Failover Cluster 環境

設定好 Windows Failover Cluster 後

就要來安裝 SQL Server Failover Cluster

依先前規畫

```
SQL Server Network Name
SQL2017SSFC

IP Address
192.168.0.55
```

服務執行帳號

```
SQL Server Agent
txstudio\sqlsvc

SQL Server Database Engine
txstudio\sqlsvc
```

SQL Server 最高管理者 Windows 登入帳號

```
txstudio\sqladmin
```


## 新的 SQL Server Failover Cluster 安裝

連線到主要 Cluster 節點 TXSTUDIO056DB 並點選進入 SQL Server 安裝光碟路徑

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-01-a.png)

點選 setup 開啟安裝精靈

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-02.png)

點選 Installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-03.png)

點選 New SQL Server failover cluster installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-04.png)

選擇 Developer 版本

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-05.png)

勾選 I accept the license terms.

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-06.png)

忽略 Microsoft Update

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-07.png)

驗證 Failover Cluster

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-08.png)

勾選需要安裝的服務 Database Engine Services
- SQL Server Replication
- Full-Text and Semantic Extractions for S ...
- Data Quality Services

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-09.png)

輸入 SQL Server Network 名稱 SQL2017SSFC

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-10.png)

勾選檔案磁碟 FileDisk

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-11.png)

輸入 SQL Server Failover Cluster 的 IP 位址資訊

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-12.png)

輸入 SQL Server Database Engine 與 SQL Server Agent 服務執行的 Windows 帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-13.png)

檔案路徑依預設

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-14.png)

TempDB 會依照處理器核心數初始化預設數量

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-15.png)

在 Server Configuration 勾選 Mixed Mode 並輸入登入密碼

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-16.png)

點選 Add 加入指定的 Windows 登入帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-17.png)

輸入 txstudio\sqladmin 並點選 Check Names

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-18.png)

點選 Ok 將帳號設定成 SQL Server 管理員帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-19.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-20.png)

點選 Install 進行安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-21.png)

安裝會需要一段時間

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-22.png)

SQL Server Failover Cluster 安裝完成，點選 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/17/screenshot-23.png)

## 下一步

安裝好新的 SQL Server Failover Cluster 後

接下來要加入新的 SQL Server Failover Cluster 節點
