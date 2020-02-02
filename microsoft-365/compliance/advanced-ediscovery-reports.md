---
title: 進階電子文件探索報表
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 736117f62877bd0b33ae1007f00d5a32680963fb
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662199"
---
# <a name="advanced-ediscovery-reports-preview"></a>進階電子文件報告 （預覽）

您進階電子文件探索報告說明整個組織簡化資料分析和組織報告彙總案例資料。 進階電子文件報告功能包含幾個內建的報告來協助您回答問題，例如：

- 多少 active custodians 是否有我的組織中的所有案例的？

- 為我的組織中的所有案例，保留多少資料來源位於嗎？

- 多少保留在 [我的組織中的所有案例的最後一個月份已經發出通知？

- 多少作用中及已關閉的情況下我的組織內是否有一些？

## <a name="before-you-begin"></a>開始之前

- 若要存取進階電子文件報告，您必須是 「 eDiscovery 系統管理員角色群組的成員。 這個角色群組的成員所提供的檢視、 篩選及匯出報告資料的必要權限。 如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。

- 進階電子文件報告每日重新整理。 因此，可能會有延遲時建立新的情況下，custodians、 資料來源而言和通訊，它們會出現在對應的報告。

若要存取進階電子文件報告：

1. 請移至 https://protection.office.com
  
2. 登入 Office 365 中，使用您的工作或學校帳戶。
  
3. 在安全性 & 合規性中心，按一下 [ **eDiscovery > 進階電子文件**。
  
   在**進階電子文件探索**首頁] 頁面上，大小寫、 Custodian、 資料來源，以及通訊報表索引標籤會顯示跨頁的最頂端。 
  
   ![在 [首頁] 頁面上的進階電子文件探索報表](media/report-home.png)

5. 若要檢視報表，按一下 [報表] 索引標籤中，，然後視您可以執行下列其中一個下列事項：

   ![您可以篩選或下載報告資料](media/AeDReportsFilterDownload.png)

   a. 按一下 [**篩選器**來縮小報表資料。 您可以篩選每個報表的不同內容。
  
   b. 按一下 [**下載至 CSV** ] 若要將報表資料匯出至 CSV 檔案。

## <a name="case-report"></a>大小寫的報表

Case 報表彙總您組織中的作用中及已關閉事先 eDiscovery 案例的相關資訊。

|欄        |描述|
|:-------------|:-------------|
|大小寫的識別碼 | 每個案例的唯一識別碼。| 
|案例名稱 | 使用者定義的大小寫名稱。|
|狀態 | 會指出作用中或關閉，是否是這種情況。|
|建立日期 |建立這種情況對日期。 日期為 UTC 格式。|
|上次修改日期 |這種情況時已關閉，或上次更新日期。 日期為 UTC 格式。| 
|||

## <a name="custodian-report"></a>Custodian 報表

中的 eDiscovery 工作流程之主旨的法律案件或調查的人稱為*資料 custodians* （或只是*custodians*），且會定義為 「 人員擁有管理控制文件或電子檔案 」。 Custodian 報告可協助您識別所有其資料來源處於 custodians 按住您的組織中的所有案例。

|欄         |描述|
|:-------------|:-------------|
|Custodian 名稱| 在 [Active Directory custodian 名稱。|
|Custodian UPN | Custodian 使用者主體名稱。|
|Custodian 識別碼 | Custodian 內的特定案例的唯一識別碼。 |
|案例名稱 | 案例的使用者定義的名稱。|
|保留狀態 | 會指出是否 custodian 目前保留，或者如果他們已經發行從案例。|
|大小寫的識別碼 | 這種情況的唯一識別碼。|
|通訊狀態 |代表 custodian 是否所發出的合法持有通知。 |
|新增 custodian | Custodian 已新增至案例的日期。 日期為 UTC 格式。|
|||

## <a name="data-source-report"></a>資料來源的報表

您可以使用進階電子文件探索案例來建立保留來保留可能與案件相關的內容。 使用進階電子文件保留功能，您可以將保留 custodians 和其資料來源上。 此外，您可以保留非 custodial 信箱和 OneDrive for 商務用帳戶。 您可以使用資料來源報表彙總的詳細資訊的相關內容位置上的按住您的組織中的所有案例。

|欄        |描述|
| -------------|-------------|
|大小寫的識別碼 |每個案例的唯一識別碼。 |
|工作負載 |會指出處於暫止狀態 （例如 Exchange 或 SharePoint） 的內容位置的類型。
|位置名稱 |會指出 （適用於 Exchange 信箱） 的 SMTP 地址或內容的位置 （適用於 SharePoint 網站） 的 URL。 | 
|Custodian 識別碼 |如果資料來源屬於 custodian，此欄顯示在特定情況下 custodian 的唯一識別碼。 此欄都是 null 非 custodial 的位置。|
|Custodian 名稱 |在 [Active Directory custodian 名稱。| 
|案例名稱 |案例的使用者定義的名稱。| 
|狀態 |會指出內容的位置是否目前保留。 | 
|保留原則識別碼 |保留包含的內容位置的唯一識別碼。 | 
|建立保留日期 |會指出建立保留原則時的日期。 日期為 UTC 格式。 | 
|保留原則名稱 |包含的內容位置的保留名稱。 |
|保留已修改的日期 |保留上次修改日期。 日期為 UTC 格式。| 
|上次修改者的保留|上次修改日期保留使用者的名稱。| 
|||

## <a name="communication-report"></a>通訊報告

您的組織可能會發出通知 custodians 其義務保留一部分法律案件或調查的相關資訊的合法持有通知。 您可以使用通訊報告來檢視通知、 提醒、 擴大，與其他類型的通訊的彙總資料。

|欄         |描述|
| -------------|-------------|
|大小寫的識別碼 | 這種情況的唯一識別碼。|
|案例名稱 | 使用者定義的大小寫名稱。|
|Custodian 識別碼 |在特定情況下 custodian 唯一識別碼。|
|Custodian 名稱 |Custodian 名稱。|
|請注意類型 |會指出至 custodian 所發出的通知的類型。|
|發出長 |發出法律使用者的名稱保留通知。|
|通知事件|會指出傳送給使用者的合法持有通知訊息。 可能的值包括： 提醒、 呈報、 而言，並保留發行。|
|傳送的日期 |通訊時所發行日期。 Acknowledgments，此資料行表示 custodian 已認可通知的時間。 日期為 UTC 格式。|
|||
