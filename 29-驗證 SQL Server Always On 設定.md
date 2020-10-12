# 驗證 SQL Server Always On 設定

設定完成 AdventureWork 資料庫做高可用性資料庫後，來測試資料是否會正確的同步到次要資料庫複本

## 進行 SQL Server Always On 驗證

先連線到 SQL2017SSFC 資料庫，在 AdventureWorks 資料庫建立新查詢

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-01.png)

寫一個會產生錯誤除以零的查詢，並使用 dbo.uspLogError 做紀錄

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-02.png)

產生的錯誤紀錄會儲存到 dbo.ErrorLog 資料表

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-03.png)

連線到 SQL Server Always On 的次要複本檢視 dbo.ErrorLog 資料表

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-04.png)

錯誤的資料列有同步到次要複本

## 重複驗證

再執行一次產生資料列

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-05.png)

錯誤資料也有正確同步到次要複本

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/29/screenshot-06.png)

## 驗證完畢

透過上次步驟，成功確認 SQL Server Always On 功能有成功將主要複本的異動同步到次要複本，當然也可以做更多步驟確認




