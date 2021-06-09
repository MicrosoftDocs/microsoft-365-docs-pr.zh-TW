---
title: 模擬深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解類比真知灼見的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b539cc50d3cf6ad637a749faa9d2cb5b2033b81
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821319"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Office 365 的 Defender 中的模仿洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。

類比是指電子郵件寄件者與實際或預期寄件者電子郵件地址非常類似的地方。 攻擊者常常會利用網路釣魚或其他類型的攻擊中的使用者模仿寄件者電子郵件地址，以取得收件者的信任。 這主要有兩種模擬類型：

- **網域** 模擬：非 lila@contoso.com，類比寄件者的電子郵件地址是 lila@ćóntoso.com。
- **使用者** 模擬：非 michelle@contoso.com，類比寄件者的電子郵件地址是 rnichell@contoso.com。

網域模擬與 [網域欺騙](anti-spoofing-protection.md)不同，因為模擬的網域通常是實際註冊的網域。 來自模擬網域中寄件者的郵件，通常可通過一般的電子郵件驗證檢查，以驗證 (SPF、DKIM 及 DMARC) 的欺騙嘗試。

模擬保護是適用于 Microsoft Defender Office 365 的反網路釣魚原則設定的一部分。 如需這些設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。

您可以使用 Microsoft 365 security center 中的模仿洞察力，快速識別已設定為模擬保護的模仿寄件者或寄件者網域中的郵件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以開啟安全性中心，網址為 <https://security.microsoft.com>。 若要直接移至 **反網路釣魚** 網頁上的類比洞察力，請使用 <https://security.microsoft.com/antiphishing> 。 若要直接移至 [模擬 **洞察力** ] 頁面，請使用 <https://security.microsoft.com/impersonationinsight> 。

- 您必須先在 [安全性中心] 中指派許可權，才能執行本文中的程式：
  - **組織管理**
  - **安全性系統管理員**
  - **安全性讀取者**
  - **全域讀取者**

  如需詳細資訊，請參閱 [安全性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

  **附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色 _，_ 可為使用者提供 Microsoft 365 中其他功能的必要許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

- 您可以在 Microsoft Defender 的反網路釣魚原則中啟用和設定模擬保護，以供 Office 365。 預設不會啟用類比保護。 如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="open-the-impersonation-insight-in-the-security-center"></a>在 [安全性中心] 開啟類比真知灼見

1. 在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，類比洞察力看起來像這樣：

   ![反網路釣魚原則頁面上的模擬洞察力和欺騙智慧](../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png)

   洞察力有兩種模式：

    - **深入瞭解模式**：如果在任何反網路釣魚原則中啟用並設定了模擬保護，則真知灼見會顯示在過去七天內，由模擬的網域和模擬使用者 (寄件者) 所偵測到的郵件數目。 這是所有反網路釣魚原則中偵測到的所有已模擬寄件者總數。
    - **假設模式**：如果未啟用並設定任何使用中的反網路釣魚原則，則洞察力會顯示在過去7天內，類比保護功能 *會* 偵測到的郵件數目。

若要查看模擬偵測的相關資訊，請按一下 [類比洞察力] 中的 [ **view impersonations** ]。

   > [!NOTE]
   > 如需有關欺騙智慧洞察力的詳細資訊，請參閱 [EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)。

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>從類比網域中的寄件者查看郵件相關資訊

在 [模擬洞察力] 中按一下 [ **View impersonations** ] 之後所出現的 [**類比洞察力**] 頁面，確認已選取 [**網域**] 索引標籤。 [ **網域** ] 索引標籤包含下列資訊：

- **寄件者網域**：模仿的網域，它是用來傳送電子郵件的網域。
- **郵件計數**：從過去7天類比寄件者網域的郵件數目。
- 模擬 **類型**：此值會顯示模擬 (的偵測位置（例如，**網域在位址) 中**）。
- 模擬的 **網域 (s)**：模擬的網域，它應接近于在反網路釣魚原則中為模擬保護設定的網域。
- **網欄位型別**：此值是自訂網域的內部網域或 **自訂網域** 的 **公司網域**。
- **原則**：偵測到模擬的網域的反網路釣魚原則。
- **允許模仿**：下列其中一個值：
  - **是**：網域已設定為受信任的網域 (反網路釣魚原則中的類比保護) 例外狀況。 已偵測到來自類比網域中寄件者的郵件，但允許。
  - **No**：網域已設定為在反網路釣魚原則中進行類比保護。 已偵測來自模擬網域中寄件者的郵件，並根據反網路釣魚原則中模擬網域的動作來採取行動。

您可以按一下 [選取的欄標題] 來排序結果。

若要篩選結果，您可以使用「 ![ 搜尋」圖示 ](../../media/m365-cc-sc-search-icon.png) **搜尋** 方塊來輸入以逗號分隔的值清單，以篩選結果。

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>從類比網域中的寄件者查看郵件的詳細資料

在 [模擬 **洞察力**] 頁面上的 [**網域**] 索引標籤上，選取其中一個可用的類比偵測。 出現的詳細資料浮出控制項包含下列資訊和功能：

- **要修改的選取專案模擬原則**：選取您要修改的受影響的反網路釣魚原則。 僅適用于原則中定義模擬網域的原則。 請參閱前一頁，查看哪個原則實際負責偵測模擬的網域 (可能是根據收件者和原則) 的優先順序而定。
- **新增至允許的模仿清單**：使用此切換，可在 [ **信任的寄件者和網域** ] 中新增或移除寄件者。 (類比例外狀況) 針對您選取的反網路釣魚原則：
  - 如果此專案的 **允許** 模擬值為 [ **否**]，則會關閉切換功能。 若要免除模擬保護評估此網域中的所有寄件者，請將開關滑動至 [開啟]：開啟開啟] ![ ](../../media/scc-toggle-on.png) 。 網域會新增至反網路釣魚原則之類比保護設定中的 [ **受信任的網域** ] 清單。
  - 如果此專案的 **允許** 模擬值為 **[是]**，則開啟切換功能。 若要透過模擬保護將此網域中的所有寄件者傳回評估，請將此開關滑動至 [關閉]： [關閉] ![ ](../../media/scc-toggle-off.png) 。 此網域會從反網路釣魚原則的類比保護設定中的 [ **受信任的網域** ] 清單中移除。
- 我們為何會發現這種情況。
- 您需要執行的工作。
- 列出類比網域的域摘要。
- WhoIs 寄件者的相關資料。
- 開啟 [威脅瀏覽器](threat-explorer.md) 的連結，以查看有關寄件者的其他詳細資料。
- 來自相同寄件者的類似郵件已傳遞給您的組織。

## <a name="view-information-about-messages-from-impersonated-senders"></a>查看類比寄件者的郵件相關資訊

在 [模擬洞察力] 中按一下 [ **View impersonations** ] 之後所出現的 [**類比洞察力**] 頁面，按一下 [**使用者**] 索引標籤。[**使用者**] 索引標籤包含下列資訊：

- **寄件者**：傳送電子郵件之模仿寄件者的電子郵件地址。
- **郵件數目**：來自于過去7天之模仿寄件者的郵件數目。
- **模仿類型**：此值是 **使用者在顯示名稱中**。
- 模擬 **使用者 (s)**：模擬之寄件者的電子郵件地址，其應接近于在反網路釣魚原則中為模擬保護設定的使用者。
- **使用者類型**：此值顯示套用的保護類型 (例如， **受保護的使用者** 或 **信箱智慧**) 。
- **原則**：偵測模擬寄件者的反網路釣魚原則。
- **允許模仿**：下列其中一個值：
  - **是**：寄件者已設定為「信任的使用者」 (反網路釣魚原則中的類比保護) 例外狀況。 偵測到來自類比寄件者的郵件，但允許。
  - **No**：在反網路釣魚原則中，寄件者已設定為類比保護。 偵測到寄件者的郵件會根據反網路釣魚原則中模擬使用者的動作偵測並處理。

您可以按一下 [選取的欄標題] 來排序結果。

若要篩選結果，您可以使用 [ **篩選寄件者** ] 方塊來輸入以逗號分隔的值清單，以篩選結果。

### <a name="view-details-about-messages-from-impersonated-senders"></a>從類比寄件者查看郵件的詳細資料

在 [**類比洞察力**] 頁面上的 [**使用者**] 索引標籤上，選取其中一個可用的模擬偵測。 出現的詳細資料浮出控制項包含下列資訊和功能：

- **要修改的選取專案模擬原則**：選取您要修改的受影響的反網路釣魚原則。 只提供在原則中定義模擬寄件者的原則。 請參閱上一頁，查看哪個原則實際負責偵測模擬寄件者 (可能是根據收件者和原則) 的優先順序而定。
- **新增至允許的模仿清單**：使用此切換，可在 [ **信任的寄件者和網域** ] 中新增或移除寄件者。 (類比例外狀況) 針對您選取的反網路釣魚原則：
  - 如果此專案的 **允許** 模擬值為 [ **否**]，則會關閉切換功能。 若要將收件者從類比保護中免除，請將切換滑動至 [開啟] 開啟 ![ ](../../media/scc-toggle-on.png) 。 寄件者會新增至反網路釣魚原則之類比保護設定中的 [ **信任的使用者** ] 清單。
  - 如果此專案的 **允許** 模擬值為 **[是]**，則開啟切換功能。 若要透過模擬保護將寄件者傳回評估，請將此開關滑動至 [關閉]： [關閉] ![ ](../../media/scc-toggle-off.png) 。 寄件者會從反網路釣魚原則的類比保護設定中的 [ **信任的使用者** ] 清單中移除。
- 我們為何會發現這種情況。
- 您需要執行的工作。
- 列出類比寄件者的寄件者摘要。
- WhoIs 寄件者的相關資料。
- 開啟 [威脅瀏覽器](threat-explorer.md) 的連結，以查看有關寄件者的其他詳細資料。
- 來自相同寄件者的類似郵件已傳遞給您的組織。
