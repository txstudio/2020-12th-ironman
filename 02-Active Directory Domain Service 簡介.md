
# Active Directory Domain Service 簡介

一般情況下架設 SQL Server Failover Cluster 的電腦接需要納入 Active Directory 環境

> Active Directory 是可以不需要但本次還是依照正常流程建置

## Active Directory 簡介

透過 Active Directory 網域服務

登入 Windows 帳號、電腦、組織 ... 等都由網域控制站 (Domain Controller) 統一管理

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/02/active-directory-basic-graphic.gif)

建立一次登入帳號後，該帳號就可以在所有有加入網域的電腦中進行登入

> 前提是要有可以登入此電腦的權限

加入網域的電腦清單，都會登記在網域控制站的電腦目錄中

所有要架設 Failover Cluster 的 Windows Server

皆需要加入 AD 網域環境註冊「電腦名稱」與「使用者帳號」

之後架設的 Windows Failover Cluster 與 SQL Server Failover Cluster 的服務名稱也會登入在網域控制站中

## 下一步

接下來會介紹儲存伺服器與使用的傳輸協定 iSCSI

