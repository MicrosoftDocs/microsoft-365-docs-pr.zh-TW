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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 系統管理員可以瞭解 Exchange Online Protection 中的反網路釣魚防護功能 (EOP) 和 Office 365 Advanced 威脅防護 (Office 365 ATP) 。
ms.openlocfilehash: f6d864a7f9995de64f3714dffcd1838b2480a627
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867172"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 中的反網路釣魚保護

*網路釣魚* 是一種電子郵件攻擊，可嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊。 有特定類別的網路釣魚。 例如：

- **Spear 網路釣魚** 使用具有焦點的自訂內容，專門為目標收件者量身定制 (一般會在攻擊者) 後，在收件者上偵測之後。

- **Whaling** 是導向組織中的主管或其他高價值目標，以達到最大效果。

- **商務電子郵件洩漏 (BEC) ** 使用偽造的信任寄件者 (財務主管、客戶、信任的協力廠商等。 ) 欺騙收件者以核准付款、轉帳基金或透露客戶資料。

- 在網路釣魚郵件中，加密您的資料和要求付款以進行解密的**勒索軟體**幾乎永遠不會開始。 反網路釣魚保護無法協助您解密加密的檔案，但可協助偵測與勒索軟體相關的初始網路釣魚郵件。 如需從勒索軟體攻擊復原的詳細資訊，請參閱 [從 Microsoft 365 的勒索軟體攻擊復原](recover-from-ransomware.md)。

隨著攻擊複雜度的日益增加，訓練的使用者甚至很難識別複雜的網路釣魚郵件。 幸運的是，Exchange Online Protection (EOP) ，此外，Office 365 的高級威脅防護中的其他功能 (Office 365 ATP) 可有所説明。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的反網路釣魚保護

EOP (，也就是沒有 ATP) 的 Microsoft 365 組織，包含可協助您保護組織免受網路釣魚威脅的功能：

- **詐騙情報**：檢閱來自內部和外部網域中寄件者的詐騙郵件，並允許或封鎖那些寄件者。 如需詳細資訊，請參閱 [在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。

- **EOP 中的反網路釣魚原則**：開啟或關閉哄騙情報、在 Outlook 中開啟或關閉未驗證的寄件者識別，以及指定封鎖的寄件者的動作， (移至 [垃圾郵件] 資料夾或隔離) 。 如需詳細資訊，請參閱 [CONFIGURE EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

- **隱含電子郵件驗證**： EOP 可增強內送)  (電子郵件的標準電子郵件[DMARC](use-dmarc-to-validate-email.md) [驗證檢查](set-up-spf-in-office-365-to-help-prevent-spoofing.md)，包括發[件人信譽](use-dkim-to-validate-outbound-email.md)、寄件者記錄、收件者記錄、行為分析和其他高級技巧，以協助識別偽造的寄件者。 如需詳細資訊，請參閱 [Microsoft 365 中的電子郵件驗證](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP 中的其他反網路釣魚保護

Office 365 ATP 包含更多和更高級的反網路釣魚功能：

- **ATP 反網路釣魚原則**：建立新的自訂原則、設定反模仿設定 (保護使用者和網域不會受到模擬) 、信箱智慧設定，以及可調整的高級網路釣魚閥值。 如需詳細資訊，請參閱 [在 Microsoft 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。 如需有關反網路釣魚原則和 ATP 反網路釣魚原則之間差異的詳細資訊，請參閱 [Microsoft 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。

- **即時檢視**：機器學習和其他試探法識別及分析與整個服務和組織有關之協同網頁網路攻擊的相關訊息。 如需詳細資訊，請參閱 [Office 365 ATP 中的市場即時檢視](campaigns.md)。

- **攻擊模擬器**：系統管理員可以建立虛假的網路釣魚郵件，並以教育工具形式傳送給內部使用者。 如需詳細資訊，請參閱 [Office 365 ATP 中的攻擊模擬器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他反網路釣魚資源

- 針對使用者： [從網路釣魚騙術和其他形式的線上欺詐進行保護](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 如何驗證寄件者位址，以防止網路釣魚](how-office-365-validates-the-from-address.md)。
