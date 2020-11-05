---
title: 逐步解說 - 欺騙情報深入解析
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
description: 系統管理員可以瞭解欺騙性智慧洞察力的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920475"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>逐步解說-Microsoft Defender for Office 365 中的欺騙智慧洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Office 的 Defender for Office 365 的 Microsoft 365 組織中，您可以使用哄騙情報洞察力，快速判斷哪些寄件者可以合法傳送您未驗證的電子郵件 (來自未通過 SPF、DKIM 或 DMARC 檢查) 的郵件。

透過允許已知寄件者從已知位置傳送哄騙郵件，您可以減少誤報 (已標示為錯誤) 的良好電子郵件。 透過監視允許的欺騙寄件者，您可以提供額外的安全性層級，以防止不安全的郵件到達您的組織中。

如需報表和洞察力的詳細資訊，請參閱 [安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。

此逐步解說是安全性 & 規範中心的其中一項。 若要瞭解如何導覽報表和真知灼見，請參閱 [相關主題](#related-topics) 區段中的演練。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **安全性] 儀表板** 頁面，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。 不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。

- 您必須已獲指派許可權，才能執行本主題中的程式。 若要使用哄騙智慧洞察力，您必須是下列其中一個角色群組的成員：

  - **組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員** 。 
  - **組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理** 。
  - [安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者** 。
  - [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理** 。

- 您可以在 Microsoft Defender for Office 365 中啟用和停用反網路釣魚原則中的欺騙智慧。 如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

- 若要使用欺騙智慧來監視及管理傳送您未驗證之郵件的寄件者，請參閱 [在 Microsoft 365 中設定欺騙智慧](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心開啟欺騙性智慧洞察力

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** ] \> **儀表板。**

2. 在 [ **洞察力** ] 列中，尋找下列其中一個專案：

   - **已啟用欺騙情報** ：此真知灼見稱為 **欺詐網域，其驗證過去30天失敗** 。 此為預設值。
   - **已停用欺騙情報** ：以命名方式 **啟用欺騙保護** 的洞察力，並按一下該功能可讓您啟用欺騙智慧。

3. 儀表板上的洞察力顯示如下資訊：

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   這兩種洞察力分為兩種模式：

   - **洞察力模式** ：如果已啟用欺騙智慧，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。

   - **假設模式** ：如果已停用欺騙智慧，則真知灼見會顯示過去30天內，我們的欺騙智慧功能 *會* 影響的郵件數目。

   無論是哪一種方式，顯示在真知灼見中的冒牌網域都會分為兩類： **可疑的網域配對** 和 **非可疑網域配對** 。 這些類別會進一步細分為三個不同的桶，供您審閱。

   **網域對** 是 [寄件者] 位址及傳送基礎結構的組合：

   - 寄件者位址是寄件者的電子郵件地址，顯示在電子郵件客戶程式的 [寄件者] 方塊中。 此位址也稱為 `5322.From` 位址。

   - 傳送基礎結構（或寄件者）是反向 DNS 查閱 (PTR 記錄) 的傳送 IP 位址的組織網域。 如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過 CIDR 標記法 (/24) 中的255.255.255.0 子網路遮罩傳送 IP 加以識別。 例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。

   **可疑的網域配對** 包括：

   - **高度信賴性哄騙** ：根據電子郵件傳送模式和網域的信譽分數，我們強烈相信網域是哄騙的，而來自這些網域的郵件更可能是惡意的。

   - **適中** 的信譽哄騙：根據歷史傳送模式和網域的信譽分數，我們適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。 在此類別中，誤報很可能超出高可信度的欺騙。

   - **非可疑的網域配對** (包括 **rescued 欺騙** ) ：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。 不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。 因此，不會對郵件採取任何反欺詐動作。

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。

1. 在 [偽造情報資訊] 中，按一下 [rescued 高]、[適中] 或 []) 中的任何網域 (對。

   [ **哄騙智慧洞察力** ] 頁面隨即顯示。 此頁面會向您顯示傳送未驗證電子郵件至組織的寄件者清單。

   此資訊可協助您判斷是否已授權哄騙郵件，或者是否需要進一步採取動作。

   您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。

2. 選取表格中的專案，以開啟包含網域配對相關資訊的詳細資料窗格。 此資訊包含：
   - 我們為何會發現這種情況。
   - 您需要執行的工作。
   - 網域摘要。
   - WhoIs 寄件者的相關資料。
   - 來自相同寄件者的您租使用者中所看到的類似訊息。

   在這裡，您也可以選擇從 **AllowedToSpoof** 安全寄件者清單中新增或移除網域對。

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>從 AllowedToSpoof 清單中新增或移除網域

您可以在網域對的欺騙性智慧洞察力的詳細資料窗格中，新增或移除網域 AllowedToSpoof (安全寄件者) ] 清單。 只會據此設定切換。

允許網域對只允許結合欺騙的網域 *和* 傳送基礎結構。 不允許來自任何來源的冒牌網域的電子郵件，也不允許來自任何網域之傳送基礎結構的電子郵件。

例如，您可以讓下列網域對傳送欺騙性郵件給您的組織：

- *冒牌網域* ： gmail.com "
- 傳送 *基礎結構* `tms.mx.com` ：

只允許來自該網域對的電子郵件進行欺騙。 不允許其他企圖哄騙 gmail.com 的寄件者。 來自 tms.mx.com 的其他網域中的郵件會受到欺騙智慧的檢查。

## <a name="related-topics"></a>相關主題

[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)
