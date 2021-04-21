---
title: 活動 explorer 中所報告的標記動作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 列出活動瀏覽器中可用的標記動作清單。
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902941"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>活動瀏覽器中可用的標記活動

## <a name="sensitivity-label-applied"></a>套用敏感度標籤

此事件會在每次標記未標記的檔或以標籤傳送電子郵件時產生。 

- 它會在 Office 原生應用程式和 web 應用程式中儲存時捕獲。 
- 它會在 Azure 資訊保護增益集發生時捕獲。 
- 升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。   


|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------|
| Word、Excel、PowerPoint|是 |
|Outlook| 是 |從 Win 32 |
|線上 SharePoint OneDrive|是 | |
|Exchange        |是         | |
|Azure 資訊保護 (AIP) 整合用戶端和 AIP 整合掃描程式 |是 |AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*   |
|Microsoft 資訊保護 (MIP) SDK         |是|AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*|
|Rights Management Service (RMS)          |不適用         | |
|Power BI desktop 和 web        | 否| 可在 Microsoft 365 審計記錄檔中存取         |
|Microsoft Cloud App Security (MCAS)         |否|         |

## <a name="sensitivity-label-changed"></a>已變更敏感度標籤

每當檔或電子郵件上的標籤更新時，就會產生此事件。

- 針對 AIP 整合用戶端、統一掃描器和 MIP SDK 來源，AIP *升級卷* 標和 *降級標籤* 指令會對應至活動 explorer *標籤已變更*

- 它會在 Office 原生應用程式和 web 應用程式中的儲存點進行捕獲。 
- 在 Azure 資訊保護統一用戶端增益集與掃描器 enforcements 中發生時，會將它捕獲
- 升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。 除了 SharePoint Online 和 OneDrive 之外，也會捕獲 *調整* 文字。
- 在 Outlook 上的 Office 原生應用程式中完成的敏感度標記，會收集在檔儲存/電子郵件傳送動作之前所產生的最後一個動作。 例如，如果使用者在傳送之前在電子郵件上變更了標籤，則會在電子郵件傳送時，最後一個標籤會在審計記錄檔中取得，然後在活動 explorer 中報告。 


|來源  |活動 explorer 中報告|注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |是         |
|Outlook         |是         |Win 32|
|線上 SharePoint OneDrive         |是         |
|Exchange         |是         |
|AIP 整合用戶端         |是         |
|AIP 整合掃描器         |是         |
|MIP SDK         |是         |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |否         |可在 Microsoft 365 審計記錄檔中存取 |
|MCAS     |否         |         |

## <a name="sensitivity-label-removed"></a>已移除敏感度標籤

此事件會在每次從檔案或檔中移除標籤時產生。

- 在 Office 原生應用程式和 web 應用程式中儲存時，會捕獲此事件。
- 它會在 Azure 資訊保護增益集發生時捕獲。 
- 在 Outlook 上，使用 Office native MIP 標籤的敏感度標籤，會收集在儲存檔/電子郵件傳送動作之前所產生的最後一個標記事件。

|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |是         |
|Outlook         |是         |Win 32|
|線上 SharePoint OneDrive         |是         |
|Exchange         |是         |
|AIP 整合用戶端         |是         |AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作|
|AIP 整合掃描器         |是         |AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作 |
|MIP SDK         |是         |AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作 |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |否         |可在 Microsoft 365 審計記錄檔中存取 |
|MCAS     |否         |         |
 

## <a name="sensitivity-label-file-read"></a>敏感度標籤檔案讀取

此事件會在每次開啟已標記或受保護的檔時產生。

|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |是         |
|Outlook         |否         |
|線上 SharePoint OneDrive         |否         |
|Exchange         |否         |
|AIP 整合用戶端         |是         |AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作|
|AIP 整合掃描器         |是         |AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作|
|MIP SDK         |是         |AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作|
|RMS 服務         |是         |*存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作 |
|Power BI desktop 和 Web         |否         |可在 Microsoft 365 審計記錄檔中存取 |
|MCAS     |否         |         |


## <a name="sensitivity-label-files-discovered"></a>已探索敏感度標籤檔案

當您每次使用 AIP 掃描程式來掃描不同位置的敏感性資料並尋找檔案時，就會產生這個事件。

|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |不適用         |
|Outlook         |不適用         |
|線上 SharePoint OneDrive         |不適用         |
|Exchange         |不適用         |
|AIP 整合用戶端         |不適用       |
|AIP 整合掃描器         |是         |AIP *探索* 動作會對應至活動瀏覽器中已 *發現的檔* 動作|
|MIP SDK         |是         |AIP *探索* 動作會對應至活動瀏覽器中的 [已 *發現的檔* ] 動作|
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |不適用         |
|MCAS     |不適用         |         |


## <a name="sensitivity-label-file-renamed"></a>敏感度標籤檔案名已重新命名

此事件會在每次重新命名具有敏感度標籤的檔時產生。 

|來源  | 活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |是         |
|Outlook         |不適用         |
|線上 SharePoint OneDrive         |否        |
|Exchange         |不適用         |
|AIP 整合用戶端         |否         |
|AIP 整合掃描器         |否         |
|MIP SDK         |否         |
|RMS 服務         |否      |
|Power BI desktop 和 Web         |否         |
|MCAS     |否         |         |


## <a name="sensitivity-label-file-removed"></a>已移除敏感度標籤檔案

此事件會在每次 AIP 掃描程式偵測到先前掃描的檔案已移除時產生。

|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |不適用         |
|Outlook         |不適用         |
|線上 SharePoint OneDrive         |不適用           |
|Exchange         |不適用         |
|AIP 整合用戶端         |不適用            |
|AIP 整合掃描器         |是         |
|MIP SDK         |不適用            |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |不適用  |
|MCAS     |不適用        |         |

### <a name="sensitivity-label-protection-applied"></a>套用敏感度標籤保護

此事件會產生第一次保護是手動新增至沒有標籤的專案。

|來源  |活動 explorer 中報告 | 注意  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|線上 SharePoint OneDrive         |不適用           |
|Exchange         |否       |
|AIP 整合用戶端         |是            |
|AIP 整合掃描器         |不適用         |
|MIP SDK         |是            |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |不適用            |
|MCAS     |不適用        |         |

## <a name="sensitivity-label-protection-changed"></a>已變更敏感度標籤保護

每當以手動方式變更未標記檔的保護時，就會產生此事件。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|線上 SharePoint OneDrive         |不適用           |
|Exchange         |否       |
|AIP 整合用戶端         |是            |
|AIP 整合掃描器         |不適用         |
|MIP SDK         |是            |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |不適用            |
|MCAS     |不適用        |

## <a name="sensitivity-label-protection-removed"></a>已移除敏感度標籤保護

每當以手動方式變更未標記檔的保護時，就會產生此事件。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|線上 SharePoint OneDrive         |不適用           |
|Exchange         |否       |
|AIP 整合用戶端         |是            |
|AIP 整合掃描器         |不適用         |
|MIP SDK         |是            |
|RMS 服務         |不適用         |
|Power BI desktop 和 Web         |不適用            |
|MCAS     |不適用        |

## <a name="sensitivity-label-dlp-policy-matched"></a>敏感度標籤 DLP 原則符合

每當符合 DLP 原則時，就會產生此事件。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Exchange         |是       |
|SharePoint Online|是          |
|OneDrive |是|
|Teams |是   |
|Windows 10 裝置         |是 |
|Mac         |否     |
|內部部署         |否|
|MCAS     |否        | 

Windows 10 裝置的事件 (端點 DLP) 如下：

- 已刪除檔案
- 已建立檔
- 檔案已複製到剪貼簿
- 修改檔案
- 檔案讀取
- 已列印檔案
- 重新命名的檔案名
- 檔案已複製到網路共用
- unallowed 應用程式所存取的檔案


## <a name="retention-label-applied"></a>套用保留標籤 

此事件會在每次標記未標記的檔或以標籤傳送電子郵件時產生。

- 它會在 Office 原生應用程式和 web 應用程式中儲存時捕獲。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|

## <a name="retention-label-changed"></a>已變更保留標籤

每當檔或電子郵件上的標籤更新時，就會產生此事件。

- 它會在儲存時被捕獲。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|
 
## <a name="retention-label-removed"></a>已移除保留標籤

此事件會在每次從檔案或檔中移除標籤時產生。

- 它會在儲存時被捕獲。

|來源  |活動 explorer 中報告 |
|---------|---------| 
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|


## <a name="known-issues"></a>已知問題
  
- 向使用者顯示建議的標籤工具提示時，不會將其捕獲。 不過，如果使用者選擇套用建議的標籤，標籤會顯示在 *建議* 的 *套用欄位底下*。  

- 敏感度標籤上目前無法使用對齊文字，請從 Sharepoint 和 OneDrive 降級。  

- 機密資訊類型目前不適用於來自 Word、Excel、PowerPoint 和 Outlook 的 autolabeling 活動，以及 SharePoint 線上及 OneDrive。
