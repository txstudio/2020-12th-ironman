
# 將 SQL Server Always On 機器加入網域

接下來要開始準備 SQL Server Always On 的資料庫伺服器

首先要先將伺服器加入 Active Directory 網域環境才可以進行加入 Failover Cluster 作業

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/architechture-add-domain-and-failover-clustering.gif)

## 加入現有的 Active Directory 網域

進入 TXSTUDIO058DB 的 Server Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-01.png)

點選 WORKGROUP

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-02.png)

在 System Properites 點選 Change

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-03.png)

在 Domain 輸入網域名稱 txstudio.com

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-04.png)

輸入擁有加入網域權限的帳號密碼

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-05.png)

加入網域成功

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-06.png)

點選 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-07.png)

點選 Restart Now 重新啟動伺服器

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-08.png)

重新啟動完成後就會在網域環境中

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-09.png)

## 驗證加入網域結果

重新開啟完成後就可以使用 txstudio\administrator 登入

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-10.png)

在 Server Manager 可以看到已經加入網域

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-11.png)

接下來進入網域控制站確認

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-12.png)

開啟 Computers 

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-13.png)

右鍵點選 Refresh

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-14.png)

可以看到 Computers 有 TXSTUDIO058DB 的電腦

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/21/screenshot-15.png)

## 下一步

加入網域後，還要將電腦加入到先前已設定好的 Windows Failover Cluster