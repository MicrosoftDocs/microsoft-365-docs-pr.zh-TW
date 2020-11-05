---
title: Microsoft 365 安全性與合規性中心的權限
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 透過使用 Microsoft 365 安全性中心或 Microsoft 365 合規性中心，您可以集中管理與安全性或合規性相關的所有工作權限。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f7dcddd7070f95ae61b17b9623dfcbab4a62e5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920629"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Microsoft 365 合規性中心和 Microsoft 365 安全性中心中的權限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


您的組織需要管理跨所有 Microsoft 365 服務的安全性與合規性案例。 您需要靈活地為組織 IT 群組中的合適人員提供正確的管理員權限。 透過使用 Microsoft 365 安全性中心或 Microsoft 365 合規性中心，您可以集中管理與安全性或合規性相關的所有工作權限。

在全域管理員指派這些系統管理員角色後，系統管理員就可以存取 Microsoft 365 中所有服務的功能和資料，例如 Microsoft 365 安全性中心、Microsoft 365 合規性中心、Azure、Office 365和 Enterprise Mobility + Security。

## <a name="what-the-microsoft-365-roles-are"></a>什麼是 Microsoft 365 角色

Microsoft 365 合規性中心和Microsoft 365 安全性中心中出現的角色是 Azure Active Directory 角色。 這些角色的設計符合組織 IT 群組中的各個職位，進而能輕鬆地為人員提供完成工作所需的所有權限。

****

|角色|描述|
|---|---|
|**全域管理員**|具有此角色的使用者可以存取所有 Microsoft 365 服務中的所有系統管理功能。 只有全域管理員才能指派其他系統管理員角色。|
|**合規性資料管理員**|具有此角色的使用者可以追蹤 Microsoft 365 中的組織資料，確保其受到保護，並深入了解任何問題以協助降低風險。|
|**合規性管理員**|具有此角色的使用者可幫助您的組織遵守任何法規要求、管理電子文件探索案例，並維護Microsoft 365 各個位置、身分和應用程式的資料監管原則。|
|**安全性操作員**|具有此角色的使用者可檢視、調查和回應 Microsoft 365 使用者、裝置和內容所受的主動威脅。|
|**安全性讀取者**|具有此角色的使用者可檢視和調查 Microsoft 365 使用者、裝置和內容所受的主動威脅，但是 (與安全性操作員不同) 他們沒有透過採取行動而回應的權限。|
|**安全性系統管理員**|具有此角色的使用者可透過管理安全性原則、檢視 Microsoft 365各項產品的安全性分析和報告以及在威脅環境中保持最新速度來控制組織的整體安全性。|
|

## <a name="what-the-microsoft-365-roles-have-access-to"></a>Microsoft 365 角色擁有哪些權限

以下是可用的角色以及獲派角色的人員可執行的工作。

### <a name="global-administrator"></a>全域管理員

具有此角色的使用者可以存取 Azure Active Directory 中所有的系統管理功能，以及使用 Azure Active Directory 身分識別的服務，例如 Microsoft 365 資訊安全中心、Microsoft 365 合規性中心、Exchange Online、SharePoint Online 和商務用 Skype Online。 註冊 Azure Active Directory 租用戶的人員會變成全域管理員。 只有全域管理員才能指派其他系統管理員角色。 您的公司可以有多位全域管理員。 全域管理員可以為任何使用者和所有其他系統管理員重設密碼。

### <a name="compliance-administrator"></a>合規性管理員

具有此角色的使用者有權限管理 Microsoft 365 合規性中心、Microsoft 365 系統管理中心、Azure 和安全性與合規性中心中的合規性相關功能。 使用者也可以管理 Exchange 系統管理中心、Teams 和商務用 Skype 系統管理中心內的所有功能，並建立適用於 Azure 和 Microsoft 365 的支援票證。

****

|在此服務中...|合規性系統管理員可以...|
|---|---|
|[**Microsoft 365 合規性中心**](https://compliance.microsoft.com/)|保護和管理組織在所有 Microsoft 365 服務中的資料。 <br/><br/> 管理合規性警示。|
|[**合規性管理員**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|追蹤、指派和確認組織的法規合規性活動。|
|[**安全性與合規性中心**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|管理資料控管。 <br/><br/> 執行法律和資料調查。 <br/><br/> 管理資料主體要求。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|檢視所有 Intune 稽核資料。|
|[**雲端 App 安全性**](https://docs.microsoft.com/cloud-app-security/manage-admins)|具有唯讀權限，並可管理警示。 <br/><br/> 可建立和修改檔案原則，並允許檔案控管動作。 <br/><br/> 可檢視 [資料管理] 下的所有內建報告。|
|

### <a name="compliance-data-administrator"></a>合規性資料管理員

具有此角色的使用者有權限保護和追蹤 Microsoft 365 合規性中心、Microsoft 365 系統管理中心和 Azure 中的資料。 使用者也可以管理 Exchange 系統管理中心、合規性管理員、Teams 和商務用 Skype 系統管理中心內的所有功能，並建立適用於 Azure 和 Microsoft 365 的支援票證。

****

|在此服務中...|合規性資料系統管理員可以...|
|---|---|
|[**Microsoft 365 合規性中心**](https://compliance.microsoft.com/)|保護和管理組織在所有 Microsoft 365 服務中的資料。 <br/><br/> 管理合規性警示。 <br/><br/> 管理敏感度標籤|
|[**合規性管理員**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|追蹤、指派和確認組織的法規合規性活動。|
|[**安全性與合規性中心**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|管理資料控管。 <br/><br/> 執行法律和資料調查。 <br/><br/> 管理資料主體要求。 <br/><br/> 管理敏感度標籤|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control) (即將推出)|檢視所有 Intune 稽核資料。|
|[**雲端 App 安全性**](https://docs.microsoft.com/cloud-app-security/manage-admins)|使用唯讀權限來檢視資訊。 <br/>管理警示。 <br/><br/> 建立和修改檔案原則，並允許檔案控管動作。 <br/><br/> 檢視 [資料管理] 下的所有內建報告。|
|

### <a name="security-administrator"></a>安全性系統管理員

具有此角色的使用者有權限管理 Microsoft 365 安全性中心、Azure Active Directory Identity Protection、Azure 資訊保護和安全性與合規性中心中的安全性相關功能。

****

|在此服務中...|安全性系統管理員可以...|
|---|---|
|[**Microsoft 365 安全性中心**](https://security.microsoft.com/)|監視所有 Microsoft 365 服務的安全性相關原則。 <br/><br/>  管理安全性威脅和警示。 <br/><br/> 檢視報告。 <br/><br/> 管理敏感度標籤。|
|**身分識別保護中心**|執行安全性讀取者角色可執行的所有動作，並執行所有身分識別保護中心的作業，除了重設密碼之外。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|執行安全性讀取者角色可執行的所有動作。 <br/><br/> 「無法」管理 Azure AD 角色指派或設定。|
|[**安全性與合規性中心**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|管理安全性原則。 <br/><br/> 檢視、調查及回應安全性威脅 <br/><br/> 檢視報告。 <br/><br/> 管理敏感度標籤。|
|**適用於身分識別的 Microsoft Defender**|監視與回應可疑的安全性活動。|
|**適用於端點的 Microsoft Defender 和 EDR**|指派角色。 <br/><br/> 管理電腦群組。 <br/><br/> 設定端點威脅偵測和自動補救。 <br/><br/> 檢視、調查及回應警示。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|檢視使用者、裝置、註冊、設定及應用程式資訊。 <br/><br/> 「無法」變更 Intune。|
|[**雲端 App 安全性**](https://docs.microsoft.com/cloud-app-security/manage-admins)|新增系統管理員、新增原則和設定、上傳記錄及執行控管動作。|
|[**Azure Defender**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles) (即將推出)|檢視安全性原則、檢視安全性狀態、編輯安全性原則、檢視警示和建議、關閉警示和建議。|
|[**Office 365 服務健康狀態**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|檢視 Office 365 服務的健康狀態。|
|

### <a name="security-operator"></a>安全性操作員

具備此角色的使用者可管理警示，並具有安全性相關功能的全域唯讀存取權 (含 Microsoft 365 安全性中心、Azure Active Directory、身分識別保護、Privileged Identity Management 中的所有資訊)，並能讀取 Azure Active Directory 登入報告與稽核記錄，且具有安全性與合規性中心的全域唯讀存取權。

****

|在此服務中...|安全性系統操作員可以...|
|---|---|
|[**Microsoft 365 安全性中心**](https://security.microsoft.com/)|執行安全性讀取者角色可執行的所有動作。 <br/><br/> 檢視、調查及回應安全性警示。|
|**身分識別保護中心** (即將推出)|執行安全性讀取者角色可執行的所有動作。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|執行安全性讀取者角色可執行的所有動作。|
|[**安全性與合規性中心**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|執行安全性讀取者角色可執行的所有動作。 <br/><br/> 檢視、調查及回應安全性威脅|
|**適用於端點的 Microsoft Defender 和 EDR**|執行安全性讀取者角色可執行的所有動作。 <br/><br/> 檢視、調查及回應警示。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|檢視使用者、裝置、註冊、設定及應用程式資訊。 <br/><br/> 「無法」變更 Intune。|
|[**雲端 App 安全性**](https://docs.microsoft.com/cloud-app-security/manage-admins)|執行安全性讀取者角色可執行的所有動作，以及檢視核取消警示。|
|[**Office 365 服務健康狀態**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|檢視 Office 365 服務的健康狀態。|
|

### <a name="security-reader"></a>安全性讀取者

具備此角色的使用者具有安全性相關功能的全域唯讀存取權 (含 Microsoft 365 資訊安全中心、Azure Active Directory、Identity Protection、Privileged Identity Management 中的所有資訊)，並能讀取 Azure Active Directory 登入報告與稽核記錄，且具有安全性與合規性中心的全域唯讀存取權。

****

|在此服務中...|安全性讀取者可以...|
|---|---|
|[**Microsoft 365 安全性中心**](https://security.microsoft.com/)|檢視所有 Microsoft 365 服務的安全性相關原則。 <br/><br/> 檢視安全性威脅和警示。 <br/><br/> 檢視報告。|
|**身分識別保護中心**|閱讀有關安全性功能的所有安全性報告和設定資訊：反垃圾郵件、加密、資料遺失防護 (DLP)、反惡意程式碼、適用於 Office 365 的 Defender、反網路釣魚和郵件流程規則 (也稱為傳輸規則)。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|以唯讀方式存取 Azure AD PIM 中所顯示的一切資訊︰Azure AD 角色指派的原則和報告、安全性檢閱，以及在未來還可透過讀取來存取 Azure AD 角色指派以外案例的原則資料和報告。 <br/><br/> 「無法」註冊 Azure AD PIM 或對它進行任何變更。 擔任此角色的人員可以在 PIM 的入口網站中或是透過 PowerShell，來啟用其他角色 (例如「全域管理員」或「特殊權限角色管理員」)，前提是該使用者必須有資格擔任該角色。|
|[**安全性與合規性中心**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|檢視安全性原則。 <br/><br/> 檢視及調查安全性威脅。 <br/><br/> 檢視報告。|
|**適用於端點的 Microsoft Defender 和 EDR**|檢視和調查警示。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|檢視使用者、裝置、註冊、設定及應用程式資訊。 <br/><br/> 「無法」變更 Intune。|
|[**雲端 App 安全性**](https://docs.microsoft.com/cloud-app-security/manage-admins)|使用唯讀權限來檢視資訊。 <br/><br/> 管理警示。|
|[**Azure Defender**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles)|檢視建議和警示。 <br/><br/> 檢視安全性原則。 <br/><br/> 檢視安全性狀態、但無法進行變更。|
|[**Office 365 服務健康狀態**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|檢視 Office 365 服務的健康狀態。|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>全域管理員可在 Azure Active Directory 中管理角色

在 Microsoft 365合規性中心和 Microsoft 365 安全性中心選取角色時，即可檢視其指派。 但若要管理這些指派，您需要移至 Azure Active Directory。

如需詳細資訊，請參閱[在 Azure Active Directory 中檢視和指派系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

![在 Azure Active Directory 中管理權限的連結](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>在服務而非 Azure Active Directory 中管理角色

在 Microsoft 365 合規性中心和Microsoft 365 安全性中心中出現的角色也會出現在這些角色有權限的服務中。 例如，您可以在安全性與合規性中心看到這些角色。

![安全性與合規性中心的角色](../../media/m365-roles-in-o365-scc.png)

### <a name="breaking-inheritance"></a>打破繼承

請務必了解，您在 Azure Active Directory 中管理這些角色時，您也是在為「所有」Microsoft 365 服務集中管理這些角色。 但是，當您在特定服務中 (例如安全性與合規性中心) 中管理角色時，您只是管理「該特定服務」的角色。 服務中角色的指派和權限會覆寫授予 Azure Active Directory 角色的任何權限。

這可能很有用 - 例如，如果將某人指派為安全性系統管理員角色，則他們沒有管理事件的權限。 但是，您可以使用適用於端點的 Microsoft Defender 中的權限來授與他們該服務中事件管理的特定權限。

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>在哪裡可找到每個 Microsoft 365 服務的角色資訊

透過將使用者指派為其中一個 Microsoft 365 合規性或安全性系統管理員角色，您可以授與該使用者授予一系列的 Microsoft 365 服務權限。 使用以下連結來尋找每個服務中，角色特定權限的詳細資訊。

****

|Microsoft 365 服務|角色資訊|
|---|---|
|Office 365 與 Microsoft 365 商務方案中的系統管理員角色|[Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)|
|Azure Active Directory (Azure AD) 與 Azure AD Identity Protection|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|適用於身分識別的 Microsoft Defender|[適用於身分識別的 Microsoft Defender 角色群組](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure 資訊保護|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|合規性管理員|[合規性管理員](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager-setup#set-user-permissions-and-assign-roles) (英文)|
|Exchange Online|[Exchange 角色型存取控制](https://docs.microsoft.com/exchange/understanding-role-based-access-control-exchange-2013-help)|
|Intune|[Intune 角色型存取控制](https://docs.microsoft.com/intune/role-based-access-control)|
|受管理的電腦|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[角色型存取控制](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|安全性與合規性中心|[Microsoft 365 系統管理員角色](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|安全分數|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <br/><br/> [關於 Office 365 中的 SharePoint 系統管理員角色](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/商務用 Skype|[Azure AD 系統管理員角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|適用於端點的 Microsoft Defender|[適用於端點的 Microsoft Defender 角色式存取控制](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="what-is-coming-soon"></a>即將推出的內容

我們仍在努力建立 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中的權限。 例如，我們目前正努力支援以下功能：

- 在 Microsoft 365 合規性中心和Microsoft 365 安全性中心中管理角色，而不需移至 Azure Active Directory。

- 透過新增或移除特定權限來自訂角色。

- 使用您所選權限來建立自訂角色。
