---
title: 存取系統管理入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
description: 如何尋找及使用管理員入口網站，包括控制對它的存取。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: d22cef41fb1d6dc3fde39681ad84edc510440b11
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110004"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="1cc15-104">存取管理員入口網站</span><span class="sxs-lookup"><span data-stu-id="1cc15-104">Access the admin portal</span></span>

<span data-ttu-id="1cc15-105">您的 Microsoft Managed 桌面服務閘道是 [Microsoft 端點管理員](https://endpoint.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="1cc15-105">Your gateway to the Microsoft Managed Desktop service is [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="1cc15-106">如果您不熟悉此入口網站的裝置管理功能，請參閱 [Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。</span><span class="sxs-lookup"><span data-stu-id="1cc15-106">If you are unfamiliar with the capabilities of this portal for device management, see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

> [!NOTE]
> <span data-ttu-id="1cc15-107">在 [Microsoft 端點管理員](https://endpoint.microsoft.com/) 中，支援下列瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="1cc15-107">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) the following browsers are supported:</span></span>
> - <span data-ttu-id="1cc15-108">Microsoft Edge (最新版本) </span><span class="sxs-lookup"><span data-stu-id="1cc15-108">Microsoft Edge (latest version)</span></span>
> - <span data-ttu-id="1cc15-109">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="1cc15-109">Microsoft Internet Explorer 11</span></span>
> - <span data-ttu-id="1cc15-110">Safari (最新版本，僅限 Mac) </span><span class="sxs-lookup"><span data-stu-id="1cc15-110">Safari (latest version, Mac only)</span></span>
> - <span data-ttu-id="1cc15-111">Chrome (最新版本) </span><span class="sxs-lookup"><span data-stu-id="1cc15-111">Chrome (latest version)</span></span>
> - <span data-ttu-id="1cc15-112">Firefox (最新版本) </span><span class="sxs-lookup"><span data-stu-id="1cc15-112">Firefox (latest version)</span></span>

<span data-ttu-id="1cc15-113">您的系統管理帳戶需要特定許可權，才能存取 Microsoft 端點管理員中的 Microsoft 受管理桌面系統管理功能。</span><span class="sxs-lookup"><span data-stu-id="1cc15-113">Your administrative account will need specific permissions in order to access the Microsoft Managed Desktop administrative features in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="1cc15-114">您可以使用以角色為基礎的存取控制，管理組織內這些功能的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="1cc15-114">You can manage admin access to these features within your organization by using role-based access control.</span></span> <span data-ttu-id="1cc15-115">有幾個 Azure Active Directory (Azure AD) 系統管理員角色和內建 Microsoft 受管理的桌面角色，可提供更細微的控制，可對 Microsoft Managed Desktop Admin 入口網站內的不同功能提供更細微的控制。</span><span class="sxs-lookup"><span data-stu-id="1cc15-115">Several Azure Active Directory (Azure AD) administrator roles and built-in Microsoft Managed Desktop roles are available to provide more granular control to different features within the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="1cc15-116">如需 Azure Active Directory 角色的詳細資訊，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1cc15-116">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="1cc15-117">與適用于各種 Microsoft 產品和服務的 Azure AD 系統管理員角色不同，內建角色是 Microsoft 受管理的桌面所特有的，只會保證此服務的系統管理功能存取權。</span><span class="sxs-lookup"><span data-stu-id="1cc15-117">Unlike Azure AD administrator roles that apply to various Microsoft products and services, the built-in roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service.</span></span> <span data-ttu-id="1cc15-118">管理員可以個別或結合 Azure AD 系統管理員角色，將內建角色指派給使用者，以將 Microsoft 管理的桌面許可權新增至現有的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1cc15-118">Admins can assign built-in roles to users individually or in combination with Azure AD administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.</span></span>

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a><span data-ttu-id="1cc15-119">具有 Microsoft 受管理桌面存取權的 Azure Active Directory 角色</span><span class="sxs-lookup"><span data-stu-id="1cc15-119">Azure Active Directory roles with Microsoft Managed Desktop access</span></span>

|<span data-ttu-id="1cc15-120">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="1cc15-120">Azure AD role</span></span>  |<span data-ttu-id="1cc15-121">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="1cc15-121">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="1cc15-122">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-122">Global Administrator</span></span>     | <span data-ttu-id="1cc15-123">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中 **所有功能的讀取和寫入權限** 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-123">Admins with this role will have **read and write permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="1cc15-124">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="1cc15-124">Global Reader</span></span>     | <span data-ttu-id="1cc15-125">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-125">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="1cc15-126">Intune 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-126">Intune Service Administrator</span></span>     |  <span data-ttu-id="1cc15-127">具有此角色的系統管理員具有與 Microsoft Managed Desktop Admin 入口網站中的 **安全性無關的功能的讀取和寫入權限** 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-127">Admins with this role will have **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="1cc15-128">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-128">Service Support Administrator</span></span>     | <span data-ttu-id="1cc15-129">具有此角色的系統管理員對與安全性和寫入權限不相關的功能，對 Microsoft Managed Desktop Admin 入口網站中 **管理支援要求** 的 **功能具有唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="1cc15-129">Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="1cc15-130">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-130">Security Admin</span></span> | <span data-ttu-id="1cc15-131">具有此角色的系統管理員對管理員入口網站中 Microsoft 受管理的電腦具有 **安全性相關功能的** 所有功能和寫入權限，具有 **唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="1cc15-131">Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the Admin portal.</span></span> |
|<span data-ttu-id="1cc15-132">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="1cc15-132">Security Reader</span></span> |<span data-ttu-id="1cc15-133">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-133">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>|

<span data-ttu-id="1cc15-134">如果您需要協助指派 Azure Active Directory 角色，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1cc15-134">If you need help with assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cc15-135">只有全域系統管理員角色具有在 Microsoft Managed Desktop 中 *註冊* 您的組織所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="1cc15-135">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1cc15-136">請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。</span><span class="sxs-lookup"><span data-stu-id="1cc15-136">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="1cc15-137">在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的 *最低* 許可權。</span><span class="sxs-lookup"><span data-stu-id="1cc15-137">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a><span data-ttu-id="1cc15-138">Microsoft 受管理的桌面所提供的內建角色</span><span class="sxs-lookup"><span data-stu-id="1cc15-138">Built-in roles provided by Microsoft Managed Desktop</span></span>


|<span data-ttu-id="1cc15-139">內建角色</span><span class="sxs-lookup"><span data-stu-id="1cc15-139">Built-in role</span></span>  |<span data-ttu-id="1cc15-140">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="1cc15-140">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="1cc15-141">Microsoft 受管理的桌面服務管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-141">Microsoft Managed Desktop Service Administrator</span></span>  | <span data-ttu-id="1cc15-142">指派給使用者時，此角色可讓系統管理員 **讀取和寫入權限給** 與 Microsoft Managed Desktop admin 入口網站中的安全性無關的功能。</span><span class="sxs-lookup"><span data-stu-id="1cc15-142">When assigned to a user, this role gives the admin **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>  |
|<span data-ttu-id="1cc15-143">Microsoft 受管理的桌面服務讀取器</span><span class="sxs-lookup"><span data-stu-id="1cc15-143">Microsoft Managed Desktop Service Reader</span></span> | <span data-ttu-id="1cc15-144">指派給使用者時，此角色可讓系統管理員對與 Microsoft Managed Desktop Admin 入口網站中的安全性無關的 **功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-144">When assigned to a user, this role gives the admin **read-only permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span> |
|<span data-ttu-id="1cc15-145">Microsoft 受管理的桌面安全性管理員</span><span class="sxs-lookup"><span data-stu-id="1cc15-145">Microsoft Managed Desktop Security Manager</span></span> |<span data-ttu-id="1cc15-146">指派給使用者時，此角色只會讓系統管理員 **讀取和寫入權限，只會針對** Microsoft Managed Desktop admin 入口網站中的安全性相關功能。</span><span class="sxs-lookup"><span data-stu-id="1cc15-146">When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the Microsoft Managed Desktop Admin portal.</span></span>   |

> [!NOTE]
> <span data-ttu-id="1cc15-147">安全性功能包括安全性相關的通訊、安全性連絡人的管理、安全性相關支援要求的管理，以及與安全性相關的報表存取。</span><span class="sxs-lookup"><span data-stu-id="1cc15-147">Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.</span></span> 

### <a name="assigning-built-in-roles-to-user"></a><span data-ttu-id="1cc15-148">將內建角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="1cc15-148">Assigning built-in roles to user</span></span>

<span data-ttu-id="1cc15-149">為了便於管理內建角色，每個自訂角色的安全性群組都有名稱為「新式工作區角色- _角色名稱_」 (例如，「新式工作區角色–安全性管理員」 ) 。</span><span class="sxs-lookup"><span data-stu-id="1cc15-149">For easy management of built-in roles, there is a security group for each custom role with the name "Modern Workplace Roles - _Role Name_"(for example, “Modern Workplace Roles – Security Manager”).</span></span> <span data-ttu-id="1cc15-150">若要將使用者指派給其中一個安全性群組，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1cc15-150">To assign users to one of these security groups, follow these steps:</span></span>
1.  <span data-ttu-id="1cc15-151">請移至 Microsoft 端點管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="1cc15-151">Go the Microsoft Endpoint Manager portal.</span></span>
2.  <span data-ttu-id="1cc15-152">選取左側的 [ **群組** ]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-152">Select **Groups** on the left side.</span></span>
3.  <span data-ttu-id="1cc15-153">搜尋 **新式的工作區角色**，然後選取與您要指派之角色相關聯的群組。</span><span class="sxs-lookup"><span data-stu-id="1cc15-153">Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.</span></span> 
4.  <span data-ttu-id="1cc15-154">選取左側的 [ **成員** ]，然後選取 [+ 在命令列 **新增成員** ]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-154">Select **Members** on the left side, and then select **+ Add members** on the command bar.</span></span>
5.  <span data-ttu-id="1cc15-155">輸入要新增之人員的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1cc15-155">Enter the email of the person being added.</span></span> <span data-ttu-id="1cc15-156">若為來賓，您必須先將其邀請，才能指派群組。</span><span class="sxs-lookup"><span data-stu-id="1cc15-156">If they are a guest, you must invite them before you can assign the group.</span></span>
6.  <span data-ttu-id="1cc15-157">選取底部的 [ **選取** ]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-157">Select **Select** at the bottom.</span></span>

> [!NOTE]
> <span data-ttu-id="1cc15-158">目前不支援角色指派的嵌套安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1cc15-158">Nesting security groups for role assignment is not currently supported.</span></span> 

### <a name="assigning-built-in-roles-to-groups"></a><span data-ttu-id="1cc15-159">將內建角色指派給群組</span><span class="sxs-lookup"><span data-stu-id="1cc15-159">Assigning built-in roles to groups</span></span>

<span data-ttu-id="1cc15-160">如果您需要將一個或多個內建角色指派給現有的群組，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1cc15-160">If you need to assign one or more of the built-in roles to a existing group, follow these steps:</span></span>
1. <span data-ttu-id="1cc15-161">移至 [portal.azure.com](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="1cc15-161">Go to [portal.azure.com](https://portal.azure.com/).</span></span>
2. <span data-ttu-id="1cc15-162">搜尋及開啟 **企業應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1cc15-162">Search for and open **Enterprise applications**.</span></span>
3. <span data-ttu-id="1cc15-163">將 **應用程式類型** 篩選變更為 _Microsoft 應用程式_ ，然後 **選取 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-163">Change the **Application type** filter to _Microsoft Applications_ and, then select **Apply**.</span></span>
4. <span data-ttu-id="1cc15-164">搜尋並選取 _新式的 Workplace 客戶 APIs_。</span><span class="sxs-lookup"><span data-stu-id="1cc15-164">Search for and select _Modern Workplace Customer APIs_.</span></span>
5. <span data-ttu-id="1cc15-165">從左側窗格中選取 [ **使用者和群組** ]，然後選取 [ **+ 新增使用者/群組**]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-165">Select **Users and groups** from the pane on the left side, and then select **+ Add user/group**.</span></span>
6. <span data-ttu-id="1cc15-166">從 **使用者和群組** 搜尋您想要的群組。</span><span class="sxs-lookup"><span data-stu-id="1cc15-166">Search for the group you want from **Users and groups**.</span></span>
7. <span data-ttu-id="1cc15-167">在 [ **選取角色**] 中搜尋適用的角色，然後選取該角色。</span><span class="sxs-lookup"><span data-stu-id="1cc15-167">Search for the applicable role from **Select a role**, and then select it.</span></span>
8. <span data-ttu-id="1cc15-168">選取 [ **指派**]。</span><span class="sxs-lookup"><span data-stu-id="1cc15-168">Select **Assign**.</span></span>
 
