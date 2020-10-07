---
title: Microsoft 365 群組、小組和 SharePoint 之間的設定互動
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 深入瞭解 Microsoft 365 群組、小組和 SharePoint 之間的設定互動
ms.openlocfilehash: 3a6d4e057f88410a8808ea133bf7e579d0041228
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377542"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 群組、小組和 SharePoint 之間的設定互動

Microsoft 365 群組、Microsoft 團隊和 SharePoint 在 Microsoft 365 中的一些設定，尤其與共享和群組/小組和 SharePoint 網站建立有關，彼此重疊。 本文提供這些互動的說明，以及如何使用這些設定的最佳作法。

![SharePoint、小組和群組功能的卞氏圖表圖表](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>SharePoint 群組和團隊設定的影響

|SharePoint 設定|描述|對 Microsoft 365 群組和團隊的影響|建議|
|:-----------------|:----------|:---------------------------------------|:-------------|
|組織和網站的外部共用|決定網站、檔案及資料夾是否可以與組織外部的人員共用。|如果 SharePoint、群組和團隊設定不符，則可能會封鎖小組中的來賓存取網站，或可能發生意外的外部存取。|變更共用設定時，請檢查群組連線小組網站的群組設定、小組設定和 SharePoint 網站設定。<br><br> 請參閱[與小組中的客人共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業|
|網域允許/封鎖|允許或防止內容與指定的網域共用。|群組和團隊無法辨識 SharePoint 允許或封鎖清單。 來自 SharePoint 不允許的網域使用者可以透過小組存取 SharePoint 網站或內容。|管理 Azure AD 和 SharePoint 的網域允許/封鎖清單。 建立組織範圍內允許和封鎖網域的管理程式。<br><br>請參閱 [SharePoint 網域設定](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 和 [Azure AD 網域設定](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|只允許特定安全性群組中的使用者在外部共用|指定可以在外部共用 SharePoint 網站、資料夾及檔案的安全性群組。|此設定不會讓小組擁有者在外部共用小組。 小組來賓可以存取相關聯的 SharePoint 網站。||
|SharePoint 網站共用設定|決定誰可以直接在小組成員資格外共用網站。 這是由小組或網站擁有者設定。|此設定不會直接影響小組，但可讓使用者加入至網站，而且無法存取小組自身或其他小組資源。|請考慮使用此設定來直接限制網站共用，並透過團隊管理網站存取。|
|讓使用者從 SharePoint 開始頁面及 OneDrive 中建立網站|指定使用者是否可以建立新的 SharePoint 網站。|如果關閉此設定，使用者仍然可以建立小組建立群組連線的小組網站。||

## <a name="the-effects-of-groups-settings-on-teams"></a>群組設定對小組的影響

|Microsoft 365 群組設定|描述|對小組的影響|建議|
|:---------------------------|:----------|:--------------|:-------------|
|命名原則|指定群組名稱首碼和尾碼，以及群組建立的封鎖文字|為建立小組的使用者強制執行原則。||
|群組來賓存取|指定組織外部的人員是否可以新增至群組。|如果 [群組] 或 [小組] 的 [來賓共用] 設定為 [關閉]，則無法與來賓共用該小組。|變更來賓共用設定時，請檢查小組、群組和與小組相關聯的 SharePoint 網站設定。<br><br> 請參閱[與小組中的客人共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業|
|依安全性群組建立群組|群組只能由特定安全性群組的成員來建立。|不是安全性群組成員的使用者將無法建立小組。|請確定要求群組的套裝程式含要求小組或 SharePoint 網站的指示。|
|群組到期原則|指定一段時間，在此時間之後將會自動刪除未使用中的群組。|刪除群組時，也會刪除小組和相關聯的 SharePoint 網站。 保留以保留原則保護的內容。|使用到期原則，避免未使用的小組、群組和網站的蔓延。|

## <a name="related-topics"></a>相關主題

[與組織外部人員合作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[在 SharePoint 中管理網站建立](https://docs.microsoft.com/sharepoint/manage-site-creation)
