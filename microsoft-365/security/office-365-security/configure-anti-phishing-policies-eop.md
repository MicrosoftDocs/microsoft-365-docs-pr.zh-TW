---
title: 在 EOP 中設定反網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用或不具有 Exchange Online 信箱，來建立、修改和刪除 Exchange Online Protection (EOP) 組織中可用的反網路釣魚原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec944a2bf6fa7600a9970a7354332d140293ab5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878541"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>在 EOP 中設定反網路釣魚原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，則會有預設的反網路釣魚原則，其中包含預設會啟用的有限的反欺騙功能。 如需詳細資訊，請參閱[防網路釣魚原則中的詐騙](set-up-anti-phishing-policies.md#spoof-settings)。

系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。 為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

具有 Exchange Online 信箱的組織可以設定 Microsoft 365 Defender 入口網站或 Exchange Online PowerShell 中的反網路釣魚原則。 獨立 EOP 組織只能使用 Microsoft 365 Defender 入口網站。

如需建立及修改可用於 Office 365 microsoft defender 的更高級防網路釣魚原則的詳細資訊，請參閱[在 microsoft defender 中設定 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

反網路釣魚原則的基本元素如下：

- **反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。
- **反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。

當您在 Microsoft 365 Defender 入口網站中管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。

- 當您建立反網路釣魚原則時，實際上是建立反網路釣魚規則，同時也為這兩者使用相同的名稱建立了關聯的反網路釣魚原則。
- 當您修改反網路釣魚原則時，與名稱、優先順序、啟用或停用的名稱和收件者篩選器相關的設定會修改反網路釣魚規則。 所有其他設定會修改關聯的反網路釣魚原則。
- 當您移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。

在 Exchange Online PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 設定反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies)一節。

每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：

- 原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。
- 此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。 任何您建立的自訂原則皆具有較高的優先順序。
- 此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。

若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以在中開啟 Microsoft 365 的 Defender 入口網站 <https://security.microsoft.com> 。 若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://security.microsoft.com/antiphishing> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

  您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **View-Only 組織管理** 角色群組也會提供該功能的唯讀存取權 <sup>\*</sup> 。

- 如需有關反網路釣魚原則的建議設定，請參閱 [EOP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。

- 允許套用更新的原則最多30分鐘。

- 如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>使用 Microsoft 365 Defender 入口網站建立反網路釣魚原則

在 Microsoft 365 Defender 入口網站中建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** 網頁] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。

3. 原則精靈隨即開啟。 在 [ **原則名稱** ] 頁面上，設定下列設定：
   - **名稱**：輸入原則的唯一描述性名稱。
   - **說明**：輸入原則的選擇性說明。

   完成後，按 [下一步 **]**。

4. 在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：
   - **使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。
   - **群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。
   - **網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。

   按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。 視需要重複此程序多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

   針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。 針對使用者，接著輸入星號 (\*) 來查看所有可用的值。

   相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

   - **排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。 設定和行為就像是條件。

   完成後，按 [下一步 **]**。

5. 在出現的 [ **網路釣魚閥值 & 保護** ] 頁面上，使用 [ **啟用欺騙情報** ] 核取方塊，以開啟或關閉欺騙智慧。 預設值為 (選取) 上，建議您將其保持開啟。 在下一個頁面上，設定要對封鎖的冒牌郵件採取的動作。

   若要關閉欺騙情報，請清除核取方塊。

   > [!NOTE]
   > 如果您的 MX 記錄未指向 Microsoft 365，您就不需要關閉反欺騙保護;請改為啟用連接器的增強篩選。 如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   完成後，按 [下一步 **]**。

6. 在顯示的 [動作 **]** 頁面上，設定下列設定：
   - **如果偵測到郵件為欺騙** 性：只有在先前頁面上選取 [ **啟用哄騙情報** ] 時，才可使用此設定。 在已封鎖的欺騙寄件者的郵件下拉式清單中，選取下列其中一項動作：
     - **將郵件移至收件者的 [垃圾郵件] 資料夾**
     - **隔離郵件**

   - **安全性秘訣 & 指示器**：只有在您選取 [在上一頁上 **啟用欺騙情報** ] 時，才可使用此設定：
     - **Show (？ ) （未驗證的寄件者以取得哄騙**）：如果郵件未通過 SPF 或 DKIM 檢查 **，且** 郵件未透過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)，則會在 Outlook 中的寄件者相片中新增問號。
     - **顯示「透過**」標籤：將透過 tag (chris@contoso.com 透過 Fabrikam.com) 新增至 [寄件者] 位址，如果不同于 DKIM 簽章中的網域或郵件的 [ **發件** 人] 位址。

       > [!NOTE]
       > 目前，「 **透過」標記** 設定並非所有組織皆可使用。 如果您沒有顯示「**透過」標記** 設定，則會使用 [**顯示 (？ ) 針對您組織中未驗證的寄件者進行欺騙** 設定）來控制 [問號]**和**[via] 標記。

     若要開啟設定，請選取核取方塊。 若要將它關閉，請清除核取方塊。

   完成後，按 [下一步 **]**。

7. 在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   當您完成時，按一下 [ **提交**]。

8. 在顯示的確認頁面上，按一下 [完成 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>使用 Microsoft 365 Defender 入口網站來查看反網路釣魚原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，下列屬性會顯示在反網路釣魚原則的清單中：

   - **名稱**
   - **狀態**
   - **優先順序**
   - **上次修改日期**

3. 當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>使用 Microsoft 365 Defender 入口網站修改反網路釣魚原則

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取原則。

3. 在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 如需這些設定的詳細資訊，請參閱本文前面的[使用 Microsoft 365 Defender 入口網站建立反網路釣魚原則](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)一節。  

   針對預設的反網路釣魚原則，「 **使用者、群組及網域** 」區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。

若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>啟用或停用自訂的反網路釣魚原則

您無法停用預設的反網路釣魚原則。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。

3. 在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：
   - **原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。
   - **原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。

4. 在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。

5. 按一下原則詳細資料飛出視窗中的 [關閉 **]**。

回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>設定自訂的反網路釣魚原則優先順序

根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

若要變更原則的優先順序，請按一下 [**增加優先順序**] 或 [**降低優先順序**] 的原則 (您無法直接修改 Microsoft 365 Defender 入口網站) 中的 **優先順序** 號碼。 只有在您有多個原則時，變更原則的優先順序才有意義。

 **附註**：

- 在 Microsoft 365 Defender 入口網站中，您只能在建立後變更反網路釣魚原則的優先順序。 在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。
- 反網路釣魚原則會依顯示的連續處理 (第一個原則的 **Priority** 值為 0) 。 預設的反網路釣魚原則的優先順序值是 **最低** 的，您無法變更。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。

3. 在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：
   - 具有 **Priority** 值 **0** 的反網路釣魚原則只有 [ **降低優先順序** ] 選項可用。
   - 具有最低 **優先順序** 值的反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。
   - 如果您有三個或更多的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。

   按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。

4. 完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>使用 Microsoft 365 Defender 入口網站來移除自訂的反網路釣魚原則

當您使用 Microsoft 365 Defender 入口網站移除自訂的反網路釣魚原則時，會同時刪除反網路釣魚規則和對應的反網路釣魚原則。 您無法移除預設的反網路釣魚原則。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。

2. 按一下原則的名稱，從清單中選取自訂原則。 在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。

3. 在顯示的確認對話方塊中，按一下 [是 **]**。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>使用 Exchange Online PowerShell 設定反網路釣魚原則

如先前所述，反網路釣魚原則是由反網路釣魚原則和反網路釣魚規則所組成。

在 Exchange Online PowerShell 中，反網路釣魚原則與反網路釣魚規則之間的差異很明顯。 您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。

- 在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。
- 在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。
- 當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。

> [!NOTE]
> 在獨立 EOP 組織中，使用 Exchange Online Protection PowerShell 無法使用下列 PowerShell 程式。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 建立反網路釣魚原則

在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：

1. 建立反網路釣魚原則。
2. 建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。

 **附註**：

- 您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。 反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。

- 您可以在建立原則之前，于 Microsoft 365 Defender 入口網站中無法使用 PowerShell 中的新反網路釣魚原則上設定下列設定：

  - _在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。
  - 在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。

- 在您將原則指派至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在 Microsoft 365 Defender 入口網站中。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步驟1：使用 PowerShell 建立反網路釣魚原則

若要建立反網路釣魚原則，請使用下列語法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚策略：

- 描述為：「調研部門原則」。
- 將哄騙的預設動作變更為「隔離」。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步驟2：使用 PowerShell 建立反網路釣魚規則

若要建立反網路釣魚規則，請使用下列語法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：

- 此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。
- 此規則適用於名為 Research Department 之群組的成員。
- 因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 來查看反網路釣魚原則

若要查看現有的反網路釣魚原則，請使用下列語法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>使用 PowerShell 來查看反網路釣魚規則

若要查看現有的反網路釣魚規則，請使用下列語法：

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

若要依啟用或停用篩選規則的清單，請執行下列命令：

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改反網路釣魚原則

除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則時，依照 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 中所述，您可以在本文中修改反網路釣魚原則時，使用相同設定。

- _MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。
- 您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。 當您在 Microsoft 365 Defender 入口網站中重新命名防網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。

若要修改反網路釣魚原則，請使用下列語法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改反網路釣魚規則

當您在 PowerShell 中修改反網路釣魚規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的反網路釣魚規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) ] 區段所述時，就可以使用相同的設定。

若要修改反網路釣魚規則，請使用下列語法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 來啟用或停用反網路釣魚規則

啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。 您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。

若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

本範例會停用名為「行銷部門」的反網路釣魚規則。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

此範例會啟用相同規則。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule)。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>使用 PowerShell 設定反網路釣魚規則的優先順序

您可以對規則設定的最高優先順序值為 0。 您可以設定的最低值則取決於規則的數目。 例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。 變更現有規則的優先順序會對其他規則造成階層式影響。 例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。

若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。 優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**附註**：

- 若要在建立新規則時設定其優先順序，請改用 **AntiPhishRule** Cmdlet 上的 _priority_ 參數。
- 預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序 **值。**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>使用 PowerShell 移除反網路釣魚原則

當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。

若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

此範例會移除名為「行銷部門」的反網路釣魚原則。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 移除反網路釣魚規則

當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。

若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

此範例會移除名為「行銷部門」的反網路釣魚規則。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已在 EOP 中成功設定反網路釣魚原則，請執行下列任一步驟：

- 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **原則**] 區段 \> **反網路釣魚**。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請按一下 [名稱]，然後在顯示的浮出控制項中查看詳細資料，以選取清單中的原則。

- 在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
