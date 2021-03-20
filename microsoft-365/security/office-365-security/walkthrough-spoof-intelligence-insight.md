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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解欺騙性智慧洞察力的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc53d49401afe3a0d7871bf5f294126315aacfec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908091"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>逐步解說-Microsoft Defender for Office 365 中的欺騙智慧洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在使用 Office 的 Defender for Office 365 的 Microsoft 365 組織中，您可以使用「欺騙性智慧洞察力」快速判斷哪些外部寄件者可合法傳送您未經驗證的電子郵件 (來自未通過 SPF、DKIM 或 DMARC 檢查的網域的郵件) 。

透過允許已知的外部寄件者從已知位置傳送哄騙郵件，您可以減少誤報 (已標示為錯誤) 的良好電子郵件。 透過監視允許的欺騙寄件者，您可以提供額外的安全性層級，以防止不安全的郵件到達您的組織中。

如需報表和洞察力的詳細資訊，請參閱 [安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。

此逐步解說是安全性 & 規範中心的其中一項。 若要瞭解如何導覽報表和真知灼見，請參閱 [相關主題](#related-topics) 區段中的演練。

> [!NOTE]
> 「欺騙性智慧洞察力」顯示過去7天的資料。 Exchange Online 中的 [欺騙智慧原則](learn-about-spoof-intelligence.md) 和對應的 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) Cmdlet PowerShell 顯示過去30天的資料。 [SpoofMailReport](/powershell/module/exchange/get-spoofmailreport)顯示最多90天的資料。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **安全性] 儀表板** 頁面，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。 不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。

- 您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：
  - **組織管理**
  - **安全性系統管理員**
  - **安全性讀取者**
  - **全域讀取者**

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附注**：將使用者新增至 microsoft 365 系統管理中心的對應 Azure Active Directory 角色，可讓使用者具備安全性 & 合規性中心的許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

- 您可以在 Microsoft Defender for Office 365 中啟用和停用反網路釣魚原則中的欺騙智慧。 預設會啟用欺騙智慧。 如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

- 若要使用欺騙智慧來監視及管理傳送您未驗證之郵件的寄件者，請參閱 [在 Microsoft 365 中設定欺騙智慧](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心開啟欺騙性智慧洞察力

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **儀表板。**

2. 在 [ **洞察力** ] 列中，尋找下列其中一個專案：

   - **過去七天內可能會出現的欺騙網域**：此認知表示已啟用欺騙情報 (預設會啟用該功能) 。
   - **啟用欺騙保護**：此真知灼見表示已停用欺騙智慧，按一下洞察力可讓您啟用欺騙智慧。

3. 儀表板上的洞察力顯示如下資訊：

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   這兩種洞察力分為兩種模式：

   - **深入瞭解模式**：如果已啟用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能會影響的郵件數目。
   - **假設模式**：如果已停用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能 *會* 影響的郵件數目。

   無論是哪種方式，顯示在真知灼見中的欺騙性網域都會分為兩類： **可疑的網域** 和 **非可疑的網域**。

   - **可疑的網域** 包括：

     - 高度信賴性哄騙：根據電子郵件傳送模式和網域的信譽分數，我們強烈相信網域是哄騙的，而來自這些網域的郵件更可能是惡意的。

     - 適中的信譽哄騙：根據歷史傳送模式和網域的信譽分數，我們適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。 在此類別中，誤報很可能超出高可信度的欺騙。

   **非可疑網域**：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。 不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。 因此，不會對郵件採取任何反欺詐動作。

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>從哄騙情報洞察力中查看有關可疑網域的詳細資訊

1. 在 [偽造智慧洞察力] 中，按一下 [ **可疑的網域** 或 **非可疑的網域** ]，以移至 [ **偽造智慧洞察力** ] 頁面。 「 **欺騙性智慧洞察力** 」頁面包含下列資訊：

   - **冒牌網域**：電子郵件客戶程式的 [ **寄件者** ] 方塊中顯示的欺騙使用者網域。 此位址也稱為 `5322.From` 位址。
   - **基礎結構**：也稱為傳送 _基礎結構_。 ) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域。 如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。
   - **郵件數目**：傳送基礎結構至您的組織中，在過去7天內包含指定的冒牌網域的郵件數目。
   - **上次看到**：從包含欺騙網域之傳送基礎結構接收郵件的最後日期。
   - **哄騙類型**：此值為 **External**。
   - 是否 **允許哄騙？**：您在這裡看到的值包括：
     - **Yes**：來自欺騙使用者網域和傳送基礎結構的電子郵件會被允許，未被視為欺騙電子郵件。
     - **No**：來自欺騙使用者網域及傳送基礎結構的郵件會標示為欺騙。 此巨集指令是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。

     如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

2. 選取清單中的專案，以查看快顯視窗中網域/傳送基礎結構對的詳細資料。 此資訊包含：
   - 我們為何會發現這種情況。
   - 您需要執行的工作。
   - 網域摘要。
   - WhoIs 寄件者的相關資料。
   - 來自相同寄件者的您租使用者中所看到的類似訊息。

   在這裡，您也可以選擇從 **允許欺騙** 寄件者允許清單中，新增或移除網域/傳送基礎結構對。 只會據此設定切換。

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>將網域新增至允許的欺騙清單

從欺詐智慧洞察力中將網域新增至允許的欺騙性清單，只允許將冒牌網域 *和* 傳送基礎結構組合在一起。 不允許來自任何來源的冒牌網域的電子郵件，也不允許來自任何網域之傳送基礎結構的電子郵件。

例如，您可以讓下列網域成為允許的欺騙清單：

- **網域**： gmail.com
- **基礎結構**： tms.mx.com

只有來自該網域/傳送基礎結構對的電子郵件才會遭到欺騙。 不允許其他企圖哄騙 gmail.com 的寄件者。 來自 tms.mx.com 的其他網域中的郵件會受到欺騙智慧的檢查。

## <a name="related-topics"></a>相關主題

[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)