---
title: 舊版電子文件探索工具淘汰
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery 和 In-Place 暫止 (，) 中的對應 PowerShell Cmdlet 會在2020的上半年內淘汰。 Search-Mailbox Cmdlet 和 Advanced eDiscovery 的1.0 也會在相同的時段內淘汰。
ms.openlocfilehash: c5f1ddb4c817ebc316c2e2efdba9a4bc605eb5a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842659"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="f0acf-104">舊版電子文件探索工具淘汰</span><span class="sxs-lookup"><span data-stu-id="f0acf-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0acf-105">Microsoft 已評估公開健康情況，我們瞭解這對客戶造成的影響。</span><span class="sxs-lookup"><span data-stu-id="f0acf-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="f0acf-106">我們想要成為強大的合作夥伴和負責的全球公民。</span><span class="sxs-lookup"><span data-stu-id="f0acf-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="f0acf-107">為了簡化您面臨的眾多工作之一，我們會將本文所述之舊版 eDiscovery 工具的計畫停用延遲為三個月。</span><span class="sxs-lookup"><span data-stu-id="f0acf-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="f0acf-108">**更新後的退休日期會反映在下方。**</span><span class="sxs-lookup"><span data-stu-id="f0acf-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="f0acf-109">在幾年中，Microsoft 提供了 eDiscovery 工具，可讓您從 Exchange Online 搜尋、預覽及匯出電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="f0acf-110">不過，這些工具不再提供有效的方式，可在其他 Microsoft 365 服務中搜尋非 Exchange 內容，例如 SharePoint 線上及 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="f0acf-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="f0acf-111">為了解決此情況，Microsoft 提供了其他 eDiscovery 工具，可協助您搜尋各種各樣的 Microsoft 365 內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="f0acf-112">而且我們已致力於在[Microsoft 365 規範中心](https://compliance.microsoft.com)內整合最新和功能強大的 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="f0acf-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="f0acf-113">這可讓組織對許多 Microsoft 365 服務中的內容（包括 Exchange Online 在內）進行法律、內部及其他檔要求。</span><span class="sxs-lookup"><span data-stu-id="f0acf-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="f0acf-114">隨著 Microsoft 365 規範中心的這項新的和改良的 ediscovery 功能的產生，我們會在 Exchange Online 和 Microsoft 365 中，淘汰下列與搜尋電子郵件內容相關的 eDiscovery 相關功能：</span><span class="sxs-lookup"><span data-stu-id="f0acf-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="f0acf-115">Exchange 系統管理中心中[就地電子檔探索](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[In-Place 保留](/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-115">[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="f0acf-116">Exchange Online PowerShell 指令程式支援 In-Place eDiscovery 及 In-Place 保留， (這些指令程式共同識別為 \**-get-mailboxsearch 程式* Cmdlet) 。</span><span class="sxs-lookup"><span data-stu-id="f0acf-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="f0acf-117">這包括下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f0acf-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="f0acf-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="f0acf-118">New-MailboxSearch</span></span>](/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="f0acf-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="f0acf-119">Start-MailboxSearch</span></span>](/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="f0acf-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="f0acf-120">Stop-MailboxSearch</span></span>](/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="f0acf-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="f0acf-121">Set-MailboxSearch</span></span>](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="f0acf-122">當其他 \* \*-MailboxSearch \* \* \* \* \* 指令程式已停用之後，就可以使用 [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) 和 [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) Cmdlet，這樣您就可以使用這些 Cmdlet 來協助您轉換至其他 eDiscovery 和保留工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-122">The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="f0acf-123">不過，在下列 (所提及的特定日期之後) Microsoft 支援將不再支援這兩種 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0acf-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="f0acf-124">Exchange Online PowerShell 中的[Search-Mailbox](/powershell/module/exchange/search-mailbox) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0acf-124">The [Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="f0acf-125">Exchange Web 服務 API 中的下列作業：</span><span class="sxs-lookup"><span data-stu-id="f0acf-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="f0acf-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="f0acf-126">GetSearchableMailboxes</span></span>](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="f0acf-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="f0acf-127">SearchMailboxes</span></span>](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="f0acf-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="f0acf-128">SetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="f0acf-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="f0acf-129">GetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="f0acf-130">[Office 365 進階電子檔探索 1.0](./overview-ediscovery-20.md)版，也就是透過 Office 365 安全性 & 規範中心內的核心 eDiscovery 案例所存取 Advanced eDiscovery 的第一個版本。</span><span class="sxs-lookup"><span data-stu-id="f0acf-130">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="f0acf-131">停用 Advanced eDiscovery v 1.0 並不會影響您建立及管理核心 eDiscovery 案例的能力。</span><span class="sxs-lookup"><span data-stu-id="f0acf-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="f0acf-132">即將淘汰的 eDiscovery 功能僅適用于雲端型版本的 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f0acf-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="f0acf-133">在內部部署版本的 Exchange 和 SharePoint 中的 eDiscovery 功能仍會受到支援，直到進一步通知。</span><span class="sxs-lookup"><span data-stu-id="f0acf-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="f0acf-134">本文中的下列各節提供每個已撤銷的功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f0acf-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="f0acf-135">此資訊包含時程表和您可以使用的替代工具，而不是退休工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="f0acf-136">Exchange 系統管理中心中 In-Place eDiscovery 和 In-Place 存放</span><span class="sxs-lookup"><span data-stu-id="f0acf-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="f0acf-137">根據2017年7月1日的原始宣告，Exchange 系統管理員中心的 In-Place eDiscovery & 保留功能 (EAC) 即將停用。</span><span class="sxs-lookup"><span data-stu-id="f0acf-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="f0acf-138">EAC 中 In-Place eDiscovery & 保留頁面允許您從 Exchange Online 搜尋、保留及匯出內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="f0acf-139">In-Place eDiscovery 也可讓您將搜尋結果複製到探索信箱，讓您或其他 eDiscovery 管理員可以查看內容，並將其提供給法律、法規及公開的要求。</span><span class="sxs-lookup"><span data-stu-id="f0acf-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="f0acf-140">由於所有這些功能 (，除了將搜尋結果複製到探索信箱) 之外， [Microsoft 365 合規性中心](./microsoft-365-compliance-center.md)的 eDiscovery 和 Advanced eDiscovery 工具 (使用增強的功能、可靠性，以及支援廣泛的 Microsoft 365 服務) ，我們建議您儘早開始使用這些工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](./microsoft-365-compliance-center.md) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="f0acf-141">為了協助您轉換至這些其他 eDiscovery 工具，下表列出您可以使用的工具，而不是 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="f0acf-142">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="f0acf-142">Scope of affected organizations</span></span>

- <span data-ttu-id="f0acf-143">Office 365 和 Microsoft 365 企業版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="f0acf-144">Office 365 和 Microsoft 365 教育版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="f0acf-145">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD</span><span class="sxs-lookup"><span data-stu-id="f0acf-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="f0acf-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0acf-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="f0acf-147">退休的時程表</span><span class="sxs-lookup"><span data-stu-id="f0acf-147">Timeline for retirement</span></span>

- <span data-ttu-id="f0acf-148">2020年7月1日：您將無法建立新的搜尋和保留，但是您仍然可以自行承擔執行、編輯和刪除現有的搜尋。</span><span class="sxs-lookup"><span data-stu-id="f0acf-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="f0acf-149">Microsoft 支援將不會再 In-Place EAC 中的 eDiscovery & 保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="f0acf-150">2020年10月1日： In-Place eDiscovery & 保留 EAC 中的功能將置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="f0acf-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="f0acf-151">這表示您只可以移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="f0acf-152">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-152">Alternative tools</span></span>

<span data-ttu-id="f0acf-153">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f0acf-154">功能</span><span class="sxs-lookup"><span data-stu-id="f0acf-154">Functionality</span></span></th>
<th><span data-ttu-id="f0acf-155">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-155">Alternative tool</span></span></th>
<th><span data-ttu-id="f0acf-156">註解</span><span class="sxs-lookup"><span data-stu-id="f0acf-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f0acf-157">出於法律目的進行搜尋、匯出和保留</span><span class="sxs-lookup"><span data-stu-id="f0acf-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="f0acf-158">Microsoft 365 規範中心內的核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="f0acf-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="f0acf-159">使用核心 eDiscovery 案例的功能，可提供功能性同位，以 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="f0acf-160">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="f0acf-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="f0acf-161">搜尋可擴展至數百萬位置</span><span class="sxs-lookup"><span data-stu-id="f0acf-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="f0acf-162">更高的可靠性用於搜尋、匯出及放置內容保留</span><span class="sxs-lookup"><span data-stu-id="f0acf-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="f0acf-163">在 Exchange Online 中搜尋內容、SharePoint 線上、商務用 OneDrive、商務用 Skype、Microsoft Teams、Yammer 群組、Microsoft 365 群組，以及儲存在 Office 365 應用程式中的其他內容</span><span class="sxs-lookup"><span data-stu-id="f0acf-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0acf-164">保留以供保留用途</span><span class="sxs-lookup"><span data-stu-id="f0acf-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="f0acf-165">Microsoft 365 規範中心內的保留原則</span><span class="sxs-lookup"><span data-stu-id="f0acf-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="f0acf-166">您可以使用保留原則來保留內容，如有需要，請在保留期間到期之後加以刪除。</span><span class="sxs-lookup"><span data-stu-id="f0acf-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="f0acf-167">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="f0acf-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="f0acf-168">將原則套用至整個組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="f0acf-169">將原則套用至特定的內容位置，例如 Exchange Online、SharePoint 線上、商務用 OneDrive、商務用 Skype、Microsoft Teams 和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="f0acf-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="f0acf-170">將原則套用至特定使用者</span><span class="sxs-lookup"><span data-stu-id="f0acf-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="f0acf-171">如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/retention-policies"> 瞭解保留原則和保留標籤</a>。</span><span class="sxs-lookup"><span data-stu-id="f0acf-171">For more information, see <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f0acf-172">將電子郵件搜尋結果複製到探索信箱以供審閱</span><span class="sxs-lookup"><span data-stu-id="f0acf-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="f0acf-173">在 Advanced eDiscovery v 2.0 中檢查集合</span><span class="sxs-lookup"><span data-stu-id="f0acf-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="f0acf-174">在 Microsoft 365 中審閱內容的工作變得不容易。</span><span class="sxs-lookup"><span data-stu-id="f0acf-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="f0acf-175">「複查集」具有許多強大的功能，可協助您減少所需的查看時間和資料量，包括：</span><span class="sxs-lookup"><span data-stu-id="f0acf-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0acf-176">執行 fast search 查詢及篩選審閱集中的內容</span><span class="sxs-lookup"><span data-stu-id="f0acf-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="f0acf-177">分析審閱集中的內容;這包括電子郵件執行緒、接近重複偵測、主題分析和預測編碼</span><span class="sxs-lookup"><span data-stu-id="f0acf-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="f0acf-178">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="f0acf-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="f0acf-179">標記建議，以協助識別律師用戶端許可權內容</span><span class="sxs-lookup"><span data-stu-id="f0acf-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="f0acf-180">如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的進階電子文件探索解決方案概觀</a>。</span><span class="sxs-lookup"><span data-stu-id="f0acf-180">For more information, see <a href="/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="f0acf-181">或者，您可以將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 365 匯入服務，將 pst 匯入探索信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="f0acf-182">如需逐步指示，請參閱<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用網路上傳將 PST 檔案匯入至 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="f0acf-182">For step-by-step instruction, see <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="f0acf-183">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="f0acf-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="f0acf-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="f0acf-185">若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="f0acf-186">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="f0acf-187">從 [可復原的專案] 資料夾還原專案</span><span class="sxs-lookup"><span data-stu-id="f0acf-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="f0acf-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="f0acf-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="f0acf-189">您可以還原永久刪除的專案 (也稱為虛 <i>刪除的</i> 專案) 在信箱中，只要專案的刪除專案保留期間尚未過期。</span><span class="sxs-lookup"><span data-stu-id="f0acf-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="f0acf-190">如需詳細資訊，請參閱<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的 [可復原的專案] 資料夾</a>。</span><span class="sxs-lookup"><span data-stu-id="f0acf-190">For more information, see <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="f0acf-191">有關 In-Place eDiscovery 和 In-Place 保留的 FAQs</span><span class="sxs-lookup"><span data-stu-id="f0acf-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="f0acf-192">**我使用 In-Place eDiscovery & 的「副本搜尋結果」功能，將搜尋結果複製到探索信箱，以供律師審閱。我現在有哪些選項？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-192">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="f0acf-193">目前有兩種方法可以複製這項功能。</span><span class="sxs-lookup"><span data-stu-id="f0acf-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="f0acf-194">第一個用途是使用[Advanced eDiscovery v 2.0 中的審閱集](./view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-194">The first is to use [review sets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md).</span></span> <span data-ttu-id="f0acf-195">「審閱」集中的功能，您可以在傳統的回顧工具中看到許多相同的功能，例如快速搜尋檔、標記、電子郵件執行緒、接近重複群組、主題分析和預測編碼。</span><span class="sxs-lookup"><span data-stu-id="f0acf-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="f0acf-196">如果您仍然想要使用探索信箱進行審閱，第二個選項是將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 規範中心的 [Pst 匯入] [功能](use-network-upload-to-import-pst-files.md) ，將 pst 檔案匯入到探索信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="f0acf-197">**如何控制哪些內容位置 (例如可 eDiscovery 管理員可以使用新工具搜尋的信箱或網站) ？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="f0acf-198">Microsoft 365 規範中心也會使用[規範界限](set-up-compliance-boundaries.md)來控制 eDiscovery 管理員可搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="f0acf-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="f0acf-199">規範界限可用於政府機構內，但必須保持在代理商界限或具備地理位置 boarders 的多國公司。</span><span class="sxs-lookup"><span data-stu-id="f0acf-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="f0acf-200">**如何將目前的搜尋和保留移至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="f0acf-201">您可以使用 PowerShell 從 EAC 遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="f0acf-202">如需相關指示，請參閱將[搜尋和保留從 EAC 遷移至 Microsoft 365 規範中心](./migrate-legacy-ediscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="f0acf-203">\*-Get-mailboxsearch 程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f0acf-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="f0acf-204">根據在 Exchange 系統管理中心的2017年7月1日宣佈的原始宣告，In-Place eDiscovery & 保留功能和對應的 **\* get-mailboxsearch 程式** Cmdlet 即將停用。</span><span class="sxs-lookup"><span data-stu-id="f0acf-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="f0acf-205">這些 Cmdlet 可讓使用者搜尋、保留及匯出法律、法規及公開要求的信箱內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="f0acf-206">因為這些功能現在可在[<span class="underline">Microsoft 365 規範中心</span>](./microsoft-365-compliance-center.md)中取得，而且 Office 365 安全性 & 合規性中心 PowerShell 改善的效能與擴充性，所以您應該使用這些改進的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0acf-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](./microsoft-365-compliance-center.md) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="f0acf-207">這些 Cmdlet 包括[<span class="underline"> \* -get-compliancecase</span>](/powershell/module/exchange/get-compliancecase)、 [<span class="underline"> \* -new-compliancesearch</span>](/powershell/module/exchange/get-compliancesearch)、 [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy)、 [<span class="underline"> \* -new-caseholdrule</span>](/powershell/module/exchange/get-caseholdrule)及[<span class="underline"> \* -new-compliancesearchaction</span>](/powershell/module/exchange/get-compliancesearchaction)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="f0acf-208">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="f0acf-208">Scope of affected organizations</span></span>

- <span data-ttu-id="f0acf-209">Office 365 和 Microsoft 365 企業版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="f0acf-210">Office 365 和 Microsoft 365 教育版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="f0acf-211">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD</span><span class="sxs-lookup"><span data-stu-id="f0acf-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="f0acf-212">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0acf-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="f0acf-213">時間表</span><span class="sxs-lookup"><span data-stu-id="f0acf-213">Timeline</span></span>

- <span data-ttu-id="f0acf-214">2020年7月1日：您將無法使用 **New-MailboxSearch** 來建立新的 In-Place eDiscovery 搜尋和 In-Place 保留，但是您仍然可以使用 Cmdlet 來執行、編輯和刪除現有的搜尋，並以您自己的風險進行。</span><span class="sxs-lookup"><span data-stu-id="f0acf-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="f0acf-215">Microsoft 支援人員將不再為這些類型的搜尋和保留提供協助。</span><span class="sxs-lookup"><span data-stu-id="f0acf-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="f0acf-216">2020年10月1日：如先前所述，將 EAC 中的 In-Place eDiscovery & 保留功能會置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="f0acf-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="f0acf-217">這也表示您將無法使用 **New-MailboxSearch**、 **Start-MailboxSearch** 或 **Set-MailboxSearch** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0acf-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="f0acf-218">您只可以取得及移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="f0acf-219">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-219">Alternative tools</span></span>

<span data-ttu-id="f0acf-220">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f0acf-221">功能</span><span class="sxs-lookup"><span data-stu-id="f0acf-221">Functionality</span></span></th>
<th><span data-ttu-id="f0acf-222">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-222">Alternative tools</span></span></th>
<th><span data-ttu-id="f0acf-223">註解</span><span class="sxs-lookup"><span data-stu-id="f0acf-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f0acf-224">搜尋和匯出</span><span class="sxs-lookup"><span data-stu-id="f0acf-224">Search and export</span></span></td>
<td><p><span data-ttu-id="f0acf-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="f0acf-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="f0acf-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="f0acf-228">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="f0acf-229">您可以使用 <strong>新的-</strong>、 <strong>Get</strong>及 <strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="f0acf-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="f0acf-230">然後，您可以使用 <strong>New-ComplianceSearchAction</strong> Cmdlet 來匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f0acf-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="f0acf-231">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="f0acf-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="f0acf-232"><strong>附注：</strong>如果您使用這些 Cmdlet 來建立未與核心 eDiscovery 案例相關聯的搜尋，這些搜尋會位於 Microsoft 365 規範中心的「<strong>內容搜尋</strong>」頁面上。</span><span class="sxs-lookup"><span data-stu-id="f0acf-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0acf-233">保留信箱中的內容</span><span class="sxs-lookup"><span data-stu-id="f0acf-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="f0acf-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="f0acf-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="f0acf-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="f0acf-237">保留在 Microsoft 365 規範中心必須與 get-compliancecase 相關聯。</span><span class="sxs-lookup"><span data-stu-id="f0acf-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="f0acf-238">首先，建立規範案例，然後建立 CaseHoldPolicy 及 New-caseholdrule。</span><span class="sxs-lookup"><span data-stu-id="f0acf-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="f0acf-239"><strong>附注：</strong> 建立沒有建立 New-caseholdrule 的 CaseHoldPolicy，會在建立 New-caseholdrule 並與 CaseHoldPolicy 關聯之前，使保留無法運作。</span><span class="sxs-lookup"><span data-stu-id="f0acf-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="f0acf-240">如需詳細資訊，請參閱 Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="f0acf-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f0acf-241">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="f0acf-242">無</span><span class="sxs-lookup"><span data-stu-id="f0acf-242">None</span></span></td>
<td><span data-ttu-id="f0acf-243">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="f0acf-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="f0acf-244">請參閱下列常見問題，以取得其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="f0acf-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="f0acf-245">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="f0acf-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="f0acf-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="f0acf-247">若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="f0acf-248">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="f0acf-249">FAQs 關於 \***-get-mailboxsearch 程式** Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f0acf-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="f0acf-250">**我們使用「複製搜尋」來匯出電子郵件訊息或立即訊息，以供其他 eDiscovery 和法律調查之用。停用這些 Cmdlet 後，還有哪些其他選項？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="f0acf-251">[<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph)提供許多方法，可讓您提取資料，以進行分析，以及與使用 **\* -get-mailboxsearch 程式** 指令程式相比更具彈性性及可擴充性的其他目的。</span><span class="sxs-lookup"><span data-stu-id="f0acf-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="f0acf-252">**如何將搜尋遷移並保留至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="f0acf-253">您可以使用 PowerShell 腳本，從 Exchange 系統管理中心遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="f0acf-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="f0acf-254">如需詳細資訊，請參閱[遷移舊版 eDiscovery 搜尋並保留至 Microsoft 365 規範中心](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="f0acf-255">**在終止 Cmdlet 後，是否仍然可以移除或取回搜尋？**</span><span class="sxs-lookup"><span data-stu-id="f0acf-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="f0acf-256">是的，雖然我們正在移除建立及修改搜尋的能力，但您仍然可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch** ，直到進一步通知。</span><span class="sxs-lookup"><span data-stu-id="f0acf-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="f0acf-257">不過，在退休日期之後使用這些 Cmdlet 會有您自己的風險，而且 Microsoft 支援將不再能夠提供協助。</span><span class="sxs-lookup"><span data-stu-id="f0acf-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="f0acf-258">Search-Mailbox Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f0acf-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="f0acf-259">Exchange Online PowerShell 中的 **Search-Mailbox** Cmdlet 已于最初宣告時，在指令指令的指令中從2018開始傳回的警告。</span><span class="sxs-lookup"><span data-stu-id="f0acf-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="f0acf-260">**Search-Mailbox** Cmdlet 最初是用來搜尋使用者的信箱，並清除惡意內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="f0acf-261">建議您開始使用 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** Cmdlet Office 365 安全性 & 規範中心 PowerShell 來搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="f0acf-262">針對內建的安全性體驗，Microsoft 365 的[<span class="underline">安全性功能</span>](../security/index.yml)會為電子郵件和許多其他 Microsoft 服務提供強健的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="f0acf-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](../security/index.yml) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="f0acf-263">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="f0acf-263">Scope of affected organizations</span></span>

- <span data-ttu-id="f0acf-264">Office 365 和 Microsoft 365 企業版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="f0acf-265">Office 365 和 Microsoft 365 教育版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="f0acf-266">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD</span><span class="sxs-lookup"><span data-stu-id="f0acf-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="f0acf-267">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0acf-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="f0acf-268">時間表</span><span class="sxs-lookup"><span data-stu-id="f0acf-268">Timeline</span></span>

-  <span data-ttu-id="f0acf-269">2020年7月1日：將無法再使用 **Search-Mailbox** Cmdlet，Microsoft 支援人員將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="f0acf-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="f0acf-270">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-270">Alternative tools</span></span>

<span data-ttu-id="f0acf-271">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="f0acf-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f0acf-272">功能</span><span class="sxs-lookup"><span data-stu-id="f0acf-272">Functionality</span></span></th>
<th><span data-ttu-id="f0acf-273">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-273">Alternative tools</span></span></th>
<th><span data-ttu-id="f0acf-274">註解</span><span class="sxs-lookup"><span data-stu-id="f0acf-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f0acf-275">搜尋信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="f0acf-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="f0acf-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="f0acf-278">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="f0acf-279">您可以使用 <strong>新的-</strong>、 <strong>Get</strong>及 <strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="f0acf-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="f0acf-280">然後，您可以使用 <strong>New-ComplianceSearchAction 匯出</strong> 命令匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f0acf-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="f0acf-281">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="f0acf-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0acf-282">從信箱刪除大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="f0acf-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="f0acf-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">設定信箱的封存與刪除原則</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="f0acf-284">系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0acf-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0acf-285">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="f0acf-286">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="f0acf-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="f0acf-287">如需其他解決方案，請參閱 <strong>\*-MailboxSearch Cmdlet</strong> 區段中的 FAQs。</span><span class="sxs-lookup"><span data-stu-id="f0acf-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="f0acf-288">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="f0acf-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="f0acf-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="f0acf-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="f0acf-290">若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="f0acf-291">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="f0acf-292">清除信箱中的郵件</span><span class="sxs-lookup"><span data-stu-id="f0acf-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="f0acf-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="f0acf-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="f0acf-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="f0acf-295">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="f0acf-296">您可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> Cmdlet 來建立和執行搜尋，然後您可以使用 <strong>New-ComplianceSearchAction-Purge PurgeType</strong> 命令來清除內容。</span><span class="sxs-lookup"><span data-stu-id="f0acf-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="f0acf-297">如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜尋並刪除郵件</span></a>。</span><span class="sxs-lookup"><span data-stu-id="f0acf-297">For more information, see <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="f0acf-298">清除信箱中的郵件</span><span class="sxs-lookup"><span data-stu-id="f0acf-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="f0acf-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="f0acf-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="f0acf-300">若要清除信箱中的郵件，請指派管理員許可權來存取該員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0acf-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="f0acf-301">您可以在必要時刪除和回收郵件，以利用 Outlook 中內建的搜尋和觀賞功能。</span><span class="sxs-lookup"><span data-stu-id="f0acf-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="f0acf-302">ExchangeWeb 服務 API 作業</span><span class="sxs-lookup"><span data-stu-id="f0acf-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="f0acf-303">Exchange Web 服務 API 中的這些作業是由 Exchange 系統管理中心中的 In-Place eDiscovery & 保留功能，以及 Exchange Online PowerShell 中的對應 **\* get-mailboxsearch 程式** Cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="f0acf-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="f0acf-304">當您淘汰其他舊版 eDiscovery 工具時，也會將其淘汰。</span><span class="sxs-lookup"><span data-stu-id="f0acf-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="f0acf-305">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="f0acf-305">Scope of affected organizations</span></span>

- <span data-ttu-id="f0acf-306">Office 365 和 Microsoft 365 企業版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="f0acf-307">Office 365 和 Microsoft 365 教育版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="f0acf-308">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD</span><span class="sxs-lookup"><span data-stu-id="f0acf-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="f0acf-309">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0acf-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="f0acf-310">時間表</span><span class="sxs-lookup"><span data-stu-id="f0acf-310">Timeline</span></span>

- <span data-ttu-id="f0acf-311">2020年7月1日：將不再提供 GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 作業，而且 Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="f0acf-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="f0acf-312">Advanced eDiscovery v 1。0</span><span class="sxs-lookup"><span data-stu-id="f0acf-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="f0acf-313">Advanced eDiscovery 1.0 版，也就是在核心 eDiscovery 案例中，按一下 [**切換至 Advanced eDiscovery**]，就會停用 Advanced eDiscovery 的版本。</span><span class="sxs-lookup"><span data-stu-id="f0acf-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="f0acf-314">其功能已由 Microsoft 365 規範中心內的新[Advanced eDiscovery 解決方案](./ediscovery.md)所取代。</span><span class="sxs-lookup"><span data-stu-id="f0acf-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](./ediscovery.md) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="f0acf-315">若要判斷您的組織是否使用 Advanced eDiscovery 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="f0acf-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="f0acf-316">移至[Office 365 安全性 & 規範中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="f0acf-317">在安全性 & 規範中心的左功能窗格中，按一下 [ **ediscovery > ediscovery**，然後開啟核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="f0acf-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="f0acf-318">如果您看到 [**切換至 Advanced eDiscovery** ] 按鈕，按一下該按鈕將會帶您的1.0 版 Advanced eDiscovery （即將淘汰）。</span><span class="sxs-lookup"><span data-stu-id="f0acf-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="f0acf-319">在核心 eDiscovery 中建立及管理案例的功能將不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="f0acf-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="f0acf-320">只有透過按一下 [**切換至 Advanced eDiscovery** ]) 才能在 Advanced eDiscovery 的 1.0 (中新增及分析大小寫資料的功能會被停用。</span><span class="sxs-lookup"><span data-stu-id="f0acf-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="f0acf-321">Microsoft 365 中的新 Advanced eDiscovery 方案 (也稱為 *Advanced eDiscovery v 2.0*) 提供原始解決方案的所有功能，但現在包含以保管人為基礎的方法，可識別其他 Microsoft 365 服務中的內容、收集該內容，然後將其新增至審閱集，讓檢閱者可以利用 fast search 查詢、標記和分析功能，以挑選相關的檔。</span><span class="sxs-lookup"><span data-stu-id="f0acf-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="f0acf-322">Advanced eDiscovery 現在包括 Microsoft 和非 Microsoft 檔案類型的增強處理和原生檢視器，[這裡](./supported-filetypes-ediscovery20.md)有檔案類型的完整清單和支援的元資料欄位在[這裡](./document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields are [here](./document-metadata-fields-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="f0acf-323">此外，新的 Advanced eDiscovery 解決方案提供功能強大的保管人保留功能，可讓您將保留套用至不同服務中的內容、通知使用者保留，以及追蹤保管人回應，全部都是在 Advanced eDiscovery 案例內。</span><span class="sxs-lookup"><span data-stu-id="f0acf-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="f0acf-324">若要存取進階電子文件探索 v2.0：</span><span class="sxs-lookup"><span data-stu-id="f0acf-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="f0acf-325">移至 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="f0acf-326">在 Microsoft 365 合規性中心的左功能窗格中，按一下 \*\*\*\*[顯示全部]，然後按一下 \*\*\*\*[電子文件探索] > [進階]。</span><span class="sxs-lookup"><span data-stu-id="f0acf-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="f0acf-327">此時，我們建議您開始將 eDiscovery 工作流程轉換為新的 Advanced eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="f0acf-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="f0acf-328">如有需要，您可以匯出內容並將其儲存在離線狀態，封存 Advanced eDiscovery 1.0 案例。</span><span class="sxs-lookup"><span data-stu-id="f0acf-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="f0acf-329">雖然您仍然可以在現有案例中存取 Advanced eDiscovery 的1.0，直到2020年12月31日為止，Microsoft 支援服務不會在 2020 10 月1日之後提供支援。</span><span class="sxs-lookup"><span data-stu-id="f0acf-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="f0acf-330">如需詳細資訊，請參閱下列時程表。</span><span class="sxs-lookup"><span data-stu-id="f0acf-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="f0acf-331">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="f0acf-331">Scope of affected organizations</span></span>

- <span data-ttu-id="f0acf-332">Office 365 和 Microsoft 365 企業版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="f0acf-333">Office 365 和 Microsoft 365 教育版組織</span><span class="sxs-lookup"><span data-stu-id="f0acf-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="f0acf-334">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD</span><span class="sxs-lookup"><span data-stu-id="f0acf-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="f0acf-335">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0acf-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="f0acf-336">時間表</span><span class="sxs-lookup"><span data-stu-id="f0acf-336">Timeline</span></span>

- <span data-ttu-id="f0acf-337">2020年7月1日：您將無法建立新的 Advanced eDiscovery 1.0 案例。</span><span class="sxs-lookup"><span data-stu-id="f0acf-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="f0acf-338">2020年10月1日：您將無法新增資料 (針對 Advanced eDiscovery) 的任何案例準備搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f0acf-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="f0acf-339">您將能夠繼續使用現有案例中的資料，必須自行承擔。</span><span class="sxs-lookup"><span data-stu-id="f0acf-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="f0acf-340">Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="f0acf-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="f0acf-341">2020年12月31日：您將無法存取 Advanced eDiscovery 的1.0 案例。</span><span class="sxs-lookup"><span data-stu-id="f0acf-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="f0acf-342">替代工具</span><span class="sxs-lookup"><span data-stu-id="f0acf-342">Alternative tools</span></span>

<span data-ttu-id="f0acf-343">Microsoft 365 規範中心的[Advanced eDiscovery 解決方案](./overview-ediscovery-20.md)。</span><span class="sxs-lookup"><span data-stu-id="f0acf-343">The [Advanced eDiscovery solution](./overview-ediscovery-20.md) in the Microsoft 365 compliance center.</span></span>