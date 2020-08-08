---
title: 選擇建立 Microsoft 365 群組時要使用的網域
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '透過設定電子郵件地址原則使用 PowerShell，瞭解如何選擇建立 Microsoft 365 群組時所使用的網域。 '
ms.openlocfilehash: 19caa4f4dfdef4895fa58f8bf5c198269844044f
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597374"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="3d648-103">選擇建立 Microsoft 365 群組時要使用的網域</span><span class="sxs-lookup"><span data-stu-id="3d648-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

 <span data-ttu-id="3d648-104">有些組織會使用不同的電子郵件網域來將業務區隔為不同部分。</span><span class="sxs-lookup"><span data-stu-id="3d648-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="3d648-105">您可以指定當使用者建立 Microsoft 365 群組時，應使用的網域。</span><span class="sxs-lookup"><span data-stu-id="3d648-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="3d648-106">如果您的組織需要使用者在公司預設的公認網域以外的網域中建立他們的群組，您可以使用 PowerShell 來設定電子郵件地址原則 (EAPs) ，以允許這麼做。</span><span class="sxs-lookup"><span data-stu-id="3d648-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="3d648-107">在您可以執行 PowerShell Cmdlet 之前，請下載並安裝可讓您與組織交談的模組。</span><span class="sxs-lookup"><span data-stu-id="3d648-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="3d648-108">[使用遠端 PowerShell 查看 [連線至 Exchange Online]](https://go.microsoft.com/fwlink/p/?LinkId=785881)。</span><span class="sxs-lookup"><span data-stu-id="3d648-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="3d648-109">範例案例</span><span class="sxs-lookup"><span data-stu-id="3d648-109">Example scenarios</span></span>

<span data-ttu-id="3d648-110">假設您公司的主要網域是 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3d648-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="3d648-111">不過，您組織的預設公認網域是 service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3d648-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="3d648-112">這表示將會在 service.contoso.com (中建立群組，例如，jimsteam@service.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="3d648-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="3d648-113">假設您的組織中也有設定子域。</span><span class="sxs-lookup"><span data-stu-id="3d648-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="3d648-114">您也想要在這些網域中建立群組：</span><span class="sxs-lookup"><span data-stu-id="3d648-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="3d648-115">學生 students.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d648-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="3d648-116">教職員 faculty.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d648-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="3d648-117">下列兩個案例會說明如何完成此作業。</span><span class="sxs-lookup"><span data-stu-id="3d648-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d648-118">當您有多個 EAPs 時，會以優先順序的順序評估。</span><span class="sxs-lookup"><span data-stu-id="3d648-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="3d648-119">值為1表示最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="3d648-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="3d648-120">EAP 符合後，就不會再評估任何 EAP，而且在群組上加蓋標記的位址，都是根據相符的 EAP。</span><span class="sxs-lookup"><span data-stu-id="3d648-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="3d648-121">> 如果沒有 EAPs 符合指定的準則，群組便會在組織的預設公認網域中布建。</span><span class="sxs-lookup"><span data-stu-id="3d648-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="3d648-122">請參閱[管理 Exchange Online 中公認的網域](https://go.microsoft.com/fwlink/p/?LinkId=785428)，以取得如何新增公認的網域的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3d648-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="3d648-123">案例 1</span><span class="sxs-lookup"><span data-stu-id="3d648-123">Scenario 1</span></span>

<span data-ttu-id="3d648-124">下列範例顯示如何在 groups.contoso.com 網域中布建組織中的所有 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="3d648-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="3d648-125">案例 2</span><span class="sxs-lookup"><span data-stu-id="3d648-125">Scenario 2</span></span>

<span data-ttu-id="3d648-126">假設您想要控制哪些子域中建立的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="3d648-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="3d648-127">你想要：</span><span class="sxs-lookup"><span data-stu-id="3d648-127">You want:</span></span>
  
- <span data-ttu-id="3d648-128">由學生所建立的群組 (使用者**已設定**為) 在 Students.groups.contoso.com 網域中的**學生**的使用者。</span><span class="sxs-lookup"><span data-stu-id="3d648-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="3d648-129">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="3d648-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="3d648-130">教職員所建立的群組 (**使用者已設定**為**教職員或電子郵件地址**的使用者，在 faculty.groups.contoso.com 網域中包含 faculty.contoso.com) ) 。</span><span class="sxs-lookup"><span data-stu-id="3d648-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="3d648-131">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="3d648-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="3d648-132">Groups.contoso.com 網域中的所有其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3d648-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="3d648-133">請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="3d648-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="3d648-134">變更電子郵件地址原則</span><span class="sxs-lookup"><span data-stu-id="3d648-134">Change email address policies</span></span>

<span data-ttu-id="3d648-135">若要變更現有 EAP 的優先順序或電子郵件地址範本，請使用 Set-EmailAddressPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d648-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="3d648-136">變更 EAP 不會影響已布建的群組。</span><span class="sxs-lookup"><span data-stu-id="3d648-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="3d648-137">刪除電子郵件地址原則</span><span class="sxs-lookup"><span data-stu-id="3d648-137">Delete email address policies</span></span>

<span data-ttu-id="3d648-138">若要刪除 EAP，請使用 Remove-EmailAddressPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d648-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="3d648-139">變更 EAP 不會影響已布建的群組。</span><span class="sxs-lookup"><span data-stu-id="3d648-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="3d648-140">混合需求</span><span class="sxs-lookup"><span data-stu-id="3d648-140">Hybrid requirements</span></span>

<span data-ttu-id="3d648-141">如果您的組織是在混合案例中設定，請參閱[使用內部部署 Exchange 混合式設定 Microsoft 365 群組](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)，以確保您的組織符合建立 Microsoft 365 群組的需求。</span><span class="sxs-lookup"><span data-stu-id="3d648-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="3d648-142">使用電子郵件地址原則群組的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="3d648-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="3d648-143">還有其他一些事項需要注意：</span><span class="sxs-lookup"><span data-stu-id="3d648-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="3d648-144">建立的速度群組取決於您組織中設定的 EAPs 數目。</span><span class="sxs-lookup"><span data-stu-id="3d648-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="3d648-145">管理員和使用者也可以在建立群組時修改網域。</span><span class="sxs-lookup"><span data-stu-id="3d648-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="3d648-146">使用者群組是使用標準查詢（ (使用者屬性) 已可用）決定。</span><span class="sxs-lookup"><span data-stu-id="3d648-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="3d648-147">請查看[-RecipientFilter 參數](https://go.microsoft.com/fwlink/p/?LinkId=785918)的可篩選內容，以取得支援的可篩選屬性。</span><span class="sxs-lookup"><span data-stu-id="3d648-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="3d648-148">如果您未設定群組的任何 EAPs，則會選取預設的公認網域以建立群組。</span><span class="sxs-lookup"><span data-stu-id="3d648-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="3d648-149">如果您移除公認的網域，您應該先更新 EAPs，否則將會影響群組布建。</span><span class="sxs-lookup"><span data-stu-id="3d648-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="3d648-150">您可以為組織設定100電子郵件地址原則的上限。</span><span class="sxs-lookup"><span data-stu-id="3d648-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3d648-151">相關文章</span><span class="sxs-lookup"><span data-stu-id="3d648-151">Related articles</span></span>

[<span data-ttu-id="3d648-152">在系統管理中心建立 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="3d648-152">Create an Microsoft 365 group in the admin center</span></span>](create-groups.md)
