---
title: 開啟或關閉 Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 瞭解如何在 Microsoft 365 中取得 Microsoft 預約的存取權。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913763"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>開啟或關閉 Microsoft Bookings

您的整個組織或特定使用者可以開啟或關閉預約。 當您為使用者開啟預約時，他們可以建立預約頁面、建立行事曆，以及允許其他人與他們一起預約時間。

> [!NOTE]
> 這些區段中所述的系統管理控制措施不適用於由世紀 (中國) 客戶運作的 Office 365。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心為您的組織開啟或關閉預定功能

1. 以全域系統管理員身分登入 Microsoft 365 系統管理中心。

2. 在系統管理中心中，移至  **設定**   \> **Org 設定** 並選取 [**預定**]。

3. 選取 [ **允許貴組織使用預定** 為您的組織啟用或停用預定] 的核取方塊。

   > [!NOTE]
   > 關閉預約功能會停用對該服務的所有存取，包括建立及管理預定頁面。

4. 選取 [ **儲存變更**]。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>使用 PowerShell 為您的組織開啟或關閉預定功能

若要使用 PowerShell Cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)為您的組織開啟或關閉預約，請[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)並執行下列命令：

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>為個別使用者開啟或關閉預約功能

您可以為個別使用者停用預定。

1. 移至 Microsoft 365 系統管理中心，然後選取 [**使用者**] [作用中 \> **使用者**]。

1. 選取所需的使用者，然後選取 [ **授權和應用程式**]。

1. 展開 [ **應用程式** ]，然後清除 [Microsoft 預約] 的核取方塊。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>在共用空閒/忙碌資訊之前需要人員核准

系統管理員可以在其可用性資訊透過預約共用之前，讓組織中的員工進入自願加入，然後才能透過預約頁面進行 bookable。 在 [設定預約]**設定** 下的 Microsoft 365 系統管理中心中，可以使用此設定 \>  \> ****。

啟用此設定時，在預約行事曆中新增為職員的員工，會在收到的電子郵件通知中找到核准/拒絕連結。

這項功能會逐漸向全球範圍推廣 Microsoft 365 的客戶。 如果您在 Microsoft 365 系統管理中心中未看到此選項，請稍後再回來查看。

## <a name="block-social-sharing-options"></a>封鎖社交共用選項

系統管理員可以控制在社交網路上共用預約頁面的方式。 在 [設定預約]**設定** 下的 Microsoft 365 系統管理中心中，可以使用此設定 \>  \> ****。

這項功能會逐漸向全球範圍推廣 Microsoft 365 的客戶。 如果您在 Microsoft 365 系統管理中心中未看到此選項，請稍後再回來查看。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>只允許選取的使用者建立預定行事曆

透過使用原則限制，您可以限制已授權的使用者無法建立預定的行事曆。 您必須先為整個組織啟用預定。 您組織中的所有使用者都具有預約授權，但只有納入原則的使用者可以建立預約行事曆，而且可以完全控制誰可以存取他們所建立的行事曆。

包含在此原則中的使用者可以建立新的預約行事曆，也可以新增為任何產能的人員， (包括「系統管理員」角色) 現有的預約行事曆。 未包含在此原則中的使用者將無法建立新的預約行事曆，如果他們嘗試這麼做，將會收到錯誤訊息。

您必須使用 Exchange Online PowerShell 執行下列命令。 如需執行 Exchange Online Cmdlet 的詳細資訊，請參閱[連線 to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

> [!IMPORTANT]
> 下列步驟會假設您的組織中未建立任何其他 Outlook Web App (OWA) 信箱原則。

1. 為應該允許建立預約行事曆的使用者建立新的信箱原則。 預設會使用新的信箱原則， (預定的行事曆建立。 ) 

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   如需詳細資訊，請參閱 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。

2. 針對您想要授與建立預約行事曆許可權的每個使用者執行此命令，將此原則指派給相關的使用者。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   如需詳細資訊，請參閱 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。

3. 選用：如果您想要對組織中的其他所有使用者停用預定，請執行此命令。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   如需詳細資訊，請參閱＜[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)＞。

如需 OWA 信箱原則的詳細資訊，請參閱下列主題：

- [在 Exchange Online 中建立 Outlook 網頁版信箱原則](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [在 Exchange Online 中的信箱上套用或移除網頁信箱原則上的 Outlook](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)