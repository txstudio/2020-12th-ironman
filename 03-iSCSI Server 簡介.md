
# iSCSI Server 簡介

本次架設 SQL Server Failover Cluster 使用 iSCSI Server 掛載硬碟作為資料庫檔案的磁碟區

## 掛載實體磁碟

在常見的實體個人電腦中

使用磁碟管理工具將電腦的實體硬碟掛載到作業系統上

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/03/graphic-volumn-common.gif)

> 實體硬碟透過傳輸介面與電腦的主機板做連結

## 使用 iSCSI 掛載磁碟

iSCSI 可提供空間給 Windows Server 掛載成磁碟區

透過網路將資料寫至指定的檔案伺服器中

類似加上一顆硬碟到電腦中使用磁碟管理來操作

![](https://raw.githubusercontent.com/txstudio/2020-12th-ironman/master/images/03/graphic-volumn-with-iscsi-server.gif)

在 Failover Cluster 架構下

兩台以上節點伺服器皆會掛載相同的 iSCSI 空間

並在主要節點停止服務時，次要節點會自動掛載 iSCSI 硬碟

持續提供儲存服務

iSCSI Server 可在 Linux 系統建立，大部分的 NAS 也有支援此服務

本次範例環境使用 Windows Server 建立 iSCSI Server 提供服務

## 下一步

接下來會對 SQL Server Failover Cluster 的機制做簡短說明