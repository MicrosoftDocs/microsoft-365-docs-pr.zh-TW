---
title: 關於 Office 365 試用版的 Microsoft Defender
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: 系統管理員可以深入瞭解 Microsoft Defender Office 365 的試用模式
ms.openlocfilehash: ba01fa45ca9a4e2e5b3597378bf7ddafc8be3f56
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768743"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>關於 Office 365 試用版的 Microsoft Defender

Microsoft Defender Office 365 會保護您的組織免受電子郵件訊息、連結 (URLs) 及共同作業工具所造成的惡意威脅。 適用於 Office 365 的 Defender 包括：

- **威脅防護原則**：定義威脅防護原則，用來為組織設定適當的保護層級。
- **報告**：查看即時報告，以監視您組織中 Office 365 效能的 Defender。
- **威脅調查與回應功能**：使用先進的工具來調查、了解、模擬以及防止潛在威脅。
- **自動調查及回應功能**：節省調查和減輕威脅的時間和精力。

Office 365 試用版的 Microsoft Defender 是嘗試 Office 365 的 Defender 功能的最簡單方法，而設定它只需要幾次按一下。 在試用設定完成之後，組織中的所有 Office 365 的試用版方案1和方案2功能可在最多90天內取得。

> [!NOTE]
> 本文所述的自動設定目前是公開預覽，可能無法在您的位置提供。

## <a name="terms-and-conditions"></a>條款與條件

Office 365 試用版的 Defender 可用於90天，且可為所有使用者啟動。 如需詳細資訊，請參閱[Microsoft Defender Office 365 試用字詞 & 條件](defender-for-office-365-trial-terms-and-conditions.md)。

## <a name="set-up-a-defender-for-office-365-trial"></a>設定 Office 365 試用版的 Defender

試用版可讓組織輕鬆安裝和設定 Office 365 功能的 Defender。 在安裝期間，[在反垃圾郵件原則中](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)專用於 Office 365 的 Defender 的原則 (特別，[安全附件](safe-attachments.md)、[安全連結](safe-links.md)和模擬保護，) 是使用標準範本來套用，以供預設的[安全性原則](preset-security-policies.md)使用。

根據預設，這些原則的適用範圍是組織中的所有使用者，但是系統管理員可以在安裝程式期間或之後自訂原則，讓它們只適用于特定使用者。

在設定期間，也會為整個組織設定 MDO P2 或對等) 中 (所找到的 MDO 回應功能。 不需要任何原則範圍。

## <a name="licensing"></a>授權

在試用安裝程式中，Office 365 授權的 Defender 會自動套用至組織。 授權在前90天內沒有任何收費。

## <a name="permissions"></a>權限

若要開始或結束試用，您必須是 Azure Active Directory 中 **全域管理員** 或 **安全性管理員** 角色的成員。 如需詳細資訊，請參閱 [關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="additional-information"></a>其他資訊

在您註冊試用版之後，最多可能需要2個小時的時間，所做的變更和更新才可供使用。 而且，系統管理員必須登出後再登入以查看變更。

系統管理員可以移至 <> 卡，隨時停用試用版。

## <a name="availability"></a>可用性

Office 365 試用版的試用版，會逐步向外推行符合特定準則的現有客戶， (包括地理) ，而且沒有現有的試用版 Office 365 Plan 1 或 Plan 2 授權 (包含在其訂閱中或作為附加元件) 。

## <a name="learn-more-about-defender-for-office-365"></a>深入瞭解 Office 365 的 Defender

Office 365 的 Defender 可提供完整的功能蓋板，協助組織加強其企業的安全性。

您也可以在本[互動指南](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)中深入瞭解 Office 365 的 Defender。

![適用于 Office 365 概念圖表的 Microsoft Defender](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>預防

穩健的篩選堆疊可防止各種大量的大量型攻擊，包括商務電子郵件洩漏、認證網路釣魚、勒索代碼和高級惡意程式碼。

- [反網路釣魚原則： Office 365 中的 Defender 的獨佔設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [安全附件](safe-attachments.md)
- [安全連結](safe-links.md)

### <a name="detection"></a>偵測

業界領先的 AI 會偵測惡意和可疑的內容，並關聯攻擊模式，以找出保護的活動。

- [Microsoft Defender 中 Office 365 的即時檢視](campaigns.md)

### <a name="investigation-and-hunting"></a>調查和搜尋

強大的體驗可協助識別、優先考慮威脅，並利用高級搜尋功能追蹤所有 Office 365 的攻擊。

- [威脅瀏覽器和即時偵測](threat-explorer.md)
- [Office 365 的 Defender 中的即時報告](view-reports-for-mdo.md)
- [威脅追蹤器 - 新增和值得注意的功能](threat-trackers.md)
- 與[Microsoft 365 Defender](../defender/microsoft-365-defender.md)整合

### <a name="response-and-remediation"></a>回應和修正

大量的事件回應和自動化功能會 amplify 您的安全性小組的效能和效能。

- [Microsoft Defender 中 Office 365 的自動調查和回應 (AIR) ](office-365-air.md)

### <a name="awareness-and-training"></a>意識和訓練

透過用戶端應用程式內的整合體驗，豐富的類比和訓練功能會建立使用者知曉。

- [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>安全狀況

建議的範本和設定真知灼見可協助客戶取得並保持安全。

- [EOP 和 Microsoft Defender for Office 365 中的預設安全性原則](preset-security-policies.md)
- [EOP 和 Microsoft Defender for Office 365 中的保護原則的設定 analyzer](configuration-analyzer-for-security-policies.md)。

## <a name="give-feedback"></a>提供意見

您的意見反應可協助我們在保護您的環境時免受高級攻擊。 分享您的經驗和產品功能與試用結果的印象。
