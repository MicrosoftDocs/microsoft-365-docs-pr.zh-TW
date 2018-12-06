---
title: 步驟 15：設定動態群組成員資格
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解自動群組成員資格並根據帳戶屬性進行設定。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866635"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="31d29-103">步驟 15：設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="31d29-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="31d29-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="31d29-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="31d29-p101">在本步驟中，您將建立一系列的規則，這些規則會自動新增或移除使用者帳戶作為 Azure AD 群組成員的身分。這稱為*動態群組成員資格*。這些規則根據使用者帳戶屬性 (例如部門或國家/地區) 而定。</span><span class="sxs-lookup"><span data-stu-id="31d29-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="31d29-108">以下是規則適用的方式：</span><span class="sxs-lookup"><span data-stu-id="31d29-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="31d29-109">如果新的使用者帳戶與群組的所有規則相符，就會成為成員。</span><span class="sxs-lookup"><span data-stu-id="31d29-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="31d29-110">如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="31d29-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="31d29-111">若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="31d29-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="31d29-112">如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。</span><span class="sxs-lookup"><span data-stu-id="31d29-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="31d29-p102">若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="31d29-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="31d29-115">請參閱[指示以建立及設定動態 Azure AD 群組的規則](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="31d29-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="31d29-116">此步驟的結果如下：</span><span class="sxs-lookup"><span data-stu-id="31d29-116">The results of this step are:</span></span>

- <span data-ttu-id="31d29-117">可針對動態成員資格而設定的一組 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="31d29-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="31d29-118">針對每個動態群組的一組規則</span><span class="sxs-lookup"><span data-stu-id="31d29-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="31d29-120">測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="31d29-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="31d29-121">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-dyn-groups)。</span><span class="sxs-lookup"><span data-stu-id="31d29-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="31d29-122">下一步</span><span class="sxs-lookup"><span data-stu-id="31d29-122">Next step</span></span>

[<span data-ttu-id="31d29-123">識別基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="31d29-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
