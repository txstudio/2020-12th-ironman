
# 升級為網域控制站 (Active Directory Domain Controller)

安裝好網域服務角色後

還要經過設定才會變成網域控制站 (Active Directory Domain Controller) 提供網域服務 (Active Directory Domain Service)

根據先前規劃升級網域控制站的必要設定如下

- 網域名稱為 txstudio.com

## 將電腦升級為網域控制站

點選 Server Manager 的黃色驚嘆號點選 Promote this server to a domain controller

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-01.png)

選擇 Add a new forest 並輸入 Root domain name

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-02.png)

Level 依照預設設定為 Windows Server 2016 並輸入還原密碼

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-03.png)

因為沒有既有 DNS 伺服器所以會加入 DNS 功能，點選 Next

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-04.png)

確認 NetBIOS 名稱

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-05.png)

LOG 紀錄使用預設

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-06.png)

點選 Next 準備開始安裝

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-07.png)

點選 Install 開始升級成網域控制站

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-08.png)

設定完成後會自動重新開機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-09.png)

重新開機後機器就會成為網域控制站 (Domain Controller)

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/07/screenshot-10.png)

重新啟動後

登入帳號輸入 txstudio\administrator 就是使用網域帳戶登入

輸入 TXSTUDIO050DC\administrator 就是使用本機帳戶登入

## 下一步

網域控制站設定完成後，接下來要來設定 iSCSI Server 
