---
title: 步驟 5：使用群組進行管理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 您可以使用群組來自動管理某些系統管理工作。
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067270"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="d1d57-103">步驟 5：使用群組進行管理</span><span class="sxs-lookup"><span data-stu-id="d1d57-103">Step 5: Use groups for management</span></span>

![階段 2 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="d1d57-105">允許使用者建立及管理自己的群組</span><span class="sxs-lookup"><span data-stu-id="d1d57-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="d1d57-106">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="d1d57-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d1d57-107">在本節中，您將識別可由群組擁有者而非 IT 系統管理員管理的Azure Active Directory (Azure AD) 群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="d1d57-108">此功能也稱為*自助服務群組管理*，允許未獲指派系統管理角色的群組擁有者建立和管理安全群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="d1d57-p102">使用者可要求安全性群組的成員資格，該要求會傳送給群組擁有者，而不是 IT 系統管理員。這可將群組成員資格的每日控制委派給小組、專案或業務擁有者，他們了解群組的業務使用，可以管理成員資格。</span><span class="sxs-lookup"><span data-stu-id="d1d57-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="d1d57-111">自助群組管理功能僅適用於 Azure AD 安全性和 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="d1d57-112">它不適用於已啟用郵件功能的群組、通訊群組清單或已從內部部署 Active Directory 網域服務 (AD DS) 同步處理的任何群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="d1d57-113">如需詳細資訊，請參閱[設定 Azure AD 群組自助管理的指示](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="d1d57-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="d1d57-114">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-self-service-groups)。</span><span class="sxs-lookup"><span data-stu-id="d1d57-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="d1d57-115">設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="d1d57-115">Set up dynamic group membership</span></span>

<span data-ttu-id="d1d57-116">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="d1d57-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d1d57-117">在這一節中，您將建立一系列規則，來自動新增或移除作為 Azure AD 群組成員的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d1d57-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="d1d57-118">這稱為*動態群組成員資格*。</span><span class="sxs-lookup"><span data-stu-id="d1d57-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="d1d57-119">規則會以使用者帳戶屬性為基礎，例如部門或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="d1d57-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="d1d57-120">以下是規則適用的方式：</span><span class="sxs-lookup"><span data-stu-id="d1d57-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="d1d57-121">如果新的使用者帳戶與群組的所有規則相符，就會成為成員。</span><span class="sxs-lookup"><span data-stu-id="d1d57-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="d1d57-122">如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d1d57-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="d1d57-123">若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="d1d57-124">如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。</span><span class="sxs-lookup"><span data-stu-id="d1d57-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="d1d57-p105">若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="d1d57-127">請參閱[指示以建立及設定動態 Azure AD 群組的規則](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d1d57-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="d1d57-128">這一節的結果如下：</span><span class="sxs-lookup"><span data-stu-id="d1d57-128">The results of this section are:</span></span>

- <span data-ttu-id="d1d57-129">可針對動態成員資格而設定的一組 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="d1d57-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="d1d57-130">針對每個動態群組的一組規則</span><span class="sxs-lookup"><span data-stu-id="d1d57-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d1d57-132">測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="d1d57-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d1d57-133">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-dyn-groups)。</span><span class="sxs-lookup"><span data-stu-id="d1d57-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="d1d57-134">設定自動授權</span><span class="sxs-lookup"><span data-stu-id="d1d57-134">Set up automatic licensing</span></span>

<span data-ttu-id="d1d57-135">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="d1d57-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d1d57-136">在這一節中，您將在 Azure AD 中設定安全性群組，以自動將一組訂閱中的授權指派給該群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="d1d57-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="d1d57-137">這稱為*群組型授權*。</span><span class="sxs-lookup"><span data-stu-id="d1d57-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="d1d57-138">如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="d1d57-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="d1d57-139">針對 Microsoft 365 企業版，您將設定 Azure AD 安全性群組，以指派適當的 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="d1d57-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="d1d57-140">請確定您有足夠的授權可供所有群組成員使用。</span><span class="sxs-lookup"><span data-stu-id="d1d57-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="d1d57-141">如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="d1d57-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="d1d57-142">您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定*以群組為基礎的授權*。</span><span class="sxs-lookup"><span data-stu-id="d1d57-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="d1d57-143">查看 [Azure Active Directory 中以群組為基礎之授權基本概念](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="d1d57-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="d1d57-144">請參閱「[為 Azure 安全性群組設定以群組為基礎之授權的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」。</span><span class="sxs-lookup"><span data-stu-id="d1d57-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="d1d57-145">這一節的結果如下：</span><span class="sxs-lookup"><span data-stu-id="d1d57-145">The results of this section are:</span></span>

- <span data-ttu-id="d1d57-146">您已識別出哪些安全性群組適用於以群組為基礎的授權。</span><span class="sxs-lookup"><span data-stu-id="d1d57-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="d1d57-147">您已為以群組為基礎的授權設定這些群組。</span><span class="sxs-lookup"><span data-stu-id="d1d57-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d1d57-149">測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="d1d57-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d1d57-150">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-group-license)。</span><span class="sxs-lookup"><span data-stu-id="d1d57-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![步驟 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="d1d57-152">設定身分識別治理</span><span class="sxs-lookup"><span data-stu-id="d1d57-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
