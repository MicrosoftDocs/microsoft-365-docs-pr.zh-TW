---
title: 管理 Microsoft 365 群組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 瞭解如何管理 Microsoft 365 群組。
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911004"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="d7d8e-103">管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="d7d8e-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="d7d8e-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d7d8e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d7d8e-105">您可以根據您的設定，以數種不同的方式管理 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="d7d8e-106">您可以在「 [Microsoft 365 系統管理中心](../admin/add-users/index.yml)」、「PowerShell」、Active Directory 網域服務 (AD DS) 或[Azure Active Directory (Azure AD) 系統管理中心](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)] 中管理使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="d7d8e-107">規劃管理群組的位置和方式</span><span class="sxs-lookup"><span data-stu-id="d7d8e-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="d7d8e-108">您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="d7d8e-109">這兩個整體模型為雲端且混合式。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="d7d8e-110">僅雲端</span><span class="sxs-lookup"><span data-stu-id="d7d8e-110">Cloud-only</span></span>

<span data-ttu-id="d7d8e-111">您可以使用下列方式建立及管理群組：</span><span class="sxs-lookup"><span data-stu-id="d7d8e-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="d7d8e-112">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7d8e-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="d7d8e-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7d8e-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d7d8e-114">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7d8e-114">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="d7d8e-115">混合式</span><span class="sxs-lookup"><span data-stu-id="d7d8e-115">Hybrid</span></span>

<span data-ttu-id="d7d8e-116">ad ds 群組與從 AD ds Microsoft 365 同步處理，所以您必須使用內部部署 AD ds 工具來管理這些群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="d7d8e-117">您也可以建立和管理獨立于 AD DS 群組的 Azure AD 群組，但可包含 AD DS 中的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="d7d8e-118">在此情況下，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="d7d8e-118">In this case, you can use:</span></span>

- [<span data-ttu-id="d7d8e-119">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7d8e-119">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="d7d8e-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7d8e-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d7d8e-121">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7d8e-121">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="d7d8e-122">允許使用者建立及管理自己的群組</span><span class="sxs-lookup"><span data-stu-id="d7d8e-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="d7d8e-123">Azure AD 允許群組擁有者管理的群組，而不是由 IT 系統管理員來管理。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="d7d8e-124">此功能也稱為 *自助服務群組管理*，允許未獲指派系統管理角色的群組擁有者建立和管理安全群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="d7d8e-p105">使用者可要求安全性群組的成員資格，該要求會傳送給群組擁有者，而不是 IT 系統管理員。這可將群組成員資格的每日控制委派給小組、專案或業務擁有者，他們了解群組的業務使用，可以管理成員資格。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="d7d8e-127">自助群組管理功能僅適用於 Azure AD 安全性和 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="d7d8e-128">這不適用於已啟用郵件功能的群組、通訊群組清單或任何已從 AD DS 同步處理的群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="d7d8e-129">如需詳細資訊，請參閱[設定 Azure AD 群組自助管理的指示](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-129">For more information, see the [instructions to configure an Azure AD group for self-service management](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="d7d8e-130">設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="d7d8e-130">Set up dynamic group membership</span></span>

<span data-ttu-id="d7d8e-131">Azure AD 支援設定一系列規則，自動將使用者帳戶新增或移除為 Azure AD 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="d7d8e-132">這稱為 *動態群組成員資格*。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="d7d8e-133">規則會以使用者帳戶屬性為基礎，例如部門或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="d7d8e-134">以下是規則適用的方式：</span><span class="sxs-lookup"><span data-stu-id="d7d8e-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="d7d8e-135">如果新的使用者帳戶與群組的所有規則相符，就會成為成員。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="d7d8e-136">如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="d7d8e-137">若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="d7d8e-138">如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="d7d8e-p108">若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="d7d8e-141">請參閱[指示以建立及設定動態 Azure AD 群組的規則](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="d7d8e-142">設定自動授權</span><span class="sxs-lookup"><span data-stu-id="d7d8e-142">Set up automatic licensing</span></span>

<span data-ttu-id="d7d8e-143">您可以在 Azure AD 中設定安全性群組，以自動將一組訂閱的授權指派給群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="d7d8e-144">這稱為 *群組型授權*。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="d7d8e-145">如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="d7d8e-146">針對 Microsoft 365 企業版，您將設定 Azure AD 安全性群組，以指派適當的 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="d7d8e-147">請確定您有足夠的授權可供所有群組成員使用。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="d7d8e-148">如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="d7d8e-149">您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定以群組為基礎的授權。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="d7d8e-150">如需詳細資訊，請參閱 [在 AZURE AD 中以群組為基礎的授權基礎](/azure/active-directory/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-150">For more information, see [Group-based licensing basics in Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="d7d8e-151">請參閱 [指示，設定 Azure 安全性群組的群組型授權](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d7d8e-151">See the [instructions to configure group-based licensing for an Azure security group](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>