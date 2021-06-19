---
title: 防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的反網路釣魚保護功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1539153282f14a13ddd9066350cbcdca2a074a
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029234"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 中的反網路釣魚保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*網路釣魚* 是一種電子郵件攻擊，會在看似來自合法或信任寄件者的訊息中嘗試竊取敏感性資訊。 有特定類別的網路釣魚。 例如：

- **Spear 網路釣魚** 使用具有焦點的自訂內容，專門為目標收件者量身定制 (一般會在攻擊者) 後，在收件者上偵測之後。

- **Whaling** 是導向組織中的主管或其他高價值目標，以達到最大效果。

- **商務電子郵件洩漏 (BEC)** 使用偽造的信任寄件者 (財務主管、客戶、信任的協力廠商等。 ) 欺騙收件者以核准付款、轉帳基金或透露客戶資料。 觀看[此影片](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)瞭解更多資訊。

- 在網路釣魚郵件中，加密您的資料和要求付款以進行解密的 **勒索軟體** 幾乎永遠不會開始。 反網路釣魚保護無法協助您解密加密的檔案，但可協助偵測與勒索軟體相關的初始網路釣魚郵件。 如需從勒索軟體攻擊復原的詳細資訊，請參閱[從 Microsoft 365 中的勒索軟體復原](recover-from-ransomware.md)。

隨著攻擊複雜度的日益增加，訓練的使用者甚至很難識別複雜的網路釣魚郵件。 幸運的是，Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的其他功能都有助。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的防網路釣魚保護

EOP (，也就是 Microsoft 365 沒有 Microsoft Defender for Office 365) 的功能包含可協助您保護組織免受網路釣魚威脅的功能：

- 欺詐 **情報**：使用哄騙情報洞察力，以查看來自外部和內部網域之郵件中的欺騙寄件者，並手動允許或封鎖所偵測到的寄件者。 如需詳細資訊，請參閱 [EOP 中的詐騙情報見解](learn-about-spoof-intelligence.md)。

- **EOP 中的反網路釣魚原則**：開啟或關閉欺騙智慧，開啟或關閉 Outlook 中的未驗證寄件者識別碼，並指定封鎖的欺騙寄件者的動作。 如需詳細資訊，請參閱 [CONFIGURE EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

- **在租用戶允許/封鎖清單中允許或封鎖詐騙寄件者**：當您覆寫詐騙情報見解中的決策時，詐騙寄件者會變成手動允許或封鎖項目，且只會出現在租用戶允許/封鎖清單的 **[詐騙]** 索引標籤上。 您也可以在詐騙情報偵測到詐騙寄件者之前，手動建立允許或封鎖項目。 如需詳細資訊，請參閱[管理 EOP 中的租用戶允許/封鎖清單](tenant-allow-block-list.md)。

- **隱含電子郵件驗證**： EOP 可增強內送)  (電子郵件的標準電子郵件 [](use-dmarc-to-validate-email.md) [驗證檢查](set-up-spf-in-office-365-to-help-prevent-spoofing.md)，包括發 [件人信譽](use-dkim-to-validate-outbound-email.md)、寄件者記錄、收件者記錄、行為分析和其他高級技巧，以協助識別偽造的寄件者。 如需詳細資訊，請參閱 [Microsoft 365 中的電子郵件驗證](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender 中的防網路釣魚防護

適用於 Office 365 的 Microsoft Defender 包含額外和進階的防網路釣魚功能：

- **Microsoft Defender 中 Office 365 的反網路釣魚原則**：針對特定郵件寄件者和寄件者網域、信箱智慧設定及可調整的高級網路釣魚臨界值，設定模擬防護設定。 如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-mdo-anti-phishing-policies.md)。 如需 EOP 中 Office 365 和反網路釣魚原則中的反網路釣魚原則之間差異的詳細資訊，請參閱[Microsoft 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。

- **即時檢視**：機器學習和其他試探法識別及分析與整個服務和組織有關之協同網頁網路攻擊的相關訊息。 如需詳細資訊，請參閱[Microsoft Defender 中 Office 365 的市場即時檢視](campaigns.md)。

- **攻擊模擬器**：系統管理員可以建立虛假的網路釣魚郵件，並以教育工具形式傳送給內部使用者。 如需詳細資訊，請參閱[適用于 Microsoft Defender 的 Office 365 中的攻擊模擬器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他反網路釣魚資源

- 針對使用者： [從網路釣魚騙術和其他形式的線上欺詐進行保護](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 如何驗證寄件者位址，以防止網路釣魚](how-office-365-validates-the-from-address.md)。
