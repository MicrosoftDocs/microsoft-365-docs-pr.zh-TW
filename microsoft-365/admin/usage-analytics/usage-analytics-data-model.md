---
title: Microsoft 365 使用情況分析資料模型
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '瞭解流量分析如何連接至 API，並提供各種 Microsoft 365 服務每月的使用趨勢。  '
ms.openlocfilehash: 877ad005e3ff7f7537247963fafcab5fb1ff6c74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580747"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 使用情況分析資料模型

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365 流量分析表的資料

Microsoft 365 流量分析會連接至公開多維度資料模型的 API。 Microsoft 365 流量分析用來產生其資料的 APIs，都來自各種、可供一般使用的 Graph APIs。 Microsoft 365 流量分析 API 的功能一般無法使用。
  
> [!NOTE]
> 如需詳細資訊，請參閱使用[Microsoft Graph 中的 Microsoft 365 使用方式報告](/graph/api/resources/report)。 
  
此 API 提供各種 Microsoft 365 服務每月使用趨勢的相關資訊。 如需 API 傳回的確切資料，請參閱下一節中的表格。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 報告 API 傳回的資料表格

|**表格名稱**|**表格中的資訊**|**日期範圍**|
|:-----|:-----|:-----|
|租用戶產品使用情況  <br/> |包含啟用、作用中使用者、每月保留使用者、第一次使用者和累計使用中使用者的每月總數。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶產品活動  <br/> |包含各項活動的每月總數，以及產品內各種活動的活動使用者計數。  <br/> 如需產品內此資料表格中傳回活動的相關資訊，請參閱[作用中使用者定義](active-user-in-usage-reports.md)。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶 Office 授權  <br/> |包含指派給使用者之 Microsoft Office 訂閱數的相關資料  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|租用戶信箱使用量  <br/> |會包含使用者信箱的相關資料、信箱總數，以及使用儲存體的方式。  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|租用戶用戶端使用量  <br/> |包含主動使用特定用戶端/裝置連線到 Exchange Online、商務用 Skype 和 Yammer 之使用者數目的相關資料。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶 SharePoint Online 使用量  <br/> |包含 SharePoint 網站 (涵蓋小組或群組網站) 的相關資料，例如網站總數、網站上的文件數目、依活動類型計算的檔案計數，以及使用的儲存空間。  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|租用戶商務用 OneDrive 使用量  <br/> |包含 OneDrive 帳戶的相關資料，例如帳戶數目、OneDrive 上的文件數目、使用的儲存空間、依活動類型計算的檔案計數。  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|租使用者 Microsoft 365 群組使用量  <br/> |包含有關 Microsoft 365 群組使用量的資料，包括信箱、SharePoint 及 Yammer。  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|租用戶 Office 啟用  <br/> |包含有關 Office 訂閱啟用的數目、每個裝置的啟用計數 (Android/iOS/Mac/PC) ，依服務方案啟動的資料，例如 Microsoft 365 Apps 企業版、Visio、Project。  <br/> |包含第12個月期間內的月末狀態資料，包括目前部分月份。  <br/> |
|使用者狀態  <br/> |包含使用者的相關中繼資料，包括使用者顯示名稱、指派的產品、地點、部門、職稱、公司。 此資料是關於在最後一個完整月份期間獲指派授權的使用者。 每個使用者都由使用者識別碼唯一表示。  <br/> |此資料與上一個完整月份期間指派授權的使用者有關。  <br/> |
|使用者活動  <br/> |包含授權使用者執行活動的每個使用者層級資訊。  <br/> 如需產品內此資料表格中傳回活動的相關資訊，請參閱[作用中使用者定義](active-user-in-usage-reports.md)。  <br/> |此資料與上一個完整月份期間在任何服務中執行活動的使用者有關。  <br/> |
   
展開下列各節，以查看每個資料表格的詳細資訊。
  
### <a name="data-table---user-state"></a>資料表格 - 使用者狀態

此表格會針對在最後一個完整月份期間指派授權的所有使用者，提供使用者層級的詳細資料。 它會從 Azure Active Directory 匯入資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|UserId  <br/> |代表使用者的唯一使用者識別碼，可與資料集內的其他資料表格加入。  <br/> |
|Timeframe  <br/> |此表格內含資料的月份值。  <br/> |
|UPN  <br/> |使用者主體名稱，可唯一識別能夠使用其他外部資料來源加入的使用者。  <br/> |
|DisplayName  <br/> |使用者的顯示名稱。  <br/> |
|IDType  <br/> |如果使用者是使用其 Yammer 識別碼進行連線的 Yammer 使用者，則識別碼類型設為 1; 如果使用者使用 Microsoft 365 識別碼連線到 Yammer，則為0。  <br/> 值為1表示此使用者使用 Yammer 識別碼（而不是其 Microsoft 365 識別碼）連接至 Yammer  <br/> |
|HasLicenseEXO  <br/> |如果使用者有獲指派授權，而且可以使用 Exchange，則設為 true。  <br/> |
|HasLicenseODB  <br/> |如果使用者有獲指派授權，而且可以使用商務用 OneDrive，則設為 true。  <br/> |
|HasLicenseSPO  <br/> |如果使用者有獲指派授權，而且可以使用 SharePoint Online，則設為 true。  <br/> |
|HasLicenseYAM  <br/> |如果使用者有獲指派授權，而且可以使用 Yammer，則設為 true。  <br/> |
|HasLicenseSFB  <br/> |如果使用者有獲指派授權，而且可以使用商務用 Skype，則設為 true。  <br/> |
|HasLicenseTeams  <br/> |若使用者已獲指派授權，而且可以使用 Microsoft Teams 則設定為 true。  <br/> |
|Company  <br/> |在 Azure Active Directory 中表示此使用者的公司資料。  <br/> |
|Department  <br/> |在 Azure Active Directory 中表示此使用者的部門資料。  <br/> |
|LocationCity  <br/> |在 Azure Active Directory 中表示此使用者的城市資料。  <br/> |
|LocationCountry  <br/> |在 Azure Active Directory 中表示此使用者的國家/地區資料。  <br/> |
|LocationState  <br/> |在 Azure Active Directory 中表示此使用者的州資料。  <br/> |
|LocationOffice  <br/> |使用者的辦公室。  <br/> |
|Title  <br/> |在 Azure Active Directory 中表示此使用者的職稱資料。  <br/> |
|Deleted  <br/> |True 是表示如果使用者已從最後一個完整月份的 Microsoft 365 中刪除。  <br/> |
|DeletedDate  <br/> |從 Microsoft 365 刪除使用者的日期。  <br/> |
|YAM_State  <br/> |Yammer 系統中使用者的狀態，可為作用中、已刪除或已暫停狀態。  <br/> |
|YAM_ActivationDate  <br/> |使用者在 Yammer 中進入作用中狀態的日期。  <br/> |
|YAM_DeletionDate  <br/> |使用者在 Yammer 中進入已刪除狀態的日期。  <br/> |
|YAM_SuspensionDate  <br/> |使用者在 Yammer 中進入已暫停狀態的日期。  <br/> |
   
### <a name="data-table---user-activity"></a>資料表格 - 使用者活動

此表格包含上個月在任何服務中有活動之每個使用者的相關資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|UserID  <br/> |代表使用者的唯一使用者識別碼，可與資料集內的其他資料表格加入。  <br/> |
|IDType  <br/> |如果使用者是使用其 Yammer 識別碼進行連線的 Yammer 使用者，則識別碼類型設為 1; 如果使用者使用 Microsoft 365 識別碼連線到 Yammer，則為0。  <br/> 值為1表示此使用者使用 Yammer 識別碼（而不是其 Microsoft 365 識別碼）連接至 Yammer  <br/> |
|Timeframe  <br/> |此表格表示有資料的月份值。  <br/> |
|EXO_EmailSent  <br/> |已傳送的電子郵件數目。  <br/> |
|EXO_EmailReceived  <br/> |已接收的電子郵件數目。  <br/> |
|EXO_EmailRead  <br/> |使用者執行的電子郵件讀取活動數目，可以多次讀取已讀取的電子郵件，或先前收到的電子郵件。  <br/> |
|EXO_AppointmentCreated  <br/> |建立的約會數目。  <br/> |
|EXO_MeetingAccepted  <br/> |已接受的會議數目。  <br/> |
|EXO_MeetingCancelled  <br/> |取消的會議數目。  <br/> |
|EXO_MeetingDeclined  <br/> |謝絕的會議數目。  <br/> |
|EXO_MeetingSent  <br/> |已傳送的會議數目。  <br/> |
|ODB_FileViewedModified  <br/> |此使用者在任何商務用 OneDrive 上互動的檔案數目 (例如建立、更新、刪除、檢視或下載)。  <br/> |
|ODB_FileSynched  <br/> |此使用者在任何商務用 OneDrive 上同步處理的檔案數目。  <br/> |
|ODB_FileSharedInternally  <br/> |此使用者從任何商務用 OneDrive （或群組 (中的使用者）內部共用的檔案數目（可能包括外部使用者) ）。  <br/> |
|ODB_FileSharedExternally  <br/> |此使用者從任何商務用 OneDrive 外部共用的檔案數目。  <br/> |
|ODB_AccessByOwner  <br/> |使用者與自己的商務用 OneDrive 上檔案互動的檔案數目。  <br/> |
|ODB_AccessOthers  <br/> |使用者與其他使用者的商務用 OneDrive 上檔案互動的檔案數目。  <br/> |
|SPO_GroupFileViewedModified  <br/> |與此使用者在任何群組網站上互動的檔案數目。  <br/> |
|SPO_GroupFileSynched  <br/> |此使用者在任何群組網站上同步處理的檔案數目。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |與組織內的使用者共用的檔案數目，或與可能包含外部使用者) 的群組 (中的使用者共用的檔案數目。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |此使用者從任何群組網站外部共用的檔案數目。  <br/> |
|SPO_GroupAccessByOwner  <br/> |使用者與自己的群組網站上檔案互動的檔案數目。  <br/> |
|SPO_GroupAccessByOthers  <br/> |使用者與其他使用者的群組網站上檔案互動的檔案數目。  <br/> |
|SPO_OtherFileViewedModified  <br/> |此使用者在任何其他網站上互動的檔案數目。  <br/> |
|SPO_OtherFileSynched  <br/> |此使用者從任何其他網站同步處理的檔案數目。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |此使用者從任何其他網站內部共用的檔案數目，或與可能包含外部使用者) 的群組 (中的使用者共用的檔案數目。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |此使用者從任何其他網站外部共用的檔案數目。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |使用者與其所擁有之其他網站上的互動的網站數目。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |使用者與其他使用者所擁有的其他網站進行互動的網站數目。  <br/> |
|SPO_TeamFileViewedModified  <br/> |與此使用者在任何小組網站上互動的檔案數目。  <br/> |
|SPO_TeamFileSynched  <br/> |此使用者從任何小組網站同步處理的檔案數目。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |此使用者從任何小組網站內部共用的檔案數目，或與可能包含外部使用者) 的群組 (中的使用者共用的檔案數目。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |此使用者從任何小組網站外部共用的檔案數目。  <br/> |
|SPO_TeamAccessByOwner  <br/> |使用者與自己的小組網站上檔案互動的檔案數目。  <br/> |
|SPO_TeamAccessByOthers  <br/> |使用者與其他使用者的小組網站上檔案互動的檔案數目。  <br/> |
|Teams_ChatMessages  <br/> |已傳送的聊天訊息數目。  <br/> |
|Teams_ChannelMessage  <br/> |張貼到通道的郵件數目。  <br/> |
|Teams_CallParticipate  <br/> |使用者參與的通話數目。  <br/> |
|Teams_MeetingParticipate  <br/> |使用者加入的會議數目。  <br/> |
|Teams_HasOtherAction  <br/> |布林值，如果使用者在 Microsoft Teams 中執行其他動作。  <br/> |
|YAM_MessagePost  <br/> |此使用者投遞的 Yammer 郵件數目。  <br/> |
|YAM_MessageLiked  <br/> |此使用者贊的 Yammer 郵件數目。  <br/> |
|YAM_MessageRead  <br/> |此使用者讀取的 Yammer 郵件數目。  <br/> |
|SFB_P2PSummary  <br/> |此使用者參與的對等工作階段數目。  <br/> |
|SFB_ConfOrgSummary  <br/> |此使用者組織的會議工作階段數目。  <br/> |
|SFB_ConfPartSummary  <br/> |此使用者參與的會議工作階段數目。  <br/> |

> [!NOTE]
> Teams_HasOtherAction 表示使用者被視為作用中，但聊天訊息、1:1 通話、通道訊息、會議總數和會議組織值都是空的。
   
### <a name="data-table---tenant-product-usage"></a>資料表格 - 租用戶產品使用情況

此表格針對 Microsoft 365 中每個產品的「啟用」、「作用中」、「傳回」和「初次」的使用者，提供每月採用的採用資料。 Microsoft 365 值代表任何產品中的使用中用法。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|Product  <br/> |摘要說明其使用情況資訊的產品名稱。 [產品] 欄中的 Microsoft 365 值代表任何產品間的活動  <br/> |
|Timeframe  <br/> |月份值。每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|EnabledUsers  <br/> |已啟用的使用者人數若要將產品用於時間框架值，如果使用者已啟用某月的一部分，仍然會計算這些使用者。  <br/> |
|ActiveUsers  <br/> |在產品中執行「有意」活動的時間框架值的使用者人數。  <br/> A user is counted as active for a product in a particular month, if they have performed one of the key activities in the product. The key activities are available in the **Tenant Product Activity** table.  <br/> |
|CumulativeActiveUsers  <br/> |可使用產品，而且自新的使用情況系統開始收集資料起，已在時間範圍月份內至少使用一次產品的使用者數目。  <br/> |
|MoMReturningUsers  <br/> |在時間範圍月份內有效，且在上一個月也有效的使用者數目。  <br/> |
|FirstTimeUsers  <br/> |自新的使用情況系統開始收集資料起，在時間範圍內第一次成為作用中使用者的使用者數目。  <br/> 如果我們自這個新的報告系統開始收集資料起，第一次偵測到使用者的活動，則會將該使用者計入特定月份的初次使用者。 即使此使用者在其活動中有大量的缺口，也不會再次計算為第一次使用者  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>資料表格 - 租用戶產品活動

此表格提供各項活動的每月總數，以及各項活動的使用中使用者計數。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|Timeframe  <br/> |月份值。每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|Product  <br/> |可供使用中資料的 Microsoft 365 內的產品名稱。  <br/> |
|Activity  <br/> |產品中用來展現產品使用中的活動名稱。  <br/> |
|ActivityCount  <br/> |這是針對產品內所有作用中使用者執行的每個活動計算的動作總數。  <br/> **注意：** 若是 SharePoint Online 和商務用 OneDrive 活動，此值代表與使用者互動的不同文件數目。  <br/> |
|ActiveUserCount  <br/> |已在產品內執行活動的使用者數目。  <br/> |
|TotalDurationInMinute  <br/> |在適用的商務用 Skype 活動中，使用音訊或視訊工作階段之所有作用中使用者持續使用的分鐘數。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>資料表格 - 租用戶信箱使用量

此表格包含所有擁有使用者信箱之授權 Exchange Online 使用者的摘要資料。 其中包含所有使用者信箱的月底狀態。 此表格在多個月份內的資料不具有累計性。 此表格中最新月份的資料代表最新的狀態。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|TotalMailboxes  <br/> |Microsoft 365 訂閱的使用者信箱數目。  <br/> |
|IssueWarningQuota  <br/> |在所有使用者信箱中發出警告的總配額。  <br/> |
|ProhibitSendQuota  <br/> |在所有使用者信箱中禁止傳送的配額總計。  <br/> |
|ProhibitSendReceiveQuota  <br/> |在所有使用者信箱中禁止傳送接收配額的配額總計。  <br/> |
|TotalItemBytes  <br/> |所有使用者信箱所使用的儲存空間量 (以位元組為單位)。  <br/> |
|MailboxesNoWarning  <br/> |在儲存空間警告限制之下的使用者信箱數目。  <br/> |
|MailboxesIssueWarning  <br/> |針對儲存空間配額發出警告的使用者信箱數目。  <br/> |
|MailboxesExceedSendQuota  <br/> |已超過傳送配額的使用者信箱數目。  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |超過傳送/接收配額的使用者信箱數目。  <br/> |
|DeletedMailboxes  <br/> |在時間範圍內刪除的使用者信箱數目。  <br/> |
|Timeframe  <br/> |月份值。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>資料表格 - 租用戶用戶端使用量

此表格提供每月的摘要資料，以供使用者用來連線至 Exchange Online、商務用 Skype 及 Yammer 的用戶端使用。 此表格還沒有適用於 SharePoint Online 和商務用 OneDrive 的用戶端使用資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|Product  <br/> |可供使用之用戶端使用狀況資料 Microsoft 365 內的產品名稱。  <br/> |
|ClientId  <br/> |用來連線至產品之每個裝置的名稱。  <br/> |
|UserCount  <br/> |使用每個產品適用之每個用戶端的使用者數目。  <br/> |
|Timeframe  <br/> |月份值  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>資料表格 - 租用戶 SharePoint Online 使用量

此表格包含 SharePoint Online 網站使用量或活動的每月相關摘要資料。 這只涵蓋小組網站與群組網站。 SharePoint Online 網站的 month 狀態的結束點會以此欄位表示，例如，如果使用者建立了五個檔，並使用 10 mb 來儲存總儲存體，然後刪除部分檔案，並新增更多的檔案，讓檔案的月末狀態為使用五 MB 儲存體的7個，則此表格中所表示的值就是月底的狀態。 系統會隱藏此表格以避免重複計算彙總，並當做建立兩個參照表格的來源使用。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|SiteType  <br/> |網站類型值 (任何/小組/群組) (任何都可以代表這 2 個網站類型之一)。  <br/> |
|TotalSites  <br/> |在時間範圍結束時存在的網站數目。  <br/> |
|DocumentCount  <br/> |在時間範圍結束時存在網站上的文件總數。  <br/> |
|Diplansed  <br/> |在時間範圍結束時，所有網站上加總的已使用儲存空間總計。  <br/> |
|ActivityType  <br/> |記錄各種類型檔案活動 (任何/作用中的檔案/共用 EXT 的檔案/INT/同步處理的檔案) 的網站數目。  <br/> 代表所執行的任何檔案活動。  <br/> |
|SitesWithOwnerActivities  <br/> |作用中網站的數目，其中網站擁有者會在自己的網站上執行特定的檔案活動。 您可以從 PowerShell 命令 **get-sposite** 取得網站擁有者。 這是負責網站的人員。   <br/> |
|SitesWithNonOwnerActivities  <br/> |整個月加總的作用中網站數目，其中網站擁有者以外的使用者會在網站上執行特定的檔案活動。 您可以從 PowerShell 命令 **get-sposite** 取得網站擁有者。 這是負責網站的人員。 <br/> |
|ActivityTotalSites  <br/> |在時間範圍期間記錄任何活動的網站數目。如果網站的活動在時間範圍內稍早的時候，而且在時間範圍結束時遭到刪除，則仍然會將該網站計入該時間範圍內的作用中網站總數。  <br/> |
|Timeframe  <br/> |此欄有日期值。當做行事曆表格的多對一關係使用。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>資料表格-租使用者 OneDrive 使用方式

此表格提供 OneDrive 帳戶的相關資料，例如，帳戶數目、OneDrive 帳戶上的文件數目、所使用的儲存空間、依活動類型計算的檔案計數。 商務用 OneDrive 帳戶的月底狀態會在此表格中表示。 例如，如果使用者建立了五個使用 10 MB 儲存區的檔，然後刪除少量的檔案，然後再新增一些檔案，使其在月末會有七個使用五 MB 儲存空間的檔案，則在當月結束時，此表格中會呈現 month 值的結尾。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|SiteType  <br/> |值為 "OneDrive"。  <br/> |
|TotalSites  <br/> |在時間範圍結束時存在的商務用 OneDrive 帳戶數目。  <br/> |
|DocumentCount  <br/> |在時間範圍結束時，所有商務用 OneDrive 帳戶上存在的文件總數。  <br/> |
|Diplansed  <br/> |在時間範圍結束時，所有 OneDrive 帳戶總使用的儲存空間總計。  <br/> |
|ActivityType  <br/> |記錄各種類型檔案活動 (任何/作用中的檔案/共用 EXT 的檔案/INT/同步處理的檔案) 的帳戶數目。  <br/> 任何都可以代表所執行的任何檔案活動  <br/> |
|SitesWithOwnerActivities  <br/> |作用中商務用 OneDrive 帳戶的數目，其中帳戶擁有者會在自己的帳戶上執行特定的檔案活動。  <br/> |
|SitesWithNonOwnerActivities  <br/> |商務用 OneDrive 帳戶的計數，其中帳戶擁有者以外的使用者會在其上執行檔案活動。  <br/> |
|ActivityTotalSites  <br/> |在時間範圍期間記錄任何活動的商務用 OneDrive 帳戶數目。如果商務用 OneDrive 帳戶的活動在時間範圍內稍早的時候，而且在時間範圍結束時遭到刪除，則仍然會將該帳戶計入該時間範圍內的作用中商務用 OneDrive 帳戶。  <br/> |
|Timeframe  <br/> |此欄有日期值。當做行事曆表格的多對一關係使用。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>資料表格-租使用者 Microsoft 365 群組使用量

此表格提供有關如何在整個組織中使用 Microsoft 365 群組的資料。
  
****

|**資料行名稱**|**欄說明**|
|:-----|:-----|
|時間  <br/> |月份值。每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|GroupType  <br/> |群組 (private/public/any) 的類型。  <br/> |
|TotalGroups  <br/> |每個群組類型中的群組數目。  <br/> |
|ActiveGroups  <br/> |作用中的群組數目。  <br/> |
|MBX_TotalGroups  <br/> |信箱群組數目。  <br/> |
|MBX_ActiveGroups  <br/> |主動信箱群組數目。  <br/> |
|MBX_TotalActivities  <br/> |信箱活動的數目。  <br/> |
|MBX_TotalItems  <br/> |信箱專案數目。  <br/> |
|MBX_StorageUsed  <br/> |使用的信箱儲存數量。  <br/> |
|SPO_TotalGroups  <br/> |SharePoint 群組數目。  <br/> |
|SPO_ActiveGroups  <br/> |作用中 SharePoint 群組數目。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |具有檔案存取活動的 SharePoint 群組數目。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |具有檔同步處理活動的 SharePoint 群組數目。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |在內部進行共用活動的 SharePoint 群組數目，或與可能包含外部使用者) 的群組 (的數目。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |已共用外部活動的 SharePoint 群組數目。  <br/> |
|SPO_TotalActivities  <br/> |SharePoint 活動的數目。  <br/> |
|SPO_FileAccessedActivities  <br/> |SharePoint 檔案存取活動的數目。  <br/> |
|SPO_FileSyncedActivities  <br/> |SharePoint 檔同步處理的活動數目。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |內部 SharePoint 檔案共用活動的數目，或使用可能包含外部成員) 的群組 (。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |共用外部活動的 SharePoint 檔案數目。  <br/> |
|SPO_TotalFiles  <br/> |SharePoint 檔的數目。  <br/> |
|SPO_ActiveFiles  <br/> |作用中 SharePoint 檔案數目。  <br/> |
|SPO_StorageUsed  <br/> |使用的 SharePoint 儲存量數量。  <br/> |
|YAM_TotalGroups  <br/> |Yammer 群組數目。  <br/> |
|YAM_ActiveGroups  <br/> |作用中 Yammer 群組數目。  <br/> |
|YAM_LikedActiveGroups  <br/> |具有類似活動的 Yammer 群組數目。  <br/> |
|YAM_PostedActiveGroups  <br/> |具有開機自檢活動的 Yammer 群組數目。  <br/> |
|YAM_ReadActiveGroups  <br/> |具有讀取活動的 Yammer 群組數目。  <br/> |
|YAM_TotalActivities  <br/> |Yammer 活動的數目。  <br/> |
|YAM_LikedActivities  <br/> |Yammer 類似活動的數目。  <br/> |
|YAM_PostedActivties  <br/> |Yammer 開機自檢活動的數目。  <br/> |
|YAM_ReadActivites  <br/> |Yammer 讀取活動的數目。  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>資料表格 - 租用戶 Office 啟用

此表格提供有關整個服務方案中的 Office 訂閱啟用數目的資料，例如，針對企業、Visio Project 的 Microsoft 365 Apps。 它也會提供每個裝置 (Android/iOS/Mac/PC) 啟用次數的相關資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|ServicePlanName  <br/> |服務方案名稱值和裝置啟用計數的清單，如下欄所述。  <br/> |
|TotalEnabled  <br/> |每個服務方案名稱在時間範圍結束前啟用的使用者數目。  <br/> |
|TotalActivatedUsers  <br/> |已在時間範圍結束前啟用每個服務方案的使用者數目。  <br/> |
|AndroidCount  <br/> |Android 裝置的每個服務方案在時間範圍結束前的啟用次數。  <br/> |
|iOSCount  <br/> |iOS 裝置的每個服務方案在時間範圍結束前的啟用次數。  <br/> |
|MacCount  <br/> |MAC 裝置的每個服務方案在時間範圍結束前的啟用次數。  <br/> |
|PcCount  <br/> |PC 裝置的每個服務方案在時間範圍結束前的啟用次數。  <br/> |
|WinRtCount  <br/> |Windows Mobile 裝置的每個服務方案在時間範圍結束前的啟用次數。  <br/> |
|Timeframe  <br/> |此欄有日期值。當做行事曆表格的多對一關係使用。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
