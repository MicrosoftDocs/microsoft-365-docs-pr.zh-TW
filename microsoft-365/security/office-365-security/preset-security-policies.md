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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 和 Microsoft Defender Office 365 的保護功能上套用標準和嚴格的原則設定
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb5fb2e882348e2cd0480abf5ad7217095b2522d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083485"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中的預設安全性原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

「預設」安全性原則提供集中式的位置，可讓使用者同時套用所有建議的垃圾郵件、惡意程式碼和網路釣魚原則。 無法設定原則設定。 相反地，這些是由 us 設定，並以資料中心的觀察和經驗為基礎，以進行保持有害內容與使用者之間的平衡，避免不必要的中斷。

本文的其餘部分將說明預設的安全性原則，以及如何加以設定。

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

可用的條件和例外狀況如下：

- **使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。
- **群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。
- **網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。

您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

### <a name="policies-in-preset-security-policies"></a>預先設定安全性原則中的原則

預設的安全性原則使用 EOP 和 Microsoft Defender for Office 365 中各種保護功能的對應原則。 在您指派 **標準保護** 或 **嚴格保護** 的預設安全性原則給使用者 _之後_，就會建立這些原則。 您無法修改這些原則。

- **Exchange Online Protection (EOP) 原則**：這包括具有 Exchange Online 信箱和獨立 EOP 組織的 Microsoft 365 組織，但沒有 Exchange Online 信箱：

  - 名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反垃圾郵件原則](configure-your-spam-filter-policies.md)。
  - 名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反惡意程式碼原則](configure-anti-malware-policies.md)。
  - EOP 欺騙設定) 的「**標準預先設定安全性原則**」和「**嚴格預設安全性 (原則**」[的反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。

- **適用于 Office 365 原則的 Microsoft Defender**：這包括具有 Microsoft 365 E5 或 Defender 的組織 Office 365 附加元件訂閱：

  - Microsoft Defender 中 Office 365 名為 **Standard Standard Standard security policy** and **Strict Standard security policy** 的反網路釣魚原則，其中包括：

    - EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [類比設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高級網路釣魚臨界值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - 保管庫名為 **Standard Standard security policy** and **Strict standard security policy** 的 [連結原則](set-up-safe-links-policies.md)。

  - 保管庫名為 **Standard Standard security policy** and **Strict standard security policy** 的 [附件原則](set-up-safe-attachments-policies.md)。

請注意，您可以將 EOP 保護套用至不同于 Microsoft Defender Office 365 保護的使用者。

### <a name="policy-settings-in-preset-security-policies"></a>預設安全性原則中的原則設定

您無法修改保護設定檔中的原則設定。 [EOP 和 Microsoft Defender for Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)會說明 **標準** 和 **嚴格** 的原則設定值。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>預先設定的安全性原則及其他原則的優先權順序

將多個原則套用至使用者時，下列順序會從最高優先順序套用至最低優先順序：

1. **嚴格保護** 預設安全性原則
2. **標準保護** 預設安全性原則
3. 自訂安全性原則
4. 預設的安全性原則

換句話說， **嚴格保護** 原則的設定會覆寫 **標準保護** 原則的設定，它會覆寫自訂原則中的設定，以覆寫預設原則中的設定。

## <a name="assign-preset-security-policies-to-users"></a>將預先設定的安全性原則指派給使用者

### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [ **預先設定的安全性原則** ] 頁面，請使用 <https://security.microsoft.com/presetSecurityPolicies> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要設定預先設定的安全性原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要針對預設安全性原則進行唯讀存取，您必須是 **全域讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 中其他功能所需的許可權 _和_ 許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>使用 Microsoft 365 Defender 入口網站將預置的安全性原則指派給使用者

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **範本化原則**] 區段 \> 中的 **安全性原則**。

2. 在 [ **標準防護** ] 或 [ **嚴格防護**] 底下，按一下 [ **編輯**]。

3. [套用 **標準保護** ] 或 [套用 **嚴格防護** ] 嚮導即會啟動。 在 [ **EOP 保護套用至** ] 頁面上，找出 [EOP 防護](#policies-in-preset-security-policies) 適用于 (收件者條件的內部收件者) ：
   - **使用者**
   - **群組**
   - **網域**

   按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。 視需要重複此程序多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

   針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。 針對使用者，接著輸入星號 (\*) 來查看所有可用的值。

   - **排除這些使用者、群組和網域**：若要新增原則套用至 (收件者例外狀況) 的內部收件者例外狀況，請選取此選項並設定例外狀況。 設定和行為就像是條件。

   完成後，按 [下一步 **]**。

4. 在適用于 Office 365 組織的 Microsoft Defender 中，您會進入的「 **Office 365 防護的 defender** 」套用至頁面，識別 [Microsoft Defender for Office 365 防護](#policies-in-preset-security-policies)所套用的內部收件者，以)  (的收件者條件。

   設定和行為完全像是 **EOP 防護套用至** 頁面。

   完成後，按 [下一步 **]**。

5. 在 [ **檢查並確認您的變更** ] 頁面上，確認您的選擇，然後按一下 [ **確認**]。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>使用 Microsoft 365 Defender 入口網站修改預設安全性原則的指派

修改 **標準保護** 或 **嚴格保護** 安全性原則指派的步驟，與初次 [指派預先設定的安全性原則給使用者](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)相同。

若要在仍然保留現有條件和例外狀況的情況下停用 **標準保護** 或 **嚴格保護** 安全性原則，請將切換滑動到 **停用** 的 ![ 切換功能 ](../../media/scc-toggle-off.png) 。 若要啟用這些原則，請將切換滑動至 [ **啟用** ![ 時開啟] ](../../media/scc-toggle-on.png) 。

### <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功將 **標準保護** 或 **嚴格保護** 安全性原則指派給使用者，請使用預設值與 **標準防護** 設定不同的保護設定，這與 **嚴格防護** 設定不同。

例如，針對偵測為垃圾郵件的電子郵件 (不會有高信心的垃圾郵件) 確認郵件會傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，並隔離為 **嚴格保護** 使用者。

或者，對於 [大宗郵件](bulk-complaint-level-values.md)，請確認 BCL 值6或更高版本將郵件傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，而且 bcl 值4或更高隔離郵件以取得 **嚴格保護** 使用者。
