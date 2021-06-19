---
title: 設定 eDiscovery 調查的合規性界限
f1.keywords:
- NOCSH
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
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 瞭解如何使用規範界限來建立邏輯界限，以控制 eDiscovery 管理員可以在 Microsoft 365 中搜尋的使用者內容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23ff50b9cd0ab0178962f7be9f1cedfbd6a7a1f7
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022339"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a><span data-ttu-id="90d51-103">設定 eDiscovery 調查的合規性界限</span><span class="sxs-lookup"><span data-stu-id="90d51-103">Set up compliance boundaries for eDiscovery investigations</span></span>

<span data-ttu-id="90d51-104">使用核心 eDiscovery 或 Advanced eDiscovery 管理調查時，可以套用本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="90d51-104">The guidance in this article can be applied when using either Core eDiscovery or Advanced eDiscovery to manage investigations.</span></span>

<span data-ttu-id="90d51-105">規範界限在組織內建立邏輯界限，以控制使用者內容位置 (例如，信箱、OneDrive 帳戶，以及 eDiscovery 管理員可搜尋) 的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="90d51-105">Compliance boundaries create logical boundaries within an organization that control the user content locations (such as mailboxes, OneDrive accounts, and SharePoint sites) that eDiscovery managers can search.</span></span> <span data-ttu-id="90d51-106">此外，合規性界限控制誰可以存取 eDiscovery 案例，以用於管理組織內的法律、人力資源或其他調查。</span><span class="sxs-lookup"><span data-stu-id="90d51-106">Also, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="90d51-107">對於必須遵守地理 boarders 及法規及政府（通常分為不同的代理商）的跨國公司，必須使用規範界限。</span><span class="sxs-lookup"><span data-stu-id="90d51-107">The need for compliance boundaries is often necessary for multi-national corporations that have to respect geographical boarders and regulations and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="90d51-108">在 Microsoft 365 中，相容性界限可協助您在使用 eDiscovery 案例執行內容搜尋及管理調查時符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="90d51-108">In Microsoft 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="90d51-109">我們會使用下圖中的範例，說明規範界限的運作方式。</span><span class="sxs-lookup"><span data-stu-id="90d51-109">We use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![規範界限是由控制對電子檔或系統管理員角色群組存取的搜尋許可權篩選所組成，以控制 eDiscovery 案例的存取](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
<span data-ttu-id="90d51-111">在此範例中，Contoso 有限公司是由兩個分公司、第四個咖啡和 Coho Winery 所組成的組織。</span><span class="sxs-lookup"><span data-stu-id="90d51-111">In this example, Contoso LTD is an organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="90d51-112">業務要求 eDiscovery mangers 和調查人員只能搜尋其代理人中 Exchange 信箱、OneDrive 帳戶及 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="90d51-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="90d51-113">此外，eDiscovery 管理員和調查人員只會查看其代理人中的 eDiscovery 案例，而且只能存取他們隸屬的案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-113">Also, eDiscovery managers and investigators can only see eDiscovery cases in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="90d51-114">此外，在這種情況下，調查人員無法保留內容位置或從案例中匯出內容。</span><span class="sxs-lookup"><span data-stu-id="90d51-114">Additionally in this scenario, investigators cannot place content locations on hold or export content from a case.</span></span> <span data-ttu-id="90d51-115">以下是規範界限如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="90d51-115">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="90d51-116">內容搜尋中的搜尋許可權篩選功能會控制 eDiscovery 管理員和調查人員可搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-116">The search permissions filtering functionality in Content search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="90d51-117">這表示 Fourth Coffee 機構內的電子文件探索管理員和調查人員只能搜尋 Fourth Coffee 子公司內的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-117">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="90d51-118">Coho Winery 子公司也有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="90d51-118">The same restriction applies to the Coho Winery subsidiary.</span></span>

- <span data-ttu-id="90d51-119">[角色群組](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) 為符合性界限提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="90d51-119">[Role groups](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) provide the following functions for compliance boundaries:</span></span>

  - <span data-ttu-id="90d51-120">控制在 Microsoft 365 合規性中心中誰可以查看 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-120">Control who can see the eDiscovery cases in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="90d51-121">這表示電子文件探索管理員和調查人員只能查看其機構內的電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-121">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>

  - <span data-ttu-id="90d51-122">控制誰可以指派成員至 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-122">Control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="90d51-123">這表示電子文件探索管理員和調查人員只能將成員指派給其本身為成員的案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-123">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>

  - <span data-ttu-id="90d51-124">新增或移除指派特定許可權的角色，以控制可執行成員的 eDiscovery 相關工作。</span><span class="sxs-lookup"><span data-stu-id="90d51-124">Control the eDiscovery-related tasks that members can perform by adding or removing roles that assign specific permissions.</span></span>

<span data-ttu-id="90d51-125">以下是設定規范界限的程式：</span><span class="sxs-lookup"><span data-stu-id="90d51-125">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="90d51-126">步驟1：識別使用者屬性以定義您的機構</span><span class="sxs-lookup"><span data-stu-id="90d51-126">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="90d51-127">步驟2：建立每個代理人的角色群組</span><span class="sxs-lookup"><span data-stu-id="90d51-127">Step 2: Create a role group for each agency</span></span>](#step-2-create-a-role-group-for-each-agency)

[<span data-ttu-id="90d51-128">步驟3：建立搜尋許可權篩選以強制執行規范界限</span><span class="sxs-lookup"><span data-stu-id="90d51-128">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="90d51-129">步驟4：建立內部公司調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="90d51-129">Step 4: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a><span data-ttu-id="90d51-130">設定規范界限之前</span><span class="sxs-lookup"><span data-stu-id="90d51-130">Before you set up compliance boundaries</span></span>

- <span data-ttu-id="90d51-131">使用者必須被指派 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="90d51-131">Users must be assigned an Exchange Online license.</span></span> <span data-ttu-id="90d51-132">若要確認這一點，請在 Exchange Online PowerShell 中使用[Get-User](/powershell/module/exchange/get-user) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90d51-132">To verify this, use the [Get-User](/powershell/module/exchange/get-user) cmdlet in Exchange Online PowerShell.</span></span>

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="90d51-133">步驟1：識別使用者屬性以定義您的機構</span><span class="sxs-lookup"><span data-stu-id="90d51-133">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="90d51-134">第一步是選擇用來定義您的機構的屬性。</span><span class="sxs-lookup"><span data-stu-id="90d51-134">The first step is to choose an attribute to use that will define your agencies.</span></span> <span data-ttu-id="90d51-135">此屬性是用來建立「搜尋許可權」篩選，它會限制 eDiscovery 管理員只搜尋指派此屬性之特定值之使用者的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-135">This attribute is used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="90d51-136">例如，假設 Contoso 決定使用 [ **部門** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="90d51-136">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="90d51-137">此屬性的值為第四個咖啡分公司中的使用者，則為  `FourthCoffee`  Coho Winery 子公司中的使用者的值 `CohoWinery` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-137">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="90d51-138">在步驟3中，您可以使用這  `attribute:value`  對 (例如， *部門： FourthCoffee*) 來限制 eDiscovery 管理員可搜尋的使用者內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-138">In Step 3, you use this  `attribute:value`  pair (for example, *Department:FourthCoffee*) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="90d51-139">以下是您可以用於規範界限的使用者屬性範例：</span><span class="sxs-lookup"><span data-stu-id="90d51-139">Here are some examples of user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="90d51-140">Company</span><span class="sxs-lookup"><span data-stu-id="90d51-140">Company</span></span>

- <span data-ttu-id="90d51-141">CustomAttribute1 CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="90d51-141">CustomAttribute1 - CustomAttribute15</span></span>

- <span data-ttu-id="90d51-142">部門</span><span class="sxs-lookup"><span data-stu-id="90d51-142">Department</span></span>

- <span data-ttu-id="90d51-143">辦公室</span><span class="sxs-lookup"><span data-stu-id="90d51-143">Office</span></span>

- <span data-ttu-id="90d51-144">CountryOrRegion (兩個字母的國家/地區碼) </span><span class="sxs-lookup"><span data-stu-id="90d51-144">CountryOrRegion (Two-letter country code)</span></span>

<span data-ttu-id="90d51-145">如需完整清單，請參閱支援的 [信箱篩選器](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)的完整清單。</span><span class="sxs-lookup"><span data-stu-id="90d51-145">For a complete list, see the full list of supported [mailbox filters](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties).</span></span>

## <a name="step-2-create-a-role-group-for-each-agency"></a><span data-ttu-id="90d51-146">步驟2：建立每個代理人的角色群組</span><span class="sxs-lookup"><span data-stu-id="90d51-146">Step 2: Create a role group for each agency</span></span>

<span data-ttu-id="90d51-147">下一步是在安全性 & 規範中心建立角色群組，以與您的機構相符。</span><span class="sxs-lookup"><span data-stu-id="90d51-147">The next step is to create the role groups in the Security & Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="90d51-148">建議您複製內建的電子文件探索管理員群組、新增適當的成員，以及移除可能不適用於您需求的角色，來建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="90d51-148">We recommend that you create a role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="90d51-149">如需有關 eDiscovery 相關角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="90d51-149">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="90d51-150">若要建立角色群組，請移至安全性與合規性中心內的 [權限]\*\*\*\* 頁面，然後為每個機構中將會使用合規性界限和電子文件探索案例來管理調查的每個小組建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="90d51-150">To create the role groups, go to the **Permissions** page in the Security & Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span>
  
<span data-ttu-id="90d51-151">使用 Contoso 相容性邊界案例，必須建立四個角色群組，並將適當的成員新增至每一個群組。</span><span class="sxs-lookup"><span data-stu-id="90d51-151">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="90d51-152">Fourth Coffee 電子文件探索管理員</span><span class="sxs-lookup"><span data-stu-id="90d51-152">Fourth Coffee eDiscovery Managers</span></span>

- <span data-ttu-id="90d51-153">Fourth Coffee 調查人員</span><span class="sxs-lookup"><span data-stu-id="90d51-153">Fourth Coffee Investigators</span></span>

- <span data-ttu-id="90d51-154">Coho Winery 電子文件探索管理員</span><span class="sxs-lookup"><span data-stu-id="90d51-154">Coho Winery eDiscovery Managers</span></span>

- <span data-ttu-id="90d51-155">Coho Winery 調查人員</span><span class="sxs-lookup"><span data-stu-id="90d51-155">Coho Winery Investigators</span></span>
  
<span data-ttu-id="90d51-156">為了符合 Contoso 合規性邊界案例的需求，您也可以移除「調查人員」角色群組中的 **保留** 和 **匯出** 角色，以防止調查人員在內容位置上放置保留，以及從案例中匯出內容。</span><span class="sxs-lookup"><span data-stu-id="90d51-156">To meet the requirements of the Contoso compliance boundaries scenario, you would also remove the **Hold** and **Export** roles from the investigators role groups to prevent investigators from placing holds on content locations and exporting content from a case.</span></span>

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="90d51-157">步驟3：建立搜尋許可權篩選以強制執行規范界限</span><span class="sxs-lookup"><span data-stu-id="90d51-157">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="90d51-158">在您為每個代理商建立角色群組之後，下一步是建立搜尋許可權篩選器，將每個角色群組關聯至特定的代理人，並定義規範界限本身。</span><span class="sxs-lookup"><span data-stu-id="90d51-158">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="90d51-159">您必須為每個代理人建立一個搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-159">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="90d51-160">如需建立安全性許可權篩選的詳細資訊，請參閱 [設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="90d51-160">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="90d51-161">以下是用來建立搜尋許可權篩選以用於規範界限的語法。</span><span class="sxs-lookup"><span data-stu-id="90d51-161">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

<span data-ttu-id="90d51-162">以下是命令中每個參數的描述：</span><span class="sxs-lookup"><span data-stu-id="90d51-162">Here's a description of each parameter in the command:</span></span>
  
- <span data-ttu-id="90d51-163">`FilterName`：指定篩選器的名稱。</span><span class="sxs-lookup"><span data-stu-id="90d51-163">`FilterName`: Specifies the name of the filter.</span></span> <span data-ttu-id="90d51-164">使用描述或識別篩選所用的代理人的名稱。</span><span class="sxs-lookup"><span data-stu-id="90d51-164">Use a name that describes or identifies the agency that the filter is used in.</span></span>

- <span data-ttu-id="90d51-165">`Users`：指定套用此篩選器的使用者或群組，將其套用至執行的搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="90d51-165">`Users`: Specifies the users or groups who get this filter applied to the search actions they perform.</span></span> <span data-ttu-id="90d51-166">針對相容性界限，此參數會指定您在建立篩選的代理人中，您在步驟 3) 中所建立的角色群組 (。</span><span class="sxs-lookup"><span data-stu-id="90d51-166">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="90d51-167">附注這是多重值參數，因此您可以包含一或多個角色群組，以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="90d51-167">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span>

- <span data-ttu-id="90d51-168">`Filters`：指定篩選的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="90d51-168">`Filters`: Specifies the search criteria for the filter.</span></span> <span data-ttu-id="90d51-169">針對規範界限，您可以定義下列篩選器。</span><span class="sxs-lookup"><span data-stu-id="90d51-169">For the compliance boundaries, you define the following filters.</span></span> <span data-ttu-id="90d51-170">每個套用至內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-170">Each one applies to a content location.</span></span>

    - <span data-ttu-id="90d51-171">`Mailbox`：指定參數中定義的角色群組可以搜尋的信箱或 OneDrive 帳戶 `Users` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-171">`Mailbox`: Specifies the mailboxes or OneDrive accounts that the role groups defined in the `Users` parameter can search.</span></span> <span data-ttu-id="90d51-172">此篩選器允許角色群組的成員只搜尋特定機構中的信箱或 OneDrive 帳戶;例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-172">This filter allows members of the role group to search only the mailboxes or OneDrive accounts in a specific agency; for example, `"Mailbox_Department -eq 'FourthCoffee'"`.</span></span>

    - <span data-ttu-id="90d51-173">`Site_Path`：指定參數中定義的角色群組 `Users` 可以進行搜尋的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="90d51-173">`Site_Path`: Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="90d51-174">*SharePointURL* 會指定該角色群組的成員可以搜尋的代理人中的網站。</span><span class="sxs-lookup"><span data-stu-id="90d51-174">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search.</span></span> <span data-ttu-id="90d51-175">例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。</span><span class="sxs-lookup"><span data-stu-id="90d51-175">For example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`.</span></span> <span data-ttu-id="90d51-176">請注意 `Site` ， `Site_Path` 篩選器是由 **-或** 運算子所連接。</span><span class="sxs-lookup"><span data-stu-id="90d51-176">Notice the `Site` and `Site_Path` filters are connected by an **-or** operator.</span></span>

     > [!NOTE]
     > <span data-ttu-id="90d51-177">參數的語法 `Filters` 包含 *篩選器清單*。</span><span class="sxs-lookup"><span data-stu-id="90d51-177">The syntax for the `Filters` parameter includes a *filters list*.</span></span> <span data-ttu-id="90d51-178">篩選清單是一個包含信箱篩選器和以逗號分隔的網站路徑篩選器的篩選器。</span><span class="sxs-lookup"><span data-stu-id="90d51-178">A filters list is a filter that includes a mailbox filter and a site path filter separated by a comma.</span></span> <span data-ttu-id="90d51-179">在上面的範例中，請注意，逗號分隔 **Mailbox_MailboxPropertyName** 和 **Site_Path**： `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-179">In the previous example, notice that a comma separates **Mailbox_MailboxPropertyName** and **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"`.</span></span> <span data-ttu-id="90d51-180">在執行內容搜尋時處理此篩選器時，會從 [篩選] 清單中建立兩個搜尋許可權篩選：一個信箱篩選器和一個 SharePoint 篩選器。</span><span class="sxs-lookup"><span data-stu-id="90d51-180">When this filter is processed during the running of a content search, two search permissions filters are created from the filters list: one mailbox filter and one SharePoint filter.</span></span> <span data-ttu-id="90d51-181">使用篩選器清單的另一種方法是，為每個代理人建立兩個不同的「搜尋許可權」篩選：信箱屬性的單一搜尋許可權篩選，以及 SharePoint 網站屬性的一個篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-181">An alternative to using a filters list would be to create two separate search permissions filters for each agency: one search permissions filter for the mailbox attribute and one filter for the SharePoint site attributes.</span></span> <span data-ttu-id="90d51-182">在任何情況下，結果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="90d51-182">In either case, the results will be the same.</span></span> <span data-ttu-id="90d51-183">使用篩選清單或建立個別的「搜尋許可權」篩選是很重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="90d51-183">Using a filters list or creating separate search permissions filters is a matter of preference.</span></span>

- <span data-ttu-id="90d51-184">`Action`：指定篩選所套用的搜尋動作類型。</span><span class="sxs-lookup"><span data-stu-id="90d51-184">`Action`: Specifies the type of search action the filter is applied to.</span></span> <span data-ttu-id="90d51-185">例如，  `-Action Search` 只有當參數中定義的角色群組的成員執行搜尋時，才會套用篩選器 `Users` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-185">For example,  `-Action Search` would only apply the filter when members of the role group defined in the `Users` parameter run a search.</span></span> <span data-ttu-id="90d51-186">在此情況下，匯出搜尋結果時不會套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="90d51-186">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="90d51-187">針對規範界限，請使用，  `-Action All` 篩選器會套用到所有的搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="90d51-187">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 

    <span data-ttu-id="90d51-188">如需搜尋動作的清單，請參閱 [設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的「New-ComplianceSecurityFilter」一節。</span><span class="sxs-lookup"><span data-stu-id="90d51-188">For a list of the search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>

<span data-ttu-id="90d51-189">以下是為了支援 Contoso 合規性界限案例所會建立的兩個搜尋權限篩選範例。</span><span class="sxs-lookup"><span data-stu-id="90d51-189">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span> <span data-ttu-id="90d51-190">這兩個範例都包含逗號分隔篩選清單，信箱和網站篩選會包含在相同的搜尋權限篩選中，並以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="90d51-190">Both of these examples include a comma-separated filters list, in which the mailbox and site filters are included in the same search permissions filter and are separated by a comma.</span></span>
  
### <a name="fourth-coffee"></a><span data-ttu-id="90d51-191">第四個咖啡</span><span class="sxs-lookup"><span data-stu-id="90d51-191">Fourth Coffee</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a><span data-ttu-id="90d51-192">Coho Winery</span><span class="sxs-lookup"><span data-stu-id="90d51-192">Coho Winery</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a><span data-ttu-id="90d51-193">步驟4：建立內部公司調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="90d51-193">Step 4: Create an eDiscovery case for intra-agency investigations</span></span>

<span data-ttu-id="90d51-194">最後一個步驟是在 Microsoft 365 合規性中心中建立核心 eDiscovery 案例或 Advanced eDiscovery 案例，然後將您在步驟2中建立的角色群組新增為案例成員。</span><span class="sxs-lookup"><span data-stu-id="90d51-194">The final step is to create a Core eDiscovery case or Advanced eDiscovery case in the Microsoft 365 compliance center and then add the role group that you created in Step 2 as a member of the case.</span></span> <span data-ttu-id="90d51-195">這會產生使用規範界限的兩個重要特徵：</span><span class="sxs-lookup"><span data-stu-id="90d51-195">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="90d51-196">只有新增至案例之角色群組的成員，才能夠在安全性 & 規範中心中查看和存取案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-196">Only members of the role group added to the case will be able to see and access the case in the Security & Compliance Center.</span></span> <span data-ttu-id="90d51-197">例如，如果第四個「咖啡調查人員」角色群組是案例的唯一成員，則第四個咖啡 eDiscovery 管理員角色群組的成員 (或任何其他角色群組的成員) 將無法查看或存取此案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-197">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>

- <span data-ttu-id="90d51-198">當指派給案例的角色群組成員執行與案例相關聯的搜尋時，他們只能夠搜尋其組織內的內容位置， (由您在步驟3中建立的「搜尋許可權」篩選所定義。 ) </span><span class="sxs-lookup"><span data-stu-id="90d51-198">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 3.)</span></span>

<span data-ttu-id="90d51-199">若要建立案例並指派成員：</span><span class="sxs-lookup"><span data-stu-id="90d51-199">To create a case and assign members:</span></span>

1. <span data-ttu-id="90d51-200">移至 Microsoft 365 合規性中心中的 **核心 eDiscovery** 或 **Advanced eDiscovery** 頁面，並建立案例。</span><span class="sxs-lookup"><span data-stu-id="90d51-200">Go to the **Core eDiscovery** or **Advanced eDiscovery** page in the Microsoft 365 compliance center and create a case.</span></span>

2. <span data-ttu-id="90d51-201">在案例清單中，按一下您建立的案例名稱。</span><span class="sxs-lookup"><span data-stu-id="90d51-201">In the list of cases, click the name of the case you created.</span></span>

3. <span data-ttu-id="90d51-202">將角色群組新增為案例的成員。</span><span class="sxs-lookup"><span data-stu-id="90d51-202">Add role groups as members to the case.</span></span> <span data-ttu-id="90d51-203">如需相關指示，請參閱下列其中一篇文章：</span><span class="sxs-lookup"><span data-stu-id="90d51-203">For instructions, see the one of the following articles:</span></span>

   - [<span data-ttu-id="90d51-204">新增成員至核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="90d51-204">Add members to a Core eDiscovery case</span></span>](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [<span data-ttu-id="90d51-205">將成員新增至 Advanced eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="90d51-205">Add members to an Advanced eDiscovery case</span></span>](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> <span data-ttu-id="90d51-206">將角色群組新增至案例時，您只可以新增您是其成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="90d51-206">When adding a role group to a case, you can only add the role groups that you are a member of.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="90d51-207">在多地理位置環境中搜尋和匯出內容</span><span class="sxs-lookup"><span data-stu-id="90d51-207">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="90d51-208">搜尋許可權篩選也可讓您控制要匯出內容的位置，以及在[SharePoint 多地理位置環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中搜尋內容位置時可搜尋的資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-208">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).</span></span>
  
- <span data-ttu-id="90d51-209">**匯出搜尋結果：** 您可以從特定資料中心的 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90d51-209">**Export search results:** You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="90d51-210">這表示您可以指定要從中匯出搜尋結果的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-210">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="90d51-211">使用 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** Cmdlet 的 **Region** 參數，來建立或變更匯出將透過哪一個資料中心進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="90d51-211">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="90d51-212">**參數值**</span><span class="sxs-lookup"><span data-stu-id="90d51-212">**Parameter value**</span></span>|<span data-ttu-id="90d51-213">**資料中心位置**</span><span class="sxs-lookup"><span data-stu-id="90d51-213">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="90d51-214">NAM</span><span class="sxs-lookup"><span data-stu-id="90d51-214">NAM</span></span>  <br/> |<span data-ttu-id="90d51-215">北美 (資料中心是在美國) </span><span class="sxs-lookup"><span data-stu-id="90d51-215">North American (datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="90d51-216">EUR</span><span class="sxs-lookup"><span data-stu-id="90d51-216">EUR</span></span>  <br/> |<span data-ttu-id="90d51-217">歐洲</span><span class="sxs-lookup"><span data-stu-id="90d51-217">Europe</span></span>  <br/> |
    |<span data-ttu-id="90d51-218">APC</span><span class="sxs-lookup"><span data-stu-id="90d51-218">APC</span></span>  <br/> |<span data-ttu-id="90d51-219">亞太地區</span><span class="sxs-lookup"><span data-stu-id="90d51-219">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="90d51-220">CAN</span><span class="sxs-lookup"><span data-stu-id="90d51-220">CAN</span></span> <br/> |<span data-ttu-id="90d51-221">加拿大</span><span class="sxs-lookup"><span data-stu-id="90d51-221">Canada</span></span>|
    |||

- <span data-ttu-id="90d51-222">**路由內容搜尋：** 您可以將 SharePoint 網站和 OneDrive 帳戶的內容搜尋路由傳送至附屬資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-222">**Route content searches:** You can route the content searches of SharePoint sites and OneDrive accounts to a satellite datacenter.</span></span> <span data-ttu-id="90d51-223">這表示您可以指定將執行搜尋的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-223">This means you can specify the datacenter location where searches will be run.</span></span>

    <span data-ttu-id="90d51-224">使用 **Region** 參數的下列其中一個值，控制搜尋會在搜尋 SharePoint 網站和 OneDrive 帳戶時所執行的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-224">Use one of the following values for the **Region** parameter to control the datacenter location that searches will run in when searching SharePoint sites and OneDrive accounts.</span></span> 
  
    |<span data-ttu-id="90d51-225">**參數值**</span><span class="sxs-lookup"><span data-stu-id="90d51-225">**Parameter value**</span></span>|<span data-ttu-id="90d51-226">**SharePoint 的資料中心路由位置**</span><span class="sxs-lookup"><span data-stu-id="90d51-226">**Datacenter routing locations for SharePoint**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="90d51-227">NAM</span><span class="sxs-lookup"><span data-stu-id="90d51-227">NAM</span></span>  <br/> |<span data-ttu-id="90d51-228">我們</span><span class="sxs-lookup"><span data-stu-id="90d51-228">US</span></span>  <br/> |
    |<span data-ttu-id="90d51-229">EUR</span><span class="sxs-lookup"><span data-stu-id="90d51-229">EUR</span></span>  <br/> |<span data-ttu-id="90d51-230">歐洲</span><span class="sxs-lookup"><span data-stu-id="90d51-230">Europe</span></span>  <br/> |
    |<span data-ttu-id="90d51-231">APC</span><span class="sxs-lookup"><span data-stu-id="90d51-231">APC</span></span>  <br/> |<span data-ttu-id="90d51-232">亞太地區</span><span class="sxs-lookup"><span data-stu-id="90d51-232">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="90d51-233">CAN</span><span class="sxs-lookup"><span data-stu-id="90d51-233">CAN</span></span>  <br/> |<span data-ttu-id="90d51-234">我們</span><span class="sxs-lookup"><span data-stu-id="90d51-234">US</span></span>  <br/> |
    |<span data-ttu-id="90d51-235">AUS</span><span class="sxs-lookup"><span data-stu-id="90d51-235">AUS</span></span>  <br/> |<span data-ttu-id="90d51-236">亞太地區</span><span class="sxs-lookup"><span data-stu-id="90d51-236">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="90d51-237">KOR</span><span class="sxs-lookup"><span data-stu-id="90d51-237">KOR</span></span>  <br/> |<span data-ttu-id="90d51-238">組織的預設資料中心</span><span class="sxs-lookup"><span data-stu-id="90d51-238">The organization's default datacenter</span></span>  <br/> |
    |<span data-ttu-id="90d51-239">GBR</span><span class="sxs-lookup"><span data-stu-id="90d51-239">GBR</span></span>  <br/> |<span data-ttu-id="90d51-240">歐洲</span><span class="sxs-lookup"><span data-stu-id="90d51-240">Europe</span></span>  <br/> |
    |<span data-ttu-id="90d51-241">JPN</span><span class="sxs-lookup"><span data-stu-id="90d51-241">JPN</span></span>  <br/> |<span data-ttu-id="90d51-242">亞太地區</span><span class="sxs-lookup"><span data-stu-id="90d51-242">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="90d51-243">IND</span><span class="sxs-lookup"><span data-stu-id="90d51-243">IND</span></span>  <br/> |<span data-ttu-id="90d51-244">亞太地區</span><span class="sxs-lookup"><span data-stu-id="90d51-244">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="90d51-245">議員</span><span class="sxs-lookup"><span data-stu-id="90d51-245">LAM</span></span>  <br/> |<span data-ttu-id="90d51-246">我們</span><span class="sxs-lookup"><span data-stu-id="90d51-246">US</span></span>  <br/> |
    |<span data-ttu-id="90d51-247">也</span><span class="sxs-lookup"><span data-stu-id="90d51-247">NOR</span></span>  <br/> |<span data-ttu-id="90d51-248">歐洲</span><span class="sxs-lookup"><span data-stu-id="90d51-248">Europe</span></span> |
    |<span data-ttu-id="90d51-249">胸罩</span><span class="sxs-lookup"><span data-stu-id="90d51-249">BRA</span></span>  <br/> |<span data-ttu-id="90d51-250">北美資料中心</span><span class="sxs-lookup"><span data-stu-id="90d51-250">North American datacenters</span></span> |
    |||

   <span data-ttu-id="90d51-251">如果您未指定「搜尋許可權」篩選的 **Region** 參數，則會搜尋該組織的主要 SharePoint 區域。</span><span class="sxs-lookup"><span data-stu-id="90d51-251">If you don't specify the **Region** parameter for a search permissions filter, the organization's primary SharePoint region will be searched.</span></span> <span data-ttu-id="90d51-252">搜尋結果會匯出至最接近的資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-252">Search results are exported to the closest datacenter.</span></span>

   <span data-ttu-id="90d51-253">為了簡化概念， **Region** 參數會控制用來搜尋 SharePoint 和 OneDrive 中內容的資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-253">To simplify the concept, the **Region** parameter controls the datacenter that is used to search for content in SharePoint and OneDrive.</span></span> <span data-ttu-id="90d51-254">這不會套用至 Exchange 中搜尋內容，因為 Exchange 內容搜尋不會受資料中心地理位置的限制。</span><span class="sxs-lookup"><span data-stu-id="90d51-254">This doesn't apply to searching for content in Exchange because Exchange content searches aren't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="90d51-255">此外，相同的 **Region** 參數值也可能會規定匯出所傳送的資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-255">Also, the same **Region** parameter value may also dictate the datacenter that exports are routed through.</span></span> <span data-ttu-id="90d51-256">這通常是必要的方式，以跨地理 boarders 控制資料的移動。</span><span class="sxs-lookup"><span data-stu-id="90d51-256">This is often necessary to control the movement of data across geographic boarders.</span></span>

> [!NOTE]
> <span data-ttu-id="90d51-257">如果您正在使用 Advanced eDiscovery，則 **region** 參數不會控制從中匯出資料的區域。</span><span class="sxs-lookup"><span data-stu-id="90d51-257">If you're using Advanced eDiscovery, the **Region** parameter doesn't control the region that data is exported from.</span></span> <span data-ttu-id="90d51-258">資料是從組織的主要資料中心匯出。</span><span class="sxs-lookup"><span data-stu-id="90d51-258">Data is exported from the organization's primary datacenter.</span></span> <span data-ttu-id="90d51-259">此外，搜尋 SharePoint 和 OneDrive 中的內容並不受資料中心地理位置的限制。</span><span class="sxs-lookup"><span data-stu-id="90d51-259">Also, searching for content in SharePoint and OneDrive isn't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="90d51-260">會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-260">All datacenters are searched.</span></span> <span data-ttu-id="90d51-261">如需 Advanced eDiscovery 的詳細資訊，請參閱[Microsoft 365 中的 Advanced eDiscovery 解決方案概況](overview-ediscovery-20.md)。</span><span class="sxs-lookup"><span data-stu-id="90d51-261">For more information about Advanced eDiscovery, see [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).</span></span>

<span data-ttu-id="90d51-262">以下是在建立規範界限之搜尋許可權篩選時使用 **Region** 參數的範例。</span><span class="sxs-lookup"><span data-stu-id="90d51-262">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="90d51-263">這假設第四個咖啡分公司位於北美，且 Coho Winery 位於歐洲。</span><span class="sxs-lookup"><span data-stu-id="90d51-263">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

<span data-ttu-id="90d51-264">在多地理位置環境中搜尋和匯出內容時，請牢記下列事項。</span><span class="sxs-lookup"><span data-stu-id="90d51-264">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="90d51-265">**[地區]** 參數不會控制 Exchange 信箱的搜尋。</span><span class="sxs-lookup"><span data-stu-id="90d51-265">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="90d51-266">當您搜尋信箱時，會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-266">All datacenters will be searched when you search mailboxes.</span></span> <span data-ttu-id="90d51-267">若要限制搜尋 Exchange 信箱的範圍，請在建立或變更搜尋許可權篩選時使用 **Filters** 參數。</span><span class="sxs-lookup"><span data-stu-id="90d51-267">To limit the scope of which Exchange mailboxes are searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span>

- <span data-ttu-id="90d51-268">若要讓 ediscovery 管理員在多個 SharePoint 區域中進行搜尋，您需要為該 ediscovery 管理員建立不同的使用者帳戶，以在「搜尋許可權」篩選中使用，以指定 SharePoint 網站或 OneDrive 帳戶所在的地區。</span><span class="sxs-lookup"><span data-stu-id="90d51-268">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you need to create a different user account for that eDiscovery manager to use in the search permissions filter to specify the region where the SharePoint sites or OneDrive accounts are located.</span></span> <span data-ttu-id="90d51-269">如需設定此選項的詳細資訊，請參閱[內容搜尋](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)中的「在 SharePoint 多地理位置環境中搜尋內容」一節。</span><span class="sxs-lookup"><span data-stu-id="90d51-269">For more information about setting this up, see the "Searching for content in a SharePoint Multi-Geo environment" section in [Content Search](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).</span></span>

- <span data-ttu-id="90d51-270">在 SharePoint 和 OneDrive 中搜尋內容時， **Region** 參數會將搜尋導向主要或衛星位置，以 ediscovery 管理員進行 ediscovery 調查。</span><span class="sxs-lookup"><span data-stu-id="90d51-270">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the primary or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="90d51-271">[！注意] 如果 eDiscovery 管理員搜尋 SharePoint 和 OneDrive 「搜尋許可權」篩選中指定之區域以外的網站，將不會傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90d51-271">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results are returned.</span></span>

- <span data-ttu-id="90d51-272">匯出搜尋結果時，所有內容位置的內容 (包括 Exchange、商務用 Skype、SharePoint、OneDrive，以及您可以使用內容搜尋工具進行搜尋的其他服務) 會上載至 **Region** 參數所指定之資料中心的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-272">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive, and other services that you can search by using the Content Search tool) are uploaded to the Azure Storage location in the datacenter that's specified by the **Region** parameter.</span></span> <span data-ttu-id="90d51-273">這可協助組織在法規遵從性的情況中，不允許透過可控框線匯出內容。</span><span class="sxs-lookup"><span data-stu-id="90d51-273">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="90d51-274">如果 [搜尋許可權] 篩選中未指定任何區域，則會將內容上傳至組織的主要資料中心。</span><span class="sxs-lookup"><span data-stu-id="90d51-274">If no region is specified in the search permissions filter, content is uploaded to the organization's primary datacenter.</span></span>

- <span data-ttu-id="90d51-275">您可以執行下列命令來編輯現有的「搜尋許可權」篩選，以新增或變更區域：</span><span class="sxs-lookup"><span data-stu-id="90d51-275">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a><span data-ttu-id="90d51-276">使用 SharePoint hub 網站的規範界限</span><span class="sxs-lookup"><span data-stu-id="90d51-276">Using compliance boundaries for SharePoint hub sites</span></span>

<span data-ttu-id="90d51-277">[SharePoint hub 網站](/sharepoint/dev/features/hub-site/hub-site-overview)通常會與 eDiscovery 相容性邊界遵循的相同地理位置或代理商界限對齊。</span><span class="sxs-lookup"><span data-stu-id="90d51-277">[SharePoint hub sites](/sharepoint/dev/features/hub-site/hub-site-overview) often align with the same geographical or agency boundaries that eDiscovery compliance boundaries follow.</span></span> <span data-ttu-id="90d51-278">這表示您可以使用 hub 網站的 site ID 屬性來建立符合性界限。</span><span class="sxs-lookup"><span data-stu-id="90d51-278">That means you can use the site ID property of the hub site to create a compliance boundary.</span></span> <span data-ttu-id="90d51-279">若要這麼做，請在 SharePoint Online PowerShell 中使用[SPOHubSite 指令程式](/powershell/module/sharepoint-online/get-spohubsite#examples)，以取得 hub 網站的 SiteId，然後使用 [部門 ID] 屬性的此值建立搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-279">To do this, use the [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet in SharePoint Online PowerShell to obtain the SiteId for the hub site and then use this value for the department ID property to create a search permissions filter.</span></span>

<span data-ttu-id="90d51-280">使用下列語法為 SharePoint hub 網站建立搜尋許可權篩選：</span><span class="sxs-lookup"><span data-stu-id="90d51-280">Use the following syntax to create a search permissions filter for a SharePoint hub site:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

<span data-ttu-id="90d51-281">以下是為 Coho Winery agency 的 hub 網站建立搜尋許可權篩選的範例：</span><span class="sxs-lookup"><span data-stu-id="90d51-281">Here's an example of creating a search permissions filter for a hub site for the Coho Winery agency:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="90d51-282">規範界限限制</span><span class="sxs-lookup"><span data-stu-id="90d51-282">Compliance boundary limitations</span></span>

<span data-ttu-id="90d51-283">在管理使用性範圍的 eDiscovery 案例和調查時，請牢記下列限制。</span><span class="sxs-lookup"><span data-stu-id="90d51-283">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="90d51-284">在建立及執行搜尋時，您可以選取機構外部的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-284">When creating and running a search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="90d51-285">不過，由於搜尋權限篩選的緣故，這些位置的內容不會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="90d51-285">However, because of the search permissions filter, content from those locations isn't included in the search results.</span></span>

- <span data-ttu-id="90d51-286">合規性界限不適用於 eDiscovery 案例中的保留。</span><span class="sxs-lookup"><span data-stu-id="90d51-286">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="90d51-287">這表示某家機構中的電子文件探索管理員可以保留不同機構中的使用者。</span><span class="sxs-lookup"><span data-stu-id="90d51-287">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="90d51-288">不過，如果電子文件探索管理員針對處於保留狀態的使用者搜尋其內容位置，則會強制執行合規性界限。</span><span class="sxs-lookup"><span data-stu-id="90d51-288">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="90d51-289">這表示電子文件探索管理員將無法搜尋使用者的內容位置，即使其可以保留使用者也沒有用。</span><span class="sxs-lookup"><span data-stu-id="90d51-289">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>

    <span data-ttu-id="90d51-290">此外，保留統計資料只適用於機構中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90d51-290">Also, hold statistics will only apply to content locations in the agency.</span></span>

- <span data-ttu-id="90d51-291">如果您是指派「搜尋許可權」篩選 (信箱或網站篩選) ，而您嘗試匯出包含組織中所有 SharePoint 網站之搜尋的未編制索引項目目，您會收到下列錯誤訊息： `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-291">If you're assigned a search permissions filter (either a mailbox or a site filter) and you try to export unindexed items for a search that includes all SharePoint sites in your organization, you'll receive the following error message: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`.</span></span> <span data-ttu-id="90d51-292">如果您是指派「搜尋許可權」篩選，而且想要從 SharePoint 匯出未編制索引的專案，則必須重新執行搜尋，並包含特定 SharePoint 網站進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="90d51-292">If you're assigned a search permissions filter and you want to export unindexed items from SharePoint, you'll have to rerun the search and include specific SharePoint sites to search.</span></span> <span data-ttu-id="90d51-293">否則，您只可以從包含所有 SharePoint 網站的搜尋中匯出已編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90d51-293">Otherwise, you'll only be able to export indexed items from a search that includes all SharePoint sites.</span></span> <span data-ttu-id="90d51-294">如需有關匯出搜尋結果時的選項的詳細資訊，請參閱 [匯出內容搜尋結果](export-search-results.md#step-1-prepare-search-results-for-export)。</span><span class="sxs-lookup"><span data-stu-id="90d51-294">For more information about the options when you export search results, see [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).</span></span>

- <span data-ttu-id="90d51-295">搜尋權限篩選不會適用於 Exchange 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="90d51-295">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="more-information"></a><span data-ttu-id="90d51-296">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="90d51-296">More information</span></span>

- <span data-ttu-id="90d51-297">如果信箱已取消授權或虛刪除，使用者將不會被視為符合性界限內。</span><span class="sxs-lookup"><span data-stu-id="90d51-297">If a mailbox is de-licensed or soft-deleted, the user will no longer be considered within the compliance boundary.</span></span> <span data-ttu-id="90d51-298">如果信箱在刪除時保留在信箱上，保留在信箱中的內容仍受限於合規性界限或搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-298">If a hold was placed on the mailbox when it was deleted, the content preserved in the mailbox is still subject to a compliance boundary or search permissions filter.</span></span>

- <span data-ttu-id="90d51-299">如果為使用者執行規范界限和搜尋許可權篩選，建議您不要刪除使用者的信箱，而不是刪除其 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="90d51-299">If compliance boundaries and search permissions filters are implemented for a user, then we recommend that you don't delete a user's mailbox and not their OneDrive account.</span></span> <span data-ttu-id="90d51-300">換句話說，如果您刪除使用者的信箱，您也應該移除使用者的 OneDrive 帳戶，因為 mailbox_RecipientFilter 是用來強制 OneDrive 的搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-300">In other words, if you delete a user's mailbox, you should also remove the user's OneDrive account since mailbox_RecipientFilter is used to enforce search permission filter for OneDrive.</span></span>

- <span data-ttu-id="90d51-301">規範界限和搜尋許可權篩選器，取決於在 Exchange、OneDrive 和 SharePoint 中的內容上加蓋的屬性，以及此衝壓內容的後續編制索引。</span><span class="sxs-lookup"><span data-stu-id="90d51-301">Compliance boundaries and search permissions filters depend on attributes being stamped on content in Exchange, OneDrive, and SharePoint and the subsequent indexing of this stamped content.</span></span>

- <span data-ttu-id="90d51-302">建議您不要使用排除篩選 (例如 `-not()` 在搜尋許可權篩選) 中使用以內容為基礎的規範界限。</span><span class="sxs-lookup"><span data-stu-id="90d51-302">We don't recommend using exclusion filters (such as using `-not()` in a search permissions filter) for a content-based compliance boundary.</span></span> <span data-ttu-id="90d51-303">若最近更新之屬性的內容尚未編制索引，使用排除篩選可能會產生意外的結果。</span><span class="sxs-lookup"><span data-stu-id="90d51-303">Using an exclusion filter can have unexpected results if content with recently updated attributes hasn't been indexed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="90d51-304">常見問題集</span><span class="sxs-lookup"><span data-stu-id="90d51-304">Frequently asked questions</span></span>

<span data-ttu-id="90d51-305">**誰可以使用 New-ComplianceSecurityFilter 和 Set-ComplianceSecurityFilter Cmdlet) 來建立及管理搜尋許可權篩選 (？**</span><span class="sxs-lookup"><span data-stu-id="90d51-305">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets)?**</span></span>
  
<span data-ttu-id="90d51-306">若要建立、查看及修改搜尋許可權篩選，您必須是 Microsoft 365 規範中心內「組織管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90d51-306">To create, view, and modify search permissions filters, you have to be a member of the Organization Management role group in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="90d51-307">**若將 eDiscovery 管理員指派給跨越多個機關的一個以上角色群組，他們會如何在一個機構或另一個機構搜尋內容？**</span><span class="sxs-lookup"><span data-stu-id="90d51-307">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="90d51-308">EDiscovery 管理員可以將參數新增至其搜尋查詢，將搜尋限制在特定的代理人。</span><span class="sxs-lookup"><span data-stu-id="90d51-308">The eDiscovery manager can add parameters to their search query that restrict the search to a specific agency.</span></span> <span data-ttu-id="90d51-309">例如，如果組織已將 **CustomAttribute10** 屬性指定給不同的機構，他們可以在搜尋查詢中附加下列專案，以在特定機構中搜尋信箱和 OneDrive 帳戶：  `CustomAttribute10:<value>` 。</span><span class="sxs-lookup"><span data-stu-id="90d51-309">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value>`.</span></span>
  
<span data-ttu-id="90d51-310">**若在搜尋許可權篩選中做為符合性屬性的屬性值已變更，會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="90d51-310">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="90d51-311">搜尋許可權篩選會花三天的時間，以在篩選中所使用之屬性的值變更時，強制執行規范界限。</span><span class="sxs-lookup"><span data-stu-id="90d51-311">It takes up to three days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="90d51-312">例如，在 Contoso 案例中，第四個咖啡機關中的使用者會轉接至 Coho Winery agency。</span><span class="sxs-lookup"><span data-stu-id="90d51-312">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="90d51-313">因此，使用者物件上的 **部門** 屬性值會從 *FourthCoffee* 變更為 *CohoWinery*。</span><span class="sxs-lookup"><span data-stu-id="90d51-313">As a result, the value of the **Department** attribute on the user object is changed from *FourthCoffee* to *CohoWinery*.</span></span> <span data-ttu-id="90d51-314">在此情況下，第四個咖啡 eDiscovery 和投資者會在屬性變更後的三天內，取得該使用者的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90d51-314">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed.</span></span> <span data-ttu-id="90d51-315">同樣地，在 Coho Winery eDiscovery 管理員和調查人員取得使用者的搜尋結果之前，最多需要花三天。</span><span class="sxs-lookup"><span data-stu-id="90d51-315">Similarly, it takes up to three days before Coho Winery eDiscovery managers and investigators get search results for the user.</span></span>
  
<span data-ttu-id="90d51-316">**EDiscovery 管理員可以從兩個不同的規範界限查看內容嗎？**</span><span class="sxs-lookup"><span data-stu-id="90d51-316">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="90d51-317">是的，您可以在搜尋 Exchange 信箱時，將 eDiscovery 管理員新增至雙方可看到這兩個機構的角色群組進行。</span><span class="sxs-lookup"><span data-stu-id="90d51-317">Yes, this can be done when searching Exchange mailboxes by adding the eDiscovery manager to role groups that have visibility to both agencies.</span></span> <span data-ttu-id="90d51-318">不過，當搜尋 SharePoint 網站和 OneDrive 帳戶時，只有當機構位於相同地區或地理位置時，eDiscovery 管理員才能搜尋不同規範界限中的內容。</span><span class="sxs-lookup"><span data-stu-id="90d51-318">However when searching SharePoint sites and OneDrive accounts, an eDiscovery manager can search for content in different compliance boundaries only if the agencies are in the same region or geo location.</span></span> <span data-ttu-id="90d51-319">**附注：** 這種網站限制不適用於「高級 eDiscovery」，因為搜尋 SharePoint 中的內容，而且 OneDrive 並未依地理位置系結。</span><span class="sxs-lookup"><span data-stu-id="90d51-319">**Note:** This limitation for sites doesn't apply in Advanced eDiscovery because searching for content in SharePoint and OneDrive isn't bound by geographic location.</span></span>
  
<span data-ttu-id="90d51-320">**搜尋許可權篩選器適用于 eDiscovery 案例保留、Microsoft 365 保留原則或 DLP？**</span><span class="sxs-lookup"><span data-stu-id="90d51-320">**Do search permissions filters work for eDiscovery case holds, Microsoft 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="90d51-321">否，但目前未這麼做。</span><span class="sxs-lookup"><span data-stu-id="90d51-321">No, not at this time.</span></span>
  
<span data-ttu-id="90d51-322">**如果我指定區域來控制匯出內容的位置，但我在該地區沒有 SharePoint 組織，仍然可以搜尋 SharePoint 嗎？**</span><span class="sxs-lookup"><span data-stu-id="90d51-322">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="90d51-323">如果組織中的「搜尋許可權」篩選中所指定的地區不存在，則會搜尋預設區域。</span><span class="sxs-lookup"><span data-stu-id="90d51-323">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
<span data-ttu-id="90d51-324">**組織中可以建立的「搜尋許可權」篩選的數目上限為何？**</span><span class="sxs-lookup"><span data-stu-id="90d51-324">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="90d51-325">可在組織中建立的「搜尋許可權」篩選的數目沒有限制。</span><span class="sxs-lookup"><span data-stu-id="90d51-325">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="90d51-326">不過，當搜尋許可權篩選超過100時，搜尋效能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="90d51-326">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="90d51-327">若要盡可能使組織中的「搜尋許可權」篩選的數目盡可能小，請盡可能建立篩選，將 Exchange、SharePoint 及 OneDrive 的規則結合成單一搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="90d51-327">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
