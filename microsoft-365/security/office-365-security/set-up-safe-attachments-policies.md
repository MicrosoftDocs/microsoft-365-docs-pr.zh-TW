---
title: 在 Microsoft Defender 中設定 Office 365 的保管庫附件原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 瞭解如何定義保管庫附件原則，以利用電子郵件中的惡意檔案保護您的組織。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108220"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 中設定 Office 365 的保管庫附件原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文適用於擁有[適用於 Office 365 的 Microsoft Defender](whats-new-in-defender-for-office-365.md) 的商務客戶。 如果您是尋找 Outlook 中附件掃描相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保管庫附件是[Microsoft Defender 中用於 Office 365](whats-new-in-defender-for-office-365.md)的功能，可使用虛擬環境在[Exchange Online Protection (EOP) 中的反惡意程式碼保護](anti-malware-protection.md)（但傳送至收件者）之後，檢查輸入電子郵件中的附件。 如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 附件](safe-attachments.md)。

沒有內建或預設的保管庫附件原則。 若要取得保管庫電子郵件附件掃描的附件，您必須建立一個或多個保管庫附件原則，如本文所述。

您可以在 Microsoft 365 Defender 入口網站中設定保管庫附件原則，或在 Exchange Online 中使用信箱 PowerShell (PowerShell Microsoft 365 使用中的信箱 Exchange Online;組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Defender Office 365 附加元件訂閱) 。

保管庫附件原則的基本元素如下：

- **安全附件原則**：指定未知惡意程式碼偵測的動作，是否要將具有惡意軟體附件的郵件傳送至指定的電子郵件地址，以及是否要在保管庫附件掃描無法完成時傳遞郵件。
- **安全附件規則**：指定原則套用至) 的優先順序和收件者篩選 (。

當您在 Microsoft 365 Defender 入口網站中管理保管庫附件原則時，這兩個元素之間的差異並不明顯：

- 當您建立保管庫附件原則時，實際上是同時建立安全附件規則和相關聯的安全附件原則，同時為這兩者使用相同的名稱。
- 當您修改保管庫附件原則時，與名稱、優先順序、啟用或停用的名稱或收件者篩選器相關的設定會修改安全附件規則。 所有其他設定會修改關聯的安全附件原則。
- 當您移除保管庫附件原則時，會移除安全附件規則和相關聯的安全附件原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫附件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)」一節。

> [!NOTE]
> 在 [保管庫附件設定] 的 [通用設定] 區域中，設定不依賴保管庫附件原則的功能。 如需相關指示，請參閱在[保管庫中](safe-docs.md)[開啟 SharePoint、OneDrive 及 Microsoft Teams 及 Microsoft 365 E5 檔的保管庫附件](turn-on-mdo-for-spo-odb-and-teams.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [**保管庫附件**] 頁面，請使用 <https://security.microsoft.com/safeattachmentv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須具備下列許可權，才可執行本文中的程式：
  - 若要建立、修改和刪除保管庫附件原則，您必須是 Microsoft 365 Defender 入口網站中 **組織管理** 或 **安全性管理員** 角色群組的成員，**以及** Exchange Online 中 **組織管理** 角色群組的成員。
  - 若要取得保管庫附件原則的唯讀存取權，您必須是 Microsoft 365 Defender 入口網站中 **全域讀取器** 或 **安全性讀者** 角色群組的成員。

  如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 如需保管庫附件原則的建議設定，請參閱[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

- 最多允許30分鐘，以套用新的或更新的原則。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>使用 Microsoft 365 Defender 入口網站建立保管庫附件原則

在 Microsoft 365 Defender 入口網站中建立自訂的保管庫附件原則，會同時使用相同的名稱建立安全附件規則和關聯的安全附件原則。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。

3. 原則精靈隨即開啟。 在 [ **命名您的原則** ] 頁面上，設定下列設定：
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

   - **排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。 設定和行為就像是條件。

   完成後，按 [下一步 **]**。

5. 在 [**設定**] 頁面上，設定下列設定：

   - **保管庫附件未知的惡意程式碼回應**：請選取下列其中一個值：
     - **Off**：一般而言，我們不建議此值。
     - **監視**
     - **封鎖**：這是預設值，以及標準及嚴格的預設 [安全性原則](preset-security-policies.md)中的建議值。
     - **Replace**
     - **動態傳遞 (預覽功能)**

     這些值會在[保管庫附件原則設定](safe-attachments.md#safe-attachments-policy-settings)中說明。

   - **以偵測到的附件重新導向郵件**：如果您選取 [ **啟用重新導向**]，您可以在 [ **傳送** 包含惡意程式碼附件的電子郵件] 方塊中，指定電子郵件地址，以傳送包含惡意程式碼附件進行分析和調查的郵件。

     標準和嚴格原則設定的建議是啟用重新定向。 如需詳細資訊，請參閱[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

   - **如果掃描無法完成 (超時或) 錯誤，請套用保管庫附件偵測回應**。保管庫附件指定的動作會對郵件採取 **未知惡意程式碼回應**，即使保管庫附件掃描無法完成也是一樣。 如果您選取此選項，請永遠選取 [ **啟用重新導向** ]，並指定電子郵件地址以傳送包含惡意程式碼附件的郵件。 否則，郵件可能會遺失。

   完成後，按 [下一步 **]**。

6. 在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   當您完成時，按一下 [ **提交**]。

7. 在顯示的確認頁面上，按一下 [完成 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>使用 Microsoft 365 Defender 入口網站來查看保管庫附件原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，下列屬性會顯示在原則清單中：
   - **名稱**
   - **狀態**
   - **優先順序**

3. 當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>使用 Microsoft 365 Defender 入口網站修改保管庫附件原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。

3. 在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 如需這些設定的詳細資訊，請參閱本文前面的[使用 Microsoft 365 Defender 入口網站來建立保管庫附件原則](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)一節。  

若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。

### <a name="enable-or-disable-safe-attachments-policies"></a>啟用或停用保管庫附件原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。

3. 在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：
   - **原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。
   - **原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。

4. 在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。

5. 按一下原則詳細資料飛出視窗中的 [關閉 **]**。

回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。

### <a name="set-the-priority-of-safe-attachments-policies"></a>設定保管庫附件原則的優先順序

根據預設，保管庫附件原則的優先順序是根據在 (較舊的原則中建立的順序，而不是舊的原則) 的優先順序。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

保管庫附件原則會以處理的順序顯示， (第一個原則的 **優先順序** 值為 0) 。

**附注**：在 Microsoft 365 Defender 入口網站中，您可以在建立保管庫附件原則之後，才變更其優先順序。 在 PowerShell 中，您可以在建立安全附件規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。

若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。 只有在您有多個原則時，變更原則的優先順序才有意義。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。

3. 在出現的 [原則詳細資料] 浮出視窗頂端，您會看到 [ **增加優先順序** ] 或 [ **降低] 優先順序** ，取決於目前的優先順序值和原則數目：
   - **優先順序** 值為 **0** 的原則只有 [**降低優先順序**] 選項可用。
   - 具有最低 **優先順序** 值的原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。
   - 如果您有三個或多個原則，則最高和最低優先順序值之間的原則都具有 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。

   按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。

4. 完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>使用 Microsoft 365 Defender 入口網站移除保管庫附件原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下原則的名稱，從清單中選取自訂原則。

3. 在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。

4. 在顯示的確認對話方塊中，按一下 [是 **]**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫附件原則

如先前所述，保管庫附件原則是由安全附件原則和安全附件規則所組成。

在 PowerShell 中，安全附件原則與安全附件規則之間的差異很明顯。 您可以使用 **\* -SafeAttachmentPolicy** Cmdlet 來管理安全附件原則，也可以使用 **\* -SafeAttachmentRule** Cmdlet 來管理安全附件規則。

- 在 PowerShell 中，您先建立安全附件原則，然後建立可識別套用規則之原則的安全附件規則。
- 在 PowerShell 中，您可以分別修改安全附件原則和安全附件規則中的設定。
- 當您從 PowerShell 中移除安全附件原則時，不會自動移除對應的安全附件規則，反之亦然。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>使用 PowerShell 建立保管庫附件原則

在 PowerShell 中建立保管庫附件原則是兩個步驟的程式：

1. 建立安全附件原則。
2. 建立安全附件規則，以指定套用規則的安全附件原則。

 **附註**：

- 您可以建立新的安全附件規則，並將現有的、未關聯的安全附件原則指派給它。 安全附件規則無法與一個以上的安全附件原則相關聯。

- 您可以在建立原則之前，于 Microsoft 365 Defender 入口網站上無法使用 PowerShell 中的新安全附件原則上設定下列設定：
  - _在_ `$false` **New-SafeAttachmentRule** Cmdlet) 上，建立新原則做為已停用 (。
  - 在 _\<Number\>_ **New-SafeAttachmentRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。

- 在您將原則指派至安全附件規則之前，您在 PowerShell 中所建立的新安全附件原則不會顯示在 Microsoft 365 Defender 入口網站中。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>步驟1：使用 PowerShell 建立安全附件原則

若要建立安全附件原則，請使用下列語法：

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

此範例會建立名為 Contoso 的安全附件原則，並提供下列值：

- 保管庫檔掃描時，封鎖所找到之惡意程式碼的郵件， (我們不會使用 _Action_ 參數，且預設值為 `Block`) 。
- 已啟用重新導向，而且找到包含惡意程式碼的郵件會傳送至 sec-ops@contoso.com 進行分析和調查。
- 如果保管庫附件掃描無法使用或遇到錯誤，請勿傳遞郵件 (我們不會使用 _ActionOnError_ 參數，預設值為 `$true`) 。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。

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

如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>使用 PowerShell 修改安全附件原則

您無法在 PowerShell 中重新命名安全附件原則 (**Set-SafeAttachmentPolicy** Cmdlet 沒有 _Name_ 參數) 。 當您重新命名 Microsoft 365 Defender 入口網站的保管庫附件原則時，您只會重新命名安全附件 _規則_。

否則，當您建立安全附件原則時，就會使用相同的設定，如本文稍早 [使用 [步驟1：使用 PowerShell 來建立安全附件原則](#step-1-use-powershell-to-create-a-safe-attachment-policy) ] 區段所述。

若要修改安全附件原則，請使用下列語法：

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>使用 PowerShell 修改安全附件規則

當您在 PowerShell 中修改安全附件規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的安全附件規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全附件規則](#step-2-use-powershell-to-create-a-safe-attachment-rule) ] 區段所述時，就可以使用相同的設定。

若要修改安全附件規則，請使用下列語法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>使用 PowerShell 來啟用或停用安全附件規則

啟用或停用 PowerShell 中的安全附件規則可啟用或停用整個保管庫附件原則 (安全附件規則和指派的安全附件原則) 。

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

如需詳細的語法及參數資訊，請參閱 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 和 [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule)。

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

如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功建立、修改或移除保管庫附件原則，請執行下列任一步驟：

- 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則** \> **保管庫附件**。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請按一下 [名稱]，然後在 [飛出] 中查看詳細資料，從清單中選取原則。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，以 \<Name\> 原則或規則名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

若要驗證保管庫附件是否正在掃描郵件，請檢查可用的 Defender 以取得 Office 365 報告。 如需詳細資訊，請參閱[View Office 365 的 Defender 報告](view-reports-for-mdo.md)]，然後[在 Microsoft 365 Defender 入口網站中使用 Explorer](threat-explorer.md)。
