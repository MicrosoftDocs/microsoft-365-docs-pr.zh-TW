---
title: 關於 Microsoft 365 系統管理中心的系統管理員角色
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: 系統管理員角色會與商務功能對應，並提供在系統管理中心執行特定工作的權限。 例如，服務系統管理員向 Microsoft 開啟支援票證。
ms.custom: okr_smb
ms.openlocfilehash: 446af9ad49649487f4df1982613f8e84fdf39910
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857188"
---
# <a name="about-admin-roles"></a>關於系統管理員角色

您的訂閱隨附一組系統管理員角色，您可以將這些角色指派給組織中的使用者。 每個系統管理員角色會與常見的商務功能對應，並可讓組織中的人員在系統管理中心執行特定工作的權限。 如需詳細資訊，請參閱[指派系統管理員角色](assign-admin-roles.md)

> [!TIP] 
> 正在尋找詳細的角色描述嗎？ 查看 [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

## <a name="things-to-consider"></a>考量事項...

因為系統管理員可以存取機密資料和檔案，建議您遵循這些指導方針，讓組織的資料更安全。

| 建議                  | 這為什麼很重要？                 |
| :------------------- | :------------------- |
| 有 2 到 4 個全域系統管理員  | 由於只有另一個全域系統管理員可以重設全域系統管理員的密碼，建議您在組織中至少有 2 個全域系統管理員，以防帳戶鎖定。 但是全域系統管理員對組織的設定和大部分的資料具有幾乎不受限制的存取，因此建議您不要擁有 4 個以上的全域系統管理員，因為這會是安全性威脅。 |
| 指派*最嚴謹*角色    | 指派*最嚴謹*角色表示，僅提供系統管理員完成工作所需的存取權。 例如，如果您希望某人重設員工密碼，您不應指派無限制的全域系統管理員角色，而是應指派有限制的系統管理員角色，例如密碼系統管理員或服務台系統管理員。這可協助保護您的資料安全。                 |
| 要求系統管理員使用多重要素驗證                  |    要求所有使用者使用 MFA 實際上是個好想法，但一定要要求系統管理員使用 MFA 登入。 MFA 可讓使用者輸入第二個身分識別方法，以驗證他們是否為他們所聲稱的人。 系統管理員可以存取許多客戶和員工資料，而且如果您需要進行 MFA，即使系統管理員的密碼遭到侵，密碼在沒有第二個格式身分識別格式的情況下毫無用處。  <br><br>當您開啟 MFA 時，使用者下次登入時，必須提供用於帳戶復原用途的備用電子郵件地址和電話號碼。  <br> [設定多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)          |

  
## <a name="some-roles-are-missing-from-active-users--manage-admin-roles-where-did-they-go"></a>[作用中的使用者] > [管理系統管理員角色] 中缺少部分角色。 它們去哪裡了？
根據預設，我們會先顯示大部分組織使用的角色。 如果您找不到某個角色，請移至清單底部，然後選取 [查看更多角色]****。

## <a name="how-can-i-tell-which-permissions-are-assigned-to-me"></a>我如何判斷指派給我的權限？
如果您在系統管理中心收到一則訊息，指出您沒有權限可編輯某項設定或頁面，這是因為您獲指派的角色沒有該權限。

## <a name="what-about-the-azure-active-directory-roles"></a>那 Azure Active Directory 角色呢？

Azure 入口網站具有較 Microsoft 365 系統管理中心所提供更多的角色。 如果您有大型企業，則 Azure 入口網站中的角色可能符合您組織的需求。

如需所有 Azure Active Directory 角色的清單和描述，請參閱 [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

無論您是在 Microsoft 365 系統管理中心或適用於 Windows PowerShell 的 Azure AD 模組中指派角色，已獲指派系統管理員角色的使用者，將對貴組織已訂閱的雲端服務具備相同層級的存取權。
  
## <a name="roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心提供的角色

Microsoft 365 系統管理中心可讓您管理超過 30 個 Azure AD 角色。 不過，這些角色是 Azure 入口網站中可用角色的子集。

::: moniker range="o365-worldwide"

在系統管理中心中，您可以移至 [角色]****，然後選取任何角色來開啟其詳細資料窗格。 選取 [權限]**** 索引標籤，以檢視系統管理員指派該角色具備權限之工作的詳細清單。

::: moniker-end

您可能只需要在組織中指派下列角色。 (如需詳細資訊，包括與角色相關聯的 Cmdlet，請參閱 [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。)

|系統管理員角色     |誰應獲指派此角色？  |
|---------|---------|
|Exchange 系統管理員     |   將 Exchange 系統管理員角色指派給需要檢視和管理您使用者的電子郵件信箱、Office 365 群組和 Exchange Online 的使用者。 <br><br> Exchange 系統管理員也可以：<br> - 復原使用者信箱中已刪除的郵件 <br> - 設定「傳送為」和「代表傳送」代理人 <br>  |
|全域系統管理員     |   將全域系統管理員角色指派給需要透過 Microsoft 線上服務多數管理功能和資料的全域存取權的使用者。 <br><br> 授與太多的使用者全域存取權會造成安全性風險，因此建議您擁有 2 到 4 個之間的全域系統管理員。 <br><br> 只有全域系統管理員可以：<br> - 重設所有使用者的密碼 <br> - 新增和管理網域 <br> <br> **附註：** 註冊 Microsoft 線上服務的人員會自動成為全域系統管理員。 |
|全域讀取者    |   將全域讀取者角色指派給需要檢視系統管理中心中的全域系統管理員可檢視的系統管理功能和設定的使用者。 全域讀取者系統管理員無法編輯任何設定。   |
|群組系統管理員     |   將群組管理員角色指派給需要跨系統管理中心管理所有群組設定的使用者，包括 Microsoft 365 系統管理中心和 Azure Active Directory 入口網站。 <br><br> 群組系統管理員可以：<br> - 建立、編輯、刪除及還原 Office 365 群組 <br> - 建立並更新群組建立、到期及命名原則 <br> - 建立、編輯、刪除及還原 Azure Active Directory 安全性群組| 
|服務台系統管理員     |   將服務台系統管理員角色指派給需要執行下列動作的使用者：<br> - 重設密碼 <br> - 強制使用者登出 <br> - 管理服務要求 <br> - 監視服務健康情況 <br> <br> **附註**：服務台系統管理員只能協助非系統管理員使用者和獲指派下列角色的使用者：目錄讀取者、來賓邀請者、服務台系統管理員、訊息中心讀取者和報告讀取者。      |
|Office應用程式系統管理員    |   將 Office 應用程式系統管理員角色指派給需要執行下列動作的使用者： <br> - 使用 Office 雲端原則服務來建立及管理 Office 的雲端式原則 <br> - 建立和管理服務要求 <br> - 管理使用者在 Office 應用程式中看到的新功能內容   <br> - 監視服務健康情況  |
|服務系統管理員    |   將服務系統管理員角色以額外角色形式指派給其角色不包含下列但仍需執行下列動作的管理員或使用者： <br> - 開啟和管理服務要求 <br> - 檢視和共用訊息中心文章   |
|SharePoint 系統管理員    |   將 SharePoint 系統管理員角色指派給需要存取和管理 SharePoint Online 系統管理中心的使用者。 <br><br>SharePoint 系統管理員也可以： <br> - 建立和刪除網站 <br> - 管理網站集合和全域 SharePoint 設定   |
|Teams 服務管理員    |   將 Teams 服務管理員角色指派給需要存取和管理 Teams 系統管理中心的使用者。 <br><br>Teams 服務管理員也可以： <br> - 管理會議 <br> - 管理會議橋接器 <br> - 管理所有的全組織設定，包括同盟、Teams 升級和 Teams 用戶端設定   |
|使用者系統管理員     |    將使用者系統管理員角色指派給需要為所有使用者執行下列動作的使用者： <br> - 新增使用者和群組 <br> - 指派授權 <br> - 管理最多使用者屬性 <br> - 建立與管理使用者檢視 <br> - 設定密碼到期原則 <br> - 管理服務要求 <br> - 監視服務健康情況 <br><br>  使用者系統管理員也可以針對非系統管理員和獲指派下列角色的使用者執行下列動作：目錄讀取者、來賓邀請者、服務台系統管理員、訊息中心讀取者、報告讀取者： <br> - 管理使用者名稱<br> - 刪除和還原使用者<br> - 重設密碼 <br> - 強制使用者登出 <br> - 更新 (FIDO) 裝置金鑰   |

### <a name="all-roles"></a>所有角色

 以下是 Microsoft 365 系統管理中心提供的所有可用系統管理員角色的清單。

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
|Power BI 系統管理員    |   完全存取 Power Bl 管理工作、管理服務要求及監視服務健康情況。   |
|Power 平台系統管理員     |    完全存取 Microsoft Dynamics 365、PowerApps、資料外洩防護原則和 Microsoft Flow。     |
|特殊權限角色系統管理員     |    管理 Privileged Identity Management 的角色指派和所有存取控制功能。     |
|報告讀取者     |   從報告儀表板、PowerBI 採用內容套件、登入報告和 Microsoft Graph 報告 API 讀取使用量報告資料。      |
|搜尋系統管理員     |    完全存取 Microsoft Search、指派搜尋系統管理員和搜尋編輯者角色、管理編輯內容、監視服務健康情況，以及建立服務要求。     |
|搜尋編輯者     |    只能建立、編輯及刪除 Microsoft Search 的內容，例如書籤、問與答和位置。     |
|安全性系統管理員     |    控制組織的安全性、管理安全性原則、檢閱安全性分析和報告，以及監視威脅的態勢。     |
|安全性操作員     |    調查及回應安全性警告、管理身分識別保護中心的功能，以及監視服務健康情況。     |
|安全性讀取者     |    對安全性功能、登入報告和稽核記錄具備唯讀存取權。     |
|服務支援系統管理員     |    建立 Azure、Microsoft 365 和 Office 365 服務的服務要求，以及監視服務健康情況。     |
|SharePoint 系統管理員     |    完全存取 SharePoint Online、管理 Office 365 群組、管理服務要求，以及監視服務健康情況。     |
|商務用 Skype 系統管理員     | 完全存取所有 Teams 和 Skype 功能、Skype 使用者屬性、管理服務要求，以及監視服務健康情況。      |
|Teams 系統管理員     |    完全存取 Teams 和 Skype 系統管理中心、管理 Office 365 群組和服務要求，以及監視服務健康情況。     |
|Teams 通訊管理員     |    指派電話號碼、建立及管理語音和會議原則，以及讀取通話分析。     |
|Teams 通訊支援工程師     |    讀取所有通話參與者的通話記錄詳細資料，以疑難排解通訊問題。     |
|Teams 通訊支援專員     |    讀取僅特定使用者的使用者通話詳細資料，以疑難排解通訊問題。|
|使用者系統管理員     |   重設使用者密碼、建立及管理使用者和群組，包括篩選、管理服務要求，以及監視服務健康情況。|

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作夥伴的委派系統管理

如果您正與 Microsoft 合作夥伴合作，您可以指派系統管理員角色給他們。 他們也可以反過來指派系統管理員角色給您公司 (或他們公司) 中的使用者。 例如，如果他們正在設定並為您管理線上組織，您可能會想要他們這樣做。
  
合作夥伴可以指派以下角色： 
  
- 完全管理：擁有等同於全域系統管理員的權限，但透過合作夥伴中心管理多重要素驗證除外。
    
- 有限系統管理，所具權限等同於服務台系統管理員。

在合作夥伴可以將這些角色指派給使用者之前，您必須先將該合作夥伴新增為您帳戶的委派系統管理員。 此程序是由獲授權的合作夥伴初始化。 合作夥伴會傳送電子郵件給您，詢問您是否想要授與其權限，以做為委派的系統管理員。如需指示，請參閱[授權或移除合作夥伴關係](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx)。
  
## <a name="related-articles"></a>相關文章

[指派系統管理員角色](assign-admin-roles.md)
  
[Microsoft 365 系統管理中心的活動報告](../activity-reports/activity-reports.md)
