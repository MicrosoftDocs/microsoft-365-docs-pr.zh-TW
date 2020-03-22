---
title: Office 365 群組到期原則
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
description: 深入瞭解 Office 365 群組到期原則。
ms.openlocfilehash: 40b0b56507c46f2a658126627d5f8794848bde27
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894512"
---
# <a name="office-365-group-expiration-policy"></a>Office 365 群組到期原則

隨著 Office 365 群組的使用量增加，管理員和使用者需要一種方式來清除未使用的群組。 到期原則可協助從系統中移除非使用中的群組，並使事情更整潔。

當群組到期時，其相關聯的所有服務（信箱、Planner、SharePoint 網站、小組等等）都會同時刪除。

當群組到期時，它會「虛刪除」，表示它仍可復原30天。

管理員可以指定到期期限及任何非作用中的群組，只要到達該期間結束，也不會被更新，將會被刪除。 到期期限是在建立群組時或在最後一次更新的日期時開始。 在到期之前，系統會自動將電子郵件傳送給群組擁有者，以允許使用者在其他到期間隔內更新群組。 小組使用者會在小組中看到持續的通知。

主動使用中的群組會自動更新。 下列任何動作都會自動更新群組：
- SharePoint-查看、編輯、下載、移動、共用或上傳檔案。
- Outlook-加入群組、讀取或寫入群組的郵件，以及類似郵件（Outlook 網頁版）。
- 團隊-來訪小組頻道。

> [!IMPORTANT]
> 當您變更到期原則時，服務會重新計算每個群組的到期日。 它永遠從建立群組的日期開始計數，然後套用新的到期原則。

請務必知道到期會預設為關閉狀態。 系統管理員若要使用它，必須為組織啟用它。

> [!NOTE]
> 設定和使用 Office 365 群組的到期原則，需要您擁有但不一定要為已套用到期原則之所有群組的成員指派 Azure AD Premium 授權。 如需詳細資訊，請參閱[Azure Active Directory Premium 快速](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)入門。

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a>誰可以設定及使用 Office 365 群組到期原則？

|角色|可以執行的動作|
|---------|---------|
|Office 365 全域管理員（在 Azure、公司管理員）、使用者管理員|建立、讀取、更新或刪除 Office 365 群組到期原則設定。|
|User|更新或[還原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)擁有的 Office 365 群組|

## <a name="how-to-set-the-expiration-policy"></a>如何設定到期原則

如以上所述，到期會預設為關閉狀態。 管理員必須啟用到期原則，並將其設定為生效。 若要啟用它，請移至**Azure Active Directory （AAD）** > **群組** > **到期**。 您可以在這裡設定預設的組生命週期，並指定您要提前多久的時間，將第一和第二個到期通知移至群組擁有者。

群組存留時間是以天數指定，可設定為180、365或您指定的自訂值。 自訂值至少必須是30天。

如果群組沒有擁有者，到期電子郵件將會移至指定的系統管理員。

您可以設定所有群組的原則，只為選取的群組，或透過選取 [**無**] 完全關閉。 請注意，目前您不能針對不同的群組使用不同的原則。

![Azure Active Directory 中群組到期設定的螢幕擷取畫面](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>到期原則與保留原則的運作方式

如果您在群組的安全性與合規性中心中有設定保留原則，到期原則會順利地使用保留原則運作。 當群組到期時，群組中的 [在信箱中交談] 核取方塊和群組網站中的檔案會保留在保留原則中所定義的特定天數內保留容器內。 但到期後，使用者將不會看到此群組或其內容。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>群組擁有者如何以及何時會到期的使用者群組

群組擁有者只會透過電子郵件通知。 如果群組是透過 Planner、SharePoint 或任何其他應用程式建立，到期通知永遠都透過電子郵件傳送。 如果群組是透過小組建立，群組擁有者會收到透過「活動」區段進行更新的通知。 如果您的群組擁有者沒有有效的電子郵件地址，建議您在群組上啟用到期。

超過此群組的30天之後，群組擁有者（或您為沒有擁有者之群組所指定的電子郵件地址）將會收到電子郵件，讓使用者可以輕鬆地更新群組。 如果不加以更新，他們會在到期前的15天內收到另一個更新電子郵件。 如果他們仍未更新，他們會在到期前的一天內收到一封以上的電子郵件通知。

若由於某些原因，任何擁有者或系統管理員都不會在過期前更新群組，管理員仍可在到期後30天內還原群組。 如需詳細資訊，請參閱：[還原已刪除的 Office 365 群組](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="related-articles"></a>相關文章

[保留原則概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[指派新擁有者給孤立的群組](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[設定 Office 365 群組到期](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
