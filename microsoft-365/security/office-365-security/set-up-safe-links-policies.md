---
title: 在 Microsoft Defender 中設定 Office 365 的保管庫連結原則
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
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中查看、建立、修改和刪除保管庫連結原則及全域保管庫連結設定。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108208"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 中設定 Office 365 的保管庫連結原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。 如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保管庫[Microsoft Defender for Office 365](defender-for-office-365.md)中的連結提供郵件流程內輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 與連結的時間。 如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 連結](safe-links.md)。

沒有內建或預設的保管庫連結原則。 若要取得保管庫的連結掃描 URLs，您需要建立一個或多個保管庫連結原則，如本文所述。

> [!NOTE]
>
> 您可以在保管庫連結原則 **之外**，設定保管庫連結保護的全域設定。 如需相關指示，請參閱[Configure global settings for 保管庫 Office 365 的 Microsoft Defender 中的連結](configure-global-settings-for-safe-links.md)。
>
> 系統管理員應考慮保管庫連結的不同設定。 其中一個可用選項是將使用者身分識別資訊加入保管庫連結中。 這項功能可讓 *安全行動小組* 調查可能的使用者損損、採取糾正動作和限制昂貴的違規行為。

您可以設定 Microsoft 365 Defender 入口網站中的保管庫連結原則或 PowerShell (Exchange Online PowerShell，以供具有 Microsoft 365 信箱的合格 Exchange Online 組織使用。組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Microsoft Defender Office 365 附加元件訂閱) 。

保管庫連結原則的基本元素如下：

- **安全連結原則**：開啟保管庫連結保護，開啟即時 URL 掃描，指定在傳遞郵件之前是否等候即時掃描，請開啟 [內部郵件的掃描]，指定是否要在 URLs 上追蹤使用者按一下，並指定是否允許使用者按一下 [trough] 至原始 URL。
- **安全連結規則**：指定原則套用至) 的優先順序和收件者篩選 (。

當您在 Microsoft 365 Defender 入口網站中管理保管庫連結原則時，這兩個元素之間的差異並不明顯：

- 當您建立保管庫連結原則時，實際上是建立安全連結規則和關聯的安全連結原則，同時為這兩者使用相同的名稱。
- 當您修改保管庫連結原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全連結規則。 所有其他設定都會修改相關聯的安全連結原則。
- 當您移除保管庫連結原則時，會移除安全連結規則和相關聯的安全連結原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫連結原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)一節。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [**保管庫連結**] 頁面，請使用 <https://security.microsoft.com/safelinksv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派許可權，才能執行本文中的程式：
  - 若要建立、修改和刪除保管庫連結原則，您必須是 Microsoft 365 Defender 入口網站中 **組織管理** 或 **安全性管理員** 角色群組的成員，**以及** Exchange Online 中 **組織管理** 角色群組的成員。
  - 若要對保管庫連結原則進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  . - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **View-Only 組織管理** 角色群組也會提供該功能的唯讀許可權。

- 如需保管庫連結原則的建議設定，請參閱[保管庫連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

- [新功能會連續新增至 Microsoft Defender 以供 Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新增新功能時，您可能需要調整現有的保管庫連結原則。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>使用 Microsoft 365 Defender 入口網站建立保管庫連結原則

在 Microsoft 365 Defender 入口網站中建立自訂的保管庫連結原則，會同時使用相同的名稱建立安全連結規則和相關聯的安全連結原則。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。

3. 隨即會開啟 [**新增保管庫連結原則**] 嚮導。 在 [ **命名您的原則** ] 頁面上，設定下列設定：

   - **名稱**：輸入原則的唯一描述性名稱。
   - **說明**：輸入原則的選擇性說明。

   完成後，按 [下一步 **]**。

4. 在出現的 [ **使用者和網域** ] 頁面上，識別原則套用至 (收件者條件) 的內部收件者：
   - **使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。
   - **群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。
   - **網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。

   按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。 視需要重複此程序多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

   針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。 針對使用者，接著輸入星號 (\*) 來查看所有可用的值。

   相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

   - **排除這些使用者、群組和網域**：若要新增原則套用至 (收件者例外狀況) 的內部收件者例外狀況，請選取此選項並設定例外狀況。 設定和行為就像是條件。

   完成後，按 [下一步 **]**。

5. 在出現的 [ **保護設定** ] 頁面上，設定下列設定：
   - **在郵件中選取未知可能惡意 URLs 的動作**：選擇 [**開啟**]，可對電子郵件中的連結啟用保管庫連結保護。 如果您開啟此設定，則可以使用下列設定：
     - **對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此選項可在電子郵件訊息中啟用連結的即時掃描。 如果您在下列設定上開啟此設定，請使用：
       - **等候 URL 掃描完成後，才會傳遞郵件**：選取此選項可等到即時 URL 掃描完成之後，才會傳遞郵件。
     - 套用 **保管庫連結至組織內傳送的電子郵件**：選取此選項可將保管庫連結原則套用至內部寄件者和內部收件者之間的郵件。
   - **在 Microsoft Teams 內選取未知或可能惡意 URLs 的動作**：選取 [**開啟**] 以啟用 Teams 中連結的保管庫連結保護。
   - **請勿追蹤使用者點擊：請** 將此設定保留為未選取狀態，以啟用追蹤使用者按一下電子郵件中的 URLs。
   - **不允許使用者依序按一下原始 url**：選取此選項，可在 [警告頁面](safe-links.md#warning-pages-from-safe-links)中封鎖使用者按一下原始 url。
   - **請勿重新寫入下列 URLs**：允許存取保管庫連結所封鎖的指定 URLs。

     在方塊中，輸入您想要的 URL 或值，然後按一下 [ **新增**]。 視需要重複此步驟多次。

     若要移除現有的專案，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 專案旁邊。

     如需輸入語法，請參閱「 [不要重新寫入下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   如需這些設定的詳細資訊，請參閱[保管庫連結設定保管庫的電子郵件訊息](safe-links.md#safe-links-settings-for-email-messages)和[Microsoft Teams 的連結設定](safe-links.md#safe-links-settings-for-microsoft-teams)。

   如需標準和嚴格原則設定的建議值，請參閱[保管庫連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

   完成後，按 [下一步 **]**。

6. 在出現的 [ **通知** ] 頁面上，選取下列其中一個值，以瞭解 **您要如何通知使用者？**：
   - **使用預設通知文字**
   - **使用自訂通知文字**：如果您選取這個值 (長度不能超過200個字元) 時，會出現下列設定：
     - **使用 Microsoft 翻譯工具進行自動當地語系化**
     - **自訂通知文字**：在此方塊中輸入自訂通知文字。

   完成後，按 [下一步 **]**。

7. 在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   當您完成時，按一下 [ **提交**]。

8. 在顯示的確認頁面上，按一下 [完成 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>使用 Microsoft 365 Defender 入口網站來查看保管庫連結原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，下列屬性會顯示在保管庫連結原則的清單中：
   - **名稱**
   - **狀態**
   - **優先順序**

3. 當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>使用 Microsoft 365 Defender 入口網站修改保管庫連結原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。

3. 在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 如需這些設定的詳細資訊，請參閱在本文中[使用 Microsoft 365 Defender 入口網站來建立保管庫連結原則](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)一節。  

若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。

### <a name="enable-or-disable-safe-links-policies"></a>啟用或停用保管庫連結原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。

3. 在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：
   - **原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。
   - **原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。

4. 在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。

5. 按一下原則詳細資料飛出視窗中的 [關閉 **]**。

回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。

### <a name="set-the-priority-of-safe-links-policies"></a>設定保管庫連結原則的優先順序

根據預設，保管庫連結的優先順序是根據在 (較舊原則中建立的順序，而不是舊原則) 的優先順序。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。 只有在您有多個原則時，變更原則的優先順序才有意義。

**附注**：

- 在 Microsoft 365 Defender 入口網站中，您只可以在建立保管庫連結原則之後，變更其優先順序。 在 PowerShell 中，您可以在建立安全連結規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。
- 保管庫連結原則會依顯示的連續處理 (第一個原則的 **Priority** 值為 0) 。 如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。

3. 在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：
   - **優先順序** 值為 **0** 的原則只有 [**降低優先順序**] 選項可用。
   - 具有最低 **優先順序** 值的原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。
   - 如果您有三個或多個原則，則最高和最低優先順序值之間的原則都具有 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。

   按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。

4. 完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>使用 Microsoft 365 Defender 入口網站移除保管庫連結原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。

2. 在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。 在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。

3. 在顯示的確認對話方塊中，按一下 [是 **]**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫連結原則

如先前所述，保管庫連結原則包含安全連結原則和安全連結規則。

在 PowerShell 中，安全連結原則與安全連結規則之間的差異很明顯。 您可以使用 **\* -SafeLinksPolicy** Cmdlet 來管理安全連結原則，也可以使用 **\* -SafeLinksRule** Cmdlet 來管理安全連結規則。

- 在 PowerShell 中，您必須先建立安全連結原則，然後建立安全連結規則，識別套用規則的原則。
- 在 PowerShell 中，您可以分別修改 [安全連結原則] 和 [安全連結] 規則中的設定。
- 當您移除 PowerShell 的安全連結原則時，不會自動移除對應的安全連結規則，反之亦然。

### <a name="use-powershell-to-create-safe-links-policies"></a>使用 PowerShell 建立保管庫連結原則

在 PowerShell 中建立保管庫連結原則的過程包括兩個步驟：

1. 建立安全連結原則。
2. 建立安全連結規則，以指定套用規則的安全連結原則。

> [!NOTE]
>
> - 您可以建立新的安全連結規則，並將現有的未關聯的安全連結原則指派給它。 安全連結規則無法與一個以上的安全連結原則相關聯。
>
> - 您可以在建立原則之前，在 PowerShell 中的新安全連結原則上設定下列設定 Microsoft 365 Defender，直到您建立原則為止：
>   - _在_ `$false` **New-SafeLinksRule** Cmdlet) 上，建立新原則做為已停用 (。
>   - 在 _\<Number\>_ **New-SafeLinksRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。
>
> - 在您將原則指派至安全連結規則之前，您在 PowerShell 中所建立的新安全連結原則不會顯示在 Microsoft 365 Defender 入口網站中。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>步驟1：使用 PowerShell 建立安全連結原則

若要建立安全連結原則，請使用下列語法：

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - 如需 _DoNotRewriteUrls_ 參數所使用之專案語法的詳細資訊，請參閱 [[不要重新寫入下列 URLs] 清單中的輸入語法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。
>
> - 如需使用 **Set-SafeLinksPolicy** Cmdlet 修改現有的安全連結原則時可用於 _DoNotRewriteUrls_ 參數的其他語法，請參閱本文稍後的 [使用 PowerShell 修改安全連結原則](#use-powershell-to-modify-safe-links-policies)一節。

此範例會建立名為 Contoso 的安全連結原則，並提供下列值：

- 開啟電子郵件訊息中的 URL 掃描和重新寫入。
- 開啟 Teams (中的 URL 掃描。點擊 [只供預覽]) 。
- 開啟已按一下的即時掃描 URLs，包括指向檔案的按一下連結。
- 等候 URL 掃描完成後，才能傳遞郵件。
- 開啟內部郵件的 URL 掃描及重新寫入。
- 追蹤與保管庫連結保護相關的使用者點擊 (我們不使用 _DoNotTrackUserClicks_ 參數，預設值為 $false，這表示會追蹤使用者按一下) 。
- 不允許使用者依序按一下原始 URL。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

如需詳細的語法及參數資訊，請參閱 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>步驟2：使用 PowerShell 建立安全連結規則

若要建立安全連結規則，請使用下列語法：

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

此範例會建立名為 Contoso 的安全連結規則，且具有下列條件：

- 此規則會與名為 Contoso All 的安全連結原則相關聯。
- 此規則會套用至 contoso.com 網域中的所有收件者。
- 因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。
-  (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

如需詳細的語法及參數資訊，請參閱 [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)。

### <a name="use-powershell-to-view-safe-links-policies"></a>使用 PowerShell 來查看安全連結原則

若要查看現有的安全連結原則，請使用下列語法：

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本範例會傳回所有安全連結原則的摘要清單。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

此範例會傳回名為 Contoso 主管的安全連結原則的詳細資訊。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。

### <a name="use-powershell-to-view-safe-links-rules"></a>使用 PowerShell 來查看安全連結規則

若要查看現有的安全連結規則，請使用下列語法：

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本範例會傳回所有安全連結規則的摘要清單。

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

若要依啟用或停用篩選規則的清單，請執行下列命令：

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

此範例會傳回名為 Contoso 主管的安全連結規則的詳細資訊。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>使用 PowerShell 修改安全連結原則

您無法在 PowerShell 中重新命名安全連結原則 (**Set-SafeLinksPolicy** 指令程式沒有 _Name_ 參數) 。 當您重新命名 Microsoft 365 Defender 入口網站的保管庫連結原則時，您只會重新命名安全連結 _規則_。

在 PowerShell 中修改安全連結原則的唯一進一步考慮，就是 (「[不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) 的 _DoNotRewriteUrls_ 參數可用語法：

- 若要新增將取代任何現有專案的值，請使用下列語法： `"Entry1","Entry2,..."EntryN"` 。
- 若要新增或移除值，而不影響其他現有的專案，請使用下列語法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

否則，當您建立安全連結原則時，可以使用相同的設定，如本文稍早的 [步驟1：使用 PowerShell 建立安全連結原則](#step-1-use-powershell-to-create-a-safe-links-policy) 一節所述。

若要修改安全連結原則，請使用下列語法：

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>使用 PowerShell 修改安全連結規則

當您在 PowerShell 中修改安全連結規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的安全連結規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全連結規則](#step-2-use-powershell-to-create-a-safe-links-rule) ] 區段所述時，就可以使用相同的設定。

若要修改安全連結規則，請使用下列語法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>使用 PowerShell 來啟用或停用安全連結規則

啟用或停用 PowerShell 中的安全連結規則可啟用或停用整個保管庫連結原則 (安全連結規則和指派的安全連結原則) 。

若要啟用或停用 PowerShell 中的安全連結規則，請使用下列語法：

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

本範例會停用名為「行銷部門」的安全連結規則。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

此範例會啟用相同規則。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule)。

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>使用 PowerShell 設定安全連結規則的優先順序

您可以對規則設定的最高優先順序值為 0。 您可以設定的最低值則取決於規則的數目。 例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。 變更現有規則的優先順序會對其他規則造成階層式影響。 例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。

若要設定 PowerShell 中安全連結規則的優先順序，請使用下列語法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。 優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 若要在建立新規則時設定其優先順序，請改用 **New-SafeLinksRule** Cmdlet 上的 _priority_ 參數。

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-remove-safe-links-policies"></a>使用 PowerShell 移除安全連結原則

當您使用 PowerShell 來移除安全連結原則時，並不會移除對應的安全連結規則。

若要移除 PowerShell 中的安全連結原則，請使用下列語法：

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

此範例會移除名為「行銷部門」的安全連結原則。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy)。

### <a name="use-powershell-to-remove-safe-links-rules"></a>使用 PowerShell 移除安全連結規則

當您使用 PowerShell 來移除安全連結規則時，並不會移除對應的安全連結原則。

若要移除 PowerShell 中的安全連結規則，請使用下列語法：

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

此範例會移除名為「行銷部門」的安全連結規則。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。

若要驗證保管庫的連結是否正在掃描郵件，請檢查可用的 Microsoft Defender 以 Office 365 報告。 如需詳細資訊，請參閱[View Office 365 的 Defender 報告](view-reports-for-mdo.md)]，然後[在 Microsoft 365 Defender 入口網站中使用 Explorer](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功建立、修改或移除保管庫連結原則，請執行下列任一步驟：

- 在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **威脅原則** \> **保管庫連結**。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，以 \<Name\> 原則或規則名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
