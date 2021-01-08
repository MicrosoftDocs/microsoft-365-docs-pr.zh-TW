---
title: 在 Microsoft Defender for Office 365 中設定安全附件原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 瞭解如何定義安全附件原則，以利用電子郵件中的惡意檔來保護組織。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8dfdcc0779fb8b8438ee7a63d2f0e180cbb12ac9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780505"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中設定安全附件原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文適用於擁有[適用於 Office 365 的 Microsoft Defender](office-365-atp.md) 的商務客戶。 如果您是尋找 Outlook 中附件掃描相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全附件是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一項功能，可在 [Exchange ONLINE protection (EOP) ](anti-malware-protection.md)中，但在傳送給收件者之前，使用虛擬環境檢查輸入電子郵件中的附件。 如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全附件](atp-safe-attachments.md)。

沒有內建或預設的安全附件原則。 若要取得安全附件掃描電子郵件附件，您需要建立一個或多個安全附件原則，如本文所述。

您可以使用 Exchange Online 中的信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中設定安全附件原則;獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但使用 Defender for Office 365 附加元件訂閱) 。

安全附件原則的基本元素如下：

- **安全附件原則**：指定未知惡意程式碼偵測的動作，是否要將具有惡意軟體附件的郵件傳送至指定的電子郵件地址，以及是否要在無法完成安全附件掃描時傳遞郵件。
- **安全附件規則**：指定原則套用至) 的優先順序和收件者篩選 (。

當您在安全性 & 合規性中心管理安全附件原則時，這兩個元素之間的差異並不明顯：

- 當您建立安全附件原則時，實際上是同時建立安全附件規則和相關聯的安全附件原則，同時為這兩者使用相同的名稱。
- 當您修改安全附件原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全附件規則。 所有其他設定會修改關聯的安全附件原則。
- 當您移除安全附件原則時，會移除安全附件規則和相關聯的安全附件原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全附件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 一節。

> [!NOTE]
> 在 [安全附件設定] 的 [全域設定] 區域中，設定不會相依于安全附件原則的功能。 如需相關指示，請參閱在[microsoft 365 E5 中](safe-docs.md)[開啟 SharePoint、OneDrive 和 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)和安全檔的 ATP。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **安全附件** ] 頁面，請使用 <https://protection.office.com/safeattachmentv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派許可權，才能執行本文中的程式：
  - 若要建立、修改和刪除安全連結原則，您必須是 Security & 合規性中心內的「 **組織管理** 」或「 **安全性管理員** 」角色群組成員， **以及** Exchange Online 中的「 **組織管理** 」角色群組的成員。
  - 若要對安全連結原則進行唯讀存取，您必須是 Security & 合規性中心內 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md) 和 [Exchange Online 中的許可權](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 如需安全附件原則的建議設定，請參閱 [安全附件設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>使用安全性 & 規範中心建立安全附件原則

在安全性 & 合規性中心建立自訂安全附件原則，會同時使用相同的名稱建立安全附件規則和相關聯的安全附件原則。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 在 [ **安全附件** ] 頁面上，按一下 [ **建立**]。

3. [ **新增安全附件原則** ] 嚮導隨即開啟。 在 [ **命名您的原則** ] 頁面上，設定下列設定：

   - **名稱**：輸入原則的唯一描述性名稱。

   - **說明**：輸入原則的選擇性說明。

   完成後，按 [下一步]。

4. 在顯示的 [ **設定** ] 頁面上，設定下列設定：

   - **安全附件未知的惡意程式碼回應**：選取下列其中一個值：

     - **Off**：一般而言，我們不建議此值。
     - **監視**
     - **封鎖**：這是預設值，以及標準及嚴格的預設 [安全性原則](preset-security-policies.md)中的建議值。
     - **Replace**
     - **動態傳遞 (預覽功能)**

     這些值會在 [安全附件原則設定](atp-safe-attachments.md#safe-attachments-policy-settings)中說明。

   - **將附件傳送至下列電子郵件地址**：針對動作值 **封鎖**、 **監視** 或 **取代**，您可以選取 [ **啟用重新導向** ] 以傳送包含惡意軟體附件的郵件，以進行分析和調查的指定內部或外部電子郵件地址。

     標準和嚴格原則設定的建議是啟用重新定向。 如需詳細資訊，請參閱 [安全附件設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

   - **若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取專案**。安全附件所指定的動作會對郵件採取 **未知惡意程式碼回應** ，即使無法完成安全附件掃描也是一樣。 如果您選取 [ **已啟用重新導向**]，一定要選取此選項。 否則，郵件可能會遺失。

   完成後，按 [下一步]。

5. 在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。

   您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

   按一下 [ **新增條件**]。 在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：

   - **收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。
   - **收件者以成員的身分存在於**：指定您組織中的一或多個群組。
   - **收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。

   選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。

   - 在方塊中按一下，並在值清單中向內移動，以選取。
   - 按一下方塊中的 [開始輸入]，以篩選清單並選取值。
   - 若要新增其他值，請按一下方塊中的空白區域。
   - 若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。
   - 若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。

   若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。

   若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。 設定和行為就像是條件。

   完成後，按 [下一步]。

6. 在 [ **複查您的設定** ] 頁面上，複查您的設定。 您可以按一下每個設定的 [ **編輯** ] 進行修改。

   完成後，請按一下 **[完成]**。

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>使用安全性 & 規範中心來查看安全附件原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

   「即時」顯示原則詳細資料

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>使用安全性 & 規範中心來修改安全附件原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在 [原則詳細資料] 顯示的 [飛出] 中，按一下 [ **編輯原則**]。

[飛出] 中的可用設定與 [ [使用安全性 & 規範中心] 建立安全附件原則](#use-the-security--compliance-center-to-create-safe-attachments-policies) 一節中所述的相同。

若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。

### <a name="enable-or-disable-safe-attachments-policies"></a>啟用或停用安全附件原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 請注意 [ **狀態** ] 欄中的值：

   - 將切換向左移動 ![關閉原則](../../media/scc-toggle-off.png) 停用原則。

   - 向右移動切換 ![開啟原則](../../media/scc-toggle-on.png) 以啟用原則。

### <a name="set-the-priority-of-safe-attachments-policies"></a>設定安全附件原則的優先順序

根據預設，安全附件原則的優先順序會根據它們在 (較舊的原則中所建立的順序而降低優先順序) 。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

安全附件原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。

**附注**：在 [安全性 & 規範中心] 中，您只能在建立安全附件原則之後變更其優先順序。 在 PowerShell 中，您可以在建立安全附件規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。

若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序] 數字)。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在顯示的 [原則詳細資料] 中，按一下 [可用的優先順序] 按鈕。

   - **優先順序** 值為 **0** 的安全附件原則只有「**降低優先順序**」按鈕可用。

   - 具有最低 **優先順序** 值的安全附件原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。

   - 如果您有三個或更多安全附件原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。

4. 按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。

5. 完成時，請按一下 [關閉]。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>使用安全性 & 規範中心移除安全附件原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

2. 在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。

3. 在顯示的 [原則詳細資料] 中，按一下 [ **刪除原則**]，然後在出現的警告對話方塊中按一下 [ **是]** 。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全附件原則

如先前所述，安全附件原則是由安全附件原則和安全附件規則所組成。

在 PowerShell 中，安全附件原則與安全附件規則之間的差異很明顯。 您可以使用 **\* -SafeAttachmentPolicy** Cmdlet 來管理安全附件原則，也可以使用 **\* -SafeAttachmentRule** Cmdlet 來管理安全附件規則。

- 在 PowerShell 中，您先建立安全附件原則，然後建立可識別套用規則之原則的安全附件規則。
- 在 PowerShell 中，您可以分別修改安全附件原則和安全附件規則中的設定。
- 當您從 PowerShell 中移除安全附件原則時，不會自動移除對應的安全附件規則，反之亦然。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>使用 PowerShell 建立安全附件原則

在 PowerShell 中建立安全附件原則的過程包括兩個步驟：

1. 建立安全附件原則。
2. 建立安全附件規則，以指定套用規則的安全附件原則。

 **附註**：

- 您可以建立新的安全附件規則，並將現有的、未關聯的安全附件原則指派給它。 安全附件規則無法與一個以上的安全附件原則相關聯。

- 您可以在 PowerShell 中的新安全附件原則上設定下列設定，而這些原則在安全性 & 合規性中心內無法使用，直到您建立原則為止：
  - _在_ `$false` **New-SafeAttachmentRule** Cmdlet) 上，建立新原則做為已停用 (。
  - 在 _\<Number\>_ **New-SafeAttachmentRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。

- 在您將原則指派至安全附件規則之前，您在 PowerShell 中建立的新安全附件原則不會顯示在安全性 & 規範中心。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>步驟1：使用 PowerShell 建立安全附件原則

若要建立安全附件原則，請使用下列語法：

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

此範例會建立名為 Contoso 的安全附件原則，並提供下列值：

- 封鎖透過安全檔所找到之惡意程式碼的郵件掃描 (我們不會使用 _Action_ 參數，而且預設值是 `Block`) 。
- 已啟用重新導向，而且找到包含惡意程式碼的郵件會傳送至 sec-ops@contoso.com 進行分析和調查。
- 如果安全附件掃描無法使用或遇到錯誤，請勿傳遞郵件 (不是使用 _ActionOnError_ 參數，預設值則是 `$true`) 。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>步驟2：使用 PowerShell 建立安全附件規則

若要建立安全附件規則，請使用下列語法：

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

此範例會建立名為 Contoso 的安全附件規則，且具有下列條件：

- 此規則會與名為 Contoso All 的安全附件原則相關聯。
- 此規則會套用至 contoso.com 網域中的所有收件者。
- 因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。
-  (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>使用 PowerShell 來查看安全附件原則

若要查看現有的安全附件原則，請使用下列語法：

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本範例會傳回所有安全附件原則的摘要清單。

```PowerShell
Get-SafeAttachmentPolicy
```

此範例會傳回名為 Contoso 主管的安全附件原則的詳細資訊。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>使用 PowerShell 來查看安全附件規則

若要查看現有的安全附件規則，請使用下列語法：

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本範例會傳回所有安全附件規則的摘要清單。

```PowerShell
Get-SafeAttachmentRule
```

若要依啟用或停用篩選規則的清單，請執行下列命令：

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

此範例會傳回名為 Contoso 主管的安全附件規則的詳細資訊。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>使用 PowerShell 修改安全附件原則

您無法在 PowerShell 中重新命名安全附件原則 (**Set-SafeAttachmentPolicy** Cmdlet 沒有 _Name_ 參數) 。 當您在安全性 & 規範中心重新命名安全附件原則時，您只是重新命名安全附件 _規則_。

否則，當您建立安全附件原則時，就會使用相同的設定，如本文稍早 [使用 [步驟1：使用 PowerShell 來建立安全附件原則](#step-1-use-powershell-to-create-a-safe-attachment-policy) ] 區段所述。

若要修改安全附件原則，請使用下列語法：

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>使用 PowerShell 修改安全附件規則

當您在 PowerShell 中修改安全附件規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的安全附件規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全附件規則](#step-2-use-powershell-to-create-a-safe-attachment-rule) ] 區段所述時，就可以使用相同的設定。

若要修改安全附件規則，請使用下列語法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>使用 PowerShell 來啟用或停用安全附件規則

啟用或停用 PowerShell 中的安全附件規則可啟用或停用安全附件規則和指派的安全附件原則)  (的整個安全附件原則。

若要啟用或停用 PowerShell 中的安全附件規則，請使用下列語法：

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

本範例會停用名為「行銷部門」的安全附件規則。

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

此範例會啟用相同規則。

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 和 [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)。

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>使用 PowerShell 設定安全附件規則的優先順序

您可以對規則設定的最高優先順序值為 0。 您可以設定的最低值則取決於規則的數目。 例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。 變更現有規則的優先順序會對其他規則造成階層式影響。 例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。

若要設定 PowerShell 中安全附件規則的優先順序，請使用下列語法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。 優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**附注**：若要在建立新規則時設定其優先順序，請改為在 **New-SafeAttachmentRule** Cmdlet 上使用 _priority_ 參數。

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>使用 PowerShell 移除安全附件原則

當您使用 PowerShell 來移除安全附件原則時，並不會移除對應的安全附件規則。

若要移除 PowerShell 中的安全附件原則，請使用下列語法：

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

此範例會移除名為 Marketing 部門的安全附件原則。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>使用 PowerShell 移除安全附件規則

當您使用 PowerShell 來移除安全附件規則時，並不會移除對應的安全附件原則。

若要在 PowerShell 中移除安全附件規則，請使用下列語法：

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

本範例會移除名為 Marketing 部門的安全附件規則。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功建立、修改或移除安全附件原則，請執行下列任一步驟：

- 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

若要驗證安全附件是否正在掃描郵件，請檢查可用的 Defender for Office 365 報告。 如需詳細資訊，請參閱 [View For Office 365 的 Defender 報告](view-reports-for-atp.md) 和 [使用 Explorer In Security & 合規性中心](threat-explorer.md)。
