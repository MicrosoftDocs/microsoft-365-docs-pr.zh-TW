---
title: 跨 Microsoft 365 部署威脅防護功能
description: 瞭解如何在 Microsoft 365 E5 中部署威脅防護服務和功能。
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: ee3acf0729920f1ab4fdaa3fb79b2b541a7a608b
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664595"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>跨 Microsoft 365 部署威脅防護功能

[惡意](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)代碼和複雜的 cyberattacks （例如[fileless 威脅](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)）都是常見的時機。 企業必須保護自己及其客戶。 這類攻擊可能會造成組織的主要問題，包括從失去信任到財務 woes、業務威脅停機等等。 防護威脅很重要，但決定組織的時間、精力和資源的位置，可能會有很大的難度。 

Microsoft 的安全性解決方案已內置於我們的產品和服務中。 「自動化」和「機器學習」功能可減少安全性小組的負載，以確保處理適當的專案。 Microsoft 安全性解決方案的強項是以 trillions 在我們每天處理的[智慧安全性圖形](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中的信號來建立。 Microsoft 365 的安全性解決方案包括[Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)，這是一種解決方案，可透過您的電子郵件、資料、裝置和身分識別，在您的組織中繪製高級威脅的圖片。

觀賞這段影片，瞭解部署程式的概況。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

使用本文作為實施威脅防護解決方案的指南。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 中的威脅防護

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)可讓您使用可自我調整的內建智慧來保護您的組織。 使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中的高級威脅、受到損害的身分識別和惡意動作。

在 Microsoft 365 E5 中，預設會整合威脅防護功能。 每項功能的信號增加了偵測及回應威脅的整體能力。 整合的一組功能可為組織（特別是多國組織）提供最佳保護，與執行非 Microsoft 產品相較。 下圖說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。

![Microsoft 威脅防護的概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

一旦您部署任何高級威脅防護功能，您就可以開啟 Microsoft 威脅防護，使信號和資料集中在一個位置。 

![Microsoft 威脅防護儀表板的概念性插圖](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

下圖描述部署這些個別功能的建議路徑。 

![M365 威脅防護信號](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|解決方案/功能  |說明  |
|---------|---------|
|多重要素驗證和條件式存取     |防護遭到損害的身分識別和裝置。 請從這種保護開始，因為它是基礎。 此指南中建議的設定包括 Azure AD 身分識別保護為先決條件。     |
|Azure 進階威脅防護     |  以雲端為基礎的安全性解決方案，可利用您的內部部署 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。 請將重點放在下一個，因為它會保護您的部署和雲端基礎結構、沒有相依性或必要條件，而且可提供立即的益處。       | 
|Office 365 進階威脅防護     | 保護您的組織免受電子郵件訊息、連結（URLs）和共同作業工具帶來的惡意威脅。 針對惡意程式碼、網路釣魚、欺騙及其他攻擊類型的保護。 這是建議的下一步，因為變更控制、從委任系統移轉設定，以及其他考慮可能需要較長時間才能部署。 <br><br>附注：請確定您也設定所有 Office 365 訂閱中包含的威脅防護功能（Exchange Online Protection）。       |
|Microsoft Defender 進階威脅防護    | Endpoint protection 平臺，可協助避免、偵測、調查和回應高級威脅。 這要花更長的時間進行部署，但如果其他系統管理員負責，則可以與其他功能同時進行。   |
|Microsoft Cloud App Security     |   雲端存取安全性經紀人，用於探索、調查和控管。 您可以在早期啟用此功能，以開始收集資料和洞察力。 在您的 SaaS 應用程式中實施資訊和其他有針對性的保護，需要規劃，而且可能需要更多時間。       | 

> [!TIP]
> 具有多個安全小組的組織可以並存執行這些功能。

## <a name="deploy-your-threat-protection-solution"></a>部署威脅防護解決方案

若要確定您的組織有可能獲得最佳保護，請安裝並部署您的安全性解決方案，以包含下列步驟：

1. [設定多重要素驗證和條件式存取原則](#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [設定 Azure 高級威脅防護](#step-2-configure-azure-advanced-threat-protection)
3. [開啟 Microsoft 威脅防護](#step-3-turn-on-microsoft-threat-protection)
4. [設定 Office 365 的高級威脅防護](#step-4-configure-office-365-advanced-threat-protection)
5. [設定 Microsoft Defender 高級威脅防護](#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [設定 Microsoft Cloud App Security](#step-6-configure-microsoft-cloud-app-security)
7. [監視狀態並採取動作](#step-7-monitor-status-and-take-actions)
8. [訓練使用者](#step-8-train-users)

您可以平行設定威脅防護功能，因此，如果您有多個安全小組負責不同的服務，他們就可以同時設定組織的保護功能。 下圖說明部署威脅防護功能的高層級流程。 

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步驟1：設定多重要素驗證和條件式存取原則

[多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)（MFA）要求使用者使用撥打電話或驗證器應用程式來驗證其身分識別。 [條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)定義必須滿足的特定需求，使用者才能存取 Microsoft 365 中的應用程式和資料。 MFA 和條件式存取原則共同運作，以保護您的組織。 例如，如果有人嘗試使用未啟用 MFA 的帳戶登入行動裝置，且條件式存取原則要求 MFA 生效，該使用者將無法登入。  

Microsoft 已測試並建議一組特定的條件式存取和相關原則，以保護所有 SaaS 應用程式的存取，尤其是 Microsoft 365。 建議使用原則進行基準、機密和高管制的保護。 從執行基準保護的原則開始。 


設定身分[ ![ 識別與裝置存取的常見原則，](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png) 
 [請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>若要執行 Microsoft 365 的基準保護

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [設定必要條件，包含 Azure Identity Protection](../enterprise/identity-access-prerequisites.md)。
2. [設定一般身分識別和裝置存取原則](../enterprise/identity-access-policies.md)，以進行基準保護。
3. 設定[來賓使用者](../enterprise/identity-access-policies-guest-access.md)、 [Microsoft 團隊](../enterprise/teams-access-policies.md)、 [Exchange online](../enterprise/secure-email-recommended-policies.md)和[SharePoint 線上及 OneDrive](../enterprise/sharepoint-file-access-policies.md)的原則。

### <a name="more-information-about-protecting-identities"></a>保護身分識別的詳細資訊

- [身分識別與裝置存取設定](../enterprise/microsoft-365-policies-configurations.md)
- [Azure MFA 的安全性指導方針](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>步驟2：設定 Azure 高級威脅防護

[Azure 高級威脅防護](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)（azure ATP）是雲端式的安全性解決方案，可與您的內部部署[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)信號搭配使用，以識別、偵測和調查您組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。

Azure ATP 可讓安全性作業（SecOps）分析員和安全性專業人員在混合環境中偵測到高級攻擊，以進行下列作業：
- 使用以教學為基礎的分析來監控使用者、實體行為和活動。
- 保護儲存在 Active Directory 中的使用者身分識別和認證。
- 識別並調查整個狙殺鍊中的可疑使用者活動和進階攻擊。
- 以簡單的時間表提供清楚的事件資訊，以進行快速分級。

### <a name="to-set-up-azure-atp"></a>設定 Azure ATP

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [設定 AZURE ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1)以保護您的主要環境。
2. 保護所有的[網域控制站](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring)和[樹](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)系。
3. 將[AZURE ATP 警示](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external)整合至您的安全性作業（SecOps）工作流程。

### <a name="more-information-about-azure-atp"></a>Azure ATP 的詳細資訊

- [什麼是 Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [影片： Azure ATP 簡介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Azure ATP 部署](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>步驟3：開啟 Microsoft 威脅防護

[Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)功能會將信號和協調功能結合成單一解決方案。 透過整合的 Microsoft 威脅防護解決方案，安全性專業人員可以結合上述威脅，讓每一種產品收到並決定威脅的完整範圍和影響;如何進入環境、受到影響的內容，以及目前對組織的影響。 Microsoft 威脅防護會自動採取動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。

Microsoft 威脅防護功能將提醒、事件、自動化調查和回應，以及跨工作負載的高級搜尋（Azure ATP，Office 365 ATP，Microsoft Defender ATP，以及 Microsoft Cloud App Security）統一成單一玻璃體驗。 在您設定一或多個高級威脅防護服務後，開啟 Microsoft 威脅防護。 新功能會連續新增至 Microsoft 威脅防護;請考慮改為接收預覽功能。

### <a name="to-set-up-microsoft-threat-protection"></a>設定 Microsoft 威脅防護

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [複查必要條件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。
2. [開啟 Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。
3. [加入宣告預覽功能](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-threat-protection"></a>Microsoft 威脅防護的詳細資訊

- [什麼是 Microsoft 威脅防護？](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 威脅防護的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>步驟4：設定 Office 365 的高級威脅防護

[Office 365 Advanced 威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（OFFICE 365 ATP）會保護您的組織免受電子郵件訊息（附件和 URLs）、Office 檔及共同作業工具中的惡意威脅。 下表列出 Microsoft 365 E5 中包含的 Office 365 ATP 功能和功能：

|||
|---|---|
|設定、保護及偵測功能|自動化、調查、修正及教育功能|
|[安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全檔](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[ATP 反網路釣魚保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[威脅追蹤工具](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[威脅總管](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自動調查及回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻擊模擬器](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

透過 Office 365 ATP，您組織中的人員可以更安全地溝通和展開電子郵件內容和 Office 檔的威脅防護。

### <a name="to-set-up-office-365-atp"></a>設定 Office 365 ATP

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [安裝和設定您的 Office 365 ATP 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
2. [查看和使用您的 Office 365 ATP 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。
3. [使用威脅調查和回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

### <a name="more-information-about-office-365-atp"></a>有關 Office 365 ATP 的詳細資訊

- [Office 365 ATP 概觀](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Office 365 ATP 中的新功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>步驟5：設定 Microsoft Defender 高級威脅防護

[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection)（MICROSOFT defender ATP）會從 cyberthreats、高級攻擊和資料違規中保護您的組織裝置（也稱為端點）。 安全小組在管理其端點的安全性時，效率會更高。 穩健的工具可協助組織使用具有[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的漏洞偵測，以不斷處理未經修補的系統。 自動偵測和修正功能，例如[攻擊面降低](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、[下一代保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、[端點偵測和回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)，以及[自動調查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)，可協助您保護裝置安全地抵禦惡意程式碼。 在這些功能上，客戶可以取得主動通知，並在需要時與 Microsoft 威脅專家（自願加入受管理的搜尋服務的一部分）接洽。 


### <a name="set-up-microsoft-defender-atp"></a>設定 Microsoft Defender ATP

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [準備您的 Microsoft DEFENDER ATP 部署](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [設定您的 Microsoft Defender ATP 部署](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [在 Microsoft DEFENDER ATP 服務上架](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [完成最常見的安全性系統管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)工作。

### <a name="more-information-about-microsoft-defender-atp"></a>Microsoft Defender ATP 的詳細資訊

- [深入瞭解 Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection)。
- [嘗試 Microsoft DEFENDER ATP 評估實驗室](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步驟6：設定 Microsoft Cloud App Security

[Microsoft Cloud App security](https://docs.microsoft.com/cloud-app-security)是雲端存取安全性經紀人，可支援記錄檔收集、API 連接器及反向 proxy。 Microsoft Cloud App Security 提供豐富的知名度、控制資料旅行和完善的分析，以在所有雲端服務之間識別及打擊 cyberthreats。 使用 Microsoft Cloud App Security，您的安全性作業可以保護組織的機密資訊、防範 cyberthreats 和異常、探索及監視存取組織資料的應用程式，以及協助確保組織的雲端應用程式符合規範需求。

### <a name="set-up-microsoft-cloud-app-security"></a>設定 Microsoft Cloud App Security

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [設定入口網站和其他基本需求](https://docs.microsoft.com/cloud-app-security/general-setup)。
2. [設定 cloud discovery](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery)和[connect 應用程式](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [為特色式應用程式部署條件式存取應用程式控制](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。
4. [使用調查工具及儀表板](https://docs.microsoft.com/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的詳細資訊

- [查看新的功能與功能](https://docs.microsoft.com/cloud-app-security/release-notes)。
- [深入瞭解 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步驟7：監控狀態並採取動作

設定並部署威脅防護服務和功能之後，下一步是監視威脅偵測，並採取適當的動作。 您最好的起點是 Microsoft 365 的安全性中心（ [https://security.microsoft.com](https://security.microsoft.com) ），您可以在其中監視和管理您的 microsoft 身分識別、資料、裝置、應用程式和基礎結構的安全性。 

:::image type="content" source="../media/solutions-architecture-center/m365-security-center.png" alt-text="Microsoft 365 安全性中心":::

Microsoft 365 的安全性中心專為安全性管理員及安全性作業小組特別設計。 在 Microsoft 365 的安全性中心，您可以：
- 以[安全得分](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)查看組織的整體安全性健康情況。
- [監視和查看](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)您的身分識別、資料、裝置、應用程式和基礎結構狀態的報告。
- 透過[事件](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)連接警示上的點。
- 使用[自動調查和修正](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)來處理威脅。
- [主動搜尋威脅](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)，例如入侵企圖或破壞您電子郵件、資料、裝置和身分識別的活動。
- 透過威脅分析[瞭解最新的攻擊活動](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns)和技術。
- ...還有更多！

### <a name="more-information-about-the-microsoft-365-security-center"></a>Microsoft 365 安全中心的詳細資訊

- [開始使用 Microsoft 365 的安全性中心](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。
- [監視和查看報告](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)。
- [請參閱 Microsoft 365 中的安全性入口網站](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>步驟8：訓練使用者

訓練使用者可將您的使用者與安全性作業小組儲存在許多時間和不滿。 聰明的使用者不太可能開啟附件或按一下可疑電子郵件訊息中的連結，也很可能避免可疑的網站。 

Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)提供好的指導方針，可為組織內的安全性感知建立強大的文化，包括訓練使用者來識別網路釣魚攻擊。 

Microsoft 365 提供下列資源，協助您在組織中告知使用者：

|概念  |資源  |
|---------|---------|
|Microsoft 365     |[可自訂的教學路徑](https://docs.microsoft.com/office365/customlearning/) <p>這些資源可協助您將組織中使用者的訓練放在一起        |
|Microsoft 365 安全性 |[學習模組：使用 Microsoft 365 內建的智慧安全性保護您的組織](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>此模組可讓您描述 Microsoft 365 安全性功能如何協同運作，並闡明這些安全性功能的優點。 |
|多重要素驗證     | [雙步驟驗證：其他驗證頁面為何？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文可協助使用者瞭解哪些多重要素驗證，以及如何在您的組織中使用它。    |

除了這項指導之外，Microsoft 也建議您的使用者採取本文所述的動作：[保護您的帳戶和裝置免受駭客和惡意](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)代碼的攻擊。 這些動作包括：
- 使用強式密碼
- 保護裝置 
- 啟用 Windows 10 和 Mac 電腦上的安全性功能（適用于非管理裝置）
    
Microsoft 也建議您採取下列文章中建議的動作來保護其個人電子郵件帳戶：
- [協助保護您的 Outlook.com 電子郵件帳戶](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [使用2步驟驗證保護您的 Gmail 帳戶](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
