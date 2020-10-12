# 進行 SQL Server Always On Availability Group 設定

經過一長串的前置作業後

終於要在此步驟開始設定 SQL Server Always On Availability Group

## 設定 Always On 高可用性群組

前往 TXSTUDIO059WG 進入 SQL Server Management Studio 並連線至 SQL2017SSFC 資料庫

在「Always On 高可用性」下的「可用性群組」點選右鍵開啟「新增可用性群組精靈」

![](images/28/screenshot-01.png)

輸入可用性群組名稱

![](images/28/screenshot-02.png)

勾選 AdventureWorks2017 資料庫

![](images/28/screenshot-03.png)

點選「加入複本」

![](images/28/screenshot-04.png)

使用 Windows 驗證連線至 TXSTUDIO058DB 資料庫

![](images/28/screenshot-05.png)

「可讀取次要」勾選為「是」，設定完成後才可以驗證

![](images/28/screenshot-06.png)

其它設定就預設即可

![](images/28/screenshot-07.png)

![](images/28/screenshot-08.png)

![](images/28/screenshot-09.png)

![](images/28/screenshot-10.png)

點選「下一步」繼續

![](images/28/screenshot-11.png)

選擇「完整的資料庫及紀錄備份」並輸入先前備份儲存的檔案共用 UNC 路徑

![](images/28/screenshot-12.png)

驗證通過後點選「下一步」

![](images/28/screenshot-13.png)

點選「完成」就會開始設定

![](images/28/screenshot-14.png)

設定完畢

![](images/28/screenshot-15.png)

此時連線至 TXSTUDIO058DB 資料庫

AdventureWorks2017 處於正在還原狀態

![](images/28/screenshot-16.png)

在可用性資料庫點選右鍵加入可用性群組

![](images/28/screenshot-17.png)

重新將資料庫加入可用性群組

![](images/28/screenshot-18.png)

AdventureWorks2017 出現綠色小圖示代表有在同步處理

![](images/28/screenshot-19.png)

開啟 AdventureWorks2017 資料庫後可以看到資料表都被同步成功了

![](images/28/screenshot-20.png)

## 下一步

設定完成後就要來進行 AdventureWorks2017 資料同步的驗證
