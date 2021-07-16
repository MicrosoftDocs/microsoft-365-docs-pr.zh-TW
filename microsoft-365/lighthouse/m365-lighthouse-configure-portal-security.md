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
# <a name="configure-microsoft-365-lighthouse-portal-security"></a><span data-ttu-id="46f1b-103">設定 Microsoft 365 Lighthouse 入口網站安全性</span><span class="sxs-lookup"><span data-stu-id="46f1b-103">Configure Microsoft 365 Lighthouse portal security</span></span>

> [!NOTE]
> <span data-ttu-id="46f1b-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="46f1b-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="46f1b-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="46f1b-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="46f1b-106">當受管理的服務提供者 (MSP) 具有其承租人的委派存取許可權時，保護對客戶資料的存取權 cybersecurity 優先順序。</span><span class="sxs-lookup"><span data-stu-id="46f1b-106">Protecting access to customer data when a Managed Service Provider (MSP) has delegated access permissions to its tenants is a cybersecurity priority.</span></span> <span data-ttu-id="46f1b-107">Microsoft 365 Lighthouse 隨附必要和選用的功能，可協助您設定 Microsoft 365 Lighthouse 入口網站安全性。</span><span class="sxs-lookup"><span data-stu-id="46f1b-107">Microsoft 365 Lighthouse comes with both required and optional capabilities to help you configure Microsoft 365 Lighthouse portal security.</span></span>

## <a name="set-up-multifactor-authentication-mfa"></a><span data-ttu-id="46f1b-108">設定多重要素驗證 (MFA) </span><span class="sxs-lookup"><span data-stu-id="46f1b-108">Set up multifactor authentication (MFA)</span></span>

<span data-ttu-id="46f1b-109">如博客文章中所述， [您的 Pa $ $word 不重要](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)：</span><span class="sxs-lookup"><span data-stu-id="46f1b-109">As mentioned in the blog post [Your Pa$$word doesn't matter](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984):</span></span>

> <span data-ttu-id="46f1b-110">[您的密碼無關緊要，但 MFA 卻這樣做。</span><span class="sxs-lookup"><span data-stu-id="46f1b-110">"Your password doesn't matter, but MFA does.</span></span> <span data-ttu-id="46f1b-111">根據我們的研究，當您使用 MFA 時，您的帳戶超過99.9% 的可能性。</span><span class="sxs-lookup"><span data-stu-id="46f1b-111">Based on our studies, your account is more than 99.9% less likely to be compromised if you use MFA."</span></span>

<span data-ttu-id="46f1b-112">當使用者第一次存取 Microsoft 365 Lighthouse 時，如果他們的 Microsoft 365 帳戶尚未設定，系統會提示他們設定 MFA。</span><span class="sxs-lookup"><span data-stu-id="46f1b-112">When users access Microsoft 365 Lighthouse for the first time, they'll be prompted to set up MFA if their Microsoft 365 account doesn't already have it configured.</span></span> <span data-ttu-id="46f1b-113">在完成必要的 MFA 設定步驟之前，使用者將無法存取 Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="46f1b-113">Users won't be able to access Microsoft 365 Lighthouse until the required MFA setup step is completed.</span></span> <span data-ttu-id="46f1b-114">若要深入瞭解驗證方法，請參閱[設定您的 Microsoft 365 登入以進行多因素驗證](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="46f1b-114">To learn more about authentication methods, see [Set up your Microsoft 365 sign-in for multifactor authentication](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

## <a name="set-up-roles-to-manage-customer-tenants"></a><span data-ttu-id="46f1b-115">設定角色以管理客戶承租人</span><span class="sxs-lookup"><span data-stu-id="46f1b-115">Set up roles to manage customer tenants</span></span>

<span data-ttu-id="46f1b-116">在 Microsoft 365 Lighthouse 中存取客戶租使用者資料和設定會限制在雲端解決方案供應商 (CSP) 程式中的系統管理員代理程式和支援人員代理程式角色。</span><span class="sxs-lookup"><span data-stu-id="46f1b-116">Access to customer tenant data and settings in Microsoft 365 Lighthouse is restricted to the Admin Agent and Helpdesk Agent roles from the Cloud Solutions Provider (CSP) program.</span></span>

<span data-ttu-id="46f1b-117">您可以透過查看 [ [AZURE AD –所有群組](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ] 頁面上的安全性群組成員資格，檢查夥伴承租人中的哪些使用者具有 Admin Agent 及服務台代理程式角色。</span><span class="sxs-lookup"><span data-stu-id="46f1b-117">You can check which users in the partner tenant have the Admin Agent and Helpdesk Agent roles by reviewing the security group memberships on the [Azure AD – All Groups](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) page.</span></span> <span data-ttu-id="46f1b-118">若要瞭解如何將 CSP 計畫角色和其他許可權指派給使用者，請參閱 [將角色和許可權指派給使用者](/partner-center/permissions-overview)。</span><span class="sxs-lookup"><span data-stu-id="46f1b-118">To learn how to assign CSP program roles and other permissions to users, see [Assign roles and permissions to users](/partner-center/permissions-overview).</span></span> <span data-ttu-id="46f1b-119">如果您還沒有委派存取許可權給客戶租使用者，請參閱如何取得客戶 [的服務或訂閱的許可權](/partner-center/customers-revoke-admin-privileges)，以供 MSP 使用。</span><span class="sxs-lookup"><span data-stu-id="46f1b-119">As an MSP, if you don't already have delegated access privileges to customer tenants, learn how to get them in the article [Obtain permissions to manage a customer's service or subscription](/partner-center/customers-revoke-admin-privileges).</span></span>

<span data-ttu-id="46f1b-120">下表列出不同的 Microsoft 365 Lighthouse 頁面，以及針對系統管理員代理程式和支援人員的客戶的使用者租使用者工作所需的許可權，以及對客戶租使用者的資料和設定所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="46f1b-120">The following table lists the different Microsoft 365 Lighthouse pages and the permissions required to view and act on customer tenant data and settings for the Admin Agent and Helpdesk Agent roles.</span></span><br><br>

| <span data-ttu-id="46f1b-121">Microsoft 365 Lighthouse 頁面</span><span class="sxs-lookup"><span data-stu-id="46f1b-121">Microsoft 365 Lighthouse page</span></span> | <span data-ttu-id="46f1b-122">管理員代理程式許可權</span><span class="sxs-lookup"><span data-stu-id="46f1b-122">Admin Agent permissions</span></span> | <span data-ttu-id="46f1b-123">服務台代理程式許可權</span><span class="sxs-lookup"><span data-stu-id="46f1b-123">Helpdesk Agent permissions</span></span> |
|--|--|--|
| <span data-ttu-id="46f1b-124">首頁</span><span class="sxs-lookup"><span data-stu-id="46f1b-124">Home</span></span> | <ul><li><span data-ttu-id="46f1b-125">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-125">View all</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-126">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-126">View all</span></span></li></ul> |
| <span data-ttu-id="46f1b-127">租用戶</span><span class="sxs-lookup"><span data-stu-id="46f1b-127">Tenants</span></span> | <ul><li><span data-ttu-id="46f1b-128">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-128">View all</span></span></li><li><span data-ttu-id="46f1b-129">更新客戶連絡人及網站</span><span class="sxs-lookup"><span data-stu-id="46f1b-129">Update customer contacts and website</span></span></li><li><span data-ttu-id="46f1b-130">查看並套用部署計畫</span><span class="sxs-lookup"><span data-stu-id="46f1b-130">View and apply deployment plans</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-131">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-131">View all</span></span></li><li><span data-ttu-id="46f1b-132">更新客戶連絡人及網站</span><span class="sxs-lookup"><span data-stu-id="46f1b-132">Update customer contacts and website</span></span></li><li><span data-ttu-id="46f1b-133">查看部署計畫</span><span class="sxs-lookup"><span data-stu-id="46f1b-133">View deployment plans</span></span></li></ul> |
| <span data-ttu-id="46f1b-134">使用者</span><span class="sxs-lookup"><span data-stu-id="46f1b-134">Users</span></span> | <ul><li><span data-ttu-id="46f1b-135">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-135">View all</span></span></li><li><span data-ttu-id="46f1b-136">重設密碼</span><span class="sxs-lookup"><span data-stu-id="46f1b-136">Reset password</span></span></li><li><span data-ttu-id="46f1b-137">封鎖登入</span><span class="sxs-lookup"><span data-stu-id="46f1b-137">Block sign-in</span></span></li><li><span data-ttu-id="46f1b-138">啟用 MFA</span><span class="sxs-lookup"><span data-stu-id="46f1b-138">Enable MFA</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-139">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-139">View all</span></span></li><li><span data-ttu-id="46f1b-140">重設密碼</span><span class="sxs-lookup"><span data-stu-id="46f1b-140">Reset password</span></span></li><li><span data-ttu-id="46f1b-141">封鎖登入</span><span class="sxs-lookup"><span data-stu-id="46f1b-141">Block sign-in</span></span></li></ul> |
| <span data-ttu-id="46f1b-142">裝置</span><span class="sxs-lookup"><span data-stu-id="46f1b-142">Devices</span></span> | <ul><li><span data-ttu-id="46f1b-143">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-143">View all</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-144">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-144">View all</span></span></li></ul> |
| <span data-ttu-id="46f1b-145">威脅</span><span class="sxs-lookup"><span data-stu-id="46f1b-145">Threats</span></span> | <ul><li><span data-ttu-id="46f1b-146">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-146">View all</span></span></li><li><span data-ttu-id="46f1b-147">執行快速掃描</span><span class="sxs-lookup"><span data-stu-id="46f1b-147">Run quick scan</span></span></li><li><span data-ttu-id="46f1b-148">執行完整掃描</span><span class="sxs-lookup"><span data-stu-id="46f1b-148">Run full scan</span></span></li><li><span data-ttu-id="46f1b-149">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="46f1b-149">Reboot device</span></span></li><li><span data-ttu-id="46f1b-150">更新防病毒</span><span class="sxs-lookup"><span data-stu-id="46f1b-150">Update antivirus</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-151">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-151">View all</span></span></li></ul> |
| <span data-ttu-id="46f1b-152">基線</span><span class="sxs-lookup"><span data-stu-id="46f1b-152">Baselines</span></span> | <ul><li><span data-ttu-id="46f1b-153">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-153">View all</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-154">查看所有 </span><span class="sxs-lookup"><span data-stu-id="46f1b-154">View all</span></span></li></ul> |
| <span data-ttu-id="46f1b-155">服務健康狀況</span><span class="sxs-lookup"><span data-stu-id="46f1b-155">Service health</span></span> | <ul><li><span data-ttu-id="46f1b-156">全部查看 \*</span><span class="sxs-lookup"><span data-stu-id="46f1b-156">View all\*</span></span></li></ul> | <ul><li><span data-ttu-id="46f1b-157">全部查看 \*</span><span class="sxs-lookup"><span data-stu-id="46f1b-157">View all\*</span></span></li></ul> |

> [!NOTE]
> <span data-ttu-id="46f1b-158">目前，若要在表格中使用以 \* 標示的動作，使用者也需要在協力廠商租使用者中使用具有下列屬性的 Azure AD 角色： **test-servicehealth 程式/allEntities/allTasks**。</span><span class="sxs-lookup"><span data-stu-id="46f1b-158">Currently, to take the actions marked with \* in the table, users will also need to have the Azure AD role in the partner tenant with the following property set: **microsoft.office365.serviceHealth/allEntities/allTasks**.</span></span> <span data-ttu-id="46f1b-159">如需 Azure AD 角色的清單，請參閱 [AZURE ad 內建角色](/azure/active-directory/roles/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="46f1b-159">For a list of Azure AD roles, see [Azure AD built-in roles](/azure/active-directory/roles/permissions-reference).</span></span>

<span data-ttu-id="46f1b-160">已知與系統管理員代理程式角色相關聯的廣泛許可權，我們建議您在將協力廠商租使用者指定為系統管理員代理程式，而不是以系統管理員代理程式身分時，遵循 [最低許可權存取](/azure/active-directory/develop/secure-least-privileged-access) 的原則。</span><span class="sxs-lookup"><span data-stu-id="46f1b-160">Given the broad permissions associated with the Admin Agent role, we suggest adhering to the principle of [least privileged access](/azure/active-directory/develop/secure-least-privileged-access) when designating a partner tenant user as an Admin Agent versus Helpdesk Agent.</span></span> <span data-ttu-id="46f1b-161">若要執行此動作，一種方式是將「服務台」代理程式角色指派給必要的合作夥伴租使用者。</span><span class="sxs-lookup"><span data-stu-id="46f1b-161">One way to do this is to assign the Helpdesk Agent role to the required partner tenant users.</span></span> <span data-ttu-id="46f1b-162">這可讓他們查看客戶資料和設定，但不會進行廣泛的變更。</span><span class="sxs-lookup"><span data-stu-id="46f1b-162">This lets them view customer data and settings but not make broad changes.</span></span> <span data-ttu-id="46f1b-163">然後，視需要使用 Azure AD Privileged Identity Management (PIM) 為使用者提供時間範圍的管理代理程式角色的即時訪問核准功能。</span><span class="sxs-lookup"><span data-stu-id="46f1b-163">Then, when needed, use the just-in-time access approval capabilities of Azure AD Privileged Identity Management (PIM) to give users a time-scoped Admin Agent role.</span></span>

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a><span data-ttu-id="46f1b-164">Privileged Identity Management (PIM 設定 Azure AD) </span><span class="sxs-lookup"><span data-stu-id="46f1b-164">Set up Azure AD Privileged Identity Management (PIM)</span></span>

<span data-ttu-id="46f1b-165">MSPs 可使用 Azure AD Privileged Identity Management (PIM) ，將存取安全資訊或資源的人員人數降至最低。</span><span class="sxs-lookup"><span data-stu-id="46f1b-165">MSPs can minimize the number of people who have access to secure information or resources by using Azure AD Privileged Identity Management (PIM).</span></span> <span data-ttu-id="46f1b-166">PIM 可降低惡意人員存取資源或授權的使用者，不小心影響敏感資源的機率。</span><span class="sxs-lookup"><span data-stu-id="46f1b-166">PIM reduces the chance of a malicious person gaining access to resources or authorized users inadvertently impacting a sensitive resource.</span></span> <span data-ttu-id="46f1b-167">MSPs 也可以授與使用者對資源的即時的特殊存取權存取權，並監視指定使用者在其特殊許可權存取中所做的工作。</span><span class="sxs-lookup"><span data-stu-id="46f1b-167">MSPs can also grant users just-in-time privileged access to resources and monitor what the designated users are doing with their privileged access.</span></span>

> [!NOTE]
> <span data-ttu-id="46f1b-168">使用 Azure AD PIM 需要合作夥伴租使用者的 Azure AD Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="46f1b-168">Using Azure AD PIM requires an Azure AD Premium P2 license in the partner tenant.</span></span>

<span data-ttu-id="46f1b-169">下列步驟使用 Azure AD PIM 將夥伴租使用者使用者提升為時間範圍的系統管理員代理角色：</span><span class="sxs-lookup"><span data-stu-id="46f1b-169">The following steps elevate partner tenant users to time-scoped Admin Agent roles by using Azure AD PIM:</span></span>

1. <span data-ttu-id="46f1b-170">建立角色可指派的群組，如在 Azure Active Directory 中[建立群組來指派角色的群組](/azure/active-directory/roles/groups-create-eligible)中所述。</span><span class="sxs-lookup"><span data-stu-id="46f1b-170">Create a role-assignable group as described in the article [Create a group for assigning roles in Azure Active Directory](/azure/active-directory/roles/groups-create-eligible).</span></span>

2. <span data-ttu-id="46f1b-171">移至 [AZURE AD –所有群組](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ，並將新群組新增為系統管理員代理群組的成員。</span><span class="sxs-lookup"><span data-stu-id="46f1b-171">Go to [Azure AD – All Groups](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) and add the new group as a member of the Admin Agents group.</span></span>

3. <span data-ttu-id="46f1b-172">設定對新群組的許可權存取，如在 [指派許可權存取群組的合格擁有者和成員](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)一文中所述。</span><span class="sxs-lookup"><span data-stu-id="46f1b-172">Set up privileged access to the new group as described in the article [Assign eligible owners and members for privileged access groups](/azure/active-directory/privileged-identity-management/groups-assign-member-owner).</span></span>

<span data-ttu-id="46f1b-173">若要深入瞭解，請參閱[什麼是 Privileged Identity Management？](/azure/active-directory/privileged-identity-management/pim-configure)</span><span class="sxs-lookup"><span data-stu-id="46f1b-173">To learn more, see [What is Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)</span></span>

## <a name="other-roles-and-permissions"></a><span data-ttu-id="46f1b-174">其他角色和許可權</span><span class="sxs-lookup"><span data-stu-id="46f1b-174">Other roles and permissions</span></span>

<span data-ttu-id="46f1b-175">下表列出合作夥伴租使用者角色及其相關聯的許可權。</span><span class="sxs-lookup"><span data-stu-id="46f1b-175">The following table lists partner tenant roles and their associated permissions.</span></span><br><br>

| <span data-ttu-id="46f1b-176">合作夥伴租使用者角色</span><span class="sxs-lookup"><span data-stu-id="46f1b-176">Partner tenant roles</span></span> | <span data-ttu-id="46f1b-177">合作夥伴承租人中的許可權</span><span class="sxs-lookup"><span data-stu-id="46f1b-177">Permissions within partner tenant</span></span> |
|--|--|
| <span data-ttu-id="46f1b-178">合作夥伴租使用者的全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="46f1b-178">Global Administrator of partner tenant</span></span> | <ul><li><span data-ttu-id="46f1b-179">註冊 Microsoft 365 系統管理中心中的 Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="46f1b-179">Sign up for Microsoft 365 Lighthouse in the Microsoft 365 admin center.</span></span></li><li><span data-ttu-id="46f1b-180">接受第一次執行體驗期間的合作夥伴合約修正。</span><span class="sxs-lookup"><span data-stu-id="46f1b-180">Accept partner contract amendments during the first-run experience.</span></span></li><li><span data-ttu-id="46f1b-181">在承租人頁面上，查看客戶承租人。\*</span><span class="sxs-lookup"><span data-stu-id="46f1b-181">View customer tenants on the Tenants page.\*</span></span></li><li><span data-ttu-id="46f1b-182">啟用並停用承租人。\*</span><span class="sxs-lookup"><span data-stu-id="46f1b-182">Activate and inactivate a tenant.\*</span></span></li><li><span data-ttu-id="46f1b-183">更新客戶連絡人及網站。\*</span><span class="sxs-lookup"><span data-stu-id="46f1b-183">Update customer contacts and website.\*</span></span></li><li><span data-ttu-id="46f1b-184">建立、更新和刪除標記。\*</span><span class="sxs-lookup"><span data-stu-id="46f1b-184">Create, update, and delete tags.\*</span></span></li><li><span data-ttu-id="46f1b-185">指派及移除客戶租使用者的標記。\*</span><span class="sxs-lookup"><span data-stu-id="46f1b-185">Assign and remove tags from a customer tenant.\*</span></span></li></ul> |
| <span data-ttu-id="46f1b-186">至少有一個夥伴承租人的系統管理員</span><span class="sxs-lookup"><span data-stu-id="46f1b-186">Administrator of partner tenant with at least one</span></span><br> <span data-ttu-id="46f1b-187">使用下列屬性集指派的 Azure AD 角色：</span><span class="sxs-lookup"><span data-stu-id="46f1b-187">Azure AD role assigned with the following property set:</span></span><br> <span data-ttu-id="46f1b-188">**office365 supportTickets/allEntities/allTasks**</span><span class="sxs-lookup"><span data-stu-id="46f1b-188">**microsoft.office365.supportTickets/allEntities/allTasks**</span></span><br> <span data-ttu-id="46f1b-189"> (若要取得 Azure AD 角色的清單，請參閱 [AZURE ad 內建角色](/azure/active-directory/roles/permissions-reference)。 ) </span><span class="sxs-lookup"><span data-stu-id="46f1b-189">(For a list of Azure AD roles, see [Azure AD built-in roles](/azure/active-directory/roles/permissions-reference).)</span></span> | <ul><li><span data-ttu-id="46f1b-190">建立 Microsoft 365 Lighthouse 服務要求。</span><span class="sxs-lookup"><span data-stu-id="46f1b-190">Create Microsoft 365 Lighthouse service requests.</span></span></li></ul> |

> [!NOTE]
> <span data-ttu-id="46f1b-191">目前，若要在表格中使用以 \* 標示的動作，全域系統管理員必須承擔管理員代理程式角色。</span><span class="sxs-lookup"><span data-stu-id="46f1b-191">Currently, to take the actions marked with \* in the table, the Global Administrator must assume the Admin Agent role.</span></span>

## <a name="related-content"></a><span data-ttu-id="46f1b-192">相關內容</span><span class="sxs-lookup"><span data-stu-id="46f1b-192">Related content</span></span>

<span data-ttu-id="46f1b-193">Microsoft 365 Lighthouse (文章) [的概覽](m365-lighthouse-overview.md)</span><span class="sxs-lookup"><span data-stu-id="46f1b-193">[Overview of Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (article)\</span></span>
<span data-ttu-id="46f1b-194">[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="46f1b-194">[Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (article)</span></span>\
<span data-ttu-id="46f1b-195">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="46f1b-195">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>