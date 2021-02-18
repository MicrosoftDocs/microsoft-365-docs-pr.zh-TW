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
description: 系統管理員可以瞭解如何建立、修改及刪除 Exchange Online Protection (EOP 中可用的反網路釣魚原則，以含或不含 Exchange Online 信箱的組織) 組織。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287910"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>在 EOP 中設定反網路釣魚原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)

在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，會有預設的反網路釣魚原則，其中包含預設啟用的有限的反欺騙功能。 如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。

系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。 為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

具有 Exchange Online 信箱的組織可在安全性 & 合規性中心或 Exchange Online PowerShell 中設定反網路釣魚原則。 獨立 EOP 組織只能使用安全性 & 合規性中心。

如需在適用365于 office 365 的 Microsoft Defender for Office 中建立及修改更高級的反網路釣魚原則的相關資訊，請參閱在 [Microsoft defender For office 365 中設定反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

反網路釣魚原則的基本元素如下：

- **反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。
- **反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。

當您在安全性 & 合規性中心管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。

- 當您建立反網路釣魚原則時，實際上是建立反網路釣魚規則，同時也為這兩者使用相同的名稱建立了關聯的反網路釣魚原則。
- 當您修改反網路釣魚原則時，與名稱、優先順序、啟用或停用的名稱和收件者篩選器相關的設定會修改反網路釣魚規則。 所有其他設定會修改關聯的反網路釣魚原則。
- 當您移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。

在 Exchange Online PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 設定反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 一節。

每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：

- 原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。
- 此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。 任何您建立的自訂原則皆具有較高的優先順序。
- 此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。

若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://protection.office.com/antiphishing> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

  您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。

- 您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：
  - 若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員 <sup>\*</sup> 。

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的「 **View-Only 組織管理**」角色群組也會提供該功能的唯讀存取權 <sup>\*</sup> 。
  - <sup>\*</sup> 在 [安全性 & 規範中心] 中，唯讀存取可讓使用者查看自訂反網路釣魚原則的設定。 唯讀使用者看不到預設反網路釣魚原則中的設定。

- 若要在獨立 EOP 中建立及修改反網路釣魚原則，您需要針對租使用者執行一些需要 _分解_ 的專案。 例如，在 Exchange 系統管理中心 (EAC) 中，您可以移至 [ **許可權** ] 索引標籤，選取現有的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後移除) 最終新增回的角色 (。 如果您的租使用者從未 hydrated，您會看到一個名為「 **更新組織」設定** 的對話方塊，其進度列應該會順利完成。 如需分解的詳細資訊，請參閱 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) Cmdlet (無法在獨立 EOP PowerShell 或安全性 & 規範中心) 。

- 如需有關反網路釣魚原則的建議設定，請參閱 [EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 允許套用更新的原則最多30分鐘。

- 如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>使用安全性 & 規範中心建立反網路釣魚原則

在安全性 & 合規性中心建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。

當您建立反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。 建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，按一下 [ **建立**]。

3. [ **建立新的反網路釣魚原則** ] 嚮導隨即開啟。 在 [ **命名您的原則** ] 頁面上，設定下列設定：

   - **名稱**：輸入原則的唯一描述性名稱。

   - **說明**：輸入原則的選擇性說明。

   完成後，按 [下一步]。

4. 在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。

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

5. 在 [ **複查您的設定** ] 頁面上，複查您的設定。 您可以按一下每個設定的 [ **編輯** ] 進行修改。

   當您完成時，按一下 [ **建立這個原則**]。

6. 在出現的確認對話方塊中，按一下 [ **確定** ]。

使用這些一般原則設定建立反網路釣魚原則之後，請使用下一節中的指示來設定原則中的保護設定。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>使用安全性 & 規範中心來修改反網路釣魚原則

請使用下列程式修改反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。

1. 如果您還沒有開啟安全性 & 規範中心，請移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 選取您要修改的自訂反網路釣魚原則。 如果已選取它，請取消選取它，然後再次選取。

3. 隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。 按一下任何區段中的 [ **編輯** ]，即可存取該區段中的設定。

   - 下列步驟會以區段出現的順序顯示，但不依序 (您可以選取及修改所有順序) 中的區段。

   - 按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳轉，您可以按一下 [**儲存**) ] 任何頁面 (] 或 [**取消**] 或 [**關閉** ![ ](../../media/scc-remove-icon.png) ] [關閉] 圖示，以回到 [**編輯您的 \<name\> 原則**] (頁面。

4. **原則設定**：按一下 [ **編輯** ]，修改當您在上一節中 [建立原則](#use-the-security--compliance-center-to-create-anti-phishing-policies) 時可用的相同設定：

   - **名稱**
   - **描述**
   - **套用對象**
   - **檢查您的設定**

   完成後，按一下 [ **儲存** ] 任何頁面。

5. **哄騙**：按一下 [ **編輯** ] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。 如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。

   請注意，Office 365 的 Defender 網路釣魚原則也提供這些相同設定。

   - **哄騙篩選設定**：預設值為 [ **開啟**]，建議您將其保持開啟。 若要將它關閉，請將開關滑動至 [ **關閉**]。 如需詳細資訊，請參閱 [在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。 如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **啟用未經驗證的寄件者功能**：預設值為 **On**。 若要將它關閉，請將開關滑動至 [ **關閉**]。

   - **動作**：指定對哄騙智慧失敗的郵件採取的動作：

     **如果電子郵件是由不允許哄騙您網域的人員所傳送**：

     - **將郵件移至收件者的 [垃圾郵件] 資料夾**
     - **隔離郵件**

   - 請 **複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。

     - 您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。
     - 您可以在此頁面 **上****直接切換** 下列設定：

       - **啟用 antispoofing 保護**
       - **啟用未經驗證的寄件者功能**

   完成後，按一下 [ **儲存** ] 任何頁面。

6. 回到 [**編輯您的原則 \<Name\>** ] 頁面上，複查您的設定，然後按一下 [**關閉**]。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>使用安全性 & 合規性中心來修改預設的反網路釣魚原則

預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。 若要修改預設的反網路釣魚原則，請執行下列步驟：

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，按一下 [ **預設原則**]。

3. 隨即會顯示 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面。 下列各節可供使用，其中包含 [修改自訂原則](#use-the-security--compliance-center-to-modify-anti-phishing-policies)時的相同設定。

   - **模擬**
   - **惡搞**
   - **進階設定**

   當您修改預設原則時，無法使用下列設定：

   - 您可以看到 [ **原則設定** ] 區段和 [值]，但沒有 **編輯** 連結，所以您無法修改設定 (原則名稱、描述，以及原則 (套用至所有收件者) ) 的原則。
   - 您無法刪除預設原則。
   - 您無法變更預設原則的優先順序 (它永遠套用於最後) 。

4. 在 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面上，複查您的設定，然後按一下 [ **關閉**]。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>啟用或停用自訂的反網路釣魚原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 請注意 [ **狀態** ] 欄中的值：

   - 將 [切換] 滑動至 [ **關閉** ] 以停用原則。

   - 將切換滑動至 **開啟** 以啟用原則。

您無法停用預設的反網路釣魚原則。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>設定自訂的反網路釣魚原則優先順序

根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

自訂的反網路釣魚原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。 預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是 **最低** 的，您無法變更它。

 **附注**：在 [安全性 & 規範中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。 在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。

若要變更原則的優先順序，您可以按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 中的原則 (您無法直接修改安全性 & 規範中心) 中的 **優先順序** 號碼。 如果您有多個原則，變更原則的優先順序只會有意義。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。

2. 選取您要修改的原則。 如果已選取它，請取消選取它，然後再次選取。

3. 隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。

   - **優先順序** 值為 **0** 的自訂反網路釣魚原則只有「**降低優先順序**」按鈕可用。

   - 具有最低 **優先順序** 值的自訂反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。

   - 如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。

4. 按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。

5. 完成時，請按一下 [關閉]。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>使用安全性 & 規範中心來查看反網路釣魚原則

1. 在安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 請執行下列其中一個步驟：

   - 選取您要查看的自訂反網路釣魚原則。 如果已選取它，請取消選取它，然後再次選取。

   - 按一下 [ **預設原則** ] 以查看預設的反網路釣魚原則。

3. 此時會出現 [**編輯您的原則 \<name\>** ] 快顯視窗，您可以在其中查看設定和值。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>使用安全性 & 規範中心移除反網路釣魚原則

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 選取您要移除的原則。 如果已選取它，請取消選取它，然後再次選取。

3. 在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。

您無法移除預設原則。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>使用 Exchange Online PowerShell 設定反網路釣魚原則

如先前所述，反網路釣魚原則是由反網路釣魚原則和反網路釣魚規則所組成。

在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。 您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。

- 在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。
- 在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。
- 當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。

> [!NOTE]
> 下列 PowerShell 程式無法在獨立 EOP 組織中使用 Exchange Online Protection PowerShell。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 建立反網路釣魚原則

在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：

1. 建立反網路釣魚原則。
2. 建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。

 **附註**：

- 您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。 反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。

- 您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：

  - _在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。
  - 在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。

- 在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步驟1：使用 PowerShell 建立反網路釣魚原則

若要建立反網路釣魚原則，請使用下列語法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚策略：

- 描述為：「調研部門原則」。
- 將哄騙的預設動作變更為「隔離」。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。

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

如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

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

如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。

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

如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改反網路釣魚原則

除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則時，依照 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 中所述，您可以在本文中修改反網路釣魚原則時，使用相同設定。

- _MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。

- 您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。 當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。

若要修改反網路釣魚原則，請使用下列語法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改反網路釣魚規則

當您在 PowerShell 中修改反網路釣魚規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的反網路釣魚規則，請參閱下一節。

否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) ] 區段所述時，就可以使用相同的設定。

若要修改反網路釣魚規則，請使用下列語法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

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

如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已在 Microsoft Defender for Office 365 中成功設定反網路釣魚原則，請執行下列任一步驟：

- 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。 請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。 若要查看更多詳細資料，請執行下列其中一個步驟：

  - 從清單中選取原則，然後在飛入的視窗中查看詳細資料。
  - 按一下 [ **預設原則** ]，然後在飛入的視窗中查看詳細資料。

- 在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
