---
title: 步驟 7：設定身分識別治理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 Azure AD 租用戶的身分識別治理。
ms.openlocfilehash: a965b74afc680c2ff506e0fc2ddebc280ee312a1
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982906"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="31c5b-103">步驟 7：設定身分識別治理</span><span class="sxs-lookup"><span data-stu-id="31c5b-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="31c5b-104">身分識別治理就是保護、監控及稽核對關鍵資產的存取權，同時確保員工生產力。</span><span class="sxs-lookup"><span data-stu-id="31c5b-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="31c5b-105">例如，您可以使用身分識別治理來確保適當的使用者具有適當資源的存取權，並隨著時間判斷該存取權是否有所變更。</span><span class="sxs-lookup"><span data-stu-id="31c5b-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="31c5b-106">如需 Azure Active Directory (Azure AD) 身分識別治理的詳細資訊，請參閱[此文章](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。</span><span class="sxs-lookup"><span data-stu-id="31c5b-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="31c5b-107">設定 Azure AD 存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="31c5b-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="31c5b-108">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="31c5b-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="31c5b-109">在此步驟中，您將設定 Azure AD 存取權檢閱，這可讓您檢閱使用者的存取權，以確保只有適當的人員可以持續存取。</span><span class="sxs-lookup"><span data-stu-id="31c5b-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="31c5b-110">例如：</span><span class="sxs-lookup"><span data-stu-id="31c5b-110">For example:</span></span>

- <span data-ttu-id="31c5b-111">當組織加入新員工時，您必須確保他們具有適當的存取權，以具有生產力。</span><span class="sxs-lookup"><span data-stu-id="31c5b-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="31c5b-112">當該員工轉移至其他小組、位置或部門時，您必須確保在必要時移除其對先前小組、位置或部門的存取權。</span><span class="sxs-lookup"><span data-stu-id="31c5b-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="31c5b-113">當該員工或來賓離開組織時，您必須確保會移除其存取權。</span><span class="sxs-lookup"><span data-stu-id="31c5b-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="31c5b-114">若您的組織受限於安全性稽核來判斷使用者帳戶是否擁有太大的存取權 (如果違反產業或地區法規，則可能會受到處罰)，則這一點特別重要。</span><span class="sxs-lookup"><span data-stu-id="31c5b-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="31c5b-115">如需 Azure AD 存取權檢閱的詳細資訊，請參閱[此文章](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="31c5b-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="31c5b-116">請參閱下列文章來設定不同類型的存取權檢閱：</span><span class="sxs-lookup"><span data-stu-id="31c5b-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="31c5b-117">群組和應用程式</span><span class="sxs-lookup"><span data-stu-id="31c5b-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="31c5b-118">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="31c5b-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="31c5b-119">Azure 資源角色</span><span class="sxs-lookup"><span data-stu-id="31c5b-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="31c5b-120">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="31c5b-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="31c5b-121">下一步</span><span class="sxs-lookup"><span data-stu-id="31c5b-121">Next step</span></span>

[<span data-ttu-id="31c5b-122">識別基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="31c5b-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

