---
title: Microsoft 365 企業版服務概觀 |Microsoft Docs
description: 此內容提供 Microsoft 365 企業版和企業使用建議的概觀。
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290158"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 企業版服務和概念

Microsoft 365 企業版專為大型組織所設計，且整合了 Office 365 企業版、Windows 10 企業版和 Enterprise Mobility + Security (EMS)，可讓每個人都能發揮其創意並安全地共同作業。 Microsoft 365 企業版包括 Windows 10 企業版和可透過 Office 365 專業增強版取得的 Office 應用程式。

Windows 10 和 Office 365 專業增強版都提供三月和九月透過半年通道釋出給企業的新功能。 半年通道的功能發行版本支援期間是 18 個月。 Microsoft Intune 和 System Center Configuration Manager 都提供部署和更新 Windows 10 和 Office 365 專業增強版的功能。

這裡提供最新版的 Windows 10、Office 365 專業增強版、Microsoft Intune 和 System Center Configuration Manager：

|     |**半年通道 (已設定目標)**|**半年通道**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (即將推出)|1703 版|
|**Office 365 專業增強版**|版本 1803|1708 版|
|**Intune**|N/A|1708 版|
|**System Center Configuration Manager**|Technical Preview 1708 版|1706 版<sup>*</sup>|

<sup>*</sup> System Center Configuration Manager Update 1706 最新分支以主控台內更新形式提供，適用於先前安裝、執行 1606、1610 或 1702 版本的站台。

> [!NOTE]
> Microsoft Azure services are also updated on a regular basis, but are not referenced by a version number. To review the latest updates, and what's coming, for Azure services, see the [cloud platform roadmap](https://www.microsoft.com/cloud-platform/roadmap).

如需有關這些版本中可用功能的詳細資訊，請參閱下列文章：
- [Windows 10 中的新增功能](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10 版本資訊](https://technet.microsoft.com/windows/release-info)
- [Windows 10 更新記錄](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365 用戶端更新通道版本](https://technet.microsoft.com/office/mt465751)
- [Microsoft Intune 的新功能](https://docs.microsoft.com/intune/whats-new)
- [System Center Configuration Manager 的新功能](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [System Center Configuration Manager Technical Preview 1708 中的功能](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>服務概觀

本節提供 Microsoft 365 Enterprise 內含的 EMS 及 Office 365 服務概觀，並介紹必要的核心概念，讓您了解如何發揮其最佳效用，以滿足組織需求。 這些服務提供多種功能，讓 Microsoft 雲端企業系統管理員不只能保護公司員工的身分識別及裝置，也能控制公司資料本身的存取權，不論是傳輸中資料或待用資料皆可。

|Service|描述|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD 提供一套完整的身分識別管理功能，包含多重要素驗證、裝置註冊、自助式密碼管理、自助式群組管理、角色型存取控制、應用程式使用量監視、進階稽核，以及安全性監視及警示。|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|此服務可讓您偵測會影響組織身分識別的潛在弱點，以及透過條件式存取原則對低、中、高程度的登入風險與使用者風險設定自動式回應。|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|此服務可讓組織將具有特殊權限作業持續存取權的人數減到最少；Azure AD Privileged Identity Management 引進了合格管理員的概念。合格管理員必須是不定時需要特殊授權存取的使用者。 該角色會處於非使用中狀態，直到使用者需要存取時，角色會完成啟動程序，並在一段預定時間內成為使用中的管理員。|
|[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure 資訊保護是一種雲端式解決方案，屬於 EMS E5 供應項目的一部份，可協助組織分類、標記及保護其文件和電子郵件。 這可以由系統管理員定義規則和條件來自動完成、由使用者手動完成，或在提供建議給使用者的情況下由系統管理員搭配使用者的組合來完成。 您可以使用 Azure 資訊保護標籤，將分類套用至文件和電子郵件。 當您這樣做時，即可隨時識別分類，無論資料的儲存位置或與誰共用。<br><br>Azure 資訊保護原則設定受 [Azure 版權管理](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)保護。 與套用標籤的方式類似，使用版權管理套用的保護會跟著文件和電子郵件，不論是在組織、網路、檔案伺服器及應用程式的內部或外部，均不受位置影響。|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune 是以雲端為基礎的企業行動管理 (EMM) 服務，可協助讓您的工作人員提高生產力，同時保護公司資料。 Intune 與 Azure AD 緊密地整合以控制身分識別及存取權，以用於裝置及應用程式管理。 [Intune 的裝置管理](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)功能可用於設定及保護使用者的裝置，包括 Windows 電腦。<br><br>Intune 裝置管理功能支援[攜帶您自己的裝置 (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 註冊，讓使用者能夠註冊個人手機、平板電腦或個人電腦；也支援[公司擁有的裝置 (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 註冊，以進行自動註冊、共用裝置或預先授權註冊需求設定等管理案例。 為了提高安全性，您甚至可以要求 MFA 註冊裝置。 一經註冊而進入管理，Intune 即可設定裝置功能及設定，以確保公司資源的存取安全無虞。|

## <a name="important-concepts-to-understand"></a>若要了解的重要概念
核心概念及 EMS 功能，您應該先熟悉下表所述。

|核心概念|說明|
|------------|-----------|
|[Azure 多重要素驗證 (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Microsoft 的雙步驟驗證解決方案，為 Azure MFA 可協助保護存取資料和應用程式，同時符合使用者需求的簡單的登入程序。 它會傳遞嚴密的驗證，透過各種驗證方法，包括電話、 文字訊息或行動應用程式驗證。|
|[Azure AD 條件式存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD 的這項功能可讓您以強制執行存取雲端您根據特定條件的環境中的應用程式上的控制項。 如果控制項，也可以連接到存取的額外需求或您也可以將它封鎖。 實作的條件式存取是以原則為基礎。|
|[Exchange Online 資料外洩防護 (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Exchange Online 資料外洩防護 (DLP) 原則，可作為的高階功能。 Exchange Online 方案 2 和 Office 365 訂用帳戶，讓組織識別、 監視和自動保護 Office 365 中的敏感資訊。<br><br>使用 Exchange Online DLP 原則可以識別許多不同的位置，例如 Exchange Online、 SharePoint Online 和商務用 OneDrive 的敏感資訊。 例如，這些原則可協助您找出包含敏感資訊的文件，或防止意外共用敏感資訊與組織外部的人員。|
|[Exchange 郵件流程/傳輸規則](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange 郵件流程規則，也稱為傳輸規則，尋找滿足特定條件的郵件，通過您組織，並對它們。 郵件流程規則就像收件匣規則都可在多個電子郵件用戶端。 郵件流程規則和規則您會在 Outlook 之類的用戶端應用程式中設定的主要差異在於規則處理郵件時在而非傳輸之後郵件會傳遞該郵件流程。 郵件流程規則也包含更豐富的條件、 例外狀況和動作，可提供讓您靈活地實作許多類型的郵件原則。|
|[Intune 行動裝置管理](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune 提供行動裝置管理 (MDM) 所使用的通訊協定或行動裝置作業系統中可用的 Api。 它包含工作，例如因此註冊裝置到管理 IT 具有的裝置存取公司服務、 設定裝置，以確保其符合公司安全性和健康情況標準，提供憑證和 VPN Fi Wi-fi/設定檔，以詳細目錄存取公司服務，報告測量裝置相容性公司標準，並從受管理的裝置移除公司資料。|
|[Intune 應用程式保護原則](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Intune 應用程式保護原則可以用來保護貴公司資料，或者沒有註冊裝置的行動裝置 app 中管理到。 事實上，您使用者的行動裝置甚至可以管理由另一個非 Microsoft MDM 解決方案時[Intune 可協助保護 Office 365 資訊](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)。 確定您的員工仍然可以提高生產力，而您也可以防止資料遺失 — 故意和意外。 藉由實作應用程式層級原則，您可以限制存取公司資源，並保留您的 IT 部門的控制項內的資料。|
|[Azure AD 權杖存留期](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|您可以指定 Azure Active Directory (Azure AD) 所發出的權杖存留的期。 您可以在組織中設定權杖存留時間在組織中的所有應用程式、 多重租用戶 （多組織） 應用程式，或特定的服務主要名稱。|
|Microsoft 身分識別代理程式|Microsoft 提供的每個行動平台允許橋接的認證跨不同廠商的應用程式的應用程式，並允許特殊的增強功能，需要單一安全的地方，從何處來驗證認證。 我們會呼叫這些代理人。 在 iOS 和 Android 透過 Microsoft Authenticator 和 Intune 公司入口網站應用程式提供這些代理人。 在 Windows 10 中，這項功能是由作業系統、 技術上而言，為 Web 驗證代理已知內建帳戶選擇提供。|

## <a name="security-best-practices-and-recommendations"></a>安全性最佳做法及建議
雖然並沒有一個適用於每種客戶環境的最佳建議，但[建議的安全性原則與設定](microsoft-365-policies-configurations.md)一文介紹了重要的安全性最佳做法概念，能讓您了解。 這篇文章也提到了一般 Microsoft 建議，能讓您了解如何在 Microsoft 雲端中套用原則與設定，來確保員工的安全性與生產力。

### <a name="baseline-recommended-security-policies-and-configurations"></a>基準的建議安全性原則和設定
[一般身分識別與裝置存取原則建議](identity-access-policies.md)說明建議的原則，以協助您保護 Microsoft 365 企業版的一般。 另外還會提到我們建議的預設平台用戶端設定，以向您的使用者提供最佳 SSO 體驗，以及條件式存取的技術必要條件。

### <a name="exchange-online-access-policies"></a>Exchange Online 存取原則
[原則建議，以協助保護電子郵件](secure-email-recommended-policies.md)提供 Microsoft 建議，以協助您保護組織的電子郵件，並支援新式驗證和條件式存取的電子郵件用戶端。 這些建議是[一般身分識別和存取原則建議](identity-access-policies.md)的補充項目。

### <a name="sharepoint-online-access-policies"></a>SharePoint Online 存取原則
除了[一般身分識別和存取原則建議](identity-access-policies.md)和[協助安全的電子郵件的原則建議](secure-email-recommended-policies.md)[保護 SharePoint Online 檔案存取](sharepoint-file-access-policies.md)所提供的建議。 本文將告訴您必須建立新原則，以及如何應該修改現有的原則，以保護 Exchange Online 的電子郵件和 SharePoint online 存取檔案。

## <a name="deploy-windows-10-and-office-365-proplus"></a>部署 Windows 10 和 Office 365 專業增強版
了解如何部署 Windows 10 和 Office 365 專業增強版並整合到 Microsoft Azure Active Directory (Azure AD) 或內部部署 Active Directory Domain Services (AD DS)。 將 Windows 10、Office 365 專業增強版和您的其他企業營運應用程式部署到新裝置，或使用 Intune、System Center Configuration Manager 和群組原則將現有的裝置升級到 Windows 10 以管理裝置。

如需詳細資訊，請參閱下列文章：
- [Windows 10 部署考量](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Office 365 專業增強版部署指南](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [在企業中部署 Office 365 專業增強版的最佳做法指南](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [使用 Intune 將 Office 365 ProPlus 應用程式部署到 Windows 10 裝置](https://docs.microsoft.com/intune/apps-add-office365)

如需有關部署 Microsoft 365 的協助，請[連絡 FastTrack](https://fasttrack.microsoft.com/microsoft365)。

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>管理 Windows 10 和 Office 365 專業增強版的更新
下列連結顯示如何以最佳方式控制 Windows 10 和 Office 365 專業增強版的品質與功能更新。 了解如何有效地控制頻寬使用量，並使用最新的特色、功能和安全性更新讓 Windows 和 Office 維持在最新狀態。

如需詳細資訊，請參閱下列文件：
- [Windows 即服務概觀](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Office 365 專業增強版更新通道的概觀](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [使用 Intune 管理軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [使用 System Center Configuration Manager 來部署 Windows 10 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [使用 Configuration Manager 管理 Office 365 ProPlus](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup> Microsoft 鼓勵目前使用 Configuration Manager 來進行 Windows 更新管理的組織繼續以這種方式管理 Windows 10 用戶端電腦。

## <a name="next-steps"></a>後續步驟
[Microsoft 365 Enterprise 產品頁面](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[雲端平台藍圖](https://www.microsoft.com/cloud-platform/roadmap)
