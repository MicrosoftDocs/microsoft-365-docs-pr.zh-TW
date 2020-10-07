---
title: 管理 Microsoft 365 身分識別管理
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
description: 深入瞭解如何使用 Microsoft 365 身分識別管理功能。
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370343"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="fc76c-103">管理 Microsoft 365 身分識別管理</span><span class="sxs-lookup"><span data-stu-id="fc76c-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="fc76c-104">身分識別治理就是保護、監控及稽核對關鍵資產的存取權，同時確保員工生產力。</span><span class="sxs-lookup"><span data-stu-id="fc76c-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="fc76c-105">例如，您可以使用身分識別治理來確保適當的使用者具有適當資源的存取權，並隨著時間判斷該存取權是否有所變更。</span><span class="sxs-lookup"><span data-stu-id="fc76c-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="fc76c-106">如需詳細資訊，請參閱 [Azure Active Directory (AZURE AD) 的身分識別管理 ](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。</span><span class="sxs-lookup"><span data-stu-id="fc76c-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="fc76c-107">設定 Azure AD 存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="fc76c-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="fc76c-108">Azure AD access 評論可讓您複查使用者的存取權，以確保只有正確的人員繼續存取。</span><span class="sxs-lookup"><span data-stu-id="fc76c-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="fc76c-109">例如：</span><span class="sxs-lookup"><span data-stu-id="fc76c-109">For example:</span></span>

- <span data-ttu-id="fc76c-110">當組織加入新員工時，您必須確保他們具有適當的存取權，以具有生產力。</span><span class="sxs-lookup"><span data-stu-id="fc76c-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="fc76c-111">當該員工轉移至其他小組、位置或部門時，您必須確保在必要時移除其對先前小組、位置或部門的存取權。</span><span class="sxs-lookup"><span data-stu-id="fc76c-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="fc76c-112">當該員工或來賓離開組織時，您必須確保會移除其存取權。</span><span class="sxs-lookup"><span data-stu-id="fc76c-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="fc76c-113">若您的組織受限於安全性稽核來判斷使用者帳戶是否擁有太大的存取權 (如果違反產業或地區法規，則可能會受到處罰)，則這一點特別重要。</span><span class="sxs-lookup"><span data-stu-id="fc76c-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="fc76c-114">如需詳細資訊，請參閱 [存取權考核的概述](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="fc76c-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="fc76c-115">請參閱下列文章來設定不同類型的存取權檢閱：</span><span class="sxs-lookup"><span data-stu-id="fc76c-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="fc76c-116">群組和應用程式</span><span class="sxs-lookup"><span data-stu-id="fc76c-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="fc76c-117">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="fc76c-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="fc76c-118">Azure 資源角色</span><span class="sxs-lookup"><span data-stu-id="fc76c-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="fc76c-119">設定 Azure AD 的權利管理</span><span class="sxs-lookup"><span data-stu-id="fc76c-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="fc76c-120">Wiht Azure AD 權利管理，您可以自動化存取要求工作流程、存取指派、評論和到期，以管理身分識別和存取生命週期。</span><span class="sxs-lookup"><span data-stu-id="fc76c-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="fc76c-121">您的員工需要存取各種群組、應用程式和網站，以執行其工作。</span><span class="sxs-lookup"><span data-stu-id="fc76c-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="fc76c-122">管理此存取可能具有挑戰性，因為需要變更、新增新的應用程式，或使用者需要其他存取權。</span><span class="sxs-lookup"><span data-stu-id="fc76c-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="fc76c-123">當您與其他組織共同作業時，可能不知道其他組織中的誰需要存取組織的資源，而外部使用者則不會知道組織所使用的應用程式、群組或網站。</span><span class="sxs-lookup"><span data-stu-id="fc76c-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="fc76c-124">Azure AD 權利管理可協助您更有效率地管理內部及外部使用者對群組、應用程式和 SharePoint 網站的存取。</span><span class="sxs-lookup"><span data-stu-id="fc76c-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="fc76c-125">如需詳細資訊，請參閱 [AZURE AD 權利管理的概述](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="fc76c-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
