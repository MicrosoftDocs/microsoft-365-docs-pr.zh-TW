---
title: Microsoft 365 中的進階稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 中的進階稽核提供新的稽核功能，以協助組織進行鑑識與合規性調查。
ms.openlocfilehash: 4812f81140bc80a1437c13b7bce38a7ed101592d
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280154"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="5050b-103">Microsoft 365 中的進階稽核</span><span class="sxs-lookup"><span data-stu-id="5050b-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="5050b-104">Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。</span><span class="sxs-lookup"><span data-stu-id="5050b-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="5050b-105">現在隨著 Microsoft 365 中進階稽核的推出，我們會加入新的稽核功能，以協助組織進行鑑識與合規性調查。</span><span class="sxs-lookup"><span data-stu-id="5050b-105">Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="5050b-106">進階稽核可供具有 Office 365 或 Microsoft 365 企業版 E5 訂閱的組織使用。</span><span class="sxs-lookup"><span data-stu-id="5050b-106">Advanced Audit is available for organizations with an Office 365 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="5050b-107">此外，當進階稽核功能需要使用每個使用者授權時，您可以將 Microsoft 365 E5 合規性附加元件訂閱指派給使用者，針對稽核記錄和存取調查重要事件的長期保留也是如此。</span><span class="sxs-lookup"><span data-stu-id="5050b-107">Additionally, a Microsoft 365 E5 Compliance add-on subscription can be assigned to users for when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span>

<span data-ttu-id="5050b-108">本文提供這些進階稽核功能的概觀。</span><span class="sxs-lookup"><span data-stu-id="5050b-108">This article provides an overview of these Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="5050b-109">長期保留稽核記錄</span><span class="sxs-lookup"><span data-stu-id="5050b-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="5050b-110">進階稽核會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄，時間為一年。</span><span class="sxs-lookup"><span data-stu-id="5050b-110">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="5050b-111">這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="5050b-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="5050b-112">這可協助進行持續的鑑識或合規性調查。</span><span class="sxs-lookup"><span data-stu-id="5050b-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="5050b-113">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」一節。</span><span class="sxs-lookup"><span data-stu-id="5050b-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="5050b-114">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="5050b-114">Audit log retention policies</span></span>

<span data-ttu-id="5050b-115">在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="5050b-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="5050b-116">不過，您現在可以建立自訂的稽核記錄保留原則，以保留其他稽核記錄最多達一年。</span><span class="sxs-lookup"><span data-stu-id="5050b-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="5050b-117">您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：</span><span class="sxs-lookup"><span data-stu-id="5050b-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="5050b-118">稽核活動發生所在的 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="5050b-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="5050b-119">特定已稽核活動</span><span class="sxs-lookup"><span data-stu-id="5050b-119">Specific audited activities</span></span>

- <span data-ttu-id="5050b-120">執行已稽核活動的使用者</span><span class="sxs-lookup"><span data-stu-id="5050b-120">The user who performs an audited activity</span></span>

<span data-ttu-id="5050b-121">您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。</span><span class="sxs-lookup"><span data-stu-id="5050b-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="5050b-122">另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="5050b-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="5050b-123">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5050b-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="5050b-124">存取調查重要事件</span><span class="sxs-lookup"><span data-stu-id="5050b-124">Access to crucial events for investigations</span></span>

<span data-ttu-id="5050b-125">重要安全性與合規性相關的稽核事件，可協助您調查可能外洩或其他與鑑識相關的調查。</span><span class="sxs-lookup"><span data-stu-id="5050b-125">Crucial security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="5050b-126">我們要發佈的第一個重要事件是 *MailItemsAccessed* 信箱稽核動作。</span><span class="sxs-lookup"><span data-stu-id="5050b-126">The first crucial event that we're releasing is the *MailItemsAccessed* mailbox auditing action.</span></span> <span data-ttu-id="5050b-127">當郵件通訊協定和郵件用戶端存取郵件資料時，即會觸發此動作。</span><span class="sxs-lookup"><span data-stu-id="5050b-127">This action is triggered when mail data is accessed by mail protocols and mail clients.</span></span> <span data-ttu-id="5050b-128">MailItemsAccessed 動作可幫助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。</span><span class="sxs-lookup"><span data-stu-id="5050b-128">The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="5050b-129">如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取郵件 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，將會觸發 MailItemsAccessed 動作。</span><span class="sxs-lookup"><span data-stu-id="5050b-129">If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="5050b-130">新的 MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：</span><span class="sxs-lookup"><span data-stu-id="5050b-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="5050b-131">MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="5050b-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="5050b-132">MailItemsAccessed 適用於所有登入類型。</span><span class="sxs-lookup"><span data-stu-id="5050b-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="5050b-133">MessageBind 僅涵蓋透過郵件用戶端的存取。</span><span class="sxs-lookup"><span data-stu-id="5050b-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="5050b-134">並不適用同步處理活動。</span><span class="sxs-lookup"><span data-stu-id="5050b-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="5050b-135">MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。</span><span class="sxs-lookup"><span data-stu-id="5050b-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="5050b-136">當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄的建立，這會導致稽核的「雜訊」。</span><span class="sxs-lookup"><span data-stu-id="5050b-136">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="5050b-137">相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="5050b-137">In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="5050b-138">如需有關信箱稽核記錄的詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="5050b-138">For more information about mailbox auditing logging, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>

### <a name="search-for-mailitemsaccessed-audit-records"></a><span data-ttu-id="5050b-139">搜尋 MailItemsAccessed 稽核記錄</span><span class="sxs-lookup"><span data-stu-id="5050b-139">Search for MailItemsAccessed audit records</span></span>

<span data-ttu-id="5050b-140">若要搜尋 MailItemsAccessed 稽核記錄，您可以在 Office 365 安全性與合規性中心的[稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 [Exchange 信箱活動]\*\*\*\* 下拉式清單中搜尋 [已存取的信箱項目]\*\*\*\* 活動。</span><span class="sxs-lookup"><span data-stu-id="5050b-140">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Office 365 security and compliance center.</span></span>

![在稽核記錄搜尋工具中搜尋 MailItemsAccessed 動作](../media/MailItemsAccessedSCC1.png)

<span data-ttu-id="5050b-142">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="5050b-142">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="5050b-143">Office 365 管理活動 API 的高頻寬存取權</span><span class="sxs-lookup"><span data-stu-id="5050b-143">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="5050b-144">透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。</span><span class="sxs-lookup"><span data-stu-id="5050b-144">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="5050b-145">這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。</span><span class="sxs-lookup"><span data-stu-id="5050b-145">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="5050b-146">隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。</span><span class="sxs-lookup"><span data-stu-id="5050b-146">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="5050b-147">結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。</span><span class="sxs-lookup"><span data-stu-id="5050b-147">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="5050b-148">頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。</span><span class="sxs-lookup"><span data-stu-id="5050b-148">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="5050b-149">所有組織一開始都會配置每分鐘 2,000 個要求的基準。</span><span class="sxs-lookup"><span data-stu-id="5050b-149">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="5050b-150">視組織的基座數和授權訂閱而定，此限制將會動態增加。</span><span class="sxs-lookup"><span data-stu-id="5050b-150">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="5050b-151">E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。</span><span class="sxs-lookup"><span data-stu-id="5050b-151">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="5050b-152">最大頻寬也會有上限，以保護服務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="5050b-152">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="5050b-153">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。</span><span class="sxs-lookup"><span data-stu-id="5050b-153">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="5050b-154">進階稽核的常見問題集</span><span class="sxs-lookup"><span data-stu-id="5050b-154">FAQs for Advanced Audit</span></span>

<span data-ttu-id="5050b-155">**我可以在哪裡存取進階稽核？**</span><span class="sxs-lookup"><span data-stu-id="5050b-155">**Where can I access Advanced Audit?**</span></span>

<span data-ttu-id="5050b-156">在您的組織推出進階稽核之後，您就可以建立稽核記錄保留原則，並使用 [Office 365 安全性與合規性中心](https://protection.office.com)中的 [稽核記錄搜尋] 工具來搜尋 MailItemsAccessed 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="5050b-156">After Advanced Audit is rolled out to your organization, you will be able to create audit log retention policies and search for MailItemsAccessed audit records using the Audit log search tool in the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="5050b-157">我們正努力在未來幾周內，在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)推出進階稽核。</span><span class="sxs-lookup"><span data-stu-id="5050b-157">We're working to roll out Advanced Audit to the [Microsoft 365 compliance center](https://compliance.microsoft.com) in the coming weeks.</span></span>

<span data-ttu-id="5050b-158">**每位使用者是否需要 E5 授權才能使用進階稽核？**</span><span class="sxs-lookup"><span data-stu-id="5050b-158">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="5050b-159">若要使用使用者層級的進階稽核功能，使用者必須獲指派 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="5050b-159">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license.</span></span> <span data-ttu-id="5050b-160">部分功能會檢查是否有適當授權，才會開放功能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5050b-160">There are some capabilities that will check for the appropriate license to expose the feature for the user.</span></span> <span data-ttu-id="5050b-161">例如，如果您正嘗試保留使用者的稽核記錄，但該使用者在 90 天內未獲指派 E5 授權，系統將會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="5050b-161">For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="5050b-162">**為什麼即使已有 E5 訂閱，而使用者也已獲指派 E5 授權，在組織中仍看不到進階稽核？**</span><span class="sxs-lookup"><span data-stu-id="5050b-162">**Why don't I see Advanced Audit in my organization, even though we have an E5 subscription and users that are assigned E5 licenses?**</span></span>

<span data-ttu-id="5050b-163">即使已具備正確的授權，您的組織可能仍無法使用 [進階稽核] 功能 (例如建立稽核記錄保留原則和記錄 MailItemsAccessed 稽核記錄的功能)。</span><span class="sxs-lookup"><span data-stu-id="5050b-163">It's possible that Advanced Audit features (such as the ability to create audit log retention policies and the logging of MailItemsAccessed audit records) aren't available in your organization, even with the correct licensing in place.</span></span> <span data-ttu-id="5050b-164">如果您遇到此問題，這是因為進階稽核套件尚未部署至您的組織。</span><span class="sxs-lookup"><span data-stu-id="5050b-164">If this is happening to you, it's because the Advanced Audit package hasn't been rolled out to your organization yet.</span></span> <span data-ttu-id="5050b-165">這是暫時的授權回填問題，在未來幾周內將會為受影響組織解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="5050b-165">This is a temporary licensing backfill issue, which should be resolved for affected organizations in the next few weeks.</span></span> <span data-ttu-id="5050b-166">若要緩解此問題，請針對每個 E5 使用者執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5050b-166">To mitigate this issue, please perform the following steps for each E5 user:</span></span>

1. <span data-ttu-id="5050b-167">在 Microsoft 365 系統管理中心，移至 [使用者] > [作用中的使用者]\*\*\*\*，然後選取使用者。</span><span class="sxs-lookup"><span data-stu-id="5050b-167">In the Microsoft 365 admin center, go to **Users > Active users**, and then select a user.</span></span>

2. <span data-ttu-id="5050b-168">在 [使用者內容] 飛出頁面上，按一下 [授權和應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5050b-168">On the user properties flyout page, click **Licenses and Apps**.</span></span>

3. <span data-ttu-id="5050b-169">展開 [應用程式]\*\*\*\* 區段，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="5050b-169">Expand the **Apps** section, and then do one of the following things:</span></span>

   <span data-ttu-id="5050b-170">a.</span><span class="sxs-lookup"><span data-stu-id="5050b-170">a.</span></span> <span data-ttu-id="5050b-171">如果沒有選取 [Microsoft 365 進階稽核]\*\*\*\* 核取方塊，請選取它，然後按一下 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5050b-171">If the **Microsoft 365 Advanced Auditing** checkbox is not selected, select it, and then click **Save changes.**</span></span> <span data-ttu-id="5050b-172">此使用者的 MailItemsAccessed 動作的稽核記錄應可在 24 小時內提供搜尋。</span><span class="sxs-lookup"><span data-stu-id="5050b-172">Audit records for MailItemsAccessed actions for this user should be searchable within 24 hours.</span></span>

   <span data-ttu-id="5050b-173">b.</span><span class="sxs-lookup"><span data-stu-id="5050b-173">b.</span></span> <span data-ttu-id="5050b-174">如果已選取 [Microsoft 365 進階稽核]\*\*\*\* 核取方塊，請清除它，然後按一下 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5050b-174">If the **Microsoft 365 Advanced Auditing** checkbox is selected, clear it, and then click **Save changes.**</span></span> <span data-ttu-id="5050b-175">請參閱步驟 4。</span><span class="sxs-lookup"><span data-stu-id="5050b-175">See step 4.</span></span>

4. <span data-ttu-id="5050b-176">如果您已在步驟 3 中清除核取方塊，請稍候 60 分鐘，然後重複步驟 3a 來啟用 Microsoft 365 進階稽核應用程式。</span><span class="sxs-lookup"><span data-stu-id="5050b-176">If you cleared the checkbox in step 3, wait 60 minutes, and then repeat step 3a to enable the Microsoft 365 Advanced Auditing app.</span></span>

<span data-ttu-id="5050b-177">**如果我的組織處於私人預覽階段的一年稽核記錄保留，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="5050b-177">**What happens if my organization was in the private preview for one-year retention of audit records?**</span></span>

<span data-ttu-id="5050b-178">只要您不以自訂稽核保留原則來覆寫和變更稽核保留原則，就可以保留預覽計畫中的審核保留原則。</span><span class="sxs-lookup"><span data-stu-id="5050b-178">Your audit retention policies from the preview program will persist as long as you don't override and change them with custom audit retention policies.</span></span>

<span data-ttu-id="5050b-179">**如果我的組織想要將稽核記錄保留一年以上，該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="5050b-179">**What if my organization wants to retain audit logs for longer than one year?**</span></span>

<span data-ttu-id="5050b-180">我們正在探索相關作法，讓我們可以為稽核記錄提供較長的保留期間。</span><span class="sxs-lookup"><span data-stu-id="5050b-180">We're exploring options for how and if we can provide longer retention periods for audit records.</span></span> <span data-ttu-id="5050b-181">您可以在 [Office 365 使用者意見](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187) (英文) 中提供關於稽核記錄較長保留時間的意見反應。</span><span class="sxs-lookup"><span data-stu-id="5050b-181">You can provide any feedback about longer retention of audit records at [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187).</span></span>

<span data-ttu-id="5050b-182">**我的組織擁有 E5 訂閱，我是否需要執行任何動作才能存取 MailItemsAccessed 事件的稽核記錄？**</span><span class="sxs-lookup"><span data-stu-id="5050b-182">**My organization has an E5 subscription, do I need to do anything to get access to audit records for MailItemsAccessed events?**</span></span>

<span data-ttu-id="5050b-183">針對符合資格的客戶，您不需要採取任何動作就能存取 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="5050b-183">For eligible customers, there is no action to get access to MailItemsAccessed events.</span></span> <span data-ttu-id="5050b-184">不過，如本主題先前所述，由於授權回填問題所造成的延遲，可能會造成稽核記錄搜尋無法傳回 MailItemsAccessed 事件的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="5050b-184">However, as previously explained in this topic, latency caused by the licensing backfill issue may prevent audit records for MailItemsAccessed event from being returned in an audit log search.</span></span> <span data-ttu-id="5050b-185">如果發生這種情況，請按照 [搜尋 MailItemsAccessed 稽核記錄] 一節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="5050b-185">If this happens, follow the instructions in the Search for MailItemsAccessed audit records section.</span></span>

<span data-ttu-id="5050b-186">**您是否計畫在今年推出其他事件？**</span><span class="sxs-lookup"><span data-stu-id="5050b-186">**Are you planning to release additional events this year?**</span></span>

<span data-ttu-id="5050b-187">是的，我們計畫在未來幾個月內推出對調查來說至關重要的新事件。</span><span class="sxs-lookup"><span data-stu-id="5050b-187">Yes, we plan to release new events that are crucial to investigations in the coming months.</span></span> <span data-ttu-id="5050b-188">接近推出日期時，我們會在 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)中公告這些新事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5050b-188">We will post information about these new events in the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) as we get closer to a release date.</span></span>

<span data-ttu-id="5050b-189">**Office 365 管理活動 API 的進階稽核中是否有新的事件？**</span><span class="sxs-lookup"><span data-stu-id="5050b-189">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="5050b-190">是。</span><span class="sxs-lookup"><span data-stu-id="5050b-190">Yes.</span></span> <span data-ttu-id="5050b-191">只要為具有適當授權的使用者產生稽核記錄，您就可以透過 Office 365 管理活動 API 存取這些記錄。</span><span class="sxs-lookup"><span data-stu-id="5050b-191">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="5050b-192">**頻寬較高代表延遲較好或更高的 SLA 嗎？**</span><span class="sxs-lookup"><span data-stu-id="5050b-192">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="5050b-193">目前，高頻寬可提供更好的管道，特別是具有大量稽核訊號和大量消費模式的組織。</span><span class="sxs-lookup"><span data-stu-id="5050b-193">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="5050b-194">這可能會導致更好的延遲。</span><span class="sxs-lookup"><span data-stu-id="5050b-194">This can lead to better latency.</span></span> <span data-ttu-id="5050b-195">不過，SLA 與高頻寬無關。</span><span class="sxs-lookup"><span data-stu-id="5050b-195">But, there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="5050b-196">標準延遲已予以記錄，且在進階稽核推出時不會變更。</span><span class="sxs-lookup"><span data-stu-id="5050b-196">Standard latencies are documented, and these don't change with the release of Advanced Audit.</span></span>
