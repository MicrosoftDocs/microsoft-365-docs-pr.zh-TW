---
title: 選擇建立 Office 365 群組時要使用的網域
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '了解如何選擇藉由設定電子郵件地址原則使用 PowerShell 建立 Office 365 群組時要使用的網域。 '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239235"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="bfcb5-103">選擇建立 Office 365 群組時要使用的網域</span><span class="sxs-lookup"><span data-stu-id="bfcb5-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="bfcb5-p101">有些組織會使用不同的電子郵件網域來將業務區隔為不同部分。當您的使用者要建立 Office 365 群組時，您可以指定應使用哪一個網域。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="bfcb5-106">如果您的組織需要使用者在非預設的網域中建立其群組之公認的網域，您的業務，您可以允許此行為設定電子郵件地址原則 (EAPs) 使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="bfcb5-107">您可以執行的 PowerShell cmdlet 之前，請下載並安裝模組，將可讓您洽詢您的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization.</span></span> <span data-ttu-id="bfcb5-108">請參閱[Connect to Exchange Online 使用遠端 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="bfcb5-109">範例案例</span><span class="sxs-lookup"><span data-stu-id="bfcb5-109">Example scenarios</span></span>

<span data-ttu-id="bfcb5-110">例如，假設貴公司的主要網域是 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="bfcb5-111">但您的組織預設的公認的網域是 service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="bfcb5-112">這表示會在 service.contoso.com (例如，jimsteam@service.contoso.com) 中建立群組。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="bfcb5-113">例如，假設您也必須設定組織中的子網域。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="bfcb5-114">您想太建立這些網域中的群組：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="bfcb5-115">學生的 students.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bfcb5-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="bfcb5-116">適用於教師成員 faculty.contoso.com 的郵件</span><span class="sxs-lookup"><span data-stu-id="bfcb5-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="bfcb5-117">下列兩個案例將說明如何您會完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfcb5-118">當您有多個站 EAPs 時，會評估定義優先順序。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="bfcb5-119">值是 1 表示最高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="bfcb5-120">一旦 EAP 符合，沒有進一步的 EAP 會評估，並取得加上戳記，群組的地址是根據符合 EAP。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="bfcb5-121">如果沒有 EAPs 符合指定的準則，則群組取得中組織的預設佈建 > 公認的網域。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="bfcb5-122">請參閱[管理公認的網域在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428)的 how to： 新增公認的網域的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="bfcb5-123">案例 1</span><span class="sxs-lookup"><span data-stu-id="bfcb5-123">Scenario 1</span></span>

<span data-ttu-id="bfcb5-124">下列範例會示範如何佈建 groups.contoso.com 網域中您組織中的所有 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="bfcb5-125">案例 2</span><span class="sxs-lookup"><span data-stu-id="bfcb5-125">Scenario 2</span></span>

<span data-ttu-id="bfcb5-126">例如，假設您想要控制子網域的 Office 365 群組中的建立。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="bfcb5-127">您想要：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-127">You want:</span></span>
  
- <span data-ttu-id="bfcb5-128">學生 （有**部門**設**學生**的使用者） 建立 students.groups.contoso.com 網域中的群組。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="bfcb5-129">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="bfcb5-130">教師成員所建立的群組 (使用者有**部門**設**教職人員或電子郵件地址包含 faculty.contoso.com 的郵件)**) faculty.groups.contoso.com 網域中。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="bfcb5-131">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="bfcb5-132">所有其他網域中的使用者 groups.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="bfcb5-133">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="bfcb5-134">變更電子郵件地址原則</span><span class="sxs-lookup"><span data-stu-id="bfcb5-134">Change email address policies</span></span>

<span data-ttu-id="bfcb5-135">若要變更現有的 EAP 優先順序或電子郵件地址範本，請使用 Set-emailaddresspolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="bfcb5-136">變更 EAP 具有已佈建的群組不會影響。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="bfcb5-137">刪除電子郵件地址原則</span><span class="sxs-lookup"><span data-stu-id="bfcb5-137">Delete email address policies</span></span>

<span data-ttu-id="bfcb5-138">若要刪除 EAP，使用 Remove-emailaddresspolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="bfcb5-139">變更 EAP 具有已佈建的群組不會影響。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="bfcb5-140">混合需求</span><span class="sxs-lookup"><span data-stu-id="bfcb5-140">Hybrid requirements</span></span>

<span data-ttu-id="bfcb5-141">如果您的組織設定混合式案例，請參閱若要確保您的組織符合建立 Office 365 群組的需求[設定 Office 365 群組與內部部署 Exchange 混合式](https://go.microsoft.com/fwlink/p/?LinkId=785430)。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="bfcb5-142">使用相關的其他資訊電子郵件地址原則群組：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="bfcb5-143">有幾個更多的須知事項：</span><span class="sxs-lookup"><span data-stu-id="bfcb5-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="bfcb5-144">如何快速建立群組，取決於您組織中設定的 EAPs 數目。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="bfcb5-145">系統管理員和使用者也可以修改網域在建立群組時。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="bfcb5-146">使用者群組會決定使用已可以使用標準查詢 （使用者內容）。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="bfcb5-147">請參閱[-RecipientFilter 參數的可篩選內容](https://go.microsoft.com/fwlink/p/?LinkId=785918)的支援的可篩選 pproperties。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="bfcb5-148">如果您未設定任何 EAPs 群組，然後預設的公認的網域選取群組建立。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="bfcb5-149">如果您移除公認的網域，您應該先更新 EAPs，否則群組佈建將會受到影響。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="bfcb5-150">上限為 100 的電子郵件地址原則可為組織設定。</span><span class="sxs-lookup"><span data-stu-id="bfcb5-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="bfcb5-151">相關文章</span><span class="sxs-lookup"><span data-stu-id="bfcb5-151">Related articles</span></span>

[<span data-ttu-id="bfcb5-152">在系統管理中心建立 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="bfcb5-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
