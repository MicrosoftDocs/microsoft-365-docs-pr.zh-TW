---
title: 類比洞察力
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
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535759"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Office 365 的 Defender 中的模仿洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。

類比是指電子郵件寄件者與實際或預期寄件者電子郵件地址非常類似的地方。 攻擊者常常會利用網路釣魚或其他類型的攻擊中的使用者模仿寄件者電子郵件地址，以取得收件者的信任。 這主要有兩種模擬類型：

- **網域** 模擬：非 lila@contoso.com，類比寄件者的電子郵件地址是 lila@ćóntoso.com。
- **使用者** 模擬：非 michelle@contoso.com，類比寄件者的電子郵件地址是 rnichell@contoso.com。

網域模擬與 [網域欺騙](anti-spoofing-protection.md)不同，因為模擬的網域通常是實際註冊的網域。 來自模擬網域中寄件者的郵件，通常可通過一般的電子郵件驗證檢查，以驗證 (SPF、DKIM 及 DMARC) 的欺騙嘗試。

模擬保護是針對 Office 365 Microsoft Defender 所獨佔的反網路釣魚原則設定) 的一部分。 如需這些設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。

您可以使用類比洞察力，快速識別已設定為模擬保護的模仿寄件者或寄件者網域中的郵件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 **反網路釣魚** 網頁上的類比洞察力，請使用 <https://protection.office.com/antiphishing> 。

- 您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：
  - **組織管理**
  - **安全性系統管理員**
  - **安全性讀取者**
  - **全域讀取者**

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 的安全性 & 合規性中心 _和_ 許可權中所需的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

- 您可以在 Microsoft Defender 的反網路釣魚原則中啟用和設定模擬保護，以供 Office 365。 預設不會啟用類比保護。 如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心開啟類比洞察力

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。

2. 在 [主要 **反網路釣魚] 頁面** 上，模擬洞察力看起來像這樣：

   這兩種洞察力分為兩種模式：

    - **深入瞭解模式**：如果在任何反網路釣魚原則中啟用並設定模擬保護，則洞察力會顯示過去七天內，來自模擬寄件者的偵測郵件數目。 這是所有反網路釣魚原則中偵測到的所有已模擬寄件者總數。
    - **假設模式**：如果未啟用並設定任何使用中的反網路釣魚原則，則洞察力會顯示在過去7天內，類比保護功能 *會* 偵測到的郵件數目。

   無論是哪一種方式， **類比的網域** 都會顯示來自受保護網域中寄件者的郵件數目，而 **使用者** 模擬會顯示受保護使用者的郵件數目。

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>從類比網域中的寄件者查看郵件相關資訊

在 [類比洞察力] 上，按一下 [ **類比的網域**]。 開啟的 **模仿洞察力** 頁面包含下列資訊：

- **寄件者網域**：模仿的網域，它是用來傳送電子郵件的網域。 
- **郵件計數**：從過去7天類比寄件者網域的郵件數目。
- 模擬 **類型**：此值會顯示模擬 (的偵測位置（例如，**網域在位址) 中**）。
- 模擬的 **網域 (s)**：模擬的網域，它應接近于在反網路釣魚原則中為模擬保護設定的網域。
- **網欄位型別**：此值是自訂網域的內部網域或 **自訂網域** 的 **公司網域**。
- **原則**：偵測到模擬的網域的反網路釣魚原則。
- **允許模仿**：下列其中一個值：
  - **是**：網域已設定為受信任的網域 (反垃圾郵件原則中的類比保護) 例外狀況。 已偵測到來自類比網域中寄件者的郵件，但允許。
  - **No**：網域已設定為反垃圾郵件原則中的類比保護。 已偵測來自模擬網域中寄件者的郵件，並根據反垃圾郵件原則中模擬網域的動作來採取行動。

您可以按一下 [選取的欄標題] 來排序結果。

若要篩選結果，您可以使用 [ **篩選網域** ] 方塊來輸入以逗號分隔的值清單，以篩選結果。

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>從類比網域中的寄件者查看郵件的詳細資料

在 [ **類比洞察力** ] 頁面上，選取其中一個可用的列。 出現的詳細資料浮出控制項包含下列資訊和功能：

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

在 [類比洞察力] 上，按一下 [ **類比的使用者**]。 開啟的 **模仿洞察力** 頁面包含下列資訊：

- **寄件者**：傳送電子郵件之模仿寄件者的電子郵件地址。
- **郵件數目**：來自于過去7天之模仿寄件者的郵件數目。
- **模仿類型**：此值是 **使用者在顯示名稱中**。
- 模擬 **使用者 (s)**：模擬之寄件者的電子郵件地址，其應接近于在反網路釣魚原則中為模擬保護設定的使用者。
- **使用者類型**：此值顯示套用的保護類型 (例如， **受保護的使用者** 或 **信箱智慧**) 。
- **原則**：偵測模擬寄件者的反網路釣魚原則。
- **允許模仿**：下列其中一個值：
  - **是**：寄件者已設定為受信任的使用者 (反垃圾郵件原則中的類比保護) 例外狀況。 偵測到來自類比寄件者的郵件，但允許。
  - **No**：寄件者已設定為反垃圾郵件原則中的類比保護。 根據反垃圾郵件原則中模擬使用者的動作，偵測並處理來自類比寄件者的郵件。

您可以按一下 [選取的欄標題] 來排序結果。

若要篩選結果，您可以使用 [ **篩選寄件者** ] 方塊來輸入以逗號分隔的值清單，以篩選結果。

### <a name="view-details-about-messages-from-impersonated-senders"></a>從類比寄件者查看郵件的詳細資料

在 [ **類比洞察力** ] 頁面上，選取其中一個可用的列。 出現的詳細資料浮出控制項包含下列資訊和功能：

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
