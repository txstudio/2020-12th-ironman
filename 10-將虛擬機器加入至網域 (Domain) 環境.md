
# 將機器加入網域環境

設定好網域控制站與檔案伺服器後

要將電腦加入到網域環境中，要加入的電腦名稱如下

- TXSTUDIO056DB
- TXSTUDIO057DB
- TXSTUDIO059WG

在加入網域前，要先將網路介面卡的 DNS SERVER 指向網域控制站設定的 DNS 伺服器

> 在目前情境中 DNS Server 與網域控制站是同一台

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/architechture-add-domain.png)

## 將 TXSTUDIO056DB 加入網域

前往 Server Manager

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-01.png)

點選 Ethernet 開啟 Network Connections

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-02.png)

選擇 Ethernet 點選右鍵開啟 Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-03.png)

選擇 Internet Protocal Version 4 (TCP/IPv4) 並點選 Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-04.png)

在 Perferred DNS Server 輸入 DNS 伺服器位址 192.168.0.50

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-05.png)

回到 Server Manager 點選 TXSTUDIO056DB

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-06.png)

點選 Change...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-07.png)

在 Domain 輸入 txstudio.com

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-08.png)

此時會要求輸入有加入網域權限的帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-09.png)

加入 txstudio.com 成功

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-10.png)

會提示需要重新開機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-11.png)

點擊 Close 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-12.png)

點擊 Restart Now

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-13.png)

重新開啟 TXSTUDIO056DB 電腦

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-14.png)

## 將 TXSTUDIO057DB 加入網域

前往 Server Manager 點選 Ethernet 開啟 Network Connections

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-15.png)

在 Ethernet 點選右鍵開啟 Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-16.png)

選擇 Internet Protocal Version 4 (TCP/IPv4) 並點選 Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-17.png)

在 Perferred DNS Server 輸入 DNS 伺服器位址 192.168.0.50

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-18.png)

點擊 Close 關閉視窗

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-19.png)

回到 Server Manager 點選 TXSTUDIO057DB 開啟 System Properties

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-20.png)

在 Computer Name 點選 Change...

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-21.png)

在 Domain 輸入 txstudio.com

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-22.png)

此時會要求輸入有加入網域權限的帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-23.png)

加入 txstudio.com 成功

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-24.png)

會提示需要重新開機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-25.png)

點擊 Close 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-26.png)

點擊 Restart Now

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-27.png)

重新開啟 TXSTUDIO057DB 電腦

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-28.png)

## 將 TXSTUDIO059WG 加入網域


因為 Windows 10 作業系統沒有 Server Manager

在檔案總管點選右鍵開啟內容

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-29.png)

連線的電腦名稱 TXSTUDIO059WG

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-30.png)

點選右下角的網路圖示

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-31.png)

點擊「開啟網路和網際網路設定」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-32.png)

點擊「變更介面卡選項」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-33.png)

在「乙太網路」使用右鍵點選「內容」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-34.png)

選擇「網際網路通訊協定第4版(TCP/IPv4)」並點擊「內容」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-35.png)

慣用 DNS 伺服器輸入 192.168.0.50

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-36.png)

回到「系統」視窗點選「變更設定」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-37.png)

在網域輸入 txstudio.com

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-38.png)

此時會要求輸入有加入網域權限的帳號

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-39.png)

加入 txstudio.com 成功

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-40.png)

會提示需要重新開機

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-41.png)

點擊 Close 關閉

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-42.png)

點擊「立刻重新開機」

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-43.png)

重新開啟 TXSTUDIO059WG 電腦

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-44.png)

## 在網域控制站確認加入網域的電腦清單

進入網域控制站電腦 TXSTUDIO050DC

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-45.png)

點選 Tools 開啟 Active Directory Users and Computers

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-46.png)

點擊 txstudio.com 展開網域

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-47.png)

開啟 Computers 可以看到三台電腦都有加入至網域

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/10/screenshot-48.png)

## 下一步

加入網域完成後

要來建立提供給 SQL Server Failover Cluster 使用**服務**與**最高管理員**的 Windows 登入帳號