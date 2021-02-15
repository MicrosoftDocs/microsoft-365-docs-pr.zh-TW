---
title: 關於 Microsoft Defender for Office 365 試用版
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
description: 系統管理員可以深入瞭解 Microsoft Defender for Office 365 的試用模式
ms.openlocfilehash: 6207ae117f06a0e5f10d4a7a47a251137c51df05
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233575"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>關於 Microsoft Defender for Office 365 試用版

Microsoft Defender for Office 365 保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。 適用於 Office 365 的 Defender 包括：

- **威脅防護原則**：定義威脅防護原則，用來為組織設定適當的保護層級。
- **報告**：查看即時報告，以監視您組織中的 Office 365 的 Defender。
- **威脅調查與回應功能**：使用先進的工具來調查、了解、模擬以及防止潛在威脅。
- **自動調查及回應功能**：節省調查和減輕威脅的時間和精力。

Microsoft Defender for Office 365 試用版是一種最簡單的方法，可嘗試使用 Office 365 的 Defender，而設定它只需要幾次按一下。 完成試用設定後，組織中的所有 Office 365 方案1和方案2功能都可在最多90天內取得。

> [!NOTE]
> 本文所述的自動設定目前是公開預覽，可能無法在您的位置提供。

## <a name="terms-and-conditions"></a>條款與條件

適用于90天的 Office 365 試用版可供使用，而且可以為您的所有使用者啟動。 如需詳細資訊，請參閱 [Microsoft Defender For Office 365 試用條款 & 條件](defender-for-office-365-trial-terms-and-conditions.md)。

## <a name="set-up-a-defender-for-office-365-trial"></a>設定 Office 365 試用版的 Defender

試用版可讓組織輕鬆安裝和設定 Office 365 的 Defender。 在安裝期間，[在反垃圾郵件原則中](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)專用於 Defender for Office 365 的原則 (具體地說，[安全附件](atp-safe-attachments.md)、[安全連結](atp-safe-links.md)和模擬保護) 會使用標準範本，以進行預設的[安全性原則](preset-security-policies.md)。

根據預設，這些原則的適用範圍是組織中的所有使用者，但是系統管理員可以在安裝程式期間或之後自訂原則，讓它們只適用于特定使用者。

在設定期間，也會為整個組織設定 MDO P2 或對等) 中 (所找到的 MDO 回應功能。 不需要任何原則範圍。

## <a name="licensing"></a>授權

在試用設定過程中，Office 365 的 Defender 會自動套用至組織。 授權在前90天內沒有任何收費。

## <a name="permissions"></a>權限

若要開始或結束試用，您必須是 Azure Active Directory 中 **全域管理員** 或 **安全性管理員** 角色的成員。 如需詳細資訊，請參閱 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="additional-information"></a>其他資訊

在您註冊試用版之後，最多可能需要2個小時的時間，所做的變更和更新才可供使用。 而且，系統管理員必須登出後再登入以查看變更。

系統管理員可以移至 <> 卡，隨時停用試用版。

## <a name="availability"></a>可用性

Office 365 試用版會逐步向外推出符合特定準則的現有客戶 (包括地理) ，而且沒有 Office 365 方案1的現有 Defender 或「計畫」2授權 (包含在其訂閱中或作為附加元件) 。

## <a name="learn-more-about-defender-for-office-365"></a>深入瞭解 Office 365 的 Defender

適用于 365 Office 的 Defender，可提供完整的功能蓋板，協助組織保護其企業。

您也可以在本 [互動指南](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)中深入瞭解 Office 365 的 Defender。

![Microsoft Defender for Office 365 概念圖表](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>預防

穩健的篩選堆疊可防止各種大量的大量型攻擊，包括商務電子郵件洩漏、認證網路釣魚、勒索代碼和高級惡意程式碼。

- [反網路釣魚原則： Office 365 的 Defender 中的獨佔設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [安全附件](atp-safe-attachments.md)
- [安全連結](atp-safe-links.md)

### <a name="detection"></a>偵測

業界領先的 AI 會偵測惡意和可疑的內容，並關聯攻擊模式，以找出保護的活動。

- [Microsoft Defender for Office 365 的即時檢視](campaigns.md)

### <a name="investigation-and-hunting"></a>調查和搜尋

強大的體驗可協助識別、優先考慮威脅，並提供高級搜尋功能，以追蹤跨 Office 365 的攻擊。

- [威脅瀏覽器和即時偵測](threat-explorer.md)
- [Defender for Office 365 的即時報告](view-reports-for-atp.md)
- [威脅追蹤器 - 新增和值得注意的功能](threat-trackers.md)
- 與[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)整合

### <a name="response-and-remediation"></a>回應和修正

大量的事件回應和自動化功能會 amplify 您的安全性小組的效能和效能。

- [Microsoft Defender for Office 365 中的自動調查和回應 (AIR) ](office-365-air.md)

### <a name="awareness-and-training"></a>意識和訓練

透過用戶端應用程式內的整合體驗，豐富的類比和訓練功能會建立使用者知曉。

- [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>安全狀況

建議的範本和設定真知灼見可協助客戶取得並保持安全。

- [EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則](preset-security-policies.md)
- [EOP 和 Microsoft Defender For Office 365 中保護原則的設定 analyzer](configuration-analyzer-for-security-policies.md)。

## <a name="give-feedback"></a>提供意見

您的意見反應可協助我們在保護您的環境時免受高級攻擊。 分享您的經驗和產品功能與試用結果的印象。
