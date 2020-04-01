---
title: 欺騙情報探索的演練
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
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
description: 請參閱新的欺騙性智慧洞察力的運作方式。
ms.openlocfilehash: 797cbc07fd068ae80edc6cea699f78b2304a8f6c
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081409"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>逐步解說：欺騙性智慧洞察力

透過使用哄騙智慧洞察力，您可以快速判斷哪些寄件者可合法傳送您未驗證的電子郵件。 透過允許他們傳送哄騙郵件，您可以降低任何誤報給使用者的風險。

此外，您也可以使用 [偽造智慧監視器] 和 [管理允許的網域對]，以提供額外的安全性層級，並防止不安全的郵件到達您的組織中。

如果您的工作或學校帳戶已具備 Office &amp; 365 全域系統管理員、安全性管理員或安全性讀取者的許可權，您可以使用安全規範中心中的欺騙智慧洞察力。 如需詳細資訊，請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

如果您是[Office 365 安全性&amp;與合規性中心內的報表和洞察力的](reports-and-insights-in-security-and-compliance.md)最新資訊，它可能會協助您瞭解如何輕鬆從儀表板流覽至真知灼見及建議的動作。

您可以在安全性&amp;與合規性中心的多個儀表板上查看哄騙智慧洞察力。 不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。

這是安全性&amp;與合規性中心的幾個演練中的其中一個。 若要瞭解如何導覽報表和真知灼見，請參閱相關主題區段中的演練。

## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>取得安全性&amp;與合規性中心的欺騙智慧洞察力

1. 若要開始，您需要[移至安全性&amp;與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。

2. 在安全性&amp;與合規性中心，移至 [**威脅管理** \> **儀表板]。**

3. 在 [**洞察力**] 列中，尋找 [偽造智慧洞察力]。 如果您已啟用欺騙情報，則真知灼見會有權**驗證過去30天內驗證失敗的欺騙性網域**。 如果您尚未啟用欺騙保護，則真知灼見會提示您使用標題 [**啟用欺騙防護**] 來執行此動作。

## <a name="about-the-insight-on-the-dashboard"></a>關於儀表板上的洞察力

儀表板上的洞察力顯示如下所示的資訊。

![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

這兩種洞察力分為兩種模式：

 **洞察力模式**。 如果您已啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。

 **If 模式**。 如果您未啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能*會*影響的郵件數目。

無論是哪種方式，顯示在真知灼見中的冒牌網域都會分為兩類;可疑的網域配對和非可疑的網域配對。 這些類別會進一步細分為三個不同的桶，供您審閱。 

*網域對*是 [寄件者：] 位址和傳送基礎結構的組合。 

- 「寄件者」位址是您的郵件應用程式顯示為 [寄件者] 位址的位址。 此地址可識別電子郵件的作者。 也就是負責撰寫郵件的使用者或系統信箱。 這有時稱為 5322.From 地址。

- 傳送基礎結構（或寄件者）是寄件者 IP 位址之 PTR 記錄的組織網域。 如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過以 CIDR 標記法（/24）的255.255.255.0 子網路遮罩傳送 IP 加以識別。 例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。

 **可疑的網域配對**包括：

- **高度信賴欺騙**。 Office 365 收到強信號，指出這些網域是可疑的，根據歷史傳送模式和網域的信譽分數而定。 Office 365 非常確信網域是哄騙的，而從這些網域傳送的郵件則不太可能合法。 

- **適中置信欺騙**。 Office 365 收到適中的信號，這些網域會根據歷史傳送模式和網域的信譽分數，來表示這些網域是可疑的。 Office 365 適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。 此 bucket 有更多的可能性包含誤報（FPs）的高可信度。

 **非可疑的網域配對**包括**rescued 欺騙**。 Rescued 欺騙是指失敗明確驗證檢查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的網域，但傳遞的是延伸驗證檢查。 因此，Office 365 會以您的身分 rescued 郵件，而且不會對郵件採取任何反欺詐動作。

## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。

1. 在 [偽造智慧洞察力] 中，按一下 [任何網域配對] （high、適中或 rescued）。

隨即會出現 [**哄騙智慧真知灼見**] 頁面，顯示將未驗證郵件傳送至組織的寄件者清單。 此頁面上的資訊可協助您判斷是否已授權哄騙郵件，或者您是否需要進一步採取動作。 您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。 （例如，按一下 [**郵件計數**] 或 [**最後一個看到**的列標題]）。

2. 選取表格中的專案，以開啟包含有關網域對之豐富資訊的詳細資訊窗格，包括以下的原因：我們所做的，您需要做的是，您需要做的是，一個網域摘要，WhoIs 有關寄件者的相關電子郵件，以及我們在您的租使用者中所看到的類似電子郵件。 在這裡，您也可以選擇從**AllowedToSpoof**安全寄件者清單中新增或移除網域對。

![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>從 AllowedToSpoof 安全寄件者清單中新增或移除網域

您可以從 AllowedToSpoof 安全的寄件者清單中新增或移除網域，在 [欺騙性智慧洞察力] 的 [詳細資料] 窗格中檢查網域對。 只會據此設定切換。

這會修改欺騙性網域和傳送基礎結構的唯一網域組合，不會對整個冒牌網域或獨立傳送基礎結構提供覆蓋範圍。 例如，如果您將下列網域對新增至 ' AllowedToSpoof ' 寄件者允許清單：*冒牌網域*"gmail.com"，並傳送*基礎結構*" *mx.com"，* 則只有該網域對中的郵件才會遭到欺騙。 其他企圖哄騙 "gmail.com" 的寄件者，以及其他「tms.mx.com」嘗試欺騙的網域，會繼續受到欺騙智慧的保護。

## <a name="related-topics"></a>相關主題

[深入了解詐騙情報](learn-about-spoof-intelligence.md)

[Office 365 的反詐騙保護](anti-spoofing-protection.md)

[逐步解說 - 從儀表板到深入解析](from-a-dashboard-to-an-insight.md)

[逐步解說 - 從詳細報告到深入解析](from-a-detailed-report-to-an-insight.md)

[逐步解說 - 從深入解析到詳細報告](from-an-insight-to-a-detailed-report.md)


