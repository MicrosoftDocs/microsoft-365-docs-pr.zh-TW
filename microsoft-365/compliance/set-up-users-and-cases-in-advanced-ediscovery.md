---
title: 在高級電子檔探索中設定使用者和案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 瞭解如何設定使用者角色、建立案例，以及在高級 eDiscovery 中將使用者指派給案例。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e24354960b517815bef3cf498822d6ce9fd9dbe
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936740"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="7c06c-103">在高級 eDiscovery （古典）中設定使用者和案例</span><span class="sxs-lookup"><span data-stu-id="7c06c-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="7c06c-104">本主題說明如何針對高級 eDiscovery （古典）設定使用者和案例。</span><span class="sxs-lookup"><span data-stu-id="7c06c-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7c06c-105">隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="7c06c-106">如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="7c06c-107">進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。</span><span class="sxs-lookup"><span data-stu-id="7c06c-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="7c06c-108">若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="7c06c-109">設定使用者和案例的需求</span><span class="sxs-lookup"><span data-stu-id="7c06c-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="7c06c-110">在 [Advanced eDiscovery] 中設定案例和使用者之前，需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="7c06c-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="7c06c-111">若要使用高級電子檔探索來分析使用者的資料，則必須將 Office 365 E5 授權指派給使用者（資料的保管人）。</span><span class="sxs-lookup"><span data-stu-id="7c06c-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="7c06c-112">或者，您可以將高級 eDiscovery 獨立授權指派給使用 Office 365 E1 或 E3 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c06c-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="7c06c-113">獲指派案例的系統管理員和合規性監察官，以及使用高級 eDiscovery 來分析資料，不需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7c06c-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="7c06c-114">您必須是安全性與合規性中心內 eDiscovery 管理員角色群組的成員， &amp; 才可建立 eDiscovery 案例並新增成員。</span><span class="sxs-lookup"><span data-stu-id="7c06c-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="7c06c-115">若要在安全性與合規性中心將自己新增至 eDiscovery 管理員角色群組 &amp; ，您必須是組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7c06c-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="7c06c-116">如果您不是全域系統管理員，則必須要求全域系統管理員將您新增至 eDiscovery 管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="7c06c-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="7c06c-117">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7c06c-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="7c06c-118">Microsoft 365 安全性與 &amp; 合規性中心的許可權</span><span class="sxs-lookup"><span data-stu-id="7c06c-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="7c06c-119">在 Microsoft 365 安全性與 &amp; 合規性中心指派 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="7c06c-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="7c06c-120">步驟1：指派使用者的 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="7c06c-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="7c06c-121">第一步是在安全性與合規性中心指派要求許可權， &amp; 讓他們可以新增為 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7c06c-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="7c06c-122">在安全性與合規性中心內將使用者新增為案例的成員後 &amp; ，他們就能在「高級 eDiscovery」中存取案例。</span><span class="sxs-lookup"><span data-stu-id="7c06c-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7c06c-123">若要指派使用者必要的許可權，使其可以新增為 eDiscovery 案例的成員，請參閱[Microsoft 365 安全性與 &amp; 合規性中心的 eDiscovery 案例中的](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)步驟1。</span><span class="sxs-lookup"><span data-stu-id="7c06c-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="7c06c-124">步驟2：建立電子檔探索案例並新增成員</span><span class="sxs-lookup"><span data-stu-id="7c06c-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="7c06c-125">下一步是在安全性 & 合規性中心建立新的 eDiscovery 案例，並新增成員。</span><span class="sxs-lookup"><span data-stu-id="7c06c-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="7c06c-126">案例的成員就能在「高級 eDiscovery」中存取案例。</span><span class="sxs-lookup"><span data-stu-id="7c06c-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="7c06c-127">若要建立新的 eDiscovery 案例，請參閱[核心 eDiscovery 開始使用](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)的步驟3。</span><span class="sxs-lookup"><span data-stu-id="7c06c-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="7c06c-128">若要將成員新增至 eDiscovery 案例，請參閱[核心 EDiscovery 快速入門中的](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)步驟4</span><span class="sxs-lookup"><span data-stu-id="7c06c-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7c06c-129">步驟3：在「高級電子檔探索」中開始案例</span><span class="sxs-lookup"><span data-stu-id="7c06c-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7c06c-130">在您建立 eDiscovery 案例並新增成員之後，您（或任何案例的任何成員）都可以在高級 eDiscovery 中存取對應案例。</span><span class="sxs-lookup"><span data-stu-id="7c06c-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="7c06c-131">若要在高級 eDiscovery 中存取案例，請參閱[在「高級 ediscovery」中存取案例](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7c06c-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="7c06c-132">See also</span></span>

[<span data-ttu-id="7c06c-133">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="7c06c-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7c06c-134">準備資料以供高級 eDiscovery （經典）</span><span class="sxs-lookup"><span data-stu-id="7c06c-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 
