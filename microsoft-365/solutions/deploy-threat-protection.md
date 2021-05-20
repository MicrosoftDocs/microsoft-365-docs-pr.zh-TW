---
title: 跨 Microsoft 365 部署威脅防護功能
description: 深入瞭解 Microsoft 365 E5 中的威脅防護服務和安全性功能。 使用 Microsoft 365 E5 保護您的使用者帳戶、裝置、電子郵件內容等等。
keywords: microsoft 威脅防護，defender，安裝程式，高級威脅防護，安全性，microsoft 365 E5，保護裝置
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583217"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>跨 Microsoft 365 E5 部署威脅防護功能

此解決方案說明 Microsoft 365 E5 中強大的威脅防護功能，以及威脅防護很重要的原因。 深入瞭解 Microsoft 365 E5 中的威脅防護，並瞭解如何為您的組織進行安裝和設定。

## <a name="why-threat-protection-is-important"></a>威脅防護為何很重要 

[惡意](/windows/security/threat-protection/intelligence/understanding-malware)代碼和複雜的 cyberattacks （例如 [fileless 威脅](/windows/security/threat-protection/intelligence/fileless-threats)）都是常見的時機。 企業必須以有效的 IT 安全性功能來保護自己及其客戶。 Cyberattacks 可能會造成組織的主要問題，包括從失去信任到財務 woes、業務威脅停機等等。 防護威脅很重要，但決定組織的時間、精力和資源的位置，可能會有很大的難度。 Microsoft 365 E5 可以提供協助。 

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 威脅防護

Microsoft 的安全性解決方案已內置於我們的產品和服務中。 「自動化」和「機器學習」功能可減少安全性小組的負載，以確保處理適當的專案。 Microsoft 安全性解決方案的強項是以 trillions 在我們每天處理的[智慧安全性 Graph](/graph/security-concept-overview)中的信號來建立。 Microsoft 365 安全性解決方案包括[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)，一種在您的電子郵件、資料、裝置和身分識別的信號，以繪製組織的高級威脅圖片。

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)可讓您使用可自我調整的內建智慧來保護您的組織。 使用 Microsoft 365 E5 中的安全性功能，您可以在內部部署和雲端) 中偵測並調查您環境中的高級威脅、受到損害的身分識別和惡意動作 (。

## <a name="better-protection-with-integration"></a>整合的更佳防護

在 Microsoft 365 E5 中，預設會整合威脅防護功能。 每項功能的信號增加了偵測及回應威脅的整體能力。 整合的一組功能可為組織（特別是多國組織）提供最佳保護，與執行非 Microsoft 產品相較。 下圖描述本文所述的威脅防護服務和功能。

![Microsoft 365 Defender 的概覽](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365Defender 會將信號和資料一起帶入整合的[Microsoft 365 安全性中心](/microsoft-365/security/defender/overview-security-center)。 

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender 儀表板的概念圖例](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>部署概觀

下圖描述部署這些個別功能的建議路徑。 

> [!div class="mx-imgBorder"]
> ![M365 威脅防護信號](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

觀看此影片以取得部署程序的概觀。
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

下表說明要設定的各種解決方案/功能及其功能。

|步驟 |解決方案/功能  |說明  |
|--|---------|---------|
| 1 |[多重要素驗證和條件式存取](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |防護遭到損害的身分識別和裝置。 請從這種保護開始，因為它是基礎。 此指南中建議的設定包括 Azure AD 身分識別保護為先決條件。 如需詳細資訊，請參閱 [AZURE AD Identity Protection](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)。     |
| 第 |[適用於身分識別的 Microsoft Defender](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  使用內部部署 Active Directory 網域服務的雲端式安全性解決方案 (AD DS) 信號來識別、偵測和調查組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。 著重于 Microsoft Defender for Identity，因為它會保護您的內部部署和雲端基礎結構、沒有相依性或必要條件，而且可以提供立即的安全性效益。 如需詳細資訊，請參閱 [何謂 Identity Protection？](/azure/active-directory/identity-protection/overview-identity-protection)。 | 
| 個 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |將信號和分割功能結合成單一解決方案。 讓安全性專業人員結合威脅信號，並決定威脅的完整範圍和影響。 Microsoft 365Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。 如需詳細資訊，請參閱[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)。 |
| 4  |[適用於 Office 365 的 Microsoft Defender](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | 保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。 防止惡意程式碼、網路釣魚、欺騙及其他攻擊類型。 建議您為 Office 365 設定 Microsoft Defender，因為變更控制會從委任系統移轉設定，而其他考慮可能需要較長時間才能部署。 如需詳細資訊，請參閱[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)。       |
| 5  |[適用於端點的 Microsoft Defender](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | 協助避免、偵測、調查和回應跨裝置的高級威脅 (也稱為端點) 。 「Defender for Endpoint」是一種強健的威脅防護服務。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。  |
| 6  |[Microsoft 雲端 App 安全性](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | 雲端存取安全性經紀人，用於探索、調查和控管。 您可以儘早啟用 Microsoft Cloud App Security，以開始收集資料和洞察力。 在您的 SaaS 應用程式中實施資訊和其他有針對性的保護，需要規劃，而且可能需要更多時間。 如需詳細資訊，請參閱[什麼是雲端 App 安全性？](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> 具有多個安全小組的組織可以並存執行功能。 例如，一個小組可以設定 Office 365 的 defender，同時另一個小組會為端點設定 defender。 設定必須嚴格遵循建議的訂單。 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>規劃部署威脅防護解決方案

下圖說明部署威脅防護功能的高層級流程。 

![部署威脅防護功能的程式](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

若要確定您的組織有可能獲得最佳保護，請使用包含下列步驟的程式來 [設定和部署您的安全性解決方案](deploy-threat-protection-configure.md) ：

1. [設定多重要素驗證和條件式存取原則](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)。
2. [設定 Microsoft Defender 身分識別](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)。
3. [開啟 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)。
4. [設定 Office 365 的 Defender](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)。
5. [設定 Microsoft Defender For Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)。
6. [設定 Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)。
7. [監視狀態並採取動作](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)。
8. [訓練使用者](deploy-threat-protection-configure.md#step-8-train-users)。

您可以平行設定威脅防護功能，因此，如果您有多個網路安全小組負責不同的服務，則可以同時設定組織的保護功能。

## <a name="next-step"></a>後續步驟

繼續[設定不同 Microsoft 365 的威脅防護功能](deploy-threat-protection-configure.md)。


