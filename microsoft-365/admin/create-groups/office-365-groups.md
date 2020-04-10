---
title: 管理員的 Office 365 群組概述
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
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
description: 深入瞭解 Office 365 群組。
ms.openlocfilehash: f5a0b72737a360a4bfe4cdd8fee4a08b7a7ff236
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212530"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>管理員的 Office 365 群組概述

Office 365 群組是一種基礎成員資格服務，可促進整個 Microsoft 365 的所有團隊合作。 您可以使用 Office 365 群組，讓一群人員能夠存取共同作業資源的集合，供他們共用。 這些資源包括：

- 共用的 Outlook 收件匣
- 共用行事曆
- SharePoint 文件庫
- Planner
- Power BI
- Yammer （如果群組是由 Yammer 建立）
- 小組（如果群組是從小組建立）
- 藍圖（如果您有 web 的專案）

使用 Office 365 群組時，您不需要手動指派每個資源的許可權，因為新增人員至群組會自動為他們提供群組所提供之工具所需的許可權。

除非您將[群組建立限制于一組特定的人員](manage-creation-of-groups.md)，否則任何 Office 365 使用者都可以建立群組。 請注意，如果您限制群組的建立，無法建立群組的使用者將無法建立 SharePoint 網站、規劃人員或小組。 這些服務要求建立群組的人員可以建立群組。 使用者仍可參與群組活動，例如在 Planner 中建立工作或使用小組聊天，但前提是群組的成員。

群組具有下列角色：

- **擁有**者-群組擁有者可以新增或移除成員，並具有獨特的許可權，例如從共用收件匣刪除交談的功能，或變更群組的不同設定。 群組擁有者可以重新命名群組、更新描述或圖片等等。
- **Members** -成員可以存取群組中的所有專案，但無法變更群組設定。 依預設，群組成員可以邀請客人加入您的群組，但您可以[控制該設定](manage-guest-access-in-groups.md)。
- **來賓**群組來賓是指來自組織外部的成員。

只有全域系統管理員、使用者管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。 您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。

身為管理員，您可以：

- [指定誰可以建立群組](manage-creation-of-groups.md)
- [為組織中的群組建立命名原則](groups-naming-policy.md)
- [選擇建立群組時所要使用的網域](choose-domain-to-create-groups.md)
- [管理群組的來賓存取權](manage-guest-access-in-groups.md)
- [復原已刪除的群組](restore-deleted-group.md)（在刪除30天內）

如果您傾向于管理 Office 365 群組的生命週期，使用一種更為自動化的方式，您可以使用到期原則，在特定的時間間隔內到期群組。 群組的擁有者會在群組到期前取得一封電子郵件30、15及1天，以允許使用者在仍需要時輕易更新群組。 請參閱： [Office 365 群組到期原則](office-365-groups-expiration-policy.md)。

您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)管理您的群組。

如果您有許多使用者，例如在大型公司或企業中，您可能會有許多使用者出於各種目的而建立群組。 強烈建議您複查[Office 365 群組中](plan-for-groups-governance.md)的控管計畫，以取得最佳作法。

## <a name="group-limits"></a>群組限制

下列限制適用于 Office 365 群組：

|最大。。。|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理員可以建立的群組|最高預設租使用者有500000位|
|Number of members |超過1000，但只有1000可以同時存取群組交談。 <br>使用者可能會注意到當存取 Outlook 中大量群組的行事曆和交談時，會發生延遲。|
|使用者可以是其成員的群組數目|1,000|
|檔存放區|每個訂閱的使用者需要 1 tb + 10 GB + 購買的任何額外儲存空間。 您可以購買無限量的額外儲存空間。|
|群組信箱大小|50 GB|

Office 365 組織可以擁有的預設 Office 365 群組數目上限為500000，但可按要求增加。 如需 Office 365 群組限制的詳細資訊，請參閱[office 365 群組-系統管理](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)說明。

當您具有群組使用量的可操作資訊時，管理 Office 365 群組會更有效。 Microsoft 365 系統管理中心有一個報告工具，可讓您查看儲存空間使用方式、您擁有的使用中群組數目，甚至是使用者使用群組的方式。 如需詳細資訊，請參閱： [admin center 中的 Office 365 報告](../activity-reports/office-365-groups.md)。

## <a name="which-office-365-plans-include-groups"></a>哪些 Office 365 方案包含群組？

任何有 Exchange Online 和 SharePoint 線上的 Office 365 訂閱都會支援群組。 包括商務基本版和商務用的方案，以及 Enterprise E1、E3 和 E5 計畫。 群組會接受建立群組的人員授權（也稱為群組的「召集人」）。 只要召集人具有您想要群組擁有的任何功能的適當授權，該授權就會傳遞給群組。

> [!NOTE]
> 如需有關 Office 365 服務系列與方案的詳細資訊，請參閱[office 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

如果您有僅限 Exchange 的計畫，您仍然可以在 Outlook 中取得群組的共用收件匣和共用行事曆功能，但不會取得文件庫、Planner 或任何其他功能。

Office 365 群組可搭配 Azure Active Directory （AAD）使用。 您取得的群組功能取決於您所擁有的 Azure Active Directory 訂閱，以及指派給群組召集人的授權。

> [!IMPORTANT]
> 針對所有群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組，不論他們是否已指派 AAD P1 授權。 不會強制執行授權。
> 我們會定期產生使用方式報告，告訴您哪些使用者已遺失授權，而且需要指派給他們，以符合授權要求。 例如，假設使用者沒有授權，而且會將其新增至強制執行命名原則的群組中。 報告會標示您需要授權。

## <a name="related-articles"></a>相關文章

[了解 Office 365 群組](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[將通訊群組清單升級至 Office 365 群組](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Office 365 群組](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
