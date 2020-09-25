
# 建立 SQL Server Failover Cluster 使用的 Windows 帳號

依規劃，需額外建立的 Windows 帳號與其用途如下

|帳號|備註|
|--|--|
|txstudio\sqlsvc|SQL Server 服務執行帳號|
|txstudio\sqladmin|SQL Server 最高管理員帳號|

## 建立網域帳號

進入網域控制站 TXSTUDIO050DC

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-01.png)

在 Tools 開啟 Active Directory Users and Computers 工具

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-02.png)

### 建立 SQL Server 服務帳號

進入 Users 項目使用右鍵 New -> User

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-03.png)

輸入帳號名稱 sqlsvc

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-04.png)

設定密碼，並不要勾選 User must change password at next login

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-05.png)

點選 Finish 建立帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-06.png)

### 建立 SQL Server 最高權限管理員帳號

在上方 Action 點選 New -> User

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-07.png)

輸入帳號名稱 sqladmin

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-08.png)

設定密碼，並不要勾選 User must change password at next login

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-09.png)

點選 Finish 建立帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-10.png)

### 為帳號加入描述

加入 Windows 帳號的描述文字，日後能夠明確的知道帳號的使用目的

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-11.png)

txstudio\sqladmin 帳號描述

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-12.png)

txstudio\sqlsvc 帳號描述

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/11/screenshot-13.png)

## 下一步

帳號建立完成後，要設定 TXSTUDIO056DB 與 TXSTUDIO057DB 到連線 iSCSI Server 存取 iSCSI 磁碟


