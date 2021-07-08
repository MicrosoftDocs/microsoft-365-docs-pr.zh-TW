---
title: 設定電子文件探索調查的合規性界限
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
description: 了解如何使用合規性界限來建立邏輯界線，以控制電子文件探索管理員可在 Microsoft 365 中搜尋的使用者內容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be857277d36d95ac1cd974ccb0c87f2048798450
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194706"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a><span data-ttu-id="96f75-103">設定電子文件探索調查的合規性界限</span><span class="sxs-lookup"><span data-stu-id="96f75-103">Set up compliance boundaries for eDiscovery investigations</span></span>

<span data-ttu-id="96f75-104">本文中的指引可在使用核心電子文件探索或進階電子文件探索來管理調查時進行套用。</span><span class="sxs-lookup"><span data-stu-id="96f75-104">The guidance in this article can be applied when using either Core eDiscovery or Advanced eDiscovery to manage investigations.</span></span>

<span data-ttu-id="96f75-105">合規性界限可在組織中建立邏輯界限，以控制電子文件探索管理員可搜尋的使用者內容位置 (例如信箱、OneDrive 帳戶和 SharePoint 網站)。</span><span class="sxs-lookup"><span data-stu-id="96f75-105">Compliance boundaries create logical boundaries within an organization that control the user content locations (such as mailboxes, OneDrive accounts, and SharePoint sites) that eDiscovery managers can search.</span></span> <span data-ttu-id="96f75-106">另外，合規性界線也控制誰可以存取用來管理組織內部法律、人力資源或其他調查的電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-106">Also, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="96f75-107">必須遵守地理邊界和法規的跨國公司，以及往往會分割為不同機關的政府機構，常常必須有合規性界限的需要。</span><span class="sxs-lookup"><span data-stu-id="96f75-107">The need for compliance boundaries is often necessary for multi-national corporations that have to respect geographical boarders and regulations and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="96f75-108">在 Microsoft 365 中，合規性界限可協助您在執行內容搜尋及管理電子文件探索案例的調查時符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="96f75-108">In Microsoft 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="96f75-109">我們使用下列圖例中的範例來說明合規性界限運作的方式。</span><span class="sxs-lookup"><span data-stu-id="96f75-109">We use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合規性界限包含搜尋權限篩選，可控制對電子文件探索案例控制存取之機構與系統管理員角色群組的存取權](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
<span data-ttu-id="96f75-111">在此範例中，Contoso LTD 是由 Fourth Coffee 和 Coho Winery 這兩個子公司組成的組織。</span><span class="sxs-lookup"><span data-stu-id="96f75-111">In this example, Contoso LTD is an organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="96f75-112">這個企業要求電子文件探索管理員和調查人員只能搜尋其機構內的 Exchange 信箱、OneDrive 帳戶和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="96f75-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="96f75-113">電子文件探索管理員和調查人員也只能查看其機構中的電子文件探索案例，且只能存取其身為成員的案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-113">Also, eDiscovery managers and investigators can only see eDiscovery cases in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="96f75-114">此外，在此案例中調查人員無法保留內容位置，也無法從案例匯出內容。</span><span class="sxs-lookup"><span data-stu-id="96f75-114">Additionally in this scenario, investigators cannot place content locations on hold or export content from a case.</span></span> <span data-ttu-id="96f75-115">以下是合規性界限符合這些需求的方式。</span><span class="sxs-lookup"><span data-stu-id="96f75-115">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="96f75-116">內容搜尋中的搜尋權限篩選功能可控制電子文件探索管理員和調查人員可以搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-116">The search permissions filtering functionality in Content search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="96f75-117">這表示 Fourth Coffee 機構內的電子文件探索管理員和調查人員只能搜尋 Fourth Coffee 子公司內的內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-117">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="96f75-118">Coho Winery 子公司也有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-118">The same restriction applies to the Coho Winery subsidiary.</span></span>

- <span data-ttu-id="96f75-119">[角色群組](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery)提供以下的合規性界限功能：</span><span class="sxs-lookup"><span data-stu-id="96f75-119">[Role groups](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) provide the following functions for compliance boundaries:</span></span>

  - <span data-ttu-id="96f75-120">控制誰可以在 Microsoft 365 合規性中心查看電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-120">Control who can see the eDiscovery cases in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="96f75-121">這表示電子文件探索管理員和調查人員只能查看其機構內的電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-121">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>

  - <span data-ttu-id="96f75-122">控制誰能夠將成員指派給電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-122">Control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="96f75-123">這表示電子文件探索管理員和調查人員只能將成員指派給其本身為成員的案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-123">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>

  - <span data-ttu-id="96f75-124">控制成員可以新增或移除指派特定權限角色來執行的電子文件探索相關工作。</span><span class="sxs-lookup"><span data-stu-id="96f75-124">Control the eDiscovery-related tasks that members can perform by adding or removing roles that assign specific permissions.</span></span>

<span data-ttu-id="96f75-125">以下是設定合規性界限的流程：</span><span class="sxs-lookup"><span data-stu-id="96f75-125">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="96f75-126">步驟 1：識別使用者屬性以定義您的機構</span><span class="sxs-lookup"><span data-stu-id="96f75-126">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="96f75-127">步驟 2：為每個機構建立角色群組</span><span class="sxs-lookup"><span data-stu-id="96f75-127">Step 2: Create a role group for each agency</span></span>](#step-2-create-a-role-group-for-each-agency)

[<span data-ttu-id="96f75-128">步驟 3：建立搜尋權限篩選來強制執行合規性界限</span><span class="sxs-lookup"><span data-stu-id="96f75-128">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="96f75-129">步驟 4：建立電子文件探索案例以進行機構內部調查</span><span class="sxs-lookup"><span data-stu-id="96f75-129">Step 4: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a><span data-ttu-id="96f75-130">在設定合規性界限之前</span><span class="sxs-lookup"><span data-stu-id="96f75-130">Before you set up compliance boundaries</span></span>

- <span data-ttu-id="96f75-131">必須為使用者指派 Exchange Online 權限。</span><span class="sxs-lookup"><span data-stu-id="96f75-131">Users must be assigned an Exchange Online license.</span></span> <span data-ttu-id="96f75-132">若要確認此情況，請使用 Exchange Online PowerShell 中的 [Get-User](/powershell/module/exchange/get-user) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96f75-132">To verify this, use the [Get-User](/powershell/module/exchange/get-user) cmdlet in Exchange Online PowerShell.</span></span>

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="96f75-133">步驟 1：識別使用者屬性以定義您的機構</span><span class="sxs-lookup"><span data-stu-id="96f75-133">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="96f75-134">第一個步驟是選擇要用來定義您機構的屬性。</span><span class="sxs-lookup"><span data-stu-id="96f75-134">The first step is to choose an attribute to use that will define your agencies.</span></span> <span data-ttu-id="96f75-135">此屬性用來建立搜尋權限篩選，以限制電子文件探索管理員只搜尋獲指派此屬性特定值之使用者的內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-135">This attribute is used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="96f75-136">例如，假設 Contoso 決定使用 **[部門]** 屬性。</span><span class="sxs-lookup"><span data-stu-id="96f75-136">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="96f75-137">適用於 Fourth Coffee 子公司中使用者之此屬性的值會是 `FourthCoffee`，而 Coho Winery 子公司中使用者的值會是 `CohoWinery`。</span><span class="sxs-lookup"><span data-stu-id="96f75-137">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="96f75-138">在步驟 3 中，您使用此 `attribute:value` 組 (例如 *部門: FourthCoffee*) 來限制電子文件探索管理員可以搜尋的使用者內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-138">In Step 3, you use this  `attribute:value`  pair (for example, *Department:FourthCoffee*) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="96f75-139">以下是一些可用於合規性界限的使用者屬性範例：</span><span class="sxs-lookup"><span data-stu-id="96f75-139">Here are some examples of user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="96f75-140">公司</span><span class="sxs-lookup"><span data-stu-id="96f75-140">Company</span></span>

- <span data-ttu-id="96f75-141">CustomAttribute1 - CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="96f75-141">CustomAttribute1 - CustomAttribute15</span></span>

- <span data-ttu-id="96f75-142">部門</span><span class="sxs-lookup"><span data-stu-id="96f75-142">Department</span></span>

- <span data-ttu-id="96f75-143">辦公室</span><span class="sxs-lookup"><span data-stu-id="96f75-143">Office</span></span>

- <span data-ttu-id="96f75-144">CountryOrRegion (兩個字母的國碼 (地區碼))</span><span class="sxs-lookup"><span data-stu-id="96f75-144">CountryOrRegion (Two-letter country code)</span></span>

<span data-ttu-id="96f75-145">如需完整清單，請參閱支援的[信箱篩選](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)完整清單。</span><span class="sxs-lookup"><span data-stu-id="96f75-145">For a complete list, see the full list of supported [mailbox filters](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties).</span></span>

## <a name="step-2-create-a-role-group-for-each-agency"></a><span data-ttu-id="96f75-146">步驟 2：為每個機構建立角色群組</span><span class="sxs-lookup"><span data-stu-id="96f75-146">Step 2: Create a role group for each agency</span></span>

<span data-ttu-id="96f75-147">下一個步驟是在安全性與合規性中心中建立與您的機構對應的角色群組。</span><span class="sxs-lookup"><span data-stu-id="96f75-147">The next step is to create the role groups in the Security & Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="96f75-148">建議您複製內建的電子文件探索管理員群組、新增適當的成員，以及移除可能不適用於您需求的角色，來建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="96f75-148">We recommend that you create a role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="96f75-149">如需有關電子文件探索相關角色的資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="96f75-149">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="96f75-150">若要建立角色群組，請移至安全性與合規性中心內的 [權限]\*\*\*\* 頁面，然後為每個機構中將會使用合規性界限和電子文件探索案例來管理調查的每個小組建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="96f75-150">To create the role groups, go to the **Permissions** page in the Security & Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span>
  
<span data-ttu-id="96f75-151">使用 Contoso 合規性界限範例案例需要建立四個角色群組，並於個別其中新增適當的成員。</span><span class="sxs-lookup"><span data-stu-id="96f75-151">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="96f75-152">Fourth Coffee 電子文件探索管理員</span><span class="sxs-lookup"><span data-stu-id="96f75-152">Fourth Coffee eDiscovery Managers</span></span>

- <span data-ttu-id="96f75-153">Fourth Coffee 調查人員</span><span class="sxs-lookup"><span data-stu-id="96f75-153">Fourth Coffee Investigators</span></span>

- <span data-ttu-id="96f75-154">Coho Winery 電子文件探索管理員</span><span class="sxs-lookup"><span data-stu-id="96f75-154">Coho Winery eDiscovery Managers</span></span>

- <span data-ttu-id="96f75-155">Coho Winery 調查人員</span><span class="sxs-lookup"><span data-stu-id="96f75-155">Coho Winery Investigators</span></span>
  
<span data-ttu-id="96f75-156">若要符合 Contoso 合規性界限案例的需求，也請移除調查人員角色群組中的 [保留 **]** 和 [匯出 **]** 角色，以防止調查人員對內容位置進行保留並從案例中匯出內容。</span><span class="sxs-lookup"><span data-stu-id="96f75-156">To meet the requirements of the Contoso compliance boundaries scenario, you would also remove the **Hold** and **Export** roles from the investigators role groups to prevent investigators from placing holds on content locations and exporting content from a case.</span></span>

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="96f75-157">步驟 3：建立搜尋權限篩選來強制執行合規性界限</span><span class="sxs-lookup"><span data-stu-id="96f75-157">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="96f75-158">為每個機構建立角色群組後，下一個步驟是建立搜尋權限篩選，可將每個角色群組與其特定機構建立關聯，並定義自身的合規性界限。</span><span class="sxs-lookup"><span data-stu-id="96f75-158">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="96f75-159">您必須為每個機構建立一個搜尋權限篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-159">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="96f75-160">如需建立安全性權限篩選的詳細資訊，請參閱[設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="96f75-160">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="96f75-161">以下是用來建立用於合規性界限之搜尋權限篩選的語法。</span><span class="sxs-lookup"><span data-stu-id="96f75-161">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

<span data-ttu-id="96f75-162">以下是命令中每個參數的描述：</span><span class="sxs-lookup"><span data-stu-id="96f75-162">Here's a description of each parameter in the command:</span></span>
  
- <span data-ttu-id="96f75-163">`FilterName`：指定篩選的名稱。</span><span class="sxs-lookup"><span data-stu-id="96f75-163">`FilterName`: Specifies the name of the filter.</span></span> <span data-ttu-id="96f75-164">使用描述或識別使用篩選器之機構的名稱。</span><span class="sxs-lookup"><span data-stu-id="96f75-164">Use a name that describes or identifies the agency that the filter is used in.</span></span>

- <span data-ttu-id="96f75-165">`Users`：指定將這個篩選套用至其所執行之搜尋動作的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="96f75-165">`Users`: Specifies the users or groups who get this filter applied to the search actions they perform.</span></span> <span data-ttu-id="96f75-166">適用於合規性界限，此參數會指定您為其建立篩選的機構內角色群組 (在步驟 3 中建立)。</span><span class="sxs-lookup"><span data-stu-id="96f75-166">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="96f75-167">請注意此為多重值參數，因此您可以包含一或多個角色群組 (以逗號分隔)。</span><span class="sxs-lookup"><span data-stu-id="96f75-167">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span>

- <span data-ttu-id="96f75-168">`Filters`：指定篩選的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="96f75-168">`Filters`: Specifies the search criteria for the filter.</span></span> <span data-ttu-id="96f75-169">適用於合規性界限，您可以定義下列篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-169">For the compliance boundaries, you define the following filters.</span></span> <span data-ttu-id="96f75-170">每個都適用於一個內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-170">Each one applies to a content location.</span></span>

    - <span data-ttu-id="96f75-171">`Mailbox`：指定在 `Users` 參數中定義之角色群組可搜尋的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="96f75-171">`Mailbox`: Specifies the mailboxes or OneDrive accounts that the role groups defined in the `Users` parameter can search.</span></span> <span data-ttu-id="96f75-172">此篩選允許角色群組的成員只搜尋特定機構中的信箱或 OneDrive 帳戶；例如 `"Mailbox_Department -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="96f75-172">This filter allows members of the role group to search only the mailboxes or OneDrive accounts in a specific agency; for example, `"Mailbox_Department -eq 'FourthCoffee'"`.</span></span>

    - <span data-ttu-id="96f75-173">`Site_Path`：指定在 `Users` 參數中定義之角色群組可搜尋的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="96f75-173">`Site_Path`: Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="96f75-174">*SharePointURL* 指定角色群組成員可搜尋的機構中網站。</span><span class="sxs-lookup"><span data-stu-id="96f75-174">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search.</span></span> <span data-ttu-id="96f75-175">例如 `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。</span><span class="sxs-lookup"><span data-stu-id="96f75-175">For example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`.</span></span> <span data-ttu-id="96f75-176">請注意， `Site` 和 `Site_Path` 篩選是由 **或** 運算子所連接。</span><span class="sxs-lookup"><span data-stu-id="96f75-176">Notice the `Site` and `Site_Path` filters are connected by an **-or** operator.</span></span>

     > [!NOTE]
     > <span data-ttu-id="96f75-177">`Filters` 參數的語法包含 *篩選清單*。</span><span class="sxs-lookup"><span data-stu-id="96f75-177">The syntax for the `Filters` parameter includes a *filters list*.</span></span> <span data-ttu-id="96f75-178">篩選清單是包含信箱篩選和網站路徑篩選的篩選 (以逗號分隔)。</span><span class="sxs-lookup"><span data-stu-id="96f75-178">A filters list is a filter that includes a mailbox filter and a site path filter separated by a comma.</span></span> <span data-ttu-id="96f75-179">在之前範例中，請注意逗號會分隔 **Mailbox_MailboxPropertyName** 和 **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"`。</span><span class="sxs-lookup"><span data-stu-id="96f75-179">In the previous example, notice that a comma separates **Mailbox_MailboxPropertyName** and **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"`.</span></span> <span data-ttu-id="96f75-180">當在內容搜尋執行期間處理此篩選時，系統會從篩選清單建立兩個搜尋權限篩選：一個信箱篩選器和一個 SharePoint 篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-180">When this filter is processed during the running of a content search, two search permissions filters are created from the filters list: one mailbox filter and one SharePoint filter.</span></span> <span data-ttu-id="96f75-181">另一個您可以使用的篩選清單替代方案則是為每個機構建立兩個個別的搜尋權限篩選：一個信箱屬性的搜尋權限篩選，以及一個 SharePoint 網站屬性的篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-181">An alternative to using a filters list would be to create two separate search permissions filters for each agency: one search permissions filter for the mailbox attribute and one filter for the SharePoint site attributes.</span></span> <span data-ttu-id="96f75-182">任何情況的結果都會相同。</span><span class="sxs-lookup"><span data-stu-id="96f75-182">In either case, the results will be the same.</span></span> <span data-ttu-id="96f75-183">請按照您的偏好使用篩選清單或建立個別的搜尋權限篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-183">Using a filters list or creating separate search permissions filters is a matter of preference.</span></span>

- <span data-ttu-id="96f75-184">`Action`：指定篩選要套用至的搜尋動作類型。</span><span class="sxs-lookup"><span data-stu-id="96f75-184">`Action`: Specifies the type of search action the filter is applied to.</span></span> <span data-ttu-id="96f75-185">例如， `-Action Search` 只有當在 `Users` 參數中定義的角色群組成員執行搜尋時，才會套用篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-185">For example,  `-Action Search` would only apply the filter when members of the role group defined in the `Users` parameter run a search.</span></span> <span data-ttu-id="96f75-186">在這種情況下，匯出搜尋結果時不會套用篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-186">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="96f75-187">適用於合規性界限，請使用 `-Action All` 以讓篩選套用至所有搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="96f75-187">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 

    <span data-ttu-id="96f75-188">如需搜尋動作的清單，請參閱 [設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的 <New-ComplianceSecurityFilter> 一節。</span><span class="sxs-lookup"><span data-stu-id="96f75-188">For a list of the search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>

<span data-ttu-id="96f75-189">以下是為了支援 Contoso 合規性界限案例所會建立的兩個搜尋權限篩選範例。</span><span class="sxs-lookup"><span data-stu-id="96f75-189">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span> <span data-ttu-id="96f75-190">這兩個範例都包含逗號分隔篩選清單，信箱和網站篩選會包含在相同的搜尋權限篩選中，並以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="96f75-190">Both of these examples include a comma-separated filters list, in which the mailbox and site filters are included in the same search permissions filter and are separated by a comma.</span></span>
  
### <a name="fourth-coffee"></a><span data-ttu-id="96f75-191">Fourth Coffee</span><span class="sxs-lookup"><span data-stu-id="96f75-191">Fourth Coffee</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a><span data-ttu-id="96f75-192">Coho Winery</span><span class="sxs-lookup"><span data-stu-id="96f75-192">Coho Winery</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a><span data-ttu-id="96f75-193">步驟 4：建立電子文件探索案例以進行機構內部調查</span><span class="sxs-lookup"><span data-stu-id="96f75-193">Step 4: Create an eDiscovery case for intra-agency investigations</span></span>

<span data-ttu-id="96f75-194">最後一個步驟是在 Microsoft 365 合規性中心建立核心電子文件探索案例或進階電子文件探索案例，然後將在步驟 2 中建立的角色群組新增為案例的成員。</span><span class="sxs-lookup"><span data-stu-id="96f75-194">The final step is to create a Core eDiscovery case or Advanced eDiscovery case in the Microsoft 365 compliance center and then add the role group that you created in Step 2 as a member of the case.</span></span> <span data-ttu-id="96f75-195">這會造成使用合規性界限的兩個重要特性結果：</span><span class="sxs-lookup"><span data-stu-id="96f75-195">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="96f75-196">只有新增到案例的角色群組成員才能在安全性與合規性中心查看和存取案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-196">Only members of the role group added to the case will be able to see and access the case in the Security & Compliance Center.</span></span> <span data-ttu-id="96f75-197">例如，如果 Fourth Coffee 調查人員角色群組是案例的唯一成員，則 Fourth Coffee 電子文件探索管理員角色群組的成員 (或任何其他角色群組的成員) 都無法查看或存取案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-197">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>

- <span data-ttu-id="96f75-198">當角色群組成員獲指派跟該案例相關聯的搜尋案例時，他們只能搜尋其機構內的內容位置 (由您於步驟 3 中建立之搜尋權限篩選所定義)。</span><span class="sxs-lookup"><span data-stu-id="96f75-198">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 3.)</span></span>

<span data-ttu-id="96f75-199">若要建立案例並指派成員：</span><span class="sxs-lookup"><span data-stu-id="96f75-199">To create a case and assign members:</span></span>

1. <span data-ttu-id="96f75-200">前往 Microsoft 365 合規性中心的 **核心電子文件探索** 或 **進階電子文件探索** 頁面，然後建立案例。</span><span class="sxs-lookup"><span data-stu-id="96f75-200">Go to the **Core eDiscovery** or **Advanced eDiscovery** page in the Microsoft 365 compliance center and create a case.</span></span>

2. <span data-ttu-id="96f75-201">在案例清單中，按一下您建立的案例名稱。</span><span class="sxs-lookup"><span data-stu-id="96f75-201">In the list of cases, click the name of the case you created.</span></span>

3. <span data-ttu-id="96f75-202">將角色群組新增為案例的成員。</span><span class="sxs-lookup"><span data-stu-id="96f75-202">Add role groups as members to the case.</span></span> <span data-ttu-id="96f75-203">如需指示，請參閱下列其中一個文章：</span><span class="sxs-lookup"><span data-stu-id="96f75-203">For instructions, see the one of the following articles:</span></span>

   - [<span data-ttu-id="96f75-204">將成員新增至核心電子文件探索案例</span><span class="sxs-lookup"><span data-stu-id="96f75-204">Add members to a Core eDiscovery case</span></span>](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [<span data-ttu-id="96f75-205">將成員新增至進階電子文件探索案例</span><span class="sxs-lookup"><span data-stu-id="96f75-205">Add members to an Advanced eDiscovery case</span></span>](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> <span data-ttu-id="96f75-206">將角色群組新增至案例時，您只可以新增您身為其中成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="96f75-206">When adding a role group to a case, you can only add the role groups that you are a member of.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="96f75-207">在多地理位置環境中搜尋和匯出內容</span><span class="sxs-lookup"><span data-stu-id="96f75-207">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="96f75-208">搜尋權限篩選也讓您控制內容要路由傳送以匯出的位置，以及當搜尋 [SharePoint 多地理位置環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中的內容位置時，可以搜尋的資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-208">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).</span></span>
  
- <span data-ttu-id="96f75-209">**匯出搜尋結果：** 您可以從 Exchange 信箱、SharePoint 網站和特定資料中心中的 One Drive 帳戶中匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="96f75-209">**Export search results:** You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="96f75-210">這表示您可以指定搜尋結果匯出來源的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-210">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="96f75-211">為 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** 　Cmdlet 使用 [地區 **]** 參數來建立或變更匯出要路由傳送經過的資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-211">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="96f75-212">**參數值**</span><span class="sxs-lookup"><span data-stu-id="96f75-212">**Parameter value**</span></span>|<span data-ttu-id="96f75-213">**資料中心位置**</span><span class="sxs-lookup"><span data-stu-id="96f75-213">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="96f75-214">NAM</span><span class="sxs-lookup"><span data-stu-id="96f75-214">NAM</span></span>  <br/> |<span data-ttu-id="96f75-215">北美洲 (資料中心位於美國)</span><span class="sxs-lookup"><span data-stu-id="96f75-215">North American (datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="96f75-216">EUR</span><span class="sxs-lookup"><span data-stu-id="96f75-216">EUR</span></span>  <br/> |<span data-ttu-id="96f75-217">歐洲</span><span class="sxs-lookup"><span data-stu-id="96f75-217">Europe</span></span>  <br/> |
    |<span data-ttu-id="96f75-218">APC</span><span class="sxs-lookup"><span data-stu-id="96f75-218">APC</span></span>  <br/> |<span data-ttu-id="96f75-219">亞太地區</span><span class="sxs-lookup"><span data-stu-id="96f75-219">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="96f75-220">CAN</span><span class="sxs-lookup"><span data-stu-id="96f75-220">CAN</span></span> <br/> |<span data-ttu-id="96f75-221">加拿大</span><span class="sxs-lookup"><span data-stu-id="96f75-221">Canada</span></span>|
    |||

- <span data-ttu-id="96f75-222">**路由內容搜尋：** 您可以將 SharePoint 網站和 OneDrive 帳戶的內容搜尋路由傳送至衛星資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-222">**Route content searches:** You can route the content searches of SharePoint sites and OneDrive accounts to a satellite datacenter.</span></span> <span data-ttu-id="96f75-223">這表示您可以指定要執行搜尋的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-223">This means you can specify the datacenter location where searches will be run.</span></span>

    <span data-ttu-id="96f75-224">為 [地區 **]** 參數使用以下其中一個值，來控制搜尋 SharePoint 網站和 OneDrive 帳戶時會執行搜尋的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-224">Use one of the following values for the **Region** parameter to control the datacenter location that searches will run in when searching SharePoint sites and OneDrive accounts.</span></span> 
  
    |<span data-ttu-id="96f75-225">**參數值**</span><span class="sxs-lookup"><span data-stu-id="96f75-225">**Parameter value**</span></span>|<span data-ttu-id="96f75-226">**SharePoint 的資料中心路由位置**</span><span class="sxs-lookup"><span data-stu-id="96f75-226">**Datacenter routing locations for SharePoint**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="96f75-227">NAM</span><span class="sxs-lookup"><span data-stu-id="96f75-227">NAM</span></span>  <br/> |<span data-ttu-id="96f75-228">美國</span><span class="sxs-lookup"><span data-stu-id="96f75-228">US</span></span>  <br/> |
    |<span data-ttu-id="96f75-229">EUR</span><span class="sxs-lookup"><span data-stu-id="96f75-229">EUR</span></span>  <br/> |<span data-ttu-id="96f75-230">歐洲</span><span class="sxs-lookup"><span data-stu-id="96f75-230">Europe</span></span>  <br/> |
    |<span data-ttu-id="96f75-231">APC</span><span class="sxs-lookup"><span data-stu-id="96f75-231">APC</span></span>  <br/> |<span data-ttu-id="96f75-232">亞太地區</span><span class="sxs-lookup"><span data-stu-id="96f75-232">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="96f75-233">CAN</span><span class="sxs-lookup"><span data-stu-id="96f75-233">CAN</span></span>  <br/> |<span data-ttu-id="96f75-234">美國</span><span class="sxs-lookup"><span data-stu-id="96f75-234">US</span></span>  <br/> |
    |<span data-ttu-id="96f75-235">AUS</span><span class="sxs-lookup"><span data-stu-id="96f75-235">AUS</span></span>  <br/> |<span data-ttu-id="96f75-236">亞太地區</span><span class="sxs-lookup"><span data-stu-id="96f75-236">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="96f75-237">KOR</span><span class="sxs-lookup"><span data-stu-id="96f75-237">KOR</span></span>  <br/> |<span data-ttu-id="96f75-238">組織的預設資料中心</span><span class="sxs-lookup"><span data-stu-id="96f75-238">The organization's default datacenter</span></span>  <br/> |
    |<span data-ttu-id="96f75-239">GBR</span><span class="sxs-lookup"><span data-stu-id="96f75-239">GBR</span></span>  <br/> |<span data-ttu-id="96f75-240">歐洲</span><span class="sxs-lookup"><span data-stu-id="96f75-240">Europe</span></span>  <br/> |
    |<span data-ttu-id="96f75-241">JPN</span><span class="sxs-lookup"><span data-stu-id="96f75-241">JPN</span></span>  <br/> |<span data-ttu-id="96f75-242">亞太地區</span><span class="sxs-lookup"><span data-stu-id="96f75-242">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="96f75-243">IND</span><span class="sxs-lookup"><span data-stu-id="96f75-243">IND</span></span>  <br/> |<span data-ttu-id="96f75-244">亞太地區</span><span class="sxs-lookup"><span data-stu-id="96f75-244">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="96f75-245">LAM</span><span class="sxs-lookup"><span data-stu-id="96f75-245">LAM</span></span>  <br/> |<span data-ttu-id="96f75-246">美國</span><span class="sxs-lookup"><span data-stu-id="96f75-246">US</span></span>  <br/> |
    |<span data-ttu-id="96f75-247">NOR</span><span class="sxs-lookup"><span data-stu-id="96f75-247">NOR</span></span>  <br/> |<span data-ttu-id="96f75-248">歐洲</span><span class="sxs-lookup"><span data-stu-id="96f75-248">Europe</span></span> |
    |<span data-ttu-id="96f75-249">BRA</span><span class="sxs-lookup"><span data-stu-id="96f75-249">BRA</span></span>  <br/> |<span data-ttu-id="96f75-250">北美洲資料中心</span><span class="sxs-lookup"><span data-stu-id="96f75-250">North American datacenters</span></span> |
    |||

   <span data-ttu-id="96f75-251">如果您未指定搜尋權限權篩選的 [地區 **]** 參數，系統便會搜尋組織的主要 SharePoint 地區。</span><span class="sxs-lookup"><span data-stu-id="96f75-251">If you don't specify the **Region** parameter for a search permissions filter, the organization's primary SharePoint region will be searched.</span></span> <span data-ttu-id="96f75-252">搜尋結果會匯出至最接近的資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-252">Search results are exported to the closest datacenter.</span></span>

   <span data-ttu-id="96f75-253">為了簡化概念，[地區 **]** 參數會控制用來搜尋 SharePoint 和 OneDrive 中內容的資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-253">To simplify the concept, the **Region** parameter controls the datacenter that is used to search for content in SharePoint and OneDrive.</span></span> <span data-ttu-id="96f75-254">這不適用於在 Exchange 中搜尋內容，因為 Exchange 內容搜尋不受資料中心的地理位置所限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-254">This doesn't apply to searching for content in Exchange because Exchange content searches aren't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="96f75-255">此外，相同的 [地區 **]** 參數值可能也會指定匯出要路由傳送經過的資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-255">Also, the same **Region** parameter value may also dictate the datacenter that exports are routed through.</span></span> <span data-ttu-id="96f75-256">這通常是控制跨地理邊界資料的移動時所必須。</span><span class="sxs-lookup"><span data-stu-id="96f75-256">This is often necessary to control the movement of data across geographic boarders.</span></span>

> [!NOTE]
> <span data-ttu-id="96f75-257">如果您使用的是進階電子文件探索，[地區 **]** 參數不會控制資料的匯出來源地區。</span><span class="sxs-lookup"><span data-stu-id="96f75-257">If you're using Advanced eDiscovery, the **Region** parameter doesn't control the region that data is exported from.</span></span> <span data-ttu-id="96f75-258">資料會從組織的中央位置匯出。</span><span class="sxs-lookup"><span data-stu-id="96f75-258">Data is exported from the organization's central location.</span></span> <span data-ttu-id="96f75-259">此外，在 SharePoint 和 OneDrive 中搜尋內容不受資料中心的地理位置限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-259">Also, searching for content in SharePoint and OneDrive isn't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="96f75-260">系統會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-260">All datacenters are searched.</span></span> <span data-ttu-id="96f75-261">如需進階電子文件探索的詳細資訊，請參閱 [Microsoft 365 進階電子文件探索解決方案概述](overview-ediscovery-20.md)。</span><span class="sxs-lookup"><span data-stu-id="96f75-261">For more information about Advanced eDiscovery, see [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).</span></span>

<span data-ttu-id="96f75-262">以下是建立合規性界限的搜尋權限權篩選時使用的 [地區 **]** 參數範例。</span><span class="sxs-lookup"><span data-stu-id="96f75-262">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="96f75-263">這假設 Fourth Coffee 子公司位於北美洲，而 Coho Winery 則位於歐洲。</span><span class="sxs-lookup"><span data-stu-id="96f75-263">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

<span data-ttu-id="96f75-264">在多地理位置環境中搜尋和匯出內容時，請留意下列事項。</span><span class="sxs-lookup"><span data-stu-id="96f75-264">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="96f75-265">[地區 **]** 參數不會控制 Exchange 信箱的搜尋。</span><span class="sxs-lookup"><span data-stu-id="96f75-265">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="96f75-266">搜尋信箱時，也會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-266">All datacenters will be searched when you search mailboxes.</span></span> <span data-ttu-id="96f75-267">若要限制搜尋 Exchange 信箱的範圍，請在建立或變更搜尋權限篩選時使用 [篩選 **]** 參數。</span><span class="sxs-lookup"><span data-stu-id="96f75-267">To limit the scope of which Exchange mailboxes are searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span>

- <span data-ttu-id="96f75-268">如果電子文件探索管理員必須跨多個 SharePoint 地區搜尋，請務必為電子文件探索管理員員建立不同的使用者帳戶在搜尋權限篩選中使用，以用來指定 SharePoint 網站或 OneDrive 帳戶所在的地區。</span><span class="sxs-lookup"><span data-stu-id="96f75-268">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you need to create a different user account for that eDiscovery manager to use in the search permissions filter to specify the region where the SharePoint sites or OneDrive accounts are located.</span></span> <span data-ttu-id="96f75-269">如需有關設定此項目的資訊，請參閱[內容搜尋](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)中的 <搜尋 SharePoint 多地理位置環境中的內容> 一節。</span><span class="sxs-lookup"><span data-stu-id="96f75-269">For more information about setting this up, see the "Searching for content in a SharePoint Multi-Geo environment" section in [Content Search](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).</span></span>

- <span data-ttu-id="96f75-270">在 SharePoint 和 OneDrive 中搜尋內容時，[地區 **]** 參數會將搜尋導向至電子文件探索管理員會進行電子文件探索調查的主要或衛星位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-270">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the primary or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="96f75-271">如果電子文件探索管理員搜尋搜尋權限篩選指定之區域以外的 SharePoint 和 OneDrive 網站，則不會傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="96f75-271">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results are returned.</span></span>

- <span data-ttu-id="96f75-272">從核心電子文件探索匯出搜尋結果時，來自所有內容位置的內容 (包括 Exchange、商務用 Skype、SharePoint、OneDrive，以及您可以使用 [內容搜尋] 工具搜尋的其他服務) 會上傳至由 [地區 **]** 參數所指定之資料中心的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-272">When exporting search results from Core eDiscovery, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive, and other services that you can search by using the Content Search tool) are uploaded to the Azure Storage location in the datacenter that's specified by the **Region** parameter.</span></span> <span data-ttu-id="96f75-273">這可協助組織不允許跨受控制邊界匯出內容而保持合規性。</span><span class="sxs-lookup"><span data-stu-id="96f75-273">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="96f75-274">如果在搜尋權限篩選中未指定任何地區，則內容會上傳到組織的主要資料中心。</span><span class="sxs-lookup"><span data-stu-id="96f75-274">If no region is specified in the search permissions filter, content is uploaded to the organization's primary datacenter.</span></span>

  <span data-ttu-id="96f75-275">從進階電子文件探索匯出內容時，您無法使用 [地區 **]** 參數控制內容的上傳位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-275">When exporting content from Advanced eDiscovery, you can't control where content is uploaded by using the **Region** parameter.</span></span> <span data-ttu-id="96f75-276">內容會上傳到貴組織中央位置資料中心中的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-276">Content is uploaded to an Azure Storage location in a datacenter in your organization's central location.</span></span> <span data-ttu-id="96f75-277">如需根據您中央位置的地理位置清單，請參閱 [Microsoft 365 多地理位置電子文件探索設定](../enterprise/multi-geo-ediscovery-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="96f75-277">For a list of geo locations based on your central location, see [Microsoft 365 Multi-Geo eDiscovery configuration](../enterprise/multi-geo-ediscovery-configuration.md).</span></span>

- <span data-ttu-id="96f75-278">您可以執行下列命令，編輯現有的搜尋權限篩選以新增或變更地區：</span><span class="sxs-lookup"><span data-stu-id="96f75-278">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a><span data-ttu-id="96f75-279">使用 SharePoint 中樞網站的合規性界限</span><span class="sxs-lookup"><span data-stu-id="96f75-279">Using compliance boundaries for SharePoint hub sites</span></span>

<span data-ttu-id="96f75-280">[SharePoint 中樞網站](/sharepoint/dev/features/hub-site/hub-site-overview)通常與電子文件探索合規性界限所遵循的相同地理或機構界限保持一致。</span><span class="sxs-lookup"><span data-stu-id="96f75-280">[SharePoint hub sites](/sharepoint/dev/features/hub-site/hub-site-overview) often align with the same geographical or agency boundaries that eDiscovery compliance boundaries follow.</span></span> <span data-ttu-id="96f75-281">這表示您可以使用中樞網站的網站識別碼屬性來建立合規性界限。</span><span class="sxs-lookup"><span data-stu-id="96f75-281">That means you can use the site ID property of the hub site to create a compliance boundary.</span></span> <span data-ttu-id="96f75-282">若要這樣做，請使用 SharePoint Online PowerShell 中的 [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) Cmdlet 來取得中樞網站的 SiteId，然後為部門識別碼屬性使用此值來建立搜尋權限篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-282">To do this, use the [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet in SharePoint Online PowerShell to obtain the SiteId for the hub site and then use this value for the department ID property to create a search permissions filter.</span></span>

<span data-ttu-id="96f75-283">使用下列語法來建立 SharePoint 中樞網站的搜尋權限權篩選：</span><span class="sxs-lookup"><span data-stu-id="96f75-283">Use the following syntax to create a search permissions filter for a SharePoint hub site:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

<span data-ttu-id="96f75-284">以下是為 Coho Winery 機構中樞網站建立搜尋權限篩選的範例：</span><span class="sxs-lookup"><span data-stu-id="96f75-284">Here's an example of creating a search permissions filter for a hub site for the Coho Winery agency:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="96f75-285">合規性界限限制</span><span class="sxs-lookup"><span data-stu-id="96f75-285">Compliance boundary limitations</span></span>

<span data-ttu-id="96f75-286">在管理使用合規性界限的電子文件探索案例和調查時，請考量到下列限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-286">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="96f75-287">在建立及執行搜尋時，您可以選取機構外部的內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-287">When creating and running a search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="96f75-288">不過，由於搜尋權限篩選的緣故，這些位置的內容不會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="96f75-288">However, because of the search permissions filter, content from those locations isn't included in the search results.</span></span>

- <span data-ttu-id="96f75-289">合規性界限不適用於電子文件探索案例中的保留。</span><span class="sxs-lookup"><span data-stu-id="96f75-289">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="96f75-290">這表示某家機構中的電子文件探索管理員可以保留不同機構中的使用者。</span><span class="sxs-lookup"><span data-stu-id="96f75-290">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="96f75-291">不過，如果電子文件探索管理員針對處於保留狀態的使用者搜尋其內容位置，則會強制執行合規性界限。</span><span class="sxs-lookup"><span data-stu-id="96f75-291">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="96f75-292">這表示電子文件探索管理員將無法搜尋使用者的內容位置，即使其可以保留使用者也沒有用。</span><span class="sxs-lookup"><span data-stu-id="96f75-292">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>

    <span data-ttu-id="96f75-293">此外，保留統計資料只適用於機構中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="96f75-293">Also, hold statistics will only apply to content locations in the agency.</span></span>

- <span data-ttu-id="96f75-294">如果您獲指派搜尋權限篩選 (信箱或網站篩選)，且嘗試匯出包含貴組織中所有 SharePoint 網站之搜尋的未編製索引項目，即會收到下列錯誤訊息: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`。</span><span class="sxs-lookup"><span data-stu-id="96f75-294">If you're assigned a search permissions filter (either a mailbox or a site filter) and you try to export unindexed items for a search that includes all SharePoint sites in your organization, you'll receive the following error message: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`.</span></span> <span data-ttu-id="96f75-295">如果您獲指派搜尋權限篩選，且要匯出 SharePoint 中的未編製索引項目，您必須重新執行搜尋，並包含要搜尋的特定 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="96f75-295">If you're assigned a search permissions filter and you want to export unindexed items from SharePoint, you'll have to rerun the search and include specific SharePoint sites to search.</span></span> <span data-ttu-id="96f75-296">否則，您僅能從包含所有 SharePoint 網站的搜尋中匯出已編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="96f75-296">Otherwise, you'll only be able to export indexed items from a search that includes all SharePoint sites.</span></span> <span data-ttu-id="96f75-297">如需匯出搜尋結果時相關選項的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-1-prepare-search-results-for-export)。</span><span class="sxs-lookup"><span data-stu-id="96f75-297">For more information about the options when you export search results, see [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).</span></span>

- <span data-ttu-id="96f75-298">搜尋權限篩選不適用於 Exchange 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="96f75-298">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="more-information"></a><span data-ttu-id="96f75-299">其他資訊</span><span class="sxs-lookup"><span data-stu-id="96f75-299">More information</span></span>

- <span data-ttu-id="96f75-300">如果信箱已取消授權或虛刪除，則不會再將使用者視為在合規性界限內。</span><span class="sxs-lookup"><span data-stu-id="96f75-300">If a mailbox is de-licensed or soft-deleted, the user will no longer be considered within the compliance boundary.</span></span> <span data-ttu-id="96f75-301">如果信箱在刪除時處於保留狀態，則信箱中保留的內容仍會受合規性界限或搜尋權限篩選的規範。</span><span class="sxs-lookup"><span data-stu-id="96f75-301">If a hold was placed on the mailbox when it was deleted, the content preserved in the mailbox is still subject to a compliance boundary or search permissions filter.</span></span>

- <span data-ttu-id="96f75-302">如果已針對使用者實作合規性邊界和搜尋權限篩選，則建議您不要刪除該使用者的信箱以及其 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="96f75-302">If compliance boundaries and search permissions filters are implemented for a user, then we recommend that you don't delete a user's mailbox and not their OneDrive account.</span></span> <span data-ttu-id="96f75-303">換句話說，如果您刪除使用者的信箱，也應該移除該使用者的 OneDrive 帳戶，因為 mailbox_RecipientFilter 是用來強制執行 OneDrive 的搜尋權限篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-303">In other words, if you delete a user's mailbox, you should also remove the user's OneDrive account since mailbox_RecipientFilter is used to enforce search permission filter for OneDrive.</span></span>

- <span data-ttu-id="96f75-304">合規性界限和搜尋權限選取決於在 Exchange、OneDrive 和 SharePoint 中內容上的戳記屬性，以及此戳記內容的後續索引。</span><span class="sxs-lookup"><span data-stu-id="96f75-304">Compliance boundaries and search permissions filters depend on attributes being stamped on content in Exchange, OneDrive, and SharePoint and the subsequent indexing of this stamped content.</span></span>

- <span data-ttu-id="96f75-305">不建議針對內容型合規性界限使用排除篩選 (例如在搜尋權限篩選中使用 `-not()`)。</span><span class="sxs-lookup"><span data-stu-id="96f75-305">We don't recommend using exclusion filters (such as using `-not()` in a search permissions filter) for a content-based compliance boundary.</span></span> <span data-ttu-id="96f75-306">如果最近更新屬性的內容尚未編製索引，則使用排除篩選可能會產生未預期的結果。</span><span class="sxs-lookup"><span data-stu-id="96f75-306">Using an exclusion filter can have unexpected results if content with recently updated attributes hasn't been indexed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="96f75-307">常見問題集</span><span class="sxs-lookup"><span data-stu-id="96f75-307">Frequently asked questions</span></span>

<span data-ttu-id="96f75-308">**誰可以建立和管理搜尋權限篩選 (使用 New-ComplianceSecurityFilter 和 Set-ComplianceSecurityFilter Cmdlet)?**</span><span class="sxs-lookup"><span data-stu-id="96f75-308">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets)?**</span></span>
  
<span data-ttu-id="96f75-309">若要建立、檢視及修改搜尋權限篩選，您必須是 Microsoft 365 合規性中心 [組織管理] 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="96f75-309">To create, view, and modify search permissions filters, you have to be a member of the Organization Management role group in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="96f75-310">**如果電子文件探索管理員獲指派超過一個跨多個機構的角色群組，他們如何在一家或另一家機構中搜尋內容?**</span><span class="sxs-lookup"><span data-stu-id="96f75-310">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="96f75-311">電子文件探索管理員可以將參數新增至其搜尋查詢，以將搜尋限制為特定機構。</span><span class="sxs-lookup"><span data-stu-id="96f75-311">The eDiscovery manager can add parameters to their search query that restrict the search to a specific agency.</span></span> <span data-ttu-id="96f75-312">例如，如果組織已指定 **CustomAttribute10** 屬性來區分機構，他們可以在搜尋查詢中附加下列項目，以搜尋特定機構中的信箱和 OneDrive 帳戶：`CustomAttribute10:<value>`。</span><span class="sxs-lookup"><span data-stu-id="96f75-312">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value>`.</span></span>
  
<span data-ttu-id="96f75-313">**如果變更搜尋權限篩選中用來做為合規性屬性的屬性值，會發生什麼情況?**</span><span class="sxs-lookup"><span data-stu-id="96f75-313">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="96f75-314">如果篩選中使用的屬性值已變更，搜尋權限篩選最多需要三天才能強制執行合規性界限。</span><span class="sxs-lookup"><span data-stu-id="96f75-314">It takes up to three days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="96f75-315">例如，在 Contoso 案例中假設 Fourth Coffee 機構中的使用者已轉移到 Coho Winery 機構。</span><span class="sxs-lookup"><span data-stu-id="96f75-315">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="96f75-316">因此，使用者物件上的 **[部門]** 屬性值會從 *FourthCoffee* 變更為 *CohoWinery*。</span><span class="sxs-lookup"><span data-stu-id="96f75-316">As a result, the value of the **Department** attribute on the user object is changed from *FourthCoffee* to *CohoWinery*.</span></span> <span data-ttu-id="96f75-317">在這種情況下，Fourth Coffee eDiscovery 和投資者會在屬性變更後最多三天內依舊取得該使用者的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="96f75-317">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed.</span></span> <span data-ttu-id="96f75-318">同樣地，Coho Winery 電子文件探索管理員和調查人員最多需要等三天的時間才能取得該使用者的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="96f75-318">Similarly, it takes up to three days before Coho Winery eDiscovery managers and investigators get search results for the user.</span></span>
  
<span data-ttu-id="96f75-319">**電子文件探索管理員可以看到來自兩種個別合規性界限的內容嗎?**</span><span class="sxs-lookup"><span data-stu-id="96f75-319">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="96f75-320">是，在搜尋 Exchange 信箱時，將電子文件探索管理員新增至可看到這兩個機構的角色群組，即可達成此作業。</span><span class="sxs-lookup"><span data-stu-id="96f75-320">Yes, this can be done when searching Exchange mailboxes by adding the eDiscovery manager to role groups that have visibility to both agencies.</span></span> <span data-ttu-id="96f75-321">然而當搜尋 SharePoint 網站和 OneDrive 帳戶時，只有在機構位於相同的地區或地理位置時，電子文件探索管理員才能搜尋不同合規性界限中的內容。</span><span class="sxs-lookup"><span data-stu-id="96f75-321">However when searching SharePoint sites and OneDrive accounts, an eDiscovery manager can search for content in different compliance boundaries only if the agencies are in the same region or geo location.</span></span> <span data-ttu-id="96f75-322">**注意：** 進階電子文件探索中不適用此網站限制，因為搜尋 SharePoint 和 OneDrive 中的內容不受地理位置限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-322">**Note:** This limitation for sites doesn't apply in Advanced eDiscovery because searching for content in SharePoint and OneDrive isn't bound by geographic location.</span></span>
  
<span data-ttu-id="96f75-323">**搜尋權限篩選是否適用於電子文件探索案例保留、Microsoft 365 保留原則或 DLP?**</span><span class="sxs-lookup"><span data-stu-id="96f75-323">**Do search permissions filters work for eDiscovery case holds, Microsoft 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="96f75-324">否，目前還不行。</span><span class="sxs-lookup"><span data-stu-id="96f75-324">No, not at this time.</span></span>
  
<span data-ttu-id="96f75-325">**如果我指定要控制內容匯出位置的地區，但我在該地區沒有 SharePoint 組織，是否仍可搜尋 SharePoint?**</span><span class="sxs-lookup"><span data-stu-id="96f75-325">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="96f75-326">如果搜尋權限篩選中指定的地區不存在於貴組織中，則會搜尋預設地區。</span><span class="sxs-lookup"><span data-stu-id="96f75-326">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
<span data-ttu-id="96f75-327">**組織中可建立的搜尋權限篩選數目上限?**</span><span class="sxs-lookup"><span data-stu-id="96f75-327">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="96f75-328">組織中可建立的搜尋權限篩選數目並沒有限制。</span><span class="sxs-lookup"><span data-stu-id="96f75-328">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="96f75-329">不過，當有超過 100 個搜尋權限篩選時，搜尋的效能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="96f75-329">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="96f75-330">若要盡可能減少貴組織的搜尋權限篩選數目，請盡可能建立將 Exchange、SharePoint 和 OneDrive 的規則結合成單一搜尋權限篩選的篩選。</span><span class="sxs-lookup"><span data-stu-id="96f75-330">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
