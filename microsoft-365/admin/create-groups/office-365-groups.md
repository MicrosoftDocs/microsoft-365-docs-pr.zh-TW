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
description: 瞭解 Microsoft 365 群組。
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925347"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)

Microsoft 365 群組是推動 Microsoft 365 所有團隊合作的基礎成員資格服務。 使用 Microsoft 365 群組，您可以讓一組人員存取共用資源集合。 這些資源包括：

- 共用的 Outlook 信箱
- 共用日曆
- SharePoint 文件庫
- A Planner
- OneNote 筆記本
- Power BI
- 如果 yammer (從 Yammer 建立群組，Yammer) 
- 如果群組 (從 Teams 建立，團隊會) 
- 如果您 (Project 網頁) 

有了 Microsoft 365 群組，您就不必手動指派許可權給這些資源。 將人員新增到群組時，會自動提供他們所需的許可權。

除非您將建立群組限制為一組特定人員，否則 [任何使用者都可以建立群組](manage-creation-of-groups.md)。 如果您限制建立群組，無法建立群組的使用者將無法建立 SharePoint 網站、規劃工具或小組。 這些服務會要求建立服務的人能夠建立群組。 只要使用者是群組的成員，他們仍可參與群組活動，例如，在 Planner 中建立工作，或是使用 Teams 聊天。

群組具有下列角色：

- **擁有者** - 群組擁有者可以新增或移除成員，而且擁有唯一的許可權，例如刪除共用之信箱中的交談，或變更群組的不同設定。 群組擁有者可以重新命名群組、更新描述或圖片等等。
- **成員** - 成員可以存取群組中所有專案，但無法變更群組設定。 根據預設，群組成員可以邀請來賓加入您的群組，不過您可以 [控制該設定](manage-guest-access-in-groups.md)。
- **來賓** - 群組來賓是組織外部的成員。

只有全域系統管理員、使用者系統管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。 您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。

做為系統管理員，您可以：

- [指定誰可以建立群組](manage-creation-of-groups.md)
- [為貴組織的群組建立命名政策](groups-naming-policy.md)
- [選擇在建立群組時要使用哪一個網域](choose-domain-to-create-groups.md)
- [管理群組的來賓存取](manage-guest-access-in-groups.md)
- [刪除後 30](restore-deleted-group.md) (復原刪除的群組) 

如果您想要更自動化的方式來管理 Microsoft 365 群組的生命週期，可以使用到期政策以特定的時間間隔到期群組。 群組的擁有者將在群組到期日的 30、15 和 1 天前收到電子郵件，允許他們在仍然需要時為群組續約。 請參閱 [：Microsoft 365 群組到期政策](office-365-groups-expiration-policy.md)。

您可以使用 Microsoft 365 系統管理中心或 [PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)來管理群組。

如果您有許多使用者 ，例如大型公司或企業，您可能有許多使用者會建立各種用途的群組。 我們強烈建議您查閱 [Microsoft 365](plan-for-groups-governance.md) 群組中的監管計畫以獲得最佳作法。

## <a name="group-limits"></a>群組限制

下列限制適用于 Microsoft 365 群組：

|最大。。。|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|系統管理員可以建立群組|租使用者的預設上限為 500 K|
|Number of members |超過 1，000 個，但只有 1，000 個可以同時存取群組交談。 <br>使用者可能會發現，在 Outlook 中存取大型群組中的日曆和交談時，有延遲的情況。|
|使用者可參與的群組數目|7,000|
|檔案儲存空間|每個訂閱的使用者 1 TB + 10 GB + 任何其他購買的儲存空間。 您可以購買無限制的額外儲存空間。|
|群組信箱大小|50 GB|

組織預設的 Microsoft 365 群組數量上限為 500，000 個。 若要超出預設限制，您必須與 Microsoft 支援服務聯繫。 有關 Microsoft 365 群組限制詳細資訊，請參閱 [Microsoft 365 群組 - 系統管理協助](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

當您有關于群組使用方式的可行資訊時，管理 Microsoft 365 群組會比較有效率。 Microsoft 365 系統管理中心有報告工具，可讓您查看儲存空間使用、使用中的群組數量，以及使用者如何使用群組。 請參閱：詳細資訊請參閱系統管理中心的 [Microsoft 365](../activity-reports/office-365-groups.md) 報告。

## <a name="sensitivity-labels"></a>敏感度標籤

您可以建立敏感度標籤，貴組織的使用者在建立 Microsoft 365 群組時可以設定。 使用敏感度標籤，您可以設定： 

- 公用 (或私人網站的隱私權) 
- 外部使用者存取
- 未管理裝置存取

例如，您可以建立稱為高度機密的卷標，並指定任何使用這個標籤所建立的群組為私人群組，且不允許外部使用者。 當貴組織的使用者在建立群組時選取此標籤時，群組會設定為私人，且不允許群組成員將外部使用者新增到群組。

> [!IMPORTANT]
> 如果您目前使用分類標籤，一旦啟用敏感度標籤後，建立群組的使用者就無法再使用這些分類標籤。 

有關建立、管理及使用敏感度標籤的資訊，請參閱使用敏感度標籤來保護 [Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些 Microsoft 365 方案包含群組？

任何擁有 Exchange Online 和 SharePoint Online 的 Microsoft 365 訂閱都支援群組。 其中包括商務基本版和商務進版方案，以及企業版 E1、E3 和 E5 方案。 群組會接受建立群組群組 (也稱為群組成員「召集人」) 。 只要該名召集人擁有您希望群組擁有的功能之適當授權，該授權就會傳達給該群組。

> [!NOTE]
> 有關 Microsoft 365 服務系列與方案的詳細資訊，請參閱 [Microsoft 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

如果您有僅適用于 Exchange 的計畫，您仍然可以取得 Outlook 中群組的共用信箱和共用日曆功能，但您不會取得文件庫、Planner 或其他任何功能。

Microsoft 365 群組可與 Azure Active Directory 一起使用。 您取得哪些群組功能取決於您擁有哪些 Azure Active Directory 訂閱，以及指派給群組的召集人哪些授權。

> [!IMPORTANT]
> 對於所有群組功能，如果您有 Azure AD Premium 訂閱，無論使用者是否已指派 AAD P1 授權，都可以加入群組。 不會強制執行授權。
> 我們會定期產生使用方式報告，告訴您哪些使用者遺失授權，並需要指派一個授權，才能符合授權要求。 例如，假設使用者沒有授權，而他們會新增到強制執行命名策略的群組中。 報告會標出您需要授權。

## <a name="related-articles"></a>相關文章

[瞭解 Microsoft 365 群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[將通訊群組清單升級至 Microsoft 365 群組](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
