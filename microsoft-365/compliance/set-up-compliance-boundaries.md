---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合规性边界在 Office 365 组织中创建逻辑边界，以控制电子数据展示经理可以搜索的用户内容位置。 合规性边界使用搜索权限筛选（也称为合规性安全筛选器）来控制特定用户可以搜索的邮箱、SharePoint 站点和 OneDrive 帐户。
ms.openlocfilehash: 1e87926910ad7dd356696368ad6759bfacfe37c2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077391"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="7c0c6-104">設定 Office 365 中電子文件探索調查的合規性界限</span><span class="sxs-lookup"><span data-stu-id="7c0c6-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="7c0c6-105">合规性边界在 Office 365 组织内创建逻辑边界，控制电子数据展示经理可以搜索的用户内容位置（如邮箱、SharePoint 站点和 OneDrive 帐户）。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-105">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search.</span></span> <span data-ttu-id="7c0c6-106">此外，合规性边界控制谁可以访问用于管理组织内的法律、人力资源或其他调查的电子邮件数据案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-106">Also, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="7c0c6-107">对于必须尊重地域董事会和条例的跨国公司和政府来说，遵守边界往往是必要的，因为政府往往被划分为不同的机构。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-107">The need for compliance boundaries is often necessary for multi-national corporations that have to respect geographical boarders and regulations and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="7c0c6-108">在 Office 365 中，合规性边界可帮助您在使用电子数据展示案例执行内容搜索和管理调查时满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-108">In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="7c0c6-109">我们使用下图中的示例来解释合规性边界的工作原理。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-109">We use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合规性边界由搜索权限筛选器组成，这些筛选器控制对控制对电子数据展示案例的访问的机构和管理角色组的访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="7c0c6-111">在此示例中，Contoso LTD 是一个 Office 365 组织，由两个子公司，第四咖啡和科霍酒厂组成。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-111">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="7c0c6-112">业务要求电子数据展示经理和调查人员只能搜索其代理中的 Exchange 邮箱、OneDrive 帐户和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="7c0c6-113">此外，电子数据展示经理和调查人员只能在其代理中看到电子数据展示案例，并且他们只能访问他们所参与的案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-113">Also, eDiscovery managers and investigators can only see eDiscovery cases in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="7c0c6-114">以下是合规性边界如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-114">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="7c0c6-115">内容搜索中的搜索权限筛选功能控制电子数据展示经理和调查人员可以搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-115">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="7c0c6-116">这意味着第四咖啡机构中的电子数据展示经理和调查人员只能搜索第四咖啡子公司的内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-116">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="7c0c6-117">同样的限制也适用于科霍酒厂的子公司。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-117">The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="7c0c6-118">角色组控制谁可以在安全&合规中心中查看电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-118">Role groups control who can see the eDiscovery cases in the Security & Compliance Center.</span></span> <span data-ttu-id="7c0c6-119">这意味着电子数据展示经理和调查人员只能在其机构中看到电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-119">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="7c0c6-120">角色组还控制谁可以将成员分配到电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-120">Role groups also control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="7c0c6-121">这意味着电子数据展示经理和调查人员只能将成员分配到他们自己属于的案件。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-121">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="7c0c6-122">以下是设置合规性边界的过程：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="7c0c6-123">第 1 步：标识用户属性以定义您的机构</span><span class="sxs-lookup"><span data-stu-id="7c0c6-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="7c0c6-124">步骤 2： 向 Microsoft 支持提交请求，将用户属性同步到 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="7c0c6-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="7c0c6-125">第 3 步：为每个机构创建角色组</span><span class="sxs-lookup"><span data-stu-id="7c0c6-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="7c0c6-126">步骤 4：创建搜索权限筛选器以强制执行合规性边界</span><span class="sxs-lookup"><span data-stu-id="7c0c6-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="7c0c6-127">第 5 步：为机构内调查创建电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="7c0c6-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="7c0c6-128">第 1 步：标识用户属性以定义您的机构</span><span class="sxs-lookup"><span data-stu-id="7c0c6-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="7c0c6-129">第一步是选择一个 Azure 活动目录属性，用于定义您的机构。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-129">The first step is to choose an Azure Active Directory attribute to use that will define your agencies.</span></span> <span data-ttu-id="7c0c6-130">此属性用于创建搜索权限筛选器，该筛选器将电子数据展示管理器限制为仅搜索为此属性分配特定值的用户的内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-130">This attribute is used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="7c0c6-131">例如，假设 Contoso 决定**使用"部门"** 属性。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-131">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="7c0c6-132">第四咖啡子公司中用户的属性值为`FourthCoffee`， Coho 酒厂子公司的用户值为`CohoWinery`。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-132">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="7c0c6-133">在步骤 4 中，`attribute:value`使用此对（例如，*部门：第四个咖啡店）* 来限制电子数据展示管理器可以搜索的用户内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-133">In Step 4, you use this  `attribute:value`  pair (for example, *Department:FourthCoffee*) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="7c0c6-134">下面是可用于合规性边界的 Azure 活动目录用户属性的列表：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="7c0c6-135">Company</span><span class="sxs-lookup"><span data-stu-id="7c0c6-135">Company</span></span>
    
- <span data-ttu-id="7c0c6-136">自定义属性1 = 自定义属性15</span><span class="sxs-lookup"><span data-stu-id="7c0c6-136">CustomAttribute1 — CustomAttribute15</span></span>
    
- <span data-ttu-id="7c0c6-137">部門</span><span class="sxs-lookup"><span data-stu-id="7c0c6-137">Department</span></span>
    
- <span data-ttu-id="7c0c6-138">辦公室</span><span class="sxs-lookup"><span data-stu-id="7c0c6-138">Office</span></span>

- <span data-ttu-id="7c0c6-139">C（两个字母的国家代码）</span><span class="sxs-lookup"><span data-stu-id="7c0c6-139">C (Two letter Country Code)</span></span>
    
<span data-ttu-id="7c0c6-140">尽管有更多的用户属性可用，特别是对于 Exchange 邮箱，但上面列出的属性是 OneDrive 目前唯一支持的属性。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-140">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="7c0c6-141">步骤 2： 向 Microsoft 支持提交请求，将用户属性同步到 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="7c0c6-141">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="7c0c6-142">下一步是向 Microsoft 支持机构提交请求，以将步骤 1 中选择的 Azure 活动目录属性同步到组织中的所有 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-142">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization.</span></span> <span data-ttu-id="7c0c6-143">发生此同步后，您在步骤 1 中选择的属性（及其值）将映射到名为`ComplianceAttribute`的 SharePoint 中的隐藏托管属性。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-143">After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`.</span></span> <span data-ttu-id="7c0c6-144">使用此属性在步骤 4 中为 OneDrive 创建搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-144">You use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="7c0c6-145">向 Microsoft 支持人员提交请求时，请包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-145">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="7c0c6-146">Office 365 组织的默认域名</span><span class="sxs-lookup"><span data-stu-id="7c0c6-146">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="7c0c6-147">Azure 活动目录属性的名称（从步骤 1 中）</span><span class="sxs-lookup"><span data-stu-id="7c0c6-147">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="7c0c6-148">支持请求用途的以下标题或说明："启用与 Azure 活动目录进行业务同步的 OneDrive，以便获得符合性安全筛选器"。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-148">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters".</span></span> <span data-ttu-id="7c0c6-149">这有助于将请求路由到实现该请求的 Office 365 电子数据展示工程团队。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-149">This helps route the request to the Office 365 eDiscovery engineering team who implements the request.</span></span>
    
<span data-ttu-id="7c0c6-150">进行工程更改并将属性同步到 OneDrive 后，Microsoft 支持将向您发送进行更改的生成号和估计的部署日期。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-150">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date.</span></span> <span data-ttu-id="7c0c6-151">在提交支持请求后，部署过程通常需要 4 到 6 周。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-151">The deployment process usually takes 4–6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="7c0c6-152">**重要提示：** 在部署更改之前，可以完成步骤 3 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-152">**Important:** You can complete Step 3 through Step 5 before the change is deployed.</span></span> <span data-ttu-id="7c0c6-153">但是，在部署更改之前，运行内容搜索不会返回搜索权限筛选器中指定的 OneDrive 网站的文档。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-153">But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="7c0c6-154">第 3 步：为每个机构创建角色组</span><span class="sxs-lookup"><span data-stu-id="7c0c6-154">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="7c0c6-155">下一步是在安全&合规中心创建与您的机构保持一致的角色组。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-155">The next step is to create the role groups in the Security & Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="7c0c6-156">我们建议您通过复制内置电子数据展示管理器组、添加适当的成员以及删除可能不适用于您的需要的角色来创建角色组。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-156">We recommend that you create a role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="7c0c6-157">有关与电子数据展示相关角色的详细信息，请参阅[在 Office 365 安全&合规性中心中分配电子数据展示权限。](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="7c0c6-157">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="7c0c6-158">要创建角色组，请转到"安全&合规**中心"中的"权限"** 页，并为每个机构中将使用合规性边界和电子数据展示案例来管理调查的每个团队创建一个角色组。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-158">To create the role groups, go to the **Permissions** page in the Security & Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="7c0c6-159">使用 Contoso 合规性边界方案，需要创建四个角色组，并将相应的成员添加到每个角色组中。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-159">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="7c0c6-160">第四位咖啡电子展示经理</span><span class="sxs-lookup"><span data-stu-id="7c0c6-160">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="7c0c6-161">第四咖啡调查员</span><span class="sxs-lookup"><span data-stu-id="7c0c6-161">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="7c0c6-162">科霍酒厂电子展示经理</span><span class="sxs-lookup"><span data-stu-id="7c0c6-162">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="7c0c6-163">科霍酒厂调查员</span><span class="sxs-lookup"><span data-stu-id="7c0c6-163">Coho Winery Investigators</span></span>
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="7c0c6-164">步骤 4：创建搜索权限筛选器以强制执行合规性边界</span><span class="sxs-lookup"><span data-stu-id="7c0c6-164">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="7c0c6-165">为每个代理创建角色组后，下一步是创建搜索权限筛选器，将每个角色组与其特定代理相关联并定义合规性边界本身。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-165">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="7c0c6-166">您需要为每个机构创建一个搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-166">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="7c0c6-167">有关创建安全权限筛选器的详细信息，请参阅[为内容搜索配置权限筛选。](permissions-filtering-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="7c0c6-167">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="7c0c6-168">下面是用于创建用于合规性边界的搜索权限筛选器的语法。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-168">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```
  
<span data-ttu-id="7c0c6-169">下面是命令中每个参数的说明：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-169">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="7c0c6-170">`FilterName`：指定筛选器的名称。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-170">`FilterName`: Specifies the name of the filter.</span></span> <span data-ttu-id="7c0c6-171">使用描述或标识筛选器所使用的代理的名称。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-171">Use a name that describes or identifies the agency that the filter is used in.</span></span> 
    
-  <span data-ttu-id="7c0c6-172">`Users`：指定将此筛选器应用于他们执行的内容搜索操作的用户或组。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-172">`Users`: Specifies the users or groups who get this filter applied to the Content Search actions they perform.</span></span> <span data-ttu-id="7c0c6-173">对于符合性边界，此参数指定要为其创建筛选器的机构中创建的角色组（在步骤 3 中创建）。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-173">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="7c0c6-174">请注意，这是一个多值参数，因此您可以包括一个或多个角色组，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-174">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="7c0c6-175">`Filters`：指定筛选器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-175">`Filters`: Specifies the search criteria for the filter.</span></span> <span data-ttu-id="7c0c6-176">对于符合性边界，您可以定义以下筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-176">For the compliance boundaries, you define the following filters.</span></span> <span data-ttu-id="7c0c6-177">每个都适用于内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-177">Each one applies to a content location.</span></span> 
    
    -  <span data-ttu-id="7c0c6-178">`Mailbox`：指定`Users`参数中定义的角色组可以搜索的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-178">`Mailbox`: Specifies the mailboxes that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="7c0c6-179">对于合规性边界，*合规性属性*与您在步骤 1 中标识的属性相同，*属性值*指定代理。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-179">For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="7c0c6-180">此筛选器允许角色组的成员仅搜索特定机构中的邮箱;例如， `"Mailbox_Department -eq 'FourthCoffee'"`.</span><span class="sxs-lookup"><span data-stu-id="7c0c6-180">This filter allows members of the role group to search only the mailboxes in a specific agency; for example, `"Mailbox_Department -eq 'FourthCoffee'"`.</span></span> 
    
    -  <span data-ttu-id="7c0c6-181">`Site`：指定`Users`参数中定义的角色组可以搜索的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-181">`Site`: Specifies the OneDrive accounts that the role groups defined in the `Users` parameter can search.</span></span> <span data-ttu-id="7c0c6-182">对于 OneDrive 筛选器，请使用实际字符串`ComplianceAttribute`。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-182">For the OneDrive filter, use the actual string  `ComplianceAttribute`.</span></span> <span data-ttu-id="7c0c6-183">这将映射到您在步骤 1 中标识的相同属性，该属性由于您在步骤 2 中提交的支持请求而同步到 OneDrive 帐户;*属性值*指定代理。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-183">This maps to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2; *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="7c0c6-184">此筛选器允许角色组的成员仅搜索特定机构中的 OneDrive 帐户;例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span><span class="sxs-lookup"><span data-stu-id="7c0c6-184">This filter allows members of the role group to search only the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
    -  <span data-ttu-id="7c0c6-185">`Site_Path`：指定`Users`参数中定义的角色组可以搜索的 SharePoint 站点。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-185">`Site_Path`: Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="7c0c6-186">*SharePointURL*指定角色组成员可以搜索的代理中的站点。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-186">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search.</span></span> <span data-ttu-id="7c0c6-187">例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-187">For example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`.</span></span> <span data-ttu-id="7c0c6-188">请注意`Site`，`Site_Path`和 筛选器由 **- 或**运算符连接。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-188">Notice the `Site` and `Site_Path` filters are connected by an **-or** operator.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="7c0c6-189">参数`Filters`的语法包括*筛选器列表。*</span><span class="sxs-lookup"><span data-stu-id="7c0c6-189">The syntax for the `Filters` parameter includes a *filters list*.</span></span> <span data-ttu-id="7c0c6-190">筛选器列表是一个筛选器，其中包括邮箱筛选器和由逗号分隔的站点筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-190">A filters list is a filter that includes a mailbox filter and a site filter separated by a comma.</span></span> <span data-ttu-id="7c0c6-191">在前面的示例中，请注意逗号分隔**邮箱_合规性属性**和**站点_合规性属性**： `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-191">In the previous example, notice that a comma separates **Mailbox_ComplianceAttribute** and **Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`.</span></span> <span data-ttu-id="7c0c6-192">在运行内容搜索期间处理此筛选器时，将从筛选器列表中创建两个搜索权限筛选器：一个邮箱筛选器和一个站点筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-192">When this filter is processed during the running of a content search, two search permissions filters are created from the filters list: one mailbox filter and one site filter.</span></span> <span data-ttu-id="7c0c6-193">使用筛选器列表的替代方法是为每个代理创建两个单独的搜索权限筛选器：一个邮箱属性的搜索权限筛选器和一个站点属性的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-193">An alternative to using a filters list would be to create two separate search permissions filters for each agency: one search permissions filter for the mailbox attribute and one filter for the site attributes.</span></span> <span data-ttu-id="7c0c6-194">在这两种情况下，结果都是一样的。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-194">In either case, the results will be the same.</span></span> <span data-ttu-id="7c0c6-195">使用筛选器列表或创建单独的搜索权限筛选器是一个首选项。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-195">Using a filters list or creating separate search permissions filters is a matter of preference.</span></span>

-  <span data-ttu-id="7c0c6-196">`Action`：指定筛选器应用于的符合性搜索操作的类型。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-196">`Action`: Specifies the type of Compliance Search action that the filter is applied to.</span></span> <span data-ttu-id="7c0c6-197">例如，仅当`-Action Search``Users`参数中定义的角色组成员运行内容搜索时，才会应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-197">For example,  `-Action Search` would only apply the filter when members of the role group defined in the `Users` parameter run a content search.</span></span> <span data-ttu-id="7c0c6-198">在这种情况下，在导出搜索结果时不会应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-198">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="7c0c6-199">对于符合性边界，请使用，`-Action All`以便筛选器应用于所有搜索操作。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-199">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="7c0c6-200">有关内容搜索操作的列表，[请参阅"内容搜索配置权限筛选"](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的"新合规性安全筛选"部分。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-200">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>

<span data-ttu-id="7c0c6-201">下面是为支持 Contoso 合规性边界方案而创建的两个搜索权限筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-201">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span> <span data-ttu-id="7c0c6-202">这两个示例都包括逗号分隔的筛选器列表，其中邮箱和站点筛选器包含在相同的搜索权限筛选器中，并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-202">Both of these examples include a comma-separated filters list, in which the mailbox and site filters are included in the same search permissions filter and are separated by a comma.</span></span>
  
 <span data-ttu-id="7c0c6-203">**第四杯咖啡**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-203">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="7c0c6-204">**科霍酒厂**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-204">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a><span data-ttu-id="7c0c6-205">第 5 步：为机构内部调查创建电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="7c0c6-205">Step 5: Create an eDiscovery case for intra-agency investigations</span></span>

<span data-ttu-id="7c0c6-206">最后一步是在安全&合规中心创建电子数据展示案例，然后将您在步骤 3 中创建的角色组添加为案例成员。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-206">The final step is to create a eDiscovery case in the Security & Compliance Center and then add the role group that you created in Step 3 as a member of the case.</span></span> <span data-ttu-id="7c0c6-207">这就产生了使用合规性边界的两个重要特征：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-207">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="7c0c6-208">只有添加到案例的角色组成员才能在安全&合规中心查看和访问案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-208">Only members of the role group added to the case will be able to see and access the case in the Security & Compliance Center.</span></span> <span data-ttu-id="7c0c6-209">例如，如果第四个咖啡调查员角色组是案例的唯一成员，则第四个咖啡电子数据展示经理角色组的成员（或任何其他角色组的成员）将无法查看或访问案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-209">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="7c0c6-210">当分配给案例的角色组的成员运行与案例关联的搜索时，他们只能搜索其代理内的内容位置（由您在步骤 4 中创建的搜索权限筛选器定义）。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-210">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>

<span data-ttu-id="7c0c6-211">要创建案例并分配成员，请：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-211">To create a case and assign members:</span></span>
    
1. <span data-ttu-id="7c0c6-212">转到安全&合规中心**中的电子数据展示**页面并创建案例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-212">Go to the **eDiscovery** page in the Security & Compliance Center and create a case.</span></span> 
    
2. <span data-ttu-id="7c0c6-213">在电子数据展示案例列表中，单击您创建的案例的名称。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-213">In the list of eDiscovery cases, click the name of the case you created.</span></span>
    
3. <span data-ttu-id="7c0c6-214">在"**管理这种情况"** 弹出窗口页中，**在"管理角色组"**![下，](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)单击"添加"**图标"添加**"。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-214">In the **Manage this case** flyout page, under **Manage role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![将角色组添加为电子数据展示案例的成员](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="7c0c6-216">在角色组列表中，选择在步骤 3 中创建的角色组之一，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-216">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="7c0c6-217">单击"**在管理此案例**弹出窗口上**保存"** 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-217">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="7c0c6-218">合规性边界限制</span><span class="sxs-lookup"><span data-stu-id="7c0c6-218">Compliance boundary limitations</span></span>

<span data-ttu-id="7c0c6-219">在管理使用合规性边界的第一个数据展示案例和调查时，请记住以下限制。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-219">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="7c0c6-220">创建和运行内容搜索时，您可以选择机构外部的内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-220">When creating and running a Content Search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="7c0c6-221">但是，由于搜索权限筛选器，来自这些位置的内容不会包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-221">However, because of the search permissions filter, content from those locations isn't included in the search results.</span></span>
    
- <span data-ttu-id="7c0c6-222">合规性边界不适用于电子数据展示案例中的保留。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-222">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="7c0c6-223">这意味着一个机构中的电子数据展示经理可以将另一个机构中的用户置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-223">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="7c0c6-224">但是，如果电子数据展示管理器搜索被置于保留状态的用户的内容位置，则将强制执行合规性边界。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-224">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="7c0c6-225">这意味着电子数据展示管理器将无法搜索用户的内容位置，即使他们能够将用户置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-225">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="7c0c6-226">此外，保留统计信息仅适用于机构中的内容位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-226">Also, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="7c0c6-227">搜索权限筛选器不应用于 Exchange 公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-227">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="7c0c6-228">在多地理位置环境中搜索和导出内容</span><span class="sxs-lookup"><span data-stu-id="7c0c6-228">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="7c0c6-229">搜索权限筛选器还允许您控制在[SharePoint 多地理位置环境中](https://go.microsoft.com/fwlink/?linkid=860840)搜索内容位置时，内容的路由位置以及可以搜索哪个数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-229">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840).</span></span>
  
- <span data-ttu-id="7c0c6-230">**导出搜索结果：** 可以从特定数据中心导出 Exchange 邮箱、SharePoint 站点和 OneDrive 帐户的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-230">**Export search results:** You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="7c0c6-231">这意味着您可以指定搜索结果将从中导出的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-231">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="7c0c6-232">使用"**区域"** 参数进行**新合规性安全筛选器**或**设置合规性安全筛选器**cmdlet 创建或更改导出将路由到的数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-232">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="7c0c6-233">**參數值**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-233">**Parameter value**</span></span>|<span data-ttu-id="7c0c6-234">**数据中心位置**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-234">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c0c6-235">NAM</span><span class="sxs-lookup"><span data-stu-id="7c0c6-235">NAM</span></span>  <br/> |<span data-ttu-id="7c0c6-236">北美（数据中心位于美国）</span><span class="sxs-lookup"><span data-stu-id="7c0c6-236">North American (datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-237">EUR</span><span class="sxs-lookup"><span data-stu-id="7c0c6-237">EUR</span></span>  <br/> |<span data-ttu-id="7c0c6-238">歐洲</span><span class="sxs-lookup"><span data-stu-id="7c0c6-238">Europe</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-239">APC</span><span class="sxs-lookup"><span data-stu-id="7c0c6-239">APC</span></span>  <br/> |<span data-ttu-id="7c0c6-240">亞太地區</span><span class="sxs-lookup"><span data-stu-id="7c0c6-240">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-241">CAN</span><span class="sxs-lookup"><span data-stu-id="7c0c6-241">CAN</span></span> <br/> |<span data-ttu-id="7c0c6-242">加拿大</span><span class="sxs-lookup"><span data-stu-id="7c0c6-242">Canada</span></span>|
    |||
    
- <span data-ttu-id="7c0c6-243">**路由内容搜索：** 您可以将 SharePoint 网站和 OneDrive 帐户的内容搜索路由到卫星数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-243">**Route content searches:** You can route the content searches of SharePoint sites and OneDrive accounts to a satellite data center.</span></span> <span data-ttu-id="7c0c6-244">这意味着您可以指定将运行搜索的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-244">This means you can specify the datacenter location where searches will be run.</span></span>
    
    <span data-ttu-id="7c0c6-245">**对"区域"** 参数使用以下值之一来控制搜索 SharePoint 站点和 OneDrive 帐户时将运行的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-245">Use one of the following values for the **Region** parameter to control the datacenter location that searches will run in when searching SharePoint sites and OneDrive accounts.</span></span> 
  
    |<span data-ttu-id="7c0c6-246">**參數值**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-246">**Parameter value**</span></span>|<span data-ttu-id="7c0c6-247">**SharePoint 的数据中心路由位置**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-247">**Datacenter routing locations for SharePoint**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c0c6-248">NAM</span><span class="sxs-lookup"><span data-stu-id="7c0c6-248">NAM</span></span>  <br/> |<span data-ttu-id="7c0c6-249">我们</span><span class="sxs-lookup"><span data-stu-id="7c0c6-249">US</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-250">EUR</span><span class="sxs-lookup"><span data-stu-id="7c0c6-250">EUR</span></span>  <br/> |<span data-ttu-id="7c0c6-251">歐洲</span><span class="sxs-lookup"><span data-stu-id="7c0c6-251">Europe</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-252">APC</span><span class="sxs-lookup"><span data-stu-id="7c0c6-252">APC</span></span>  <br/> |<span data-ttu-id="7c0c6-253">亞太地區</span><span class="sxs-lookup"><span data-stu-id="7c0c6-253">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-254">CAN</span><span class="sxs-lookup"><span data-stu-id="7c0c6-254">CAN</span></span>  <br/> |<span data-ttu-id="7c0c6-255">我们</span><span class="sxs-lookup"><span data-stu-id="7c0c6-255">US</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-256">AUS</span><span class="sxs-lookup"><span data-stu-id="7c0c6-256">AUS</span></span>  <br/> |<span data-ttu-id="7c0c6-257">亞太地區</span><span class="sxs-lookup"><span data-stu-id="7c0c6-257">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-258">KOR</span><span class="sxs-lookup"><span data-stu-id="7c0c6-258">KOR</span></span>  <br/> |<span data-ttu-id="7c0c6-259">组织的默认数据中心</span><span class="sxs-lookup"><span data-stu-id="7c0c6-259">The organization's default datacenter</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-260">GBR</span><span class="sxs-lookup"><span data-stu-id="7c0c6-260">GBR</span></span>  <br/> |<span data-ttu-id="7c0c6-261">歐洲</span><span class="sxs-lookup"><span data-stu-id="7c0c6-261">Europe</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-262">JPN</span><span class="sxs-lookup"><span data-stu-id="7c0c6-262">JPN</span></span>  <br/> |<span data-ttu-id="7c0c6-263">亞太地區</span><span class="sxs-lookup"><span data-stu-id="7c0c6-263">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-264">IND</span><span class="sxs-lookup"><span data-stu-id="7c0c6-264">IND</span></span>  <br/> |<span data-ttu-id="7c0c6-265">亞太地區</span><span class="sxs-lookup"><span data-stu-id="7c0c6-265">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="7c0c6-266">议员</span><span class="sxs-lookup"><span data-stu-id="7c0c6-266">LAM</span></span>  <br/> |<span data-ttu-id="7c0c6-267">我们</span><span class="sxs-lookup"><span data-stu-id="7c0c6-267">US</span></span>  <br/> |
    |||

   <span data-ttu-id="7c0c6-268">如果不为搜索权限筛选器**指定"区域"** 参数，则将搜索组织的默认 SharePoint 区域。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-268">If you don't specify the **Region** parameter for a search permissions filter, the organization's default SharePoint region will be searched.</span></span> <span data-ttu-id="7c0c6-269">搜索结果将导出到最近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-269">Search results are exported to the closest datacenter.</span></span>

> [!TIP]
> <span data-ttu-id="7c0c6-270">为了简化概念，**区域**参数控制用于在 SharePoint 和 OneDrive 中搜索内容的数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-270">To simplify the concept, the **Region** parameter controls the datacenter that is used to search for content in SharePoint and OneDrive.</span></span> <span data-ttu-id="7c0c6-271">这不适用于在 Exchange 中搜索内容，因为 Exchange 内容搜索不受数据中心地理位置的约束。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-271">This doesn't apply to searching for content in Exchange because Exchange content searches aren't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="7c0c6-272">此外，相同的**Region**参数值也可能指示导出的数据中心通过。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-272">Also, the same **Region** parameter value may also dictate the datacenter that exports are routed through.</span></span> <span data-ttu-id="7c0c6-273">这通常是控制数据在地理棋盘之间移动所必需的。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-273">This is often necessary to control the movement of data across geographic boarders.</span></span><br/><br/><span data-ttu-id="7c0c6-274">如果您使用的是高级电子数据展示，则在 SharePoint 和 OneDrive 中搜索内容不受数据中心地理位置的约束。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-274">If you're using Advanced eDiscovery, searching for content in SharePoint and OneDrive isn't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="7c0c6-275">搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-275">All datacenters are searched.</span></span> <span data-ttu-id="7c0c6-276">有关高级电子数据展示的详细信息，请参阅[Microsoft 365 中高级电子数据展示解决方案的概述。](overview-ediscovery-20.md)</span><span class="sxs-lookup"><span data-stu-id="7c0c6-276">For more information about Advanced eDiscovery, see [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).</span></span>

<span data-ttu-id="7c0c6-277">以下是在为合规性边界创建搜索权限筛选器时**使用"区域"** 参数的示例。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-277">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="7c0c6-278">这假定第四咖啡子公司位于北美，科霍酒厂位于欧洲。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-278">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="7c0c6-279">在多地理位置环境中搜索和导出内容时，请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-279">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="7c0c6-280">**"区域"** 参数不控制 Exchange 邮箱的搜索。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-280">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="7c0c6-281">搜索邮箱时将搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-281">All data centers will be searched when you search mailboxes.</span></span> <span data-ttu-id="7c0c6-282">要限制搜索 Exchange 邮箱的范围，请使用**筛选器**参数在创建或更改搜索权限筛选器时。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-282">To limit the scope of which Exchange mailboxes are searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="7c0c6-283">如果电子数据展示管理器需要跨多个 SharePoint 区域进行搜索，则需要为该电子数据展示管理器创建一个不同的用户帐户，以便在搜索权限筛选器中指定 SharePoint 网站或 OneDrive 的区域帐户的位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-283">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you need to create a different user account for that eDiscovery manager to use in the search permissions filter to specify the region where the SharePoint sites or OneDrive accounts are located.</span></span> <span data-ttu-id="7c0c6-284">有关设置此设置的详细信息，请参阅[Office 365 中的内容搜索中的"](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)在 SharePoint 多地理位置环境中搜索内容"部分。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-284">For more information about setting this up, see the "Searching for content in a SharePoint Multi-Geo environment" section in [Content Search in Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment).</span></span>
    
- <span data-ttu-id="7c0c6-285">在 SharePoint 和 OneDrive 中搜索内容时，"**区域"** 参数会将搜索定向到电子数据展示管理器将执行电子数据展示调查的主位置或卫星位置。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-285">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="7c0c6-286">如果电子数据展示管理器在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站，则不返回任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-286">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results are returned.</span></span> 
    
- <span data-ttu-id="7c0c6-287">导出搜索结果时，来自所有内容位置的内容（包括 Exchange、Skype 业务、SharePoint、OneDrive 和其他可以使用内容搜索工具搜索的 Office 365 服务）将上载到 中的 Azure 存储位置。**由"区域"** 参数指定的数据中心。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-287">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive, and other Office 365 services that you can search by using the Content Search tool) are uploaded to the Azure Storage location in the datacenter that's specified by the **Region** parameter.</span></span> <span data-ttu-id="7c0c6-288">这帮助组织通过不允许跨受控边界导出内容来保持合规性。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-288">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="7c0c6-289">如果在搜索权限筛选器中未指定区域，则内容将上载到组织的默认区域。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-289">If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="7c0c6-290">您可以通过运行以下命令编辑现有搜索权限筛选器以添加或更改区域：</span><span class="sxs-lookup"><span data-stu-id="7c0c6-290">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="7c0c6-291">常見問題集</span><span class="sxs-lookup"><span data-stu-id="7c0c6-291">Frequently asked questions</span></span>

 <span data-ttu-id="7c0c6-292">**谁可以创建和管理搜索权限筛选器（使用新合规性安全筛选器和设置合规性安全筛选器 cmdlet）？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-292">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets)?**</span></span>
  
<span data-ttu-id="7c0c6-293">要创建、查看和修改搜索权限筛选器，您必须是安全&合规性中心中的组织管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-293">To create, view, and modify search permissions filters, you have to be a member of the Organization Management role group in the Security & Compliance Center.</span></span>
  
 <span data-ttu-id="7c0c6-294">**如果电子数据展示经理被分配到多个跨多个机构的角色组，他们如何在一个机构或另一个机构中搜索内容？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-294">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="7c0c6-295">电子数据展示管理器可以向其搜索查询添加参数，将搜索限制为特定机构。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-295">The eDiscovery manager can add parameters to their search query that restrict the search to a specific agency.</span></span> <span data-ttu-id="7c0c6-296">例如，如果组织指定**了 CustomAttribute10**属性来区分代理，则可以将以下内容追加到搜索查询中，以搜索特定代理中的邮箱和 OneDrive 帐户： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-296">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="7c0c6-297">**如果用作搜索权限筛选器中的符合性属性的属性的值发生更改，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-297">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="7c0c6-298">如果筛选器中使用的属性的值发生更改，则搜索权限筛选器最多需要三天时间才能强制执行符合性边界。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-298">It takes up to three days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="7c0c6-299">例如，在 Contoso 场景中，假设第四咖啡代理公司中的用户被转移到 Coho 酒厂代理。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-299">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="7c0c6-300">因此，用户对象**上的"部门"** 属性的值*从"第四咖啡"* 更改为*CohoWinery*。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-300">As a result, the value of the **Department** attribute on the user object is changed from *FourthCoffee* to *CohoWinery*.</span></span> <span data-ttu-id="7c0c6-301">在这种情况下，第四咖啡电子数据展示和投资者将获得该用户的搜索结果后三天，属性被更改。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-301">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed.</span></span> <span data-ttu-id="7c0c6-302">同样，科霍酒厂电子数据展示经理和调查人员最多需要三天时间才能为用户获取搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-302">Similarly, it takes up to three days before Coho Winery eDiscovery managers and investigators get search results for the user.</span></span> 
  
 <span data-ttu-id="7c0c6-303">**电子数据展示经理能否查看来自两个独立合规性边界的内容？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-303">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="7c0c6-304">是。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-304">Yes.</span></span> <span data-ttu-id="7c0c6-305">这可以通过将用户添加到对两个机构具有可见性的角色组来实现。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-305">This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="7c0c6-306">**搜索权限筛选器是否适用于电子数据展示案例保留、Office 365 保留策略或 DLP？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-306">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="7c0c6-307">不，现在不。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-307">No, not at this time.</span></span>
  
 <span data-ttu-id="7c0c6-308">**如果我指定一个区域来控制内容的导出位置，但该区域中没有 SharePoint 组织，我是否可以搜索 SharePoint？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-308">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="7c0c6-309">如果组织中不存在搜索权限筛选器中指定的区域，则将搜索默认区域。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-309">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="7c0c6-310">**可在组织中创建的搜索权限筛选器的最大数量是多少？**</span><span class="sxs-lookup"><span data-stu-id="7c0c6-310">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="7c0c6-311">可以在组织中创建的搜索权限筛选器的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-311">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="7c0c6-312">但是，当有超过 100 个搜索权限筛选器时，搜索性能将受到影响。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-312">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="7c0c6-313">要使组织中的搜索权限筛选器数量尽可能小，请创建筛选器，尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中。</span><span class="sxs-lookup"><span data-stu-id="7c0c6-313">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
