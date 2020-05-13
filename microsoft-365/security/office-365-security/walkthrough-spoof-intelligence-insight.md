---
title: 逐步解說-欺騙性的智慧洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解欺騙性智慧洞察力的運作方式，包括如何快速判斷哪些寄件者可合法傳送您未驗證的電子郵件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a71b885926d742f86a5a0c86443a5f5ba23b8a6
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208461"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>逐步解說-在 Microsoft 365 中的 ATP 欺騙智慧洞察力

在使用高級威脅防護（ATP）的 Microsoft 365 組織中，您可以使用哄騙智慧真知灼見，快速判斷哪些寄件者可合法傳送您未驗證的電子郵件。 透過允許他們傳送哄騙郵件，您可以降低任何誤報給使用者的風險。 您也可以使用 [偽造智慧洞察力] 來監視和管理允許的網域對，以提供額外的安全性層級，並防止不安全的郵件到達您的組織中。

如果您不熟悉[安全性 & 規範中心的報表和洞察力](reports-and-insights-in-security-and-compliance.md)，它可能會協助您瞭解如何輕鬆從儀表板流覽至真知灼見及建議的動作。

此逐步解說是安全性 & 規範中心的其中一項。 若要瞭解如何導覽報表和真知灼見，請參閱相關主題區段中的演練。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [**安全性] 儀表板**頁面，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。 不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。

- 您必須已獲指派權限，才能執行這些程序。 若要使用欺騙性智慧洞察力，您必須是「**組織管理**」、「**安全性管理員**」或「**安全性讀者**」角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 您可以在 ATP 反網路釣魚原則中啟用和停用欺騙智慧。 如需詳細資訊，請參閱[在 Microsoft 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

- 在包含 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）的 Microsoft 365 組織中，如果沒有 Exchange Online 信箱，您可以使用哄騙智慧來監視和管理您傳送未驗證郵件的寄件者。 如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心開啟欺騙性智慧洞察力

1. 在 [安全性 & 規範中心] 中，移至 [**威脅管理**] \> **儀表板。**

2. 在 [**洞察力**] 列中，尋找下列其中一個專案：

   - **已啟用欺騙情報**：此真知灼見稱為**欺詐網域，其驗證過去30天失敗**。 此為預設值。

   - **已停用欺騙情報**：以命名方式**啟用欺騙保護**的洞察力，並按一下該功能可讓您啟用欺騙智慧。

3. 儀表板上的洞察力顯示如下資訊：

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   這兩種洞察力分為兩種模式：

   - **洞察力模式**。 如果您已啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。

   - **If 模式**。 如果您未啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能*會*影響的郵件數目。

   無論是哪一種方式，顯示在真知灼見中的冒牌網域都會分為兩類：**可疑的網域配對**和**非可疑網域配對**。 這些類別會進一步細分為三個不同的桶，供您審閱。

   **網域對**是 [寄件者] 位址及傳送基礎結構的組合：

   - 寄件者位址是顯示在電子郵件客戶程式中的寄件者電子郵件地址。 此地址可識別電子郵件的作者。 也就是負責撰寫郵件的使用者或系統信箱。 此位址也稱為 `5322.From` 位址。

   - 傳送基礎結構（或寄件者）是寄件者 IP 位址的反向 DNS 查找（PTR 記錄）的組織網域。 如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過以 CIDR 標記法（/24）的255.255.255.0 子網路遮罩傳送 IP 加以識別。 例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。

   **可疑的網域配對**包括：

   - **高度信賴的哄騙**： Microsoft 365 收到強信號，表示這些網域是可疑的，根據歷史傳送模式和網域的信譽得分。 Microsoft 365 非常確信網域是哄騙的，而從這些網域傳送的郵件不太可能合法。

   - 「**可信哄騙**」： Microsoft 365 收到的是這些網域是可疑的，根據歷史傳送模式和網域的信譽分數。 Office 365 適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。 此 bucket 有更多的可能性包含誤報（FPs）的高可信度。

   - **非可疑的網域配對**（包括**rescued 欺騙**）： rescued 欺騙指的是未通過明確驗證檢查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的網域，但已通過我們的隱含電子郵件驗證檢查（[複合驗證](email-validation-and-authentication.md#composite-authentication)）。 因此，Microsoft 365 會代表您 rescued 郵件，而且不會對郵件採取任何反欺詐動作。

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。

1. 在 [偽造智慧洞察力] 中，按一下 [任何網域配對] （high、適中或 rescued）。

   隨即會出現 [**哄騙智慧真知灼見**] 頁面，顯示將未驗證郵件傳送至組織的寄件者清單。 此頁面上的資訊可協助您判斷是否已授權哄騙郵件，或者是否需要進一步採取動作。 您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。 （例如，按一下 [**郵件計數**] 或 [**最後一個看到**的列標題]）。

2. 選取表格中的專案，以開啟包含有關網域對之豐富資訊的詳細資訊窗格，包括以下的原因：我們所做的，您需要做的是，您需要做的是，一個網域摘要，WhoIs 有關寄件者的相關電子郵件，以及我們在您的租使用者中所看到的類似電子郵件。 在這裡，您也可以選擇從**AllowedToSpoof**安全寄件者清單中新增或移除網域對。

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>從 AllowedToSpoof 安全寄件者清單中新增或移除網域

您可以從 AllowedToSpoof 安全的寄件者清單中新增或移除網域，在 [欺騙性智慧洞察力] 的 [詳細資料] 窗格中檢查網域對。 只會據此設定切換。

這會修改欺騙性網域和傳送基礎結構的唯一網域組合，不會對整個冒牌網域或獨立傳送基礎結構提供覆蓋範圍。

例如，如果您將下列網域對新增至 ' AllowedToSpoof ' 寄件者允許清單：*冒牌網域*"gmail.com"，並傳送*基礎結構*" *mx.com"，* 則只有該網域對中的郵件才會遭到欺騙。 其他企圖哄騙 "gmail.com" 的寄件者，以及其他「tms.mx.com」嘗試欺騙的網域，會繼續受到欺騙智慧的保護。

## <a name="related-topics"></a>相關主題

[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)

[逐步解說 - 從儀表板到深入解析](from-a-dashboard-to-an-insight.md)

[逐步解說 - 從詳細報告到深入解析](from-a-detailed-report-to-an-insight.md)

[逐步解說 - 從深入解析到詳細報告](from-an-insight-to-a-detailed-report.md)