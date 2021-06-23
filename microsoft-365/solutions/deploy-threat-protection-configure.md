---
title: 設定各個 Microsoft 365 威脅防護功能的步驟
description: 使用本文作為實施威脅防護解決方案的指南。 跨 Microsoft 365 E5 部署威脅防護服務和功能。
keywords: 安全性解決方案、設定、設定、Microsoft 365 E5、高級威脅防護、defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 48a51b8ec880726bdd2121f2eaf0d78f5cd6b3e0
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083461"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>跨 Microsoft 365 設定威脅防護功能

請遵循下列步驟，在 Microsoft 365 設定威脅防護。

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步驟1：設定多重要素驗證和條件式存取原則

[多重要素驗證](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) 要求使用者使用電話或驗證器應用程式來驗證其身分識別。 [條件式存取原則](/azure/active-directory/conditional-access/overview)定義必須滿足的特定需求，使用者才能存取 Microsoft 365 中的應用程式和資料。 MFA 和條件式存取原則共同運作，以保護您的組織。 例如，如果有人嘗試使用未啟用 MFA 的帳戶登入行動裝置，且條件式存取原則要求 MFA 生效，該使用者便無法登入。  

Microsoft 已測試並建議一組特定的條件式存取和相關原則，以保護所有 SaaS 應用程式的存取，尤其是 Microsoft 365。 建議使用原則進行基準、機密和高管制的保護。 從執行基準保護的原則開始。

設定身分[ ![ 識別與裝置存取的常見原則，](../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png) 
 [請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>若要執行 Microsoft 365 的基準保護

![部署基準保護的程式](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [設定必要條件，包含 AZURE AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md)。
2. [設定一般身分識別和裝置存取原則](../security/office-365-security/identity-access-policies.md) ，以進行基準保護。
3. 為[來賓使用者](../security/office-365-security/identity-access-policies-guest-access.md)設定原則、 [Microsoft Teams](../security/office-365-security/teams-access-policies.md)、 [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)及[SharePoint 線上及 OneDrive](../security/office-365-security/sharepoint-file-access-policies.md)。

### <a name="more-information-about-protecting-identities"></a>保護身分識別的詳細資訊

- [身分識別與裝置存取設定](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA 的安全性指導方針](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>步驟2：設定 Microsoft Defender 身分識別

[Microsoft Defender For Identity](/defender-for-identity/what-is) 是雲端式的安全性解決方案，可搭配您的內部部署 Active Directory 網域服務與您的內部部署 Active Directory 網域服務 (AD DS) 信號來識別、偵測和調查組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。

Microsoft Defender for Identity 可讓安全性作業 (SecOps) 分析員和安全性專業人員，以偵測混合式環境中的高級攻擊：

- 使用以教學為基礎的分析來監控使用者、實體行為和活動。
- 保護儲存在 Active Directory 中的使用者身分識別和認證。
- 識別並調查整個狙殺鍊中的可疑使用者活動和進階攻擊。
- 以簡單的時間表提供清楚的事件資訊，以進行快速分級。

### <a name="to-set-up-microsoft-defender-for-identity"></a>設定 Microsoft Defender 身分識別

![部署 Microsoft Defender 身分識別的程式](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. 為身分[識別設定 Microsoft Defender](/azure-advanced-threat-protection/install-atp-step1)以保護主要環境。
2. 保護所有的 [網域控制站](/azure-advanced-threat-protection/atp-sensor-monitoring) 和 [樹](/azure-advanced-threat-protection/atp-multi-forest)系。
3. 將 [Microsoft Defender 的身分識別警示](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) 整合到您的安全性作業中 (SecOps) 工作流程。

### <a name="more-information-about-microsoft-defender-for-identity"></a>Microsoft Defender 身分識別的詳細資訊

- [什麼是適用於身分識別的 Microsoft Defender？](/azure-advanced-threat-protection/what-is-atp)
- [影片： Microsoft Defender 身分識別簡介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [用於身分識別部署的 Microsoft Defender](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>步驟3：開啟 Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)會將信號和分割功能結合成單一解決方案。 透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合上述每一種產品接收及決定威脅的完整範圍及影響，以進行威脅。如何進入環境、受到影響的內容，以及目前對組織的影響。 Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。

Microsoft 365 Defender 統一的提醒、事件、自動化調查和回應，以及跨工作負載的高級搜尋 (microsoft defender for Identity、microsoft defender for Office 365、microsoft defender for Endpoint 及 Microsoft Cloud App Security) ，變成單一的玻璃體驗。 新功能會連續新增至 Microsoft 365 Defender;請考慮改為接收預覽功能。

### <a name="to-set-up-microsoft-365-defender"></a>若要設定 Microsoft 365 Defender

![部署 Microsoft 365 Defender 的程式](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [複查必要條件](../security/defender/prerequisites.md)。
2. [開啟 Microsoft 365 Defender](../security/defender/m365d-enable.md)。
3. [加入宣告預覽功能](../security/defender/preview.md)。

### <a name="more-information-about-microsoft-365-defender"></a>Microsoft 365 Defender 的詳細資訊

- [什麼是 Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Microsoft 365 Defender 的新功能](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>步驟4：為 Office 365 設定 Microsoft Defender

[Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md)會保護您的組織免受電子郵件中的惡意威脅 (附件和 URLs) 、Office 檔和協同作業工具。 下錶針對 Microsoft 365 E5 中包含的 Office 365 功能及功能，列出 Microsoft Defender：

<br>

****

|設定、保護及偵測功能|自動化、調查、修正及教育功能|
|---|---|
|[安全附件](../security/office-365-security/safe-attachments.md) <p> [安全連結](../security/office-365-security/safe-links.md) <p> [安全文件](../security/office-365-security/safe-docs.md) <p> [適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](../security/office-365-security/mdo-for-spo-odb-and-teams.md) <p> [Microsoft 365 中的反網路釣魚保護](../security/office-365-security/anti-phishing-protection.md)|[威脅追蹤工具](../security/office-365-security/threat-trackers.md) <p> [威脅總管](../security/office-365-security/threat-explorer.md) <p> [自動調查及回應](../security/office-365-security/office-365-air.md) <p> [攻擊模擬訓練](../security/office-365-security/attack-simulation-training.md)|
|

透過 Microsoft Defender 的 Office 365，您組織中的人員可以更安全地進行通訊及共同作業，其電子郵件內容和 Office 檔具有威脅防護。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>為 Office 365 設定 Microsoft Defender

![為 Office 365 部署 Microsoft Defender 的程式](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [為 Office 365 原則安裝和設定您的 Microsoft Defender](../security/office-365-security/protect-against-threats.md)。
2. [針對 Office 365 報告，查看並使用您的 Microsoft Defender](../security/office-365-security/view-reports-for-mdo.md)。
3. [使用威脅調查和回應功能](../security/office-365-security/office-365-ti.md)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>有關 Microsoft Defender Office 365 的詳細資訊

- [Microsoft Defender Office 365 概述](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Defender Office 365 的新功能](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>步驟5：設定 Microsoft Defender for Endpoint

[Microsoft Defender For Endpoint](/windows/security/threat-protection) 會保護您的組織裝置 (也稱為端點) 從 cyberthreats、高級攻擊和資料違例。 安全小組在管理其端點的安全性時，效率會更高。 穩健的工具可協助組織使用具有 [威脅和弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的漏洞偵測，以不斷處理未經修補的系統。 自動偵測和修正功能，例如 [攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、 [下一代保護](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、 [端點偵測和回應](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)，以及 [自動調查和修正](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) ，可協助您保護裝置安全地抵禦惡意程式碼。 在這些功能上，客戶可以取得主動通知，並在需要時與 Microsoft 威脅專家，作為自願加入的管理搜尋服務的一部分進行諮詢。

### <a name="set-up-microsoft-defender-for-endpoint"></a>設定 Microsoft Defender for Endpoint

![為端點部署 Microsoft Defender 的程式](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. 為[Microsoft Defender For Endpoint 準備您的環境](../security/defender-endpoint/deployment-phases.md)。
2. [部署 Microsoft Defender For Endpoint](../security/defender-endpoint/production-deployment.md)。
3. [在 Microsoft Defender For Endpoint service 上架](../security/defender-endpoint/onboarding.md)上。
4. [完成最常見的安全性系統管理](../security/defender-endpoint/tvm-security-recommendation.md)工作。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的詳細資訊

- [深入瞭解 Microsoft Defender For Endpoint](../security/defender-endpoint/microsoft-defender-endpoint.md)。
- [嘗試 Microsoft Defender For Endpoint 評估實驗室](../security/defender-endpoint/evaluation-lab.md)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步驟6：設定 Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security)是支援記錄檔收集、API 連接器及反向 proxy 的雲端存取安全性經紀人。 Microsoft Cloud App Security 提供豐富的知名度、控制資料旅行和複雜的分析，以在所有雲端服務之間識別及打擊 cyberthreats。 透過 Microsoft Cloud App Security，您的安全性作業可以保護組織的機密資訊、防範 cyberthreats 和異常、探索及監視存取組織資料的應用程式，以及協助確保組織的雲端應用程式符合規範的需求。

### <a name="set-up-microsoft-cloud-app-security"></a>設定 Microsoft Cloud App Security

![部署 Microsoft Cloud App Security 的程式](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [設定入口網站和其他基本需求](/cloud-app-security/general-setup)。
2. [設定 cloud discovery](/cloud-app-security/set-up-cloud-discovery) 和 [connect 應用程式](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [為特色式應用程式部署條件式存取應用程式控制](/cloud-app-security/proxy-deployment-aad)。
4. [使用調查工具及儀表板](/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的詳細資訊

- [查看新的功能與功能](/cloud-app-security/release-notes)。
- [深入瞭解 Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步驟7：監控狀態並採取動作

設定並部署威脅防護服務和功能之後，下一步是監視威脅偵測，並採取適當的動作。 您最好的起點是 Microsoft 365 的安全性中心 ([https://security.microsoft.com](https://security.microsoft.com)) ，您可以在其中監視和管理您的所有 Microsoft 身分識別、資料、裝置、應用程式和基礎結構的安全性。

![Microsoft 365 安全性中心](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 的安全性中心是供安全性管理員和安全性作業小組所用。 在 Microsoft 365 的安全性中心，您可以：

- 以 [安全得分](/microsoft-365/security/defender/microsoft-secure-score)查看組織的整體安全性健康情況。
- [監視和查看](../security/defender-endpoint/threat-protection-reports.md) 您的身分識別、資料、裝置、應用程式和基礎結構狀態的報告。
- 透過[事件](/microsoft-365/security/defender/incident-queue)連線警示上的點。
- 使用 [自動調查和修正](../security/defender/m365d-autoir.md) 來處理威脅。
- [主動搜尋威脅](/microsoft-365/security/defender/advanced-hunting-overview)，例如入侵企圖或破壞您電子郵件、資料、裝置和身分識別的活動。
- 透過威脅分析[瞭解最新的攻擊活動](/microsoft-365/security/defender/latest-attack-campaigns)和技術。
- ...還有更多！

### <a name="more-information-about-the-microsoft-365-security-center"></a>Microsoft 365 安全性中心的詳細資訊

- [開始使用 Microsoft 365 的安全性中心](../security/defender/overview-security-center.md)。
- [監視和查看報告](../security/defender/overview-security-center.md)。
- [請參閱 Microsoft 365 中的安全性入口網站](../security/defender/portals.md)。

## <a name="step-8-train-users"></a>步驟8：訓練使用者

訓練使用者可將您的使用者與安全性作業小組儲存在許多時間和不滿。 聰明的使用者不太可能開啟附件或按一下可疑電子郵件訊息中的連結，也很可能避免可疑的網站。 

Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 提供好的指導方針，可為組織內的安全性感知建立強大的文化，包括訓練使用者來識別網路釣魚攻擊。 

Microsoft 365 提供下列資源，協助您在組織中告知使用者：

<br>

****

|概念|資源|
|---|---|
|Microsoft 365|[可自訂的教學路徑](/office365/customlearning/) <p> 這些資源可協助您將組織中使用者的訓練放在一起|
|Microsoft 365 安全性|[Learning 模組：使用內建的智慧安全性保護組織安全 Microsoft 365](/learn/modules/security-with-microsoft-365) <p> 此模組可讓您描述 Microsoft 365 安全性功能如何協同運作，並闡明這些安全性功能的優點。|
|多重要素驗證|[雙步驟驗證：其他驗證頁面為何？](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p> 本文可協助使用者瞭解哪些多重要素驗證，以及如何在您的組織中使用它。|
|

除了這項指導之外，Microsoft 也建議您的使用者採取本文所述的動作： [保護您的帳戶和裝置免受駭客和惡意](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)代碼的攻擊。 這些動作包括：

- 使用強式密碼
- 保護裝置
- 啟用非管理裝置的 Windows 10 和 Mac 電腦 (上的安全性功能) 

Microsoft 也建議您採取下列文章中建議的動作來保護其個人電子郵件帳戶：

- [協助保護您的 Outlook .com 電子郵件帳戶](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [使用2步驟驗證保護您的 Gmail 帳戶](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
