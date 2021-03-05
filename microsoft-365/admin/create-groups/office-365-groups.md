---
title: 系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 深入瞭解 Microsoft 365 群組。
ms.openlocfilehash: 75bc743ed8f1965d0ed8a1967e6eac1bd6e0178b
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453678"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)

Microsoft 365 群組是一種基礎成員資格服務，可促進整個 Microsoft 365 的所有團隊合作。 使用 Microsoft 365 群組，您可以讓一組人員能夠存取共用資源的集合。 這些資源包括：

- 共用的 Outlook 收件匣
- 共用行事曆
- SharePoint 文件庫
- Planner
- OneNote 筆記本
- Power BI
- Yammer (如果群組是由 Yammer 建立) 
- 如果群組是從小組建立，則為小組 () 
- 如果您有 web 的專案，則為藍圖 () 
- Stream

使用 Microsoft 365 群組時，您不需要手動指派每個資源的許可權。 將人員新增至群組時，會自動為他們提供所需的許可權。

除非您將 [群組建立限制于一組特定的人員](manage-creation-of-groups.md)，否則任何使用者都可以建立群組。 如果您限制群組的建立，無法建立群組的使用者將無法建立 SharePoint 網站、規劃人員或小組。 這些服務要求建立群組的人員可以建立群組。 使用者仍可參與群組活動，例如在 Planner 中建立工作或使用小組聊天，但前提是群組的成員。

群組具有下列角色：

- **擁有** 者-群組擁有者可以新增或移除成員，並具有獨特的許可權，例如從共用收件匣刪除交談的功能，或變更群組的不同設定。 群組擁有者可以重新命名群組、更新描述或圖片等等。
- **Members** -成員可以存取群組中的所有專案，但無法變更群組設定。 依預設，群組成員可以邀請客人加入您的群組，但您可以 [控制該設定](manage-guest-access-in-groups.md)。
- **來賓** 群組來賓是指來自組織外部的成員。

只有全域系統管理員、使用者管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。 您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。

身為管理員，您可以：

- [指定誰可以建立群組](manage-creation-of-groups.md)
- [為組織中的群組建立命名原則](groups-naming-policy.md)
- [選擇建立群組時所要使用的網域](choose-domain-to-create-groups.md)
- [管理群組的來賓存取](manage-guest-access-in-groups.md)
- 在刪除的30天內，[復原已刪除的群組](restore-deleted-group.md) () 

如果您想要更自動化的方法來管理 Microsoft 365 群組的生命週期，您可以使用到期原則，在特定的時間間隔內到期群組。 群組的擁有者會收到一封電子郵件30、15及1天，允許使用者在仍需要的群組到期時進行更新。 請參閱： [Microsoft 365 群組到期原則](office-365-groups-expiration-policy.md)。

您可以從 Microsoft 365 系統管理中心或 [使用 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)管理您的群組。

如果您有許多使用者，例如在大型公司或企業中，您可能會有許多使用者出於各種目的建立群組。 強烈建議您複查 [Microsoft 365 群組中](plan-for-groups-governance.md) 的控管計畫，以取得最佳作法。

## <a name="group-limits"></a>群組限制

下列限制適用于 Microsoft 365 群組：

|最大。。。|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理員可以建立的群組|最高預設租使用者限制為 500 K|
|Number of members |超過1000，但只有1000可以同時存取群組交談。 <br>使用者可能會注意到當存取 Outlook 中大型群組的行事曆和交談時，會發生延遲。|
|使用者可以是其成員的群組數目|7000|
|檔存放區|每個訂閱的使用者需要 1 tb + 10 GB + 任何其他購買的儲存空間。 您可以購買無限量的額外儲存空間。|
|群組信箱大小|50 GB|

組織可以擁有的預設 Microsoft 365 群組數目上限為500000。 若要超出預設限制，您必須聯繫 Microsoft 支援部門。 如需 Microsoft 365 群組限制的詳細資訊，請參閱 [Microsoft 365 群組-系統管理](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)說明。

當您具有群組使用量的可操作資訊時，管理 Microsoft 365 群組會更有效。 Microsoft 365 系統管理中心有一個報告工具，可讓您查看儲存體使用方式、您擁有的使用中群組數目，以及使用者使用群組的方式。 如需詳細資訊，請參閱： [admin center 中的 Microsoft 365 報告](../activity-reports/office-365-groups.md) 。

## <a name="sensitivity-labels"></a>敏感度標籤

您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。 您可以使用敏感度標籤設定下列專案： 

- 隱私權 (公開或私人) 
- 外部使用者存取
- 未受管理的裝置存取

例如，您可以建立一個名為「 *高度機密* 」的標籤，並指定使用此標籤建立的任何群組都是私人的，而不允許外部使用者。 當您組織中的使用者在建立群組時選取此標籤時，會將群組設定為 [私人]，而且不允許群組成員將外部使用者新增至群組。

> [!IMPORTANT]
> 如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。 

如需建立、管理及使用敏感度標籤的詳細資訊，請參閱 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些 Microsoft 365 方案包含群組？

任何有 Exchange Online 和 SharePoint 線上的 Microsoft 365 訂閱都會支援群組。 其中包括商務基本方案和商務高級方案，以及 Enterprise E1、E3 和 E5 計畫。 群組會接受建立群組 (人員的授權，也稱為群組) 的「召集人」。 只要召集人具有您想要群組擁有的任何功能的適當授權，該授權就會傳遞給群組。

> [!NOTE]
> 如需 Microsoft 365 服務系列與方案的詳細資訊，請參閱 [microsoft 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

如果您有僅限 Exchange 的計畫，您仍然可以在 Outlook 中取得群組的共用收件匣和共用行事曆功能，但不會取得文件庫、Planner 或任何其他功能。

Microsoft 365 群組使用 Azure Active Directory。 您取得的群組功能取決於您所擁有的 Azure Active Directory 訂閱，以及指派給群組召集人的授權。

> [!IMPORTANT]
> 針對所有群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組，不論他們是否已指派 AAD P1 授權。 不會強制執行授權。
> 我們會定期產生使用方式報告，告訴您哪些使用者已遺失授權，而且需要指派給他們，以符合授權要求。 例如，假設使用者沒有授權，而且會將其新增至強制執行命名原則的群組中。 報告會標示您需要授權。

## <a name="related-articles"></a>相關文章

[深入瞭解 Microsoft 365 群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[將通訊群組清單升級至 Microsoft 365 群組](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[在 Microsoft Stream 中組織群組和通道](https://docs.microsoft.com/stream/groups-channels-organization)
