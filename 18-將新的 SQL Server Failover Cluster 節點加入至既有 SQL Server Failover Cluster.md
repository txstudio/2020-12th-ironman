
# 將新的節點加入 SQL Server Failover Cluster

先前步驟已經建立好一個 SQL Server Failover Cluster

但要達到完整的 Failover 功能，至少還需要第二個節點才可以做轉移

接下來要透過 SQL Server Installation Center 將 TXSTUDIO057DB 作為新的節點加入至 SQL Server Failover Cluster

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/architechture-add-node-to-cluster.gif)

## 將新的節點加入 SQL Server Failover Cluster

進入 TXSTUDIO057DB 伺服器

> 已加入 Windows Failover Cluster

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-01.png)

進入 SQL Server 2017 安裝光碟位置

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-02.png)

點選 setup 進行安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-03.png)

點選 Installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-04.png)

點選 Add node to a SQL Server failover cluster

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-05.png)

選擇 Developer 版本

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-06.png)

勾選 I accept the license terms

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-07.png)

會進行第一階段驗證

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-08.png)

忽略 Microsoft Update 更新

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-09.png)

驗證節點規則

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-10.png)

此頁面會顯示要加入的 SQL Server Failover Cluster 節點

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-11.png)

叢集網路的設定

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-12.png)

在此要輸入 SQL Server Database Engine 與 SQL Server Agent 服務使用的 Windows 帳號登入密碼

> 使用的 Windows 帳號就是在安裝 SQL Server Failover Cluster 指定的 Windows 登入資訊

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-13.png)

點選 Install 進行安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-14.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-15.png)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-16.png)

安裝完成點選 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/18/screenshot-17.png)

加入新節點的步驟相較之下比較少

有兩個節點的話就可以透過節點的轉移持續提供 SQL Server 服務

## 下一步

安裝好 SQL Server Failover Cluster 後

就要來驗證 SQL Server Failover Cluster 功能是否正確
