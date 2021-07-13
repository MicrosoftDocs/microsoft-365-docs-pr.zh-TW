---
title: 設定 Microsoft 365 Lighthouse 入口網站安全性
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解如何設定入口網站安全性。
ms.openlocfilehash: 1e67903fc6c3dfd4e1949ef8c3e80ad4af12ad5c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395082"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>設定 Microsoft 365 Lighthouse 入口網站安全性

> [!NOTE]
> 本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。 如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

當受管理的服務提供者 (MSP) 具有其承租人的委派存取許可權時，保護對客戶資料的存取權 cybersecurity 優先順序。 Microsoft 365 Lighthouse 隨附必要和選用的功能，可協助您設定 Microsoft 365 Lighthouse 入口網站安全性。

## <a name="set-up-multifactor-authentication-mfa"></a>設定多重要素驗證 (MFA) 

如博客文章中所述， [您的 Pa $ $word 不重要](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)：

> [您的密碼無關緊要，但 MFA 卻這樣做。 根據我們的研究，當您使用 MFA 時，您的帳戶超過99.9% 的可能性。

當使用者第一次存取 Microsoft 365 Lighthouse 時，如果他們的 Microsoft 365 帳戶尚未設定，系統會提示他們設定 MFA。 在完成必要的 MFA 設定步驟之前，使用者將無法存取 Microsoft 365 Lighthouse。 若要深入瞭解驗證方法，請參閱[設定您的 Microsoft 365 登入以進行多因素驗證](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-roles-to-manage-customer-tenants"></a>設定角色以管理客戶承租人

在 Microsoft 365 Lighthouse 中存取客戶租使用者資料和設定會限制在雲端解決方案供應商 (CSP) 程式中的系統管理員代理程式和支援人員代理程式角色。

您可以透過查看 [ [AZURE AD –所有群組](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ] 頁面上的安全性群組成員資格，檢查夥伴承租人中的哪些使用者具有 Admin Agent 及服務台代理程式角色。 若要瞭解如何將 CSP 計畫角色和其他許可權指派給使用者，請參閱 [將角色和許可權指派給使用者](/partner-center/permissions-overview)。 如果您還沒有委派存取許可權給客戶租使用者，請參閱如何取得客戶 [的服務或訂閱的許可權](/partner-center/customers-revoke-admin-privileges)，以供 MSP 使用。

下表列出不同的 Microsoft 365 Lighthouse 頁面，以及針對系統管理員代理程式和支援人員的客戶的使用者租使用者工作所需的許可權，以及對客戶租使用者的資料和設定所需的許可權。<br><br>

| Microsoft 365 Lighthouse 頁面 | 管理員代理程式許可權 | 服務台代理程式許可權 |
|--|--|--|
| 首頁 | <ul><li>查看所有 </li></ul> | <ul><li>查看所有 </li></ul> |
| 租用戶 | <ul><li>查看所有 </li><li>更新客戶連絡人及網站</li><li>查看並套用部署計畫</li></ul> | <ul><li>查看所有 </li><li>更新客戶連絡人及網站</li><li>查看部署計畫</li></ul> |
| 使用者 | <ul><li>查看所有 </li><li>重設密碼</li><li>封鎖登入</li><li>啟用 MFA</li></ul> | <ul><li>查看所有 </li><li>重設密碼</li><li>封鎖登入</li></ul> |
| 裝置 | <ul><li>查看所有 </li></ul> | <ul><li>查看所有 </li></ul> |
| 威脅 | <ul><li>查看所有 </li><li>執行快速掃描</li><li>執行完整掃描</li><li>重新開機裝置</li><li>更新防病毒</li></ul> | <ul><li>查看所有 </li></ul> |
| 基線 | <ul><li>查看所有 </li></ul> | <ul><li>查看所有 </li></ul> |
| 服務健康狀況 | <ul><li>全部查看 *</li></ul> | <ul><li>全部查看 *</li></ul> |

> [!NOTE]
> 目前，若要在表格中使用以 * 標示的動作，使用者也需要在協力廠商租使用者中使用具有下列屬性的 Azure AD 角色： **test-servicehealth 程式/allEntities/allTasks**。 如需 Azure AD 角色的清單，請參閱 [AZURE ad 內建角色](/azure/active-directory/roles/permissions-reference)。

已知與系統管理員代理程式角色相關聯的廣泛許可權，我們建議您在將協力廠商租使用者指定為系統管理員代理程式，而不是以系統管理員代理程式身分時，遵循 [最低許可權存取](/azure/active-directory/develop/secure-least-privileged-access) 的原則。 若要執行此動作，一種方式是將「服務台」代理程式角色指派給必要的合作夥伴租使用者。 這可讓他們查看客戶資料和設定，但不會進行廣泛的變更。 然後，視需要使用 Azure AD Privileged Identity Management (PIM) 為使用者提供時間範圍的管理代理程式角色的即時訪問核准功能。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Privileged Identity Management (PIM 設定 Azure AD) 

MSPs 可使用 Azure AD Privileged Identity Management (PIM) ，將存取安全資訊或資源的人員人數降至最低。 PIM 可降低惡意人員存取資源或授權的使用者，不小心影響敏感資源的機率。 MSPs 也可以授與使用者對資源的即時的特殊存取權存取權，並監視指定使用者在其特殊許可權存取中所做的工作。

> [!NOTE]
> 使用 Azure AD PIM 需要合作夥伴租使用者的 Azure AD Premium P2 授權。

下列步驟使用 Azure AD PIM 將夥伴租使用者使用者提升為時間範圍的系統管理員代理角色：

1. 建立角色可指派的群組，如在 Azure Active Directory 中[建立群組來指派角色的群組](/azure/active-directory/roles/groups-create-eligible)中所述。

2. 移至 [AZURE AD –所有群組](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ，並將新群組新增為系統管理員代理群組的成員。

3. 設定對新群組的許可權存取，如在 [指派許可權存取群組的合格擁有者和成員](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)一文中所述。

若要深入瞭解，請參閱[什麼是 Privileged Identity Management？](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>其他角色和許可權

下表列出合作夥伴租使用者角色及其相關聯的許可權。<br><br>

| 合作夥伴租使用者角色 | 合作夥伴承租人中的許可權 |
|--|--|
| 合作夥伴租使用者的全域系統管理員 | <ul><li>註冊 Microsoft 365 系統管理中心中的 Microsoft 365 Lighthouse。</li><li>接受第一次執行體驗期間的合作夥伴合約修正。</li><li>在承租人頁面上，查看客戶承租人。\*</li><li>啟用並停用承租人。\*</li><li>更新客戶連絡人及網站。\*</li><li>建立、更新和刪除標記。\*</li><li>指派及移除客戶租使用者的標記。\*</li></ul> |
| 至少有一個夥伴承租人的系統管理員<br> 使用下列屬性集指派的 Azure AD 角色：<br> **office365 supportTickets/allEntities/allTasks**<br>  (若要取得 Azure AD 角色的清單，請參閱 [AZURE ad 內建角色](/azure/active-directory/roles/permissions-reference)。 )  | <ul><li>建立 Microsoft 365 Lighthouse 服務要求。</li></ul> |

> [!NOTE]
> 目前，若要在表格中使用以 * 標示的動作，全域系統管理員必須承擔管理員代理程式角色。

## <a name="related-content"></a>相關內容

Microsoft 365 Lighthouse (文章) [的概覽](m365-lighthouse-overview.md)
[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (文章) \
[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) 