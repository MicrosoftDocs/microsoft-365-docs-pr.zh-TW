---
title: Microsoft 365 ISO 27001 行動計畫，前 30 天、90 天及以後的優先工作
description: 當您工作以符合國際標準組織 (ISO) 需求時可以遵循的優先行動計畫
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, ISO, ISO 27001
author: BrendaCarter
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a90ed0603a6c64797cafcae66721b86ec109d0b6
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417887"
---
# <a name="microsoft-365-iso-27001-action-plan--top-priorities-for-your-first-30-days-90-days-and-beyond"></a>Microsoft 365 ISO 27001 行動計畫 — 前 30 天、90 天及過後的首要工作

國際標準組織 (ISO) 是自願性國際標準的獨立、非政府開發者。國際電子電機委員會 (IEC) 則領導著電子、電機及相關技術國際標準的準備與發佈。ISO/IEC 27000 系列標準概述控制和機制，可以協助維護資訊資產的安全性。

ISO/IEC 27001 是用來實作資訊安全性管理系統 (ISMS) 的國際標準。ISMS 說明所使用的必要方法和與需求相關聯的辨識項，這些需求在任何類型的組織中都是可靠的資訊資產安全性管理的根本。  

本文包含當您工作以符合 ISO/IEC 27001 需求時可以遵循的優先行動計畫。此行動計畫是與 Protiviti 一同開發，該公司是 Microsoft 合作夥伴，專精於法規遵循。深入了解如何藉由參加以下工作階段，在 Microsoft Ignite 使用這個行動計畫：[規劃您的 Microsoft 365 合規性路徑和資訊保護策略](https://myignite.techcommunity.microsoft.com/videos/65720) (英文)，由 Maithili Dandige (Microsoft) 和 Antonio Maio (Protiviti) 呈現。

## <a name="action-plan-outcomes"></a>行動計畫結果

這些建議橫跨有邏輯順序的三個階段，具有下列結果： 

|||
|:-----|:-----|
|**階段**|**結果**|
|30 天|**了解您的 ISO 27001 控管和合規性需求。**<br>• 進行風險評估，並調整風險管理與風險降低以達到該評估的結果。<br>• 使用 Microsoft 合規性分數評估及管理您的合規性風險。<br>• 為 14 個 ISO 27001 群組都建立標準作業程序 (SOP)。<br><br>**開始規劃將資訊分類和保留原則與工具推出至組織，以協助使用者識別、分類及保護敏感性資料和資產。**<br>• 深入了解 Azure 資訊保護應用程式與原則如何協助使用者輕易地將視覺敏感度標示和中繼資料套用至文件和電子郵件。開發貴組織的資訊分類結構描述，以及實施教育和推出計劃。<br>• 考慮將標籤推出至組織，以協助使用者輕易地將記錄保留和保護原則套用至內容。根據資訊記錄保留的法規需求，規劃貴組織的標籤，以及實施教育和推出計劃。<br><br>**藉由建立稽核和責任原則作為標準作業程序 (SOP) 的一部分，確保與資訊安全性相關的記錄受到保護，免於遺失、刪除、修改或未經授權的存取。**<br>• 啟用稽核記錄 (包括信箱稽核) 以監視 Microsoft 365 是否有潛在的惡意活動，並啟用資料外洩的鑑識調查分析。<br>• 以定期頻率搜尋貴公司的稽核記錄，以檢閱對租用戶組態設定所做的變更。<br>• 針對機密活動啟用警示原則，例如當使用者帳戶發生權限提升時。<br>• 針對長期儲存稽核記錄資料，使用 Office 365 管理活動 API 參考以與安全性資訊和事件管理 (SIEM) 工具整合。<br><br>**定義組織的系統管理和安全性角色，以及與職責劃分相關的適當原則。**<br>• 利用 Microsoft 365 系統管理角色以啟用系統管理職責劃分。<br>• 區隔權限以確保單一系統管理員不會具備超過必要的存取權。
|90 天|**使用 Microsoft 365 安全性功能來控制對環境的存取，以及根據您定義的標準作業程序 (SOP)，保護組織資訊和資產。**<br>• 藉由啟用身分識別和驗證解決方案，例如多重要素驗證和新式驗證，來保護系統管理員和使用者帳戶。<br>• 建立強式密碼原則，以管理與保護使用者帳戶認證。<br>• 設定及推出郵件加密功能，協助使用者在透過電子郵件傳送機密資料時，符合貴組織的 SOP。<br>• 防範惡意程式碼，並實作資料外洩防護及回應程序。<br>• 設定資料外洩防護 (DLP) 原則，以識別、保護及控制敏感性資料的存取。<br>• 確保根據公司原則來儲存及存取敏感性資料。<br>• 防範最常見的攻擊，包括網路釣魚電子郵件和包含惡意連結和附件的 Office 文件。
|超過 90 天|**使用 Microsoft 365 進階資料控管工具和資訊保護，以實作個人資料的持續控管方案。**<br>• 自動識別文件和電子郵件中的個人資訊<br>• 保護在整個組織行動裝置上儲存及存取的敏感性資料，並且確保對資料使用符合公司規範的裝置。<br><br>**在 Microsoft 365 及其他 Cloud 應用程式之間監視持續合規性。**<br>• 若要根據標準作業程序 (SOP) 評估效能，請利用合規性分數執行組織資訊安全性原則及其實作的定期評估。<br>• 持續檢閱及監視資訊安全性管理系統。<br>• 使用高階權限 (例如，特殊權限或系統管理員使用者) 控制及執行所有使用者和群組的定期檢閱。<br>• 部署及設定 Microsoft 365 功能，以保護具有特殊權限的身分識別，並且嚴格控制特殊權限的存取。<br>• 標準作業程序 (SOP) 的一部分，是搜尋稽核記錄以檢閱對租用戶組態設定、使用者權限提升以及具風險的使用者活動所做的變更。<br>• 監視貴組織的雲端應用程式使用方式，並且實作進階警示原則。<br>• 追蹤有風險的活動，以識別潛在惡意系統管理員、調查資料外洩，或確認是否符合合規性。

## <a name="30-days--powerful-quick-wins"></a>30 天 — 強力快速致勝

這些工作可以快速地完成，並且對使用者的影響小。

|||
|:-----|:-----|
|**適用範圍**|**工作**|
|了解您的 ISO 27001 控管和合規性需求。|• 使用[合規性分數](compliance-score.md)評估及管理您的合規性風險，以執行貴組織的 ISO 27001:2013 評估。為 14 個 ISO 27001 群組建立標準作業程序 (SOP)。
|開始規劃將資訊分類和保留原則與工具推出至組織，以協助使用者識別、分類及保護敏感性資料和資產。|• 藉由推出分類原則和 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)應用程式，協助使用者根據您的資訊保護原則和標準作業程序 (SOP)，輕鬆地識別及分類敏感性資料。  開發貴組織的資訊分類架構 (原則)，以及實施教育和推出計劃。<br>• 藉由將 [Microsoft 365 標籤](https://docs.microsoft.com/microsoft-365/compliance/labels)推出至組織，協助使用者輕易地將記錄保留和保護原則套用至內容。根據資訊記錄保留的法規需求，規劃貴組織的標籤，以及實施教育和推出計劃。
|藉由建立稽核和責任原則作為標準作業程序 (SOP) 的一部分，確保與資訊安全性相關的記錄受到保護，免於遺失、刪除、修改或未經授權的存取。|• 針對所有 Exchange 信箱啟用[稽核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) (部分機器翻譯) 和[信箱稽核](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) (部分機器翻譯)，以監視 Microsoft 365 中是否有潛在的惡意活動，並啟用資料外洩的鑑識調查分析。<br>• 以定期頻率搜尋貴公司的稽核記錄，以檢閱對租用戶組態設定所做的變更。<br>• 在 Microsoft 365 安全性或合規性中心中，針對機密活動啟用 [Microsoft 365 警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，例如當使用者帳戶發生權限提升時。<br>•   針對稽核記錄資料的長期儲存，使用 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)以與安全性資訊和事件管理 (SIEM) 工具整合。
|定義組織的系統管理和安全性角色，以及與職責劃分相關的適當原則。|• 使用 [Microsoft 365 系統管理角色](https://support.office.com/article/understanding-administrative-roles-52f29955-6a60-435f-aba9-eb69c898606a) (英文) 以區隔系統管理職責。附註：許多系統管理員角色在 Exchange Online、SharePoint Online 和商務用 Skype Online 中有對應的角色。<br>• 區隔權限以確保單一系統管理員不會具備超過必要的存取權。|

## <a name="90-days--enhanced-protections"></a>90 天 — 加強的保護

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。 

|||
|:-----|:-----|
|**適用範圍**|**工作**|
|使用 Microsoft 365 安全性功能來控制對環境的存取，以及根據您定義的標準作業程序 (SOP)，保護組織資訊和資產。|• 藉由實作[身分識別與裝置存取原則](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations) (部分機器翻譯) 來保護系統管理員和使用者帳戶，包括針對所有使用者帳戶啟用多重要素驗證 (MFA)，針對所有應用程式啟用新式驗證。<br>• 建立[強式密碼原則](https://www.microsoft.com/research/publication/password-guidance) (英文)，以管理與保護使用者帳戶認證。<br>• 設定 [Office 365 郵件加密 (OME)](https://docs.microsoft.com/microsoft-365/compliance/ome)，協助使用者在透過電子郵件傳送機密資料時，符合組織的 SOP。<br>• 將 [Windows Defender 進階威脅防護 (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 部署至所有桌上型電腦以防範惡意程式碼，以及資料外洩防護和回應。<br>• 設定、測試及部署[資料外洩防護 (DLP) 原則](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) (部分機器翻譯)，以在文件和電子郵件內識別、監視及[自動保護](https://docs.microsoft.com/microsoft-365/compliance/apply-protection-to-personal-data-in-office-365)超過 80 個常見的敏感性資料類型，包括財務、醫療及個人識別資訊。<br>• 藉由設定[原則提示](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips) (部分機器翻譯)，在電子郵件寄件者寄送違規郵件之前，通知他們可能會違反您的其中一項原則。 在 Outlook、Outlook 網頁版和適用於裝置的 OWA 中可以將原則提示設定為呈現簡短的通知，在建立郵件期間提供可能的原則違規資訊。<br>• 實作 [Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (部分機器翻譯)，協助防範最常見的攻擊，包括網路釣魚電子郵件和包含惡意連結和附件的 Office 文件。|


## <a name="beyond-90-days--ongoing-security-data-governance-and-reporting"></a>超過 90 天 - 持續的安全性、資料控管及報告

保護待用及傳輸中的個人資料、偵測及回應資料外洩，以及協助安全性措施的一般測試。這些是以上述工作為基礎建置的安全性措施。  


|||
|:-----|:-----|
|**適用範圍**|**工作**|
|使用 Microsoft 365 進階資料控管工具和資訊保護，以實作個人資料的持續控管方案。|• 使用[將標籤套用至 Office 365 中的個人資料](https://docs.microsoft.com/microsoft-365/compliance/apply-labels-to-personal-data-in-office-365)，藉由自動套用 Microsoft 365 標籤來識別文件和電子郵件中的個人資訊。<br>• 使用 [Microsoft Intune](https://docs.microsoft.com/intune/) 保護在整個組織行動裝置上儲存及存取的機密資料，並且確保對資料使用符合公司規範的裝置。|
|在 Microsoft 365 及其他 Cloud 應用程式之間監視持續合規性。|• 若要根據標準作業程序 (SOP) 評估效能，請使用[合規性分數](compliance-score.md)持續執行組織資訊安全性原則及其實作的定期 ISO 27001:2013 評估。<br>• 持續檢閱及監視資訊安全性管理系統。<br>• 使用 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)，以高階權限 (例如，特殊權限或系統管理員使用者) 控制及執行所有使用者和群組的定期檢閱。<br>• 部署和設定 [Office 365 中特殊權限的存取管理](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-overview) (部分機器翻譯)，對 Office 365 中特殊權限的系統管理工作提供細微的存取控制。  一旦啟用，使用者必須要求即時存取，透過範圍與時間高度受到限制的核准工作流程，完成提升權限和授與特殊權限的工作。<br>• 標準作業程序 (SOP) 的一部分，是搜尋稽核記錄以檢閱對租用戶組態設定、使用者權限提升以及具風險的使用者活動所做的變更。<br>• 稽核[非擁有者信箱存取](https://docs.microsoft.com/Exchange/policy-and-compliance/non-owner-mailbox-access-reports) 以識別潛在的資訊外洩，以及主動檢閱所有 Exchange Online 信箱上的非擁有者存取。<br>• 使用 [Microsoft 365 警示原則、資料外洩防護報告和Microsoft Cloud App Security](https://docs.microsoft.com/microsoft-365/security/office-365-security/monitor-for-leaks-of-personal-data)，來監視貴組織的雲端應用程式使用方式，並且根據啟發學習法和使用者活動實作進階警示原則。<br>• 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 自動追蹤有風險的活動，以識別潛在惡意的系統管理員、調查資料外洩，或確認符合合規性要求。|

## <a name="learn-more"></a>深入了解

- Microsoft 信任中心：[ISO/IEC 27001:2013 資訊安全性管理標準](offering-iso-27001.md)
