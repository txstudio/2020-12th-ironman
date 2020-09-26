
# 安裝 Windows Failover Cluster 功能

在設定 Windows Failover Cluster 功能前

要先將所有要設定 Failover Cluster 的電腦安裝 Windows Failover Cluster 功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/install-clustering-feature.gif)

## 在 TXSTUDIO056DB 機器安裝 Failover Clustering 功能

在 Server Manager 點選 Manager 執行 Add Roles and Features

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-01.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-02.png)

選擇 Role-based or feature-based installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-03.png)

預設是將功能安裝在本機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-04.png)

Server Roles 不需要選擇項目

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-05.png)

在 Features 勾選 Failover Clustering

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-06.png)

點選 Add Features 一併安裝必要功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-07.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-08.png)

點選 Install 開始安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-09.png)

安裝完成

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-10.png)

## 在 TXSTUDIO057DB 機器安裝 Failover Clustering 功能

在 Server Manager 點選 Manager 執行 Add Roles and Features

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-11.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-12.png)

選擇 Role-based or feature-based installation

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-13.png)

預設是將功能安裝在本機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-14.png)

Server Roles 不需要選擇項目

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-15.png)

在 Features 勾選 Failover Clustering

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-16.png)

點選 Add Features 一併安裝必要功能

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-17.png)

點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-18.png)

點選 Install 開始安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-19.png)

安裝完成

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/13/screenshot-20.png)

## 下一步

安裝好 Windows Failover Cluster 功能後

接下來就是把 TXSTUDIO056DB 與 TXSTUDIO057DB 設定成 Windows Failover Cluster



