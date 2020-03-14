---
title: 舊的 eDiscovery 工具退休
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Exchange Online 中的 In-Place eDiscovery 和 In-Place 保留（以及對應的 PowerShell Cmdlet）會在2020的上半年內淘汰。 Search-Mailbox Cmdlet 和 Office 365 Advanced eDiscovery 1.0 1.0 也會在相同的時段內淘汰。
ms.openlocfilehash: 92b6648b603286871956db64631d334df2384112
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634831"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="c8acd-104">舊的 eDiscovery 工具退休</span><span class="sxs-lookup"><span data-stu-id="c8acd-104">Retirement of legacy eDiscovery tools</span></span>

<span data-ttu-id="c8acd-105">在幾年中，Microsoft 提供了 eDiscovery 工具，可讓您從 Exchange Online 搜尋、預覽及匯出電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-105">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="c8acd-106">不過，這些工具不再提供有效的方式，可在其他 Office 365 服務中搜尋非 Exchange 內容，例如 SharePoint 線上和 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c8acd-106">However, these tools no longer offer an effective way to search for non-Exchange content in other Office 365 services, such as SharePoint Online and Office 365 Groups.</span></span> <span data-ttu-id="c8acd-107">為了解決此情況，Microsoft 提供了其他 eDiscovery 工具，可協助您搜尋各種各樣的 Office 365 內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-107">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Office 365 content.</span></span> <span data-ttu-id="c8acd-108">而且我們致力於在[Microsoft 365 規範中心](https://compliance.microsoft.com)內整合最新和功能強大的 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="c8acd-108">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="c8acd-109">這可讓組織對許多 Office 365 服務（包括 Exchange Online）的內容，回應法律、內部及其他檔要求。</span><span class="sxs-lookup"><span data-stu-id="c8acd-109">This allows organizations to respond to legal, internal, and other document requests for content across many Office 365 services, including Exchange Online.</span></span>

<span data-ttu-id="c8acd-110">在 Microsoft 365 規範中心內，這項新的和改善的 eDiscovery 功能的結果是，在 Exchange Online 和 Office 365 中，我們會淘汰下列與搜尋電子郵件內容相關的 eDiscovery 相關功能：</span><span class="sxs-lookup"><span data-stu-id="c8acd-110">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Office 365:</span></span>

- <span data-ttu-id="c8acd-111">在 Exchange 系統管理中心中[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[In-Place 存放](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-111">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="c8acd-112">Exchange Online PowerShell Cmdlet，支援 In-Place eDiscovery 和 In-Place 保留（這些 Cmdlet 共同識別為 \**-get-mailboxsearch 程式*Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="c8acd-112">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="c8acd-113">這包括下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c8acd-113">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="c8acd-114">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="c8acd-114">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [<span data-ttu-id="c8acd-115">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="c8acd-115">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [<span data-ttu-id="c8acd-116">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="c8acd-116">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [<span data-ttu-id="c8acd-117">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="c8acd-117">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="c8acd-118">當其他 \* \*-MailboxSearch \* \* \* \* \* 指令程式已停用之後，就可以使用[Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)和[Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) Cmdlet，這樣您就可以使用這些 Cmdlet 來協助您轉換至其他 eDiscovery 和保留工具。</span><span class="sxs-lookup"><span data-stu-id="c8acd-118">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="c8acd-119">不過，在特定日期（如下所示）之後，Microsoft 支援將不再支援這兩個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8acd-119">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="c8acd-120">Exchange Online PowerShell 中的[Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8acd-120">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="c8acd-121">Exchange Web 服務 API 中的下列作業：</span><span class="sxs-lookup"><span data-stu-id="c8acd-121">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="c8acd-122">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="c8acd-122">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="c8acd-123">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="c8acd-123">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="c8acd-124">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="c8acd-124">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="c8acd-125">[Office 365 Advanced ediscovery 1.0](office-365-advanced-ediscovery.md)版，也就是透過 Office 365 安全性 & 合規性中心的 eDiscovery 案例所存取的第一版的高級 ediscovery。</span><span class="sxs-lookup"><span data-stu-id="c8acd-125">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through an eDiscovery case in the Office 365 Security & Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="c8acd-126">即將淘汰的 eDiscovery 功能僅適用于雲端式版本的 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8acd-126">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="c8acd-127">在內部部署 Exchange 和 SharePoint 版本中的 eDiscovery 功能仍會受到支援，直到進一步通知為止。</span><span class="sxs-lookup"><span data-stu-id="c8acd-127">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="c8acd-128">本文中的下列各節提供每個已撤銷的功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="c8acd-128">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="c8acd-129">此資訊包含時程表和您可以使用的替代工具，而不是退休工具。</span><span class="sxs-lookup"><span data-stu-id="c8acd-129">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="c8acd-130">在 Exchange 系統管理中心中 In-Place eDiscovery 和 In-Place 存放</span><span class="sxs-lookup"><span data-stu-id="c8acd-130">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="c8acd-131">根據原始宣告于2017年7月1日，在 Exchange 系統管理中心（EAC）中的 In-Place eDiscovery & 保留功能即將淘汰。</span><span class="sxs-lookup"><span data-stu-id="c8acd-131">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="c8acd-132">EAC 中 In-Place eDiscovery & 保留頁面可讓您搜尋、保留及匯出 Exchange Online 中的內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-132">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="c8acd-133">In-Place eDiscovery 也可讓您將搜尋結果複製到探索信箱，讓您或其他 eDiscovery 管理員可以查看內容，並將其提供給法律、法規及公開的要求。</span><span class="sxs-lookup"><span data-stu-id="c8acd-133">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="c8acd-134">由於所有這些功能（除了將搜尋結果複製到探索信箱之外）現在可在[Microsoft 365 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)的內容搜尋、Ediscovery 和高級 ediscovery 工具中取得，因此我們建議您儘快開始使用這些工具（改進功能、可靠性和365支援）。</span><span class="sxs-lookup"><span data-stu-id="c8acd-134">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="c8acd-135">為了協助您轉換至這些其他 eDiscovery 工具，下表列出您可以使用的工具，而不是 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-135">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="c8acd-136">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="c8acd-136">Scope of affected organizations</span></span>

- <span data-ttu-id="c8acd-137">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-137">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="c8acd-138">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-138">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="c8acd-139">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="c8acd-139">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="c8acd-140">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c8acd-140">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="c8acd-141">退休的時程表</span><span class="sxs-lookup"><span data-stu-id="c8acd-141">Timeline for retirement</span></span>

- <span data-ttu-id="c8acd-142">2020年4月1日：您將無法建立新的搜尋和保留，但是您仍然可以自行承擔執行、編輯和刪除現有的搜尋。</span><span class="sxs-lookup"><span data-stu-id="c8acd-142">April 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="c8acd-143">Microsoft 支援將不會再 In-Place EAC 中的 eDiscovery & 保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-143">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="c8acd-144">2020年7月1日： In-Place eDiscovery & 保留 EAC 中的功能將會置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="c8acd-144">July 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="c8acd-145">這表示您只可以移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-145">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="c8acd-146">替代工具</span><span class="sxs-lookup"><span data-stu-id="c8acd-146">Alternative tools</span></span>

<span data-ttu-id="c8acd-147">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="c8acd-147">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c8acd-148"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-148"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="c8acd-149"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-149"><strong>Alternative tool</strong></span></span></th>
<th><span data-ttu-id="c8acd-150"><strong>註解</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-150"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c8acd-151">出於法律目的進行搜尋、匯出和保留</span><span class="sxs-lookup"><span data-stu-id="c8acd-151">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="c8acd-152">Microsoft 365 規範中心內的核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="c8acd-152">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="c8acd-153">使用核心 eDiscovery 案例的功能，可提供功能性同位，以 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-153">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="c8acd-154">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="c8acd-154">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="c8acd-155">搜尋可擴展至數百萬位置</span><span class="sxs-lookup"><span data-stu-id="c8acd-155">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="c8acd-156">更高的可靠性用於搜尋、匯出及放置內容保留</span><span class="sxs-lookup"><span data-stu-id="c8acd-156">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="c8acd-157">在 Exchange Online 中搜尋內容、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊、Yammer 群組、Office 365 群組，以及其他儲存在 Office 365 應用程式中的內容</span><span class="sxs-lookup"><span data-stu-id="c8acd-157">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Office 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
<p><span data-ttu-id="c8acd-158">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">管理 Office 365 的法律調查</a>。</span><span class="sxs-lookup"><span data-stu-id="c8acd-158">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Manage legal investigations in Office 365</a>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c8acd-159">保留以供保留用途</span><span class="sxs-lookup"><span data-stu-id="c8acd-159">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="c8acd-160">Microsoft 365 規範中心內的保留原則</span><span class="sxs-lookup"><span data-stu-id="c8acd-160">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="c8acd-161">您可以使用保留原則來保留內容，如有需要，請在保留期間到期之後加以刪除。</span><span class="sxs-lookup"><span data-stu-id="c8acd-161">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="c8acd-162">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="c8acd-162">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="c8acd-163">將原則套用至整個組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-163">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="c8acd-164">將原則套用至特定的內容位置，例如 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="c8acd-164">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="c8acd-165">將原則套用至特定使用者</span><span class="sxs-lookup"><span data-stu-id="c8acd-165">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="c8acd-166">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">保留原則一覽</a>。</span><span class="sxs-lookup"><span data-stu-id="c8acd-166">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Overview of retention policies</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c8acd-167">將電子郵件搜尋結果複製到探索信箱以供審閱</span><span class="sxs-lookup"><span data-stu-id="c8acd-167">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="c8acd-168">在高級 eDiscovery 2.0 中複查集</span><span class="sxs-lookup"><span data-stu-id="c8acd-168">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="c8acd-169">在 Microsoft 365 中審閱內容的工作並不容易。</span><span class="sxs-lookup"><span data-stu-id="c8acd-169">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="c8acd-170">「複查集」具有許多強大的功能，可協助您減少所需的查看時間和資料量，包括：</span><span class="sxs-lookup"><span data-stu-id="c8acd-170">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8acd-171">執行 fast search 查詢及篩選審閱集中的內容</span><span class="sxs-lookup"><span data-stu-id="c8acd-171">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="c8acd-172">分析審閱集中的內容;這包括電子郵件執行緒、接近重複偵測、主題分析和預測編碼</span><span class="sxs-lookup"><span data-stu-id="c8acd-172">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="c8acd-173">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="c8acd-173">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="c8acd-174">標記建議，以協助識別律師用戶端許可權內容</span><span class="sxs-lookup"><span data-stu-id="c8acd-174">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="c8acd-175">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的進階電子文件探索解決方案概觀</a>。</span><span class="sxs-lookup"><span data-stu-id="c8acd-175">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="c8acd-176">或者，您可以將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 365 匯入服務將 Pst 匯入探索信箱。</span><span class="sxs-lookup"><span data-stu-id="c8acd-176">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="c8acd-177">如需逐步指示，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用網路上傳將 PST 檔案匯入 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="c8acd-177">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class="even">
<td><span data-ttu-id="c8acd-178">從 [可復原的專案] 資料夾還原專案</span><span class="sxs-lookup"><span data-stu-id="c8acd-178">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="c8acd-179"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="c8acd-179"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="c8acd-180">您可以還原信箱中永久刪除的專案（也稱為虛<i>刪除的</i>專案），只要專案的刪除專案保留期間尚未過期。</span><span class="sxs-lookup"><span data-stu-id="c8acd-180">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="c8acd-181">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中</a>的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c8acd-181">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="c8acd-182">有關 In-Place eDiscovery 和 In-Place 保留的 FAQs</span><span class="sxs-lookup"><span data-stu-id="c8acd-182">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="c8acd-183">**我使用 In-Place eDiscovery & 的「副本搜尋結果」功能，將搜尋結果複製到探索信箱，以供律師審閱。我現在有哪些選項？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-183">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="c8acd-184">目前有兩種方法可以複製這項功能。</span><span class="sxs-lookup"><span data-stu-id="c8acd-184">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="c8acd-185">第一個用途是使用[高級 eDiscovery 2.0 版中的複查集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-185">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="c8acd-186">「審閱」集中的功能，您可以在傳統的回顧工具中看到許多相同的功能，例如快速搜尋檔、標記、電子郵件執行緒、接近重複群組、主題分析和預測編碼。</span><span class="sxs-lookup"><span data-stu-id="c8acd-186">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="c8acd-187">如果您仍然想要使用探索信箱進行審閱，第二個選項是將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 規範中心的 [Pst 匯入][功能](use-network-upload-to-import-pst-files.md)，將 pst 檔案匯入到探索信箱。</span><span class="sxs-lookup"><span data-stu-id="c8acd-187">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="c8acd-188">**如何控制 eDiscovery 管理員可使用新工具進行搜尋的內容位置（例如信箱或網站）？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-188">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="c8acd-189">Microsoft 365 規範中心也會使用[規範界限](set-up-compliance-boundaries.md)來控制 eDiscovery 管理員可搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="c8acd-189">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="c8acd-190">規範界限可用於政府機構內，但必須保持在代理商界限或具備地理位置 boarders 的多國公司。</span><span class="sxs-lookup"><span data-stu-id="c8acd-190">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="c8acd-191">**如何將目前的搜尋和保留移動至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-191">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="c8acd-192">您可以使用 PowerShell 從 EAC 遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-192">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="c8acd-193">如需相關指示，請參閱將[搜尋和保留從 EAC 遷移至 Microsoft 365 規範中心](https://go.microsoft.com/fwlink/?linkid=2114224)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-193">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="c8acd-194">\*-Get-mailboxsearch 程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c8acd-194">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="c8acd-195">根據在 Exchange 系統管理中心的2017年7月1日宣佈的原始宣告，In-Place eDiscovery & 保留功能和對應\*\* \*的 get-mailboxsearch 程式\*\*Cmdlet 即將停用。</span><span class="sxs-lookup"><span data-stu-id="c8acd-195">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="c8acd-196">這些 Cmdlet 可讓使用者搜尋、保留及匯出法律、法規及公開要求的信箱內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-196">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="c8acd-197">由於這些功能現在可在[<span class="underline">Microsoft 365 規範中心</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)和 Office 365 安全性 & 合規性中心 PowerShell 取得，提高效能與擴充性，所以您應該使用這些改進的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8acd-197">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="c8acd-198">這些 Cmdlet 包括[<span class="underline"> \*-get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase)、 [<span class="underline"> \*-new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)、 [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)、 [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)及[<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-198">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="c8acd-199">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="c8acd-199">Scope of affected organizations</span></span>

- <span data-ttu-id="c8acd-200">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-200">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="c8acd-201">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-201">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="c8acd-202">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="c8acd-202">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="c8acd-203">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c8acd-203">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="c8acd-204">時間表</span><span class="sxs-lookup"><span data-stu-id="c8acd-204">Timeline</span></span>

- <span data-ttu-id="c8acd-205">2020年4月1日：您將無法使用**New-MailboxSearch**來建立新的 In-Place eDiscovery 搜尋和 In-Place 保留，但是您仍然可以使用 Cmdlet 來執行、編輯和刪除現有的搜尋，並以您自己的風險加以保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-205">April 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="c8acd-206">Microsoft 支援人員將不再為這些類型的搜尋和保留提供協助。</span><span class="sxs-lookup"><span data-stu-id="c8acd-206">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="c8acd-207">2020年7月1日：如先前所述，將 EAC 中的 In-Place eDiscovery & 保留功能會置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="c8acd-207">July 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="c8acd-208">這也表示您將無法使用**New-MailboxSearch**、 **Start-MailboxSearch**或**Set-MailboxSearch** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8acd-208">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="c8acd-209">您只可以取得及移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-209">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="c8acd-210">替代工具</span><span class="sxs-lookup"><span data-stu-id="c8acd-210">Alternative tools</span></span>

<span data-ttu-id="c8acd-211">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="c8acd-211">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c8acd-212"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-212"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="c8acd-213"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-213"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="c8acd-214"><strong>註解</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-214"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c8acd-215">搜尋和匯出</span><span class="sxs-lookup"><span data-stu-id="c8acd-215">Search and export</span></span></td>
<td><p><span data-ttu-id="c8acd-216"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-216"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="c8acd-217"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-217"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="c8acd-218"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-218"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="c8acd-219">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-219">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="c8acd-220">您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="c8acd-220">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="c8acd-221">然後，您可以使用<strong>New-ComplianceSearchAction</strong> Cmdlet 來匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c8acd-221">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="c8acd-222">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c8acd-222">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="c8acd-223"><strong>附注：</strong>如果您使用這些 Cmdlet 來建立未與核心 eDiscovery 案例相關聯的搜尋，則這些搜尋會位於 Microsoft 365 規範中心的 [<strong>內容搜尋</strong>] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="c8acd-223"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c8acd-224">保留信箱中的內容</span><span class="sxs-lookup"><span data-stu-id="c8acd-224">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="c8acd-225"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-225"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="c8acd-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="c8acd-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="c8acd-228">Microsoft 365 規範中心的封存必須與 Get-compliancecase 相關聯。</span><span class="sxs-lookup"><span data-stu-id="c8acd-228">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="c8acd-229">首先，建立規範案例，然後建立 CaseHoldPolicy 及 New-caseholdrule。</span><span class="sxs-lookup"><span data-stu-id="c8acd-229">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="c8acd-230"><strong>附注：</strong>建立沒有建立 New-caseholdrule 的 CaseHoldPolicy，會在建立 New-caseholdrule 並與 CaseHoldPolicy 關聯之前，使保留無法運作。</span><span class="sxs-lookup"><span data-stu-id="c8acd-230"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="c8acd-231">如需詳細資訊，請參閱 Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="c8acd-231">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c8acd-232">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="c8acd-232">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="c8acd-233">無</span><span class="sxs-lookup"><span data-stu-id="c8acd-233">None</span></span></td>
<td><span data-ttu-id="c8acd-234">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="c8acd-234">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="c8acd-235">請參閱下列常見問題，以取得其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="c8acd-235">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="c8acd-236">FAQs 關於 \***-get-mailboxsearch 程式**Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c8acd-236">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="c8acd-237">**我們使用「複製搜尋」來匯出電子郵件訊息或立即訊息，以供其他 eDiscovery 和法律調查之用。停用這些 Cmdlet 後，還有哪些其他選項？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-237">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="c8acd-238">[<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph)提供許多方法，可讓您提取資料，以進行分析，以及與使用\*\* \*-get-mailboxsearch 程式\*\*指令程式相比更具彈性性及可擴充性的其他目的。</span><span class="sxs-lookup"><span data-stu-id="c8acd-238">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="c8acd-239">**如何將搜尋遷移並保留至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-239">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="c8acd-240">使用 PowerShell 腳本，可以從 Exchange 系統管理中心遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="c8acd-240">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="c8acd-241">如需詳細資訊，請參閱將[舊版 eDiscovery 搜尋和保留遷移至 Microsoft 365 規範中心](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-241">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="c8acd-242">**在終止 Cmdlet 後，是否仍然可以移除或取回搜尋？**</span><span class="sxs-lookup"><span data-stu-id="c8acd-242">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="c8acd-243">是的，雖然我們正在移除建立及修改搜尋的能力，但您仍然可以使用**Get-MailboxSearch**和**Remove-MailboxSearch** ，直到進一步通知。</span><span class="sxs-lookup"><span data-stu-id="c8acd-243">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="c8acd-244">不過，在退休日期之後使用這些 Cmdlet 會有您自己的風險，而且 Microsoft 支援將不再能夠提供協助。</span><span class="sxs-lookup"><span data-stu-id="c8acd-244">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="c8acd-245">Search-Mailbox Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c8acd-245">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="c8acd-246">Exchange Online PowerShell 中的**Search-Mailbox** Cmdlet 會在 [正在撤銷] 中，于最初宣告的指令中的指令，于2018中從後傳回的指令。</span><span class="sxs-lookup"><span data-stu-id="c8acd-246">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="c8acd-247">**Search-Mailbox** Cmdlet 最初是用來搜尋使用者的信箱，並清除惡意內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-247">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="c8acd-248">建議您開始使用 Office 365 安全性 & 規範中心 PowerShell 的**New-ComplianceSearch**和**New-ComplianceSearchAction** Cmdlet，以搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-248">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="c8acd-249">針對內建的安全性體驗， [<span class="underline">microsoft 365 的安全性功能</span>](https://docs.microsoft.com/microsoft-365/security/)可為電子郵件和許多其他 Microsoft 服務提供強健的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="c8acd-249">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="c8acd-250">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="c8acd-250">Scope of affected organizations</span></span>

- <span data-ttu-id="c8acd-251">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-251">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="c8acd-252">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-252">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="c8acd-253">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="c8acd-253">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="c8acd-254">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c8acd-254">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="c8acd-255">時間表</span><span class="sxs-lookup"><span data-stu-id="c8acd-255">Timeline</span></span>

-  <span data-ttu-id="c8acd-256">2020年4月1日：將無法再使用**Search-Mailbox** Cmdlet，而且 Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="c8acd-256">April 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="c8acd-257">替代工具</span><span class="sxs-lookup"><span data-stu-id="c8acd-257">Alternative tools</span></span>

<span data-ttu-id="c8acd-258">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="c8acd-258">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c8acd-259"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-259"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="c8acd-260"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-260"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="c8acd-261"><strong>註解</strong></span><span class="sxs-lookup"><span data-stu-id="c8acd-261"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c8acd-262">搜尋信箱</span><span class="sxs-lookup"><span data-stu-id="c8acd-262">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="c8acd-263"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-263"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="c8acd-264"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-264"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="c8acd-265">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-265">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="c8acd-266">您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="c8acd-266">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="c8acd-267">然後，您可以使用<strong>New-ComplianceSearchAction 匯出</strong>命令匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c8acd-267">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="c8acd-268">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c8acd-268">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="c8acd-269">清除信箱中的郵件</span><span class="sxs-lookup"><span data-stu-id="c8acd-269">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="c8acd-270"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-270"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="c8acd-271"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-271"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="c8acd-272">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-272">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="c8acd-273">您可以使用<strong>New-ComplianceSearch</strong>和<strong>New-ComplianceSearch</strong> Cmdlet 來建立和執行搜尋，然後您可以使用<strong>New-ComplianceSearchAction-Purge PurgeType</strong>命令來清除內容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-273">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="c8acd-274">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜尋並刪除郵件</span></a>。</span><span class="sxs-lookup"><span data-stu-id="c8acd-274">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c8acd-275">從信箱刪除大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="c8acd-275">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="c8acd-276"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">設定信箱的封存與刪除原則</span></a></span><span class="sxs-lookup"><span data-stu-id="c8acd-276"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="c8acd-277">系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="c8acd-277">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="c8acd-278">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="c8acd-278">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="c8acd-279">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="c8acd-279">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="c8acd-280">如需其他解決方案，請參閱<strong>\*-MailboxSearch Cmdlet</strong>區段中的 FAQs。</span><span class="sxs-lookup"><span data-stu-id="c8acd-280">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
</tbody>
</table>

## <a name="getsearchablemailboxes-setholdonmailboxes-and-getholdonmailboxes-operations-in-the-ews-api"></a><span data-ttu-id="c8acd-281">EWS API 中的 GetSearchableMailboxes、SetHoldOnMailboxes 及 GetHoldOnMailboxes 作業</span><span class="sxs-lookup"><span data-stu-id="c8acd-281">GetSearchableMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations in the EWS API</span></span>

<span data-ttu-id="c8acd-282">在 exchange 系統管理中心中，In-Place eDiscovery & 保留功能會使用這三個 Exchange Web 服務 APIs，而 exchange Online PowerShell 中的對應\*\* \*get-mailboxsearch 程式\*\*Cmdlet 會使用這些 exchange Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c8acd-282">These three Exchange Web Services APIs are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="c8acd-283">當您淘汰其他舊版 eDiscovery 工具時，也會將其淘汰。</span><span class="sxs-lookup"><span data-stu-id="c8acd-283">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="c8acd-284">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="c8acd-284">Scope of affected organizations</span></span>

- <span data-ttu-id="c8acd-285">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-285">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="c8acd-286">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-286">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="c8acd-287">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="c8acd-287">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="c8acd-288">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c8acd-288">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="c8acd-289">時間表</span><span class="sxs-lookup"><span data-stu-id="c8acd-289">Timeline</span></span>

- <span data-ttu-id="c8acd-290">2020年4月1日：將不再提供 GetSearchableMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 作業，而且 Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="c8acd-290">April 1, 2020: The GetSearchableMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="c8acd-291">Advanced eDiscovery v 1。0</span><span class="sxs-lookup"><span data-stu-id="c8acd-291">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="c8acd-292">Advanced ediscovery 1.0 版，這是 eDiscovery 案例中的高級 eDiscovery 版本，可透過按一下 [**切換至高級 ediscovery** ] 進行撤銷。</span><span class="sxs-lookup"><span data-stu-id="c8acd-292">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in an eDiscovery case by clicking **Switch to Advanced eDiscovery** is being retired.</span></span> <span data-ttu-id="c8acd-293">其功能已由 Microsoft 365 規範中心內的新「[高級 eDiscovery」解決方案](https://aka.ms/edisco)所取代。</span><span class="sxs-lookup"><span data-stu-id="c8acd-293">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="c8acd-294">Microsoft 365 （也稱為「 *Advanced ediscovery 2.0 2.0*」）中新的 [ediscovery 解決方案] 提供了原始解決方案的所有功能，但現在包含以保管人為基礎的方法，可識別其他 Microsoft 365 服務中的內容、收集該內容，然後將其新增至審閱集，以供檢閱者使用 fast search 查詢、標記和分析功能，協助挑選相關的檔。</span><span class="sxs-lookup"><span data-stu-id="c8acd-294">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="c8acd-295">「高級 eDiscovery」現在包括 Microsoft 和非 Microsoft 檔案類型的增強的處理和原生檢視器、[這裡](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)是檔案類型的完整清單，以及支援的元資料欄位在[這裡](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-295">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="c8acd-296">此外，新的高級 eDiscovery 解決方案提供功能強大的保管人功能，可讓您將保留套用至不同服務中的內容、通知使用者保留，以及追蹤保管人回應，全部都是在高級 eDiscovery 案例內。</span><span class="sxs-lookup"><span data-stu-id="c8acd-296">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="c8acd-297">此時，我們建議您開始將 eDiscovery 工作流程轉換為新的高級 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="c8acd-297">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="c8acd-298">雖然您仍然可以存取現有案例中的 Advanced eDiscovery 1.0 版，但 Microsoft 支援不會在2020年7月1日之後提供支援。</span><span class="sxs-lookup"><span data-stu-id="c8acd-298">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases, Microsoft Support won’t provide support after July 1, 2020.</span></span> <span data-ttu-id="c8acd-299">如需詳細資訊，請參閱下列時程表。</span><span class="sxs-lookup"><span data-stu-id="c8acd-299">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="c8acd-300">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="c8acd-300">Scope of affected organizations</span></span>
    
- <span data-ttu-id="c8acd-301">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-301">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="c8acd-302">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="c8acd-302">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="c8acd-303">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c8acd-303">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="c8acd-304">時間表</span><span class="sxs-lookup"><span data-stu-id="c8acd-304">Timeline</span></span>

- <span data-ttu-id="c8acd-305">2020年4月1日：您將無法建立新的高級 eDiscovery 1.0 案例。</span><span class="sxs-lookup"><span data-stu-id="c8acd-305">April 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="c8acd-306">2020年7月1日：您將無法在任何情況下新增資料（為高級 eDiscovery 準備搜尋結果）。</span><span class="sxs-lookup"><span data-stu-id="c8acd-306">July 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="c8acd-307">您將能夠繼續使用現有案例中的資料，必須自行承擔。</span><span class="sxs-lookup"><span data-stu-id="c8acd-307">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="c8acd-308">Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="c8acd-308">Microsoft Support will no longer provide assistance.</span></span> 

### <a name="alternative-tools"></a><span data-ttu-id="c8acd-309">替代工具</span><span class="sxs-lookup"><span data-stu-id="c8acd-309">Alternative tools</span></span>

<span data-ttu-id="c8acd-310">Microsoft 365 規範中心的[高級 eDiscovery 解決方案](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-310">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
