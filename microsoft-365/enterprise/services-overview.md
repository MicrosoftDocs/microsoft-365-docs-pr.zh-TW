---
title: Microsoft 365 企業版服務概觀 | Microsoft Docs
description: 本內容提供 Microsoft 365 Enterprise 概觀及企業使用建議。
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866680"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 企業版服務與概念

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
> Microsoft Azure 服務也會根據定期、 更新但沒有參考的版本號碼。若要檢閱的最新更新及什麼傳入、 Azure services，請參閱[雲端平台藍圖](https://www.microsoft.com/cloud-platform/roadmap)。

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

## <a name="important-concepts-to-understand"></a>重要概念須知
下表描述了您應該很熟悉的核心概念及 EMS 功能。

|核心概念|描述|
|------------|-----------|
|[Azure Multi-Factor Authentication (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Azure MFA 是 Microsoft 的雙步驟驗證解決方案，能協助保護資料及應用程式的存取權，同時滿足使用者對簡單登入程序的需求。 其透過多種驗證方法，包含通話、簡訊或行動應用程式驗證來提供增強式驗證。|
|[Azure AD 條件式存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD 的這項功能可讓您在環境中，根據特定條件強制控制雲端應用程式的存取權。 取得控制權後，您可以為存取權加上其他要求條件，或是將其封鎖。 條件式存取的實作以原則為基礎。|
|[Exchange Online 資料外洩防護 (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Exchange Online 資料外洩防護 (DLP) 原則是 Exchange Online 方案 2 及 Office 365 訂閱的進階功能，可讓組織識別、監視及自動保護整個 Office 365 中的敏感性資訊。<br><br>利用 Exchange Online DLP 原則，您可以在多個位置識別敏感性資訊，例如 Exchange Online、SharePoint Online 及商務用 OneDrive。 舉例來說，這些原則可協助您識別包含敏感性資訊的文件，或防止不小心與組織外部人員共用敏感性資訊。|
|[Exchange 郵件流程/傳輸規則](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange 郵件流程規則又稱為傳輸規則，會在通過組織的訊息中尋找特定條件，並對其採取行動。 郵件流程規則就像是在許多電子郵件用戶端中可用的收件匣規則。 郵件流程規則與您在用戶端應用程式 (例如 Outlook) 中設定的規則的主要差異在於，郵件流程規則會在訊息傳輸途中就採取行動，而非訊息傳遞完成之後。 郵件流程規則還包含一組更多樣的條件、例外狀況及動作，提供您實作各類型訊息原則的彈性。|
|[Intune 行動裝置管理](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune 藉由使用行動作業系統中可用的通訊協定或 API，提供行動裝置管理 (MDM)。 其中包含許多工作，例如註冊裝置以進入管理，讓 IT 擁有顯示正在存取公司服務的裝置詳細目錄、設定裝置以確保這些裝置能夠達到公司安全性及健康情況的標準、提供能夠存取公司服務的憑證及 Wi-Fi/VPN 設定檔、測量裝置對公司標準的合規性並提出報告，以及將公司資料自受管理的裝置中移除。|
|[Inunte 應用程式保護原則](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Inunte 應用程式保護原則可用於保護行動應用程式中的公司資料，而不論裝置是否已註冊接受管理。 事實上，即使使用者的行動裝置由 Microsoft 以外的 MDM 解決方案進行管理，[Intune 還是可以協助保護 Office 365 資訊](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)。 確保員工生產力的同時，也能防止故意與無意的資料外洩。 藉由實作應用程式層級原則，您可以限制公司資源的存取權，並將資料保留在 IT 部門的控制範圍內。|
|[Azure AD 權杖存留期](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|您可以指定 Azure Active Directory (Azure AD) 發行之權杖的存留期。 您可以為組織中的所有應用程式、多租用戶 (多組織) 應用程式或組織中的特定服務主體設定權杖存留期。|
|Microsoft 身分識別代理程式|Microsoft 為每個允許在不同廠商的應用程式間橋接認證的行動平台提供應用程式，且允許需要單一安全位置的特殊增強行功能在該位置驗證認證。 這就稱為代理程式。 在 iOS 及 Android 上，這些代理程式能夠從 Microsoft Authenticator 及 Intune 公司入口網站取得。 在 Windows 10 中，這項功能由作業系統內建的帳戶選擇器提供，實際上稱為網頁驗證代理程式。|

## <a name="security-best-practices-and-recommendations"></a>安全性最佳做法及建議
雖然並沒有一個適用於每種客戶環境的最佳建議，但[建議的安全性原則與設定](microsoft-365-policies-configurations.md)一文介紹了重要的安全性最佳做法概念，能讓您了解。 這篇文章也提到了一般 Microsoft 建議，能讓您了解如何在 Microsoft 雲端中套用原則與設定，來確保員工的安全性與生產力。

### <a name="baseline-recommended-security-policies-and-configurations"></a>基準的建議安全性原則和設定
[一般身分識別與裝置存取原則建議](identity-access-policies.md)描述了一般建議的原則，能協助您保護 Microsoft 365 企業版。 另外還會提到我們建議的預設平台用戶端設定，以向您的使用者提供最佳 SSO 體驗，以及條件式存取的技術必要條件。

### <a name="exchange-online-access-policies"></a>Exchange Online 存取原則
[協助保護電子郵件的原則建議](secure-email-recommended-policies.md)提供了 Microsoft 建議，能協助您保護組織電子郵件，以及支援新式驗證與條件式存取的電子郵件用戶端。 這些建議是[一般身分識別與存取原則建議](identity-access-policies.md)的補充項目。

### <a name="sharepoint-online-access-policies"></a>SharePoint Online 存取原則
除了[一般身分識別與存取原則建議](identity-access-policies.md)及[協助保護電子郵件的原則建議](secure-email-recommended-policies.md)，另外還提供了[保護 SharePoint Online 檔案存取權](sharepoint-file-access-policies.md)的建議。 這篇文章描述了必須建立的新原則，以及現有原則的修改方式，來保護 Exchange Online 電子郵件與 SharePoint Online 檔案存取權。

## <a name="deploy-windows-10-and-office-365-proplus"></a>部署 Windows 10 和 Office 365 專業增強版
了解如何部署 Windows 10 和 Office 365 專業增強版並整合到 Microsoft Azure Active Directory (Azure AD) 或內部部署 Active Directory Domain Services (AD DS)。 將 Windows 10、Office 365 專業增強版和您的其他企業營運應用程式部署到新裝置，或使用 Intune、System Center Configuration Manager 和群組原則將現有的裝置升級到 Windows 10 以管理裝置。

如需詳細資訊，請參閱下列文件：
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
