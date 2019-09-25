---
title: 在 Office 365 高级电子数据展示中设置用户和案例
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、创建案例以及将用户分配给 Office 365 高级电子数据展示中的案例。  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077512"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d4a3e-103">在 Office 365 高级电子数据展示中设置用户和案例</span><span class="sxs-lookup"><span data-stu-id="d4a3e-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="d4a3e-104">本主题介绍如何为 Office 365 高级电子数据展示设置用户和案例。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4a3e-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="d4a3e-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="d4a3e-107">Prerequisites</span></span>

<span data-ttu-id="d4a3e-108">在高级电子数据展示中设置案例和用户之前，需要以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4a3e-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="d4a3e-109">要使用高级电子数据展示分析用户的数据，必须为该用户（数据的保管人）分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="d4a3e-110">或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="d4a3e-111">分配给案例并使用高级电子数据展示分析数据的管理员和合规官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="d4a3e-112">您必须是 Office 365 安全&amp;合规性中心中的电子数据展示管理器角色组的成员，才能创建电子数据展示案例并将其成员添加到该案例中。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="d4a3e-113">要将自己添加到安全&amp;合规性中心中的电子数据展示管理器角色组，您必须是 Office 365 组织中的全球管理员。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="d4a3e-114">如果您不是全局管理员，则必须要求全局管理员将您添加到电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="d4a3e-115">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d4a3e-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="d4a3e-116">Microsoft 365 安全&amp;合规性中心的权限</span><span class="sxs-lookup"><span data-stu-id="d4a3e-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="d4a3e-117">在 Microsoft 365 安全&amp;合规性中心分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="d4a3e-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="d4a3e-118">第 1 步：分配用户电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="d4a3e-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="d4a3e-119">第一步是在安全&amp;合规性中心向用户分配需求权限，以便他们可以将我添加为电子数据展示案例的成员。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="d4a3e-120">将用户添加为安全&amp;合规性中心案例的成员后，他们将能够在高级电子数据展示中访问该案例。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="d4a3e-121">要为用户分配必要的权限，以便他们可以添加为电子数据展示案例的成员，请参阅[Microsoft 365&amp;安全合规性中心中的电子数据展示案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步骤 1。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="d4a3e-122">第 2 步：创建电子数据展示案例并添加成员</span><span class="sxs-lookup"><span data-stu-id="d4a3e-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="d4a3e-123">下一步是在安全&amp;合规性中心创建新的电子数据展示案例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="d4a3e-124">然后，案例的成员将能够访问高级电子数据展示中的案件。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="d4a3e-125">要创建新的电子数据展示案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-2-create-a-new-case)中的步骤 2。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="d4a3e-126">要将成员添加到电子数据展示案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-3-add-members-to-a-case)中的步骤 3</span><span class="sxs-lookup"><span data-stu-id="d4a3e-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="d4a3e-127">第 3 步：在高级电子数据展示中进行案例展示</span><span class="sxs-lookup"><span data-stu-id="d4a3e-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="d4a3e-128">创建电子数据展示案例并添加成员后，您（或案例中的任何成员）可以访问高级电子数据展示中的相应案例。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="d4a3e-129">要访问高级电子数据展示中的案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)中的步骤 8。</span><span class="sxs-lookup"><span data-stu-id="d4a3e-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4a3e-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4a3e-130">See also</span></span>

[<span data-ttu-id="d4a3e-131">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="d4a3e-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d4a3e-132">準備安裝</span><span class="sxs-lookup"><span data-stu-id="d4a3e-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
