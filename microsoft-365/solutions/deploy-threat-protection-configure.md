---
title: 在 Microsoft 365 中設定威脅防護功能的步驟
description: 瞭解如何在 Microsoft 365 E5 部署威脅防護服務與功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931983"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>在 Microsoft 365 中設定威脅防護功能

請遵循下列步驟設定 Microsoft 365 的威脅防護。


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步驟 1：設定多重要素驗證和條件式存取策略

[MFA 應用程式的](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (驗證) 使用者需使用通話或驗證器 App 來驗證身分識別。 [條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 策略會定義使用者必須符合才能在 Microsoft 365 中存取應用程式與資料的某些需求。 MFA 和條件式存取策略能共同保護貴組織。 例如，如果有人嘗試使用未啟用 MFA 的帳戶從行動裝置上登出，而條件式存取策略要求 MFA 生效，使用者就會無法進行註冊。  

Microsoft 已經測試並建議一組特定的條件式存取和相關政策，以保護所有 SaaS 應用程式的存取權，特別是 Microsoft 365。 建議您使用比較基準、敏感性且受到高度規範的保護。 首先，執行比較基準保護的策略。 


[ ![ 身分識別與裝置存取的一般組](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [策略請參閱此圖像的較大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>為 Microsoft 365 執行基準保護

![部署基準保護的流程](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [設定先決條件，包括 Azure 身分識別保護](../security/office-365-security/identity-access-prerequisites.md)。
2. [設定一般身分識別與裝置存取策略以基礎](../security/office-365-security/identity-access-policies.md) 保護。
3. 為來賓使用者 [、Microsoft](../security/office-365-security/identity-access-policies-guest-access.md) [Teams、Exchange](../security/office-365-security/teams-access-policies.md) [Online、SharePoint](../security/office-365-security/secure-email-recommended-policies.md)Online 和 [OneDrive 設定相關政策](../security/office-365-security/sharepoint-file-access-policies.md)。

### <a name="more-information-about-protecting-identities"></a>有關保護身分身分之詳細資訊

- [身分識別與裝置存取設定](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA 的安全性指南](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>步驟 2：設定 Microsoft Defender 的身分識別

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 是一種雲端式安全性解決方案，可和內部部署 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 訊號一起運作，以識別、偵測和調查進一步威脅、身分識別已盜用，以及針對貴組織所導向的惡意 Insider 動作。

Microsoft Defender for Identity 可讓安全性作業 (SecOps) 分析師和安全性專業人員，他們努力偵測混合式環境中進一步攻擊，以：
- 使用學習型分析來監控使用者、實體行為與活動。
- 保護儲存在 Active Directory 中的使用者身分識別和認證。
- 識別並調查整個狙殺鍊中的可疑使用者活動和進階攻擊。
- 以簡單的時間表提供清楚的事件資訊，以進行快速分級。

### <a name="to-set-up-microsoft-defender-for-identity"></a>設定 Microsoft Defender 進行身分識別

![部署 Microsoft Defender 身分識別的流程](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [設定 Microsoft Defender 進行身分識別](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 以保護您的主要環境。
2. 保護您的所有[網網域控制站](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring)[及樹區](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)。
3. 將 [身分識別警示的 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) 整合至您的安全 (SecOps) 工作流程。

### <a name="more-information-about-microsoft-defender-for-identity"></a>關於 Microsoft Defender 身分識別之詳細資訊

- [什麼是適用於身分識別的 Microsoft Defender？](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [影片：Microsoft Defender 身分識別簡介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [身分識別部署的 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>步驟 3：開啟 Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 將訊號和狀態功能結合成單一解決方案。 使用整合式 Microsoft 365 Defender 解決方案，安全性專業人員可以整合每項產品收到的威脅訊號，並判斷威脅的完整範圍和影響;進入環境後的影響，以及目前對組織的影響。 Microsoft 365 Defender 會採取自動動作來防止或停止受攻擊和自我攻擊的信箱、端點和使用者身分識別。

Microsoft 365 Defender 會針對工作負載 (Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security) 提供警示、事件、自動化調查與回應，以及進一步搜尋工作量。 在您為 Office 365 服務配置一或多個 Defender 之後，請開啟 Microsoft 365 Defender。 新功能會持續新增到 Microsoft 365 Defender;請考慮加入以接收預覽功能。

### <a name="to-set-up-microsoft-365-defender"></a>設定 Microsoft 365 Defender

![部署 Microsoft 365 Defender 的流程](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [請審查先決條件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。
2. [開啟 Microsoft 365 Defender。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [加入宣告預覽功能](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-365-defender"></a>Microsoft 365 Defender 詳細資訊

- [什麼是 Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 365 Defender 的新功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>步驟 4：設定 Office 365 的 Microsoft Defender

[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 可保護貴組織免受電子郵件的惡意威脅 (附件、) 、Office 檔及共同處理工具中的惡意威脅。 下表列出 Microsoft 365 E5 中包含的 Microsoft Defender For Office 365 功能：

|組配置、保護及偵測功能|自動化、調查、補救和教育功能|
|---|---|
|[安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[適用於 Office 365 的 Defender 中的反網路釣魚防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[威脅追蹤工具](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[威脅總管](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自動調查及回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻擊模擬器](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

有了 Office 365 的 Microsoft Defender，貴組織人員就可以使用其電子郵件內容和 Office 檔的威脅防護，更安全地通訊及共同合作。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>設定 Office 365 的 Microsoft Defender

![Office 365 的 Microsoft Defender 部署程式](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [設定 Microsoft Defender 以設定 Office 365 政策](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
2. [查看及使用您的 Microsoft Defender 來查看及使用 Office 365 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。
3. [使用威脅調查與回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Office 365 的 Microsoft Defender 詳細資訊

- [Office 365 的 Microsoft Defender 概觀](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft Defender for Office 365 的新增功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>步驟 5：設定端點的 Microsoft Defender

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 可保護組織裝置 (也稱為) 網路威脅、進場攻擊和資料外泄。 安全小組可以更有效率地管理端點的安全性。 強大的工具可協助組織使用威脅與弱點管理來使用弱點偵測來維持 [未系對的系統](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 自動化偵測和補救功能，例如縮減攻擊[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)面、新一[](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)代保護、端點偵測與[回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)，以及自動化調查[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)與補救，可協助保護裝置安全免受惡意攻擊。 在這些功能的上方，客戶可以取得主動通知，並視需要向 Microsoft Threat Experts 諮詢，這是選擇參加管理的搜尋服務的一部分。 


### <a name="set-up-microsoft-defender-for-endpoint"></a>設定 Microsoft Defender 端點

![部署 Microsoft Defender 端點的流程](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [準備您的 Microsoft Defender 以部署端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [設定您的 Microsoft Defender 端點部署](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [上線至 Microsoft Defender for Endpoint 服務](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [完成您首要的安全性管理工作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>有關 Microsoft Defender for Endpoint 的資訊

- [深入瞭解 Microsoft Defender for Endpoint。](https://docs.microsoft.com/windows/security/threat-protection)
- [請嘗試 Microsoft Defender for Endpoint 評估實驗室](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步驟 6：設定 Microsoft 雲端 App 安全性

[Microsoft Cloud App 安全性](https://docs.microsoft.com/cloud-app-security) 是一種雲端存取安全性用戶端，支援記錄集合、API 連接器和反向 Proxy。 Microsoft Cloud App 安全性提供豐富的可見度、控制資料旅行，以及找出並對抗所有雲端服務中的網路威脅的精密分析。 使用 Microsoft Cloud App 安全性，您的安全性作業可保護貴組織的敏感性資訊、防範網路威脅及威脅、探索及監控存取貴組織資料的應用程式，以及協助確保貴組織的雲端 App 符合合規性要求。

### <a name="set-up-microsoft-cloud-app-security"></a>設定 Microsoft Cloud App 安全性

![部署 Microsoft Cloud App 安全性的流程](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [設定入口網站及其他基本需求](https://docs.microsoft.com/cloud-app-security/general-setup)。
2. [設定雲端探索並](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery)[連接應用程式](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [為精選應用程式部署條件式存取應用程式控制項](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。
4. [使用調查工具和儀表板](https://docs.microsoft.com/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的詳細資訊

- [請審查新的功能](https://docs.microsoft.com/cloud-app-security/release-notes)。
- [深入瞭解 Microsoft Cloud App 安全性](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步驟 7：監控狀態並採取行動

在您設定及部署您的威脅防護服務與功能後，下一步就是監控威脅偵測，並採取適當的動作。 最佳起點是 Microsoft 365 資訊安全中心 () ，您可以在其中監控和管理您 Microsoft 身分、資料、裝置、應用程式及基礎結構 [https://security.microsoft.com](https://security.microsoft.com) 的安全性。 

![Microsoft 365 安全性中心](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 資訊安全中心是專為安全性管理員和安全性作業小組所設計。 在 Microsoft 365 資訊安全中心，您可以：
- 使用安全分數來查看貴組織 [的整體安全性健康情況](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。
- [監控及查看身分](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) 驗證、資料、裝置、應用程式與基礎結構的狀態報表。
- 透過事件連接警示上的 [點](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)。
- 使用 [自動化調查與補救](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) 來解決威脅。
- [主動尋找威脅](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)，例如入侵或入侵活動會影響您的電子郵件、資料、裝置和身分驗證。
- [使用威脅分析瞭解](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) 最新的攻擊行銷活動和技巧。
- ...以及更多功能！

### <a name="more-information-about-the-microsoft-365-security-center"></a>Microsoft 365 資訊安全中心詳細資訊

- [開始使用 Microsoft 365 資訊安全中心](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。
- [監控及查看報告](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)。
- [請參閱 Microsoft 365 中的安全性入口網站](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>步驟 8：訓練使用者

訓練使用者可以節省您的使用者和安全性作業小組許多時間和挫折。 聰明的使用者較不會開啟可疑電子郵件訊息中的附件或按一下連結，而且較有可能避免可疑的網站。 

教育人員學校 [網路安全性活動手冊](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 提供在貴組織中建立強大安全性認知文化之絕佳指南，包括訓練使用者識別網路釣魚攻擊。 

Microsoft 365 提供下列資源，協助告知貴組織的使用者：

|概念  |資源  |
|---------|---------|
|Microsoft 365     |[可自訂的學習路徑](https://docs.microsoft.com/office365/customlearning/) <p>這些資源可以協助您將組織的使用者訓練整合在一起        |
|Microsoft 365 安全性 |[學習模組：使用 Microsoft 365 的內建智慧型安全性保護貴組織](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>本單元可讓您說明 Microsoft 365 安全性功能如何共同作業，並說明這些安全性功能的好處。 |
|多重要素驗證     | [雙步驟驗證：額外的驗證頁面是什麼？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文可協助使用者瞭解什麼是多重要素驗證，以及為何在貴組織中使用多重要素驗證。    |

除了此指引外，Microsoft 建議您的使用者採取本文所述的動作：保護您的帳戶和裝置不受 [駭客和惡意程式碼威脅](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 這些動作包括：
- 使用強式密碼
- 保護裝置 
- 啟用 Windows 10 和 Mac PC 上的安全性功能 (未管理裝置) 
    
Microsoft 也建議使用者採取下列文章中的建議動作，以保護他們的個人電子郵件帳戶：
- [協助保護您的Outlook.com電子郵件帳戶](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [使用兩步驟驗證保護您的 Gmail 帳戶](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
