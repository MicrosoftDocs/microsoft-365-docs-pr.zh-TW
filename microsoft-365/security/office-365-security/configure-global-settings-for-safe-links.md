---
title: 針對 Office 365 的 Defender 中的安全連結設定設定全域設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何查看和設定全域設定 (「封鎖下列 URLs」清單和 Office 365 應用程式的保護) ，以取得 Microsoft Defender for Office 365 中的安全連結。
ms.openlocfilehash: 2793985e6289b26baad268925cbf9c5e9a89dce9
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572426"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>設定 Microsoft Defender for Office 365 中安全連結的全域設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文適用于具有 [Microsoft Defender For Office 365](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全連結是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一項功能，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結。 如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全連結](atp-safe-links.md)。

您可以在安全連結原則中設定大多數的安全連結設定。 如需相關指示，請參閱 [設定 Microsoft Defender For Office 365 中的安全連結原則](set-up-atp-safe-links-policies.md)。

不過，安全連結也會使用適用于所有作用中安全連結原則中所包含之所有使用者的全域設定。 下列全域設定區域：

- **封鎖下列 URLs** 清單。 如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單。](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Office 365 應用程式的安全連結保護。 如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

您可以使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中設定全域安全連結設定，以取得適用的 Microsoft 365 組織。獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但搭配 Microsoft Defender for Office 365 附加元件訂閱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 安全連結的全域設定所提供的功能僅適用于包含在使用中安全連結原則中的使用者。 沒有內建或預設的安全連結原則，因此您必須建立至少一個安全連結原則，這些全域設定才會作用。 如需相關指示，請參閱 [設定 Microsoft Defender For Office 365 中的安全連結原則](set-up-atp-safe-links-policies.md)。

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **安全連結** ] 頁面，請使用 <https://protection.office.com/safelinksv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須在安全性 & 合規性中心指派許可權，才能執行本文中的程式：
  - 若要設定安全連結的全域設定，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要對安全連結的全域設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附註**：

  - 將使用者新增至 Microsoft 365 系統管理中心的對應 Azure Active Directory 角色，可讓使用者具備安全性 & 合規性中心的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的「 **View-Only 組織管理**」角色群組也會提供該功能的唯讀存取權。

- 如需安全連結之全域設定的建議值，請參閱 [安全連結設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

- [新功能不斷新增至 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)。 新增新功能時，您可能需要調整現有的安全連結原則。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>在安全性 & 規範中心設定「阻止下列 URLs」清單

**Block 下列 URLs** 清單會識別在支援的應用程式中，安全連結掃描時，應攔截的連結。 如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。

2. 在 **您的組織的安全連結原則** 中，會出現 [飛出]，請移至 [ **封鎖下列 URLs] 方塊** 。

3. 設定一或多個專案，如 ["封鎖下列 URLs 的專案語法](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述] 清單。

   完成後，按一下 [儲存]。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>設定 PowerShell 中的「封鎖下列 URLs」清單

如需輸入語法的詳細資訊，請參閱「 [封鎖下列 URLs 的輸入語法」清單](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

您可以使用 **AtpPolicyForO365** Cmdlet 來查看 _BlockURLs_ 屬性中的現有專案。

- 若要新增將取代任何現有專案的值，請在 Exchange Online 中使用下列語法 PowerShell 或 Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  本範例會將下列專案新增至清單：

  - 封鎖 fabrikam.com 的網域、子域及路徑。
  - 封鎖子域調查，但不封鎖 tailspintoys.com 中的父網域或其他子域

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 若要新增或移除值，而不影響其他現有的專案，請使用下列語法：

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  本範例會為 adatum.com 新增新的專案，並移除 fabrikam.com 的專案。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>在安全性 & 規範中心內設定 Office 365 應用程式的安全連結保護

Office 365 應用程式的安全連結保護適用于支援的 Office desktop、行動裝置和 web 應用程式中的檔。 如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。

2. 在已出現之 **組織的安全連結原則** 中，在 [ **電子郵件以外的內容設定** ] 區段中，設定下列設定：

   - **Office 365 應用程式**：驗證切換是否為支援的 office 365 應用程式的安全連結：開啟開啟 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

   - **當使用者按一下安全連結時，請勿追蹤**：在支援的 Office 365 應用程式中，將切換移至左側以追蹤與封鎖的 URLs 相關的使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。

   - **不要讓使用者點擊 [安全連結] 原始 URL**：確認切換是向右，以防止使用者在支援的 Office 365 應用程式中按一下原始的封鎖 URL： ![ 開啟 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

   完成後，按一下 [儲存]。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>在 PowerShell 中設定 Office 365 應用程式的安全連結保護

如果您不想使用 PowerShell 來設定 Office 365 應用程式的安全連結保護，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

此範例會針對 Office 365 應用程式中的安全連結保護設定下列設定：

- Office 365 應用程式的安全連結已開啟 (我們不會使用 _EnableSafeLinksForO365Clients_ 參數，預設值是 $true) 。
- 追蹤支援的 Office 365 應用程式中的封鎖 URLs 相關的使用者按一下。
- 在支援的 Office 365 應用程式中，不允許使用者點擊至原始的封鎖 URL (我們不會使用 _AllowClickThrough_ 參數，預設值是 $false) 。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功設定安全連結的全域設定 (**封鎖下列 URLs** 清單和 Office 365 app protection 設定) ，請執行下列任一步驟：

- 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，按一下 [ **通用設定**]，然後確認 [飛出] 中顯示的設定。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，執行下列命令，然後確認設定：

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。
