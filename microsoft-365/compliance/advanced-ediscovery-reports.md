---
title: 高級 eDiscovery 報告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 387709ebdd84968d2b93992f6b92ef1548117569
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528356"
---
# <a name="advanced-ediscovery-reports-preview"></a>高級 eDiscovery 報告（預覽）

高級 eDiscovery 報告可協助您在整個組織中匯總案例資料，以簡化資料分析和組織報告。 「高級 eDiscovery 報告」功能包含數個內建報告，可協助您回答如下的問題：

- 在我的組織中，所有情況都有多少個主動保管人？

- 組織中所有案例的資料來源保留數目為何？

- 在我的組織中所有案例的最後一個月內，已發出多少保留通知？

- 組織中有多少作用中和封閉式案例？

## <a name="before-you-begin"></a>開始之前

- 若要存取高級 eDiscovery 報告，您必須是 eDiscovery 系統管理員角色群組的成員。 成為此角色群組的成員，可為您提供在報告中查看、篩選和匯出資料的必要許可權。 如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。

- 每天都會刷新高級 eDiscovery 報告。 因此，當新案例、保管人、資料來源及通訊建立時，以及在對應的報告中顯示時，可能會發生延遲。

存取高級 eDiscovery 報告：

1. 請移至 https://protection.office.com
  
2. 使用您的公司或學校帳戶登入 Office 365。
  
3. 在 [安全性 & 規範中心] 中，按一下 [ **eDiscovery > Advanced ediscovery**。
  
   在 [ **Advanced eDiscovery** ] 首頁上，案例、保管人、資料來源及通訊報告索引標籤都顯示在頁面頂端。 
  
   ![首頁上的高級 eDiscovery 報告](../media/report-home.png)

5. 若要查看報告，請按一下 [報告] 索引標籤，必要時您可以執行下列其中一項動作：

   ![您可以篩選或下載報表資料](../media/AeDReportsFilterDownload.png)

   a. 按一下 [**篩選**] 以縮小報表資料。 您可以針對每個報告篩選不同的屬性。
  
   b. 按一下 [**下載到 csv** ]，將報告資料匯出至 csv 檔案。

## <a name="case-report"></a>案例報告

案例報告會匯總組織中主動和封閉式預先探索案例的相關資訊。

|欄        |描述|
|:-------------|:-------------|
|案例識別碼 | 每個案例的唯一識別碼。| 
|案例名稱 | 案例的使用者定義名稱。|
|狀態 | 會指出案例是否為使用中或已關閉狀態。|
|建立日期 |案例建立的第一天。 日期是 UTC 格式。|
|上次修改日期 |案例已關閉或上次更新的日期。 日期是 UTC 格式。| 
|||

## <a name="custodian-report"></a>保管人報告

在 eDiscovery 工作流程中，法律案例或調查主旨的個人稱為「*資料保管人*」（或僅限*保管人*），而且會定義為「具有檔或電子檔的系統管理控制權」的人員。 保管人報告可協助您識別組織中所有案例的資料來源是保留狀態的所有保管人。

|欄         |描述|
|:-------------|:-------------|
|保管人名稱| Active Directory 中的保管人名稱。|
|保管人 UPN | 管理員的使用者主體名稱。|
|保管人識別碼 | 指定案例內管理員的唯一識別碼。 |
|案例名稱 | 案例的使用者定義名稱。|
|保留狀態 | 會指出系統管理員目前是否正在暫止狀態，或是否已從案例中發放。|
|案例識別碼 | 案例的唯一識別碼。|
|通訊狀態 |會指出保管人是否已發出合法保留通知。 |
|已新增保管人 | 管理員加入案例的日期。 日期是 UTC 格式。|
|||

## <a name="data-source-report"></a>資料來源報告

您可以使用 Advanced eDiscovery 案例來建立保留，以保留可能與案例相關的內容。 使用「高級 eDiscovery 保留」功能，您可以將保留置於保管人及其資料來源。 此外，您可以對信箱和 OneDrive 的商務帳戶進行非 custodial 保留。 您可以使用 [資料來源] 報告，針對組織中的所有案例，匯總有關保留內容位置的詳細資料。

|欄        |描述|
| -------------|-------------|
|案例識別碼 |每個案例的唯一識別碼。 |
|工作負載 |會指出置於保留狀態的內容位置類型（例如，Exchange 或 SharePoint）。
|位置名稱 |表示內容位置的 SMTP 位址（適用于 Exchange 信箱）或 URL （SharePoint 網站）。 | 
|保管人識別碼 |如果資料來源屬於保管人，此欄位會顯示在指定的情況下，管理員的唯一識別碼。 對於非 custodial 位置，此欄會是 null。|
|保管人名稱 |Active Directory 中的保管人名稱。| 
|案例名稱 |案例的使用者定義名稱。| 
|狀態 |會指出內容位置目前是否處於保留狀態。 | 
|保留原則識別碼 |包含內容位置之保留的唯一識別碼。 | 
|保留建立日期 |會指出保留原則的建立日期。 日期是 UTC 格式。 | 
|保留原則名稱 |包含內容位置之保留的名稱。 |
|保留修改日期 |上次修改保留的日期。 日期是 UTC 格式。| 
|保留上次修改者|上次修改保留之使用者的名稱。| 
|||

## <a name="communication-report"></a>通訊報告

您的組織可能會發出法律封存通知，以通知保管人在法律案例或調查過程中，將相關資訊保留在法律上的義務。 您可以使用通訊報告來查看有關確認、提醒、升級和其他通訊類型的匯總資料。

|欄         |描述|
| -------------|-------------|
|案例識別碼 | 案例的唯一識別碼。|
|案例名稱 | 案例的使用者定義名稱。|
|保管人識別碼 |在指定的情況下，保管人的唯一識別碼。|
|保管人名稱 |管理員的名稱。|
|公告類型 |會指出發出給保管人的通知類型。|
|簽發官 |發出合法保留通知的使用者名稱。|
|Notification 事件|表示傳送給使用者的法律封存通知訊息。 可能的值包括：提醒、升級、確認和保留發佈。|
|傳送日期 |通訊的發行日期。 若為回執，此欄會指出管理員認可的通知時間。 日期是 UTC 格式。|
|||
