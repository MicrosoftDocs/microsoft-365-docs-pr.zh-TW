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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: 系統管理員角色會與商務功能對應，並提供在系統管理中心執行特定工作的權限。 例如，服務系統管理員可以透過系統管理中心開啟支援票證。
ms.openlocfilehash: d220ee918f70a56ba27bdad9d7d0f45025fad451
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759405"
---
# <a name="about-admin-roles"></a>關於系統管理員角色

Microsoft 365 或 Office 365 訂閱隨附一組系統管理員角色，您可以使用 [Microsoft 365 系統管理中心] 將這些角色指派給組織中的使用者。 每個系統管理員角色會與常見的商務功能對應，並可讓組織中的人員在系統管理中心執行特定工作的權限。

Microsoft 365 系統管理中心可讓您管理 Azure AD 角色和 Microsoft Intune 角色。 不過，這些角色是 Azure AD 入口網站和 Intune 系統管理中心中可用角色的子集。

## <a name="before-you-begin"></a>開始之前

正在尋找您可以在 Microsoft 365 系統管理中心管理的詳細 Azure AD 角色描述的完整清單嗎？ 查看 Azure Active Directory 中的系統管理員角色權限。 [Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

正在尋找您可以在 Microsoft 365 系統管理中心管理的詳細 Intune 角色描述的完整清單嗎？  請參閱 [使用 Microsoft Intune 的角色型存取控制 (RBAC)](/mem/intune/fundamentals/role-based-access-control)。

如需在 Microsoft 365 系統管理中心指派角色的詳細資訊，請參閱[指派系統管理員角色](assign-admin-roles.md)。

### <a name="watch-what-is-an-admin"></a>注意: 何謂系統管理員?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>指派角色的安全性指導方針

因為系統管理員可以存取機密資料和檔案，建議您遵循這些指導方針，讓組織的資料更安全。

| 建議                  | 這為什麼很重要？                 |
| :------------------- | :------------------- |
| 有 2 到 4 個全域系統管理員  | 由於只有另一個全域系統管理員可以重設全域系統管理員的密碼，建議您在組織中至少有 2 個全域系統管理員，以防帳戶鎖定。 但是全域系統管理員對組織的設定和大部分的資料具有幾乎不受限制的存取，因此建議您不要擁有 4 個以上的全域系統管理員，因為這會是安全性威脅。 |
| 指派 *最嚴謹* 角色    | 指派 *最嚴謹* 角色表示，僅提供系統管理員完成工作所需的存取權。 例如，如果您希望某人重設員工密碼，您不應指派無限制的全域系統管理員角色，而是應指派有限制的系統管理員角色，例如密碼系統管理員或服務台系統管理員。這可協助保護您的資料安全。                 |
| 要求系統管理員使用多重要素驗證                  |    要求所有使用者使用 MFA 實際上是個好想法，但一定要要求系統管理員使用 MFA 登入。 MFA 可讓使用者輸入第二個身分識別方法，以驗證他們是否為他們所聲稱的人。 系統管理員可以存取許多客戶和員工資料，而且如果您需要進行 MFA，即使系統管理員的密碼遭到侵，密碼在沒有第二個格式身分識別格式的情況下毫無用處。  <br><br>當您開啟 MFA 時，使用者下次登入時，必須提供用於帳戶復原用途的備用電子郵件地址和電話號碼。  <br> [設定多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)          |

如果您在系統管理中心收到一則訊息，指出您沒有權限可編輯某項設定或頁面，這是因為您獲指派的角色沒有該權限。

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>常用的 Microsoft 365 系統管理中心角色

在 Microsoft 365 系統管理中心中，您可以移至 [角色]，然後選取任何角色來開啟其詳細資料窗格。 選取 [權限] 索引標籤，以檢視系統管理員指派該角色具備權限之工作的詳細清單。 選取 [已指派] 或 [指派的系統管理員] 索引標籤來將使用者新增至角色。

您可能只需要在組織中指派下列角色。 根據預設，我們會先顯示大部分組織使用的角色。 如果您找不到某個角色，請移至清單底部，然後選取 [依類別顯示全部]。 (如需詳細資訊，包括與角色相關聯的 Cmdlet，請參閱 [Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。)

|系統管理員角色     |誰應獲指派此角色？  |
|---------|---------|
|計費系統管理員     |   將計費系統管理員角色指派給進行購買、管理訂閱和服務要求，以及監視服務健康情況的使用者。 <br><br> 計費系統管理員也可以：<br> - 管理所有層面的帳單 <br> - 在 Azure 入口網站中建立和管理支援票證 <br>  |
|Exchange 系統管理員     |   將 Exchange 系統管理員角色指派給需要檢視和管理您使用者的電子郵件信箱、Microsoft 365 群組和 Exchange Online 的使用者。 <br><br> Exchange 系統管理員也可以：<br> - 復原使用者信箱中已刪除的郵件 <br> - 設定「傳送為」和「代表傳送」代理人 <br>  |
|全域系統管理員     |   將全域系統管理員角色指派給需要透過 Microsoft 線上服務多數管理功能和資料的全域存取權的使用者。 <br><br> 授與太多的使用者全域存取權會造成安全性風險，因此建議您擁有 2 到 4 個之間的全域系統管理員。 <br><br> 只有全域系統管理員可以：<br> - 重設所有使用者的密碼 <br> - 新增和管理網域 <br> <br> **附註：** 註冊 Microsoft 線上服務的人員會自動成為全域系統管理員。 |
|全域讀取者    |   將全域讀取者角色指派給需要檢視系統管理中心中的全域系統管理員可檢視的系統管理功能和設定的使用者。 全域讀取者系統管理員無法編輯任何設定。   |
|群組系統管理員     |   將群組管理員角色指派給需要跨系統管理中心管理所有群組設定的使用者，包括 Microsoft 365 系統管理中心和 Azure Active Directory 入口網站。 <br><br> 群組系統管理員可以：<br> - 建立、編輯、刪除及還原 Microsoft 365 群組 <br> - 建立並更新群組建立、到期及命名原則 <br> - 建立、編輯、刪除及還原 Azure Active Directory 安全性群組| 
|服務台系統管理員     |   將服務台系統管理員角色指派給需要執行下列動作的使用者：<br> - 重設密碼 <br> - 強制使用者登出 <br> - 管理服務要求 <br> - 監視服務健康情況 <br> <br> **附註**：服務台系統管理員只能協助非系統管理員使用者和獲指派下列角色的使用者：目錄讀取者、來賓邀請者、服務台系統管理員、訊息中心讀取者和報告讀取者。      |
|授權系統管理員    |   將授權系統管理員角色指派給需要指派和移除使用者授權，以及編輯其使用位置的使用者。 <br/><br/> 授權系統管理員也可以： <br> - 重新處理群組型授權的授權指派 <br> - 將產品授權指派群組以進行群組型授權  |
|Office應用程式系統管理員    |   將 Office 應用程式系統管理員角色指派給需要執行下列動作的使用者： <br> - 使用 Office 雲端原則服務來建立及管理 Office 的雲端式原則 <br> - 建立和管理服務要求 <br> - 管理使用者在 Office 應用程式中看到的新功能內容   <br> - 監視服務健康情況  |
|密碼系統管理員  |   將密碼系統管理員角色指派給需要重設非系統管理員和密碼系統管理員密碼的使用者。   |
|服務支援系統管理員   |   將服務支援系統管理員角色以額外角色的形式，指派給在其常見系統管理員角色之外需要執行下列動作的管理員或使用者： <br> - 開啟和管理服務要求 <br> - 檢視和共用訊息中心文章 <br> - 監視服務健康情況   |
|SharePoint 系統管理員    |   將 SharePoint 系統管理員角色指派給需要存取和管理 SharePoint Online 系統管理中心的使用者。 <br><br>SharePoint 系統管理員也可以： <br> - 建立和刪除網站 <br> - 管理網站集合和全域 SharePoint 設定   |
|Teams 服務管理員    |   將 Teams 服務管理員角色指派給需要存取和管理 Teams 系統管理中心的使用者。 <br><br>Teams 服務管理員也可以： <br> - 管理會議 <br> - 管理會議橋接器 <br> - 管理所有的全組織設定，包括同盟、Teams 升級和 Teams 用戶端設定   |
|使用者系統管理員     |    將使用者系統管理員角色指派給需要為所有使用者執行下列動作的使用者： <br> - 新增使用者和群組 <br> - 指派授權 <br> - 管理最多使用者屬性 <br> - 建立與管理使用者檢視 <br> - 設定密碼到期原則 <br> - 管理服務要求 <br> - 監視服務健康情況 <br><br>  使用者系統管理員也可以針對非系統管理員和獲指派下列角色的使用者執行下列動作：目錄讀取者、來賓邀請者、服務台系統管理員、訊息中心讀取者、報告讀取者： <br> - 管理使用者名稱<br> - 刪除和還原使用者<br> - 重設密碼 <br> - 強制使用者登出 <br> - 更新 (FIDO) 裝置金鑰   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作夥伴的委派系統管理

如果您正與 Microsoft 合作夥伴合作，您可以指派系統管理員角色給他們。 他們也可以反過來指派系統管理員角色給您公司 (或他們公司) 中的使用者。 例如，如果他們正在設定並為您管理線上組織，您可能會想要他們這樣做。
  
合作夥伴可以指派以下角色： 
  
- **系統管理代理人**：擁有等同於全域系統管理員的權限，但透過合作夥伴中心管理多重要素驗證除外。

- **服務台代理人**：等同於服務台系統管理員的權限。

在合作夥伴可以將這些角色指派給使用者之前，您必須先將該合作夥伴新增為您帳戶的委派系統管理員。 此程序是由獲授權的合作夥伴初始化。 合作夥伴會傳送電子郵件給您，詢問您是否想要授與其權限，以做為委派的系統管理員。如需指示，請參閱[授權或移除合作夥伴關係](../misc/add-partner.md)。
  
## <a name="related-articles"></a>相關文章

[指派系統管理員角色](assign-admin-roles.md)

[Microsoft 365 系統管理中心的 Azure AD 角色](azure-ad-roles-in-the-mac.md)

[Exchange Online 系統管理員角色](about-exchange-online-admin-role.md)
  
[Microsoft 365 系統管理中心的活動報告](../activity-reports/activity-reports.md)
