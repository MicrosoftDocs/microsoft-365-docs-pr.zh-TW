---
title: Office 365 的防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: 根據預設，office 365 提供各種不同的防範網路釣魚攻擊，也是透過 Office 365 高級威脅防護（ATP）中的其他功能。 本主題將介紹可用於深入瞭解及實施 Office 365 中的反網路釣魚選項與策略的線上資源。
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537422"
---
# <a name="anti-phishing-protection-in-office-365"></a>Office 365 的防網路釣魚保護

*網路釣魚*會嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊的電子郵件攻擊。 有特定類別的網路釣魚。 例如：

- **Spear 網路釣魚**使用專門為目標收件者量身定制之非常專注和自訂的內容（通常是攻擊者在收件者的偵測之後）。

- **Whaling**是導向組織中的主管或其他高價值目標，以達到最大效果。

- **商務電子郵件安全（BEC）** 會使用偽造的信任寄件者（財務主管、客戶、信任的合作夥伴等等），以誘騙收件者以核准付款、轉帳基金或公開客戶資料。

- 在網路釣魚郵件中，加密您的資料和要求付款以進行解密的**勒索軟體**幾乎永遠不會開始。 反網路釣魚保護無法協助您解密加密的檔案，但可協助偵測與勒索軟體相關的初始網路釣魚郵件。 如需從勒索軟體攻擊復原的詳細資訊，請參閱[在 Office 365 中復原從勒索軟體攻擊](recover-from-ransomware.md)。

隨著攻擊複雜度的日益增加，訓練的使用者甚至很難識別複雜的網路釣魚郵件。 幸運的是，Exchange Online Protection （EOP）和 Office 365 高級威脅防護（ATP）中的其他功能都有助您的協助。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的反網路釣魚保護

EOP （也就是，不含 ATP 的 Office 365 組織）包含可協助您保護組織免受網路釣魚威脅的功能：

- **哄騙情報**：查看內部及外部網域中寄件者的欺騙性郵件，並允許或封鎖這些寄件者。 如需詳細資訊，請參閱[Configure 哄騙情報 In Office 365](learn-about-spoof-intelligence.md)。

- **預設的反網路釣魚原則**：開啟或關閉欺騙智慧，開啟或關閉 Outlook 中未驗證的寄件者識別，並指定封鎖的欺騙寄件者的動作（移至 [垃圾郵件] 資料夾或 [隔離]）。 如需詳細資訊，請參閱[CONFIGURE EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

- **隱含的電子郵件驗證**： EOP 可增強輸入電子郵件（[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及[DMARC](use-dmarc-to-validate-email.md)）的標準電子郵件驗證檢查，具有寄件者信譽、寄件者記錄、收件者記錄、行為分析，以及其他可協助識別偽造寄件者的高級技術。 如需詳細資訊，請參閱[Office 365 中的電子郵件驗證](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP 中的其他反網路釣魚保護

Office 365 ATP 包含更多和更高級的反網路釣魚功能：

- **ATP 反網路釣魚原則**：建立新的自訂原則、設定反模仿設定（保護使用者和網域不會模仿）、信箱智慧設定，以及可調整的高級網路釣魚臨界值。 如需詳細資訊，請參閱[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。 如需反網路釣魚原則和 ATP 反網路釣魚原則之間差異的詳細資訊，請參閱[Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。

- **即時檢視**：機器學習和其他試探法識別及分析與整個服務和組織有關之協同網頁網路攻擊的相關訊息。 如需詳細資訊，請參閱[Office 365 ATP 中的市場即時檢視](campaigns.md)。

- **攻擊模擬器**：系統管理員可以建立虛假的網路釣魚郵件，並以教育工具形式傳送給內部使用者。 如需詳細資訊，請參閱[Office 365 ATP 中的攻擊模擬器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他反網路釣魚資源

- 針對使用者：[保護您自己免受網路釣魚騙術和其他形式的線上欺詐](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)。

- [Office 365 如何驗證寄件者位址，以防止網路釣魚](how-office-365-validates-the-from-address.md)。
