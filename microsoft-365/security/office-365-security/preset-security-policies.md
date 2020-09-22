---
title: 預設安全性原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 和 Office 365 高級威脅防護 (ATP) 中，套用標準和嚴格的原則設定
ms.openlocfilehash: 35be2b1ebfcf7ef8b7aad5cc2d4b3dd7032806b2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202600"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>EOP 和 Office 365 ATP 中的預先設定安全性原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


「預設」安全性原則提供集中式的位置，可讓使用者同時套用所有建議的垃圾郵件、惡意程式碼和網路釣魚原則。 無法設定原則設定。 相反地，這些是由 us 設定，並以資料中心的觀察和經驗為基礎，以在保持有害內容不中斷其運作的情況下進行平衡。

本主題的其餘部分將說明預設的安全性原則，以及如何加以設定。

## <a name="what-preset-security-policies-are-made-of"></a>做為什麼預設安全性原則

預先設定的安全性原則包含下列元素：

- 設定檔
- 原則
- 原則設定

此外，如果有多個預先設定的安全性原則和其他原則套用至同一個人員，優先順序順序就很重要。

### <a name="profiles-in-preset-security-policies"></a>預先設定安全性原則中的設定檔

設定檔決定保護的層級。 可供使用的設定檔如下：

- **標準保護**：適用于大多數使用者的基準保護設定檔。
- **嚴格保護**：針對所選使用者的更為嚴格的保護設定檔 (高值目標或優先順序使用者) 。

您可以使用符合條件和例外狀況的規則，判斷哪些是設定檔或未套用至哪一個。

您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

可用的條件和例外狀況如下：

- 收件者**是**：信箱、郵件使用者或您組織中的郵件連絡人。
- 收件者屬於：您組織中**的群組的成員**。
- **收件者網域為**：已在 Microsoft 365 中設定的公認網域。

### <a name="policies-in-preset-security-policies"></a>預先設定安全性原則中的原則

預設的安全性原則使用 EOP 和 Office 365 ATP 中各種保護功能的對應原則。 在您指派**標準保護**或**嚴格保護**的預設安全性原則給使用者_之後_，就會建立這些原則。 您無法修改這些原則。

- **Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：
  
  - 名為**Standard Standard Security policy** And **Strict Standard Security policy**的[反垃圾郵件原則](configure-your-spam-filter-policies.md)。
  - 名為**Standard Standard Security policy** And **Strict Standard Security policy**的[反惡意程式碼原則](configure-anti-malware-policies.md)。
  - EOP 欺騙設定) 的「**標準預先設定安全性原則**」和「**嚴格預設安全性 (原則**」[的反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。

- **Office 365 Advanced 威脅防護 (ATP) 原則**：這包括使用 Microsoft 365 E5 或 OFFICE 365 ATP 附加元件訂閱的組織：

  - 名為 **Standard Standard Security policy** And **Strict Standard SECURITY policy**的 ATP 反網路釣魚原則，其中包括：

    - EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [類比設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高級網路釣魚臨界值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - 名為**Standard Standard Security policy** and Strict Standard **Security Policy**的[安全連結原則](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。

  - 名為**Standard Standard Security policy** and Strict Standard **Security Policy**的[安全附件原則](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。

請注意，您可以將 EOP 防護套用至不同的使用者，而不是 ATP 防護。

### <a name="policy-settings-in-preset-security-policies"></a>預設安全性原則中的原則設定

您無法修改保護設定檔中的原則設定。 [EOP 和 Office 365 ATP security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)會說明**標準**和**嚴格**的原則設定值。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>預先設定的安全性原則及其他原則的優先權順序

將多個原則套用至使用者時，下列順序會從最高優先順序套用至最低優先順序：

1. **嚴格保護** 預設安全性原則
2. **標準保護** 預設安全性原則
3. 自訂安全性原則
4. 預設的安全性原則

換句話說， **嚴格保護** 原則的設定會覆寫 **標準保護** 原則的設定，它會覆寫自訂原則中的設定，以覆寫預設原則中的設定。

## <a name="assign-preset-security-policies-to-users"></a>將預先設定的安全性原則指派給使用者

### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **預先設定的安全性原則** ] 頁面，請使用 <https://protection.office.com/presetSecurityPolicies> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須已獲派權限，才能進行此主題中的程序:

  - 若要設定預先設定的安全性原則，您必須是下列其中一個角色群組的成員：

    - **組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 
    - **組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。

  - 若要針對預設的安全性原則進行唯讀存取，您必須是下列其中一個角色群組的成員：

    - [安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。
    - [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>使用安全性 & 規範中心，將預先設定的安全性原則指派給使用者

1. 在 [安全性 & 規範中心] 中，移至 [**威脅管理**原則] 「預設 \> **Policy** \> **安全性原則**」。

2. 在 [ **標準防護** ] 或 [ **嚴格防護**] 底下，按一下 [ **編輯**]。

3. [套用 **標準保護** ] 或 [套用 **嚴格防護** ] 嚮導即會啟動。 在 [ **EOP 保護] 適用** 于步驟，識別 [EOP 防護](#policies-in-preset-security-policies) 適用的內部收件者：

   1. 按一下 [ **新增條件**]。 在出現的下拉式清單中，選取 [ **適用于**下列條件的條件：

      - **收件者是**
      - **收件者的成員屬於**
      - **收件者網域**

      您只能使用一次條件，但是您可以指定條件的多個值。 相同條件使用或邏輯 (的多個值，例如 _\<recipient1\>_ 或 _\<recipient2\>_) 。

   2. 您選取的條件會出現在陰影區段中。 在該區段中，按一下 [ **任何** ] 方塊。 如果您稍候片刻，便會出現一個清單，讓您可以選取值。 或者，您可以開始輸入值以篩選清單並選取值。 視需要重複此步驟多次。 若要移除個別值，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。 若要移除整個條件，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。

   3. 若要新增其他條件，請按一下 [ **新增條件** ]，然後從其餘的條件中選取。 使用不同的條件和邏輯 (例如， _\<recipient1\>_ 及 _\<member of group 1\>_) 。

      重複上述步驟，將值加入條件，並視需要重複此步驟，或在條件不足時重複此步驟。

   4. 若要新增例外狀況，請按一下 [ **新增條件**]。 在出現的下拉式清單中，選取 [ **除外**] 下的條件。 設定和行為就像是條件。

   完成後，按 [下一步]****。

4. 如果您的組織有 Office 365 ATP，您可以使用 **ATP 防護** ，以識別 [Office 365 ATP 防護](#policies-in-preset-security-policies) 適用的內部收件者。

   設定和行為完全像是 **EOP 保護套用至** 步驟。

   完成後，按 [下一步]****。

5. 在 [ **確認** ] 步驟中，確認您的選擇，然後按一下 [ **確認**]。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>使用安全性 & 合規性中心，修改預設安全性原則的指派

修改 **標準保護** 或 **嚴格保護** 安全性原則指派的步驟，與初次 [指派預先設定的安全性原則給使用者](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)相同。

若要停用 **標準保護** 或 **嚴格保護** 安全性原則，同時仍保留現有的條件和例外狀況，請將此切換滑動至 [ **停用**]。 若要啟用原則，請將開關滑動至 [ **啟用**]。

### <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功將 **標準保護** 或 **嚴格保護** 安全性原則指派給使用者，請使用預設值與 **標準防護** 設定不同的保護設定，這與 **嚴格防護** 設定不同。

例如，針對偵測為垃圾郵件的電子郵件 (不會有高信心的垃圾郵件) 確認郵件會傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，並隔離為 **嚴格保護** 使用者。

或者，針對 [大量電子郵件](bulk-complaint-level-values.md)，確認 BCL 值6或更高版本可將郵件傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，而且 bcl 值4或更高隔離郵件以取得 **嚴格保護** 使用者。
