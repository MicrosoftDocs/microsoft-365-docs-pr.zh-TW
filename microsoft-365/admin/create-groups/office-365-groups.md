---
title: 系統管理員的 Office 365 群組概觀
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解 Office 365 群組。
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239174"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>系統管理員的 Office 365 群組概觀

Office 365 群組是在整個 Microsoft 365 的磁碟機所有團隊合作置於成員資格服務。 與 Office 365 群組，您可以授與一群人存取這些人共用的共同作業資源的集合。 這些資源，包括：

- 共用的 Outlook 收件匣
- 共用行事曆
- SharePoint 文件庫
- 會議規劃
- Power BI
- Yammer （如果群組當初用來建立 Yammer）
- 小組 （如果群組已建立從 microsoft Teams）
- 藍圖 （如果您有 web 專案）

與 Office 365 群組，您不需要以手動方式將權限指派給每個這些資源，因為新增至群組的成員會自動提供給他們所需的權限群組提供的工具。

Office 365 中的任何使用者可以建立群組，除非您[限制群組建立一組特定的人員](manage-creation-of-groups.md)。 請注意，是否您限制建立群組，無法建立群組的使用者將無法建立 SharePoint 網站、 規劃人員或團隊。 這些服務必須能夠使用建立群組的使用者內容。 使用者仍可以參與群組活動，例如在 Planner 中建立工作，或回應交談在 Outlook 中，提供他們是群組的成員。

群組擁有下列角色：

- **擁有者**群組擁有者可以新增或移除成員及擁有獨特的權限，像是從共用收件匣中刪除交談，或變更群組的相關的不同設定的能力。 群組擁有者可以重新命名群組，請更新描述或圖片等等。
- **成員**的成員可以存取在] 群組中的所有項目，但不能變更群組設定。
- **來賓**-群組來賓都是來自組織外部的成員。 預設群組成員可以邀請來賓加入您的群組，但是您可以[控制設定](manage-guest-access-in-groups.md)。

只有全域系統管理員和使用者管理系統管理員可以建立及管理在系統管理中心中的群組。 您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。

身為管理員，您可以：

- [指定誰可以建立群組](manage-creation-of-groups.md)
- [在您的組織中建立群組命名原則](groups-naming-policy.md)
- [選擇 [建立群組時要使用哪一個網域](choose-domain-to-create-groups.md)
- [管理群組的來賓存取](manage-guest-access-in-groups.md)
- [復原已刪除的群組](restore-deleted-group.md)（位於內的 [刪除的 30 天）

如果您偏好使用更自動化的方式來管理您的 Office 365 群組的生命週期您可以在特定時間間隔到期群組使用到期原則。 群組的擁有者會收到密碼，讓他們能輕鬆地更新 「 群組，如果仍然需要群組到期前，電子郵件 30 度、 15 和 1 天。 請參閱： [Office 365 群組到期原則](office-365-groups-expiration-policy.md)。

您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)來管理您的群組。

如果您有許多使用者，例如中大型公司或企業版，您可能有多位使用者能夠建立各種用途的群組。 我們強烈建議您檢閱[ Plan for Office 365 群組中的控管](plan-for-groups-governance.md)的最佳作法。

## <a name="group-limits"></a>群組限制

下列限制適用於 Office 365 群組：

|最大值...]|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|群組的系統管理員可以建立|最多 500 K 個預設租用戶限制|
|Number of members |超過 1000 個，但僅 1000 可以存取群組交談同時。 <br>存取行事曆及極大型的群組，在 Outlook 中的交談時，使用者可能會注意到的延遲。|
|使用者可以是成員的群組數目|1,000|
|檔案存放區|1 Tb + 每個訂閱的使用者 + 購買任何額外儲存空間的 10 GB。 您可以購買 unlimited 額外儲存空間量。|
|群組信箱大小|50 GB|

目前每個 Office 365 組織預設的 Office 365 群組數量上限為 500,000 個，但可依要求再增加。 如需有關 Office 365 群組限制的詳細資訊，請參閱[Office 365 群組-系統管理說明](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

當您有可採取行動的群組使用方式資訊時，管理您的 Office 365 群組會更有效率。 在 Microsoft 365 系統管理中心有報告工具，可讓您查看等儲存使用中，多少作用中群組，您必須與您的使用者甚至是如何使用群組。 如需詳細資訊，請參閱：[在系統管理中心的 Office 365 報告](../activity-reports/office-365-groups.md)。

## <a name="which-office-365-plans-include-groups"></a>哪些 Office 365 方案包含群組？

任何具有 Exchange Online 和 SharePoint Online 的 Office 365 訂閱會支援群組。 包含商務基本版和商務進階版方案和企業版 E1、 E3 和 E5 方案。 上建立的群組 （也稱為 「 組合管理 」 的群組） 之人員的授權，通訊群組。 只要召集人有適當的權限的任何功能您想要有的群組，該授權會傳達給群組。

> [!NOTE]
> 如需有關 Office 365 服務系列與方案的詳細資訊，請檢查[Office 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

如果您具有您仍然可以取得的共用收件匣與共用行事曆功能僅限 Exchange 的計劃中 Outlook，但您的群組不會收到文件庫、 Planner 或任何其他功能。

Office 365 群組的運作方式與 Azure Active Directory (AAD)。 您要取得的群組功能取決於哪些 Azure Active Directory 訂閱上您有，並查看授權指派給組合管理] 群組。

> [!IMPORTANT]
> 所有的群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組有指派給他們的 AAD P1 授權。 授權不強制執行。
> 定期我們會產生流量報告，告訴您哪些使用者遺失授權，並且需要指派給它們是相容的授權需求。 例如，假設使用者沒有授權和他們已新增至群組命名原則強制執行的位置。 報表會標示為您所需的授權。

## <a name="related-articles"></a>相關文章

[了解 Office 365 群組](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[通訊群組清單升級至 Office 365 群組](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Office 365 群組](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
