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
ms.openlocfilehash: c2a5b7f837d6c43369301820019732ca3aef83bf
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053844"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="6001b-104">存取管理員入口網站</span><span class="sxs-lookup"><span data-stu-id="6001b-104">Access the admin portal</span></span>

<span data-ttu-id="6001b-105">您的 Microsoft Managed 桌面服務閘道是 [Microsoft 端點管理員](https://endpoint.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="6001b-105">Your gateway to the Microsoft Managed Desktop service is [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="6001b-106">如果您不熟悉此入口網站的裝置管理功能，請參閱 [Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。</span><span class="sxs-lookup"><span data-stu-id="6001b-106">If you are unfamiliar with the capabilities of this portal for device management, see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

> [!NOTE]
> <span data-ttu-id="6001b-107">在 [Microsoft 端點管理員](https://endpoint.microsoft.com/) 中，支援下列瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="6001b-107">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) the following browsers are supported:</span></span>
> - <span data-ttu-id="6001b-108">Microsoft Edge (最新版本) </span><span class="sxs-lookup"><span data-stu-id="6001b-108">Microsoft Edge (latest version)</span></span>
> - <span data-ttu-id="6001b-109">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="6001b-109">Microsoft Internet Explorer 11</span></span>
> - <span data-ttu-id="6001b-110">Safari (最新版本，僅限 Mac) </span><span class="sxs-lookup"><span data-stu-id="6001b-110">Safari (latest version, Mac only)</span></span>
> - <span data-ttu-id="6001b-111">Chrome (最新版本) </span><span class="sxs-lookup"><span data-stu-id="6001b-111">Chrome (latest version)</span></span>
> - <span data-ttu-id="6001b-112">Firefox (最新版本) </span><span class="sxs-lookup"><span data-stu-id="6001b-112">Firefox (latest version)</span></span>

<span data-ttu-id="6001b-113">您的管理帳戶需要特定許可權，才能存取 Azure 入口網站或 Microsoft 端點管理員中的 Microsoft 受管理桌面系統管理功能。</span><span class="sxs-lookup"><span data-stu-id="6001b-113">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop administrative features in either Azure portal or Microsoft Endpoint Manager.</span></span> <span data-ttu-id="6001b-114">您可以使用以角色為基礎的存取控制 (RBAC) ，管理組織內這些功能的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="6001b-114">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="6001b-115">有幾個 Azure Active Directory (Azure AD) 系統管理員角色和內建自訂角色，可為 Microsoft Managed Desktop Admin 入口網站中的不同功能提供更細微的控制。</span><span class="sxs-lookup"><span data-stu-id="6001b-115">Several Azure Active Directory (Azure AD) administrator roles and built-in custom roles are available to provide more granular control to different features within the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="6001b-116">如需 Azure Active Directory 角色的詳細資訊，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="6001b-116">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="6001b-117">與適用于各種 Microsoft 產品和服務的 Azure AD 系統管理員角色不同，自訂角色是 Microsoft 受管理的桌面所特有的，只會保證此服務的系統管理功能存取權。</span><span class="sxs-lookup"><span data-stu-id="6001b-117">Unlike Azure AD administrator roles that apply to various Microsoft products and services, custom roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service.</span></span> <span data-ttu-id="6001b-118">管理員可以個別或搭配使用 Azure AD 系統管理員角色，將自訂角色指派給使用者，以將 Microsoft 管理的桌面許可權新增至現有的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="6001b-118">Admins can assign custom roles to users individually or in combination with Azure AD administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.</span></span>

<span data-ttu-id="6001b-119">您可以指派下列每個角色，以提供不同的存取層級：</span><span class="sxs-lookup"><span data-stu-id="6001b-119">Each of the roles below can be assigned to provide different levels of access:</span></span>

|<span data-ttu-id="6001b-120">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="6001b-120">Azure AD role</span></span>  |<span data-ttu-id="6001b-121">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="6001b-121">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="6001b-122">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-122">Global Administrator</span></span>     | <span data-ttu-id="6001b-123">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中 **所有功能的讀取和寫入權限** 。</span><span class="sxs-lookup"><span data-stu-id="6001b-123">Admins with this role will have **read and write permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="6001b-124">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="6001b-124">Global Reader</span></span>     | <span data-ttu-id="6001b-125">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="6001b-125">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="6001b-126">Intune 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-126">Intune Service Administrator</span></span>     |  <span data-ttu-id="6001b-127">具有此角色的系統管理員具有與 Microsoft Managed Desktop Admin 入口網站中的 **安全性無關的功能的讀取和寫入權限** 。</span><span class="sxs-lookup"><span data-stu-id="6001b-127">Admins with this role will have **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="6001b-128">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-128">Service Support Administrator</span></span>     | <span data-ttu-id="6001b-129">具有此角色的系統管理員對與安全性和寫入權限不相關的功能，對 Microsoft Managed Desktop Admin 入口網站中 **管理支援要求** 的 **功能具有唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="6001b-129">Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="6001b-130">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-130">Security Admin</span></span> | <span data-ttu-id="6001b-131">具有此角色的系統管理員對管理員入口網站中 Microsoft 受管理的電腦具有 **安全性相關功能的** 所有功能和寫入權限，具有 **唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="6001b-131">Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the Admin portal.</span></span> |
|<span data-ttu-id="6001b-132">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="6001b-132">Security Reader</span></span> |<span data-ttu-id="6001b-133">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="6001b-133">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="6001b-134">只有全域系統管理員角色具有在 Microsoft Managed Desktop 中 *註冊* 您的組織所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="6001b-134">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="6001b-135">請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。</span><span class="sxs-lookup"><span data-stu-id="6001b-135">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="6001b-136">在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的 *最低* 許可權。</span><span class="sxs-lookup"><span data-stu-id="6001b-136">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

 
|<span data-ttu-id="6001b-137">自訂角色</span><span class="sxs-lookup"><span data-stu-id="6001b-137">Custom role</span></span>  |<span data-ttu-id="6001b-138">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="6001b-138">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="6001b-139">Microsoft 受管理的桌面服務管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-139">Microsoft Managed Desktop Service Administrator</span></span>  | <span data-ttu-id="6001b-140">指派給使用者時，此角色可讓系統管理員 **讀取和寫入權限給** 與 Microsoft Managed Desktop admin 入口網站中的安全性無關的功能。</span><span class="sxs-lookup"><span data-stu-id="6001b-140">When assigned to a user, this role gives the admin **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>  |
|<span data-ttu-id="6001b-141">Microsoft 受管理的桌面服務讀取器</span><span class="sxs-lookup"><span data-stu-id="6001b-141">Microsoft Managed Desktop Service Reader</span></span> | <span data-ttu-id="6001b-142">指派給使用者時，此角色可讓系統管理員對與 Microsoft Managed Desktop Admin 入口網站中的安全性無關的 **功能具有唯讀許可權** 。</span><span class="sxs-lookup"><span data-stu-id="6001b-142">When assigned to a user, this role gives the admin **read-only permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span> |
|<span data-ttu-id="6001b-143">Microsoft 受管理的桌面安全性管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-143">Microsoft Managed Desktop Security Manager</span></span> |<span data-ttu-id="6001b-144">指派給使用者時，此角色只會讓系統管理員 **讀取和寫入權限，只會針對** Microsoft Managed Desktop admin 入口網站中的安全性相關功能。</span><span class="sxs-lookup"><span data-stu-id="6001b-144">When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the Microsoft Managed Desktop Admin portal.</span></span>   |

> [!NOTE]
> <span data-ttu-id="6001b-145">安全性功能包括安全性相關的通訊、安全性連絡人的管理、安全性相關支援要求的管理，以及與安全性相關的報表存取。</span><span class="sxs-lookup"><span data-stu-id="6001b-145">Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.</span></span> 

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="6001b-146">將角色指派給系統管理員</span><span class="sxs-lookup"><span data-stu-id="6001b-146">Assigning roles to administrators</span></span>

<span data-ttu-id="6001b-147">如果您需要協助指派 Azure Active Directory 角色，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="6001b-147">If you need help with assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="6001b-148">為了便於管理內建角色，每個自訂角色 (都有一個安全性群組，例如「新式工作場所角色–安全性管理員」 ) 。</span><span class="sxs-lookup"><span data-stu-id="6001b-148">To make it easy to manage built-in roles, there is a security group for each custom role (for example, “Modern Workplace Roles – Security Manager”).</span></span> <span data-ttu-id="6001b-149">若要將使用者指派給其中一個安全性群組，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6001b-149">To assign users to one of the security groups, follow these steps:</span></span>
1.  <span data-ttu-id="6001b-150">請移至 Microsoft 端點管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="6001b-150">Go the Microsoft Endpoint Manager portal.</span></span>
2.  <span data-ttu-id="6001b-151">選取左側的 [ **群組** ]。</span><span class="sxs-lookup"><span data-stu-id="6001b-151">Select **Groups** on the left side.</span></span>
3.  <span data-ttu-id="6001b-152">搜尋 **新式的工作區角色**，然後選取與您要指派之角色相關聯的群組。</span><span class="sxs-lookup"><span data-stu-id="6001b-152">Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.</span></span> 
4.  <span data-ttu-id="6001b-153">選取左側的 [ **成員** ]，然後選取 [+ 在命令列 **新增成員** ]。</span><span class="sxs-lookup"><span data-stu-id="6001b-153">Select **Members** on the left side, and then select **+ Add members** on the command bar.</span></span>
5.  <span data-ttu-id="6001b-154">輸入要新增之人員的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6001b-154">Enter the email of the person being added.</span></span> <span data-ttu-id="6001b-155">若為來賓，您必須先將其邀請，才能指派群組。</span><span class="sxs-lookup"><span data-stu-id="6001b-155">If they are a guest, you must invite them before you can assign the group.</span></span>
6.  <span data-ttu-id="6001b-156">選取底部的 [ **選取** ]。</span><span class="sxs-lookup"><span data-stu-id="6001b-156">Select **Select** at the bottom.</span></span>

> [!NOTE]
> <span data-ttu-id="6001b-157">目前不支援角色指派的嵌套安全性群組。</span><span class="sxs-lookup"><span data-stu-id="6001b-157">Nesting security groups for role assignment is not currently supported.</span></span> 
