---
title: 設定保管庫的 Defender 中的連結設定全域設定 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何查看和設定全域設定 (「封鎖下列 URLs」清單和保護 Office 365 應用程式) ，以保管庫的 Microsoft Defender 連結。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46bafd89400dfa551641c055f6f0e208c0ecd49f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108040"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>針對 Office 365 設定 Microsoft Defender 中保管庫連結的全域設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。 如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保管庫連結是[Microsoft Defender](defender-for-office-365.md)中的功能 Office 365，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結的時間。 如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 連結](safe-links.md)。

您可以設定保管庫連結原則中的大部分保管庫連結設定。 如需相關指示，請參閱[在 Microsoft Defender for Office 365 中設定保管庫連結原則](set-up-safe-links-policies.md)。

不過，保管庫連結也會使用您在保管庫連結原則本身之外設定的下列全域設定：

- **封鎖下列 URLs** 清單。 此設定會套用至所有作用中保管庫連結原則中包含的所有使用者。 如需詳細資訊，請參閱[保管庫連結的「封鎖下列 URLs」清單。](safe-links.md#block-the-following-urls-list-for-safe-links)
- 保管庫Office 365 應用程式的連結保護。 這些設定會套用至組織中所有授權使用 Office 365 的使用者，不論使用者是否包含在 active 保管庫連結原則中。 如需詳細資訊，請參閱[保管庫連結設定 Office 365 應用程式](safe-links.md#safe-links-settings-for-office-365-apps)。

您可以設定 Microsoft 365 Defender 入口網站中的全域保管庫連結設定或 PowerShell (Exchange Online PowerShell，以供具有 Microsoft 365 信箱的合格 Exchange Online 組織使用。組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Microsoft Defender Office 365 附加元件訂閱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 沒有內建或預設的保管庫連結原則，因此您必須至少建立一個保管庫連結原則，才能讓 **封鎖下列 URLs** 清單成為作用中。 如需相關指示，請參閱[在 Microsoft Defender for Office 365 中設定保管庫連結原則](set-up-safe-links-policies.md)。

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [**保管庫連結**] 頁面，請使用 <https://security.microsoft.com/safelinksv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要設定保管庫連結的全域設定，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。
  - 若要針對保管庫連結的全域設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 如需保管庫連結之全域設定的建議值，請參閱[保管庫連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

- [新功能會連續新增至 Microsoft Defender 以供 Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新增新功能時，您可能需要調整現有的保管庫連結原則。

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>設定 Microsoft 365 Defender 入口網站中的「封鎖下列 URLs」清單

**Block 下列 URLs** 清單會識別在支援的應用程式中保管庫連結掃描時，應攔截的連結。 如需詳細資訊，請參閱[保管庫連結的「封鎖下列 URLs」清單](safe-links.md#block-the-following-urls-list-for-safe-links)。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]。 在組織的 [**保管庫連結] 原則** 中，請移出顯示的 [**封鎖下列 URLs] 方塊**。

3. 設定一或多個專案，如 ["封鎖下列 URLs 的專案語法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述] 清單。

   完成後，按一下 [儲存]。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>設定 PowerShell 中的「封鎖下列 URLs」清單

如需輸入語法的詳細資訊，請參閱「 [封鎖下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

您可以使用 **AtpPolicyForO365** Cmdlet 來查看 _BlockURLs_ 屬性中的現有專案。

- 若要新增將取代任何現有專案的值，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 入口網站中設定 Office 365 應用程式的保管庫連結保護

保管庫Office 365 應用程式的連結保護適用于支援的 Office 桌面、行動裝置及 web 應用程式中的檔。 如需詳細資訊，請參閱[保管庫連結設定 Office 365 應用程式](safe-links.md#safe-links-settings-for-office-365-apps)。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]。 在所出現的 **組織保管庫連結原則** 中，設定設定中的下列設定，這些設定 **適用于 [支援的 Office 365 應用程式**] 區段中的內容：

   - **使用 Office 365 應用程式中的保管庫連結**：確認是否要啟用支援 Office 365 應用程式的保管庫連結： ![ 開啟切換 ](../../media/scc-toggle-on.png) 。

   - **當使用者在 Office 365 應用程式中按下受保護的連結時，請勿追蹤**：將切換移至左側以追蹤與受支援 Office 365 應用程式中封鎖 URLs 相關的使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。

   - **請勿讓使用者在 Office 365 應用程式中，按原始 URL**：確認切換是向右，以防止使用者在支援的 Office 365 應用程式中按一下原始的封鎖 url：開啟開啟] ![ ](../../media/scc-toggle-on.png) 。

   完成後，按一下 [儲存]。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>在 PowerShell 中設定 Office 365 應用程式的保管庫連結保護

如果您不想使用 PowerShell 來設定 Office 365 應用程式保管庫連結保護，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

此範例會針對 Office 365 應用程式中的保管庫連結保護設定下列設定：

- 保管庫Office 365 應用程式的連結已開啟 (不是使用 _EnableSafeLinksForO365Clients_ 參數，而預設值為 $true) 。
- 會追蹤支援的 Office 365 應用程式中，與封鎖 URLs 相關的使用者按一下。
- 在支援的 Office 365 應用程式中，不允許使用者點擊至原始的封鎖 URL (我們不會使用 _AllowClickThrough_ 參數，預設值會 $false) 。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您已成功設定保管庫連結的全域設定 (**區塊下列 URLs** 清單和 Office 365 應用程式保護設定) ，請執行下列任一步驟：

- 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **原則**] 區段 \> **保管庫連結** \> 按一下 [**通用設定**]，然後確認 [飛出] 中顯示的設定。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，執行下列命令並確認設定：

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。
