---
title: 保留原則和保留標籤原則的限制
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: 瞭解針對保留原則及保留標籤原則，每個原則的原則和專案數量上限。
ms.openlocfilehash: 1ee2d07a42aaf4dff45ae22e9dfc005b3c4593d9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698961"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="1bea1-103">保留原則和保留標籤原則的限制</span><span class="sxs-lookup"><span data-stu-id="1bea1-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="1bea1-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="1bea1-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="1bea1-105">當您使用 [保留原則及保留標籤原則](retention.md#retention-policies-and-retention-labels) 以自動保留或刪除貴組織的資料時，有一些您需要注意的最大值。</span><span class="sxs-lookup"><span data-stu-id="1bea1-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="1bea1-106">每個租用戶的原則數量上限</span><span class="sxs-lookup"><span data-stu-id="1bea1-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="1bea1-107">單一租用戶最多可以有10,000個原則 (任何設定)。</span><span class="sxs-lookup"><span data-stu-id="1bea1-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="1bea1-108">這個最大值包括保留的不同原則和其他合規性原則，例如 DLP 原則、資訊屏障、eDiscovery 保留和敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="1bea1-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="1bea1-109">在此 10，000 個原則限制內，每個工作負載的保留原則數量上限也有一些限制：</span><span class="sxs-lookup"><span data-stu-id="1bea1-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="1bea1-110">Exchange Online (任何設定)：1,800</span><span class="sxs-lookup"><span data-stu-id="1bea1-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="1bea1-111">SharePoint 或 OneDrive：(自動包含所有網站)：13</span><span class="sxs-lookup"><span data-stu-id="1bea1-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="1bea1-112">SharePoint 或 OneDrive (包含或排除的特定位置)：2,600</span><span class="sxs-lookup"><span data-stu-id="1bea1-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="1bea1-113">雖然 Microsoft Teams 和 Yammer 的保留原則會使用信箱來儲存資料以用於保留目的，但 Exchange Online 的保留原則數目上限會排除 Teams 和 Yammer 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1bea1-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="1bea1-114">每個原則的專案數量上限</span><span class="sxs-lookup"><span data-stu-id="1bea1-114">Maximum number of items per policy</span></span>

<span data-ttu-id="1bea1-115">當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要注意根據原則而異的限制：</span><span class="sxs-lookup"><span data-stu-id="1bea1-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="1bea1-116">每個原則保留的專案數量上限：</span><span class="sxs-lookup"><span data-stu-id="1bea1-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="1bea1-117">1,000 個信箱 (使用者信箱或群組信箱)</span><span class="sxs-lookup"><span data-stu-id="1bea1-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="1bea1-118">1,000 個 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="1bea1-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="1bea1-119">1000 個 Teams 私人聊天使用者</span><span class="sxs-lookup"><span data-stu-id="1bea1-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="1bea1-120">100 個網站 (OneDrive 或 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="1bea1-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="1bea1-121">因為這些限制根據原則而異，因此如果您需要使用會導致超出這些數字的特定包含或排除，您可以建立具有相同保留設定的額外原則。</span><span class="sxs-lookup"><span data-stu-id="1bea1-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="1bea1-122">請參閱下一節中因此項緣由而使用多個保留原則的部分 [案例和解決方案](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)。</span><span class="sxs-lookup"><span data-stu-id="1bea1-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="1bea1-123">然而，多個原則會造成更高的系統管理費用，因此請隨時確認是否確實需要包含與排除。</span><span class="sxs-lookup"><span data-stu-id="1bea1-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="1bea1-124">請記住，套用到整個位置的預設設定並沒有任何限制，且此設定選項可能是比建立及維護多個原則更好的解決方案。</span><span class="sxs-lookup"><span data-stu-id="1bea1-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="1bea1-125">如果您需要針對此情況，建立並維護多個原則，請考慮使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) ，以進行更有效率的設定。</span><span class="sxs-lookup"><span data-stu-id="1bea1-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="1bea1-126">使用多個原則來避免超過數量上限的範例</span><span class="sxs-lookup"><span data-stu-id="1bea1-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="1bea1-127">下列範例提供一些設計解決方案，適用於當您無法只指定保留原則的位置，且必須考慮上一節中所述的專案數量上限的情況。</span><span class="sxs-lookup"><span data-stu-id="1bea1-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="1bea1-128">Exchange 範例：</span><span class="sxs-lookup"><span data-stu-id="1bea1-128">Exchange example:</span></span>

- <span data-ttu-id="1bea1-129">**需求**：在具有超過 40,000 個使用者信箱的組織中，大部分的使用者都必須將其電子郵件保留 7 年，但是子集的已識別使用者 (425) 的電子郵件只能保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="1bea1-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="1bea1-130">**解決方案**：為 Exchange 電子郵件建立一份保留原則，保留期間為 7 年，並排除使用者子集。</span><span class="sxs-lookup"><span data-stu-id="1bea1-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="1bea1-131">然後，為 Exchange 電子郵件建立第二份保留原則，保留期間為 5 年，並包含使用者子集。</span><span class="sxs-lookup"><span data-stu-id="1bea1-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="1bea1-132">在這兩種情況下，包含和排除的數字皆低於單一原則指定信箱的上限，且使用者的子集必須明確排除于第一個原則之外，因為其 [保留期間](retention.md#the-principles-of-retention-or-what-takes-precedence) 較第二個原則要長。</span><span class="sxs-lookup"><span data-stu-id="1bea1-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="1bea1-133">如果使用者的子集需要較長的保留原則，則不需要將之從第一個原則中排除。</span><span class="sxs-lookup"><span data-stu-id="1bea1-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="1bea1-134">使用這個解決方案，如果有其他人加入該組織，則其信箱會自動包含在第一個原則中 7 年限制，且不會影響支援的上限。</span><span class="sxs-lookup"><span data-stu-id="1bea1-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="1bea1-135">不過，要求 5 年保留期間的新使用者會被納入包含和排除的限制數目，則此限制將超出 1,000。</span><span class="sxs-lookup"><span data-stu-id="1bea1-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="1bea1-136">SharePoint 範例：</span><span class="sxs-lookup"><span data-stu-id="1bea1-136">SharePoint example:</span></span>

- <span data-ttu-id="1bea1-137">**需求**：一個組織擁有數千個 SharePoint 網站，但只有 2,000 個網站需要 10 年的保留期間，和 8,000 個需要 4 年保留期間的網站。</span><span class="sxs-lookup"><span data-stu-id="1bea1-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="1bea1-138">**解決方案**：建立 20 個 SharePoint 保留原則，保留期間為 10 年，其中包括 100 個特定網站，並建立 80個 SharePoint 保留原則，保留期間為 4 年，其中包含 100 個特定網站。</span><span class="sxs-lookup"><span data-stu-id="1bea1-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="1bea1-139">因為您不需要保留所有的 SharePoint 網站，您必須建立指定特定網站的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1bea1-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="1bea1-140">由於保留原則不支援超過 100 個指定的網站，因此您必須針對兩個保留期間建立多個原則。</span><span class="sxs-lookup"><span data-stu-id="1bea1-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="1bea1-141">這些保留原則所包含的網站數量為上限，因此需要保留的下一個新網站不論保留期間都會需要新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1bea1-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>