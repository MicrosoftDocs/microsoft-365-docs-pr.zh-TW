---
title: 設定 Microsoft Defender for Office 365 中的安全連結原則
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
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中查看、建立、修改及刪除安全連結原則及全域安全連結設定。
ms.openlocfilehash: ed95c72c98e0c9d59b9860e89843c5f9b4970c8e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846433"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>設定 Microsoft Defender for Office 365 中的安全連結原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文適用于具有 [Microsoft Defender For Office 365](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全連結是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一項功能，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結。 如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全連結](atp-safe-links.md)。

沒有內建或預設的安全連結原則。 若要取得 URLs 的安全連結掃描，您必須建立一個或多個安全連結原則，如本文所述。

您可以使用 Exchange Online 中的信箱，設定安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中的安全連結原則;獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但搭配 Microsoft Defender for Office 365 附加元件訂閱) 。

安全連結原則的基本元素如下：

- **安全連結原則** ：開啟安全連結保護，開啟即時 URL 掃描，指定在傳遞郵件之前是否等候即時掃描，請開啟 [內部郵件的掃描]，指定是否要在 URLs 追蹤使用者按一下，並指定是否允許使用者按一下原始 URL 的 trough。
- **安全連結規則** ：指定原則套用至) 的優先順序和收件者篩選 (。

當您在安全性 & 合規性中心管理安全連結原則時，這兩個元素之間的差異並不明顯：

- 當您建立安全連結原則時，實際上是建立安全連結規則和關聯的安全連結原則，同時為這兩者使用相同的名稱。
- 當您修改安全連結原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全連結規則。 所有其他設定都會修改相關聯的安全連結原則。
- 當您移除安全連結原則時，會移除安全連結規則和相關聯的安全連結原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 一節。

> [!NOTE]
> 您可以在安全連結原則 **以外** 的安全連結保護中，設定全域設定。 如需相關指示，請參閱 [在 Microsoft Defender For Office 365 中設定安全連結的通用設定](configure-global-settings-for-safe-links.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **安全連結** ] 頁面，請使用 <https://protection.office.com/safelinksv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看、建立、修改及刪除安全連結原則，您必須是下列其中一個角色群組的成員：

  - **組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員** 。 
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理** 。

- 如需安全連結原則的建議設定，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

- [新功能不斷新增至 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)。 新增新功能時，您可能需要調整現有的安全連結原則。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>使用安全性 & 規範中心建立安全連結原則

在安全性 & 合規性中心建立自訂安全連結原則，會同時使用相同的名稱建立安全連結規則及相關聯的安全連結原則。

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 在 [ **安全連結** ] 頁面上，按一下 [ **建立** ]。

3. [ **新增安全連結原則** ] 嚮導隨即開啟。 在 [ **命名您的原則** ] 頁面上，設定下列設定：

   - **名稱** ：輸入原則的唯一描述性名稱。

   - **說明** ：輸入原則的選擇性說明。

   完成後，按 [下一步]。

4. 在顯示的 [ **設定** ] 頁面上，設定下列設定：

   - **在郵件中選取未知可能惡意 URLs 的動作** ：選取 [ **開啟** ]，可對電子郵件中的連結啟用安全連結保護。

   - **選取 Microsoft 小組中未知或可能惡意的 URLs 的動作** ：選擇 [ **開啟** ]，可對小組中的連結啟用安全連結保護。

   - **對指向檔案的可疑連結和連結套用即時 URL 掃描** ：選取此設定可在電子郵件訊息中啟用連結的即時掃描。

   - **等候 URL 掃描完成後，才能傳遞郵件** ：選取此設定可等到即時 URL 掃描完成之後，才會傳遞郵件。

   - 套用 **安全連結至組織內傳送的電子郵件** ：選取此設定可將安全連結原則套用至內部寄件者和內部收件者之間的郵件。

   - **請勿追蹤使用者點擊：請** 將此設定保留為未選取狀態，以啟用追蹤使用者按一下電子郵件中的 URLs。

   - **不允許使用者依序按一下原始 url** ：選取此設定可在 [警告頁面](atp-safe-links.md#warning-pages-from-safe-links)中，禁止使用者按一下原始 url。

   - **請勿重新寫入下列 URLs** ：允許存取以安全連結封鎖的指定 URLs。

     在方塊中，輸入您想要的 URL 或值，然後按一下 ![新增按鈕圖示](../../media/ITPro-EAC-AddIcon.png).

     若要移除現有的專案，請選取該專案，然後按一下 ![刪除按鈕圖示](../../media/ITPro-EAC-DeleteIcon.png).

     如需輸入語法，請參閱「 [不要重新寫入下列 URLs 的輸入語法」清單](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   如需這些設定的詳細資訊，請參閱 Microsoft 小組的電子郵件訊息和[安全連結設定](atp-safe-links.md#safe-links-settings-for-microsoft-teams)[的安全連結設定](atp-safe-links.md#safe-links-settings-for-email-messages)。

   如需標準和嚴格原則設定的建議值，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

   完成後，按 [下一步]。

5. 在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。

   您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如， _\<recipient1\>_ 或 _\<recipient2\>_ )。 不同的條件或例外狀況則使用 AND 邏輯 (例如， _\<recipient1\>_ 和 _\<member of group 1\>_ )。

   按一下 [ **新增條件** ]。 在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：

   - **收件者是** ：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。
   - **收件者以成員的身分存在於** ：指定您組織中的一或多個群組。
   - **收件者網域為** ：指定組織中一或多個已設定公認網域中的收件者。

   選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。

   - 在方塊中按一下，並在值清單中向內移動，以選取。
   - 按一下方塊中的 [開始輸入]，以篩選清單並選取值。
   - 若要新增其他值，請按一下方塊中的空白區域。
   - 若要移除個別專案， **Remove** 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。
   - 若要移除整個條件，請 **Remove** 按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。

   若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。

   若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if** ] 底下的例外狀況。 設定和行為就像是條件。

   完成後，按 [下一步]。

6. 在 [ **複查您的設定** ] 頁面上，複查您的設定。 您可以按一下每個設定的 [ **編輯** ] 進行修改。

   完成後，請按一下 **[完成]** 。

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>使用安全性 & 規範中心來查看安全連結原則

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

   「即時」顯示原則詳細資料

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>使用安全性 & 規範中心來修改安全連結原則

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在 [原則詳細資料] 顯示的 [飛出] 中，按一下 [ **編輯原則** ]。

[飛出] 中的可用設定與 [ [使用安全性 & 規範中心] 建立安全連結原則](#use-the-security--compliance-center-to-create-safe-links-policies) 一節中所述。

若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。

### <a name="enable-or-disable-safe-links-policies"></a>啟用或停用安全連結原則

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 請注意 [ **狀態** ] 欄中的值：

   - 將切換開關向左移動以停用原則： ![關閉原則](../../media/scc-toggle-off.png).

   - 將切換開關向右移動以啟用原則： ![開啟原則](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>設定安全連結原則的優先順序

根據預設，安全連結原則的優先順序會根據在 (較舊的原則中所建立的順序，優先順序低於舊版的原則) 。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

安全連結原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。

**附注** ：在 [安全性 & 規範中心] 中，您只能在建立安全連結原則之後變更其優先順序。 在 PowerShell 中，您可以在建立安全連結規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。

若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序] 數字)。

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在顯示的 [原則詳細資料] 中，按一下 [可用優先順序] 按鈕：

   - **優先順序** 值為 **0** 的安全連結原則只有「 **降低優先順序** 」按鈕可用。

   - 具有最低 **優先順序** 值的安全連結原則 (例如， **3** ) 只有 [ **增加優先順序** ] 按鈕可用。

   - 如果您有三個或更多的安全連結原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。

4. 按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。

5. 完成時，請按一下 [關閉]。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>使用安全性 & 規範中心移除安全連結原則

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。

2. 在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在顯示的 [原則詳細資料] 中，按一下 [ **刪除原則** ]，然後在出現的警告對話方塊中按一下 [ **是]** 。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則

如先前所述，安全連結原則包含安全連結原則和安全連結規則。

在 PowerShell 中，安全連結原則與安全連結規則之間的差異很明顯。 您可以使用 **\* -SafeLinksPolicy** Cmdlet 來管理安全連結原則，也可以使用 **\* -SafeLinksRule** Cmdlet 來管理安全連結規則。

- 在 PowerShell 中，您必須先建立安全連結原則，然後建立安全連結規則，識別套用規則的原則。
- 在 PowerShell 中，您可以分別修改 [安全連結原則] 和 [安全連結] 規則中的設定。
- 當您移除 PowerShell 的安全連結原則時，不會自動移除對應的安全連結規則，反之亦然。

### <a name="use-powershell-to-create-safe-links-policies"></a>使用 PowerShell 建立安全連結原則

在 PowerShell 中建立安全連結原則的過程包括兩個步驟：

1. 建立安全連結原則。
2. 建立安全連結規則，以指定套用規則的安全連結原則。

 **附註** ：

- 您可以建立新的安全連結規則，並將現有的未關聯的安全連結原則指派給它。 安全連結規則無法與一個以上的安全連結原則相關聯。

- 您可以在 [安全性 & 規範中心] PowerShell 中的新安全連結原則上設定下列設定，直到您建立原則為止：

  - _在_ `$false` **New-SafeLinksRule** Cmdlet) 上，建立新原則做為已停用 (。
  - 在 _Priority_ _\<Number\>_ **New-SafeLinksRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。

- 您在 PowerShell 中建立的新安全連結原則不會顯示在安全性 & 規範中心，除非您將原則指派至安全連結規則。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>步驟1：使用 PowerShell 建立安全連結原則

若要建立安全連結原則，請使用下列語法：

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**附註** ：

- 如需 _DoNotRewriteUrls_ 參數所使用之專案語法的詳細資訊，請參閱 [[不要重新寫入下列 URLs] 清單中的輸入語法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

- 如需使用 **Set-SafeLinksPolicy** Cmdlet 修改現有的安全連結原則時可用於 _DoNotRewriteUrls_ 參數的其他語法，請參閱本文稍後的 [使用 PowerShell 修改安全連結原則](#use-powershell-to-modify-safe-links-policies)一節。

此範例會建立名為 Contoso 的安全連結原則，並提供下列值：

- 開啟電子郵件訊息中的 URL 掃描和重新寫入。
- 開啟小組中的 URL 掃描 (點擊 [只供預覽]) 。
- 開啟已按一下的即時掃描 URLs，包括指向檔案的按一下連結。
- 等候 URL 掃描完成後，才能傳遞郵件。
- 開啟內部郵件的 URL 掃描及重新寫入。
- 追蹤與安全連結保護 (相關的使用者按一下。我們不會使用 _DoNotTrackUserClicks_ 參數，而預設值則是 $false，這表示會追蹤) 的使用者按一下。
- 不允許使用者依序按一下原始 URL。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

如需詳細的語法及參數資訊，請參閱 [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。

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

如需詳細的語法及參數資訊，請參閱 [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。

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

如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>使用 PowerShell 修改安全連結原則

您無法在 PowerShell 中重新命名安全連結原則 ( **Set-SafeLinksPolicy** 指令程式沒有 _Name_ 參數) 。 當您在安全性 & 合規性中心重新命名安全連結原則時，您只會重新命名安全連結 _規則_ 。

在 PowerShell 中修改安全連結原則的唯一進一步考慮，就是 (「 [不要重新寫入下列 URLs」清單](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) 的 _DoNotRewriteUrls_ 參數可用語法：

- 若要新增將取代任何現有專案的值，請使用下列語法： `"Entry1","Entry2,..."EntryN"` 。
- 若要新增或移除值，而不影響其他現有的專案，請使用下列語法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

否則，當您建立安全連結原則時，可以使用相同的設定，如本文稍早的 [步驟1：使用 PowerShell 建立安全連結原則](#step-1-use-powershell-to-create-a-safe-links-policy) 一節所述。

若要修改安全連結原則，請使用下列語法：

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>使用 PowerShell 修改安全連結規則

當您在 PowerShell 中修改安全連結規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的安全連結規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全連結規則](#step-2-use-powershell-to-create-a-safe-links-rule) ] 區段所述時，就可以使用相同的設定。

若要修改安全連結規則，請使用下列語法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>使用 PowerShell 來啟用或停用安全連結規則

啟用或停用 PowerShell 中的安全連結規則可啟用或停用安全連結規則和指派的安全連結原則)  (的整體安全連結原則。

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

如需詳細的語法及參數資訊，請參閱 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。

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

**附注** ：若要在建立新規則時設定其優先順序，請改為在 **New-SafeLinksRule** Cmdlet 上使用 _priority_ 參數。

如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。

若要確認安全連結正在掃描郵件，請檢查可用的 Microsoft Defender for Office 365 報告。 如需詳細資訊，請參閱 [View For Office 365 的 Defender 報告](view-reports-for-atp.md) 和 [使用 Explorer In Security & 合規性中心](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功建立、修改或移除安全連結原則，請執行下列任一步驟：

- 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結** ]。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
