---
title: Office 365 群組到期原則
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
description: 了解 Office 365 群組到期原則。
ms.openlocfilehash: c4c2f7b98247cc81b3fadc561f92084f9bd39c96
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352584"
---
# <a name="office-365-group-expiration-policy"></a>Office 365 群組到期原則

使用 Office 365 群組的使用量增加，系統管理員和使用者需要方法來清除未使用的群組。 從系統移除不在作用中的群組，並讓事情更簡潔，可協助到期原則。

群組到期時，所有其相關聯的服務 (信箱，規劃中，SharePoint 網站] 等) 也會遭到刪除。

群組到期時，「 虛刪除 」 這表示它仍可復原的最多 30 天。

系統管理員可以指定到期時間和任何非使用中的群組，抵達陣列結尾的這段時間內，則不會更新，將被刪除。 建立群組，或依日期它上次更新時，會開始進行到期時間。 群組擁有者將會自動傳送一封電子郵件，讓他們能更新群組的另一個到期間隔到期之前。 Microsoft teams 使用者會看到小組的持續性通知。

目前正在使用中的群組會自動更新。 任何下列的動作將會自動續約群組：
- SharePoint-檢視、 編輯、 下載、 移動、 共用，或將檔案上傳。
- Outlook-加入群組、 讀取或寫入群組訊息，從群組中，和 like 郵件 （outlook 網頁版）。
- Teams-造訪小組通道。

> [!IMPORTANT]
> 當您變更的到期原則時，此服務會重新計算每個群組的到期日。 它一律會開始算起群組時已建立，且然後將套用的新的到期原則。

請務必了解到期預設為關閉。 系統管理員必須啟用其租用戶如果他們想要使用它。

> [!NOTE]
> 設定及使用 Office 365 群組的到期原則需要您擁有，但不是一定是將 Azure AD Premium 授權指派的到期原則會套用至其中的所有群組的成員。 如需詳細資訊，請參閱[開始使用 Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)。

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a>誰可以設定及使用 Office 365 群組到期原則？

|角色|他們可以執行的動作|
|---------|---------|
|Office 365 全域系統管理員 （Azure，公司系統管理員)，使用者系統管理員|建立、 讀取、 更新或刪除 Office 365 群組到期原則設定。|
|使用者|續約或[還原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)自己的 Office 365 群組|

## <a name="how-to-set-the-expiration-policy"></a>如何設定到期原則

如上所述，到期是預設關閉。 系統管理員必須啟用到期原則，並設定它才會生效的屬性。 若要啟用移至**Azure Active Directory (AAD)** > **群組** > **到期**。 您可以在這裡設定預設群組存留時間，並指定多久要移至群組擁有者的第一個及第二個過期通知。

群組存留期指定天內，且可以設為 180，365 或您指定自訂值。 自訂的值必須設為至少 30 天。

如果群組沒有擁有者的電子郵件會移至指定的系統管理員的到期時間。

您可以將原則設定的所有群組，僅選取群組，或將它關閉完全藉由選取 [**無**。 請注意，目前您不能有不同的群組不同的原則。

![在 Azure Active Directory 中的螢幕擷取畫面的群組到期日設定](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>到期與保留原則的運作方式

如果您有設定保留原則中群組的安全性與合規性中心，到期原則的運作順暢地與保留原則。 群組過期時，在 [郵件] 方塊中的群組交談和群組網站中的檔案會保留在 [保留] 容器中保留原則中定義特定天數。 使用者不會看到群組中或其內容之後到期, 不過。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>如何及何時群組擁有者可學習是否其群組即將到期

群組擁有者只會透過電子郵件通知。 如果透過 Planner、 SharePoint 或任何其他應用程式已建立的群組，過期通知永遠都將透過電子郵件。 如果透過小組已建立的群組，群組擁有者會收到通知，以續約透過 [活動] 區段中。 不建議您啟用群組上的到期日，如果群組擁有者都不會有有效的電子郵件地址。

30 天前群組到期時，群組擁有者 （或您所指定的群組，不需要擁有者的電子郵件地址） 將會收到一封電子郵件，讓使用者能輕鬆地更新群組。 如果他們不更新它，就會收到其他更新電子郵件過期前的 15 天。 如果他們仍尚未更新它，他們會收到一個多個電子郵件通知密碼到期前一天。

如果基於某個原因而沒有任何一個擁有者或系統管理員會更新群組到期之前，系統管理員仍可還原該群組最多 30 天之後到期。 如需詳細資訊，請參閱：[還原已刪除的 Office 365 群組](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="related-articles"></a>相關文章

[保留原則概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[指派新擁有者給孤立的群組](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[設定 Office 365 群組到期日](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
