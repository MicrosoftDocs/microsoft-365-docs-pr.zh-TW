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
description: 使用 Microsoft 365 群組，您可以讓人員群組存取共用資源的集合，以促進團隊合作的 Microsoft 365。
ms.openlocfilehash: bfcd2d27bc1d63fcc8b306267efe21c3f9564522
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582737"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)

Microsoft 365群組是一種基礎成員資格服務，可促進所有團隊間的團隊合作 Microsoft 365。 使用 Microsoft 365 群組，您可以讓一組人員能夠存取共用資源的集合。 這些資源包括：

- 共用 Outlook 收件匣
- 共用行事曆
- SharePoint 文件庫
- Planner
- OneNote 筆記本
- Power BI
- 從 Yammer 建立群組時 Yammer () 
- 如果群組是從 Teams 建立的，則為小組 () 
- 如果您有 Project 網頁) 的藍圖 (
- Stream

使用 Microsoft 365 群組時，您不需要手動指派每個資源的許可權。 將人員新增至群組時，會自動為他們提供所需的許可權。

除非您將 [群組建立限制于一組特定的人員](../../solutions/manage-creation-of-groups.md)，否則任何使用者都可以建立群組。 如果您限制群組的建立，無法建立群組的使用者將無法建立 SharePoint 網站、規劃人員或小組。 這些服務要求建立群組的人員可以建立群組。 使用者仍可參與群組活動，例如在 Planner 中建立工作，或使用 Teams 聊天室，只要是群組的成員。

群組具有下列角色：

- **擁有** 者-群組擁有者可以新增或移除成員，並具有獨特的許可權，例如從共用收件匣刪除交談的功能，或變更群組的不同設定。 群組擁有者可以重新命名群組、更新描述或圖片等等。
- **Members** -成員可以存取群組中的所有專案，但無法變更群組設定。 依預設，群組成員可以邀請客人加入您的群組，但您可以 [控制該設定](manage-guest-access-in-groups.md)。
- **來賓** 群組來賓是指來自組織外部的成員。

只有全域系統管理員、使用者管理員和群組系統管理員可以在 Microsoft 365 系統管理中心建立及管理群組。 您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。

身為管理員，您可以：

- [指定誰可以建立群組](../../solutions/manage-creation-of-groups.md)
- [為組織中的群組建立命名原則](../../solutions/groups-naming-policy.md)
- [選擇建立群組時所要使用的網域](../../solutions/choose-domain-to-create-groups.md)
- [管理群組的來賓存取](manage-guest-access-in-groups.md)
- 在刪除的30天內，[復原已刪除的群組](restore-deleted-group.md) () 

如果您想要更自動化的方式來管理 Microsoft 365 群組的生命週期，您可以使用到期原則，在特定的時間間隔內到期群組。 群組的擁有者會收到一封電子郵件30、15及1天，允許使用者在仍需要的群組到期時進行更新。 請參閱： [Microsoft 365 組到期原則](../../solutions/microsoft-365-groups-expiration-policy.md)。

您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)管理群組。

如果您有許多使用者，例如在大型公司或企業中，您可能會有許多使用者出於各種目的建立群組。 強烈建議您複查[Microsoft 365 群組中的管理計畫](../../solutions/collaboration-governance-overview.md)，以取得最佳作法。

## <a name="group-limits"></a>群組限制

下列限制適用于 Microsoft 365 群組：

|最大。。。|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理員可以建立的群組|最高預設租使用者限制為 500 K|
|Number of members |超過1000，但只有1000可以同時存取群組交談。 <br>使用者可能會注意到在 Outlook 中，存取大型群組中的行事曆和交談時，會發生延遲。|
|使用者可以是其成員的群組數目|7000|
|檔存放區|每個訂閱的使用者需要 1 tb + 10 GB + 任何其他購買的儲存空間。 您可以購買無限量的額外儲存空間。|
|群組信箱大小|50 GB|

組織可以擁有的 Microsoft 365 組預設數目上限為500000。 若要超出預設限制，您必須聯繫 Microsoft 支援部門。 如需 Microsoft 365 群組限制的詳細資訊，請參閱[Microsoft 365 群組-系統管理](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)說明。

當您具有群組使用量的可操作資訊時，管理您的 Microsoft 365 群組會更有效。 Microsoft 365 系統管理中心有一個報告工具，可讓您查看儲存體使用方式、您擁有的使用中群組數目，以及使用者使用群組的方式。 如需詳細資訊，請參閱：[在系統管理中心中 Microsoft 365 報告](../activity-reports/office-365-groups.md)。

## <a name="sensitivity-labels"></a>敏感度標籤

您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。 您可以使用敏感度標籤設定下列專案： 

- 隱私權 (公開或私人) 
- 外部使用者存取
- 未受管理的裝置存取

例如，您可以建立一個名為「 *高度機密* 」的標籤，並指定使用此標籤建立的任何群組都是私人的，而不允許外部使用者。 當您組織中的使用者在建立群組時選取此標籤時，會將群組設定為 [私人]，而且不允許群組成員將外部使用者新增至群組。

> [!IMPORTANT]
> 如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。 

如需建立、管理及使用敏感度標籤的詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../../compliance/sensitivity-labels-teams-groups-sites.md)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些 Microsoft 365 計畫包含群組？

任何 Exchange Online 且 SharePoint 線上的 Microsoft 365 訂閱都會支援群組。 包括商務基本版和商務進階版方案，以及 Enterprise E1、E3 和 E5 方案。 群組會接受建立群組 (人員的授權，也稱為群組) 的「召集人」。 只要召集人具有您想要群組擁有的任何功能的適當授權，該授權就會傳遞給群組。

> [!NOTE]
> 如需 Microsoft 365 服務系列與方案的詳細資訊，請參閱[Microsoft 365 計畫選項](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

如果您有僅限 Exchange 的計畫，您仍然可以在 Outlook 中取得群組的共用收件匣和共用行事曆功能，但不會取得文件庫、Planner 或任何其他功能。

Microsoft 365 群組可搭配 Azure Active Directory 使用。 您取得的群組功能取決於您所擁有的 Azure Active Directory 訂閱，以及指派給群組召集人的授權。

> [!IMPORTANT]
> 針對所有群組功能，如果您有 Azure AD 進階版訂閱，使用者可以加入群組，不論他們是否已指派 AAD P1 授權。 不會強制執行授權。
> 我們會定期產生使用方式報告，告訴您哪些使用者已遺失授權，而且需要指派給他們，以符合授權要求。 例如，假設使用者沒有授權，而且會將其新增至強制執行命名原則的群組中。 報告會標示您需要授權。

## <a name="related-content"></a>相關內容

[深入瞭解 Microsoft 365 群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (文章) 

[將通訊群組清單升級至 Microsoft 365 群組](../manage/upgrade-distribution-lists.md) (文章) 

[使用 PowerShell (文章管理 Microsoft 365 群組](../../enterprise/manage-microsoft-365-groups-with-powershell.md)) 

[SharePoint 線上限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (文章) 

[在 Microsoft Stream 中組織群組和頻道](/stream/groups-channels-organization) (文章) 