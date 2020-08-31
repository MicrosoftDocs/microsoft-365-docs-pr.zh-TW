---
title: Microsoft 365 NIST 800-53 行動計畫 — 前 30 天、90 天及過後的首要工作
description: 當您工作以符合美國國家標準與技術研究院 (National Institute of Standards and Technology，NIST) 需求時可以遵循的優先行動計畫
keywords: Microsoft 365、Microsoft 365 教育版, Microsoft 365 文件, NIST, NIST 800-53
author: BrendaCarter
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 09/14/2018
f1.keywords:
- NOCSH
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 355d83c4ad1e51e03f137a1342d00f3693c242e7
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308014"
---
# <a name="microsoft-365-nist-800-53-action-plan--top-priorities-for-your-first-30-days-90-days-and-beyond"></a>Microsoft 365 NIST 800-53 行動計畫 — 前 30 天、90 天及過後的首要工作

Microsoft 365 可讓您利用雲端架構經營您的企業，該架構可對齊控制項與多個法規標準。 Microsoft 365 包含 Office 365、Windows 10、Enterprise Mobility + Security。 Microsoft 的內部控制系統是以美國國家標準與技術研究院 (NIST) 特別出版品 800-53 為基礎，而 Office 365 已被視為符合最新的 NIST 800-53 標準。

Microsoft 被視為雲端安全性中的業界領導者。使用多年建置企業軟體及執行線上服務的經驗，我們的小組會持續學習並持續更新我們的服務和應用程式來提供符合業界嚴格相容性標準的安全雲端生產力服務。Microsoft 的政府雲端服務 (包括 Office 365 美國政府版) 符合美國聯邦風險與授權管理計劃 (FedRAMP) 的嚴苛需求，讓美國聯邦政府機構能受益於 Microsoft Cloud 的節省成本及嚴格的安全性。

本文包含當您工作以符合 NIST 800-53 需求時可以遵循的優先行動計畫。這個行動計畫是與 Protiviti (這是一家致力於法規合規性的 Microsoft 合作夥伴) 共同開發。 

## <a name="action-plan-outcomes"></a>行動計畫結果

這些建議橫跨有邏輯順序的三個階段，具有下列結果： 

|||
|:-----|:-----|
|**階段**|**結果**|
|30 天|*   了解您的 NIST 800-53 需求，並且考慮與 Microsoft 諮詢合作夥伴配合。<br>*   學習並了解 Microsoft 365 內建的深度防禦策略。  <br>*   保護使用者和系統管理員的 Office 365 存取權限。 <br>*   確定所有系統的存取權都可根據貴組織的稽核與責任原則進行稽核。|
|90 天|*   加強反惡意程式碼、修補和設定管理計劃。<br>*   使用 Microsoft 365 安全性功能來控制對環境的存取，以及保護組織資訊和資產。<br>*   使用內建的稽核功能來監視 Office 365 內的機密或風險活動。<br>*   針對電子郵件和 Office 文件中的連結和附件部署進階威脅防護。|
|超過 90 天|*   使用 Microsoft 365 進階工具和資訊保護來實作裝置的進行中控制措施及公司資料保護。<br>*   在 Microsoft 365 及其他 Cloud 應用程式之間監視持續合規性。  <br>*   使用改良的威脅偵測和防護功能搭配進階的威脅分析為組織提供強大的層級式安全性策略。開發事件回應計劃以減少貴組織中遭入侵系統的影響。|

## <a name="30-days--powerful-quick-wins"></a>30 天 — 強力快速致勝

這些工作可以快速地完成，並且對使用者的影響小。

|||
|:-----|:-----|
|**適用範圍**|**工作**|
|了解您的 NIST 800-53 需求，並且考慮與 Microsoft 諮詢合作夥伴配合。|•    與您的 Microsoft 合作夥伴合作，為組織執行 NIST 800-53 合規性的差距分析，並且發展規劃您的合規性旅程的藍圖。 <br>• 使用 [Microsoft 合規性分數](compliance-score.md)和中的指導方針來定義及記錄存取控制和資訊共用的原則和程序，其說明用途、範圍、角色、責任、組織實體間的協調以及合規性。|
|學習並了解 Microsoft 365 內建的深度防禦策略。|•   使用 [Microsoft 合規性分數](compliance-score.md)進行貴組織的 NIST 800-53 評定，以評定及管理合規性風險。遵循 Microsoft 365 安全性控制來管理及降低評定結果的風險。<br>•   使用 [Microsoft 安全分數](/security/office-365-security/office-365-secure-score.md) 來追蹤組織一段時間內在 Office 365 與 Windows 10 電腦上的 Microsoft 365 安全性功能使用量。 <br>•  深入了解 Microsoft 用來提供 [Office 365 資料加密](encryption.md) 的技術與策略，以及 Microsoft Cloud 中[預防拒絕服務攻擊](https://docs.microsoft.com/office365/enterprise/office-365-defending-against-denial-of-service-attacks-overview) 的策略。|
|保護使用者和系統管理員的 Office 365 存取權限。|• 建立[強化認證](https://docs.microsoft.com/azure/security/azure-ad-secure-steps#step-1---strengthen-your-credentials)來保護使用者帳戶認證。 <br> •  深入了解 Office 365 服務的[建議身分識別與裝置存取原則](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations) 。<br> • 使用 [Office 365 系統管理角色](https://support.office.com/article/understanding-administrative-roles-52f29955-6a60-435f-aba9-eb69c898606a) (英文) 來實作角色型存取系統管理功能並啟用分開的管理責任。附註：Office 365 中許多系統管理員角色在 Exchange Online、SharePoint Online 和商務用 Skype Online 中有相對應的角色。區隔權限以確保單一系統管理員沒有高於所需的存取權。|
|確定所有系統的存取權都可根據貴組織的稽核與責任原則進行稽核。|啟用[稽核記錄](search-the-audit-log-in-security-and-compliance.md)和[信箱稽核](enable-mailbox-auditing.md) (針對所有 Exchange 信箱)，以監視 Office 365 是否有潛在的惡意活動，並啟用資料外洩的鑑識調查分析。|
|||

## <a name="90-days--enhanced-protections"></a>90 天 — 加強的保護 
這些工作會需要較多時間規劃及實作。 

|||
|:-----|:-----|
|**適用範圍**|**工作**|
|加強反惡意程式碼、修補和設定管理計劃。|•   保護公司資產和電腦，方法是部署和啟用 [Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/deploy-windows-defender-antivirus) 至組織及使用其與 Windows 10 的緊密整合。<br>•   追蹤隔離受感染的系統並避免進一步的損毀，直到採取補救步驟為止。<br>•   充滿自信地仰賴 Microsoft 365 嚴格的標準變更管理程序以取得受信任的更新、Hotfix 和修補程式。|
|使用 Microsoft 365 安全性功能來控制對環境的存取，以及保護組織資訊和資產。|•   實作[建議的身分識別與裝置的存取原則](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations) 來保護使用者和系統管理員帳戶。 <br>• 實作 [Office 365 郵件加密 (OME)](ome.md) 功能，協助使用者在透過電子郵件傳送機密資料時，符合貴組織的原則。<br>• 將 [Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) (ATP) 部署至所有桌上型電腦以防範惡意程式碼，以及資料外洩防護和回應。<br>•  設定、測試和部署原則，以識別，監視和[自動保護](apply-protection-to-personal-data-in-office-365.md)文件和電子郵件中，80 多種常見的敏感資料類型，包括財務、醫療和個人身分資訊。<br>•   藉由設定[原則提示](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)，自動向電子郵件寄件者通知，他們即將違反您的其中一個原則 — 即使在他們傳送違規郵件之前。原則提示可以設定為顯示簡短通知 (在 Outlook、Outlook 網頁版及適用於裝置的 OWA 上)，在建立郵件期間提供可能的原則違規資訊。<br>• 保護企業的機密資料並符合貴組織的資訊共用原則，方法是實作[在 SharePoint Online 和商務用 OneDrive 中外部共用](https://docs.microsoft.com/onedrive/manage-sharing) 的控制措施。確定只有已驗證的外部使用者可以存取公司資料。|
|使用內建的稽核功能來監視 Office 365 內的機密或風險活動。|•   啟用 Microsoft 365 安全性或合規性中心內的[警示原則](alert-policies.md)，以在發生機密的活動 (例如當使用者的帳戶權限提高或當存取機密資料時) 時發出自動通知。 所有特殊權限功能都必須經過稽核及監視。<br>•  在安全性或合規性中心定期[搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)，以檢閱對租用戶組態設定所做的變更。<br>• 針對長期儲存稽核記錄資料，使用 Office 365 管理活動 API 參考以與安全性資訊和事件管理 (SIEM) 工具整合。|
|針對電子郵件和 Office 文件中的連結和附件部署進階威脅防護。|實作 [Office 365 進階威脅防護 (ATP)](/security/office-365-security/office-365-atp)，協助防範最常見的攻擊，包括網路釣魚電子郵件和包含惡意連結和附件的 Office 文件。|
|||

## <a name="beyond-90-days--ongoing-security-data-governance-and-reporting"></a>超過 90 天 – 持續的安全性、資料控管及報告

這些動作需要較長時間才能完成，並以上一個工作為基礎。  

|||
|:-----|:-----|
|**適用範圍**|**工作**|
|使用 Microsoft 365 進階工具和資訊保護來實作裝置的進行中控制措施及公司資料保護。|*   使用 [Microsoft Intune](https://docs.microsoft.com/intune/) 保護在行動裝置上儲存及存取的機密資料，並且確保對存取雲端服務使用符合公司規範的裝置。|
|在 Microsoft 365 及其他 Cloud 應用程式之間監視持續合規性。|*   若要根據組織定義的原則和程序評估效能，請使用[合規性分數](compliance-score.md)持續執行組織資訊安全性原則及定期評定。<br>*   使用 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)，以高階權限 (例如，特殊權限或系統管理員使用者) 控制及執行所有使用者和群組的定期檢閱。<br>*   部署和設定[特殊權限的存取管理](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-overview)，對 Office 365 中特殊權限的系統管理工作提供細微的存取控制。  一旦啟用，使用者必須要求即時存取，透過範圍與時間高度受到限制的核准工作流程，完成提升權限和授與特殊權限的工作。<br>*   稽核[非擁有者信箱存取](https://docs.microsoft.com/Exchange/policy-and-compliance/non-owner-mailbox-access-reports) 以識別潛在的資訊外洩，以及主動檢閱所有 Exchange Online 信箱上的非擁有者存取。<br>*   使用 [Office 365 警示原則、資料外洩防護報告和 Microsoft Cloud App Security](https://docs.microsoft.com/Office365/SecurityCompliance/monitor-for-leaks-of-personal-data)，來監視貴組織的雲端應用程式使用方式，並且根據啟發學習法和使用者活動實作進階警示原則。<br>*   使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 自動追蹤有風險的活動，以識別潛在惡意系統管理員、調查資料外洩，或確認是否符合要求的合規性。|
|利用改良的威脅偵測和防護功能搭配進階的威脅分析為組織提供強大的層級式安全性策略。開發事件回應計劃以減少貴組織中遭入侵系統的影響。|*   部署及設定 [Windows 進階威脅分析](https://docs.microsoft.com/advanced-threat-analytics/)以運用豐富的分析和報告，來深入解析貴組織中的哪些使用者是攻擊目標，以及所利用的網路攻擊方法。<br>*   利用 [Office 365 進階威脅防護報告和分析](/security/office-365-security/view-reports-for-atp.md) 透過在貴組織內自動偵測到的惡意內容及惡意電子郵件的深入見解來分析威脅。利用內建報告與訊息追蹤功能來調查因未知病毒或惡意程式碼而遭到封鎖的電子郵件訊息。<br>*   使用 [Office 365 威脅情報](/security/office-365-security/office-365-ti.md)來彙總各種來源的見解和資訊，以取得您雲端安全性情況的完整檢視。<br>*    [整合 Office 365 威脅情報和 Windows Defender 進階威脅防護](/security/office-365-security/integrate-office-365-ti-with-wdatp.md)以在調查 Office 365 中的威脅時，快速了解使用者的裝置是否處於風險。<br>*   使用 [Office 365 攻擊模擬器](/security/office-365-security/attack-simulator.md)來模擬在 Office 365 環境內常見的攻擊方法。  檢閱攻擊模擬中的結果以找出使用者的訓練機會，並驗證組織的事件回應程序。<br>*   設定[安全性或合規性中心內的權限](/security/office-365-security/permissions-in-the-security-and-compliance-center.md)，以確保監視與稽核資料的存取權僅限於核准的使用者，且與組織的事件回應措施整合。|
|||

## <a name="learn-more"></a>深入了解

深入了解 [Microsoft 和 NIST 網路安全架構 (CSF)](offering-nist-csf.md)，包括 NIST 800-53。
