---
title: Microsoft 365 系統管理中心的 Azure Active Directory 角色
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: 在 Microsoft 365 系統管理中心管理這些 Azure 系統管理員角色。
ms.openlocfilehash: afb025feb6e867b16be7a844a5f48ef42759b543
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898025"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的 Azure Active Directory 角色

Microsoft 365 系統管理中心可讓您管理超過 30 個 Azure AD 角色。 不過，這些角色是 Azure 入口網站中可用角色的子集。 如果您有大型企業，則 Azure 入口網站中的角色可能符合您組織的需求。 正在尋找 Azure AD 的詳細角色描述嗎？ 查看 [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

無論您是在 Microsoft 365 系統管理中心或適用於 Windows PowerShell 的 Azure AD 模組中指派角色，已獲指派系統管理員角色的使用者，將對貴組織已訂閱的雲端服務具備相同層級的存取權。

::: moniker range="o365-worldwide"

在 Microsoft 365 系統管理中心中，您可以移至 [角色]****，然後選取任何角色來開啟其詳細資料窗格。 選取 [權限]**** 索引標籤，以檢視系統管理員指派該角色具備權限之工作的詳細清單。 選取 [已指派]**** 或 [指派的系統管理員]**** 索引標籤來將使用者新增至角色。 如需在 Microsoft 365 系統管理中心指派角色的詳細資訊，請參閱[指派系統管理員角色](assign-admin-roles.md)。

::: moniker-end

## <a name="all-azure-ad-roles"></a>所有 Azure AD 角色

以下是 Microsoft 365 系統管理中心提供的所有可用系統管理員角色的清單。 正在尋找 Microsoft 365 系統管理員的詳細角色描述嗎？ 請查看[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。

|系統管理員角色     |說明  |
|---------|---------|
|應用程式系統管理員     |    完全存取企業應用程式、應用程式註冊，以及應用程式 Proxy 設定。     |
|應用程式開發人員     |    建立應用程式註冊，並代表其自己同意應用程式存取權。     |
|驗證系統管理員     |    可以要求使用者針對非密碼認證 (例如 MFA) 重新註冊驗證。     |
|Azure 資訊保護系統管理員     |   管理 Azure 資訊保護原則的標籤、管理保護範本，以及啟用保護。       |
|計費系統管理員     |    採購、管理訂閱、管理服務要求，以及監視服務健康情況。     |
|雲端應用程式系統管理員     | 完全存取企業應用程式和應用程式註冊。 無應用程式 Proxy。     |
|雲端裝置系統管理員     |    啟用、停用和刪除裝置，且可以讀取 Windows 10 BitLocker 金鑰。     |
|合規性系統管理員     |    管理法規需求和電子文件探索案例，維護位置、身分識別和應用程式的資料控管。     |
|合規性資料系統管理員     |    追蹤資料、確保資料受到保護、深入分析問題，以及協助降低風險。     |
|條件式存取系統管理員     |   管理 Azure Active Directory 條件式存取設定，而非 Exchange ActiveSync 條件式存取原則。      |
|客戶加密箱存取核准者     |      管理客戶加密箱要求，可開啟或關閉客戶加密箱。   |
|電腦分析系統管理員     |   可存取和管理桌面管理工具及服務。      |
|Dynamics 365 系統管理員     |  完全存取 Microsoft Dynamics 365 Online、管理服務要求，以及監視服務健康情況。       |
|Exchange 系統管理員     |  完全存取 Exchange Online、建立及管理群組、管理服務要求，以及監視服務健康情況。    |
|外部身分識別提供者系統管理員    |     設定身分識別提供者以在直接同盟中使用。    |
|全域系統管理員     |    對所有系統管理中心的所有管理功能和大部分資料具備不受限制的存取權。     |
|全域讀取者     |    對於系統管理中心的所有管理功能和大部分資料具備唯讀存取權。 如需此角色的存取權限和限制的詳細描述，請參閱 [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)。    |
|群組系統管理員   |跨系統管理中心建立群組和管理所有群組設定。|
|來賓邀請者     |    管理 Azure Active Directory B2B 來賓使用者邀請。     |
|服務台系統管理員     | 重設所有非系統管理員和部分系統管理員角色的密碼和重新驗證、管理服務要求，以及監視服務健康情況。      |
|Intune 系統管理員     | 完全存取 Intune、管理使用者和裝置以關聯原則、建立及管理群組。      |
|Kaizala 系統管理員     |    完全存取所有 Kaizala 管理功能和資料，管理服務要求。     |
|授權系統管理員     |     指派和移除使用者的授權，並編輯其使用位置。    |
|訊息中心隱私權讀取者     |    存取訊息中心的資料隱私權訊息，取得電子郵件通知。     |
|訊息中心讀取者     | 讀取並共用訊息中心的一般訊，取得每週的電子郵件摘要，對使用者、群組、網域和訂閱具備唯讀存取權。     |
|Office應用程式系統管理員    |   管理 Office 的雲端原則，以及使用者在其 Office 應用程式中看到的新功能內容。   |
|密碼管理員    |   重設非下列角色系統管理員或成員的使用者密碼：目錄讀取者、來賓邀請者、密碼系統管理員。 此角色無法授與管理服務要求或監視服務健康情況的能力。   |
|Power BI 系統管理員    |   完全存取 Power Bl 管理工作、管理服務要求及監視服務健康情況。   |
|Power 平台系統管理員     |    完全存取 Microsoft Dynamics 365、PowerApps、資料外洩防護原則和 Microsoft Flow。     |
|特殊權限角色系統管理員     |    管理 Privileged Identity Management 的角色指派和所有存取控制功能。     |
|特殊權限驗證系統管理員     |    重設密碼、更新非密碼認證、強制使用以登出及監視服務健康情況，以及管理服務要求。     |
|報告讀取者     |   從報告儀表板、PowerBI 採用內容套件、登入報告和 Microsoft Graph 報告 API 讀取使用量報告資料。      |
|搜尋系統管理員     |    完全存取 Microsoft Search、指派搜尋系統管理員和搜尋編輯者角色、管理編輯內容、監視服務健康情況，以及建立服務要求。     |
|搜尋編輯者     |    只能建立、編輯及刪除 Microsoft Search 的內容，例如書籤、問與答和位置。     |
|安全性系統管理員     |    控制組織的安全性、管理安全性原則、檢閱安全性分析和報告，以及監視威脅的態勢。     |
|安全性操作員     |    調查及回應安全性警告、管理身分識別保護中心的功能，以及監視服務健康情況。     |
|安全性讀取者     |    對安全性功能、登入報告和稽核記錄具備唯讀存取權。     |
|服務支援系統管理員     |    建立 Azure、Microsoft 365 和 Office 365 服務的服務要求，以及監視服務健康情況。     |
|SharePoint 系統管理員     |    完全存取 SharePoint Online、管理 Microsoft 365 群組、管理服務要求，以及監視服務健康情況。     |
|商務用 Skype 系統管理員     | 完全存取所有 Teams 和 Skype 功能、Skype 使用者屬性、管理服務要求，以及監視服務健康情況。      |
|Teams 系統管理員     |    完全存取 Teams 和 Skype 系統管理中心、管理 Microsoft 365 群組和服務要求，以及監視服務健康情況。     |
|Teams 通訊管理員     |    指派電話號碼、建立及管理語音和會議原則，以及讀取通話分析。     |
|Teams 通訊支援工程師     |    讀取所有通話參與者的通話記錄詳細資料，以疑難排解通訊問題。     |
|Teams 通訊支援專員     |    讀取僅特定使用者的使用者通話詳細資料，以疑難排解通訊問題。|
|使用者系統管理員     |   重設使用者密碼、建立及管理使用者和群組，包括篩選、管理服務要求，以及監視服務健康情況。|

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作夥伴的委派系統管理

如果您正與 Microsoft 合作夥伴合作，您可以指派系統管理員角色給他們。 他們也可以反過來指派系統管理員角色給您公司 (或他們公司) 中的使用者。 例如，如果他們正在設定並為您管理線上組織，您可能會想要他們這樣做。
  
合作夥伴可以指派以下角色： 

- 完全管理：擁有等同於全域系統管理員的權限，但透過合作夥伴中心管理多重要素驗證除外。

- 有限系統管理，所具權限等同於服務台系統管理員。

在合作夥伴可以將這些角色指派給使用者之前，您必須先將該合作夥伴新增為您帳戶的委派系統管理員。 此程序是由獲授權的合作夥伴初始化。 合作夥伴會傳送電子郵件給您，詢問您是否想要授與其權限，以做為委派的系統管理員。如需指示，請參閱[授權或移除合作夥伴關係](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。
  
## <a name="related-articles"></a>相關文章

[關於 Microsoft 365 系統管理員角色](about-admin-roles.md)

[指派系統管理員角色](assign-admin-roles.md)
  
[Microsoft 365 系統管理中心的活動報告](../activity-reports/activity-reports.md)