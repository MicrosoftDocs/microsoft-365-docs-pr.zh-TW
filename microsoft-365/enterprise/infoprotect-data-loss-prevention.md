---
title: 步驟 5：設定資料外洩防護
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 365 中的資料外洩防護並且進行部署。
ms.openlocfilehash: e3d18bf54ecdfe11f8233163e7f200a70606d81d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636973"
---
# <a name="step-5-configure-data-loss-prevention"></a>步驟 5：設定資料外洩防護

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

透過安全性與合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監控及自動保護整個 Microsoft 365 的機密資訊。 使用 DLP 原則，您可以：

- 在多個位置識別敏感性資訊，例如 Exchange Online、SharePoint Online、商務用 OneDrive 及 Microsoft Teams。
- 藉由封鎖文件的存取或封鎖包含文件的電子郵件，防止意外共用敏感性資訊。
- 監視和保護 Excel、PowerPoint 和 Word 桌面版中的敏感性資訊。
- 透過電子郵件通知和原則提示協助使用者了解如何符合規範，而不中斷其工作流程。 
- 檢視 DLP 報告以了解有哪些內容符合您的組織的 DLP 原則。

DLP 原則會指定：

- **何地：** 位置，例如 Exchange Online、SharePoint Online 和商務用 OneDrive 網站，以及 Microsoft Teams 聊天和頻道。
- **何時：** 內容必須在特定原則規則內符合的條件。
- **如何：** 讓相符原則規則自動對相符條件採用的動作。

換句話說：

- 對於這個位置中的文件 (何地)，如果內容符合規則的條件 (何時)，則自動採用規則中指定的動作 (如何)。

若要決定您需要的一組 DLP 原則，您必須分析文件，以及文件中需要進行資料外洩防護的資料類型。 舉例來說，如果您是美國的金融組織，建立 DLP 原則來防止具有社會安全號碼的文件在組織外部共用，或以電子郵件傳送到組織外部的位置。

接下來，您進行設定並且使用測試位置來測試原則，以確保正確的 DLP 行為並且將誤判降至最低。

最後，您透過通知員工有新的原則及其所需的行為並且擴大位置範圍，在貴組織中推出該原則。

如需詳細資訊，請參閱[開始使用 DLP 原則建議](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)。

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step5)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 6](../media/stepnumbers/Step6.png)|[設定電子郵件加密](infoprotect-email-encryption.md)|


