---
title: Microsoft 365 使用情況分析資料模型
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '了解如何連接至 API 流量分析，並提供每月趨勢使用情況的各種 Microsoft 365 服務。  '
ms.openlocfilehash: d2d08a46ad6bcf3659c78a381ce20d99ea805ac7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251904"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 使用情況分析資料模型

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365 使用狀況分析資料表的資料

Microsoft 365 使用情況分析連接至公開多維度資料模型的 API。 API 是預覽版，可在 `https://reports.office.com/pbi/v1.0/\<tenantid\>` (將 \<租用戶識別碼\> 取代為您的租用戶 GUID) 存取。 
  
> [!NOTE]
> 如需詳細資訊，請參閱[使用 Microsoft Graph 中的 Microsoft 365 使用情況報告](https://go.microsoft.com/fwlink/p/?linkid=864336)。 
  
此 API 提供相關資訊的每月趨勢使用情況的各種 Microsoft 365 服務。 如需 API 傳回的確切資料，請參閱下一節中的表格。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 報告 API 所傳回的資料表格

|**表格名稱**|**表格中的資訊**|**日期範圍**|
|:-----|:-----|:-----|
|租用戶產品使用情況  <br/> |包含已啟用的使用者、作用中使用者、每月保留的使用者、初次使用的使用者，以及累計作用中使用者的每月總數。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶產品活動  <br/> |包含活動以及產品內各種活動之作用中使用者計數的每月總數。  <br/> 如需產品內此資料表格中傳回活動的相關資訊，請參閱[作用中使用者定義](active-user-in-usage-reports.md)。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶 Office 授權  <br/> |包含指派給使用者之 Microsoft Office 訂閱數的相關資料  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|租用戶信箱使用量  <br/> |包含使用者信箱的相關資料，也就是信箱總數及儲存空間使用方式。  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|租用戶用戶端使用量  <br/> |包含主動使用特定用戶端/裝置連線到 Exchange Online、商務用 Skype 和 Yammer 之使用者數目的相關資料。  <br/> |包含 12 個月期間內每月彙總的資料，包括目前部分月份。  <br/> |
|租用戶 SharePoint Online 使用量  <br/> |包含 SharePoint 網站 (涵蓋小組或群組網站) 的相關資料，例如網站總數、網站上的文件數目、依活動類型計算的檔案計數，以及使用的儲存空間。  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|租用戶商務用 OneDrive 使用量  <br/> |包含 OneDrive 帳戶的相關資料，例如帳戶數目、OneDrive 上的文件數目、使用的儲存空間、依活動類型計算的檔案計數。  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|租用戶 Microsoft 365 的群組使用方式  <br/> |包含 Microsoft 365 群組使用方式，包括信箱、 SharePoint 和 Yammer 相關資料。  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|租用戶 Office 啟用  <br/> |包含 Office 訂閱啟用次數、每一個裝置 (Android/iOS/Mac/PC) 的啟用計數、依服務方案 (例如 Office 專業增強版、Visio、Project) 計算之啟用次數的相關資料。  <br/> |包含 12 個月期間內的月底狀態資料，包括目前部分月份。  <br/> |
|使用者狀態  <br/> |包含使用者的相關中繼資料，包括使用者顯示名稱、指派的產品、地點、部門、職稱、公司。此資料與上一個完整月份期間獲指派授權的使用者有關。每個使用者都會以唯一的使用者識別碼表示。  <br/> |此資料與上一個完整月份期間指派授權的使用者有關。  <br/> |
|使用者活動  <br/> |包含授權使用者執行活動的每個使用者層級資訊。  <br/> 如需產品內此資料表格中傳回活動的相關資訊，請參閱[作用中使用者定義](active-user-in-usage-reports.md)。  <br/> |此資料與上一個完整月份期間在任何服務中執行活動的使用者有關。  <br/> |
   
展開下列各節，以查看每個資料表格的詳細資訊。
  
### <a name="data-table---user-state"></a>資料表格 - 使用者狀態

此表格針對在上一個完整月份期間獲指派授權的所有使用者，提供使用者層級的詳細資料。它會從 Azure Active Directory 匯入資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|UserId  <br/> |代表使用者，而且可以使用資料集內的其他資料表格加入的唯一使用者識別碼。  <br/> |
|Timeframe  <br/> |此表格內含資料的月份值。  <br/> |
|UPN  <br/> |使用者主體名稱，可唯一識別能夠使用其他外部資料來源加入的使用者。  <br/> |
|DisplayName  <br/> |使用者的顯示名稱。  <br/> |
|IDType  <br/> |如果使用者是使用 Yammer 識別碼或 0，如果他們使用其 Microsoft 365 識別碼連線至 Yammer 連線的 Yammer 使用者識別碼類型設定為 1  <br/> 值為 1 時，表示此使用者連線至 Yammer 使用 Yammer 識別碼，而非其 Microsoft 365 id  <br/> |
|HasLicenseEXO  <br/> |如果使用者有獲指派授權，而且可以使用 Exchange，則設為 true。  <br/> |
|HasLicenseODB  <br/> |如果使用者有獲指派授權，而且可以使用商務用 OneDrive，則設為 true。  <br/> |
|HasLicenseSPO  <br/> |如果使用者有獲指派授權，而且可以使用 SharePoint Online，則設為 true。  <br/> |
|HasLicenseYAM  <br/> |如果使用者有獲指派授權，而且可以使用 Yammer，則設為 true。  <br/> |
|HasLicenseSFB  <br/> |如果使用者有獲指派授權，而且可以使用商務用 Skype，則設為 true。  <br/> |
|HasLicenseTeams  <br/> |設為 true 如果使用者已獲指派授權，並讓其使用 Microsoft Teams。  <br/> |
|Company  <br/> |在 Azure Active Directory 中表示此使用者的公司資料。  <br/> |
|Department  <br/> |在 Azure Active Directory 中表示此使用者的部門資料。  <br/> |
|LocationCity  <br/> |在 Azure Active Directory 中表示此使用者的城市資料。  <br/> |
|LocationCountry  <br/> |在 Azure Active Directory 中表示此使用者的國家/地區資料。  <br/> |
|LocationState  <br/> |在 Azure Active Directory 中表示此使用者的州資料。  <br/> |
|LocationOffice  <br/> |使用者的辦公室。  <br/> |
|Title  <br/> |在 Azure Active Directory 中表示此使用者的職稱資料。  <br/> |
|Deleted  <br/> |如果使用者已從 Microsoft 365 中的上一個完整月份刪除，則為 true。  <br/> |
|DeletedDate  <br/> |從 Microsoft 365 刪除使用者時的日期。  <br/> |
|YAM_State  <br/> |使用者在 Yammer 系統中的狀態，可以是作用中、已刪除或已暫停。  <br/> |
|YAM_ActivationDate  <br/> |使用者在 Yammer 中進入作用中狀態的日期。  <br/> |
|YAM_DeletionDate  <br/> |使用者在 Yammer 中進入已刪除狀態的日期。  <br/> |
|YAM_SuspensionDate  <br/> |使用者在 Yammer 中進入已暫停狀態的日期。  <br/> |
   
### <a name="data-table---user-activity"></a>資料表格 - 使用者活動

此表格包含上個月在任何服務中有活動之每個使用者的相關資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|UserID  <br/> |代表使用者，而且可以使用資料集內的其他資料表格加入的唯一使用者識別碼。  <br/> |
|IDType  <br/> |如果使用者是使用 Yammer 識別碼或 0，如果他們使用其 Microsoft 365 識別碼連線至 Yammer 連線的 Yammer 使用者識別碼類型設定為 1  <br/> 值為 1 時，表示此使用者連線至 Yammer 使用 Yammer 識別碼，而非其 Microsoft 365 id  <br/> |
|Timeframe  <br/> |此表格表示有資料的月份值。  <br/> |
|EXO_EmailSent  <br/> |已傳送的電子郵件數目。  <br/> |
|EXO_EmailReceived  <br/> |已接收的電子郵件數目。  <br/> |
|EXO_EmailRead  <br/> |使用者執行之已讀取電子郵件活動的次數，這可能是多次讀取已讀取的電子郵件，或先前收到的電子郵件。  <br/> |
|EXO_AppointmentCreated  <br/> |約會建立數目。  <br/> |
|EXO_MeetingAccepted  <br/> |接受會議數目。  <br/> |
|EXO_MeetingCancelled  <br/> |取消會議數目。  <br/> |
|EXO_MeetingDeclined  <br/> |拒絕會議數目。  <br/> |
|EXO_MeetingSent  <br/> |傳送的會議數目。  <br/> |
|ODB_FileViewedModified  <br/> |此使用者在任何商務用 OneDrive 上互動的檔案數目 (例如建立、更新、刪除、檢視或下載)。  <br/> |
|ODB_FileSynched  <br/> |此使用者在任何商務用 OneDrive 上同步處理的檔案數目。  <br/> |
|ODB_FileSharedInternally  <br/> |此使用者從內部共用任何 OneDrive for Business，或與使用者群組 （也可能會包括外部使用者） 內的檔案數目。  <br/> |
|ODB_FileSharedExternally  <br/> |此使用者從任何商務用 OneDrive 外部共用的檔案數目。  <br/> |
|ODB_AccessByOwner  <br/> |使用者與自己的商務用 OneDrive 上檔案互動的檔案數目。  <br/> |
|ODB_AccessOthers  <br/> |使用者與其他使用者的商務用 OneDrive 上檔案互動的檔案數目。  <br/> |
|SPO_GroupFileViewedModified  <br/> |與此使用者在任何群組網站上互動的檔案數目。  <br/> |
|SPO_GroupFileSynched  <br/> |此使用者在任何群組網站上同步處理的檔案數目。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |與組織內的使用者或群組 （也可能會包括外部使用者） 內的使用者共用的檔案計數。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |此使用者從任何群組網站外部共用的檔案數目。  <br/> |
|SPO_GroupAccessByOwner  <br/> |使用者與自己的群組網站上檔案互動的檔案數目。  <br/> |
|SPO_GroupAccessByOthers  <br/> |使用者與其他使用者的群組網站上檔案互動的檔案數目。  <br/> |
|SPO_OtherFileViewedModified  <br/> |與此使用者互動的任何其他網站上的檔案數目。  <br/> |
|SPO_OtherFileSynched  <br/> |此使用者從任何其他網站同步處理的檔案數目。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |此使用者從任何其他網站，或與使用者群組 （也可能會包括外部使用者） 內內部共用檔案的數目。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |此使用者從任何其他網站外部共用檔案的數目。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |使用者互動位於其所擁有的其他網站的網站數目。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |擁有的網站與使用者互動位於其他網站的另一位使用者數目。  <br/> |
|SPO_TeamFileViewedModified  <br/> |與此使用者在任何小組網站上互動的檔案數目。  <br/> |
|SPO_TeamFileSynched  <br/> |此使用者從任何小組網站同步處理的檔案數目。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |此使用者從任何小組網站，或與使用者群組 （也可能會包括外部使用者） 內內部共用檔案的數目。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |此使用者從任何小組網站外部共用的檔案數目。  <br/> |
|SPO_TeamAccessByOwner  <br/> |使用者與自己的小組網站上檔案互動的檔案數目。  <br/> |
|SPO_TeamAccessByOthers  <br/> |使用者與其他使用者的小組網站上檔案互動的檔案數目。  <br/> |
|Teams_ChatMessages  <br/> |聊天傳送的訊息數。  <br/> |
|Teams_ChannelMessage  <br/> |張貼到通道訊息數目。  <br/> |
|Teams_CallParticipate  <br/> |使用者參與的通話數。  <br/> |
|Teams_MeetingParticipate  <br/> |使用者加入的會議數目。  <br/> |
|Teams_HasOtherAction  <br/> |布林值，如果使用者在 Microsoft Teams 中執行其他動作。  <br/> |
|YAM_MessagePost  <br/> |此使用者張貼的 Yammer 訊息數目。  <br/> |
|YAM_MessageLiked  <br/> |此使用者按讚的 Yammer 訊息數目。  <br/> |
|YAM_MessageRead  <br/> |此使用者已讀取的 Yammer 訊息數目。  <br/> |
|SFB_P2PSummary  <br/> |此使用者參與的對等工作階段數目。  <br/> |
|SFB_ConfOrgSummary  <br/> |此使用者組織的會議工作階段數目。  <br/> |
|SFB_ConfPartSummary  <br/> |此使用者參與的會議工作階段數目。  <br/> |
   
### <a name="data-table---tenant-product-usage"></a>資料表格 - 租用戶產品使用情況

下表提供月份月採用資料中的啟用作用中、 傳回及初次使用使用者的 Microsoft 365 內每項產品。 Microsoft 365 值代表中任一項產品作用中的使用狀況。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|Product  <br/> |摘要說明其使用情況資訊的產品名稱。 在 [產品] 欄中的 Microsoft 365 值代表跨任何產品活動  <br/> |
|Timeframe  <br/> |月份值。每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|EnabledUsers  <br/> |可在時間範圍值內使用產品的使用者數目，如果在月份中的部分啟用使用者，則仍會計算在內。  <br/> |
|Activeusers 工作負載  <br/> |在時間範圍值內，執行產品中刻意活動的使用者數目。  <br/> A user is counted as active for a product in a particular month, if they have performed one of the key activities in the product. The key activities are available in the **Tenant Product Activity** table.  <br/> |
|CumulativeActiveUsers  <br/> |可使用產品，而且自新的使用情況系統開始收集資料起，已在時間範圍月份內至少使用一次產品的使用者數目。  <br/> |
|MoMReturningUsers  <br/> |在時間範圍月份內有效，且在上一個月也有效的使用者數目。  <br/> |
|FirstTimeUsers  <br/> |自新的使用情況系統開始收集資料起，在時間範圍內第一次成為作用中使用者的使用者數目。  <br/> 如果我們自這個新的報告系統開始收集資料起，第一次偵測到使用者的活動，則會將該使用者計入特定月份的初次使用者。一旦計入初次使用者之後，即使此使用者在其活動中有很大的差距，還是不會再將他們計入初次使用者  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>資料表格 - 租用戶產品活動

此表格提供活動以及產品內各種活動之作用中使用者計數的每月總數。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|Timeframe  <br/> |月份值。每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|Product  <br/> |在 Microsoft 365 使用情況都能取得資料的產品名稱。  <br/> |
|Activity  <br/> |產品中用來展現產品使用中的活動名稱。  <br/> |
|ActivityCount  <br/> |這是針對產品內所有作用中使用者執行的每個活動計算的動作總數。  <br/> **注意：** 若是 SharePoint Online 和商務用 OneDrive 活動，此值代表與使用者互動的不同文件數目。  <br/> |
|ActiveUserCount  <br/> |已在產品內執行活動的使用者數目。  <br/> |
|TotalDurationInMinute  <br/> |在適用的商務用 Skype 活動中，使用音訊或視訊工作階段之所有作用中使用者持續使用的分鐘數。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>資料表格 - 租用戶信箱使用量

此表格是由擁有使用者信箱之所有授權 Exchange Online 使用者的摘要資料所組成。其中包含所有使用者信箱的月底狀態。此表格在多個月份內的資料不具有累計性。此表格中最新月份的資料代表最新的狀態。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|TotalMailboxes  <br/> |Microsoft 365 訂用帳戶的使用者信箱數目。  <br/> |
|IssueWarningQuota  <br/> |在所有使用者信箱中發出警告的配額總計。  <br/> |
|ProhibitSendQuota  <br/> |在所有使用者信箱中禁止傳送的配額總計。  <br/> |
|ProhibitSendReceiveQuota  <br/> |在所有使用者信箱中禁止傳送接收配額的配額總計。  <br/> |
|TotalItemBytes  <br/> |所有使用者信箱所使用的儲存空間量 (以位元組為單位)。  <br/> |
|MailboxesNoWarning  <br/> |在儲存空間警告限制之下的使用者信箱數目。  <br/> |
|MailboxesIssueWarning  <br/> |針對儲存空間配額發出警告的使用者信箱數目。  <br/> |
|MailboxesExceedSendQuota  <br/> |已超過傳送配額的使用者信箱數目。  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |已超過傳送/接收配額的使用者信箱數目。  <br/> |
|DeletedMailboxes  <br/> |在時間範圍內刪除的使用者信箱數目。  <br/> |
|Timeframe  <br/> |月份值。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>資料表格 - 租用戶用戶端使用量

下表將針對使用者要用來連線至 Exchange Online、商務用 Skype 和 Yammer 的用戶端，提供每月摘要資料。此表格還沒有適用於 SharePoint Online 和商務用 OneDrive 的用戶端使用資料。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|產品  <br/> |Microsoft 365 內的用戶端使用狀況資料可用的產品名稱。  <br/> |
|ClientId  <br/> |用來連線至產品之每個裝置的名稱。  <br/> |
|UserCount  <br/> |使用每個產品適用之每個用戶端的使用者數目。  <br/> |
|Timeframe  <br/> |月份值  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>資料表格 - 租用戶 SharePoint Online 使用量

此表格包含 SharePoint Online 網站使用量或活動的每月相關摘要資料。這只涵蓋小組網站與群組網站。SharePoint Online 網站的月底狀態會在此欄中表示，例如，如果使用者建立了 5 個文件，並使用 10 MB 做為總儲存空間，然後刪除一些檔案，並新增其他檔案，如此檔案的月底狀態總計為 7 (使用 5 MB 的儲存空間)，則此表格中所表示的值就是月底狀態。系統會隱藏此表格以避免重複計算彙總，並當做建立兩個參照表格的來源使用。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|鍵入  <br/> |網站類型值 (任何/小組/群組) (任何都可以代表這 2 個網站類型之一)。  <br/> |
|TotalSites  <br/> |在時間範圍結束時存在的網站數目。  <br/> |
|DocumentCount  <br/> |在時間範圍結束時存在網站上的文件總數。  <br/> |
|Diplansed  <br/> |在時間範圍結束時，所有網站上加總的已使用儲存空間總計。  <br/> |
|ActivityType  <br/> |記錄各種類型檔案活動 (任何/作用中的檔案/共用 EXT 的檔案/INT/同步處理的檔案) 的網站數目。  <br/> 任何都可以代表所執行的任何檔案活動。  <br/> |
|SitesWithOwnerActivities  <br/> |作用中網站的數目，其中網站擁有者會在自己的網站上執行特定的檔案活動。  <br/> |
|SitesWithNonOwnerActivities  <br/> |整個月加總的作用中網站數目，其中網站擁有者以外的使用者會在網站上執行特定的檔案活動。  <br/> |
|ActivityTotalSites  <br/> |在時間範圍期間記錄任何活動的網站數目。如果網站的活動在時間範圍內稍早的時候，而且在時間範圍結束時遭到刪除，則仍然會將該網站計入該時間範圍內的作用中網站總數。  <br/> |
|Timeframe  <br/> |此欄有日期值。當做行事曆表格的多對一關係使用。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>資料表格-租用戶 OneDrive 使用量

此表格提供 OneDrive 帳戶的相關資料，例如，帳戶數目、OneDrive 帳戶上的文件數目、所使用的儲存空間、依活動類型計算的檔案計數。商務用 OneDrive 帳戶的月底狀態會在此表格中表示。例如，如果使用者建立了使用 10 MB 儲存空間的 5 個文件，然後刪除一些檔案，並新增其他檔案，如此該使用者在月底有 7 個使用 5 MB 儲存空間的檔案，則此表格會在月底表示月底值。
  
|**欄名稱**|**欄描述**|
|:-----|:-----|
|鍵入  <br/> |值為 "OneDrive"。  <br/> |
|TotalSites  <br/> |在時間範圍結束時存在的商務用 OneDrive 帳戶數目。  <br/> |
|DocumentCount  <br/> |在時間範圍結束時，所有商務用 OneDrive 帳戶上存在的文件總數。  <br/> |
|Diplansed  <br/> |在時間範圍結束時，所有 OneDrive 帳戶上加總的已使用儲存空間總計。  <br/> |
|ActivityType  <br/> |記錄各種類型檔案活動 (任何/作用中的檔案/共用 EXT 的檔案/INT/同步處理的檔案) 的帳戶數目。  <br/> 任何都可以代表所執行的任何檔案活動  <br/> |
|SitesWithOwnerActivities  <br/> |作用中商務用 OneDrive 帳戶的數目，其中帳戶擁有者會在自己的帳戶上執行特定的檔案活動。  <br/> |
|SitesWithNonOwnerActivities  <br/> |商務用 OneDrive 帳戶的計數，其中帳戶擁有者以外的使用者會在其上執行檔案活動。  <br/> |
|ActivityTotalSites  <br/> |在時間範圍期間記錄任何活動的商務用 OneDrive 帳戶數目。如果商務用 OneDrive 帳戶的活動在時間範圍內稍早的時候，而且在時間範圍結束時遭到刪除，則仍然會將該帳戶計入該時間範圍內的作用中商務用 OneDrive 帳戶。  <br/> |
|Timeframe  <br/> |此欄有日期值。當做行事曆表格的多對一關係使用。  <br/> |
|Content Date  <br/> |如果時間範圍顯示目前月份，此值將代表資料在目前月份可供使用的最晚日期。  <br/> 如果時間範圍顯示上個月，此值將代表時間範圍月份的最後一個日期。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>資料表格-租用戶 Microsoft 365 群組使用方式

下表提供有關如何使用 Microsoft 365 群組整個組織的資料。
  
****

|**資料行名稱**|**欄描述**|
|:-----|:-----|
|時間範圍結束前  <br/> |月份值。 每個產品在過去 12 個月內，每個月都會有一列，包括目前部分月份。  <br/> |
|GroupType  <br/> |群組 （私人/公開/任何） 的類型。  <br/> |
|TotalGroups  <br/> |每個群組類型] 中的群組數目。  <br/> |
|ActiveGroups  <br/> |作用中的群組數目。  <br/> |
|MBX_TotalGroups  <br/> |信箱群組數目。  <br/> |
|MBX_ActiveGroups  <br/> |作用中信箱群組數目。  <br/> |
|MBX_TotalActivities  <br/> |信箱活動數目。  <br/> |
|MBX_TotalItems  <br/> |信箱項目數目。  <br/> |
|MBX_StorageUsed  <br/> |信箱儲存空間量。  <br/> |
|SPO_TotalGroups  <br/> |SharePoint 群組數目。  <br/> |
|SPO_ActiveGroups  <br/> |作用中的 SharePoint 群組數目。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |具有檔案存取的活動的 SharePoint 群組數目。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |這有檔案同步處理的活動的 SharePoint 群組數目。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |就內部而言，共用活動的 SharePoint 群組或與群組 （也可能會包括外部使用者） 的數量。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |具有外部共用活動的 SharePoint 群組數目。  <br/> |
|SPO_TotalActivities  <br/> |SharePoint 活動數目。  <br/> |
|SPO_FileAccessedActivities  <br/> |數字的 SharePoint 檔案存取活動。  <br/> |
|SPO_FileSyncedActivities  <br/> |數字的 SharePoint 檔案同步處理活動。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |內部，或與 （，其中可能包含外部成員） 的群組活動共用 SharePoint 檔案的數目。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |外部共用活動的 SharePoint 檔案數目。  <br/> |
|SPO_TotalFiles  <br/> |SharePoint 檔案數目。  <br/> |
|SPO_ActiveFiles  <br/> |使用中的 SharePoint 檔案數目。  <br/> |
|SPO_StorageUsed  <br/> |SharePoint 使用的儲存空間量。  <br/> |
|YAM_TotalGroups  <br/> |Yammer 群組的數目。  <br/> |
|YAM_ActiveGroups  <br/> |作用中的 Yammer 群組的數目。  <br/> |
|YAM_LikedActiveGroups  <br/> |Yammer 群組有類似的活動數目。  <br/> |
|YAM_PostedActiveGroups  <br/> |Yammer 群組有 post 活動數目。  <br/> |
|YAM_ReadActiveGroups  <br/> |Yammer 群組已讀取活動數目。  <br/> |
|YAM_TotalActivities  <br/> |Yammer 活動數目。  <br/> |
|YAM_LikedActivities  <br/> |Yammer 的類似活動的數目。  <br/> |
|YAM_PostedActivties  <br/> |Yammer 文章活動數目。  <br/> |
|YAM_ReadActivites  <br/> |讀取活動的 Yammer 數目。  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>資料表格 - 租用戶 Office 啟用

此表格會針對服務方案 (例如 Office 專業增強版、Visio、Project)，提供 Office 訂閱啟用次數的相關資料。它也會提供每個裝置 (Android/iOS/Mac/PC) 啟用次數的相關資料。
  
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
   

