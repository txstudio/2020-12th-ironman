# 啟用所有電腦的 5022 防火牆連接埠

首先來說明一下

為什麼開啟防火牆連接埠要放一個章節來說

因為

1. 很常忘記
2. 很常忘記
3. 很常忘記

然後 SQL Server Always On 就架不起來

所以開啟防火牆的部分要獨立一個章節來說明

## 開通必要防火牆連接埠

目前環境中已經將三台 Windows Server 設定成 Failover Cluster

兩台架設 SQL Server Failover Cluster 一台要設定為 SQL Server Always On 次要節點

每一台電腦都要開通指定連接埠，才不會有連線會中斷的問題

## 開啟 1433 連接埠

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-01-a.png)

開啟 Windows Firewall with Advanced Security

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-02.png)

點選 Inbound Rules

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-03.png)

點選 New Rule ... 建立新規則

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-04.png)

選取 Port

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-05.png)

輸入連接埠 1433

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-06.png)

依照預設點選下一步

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-07.png)

輸入規則名稱

> 此為 MSSQLSERVER

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-08.png)

此連接埠是 SQL Server Engine 預設連接埠，沒有要透過遠端管理的話可以關閉

## 開啟 5022 連接埠

接下來要開啟 5022 連接埠，此連接埠是 Always On 使用

> 也是 SQL Server 鏡像功能使用的連接埠

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-09.png)

點選 New Rule ... 建立新規則

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-10.png)

輸入連接埠 5022

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-11.png)

依照預設點選下一步

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-12.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-13.png)

輸入規則名稱

> 此為 SQLSERVER-HA

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/25/screenshot-14.png)

依上述步驟將所有 Windows Server 都設定一次

## 下一步

防火牆設定完成後，就要來開始準備 SQL Server Always On 設定的前置作業



