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
description: Exchange Online 中的 In-Place eDiscovery 和 In-Place 保留（以及對應的 PowerShell Cmdlet）會在2020的上半年內淘汰。 Search-Mailbox Cmdlet 及 Advanced eDiscovery 1.0 1.0 也會在相同的時段內淘汰。
ms.openlocfilehash: 8b428b0d90442c937e08d4dc9ca23fb345553178
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761683"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="cc5cb-104">舊版電子文件探索工具淘汰</span><span class="sxs-lookup"><span data-stu-id="cc5cb-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc5cb-105">Microsoft 已評估公開健康情況，我們瞭解這對客戶造成的影響。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="cc5cb-106">我們想要成為強大的合作夥伴和負責的全球公民。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="cc5cb-107">為了簡化您面臨的眾多工作之一，我們會將本文所述之舊版 eDiscovery 工具的計畫停用延遲為三個月。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="cc5cb-108">**更新後的退休日期會反映在下方。**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="cc5cb-109">在幾年中，Microsoft 提供了 eDiscovery 工具，可讓您從 Exchange Online 搜尋、預覽及匯出電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="cc5cb-110">不過，這些工具不再提供有效的方式，可在其他 Microsoft 365 服務中搜尋非 Exchange 內容，例如 SharePoint 線上和 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="cc5cb-111">為了解決此情況，Microsoft 提供了其他 eDiscovery 工具，可協助您搜尋各種各樣的 Microsoft 365 內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="cc5cb-112">而且我們致力於在[Microsoft 365 規範中心](https://compliance.microsoft.com)內整合最新和功能強大的 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="cc5cb-113">這可讓組織對許多 Microsoft 365 服務（包括 Exchange Online）的內容，回應法律、內部及其他檔要求。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="cc5cb-114">由於 Microsoft 365 規範中心的這項新的和改善的 eDiscovery 功能，我們即將淘汰下列與電子檔內容在 Exchange Online 和 Microsoft 365 中搜尋相關的 eDiscovery 相關功能：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="cc5cb-115">在 Exchange 系統管理中心中[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[In-Place 存放](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="cc5cb-116">Exchange Online PowerShell Cmdlet，支援 In-Place eDiscovery 和 In-Place 保留（這些 Cmdlet 共同識別為 \**-get-mailboxsearch 程式*Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="cc5cb-117">這包括下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="cc5cb-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="cc5cb-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="cc5cb-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="cc5cb-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="cc5cb-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="cc5cb-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="cc5cb-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="cc5cb-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="cc5cb-122">當其他 \* \*-MailboxSearch \* \* \* \* \* 指令程式已停用之後，就可以使用[Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)和[Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) Cmdlet，這樣您就可以使用這些 Cmdlet 來協助您轉換至其他 eDiscovery 和保留工具。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="cc5cb-123">不過，在特定日期（如下所示）之後，Microsoft 支援將不再支援這兩個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="cc5cb-124">Exchange Online PowerShell 中的[Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox?view=exchange-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox?view=exchange-ps) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="cc5cb-125">Exchange Web 服務 API 中的下列作業：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="cc5cb-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="cc5cb-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="cc5cb-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="cc5cb-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="cc5cb-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="cc5cb-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="cc5cb-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="cc5cb-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="cc5cb-130">[Office 365 Advanced ediscovery 1.0](office-365-advanced-ediscovery.md)版，也就是透過 Office 365 安全性 & 合規性中心的核心 eDiscovery 案例所存取的第一個版本。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="cc5cb-131">停用高級 eDiscovery 1.0 版不會影響您建立及管理核心 eDiscovery 案例的能力。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="cc5cb-132">即將淘汰的 eDiscovery 功能僅適用于雲端式版本的 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="cc5cb-133">在內部部署 Exchange 和 SharePoint 版本中的 eDiscovery 功能仍會受到支援，直到進一步通知為止。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="cc5cb-134">本文中的下列各節提供每個已撤銷的功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="cc5cb-135">此資訊包含時程表和您可以使用的替代工具，而不是退休工具。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="cc5cb-136">在 Exchange 系統管理中心中 In-Place eDiscovery 和 In-Place 存放</span><span class="sxs-lookup"><span data-stu-id="cc5cb-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="cc5cb-137">根據原始宣告于2017年7月1日，在 Exchange 系統管理中心（EAC）中的 In-Place eDiscovery & 保留功能即將淘汰。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="cc5cb-138">EAC 中 In-Place eDiscovery & 保留頁面可讓您搜尋、保留及匯出 Exchange Online 中的內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="cc5cb-139">In-Place eDiscovery 也可讓您將搜尋結果複製到探索信箱，讓您或其他 eDiscovery 管理員可以查看內容，並將其提供給法律、法規及公開的要求。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="cc5cb-140">由於所有這些功能（除了將搜尋結果複製到探索信箱之外）現在可在[Microsoft 365 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)的內容搜尋、Ediscovery 和高級 ediscovery 工具中取得，因此我們建議您儘快開始使用這些工具（改進功能、可靠性和365支援）。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="cc5cb-141">為了協助您轉換至這些其他 eDiscovery 工具，下表列出您可以使用的工具，而不是 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="cc5cb-142">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="cc5cb-142">Scope of affected organizations</span></span>

- <span data-ttu-id="cc5cb-143">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="cc5cb-144">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="cc5cb-145">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="cc5cb-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="cc5cb-146">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="cc5cb-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="cc5cb-147">退休的時程表</span><span class="sxs-lookup"><span data-stu-id="cc5cb-147">Timeline for retirement</span></span>

- <span data-ttu-id="cc5cb-148">2020年7月1日：您將無法建立新的搜尋和保留，但是您仍然可以自行承擔執行、編輯和刪除現有的搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="cc5cb-149">Microsoft 支援將不會再 In-Place EAC 中的 eDiscovery & 保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="cc5cb-150">2020年10月1日： In-Place eDiscovery & 保留 EAC 中的功能將置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="cc5cb-151">這表示您只可以移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="cc5cb-152">替代工具</span><span class="sxs-lookup"><span data-stu-id="cc5cb-152">Alternative tools</span></span>

<span data-ttu-id="cc5cb-153">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cc5cb-154"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-154"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="cc5cb-155"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-155"><strong>Alternative tool</strong></span></span></th>
<th><span data-ttu-id="cc5cb-156"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-156"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cc5cb-157">出於法律目的進行搜尋、匯出和保留</span><span class="sxs-lookup"><span data-stu-id="cc5cb-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="cc5cb-158">Microsoft 365 規範中心內的核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="cc5cb-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="cc5cb-159">使用核心 eDiscovery 案例的功能，可提供功能性同位，以 In-Place eDiscovery 和 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="cc5cb-160">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="cc5cb-161">搜尋可擴展至數百萬位置</span><span class="sxs-lookup"><span data-stu-id="cc5cb-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="cc5cb-162">更高的可靠性用於搜尋、匯出及放置內容保留</span><span class="sxs-lookup"><span data-stu-id="cc5cb-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="cc5cb-163">在 Exchange Online 中搜尋內容、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊、Yammer 群組、Microsoft 365 群組，以及其他儲存在 Office 365 應用程式中的內容</span><span class="sxs-lookup"><span data-stu-id="cc5cb-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
<p><span data-ttu-id="cc5cb-164">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">管理 Office 365 的法律調查</a>。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-164">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Manage legal investigations in Office 365</a>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc5cb-165">保留以供保留用途</span><span class="sxs-lookup"><span data-stu-id="cc5cb-165">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="cc5cb-166">Microsoft 365 規範中心內的保留原則</span><span class="sxs-lookup"><span data-stu-id="cc5cb-166">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="cc5cb-167">您可以使用保留原則來保留內容，如有需要，請在保留期間到期之後加以刪除。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-167">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="cc5cb-168">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-168">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="cc5cb-169">將原則套用至整個組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-169">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="cc5cb-170">將原則套用至特定的內容位置，例如 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="cc5cb-170">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="cc5cb-171">將原則套用至特定使用者</span><span class="sxs-lookup"><span data-stu-id="cc5cb-171">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="cc5cb-172">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">保留原則一覽</a>。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-172">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Overview of retention policies</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cc5cb-173">將電子郵件搜尋結果複製到探索信箱以供審閱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-173">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="cc5cb-174">在高級 eDiscovery 2.0 中複查集</span><span class="sxs-lookup"><span data-stu-id="cc5cb-174">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="cc5cb-175">在 Microsoft 365 中審閱內容的工作並不容易。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-175">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="cc5cb-176">「複查集」具有許多強大的功能，可協助您減少所需的查看時間和資料量，包括：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-176">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc5cb-177">執行 fast search 查詢及篩選審閱集中的內容</span><span class="sxs-lookup"><span data-stu-id="cc5cb-177">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="cc5cb-178">分析審閱集中的內容;這包括電子郵件執行緒、接近重複偵測、主題分析和預測編碼</span><span class="sxs-lookup"><span data-stu-id="cc5cb-178">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="cc5cb-179">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="cc5cb-179">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="cc5cb-180">標記建議，以協助識別律師用戶端許可權內容</span><span class="sxs-lookup"><span data-stu-id="cc5cb-180">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="cc5cb-181">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的進階電子文件探索解決方案概觀</a>。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-181">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="cc5cb-182">或者，您可以將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 365 匯入服務將 Pst 匯入探索信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-182">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="cc5cb-183">如需逐步指示，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用網路上傳將 PST 檔案匯入 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-183">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="cc5cb-184">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-184">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="cc5cb-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="cc5cb-186">若要讓人員能夠存取另一個使用者的電子郵件（例如，當員工離開您的組織，而您需要讓其他人存取先前員工的電子郵件），建議您指派該人員存取先前員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-186">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="cc5cb-187">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-187">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="cc5cb-188">從 [可復原的專案] 資料夾還原專案</span><span class="sxs-lookup"><span data-stu-id="cc5cb-188">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="cc5cb-189"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="cc5cb-189"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="cc5cb-190">您可以還原信箱中永久刪除的專案（也稱為虛<i>刪除的</i>專案），只要專案的刪除專案保留期間尚未過期。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-190">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="cc5cb-191">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中</a>的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-191">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="cc5cb-192">有關 In-Place eDiscovery 和 In-Place 保留的 FAQs</span><span class="sxs-lookup"><span data-stu-id="cc5cb-192">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="cc5cb-193">**我使用 In-Place eDiscovery & 的「副本搜尋結果」功能，將搜尋結果複製到探索信箱，以供律師審閱。我現在有哪些選項？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-193">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="cc5cb-194">目前有兩種方法可以複製這項功能。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-194">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="cc5cb-195">第一個用途是使用[高級 eDiscovery 2.0 版中的複查集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-195">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="cc5cb-196">「審閱」集中的功能，您可以在傳統的回顧工具中看到許多相同的功能，例如快速搜尋檔、標記、電子郵件執行緒、接近重複群組、主題分析和預測編碼。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-196">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="cc5cb-197">如果您仍然想要使用探索信箱進行審閱，第二個選項是將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 規範中心的 [Pst 匯入][功能](use-network-upload-to-import-pst-files.md)，將 pst 檔案匯入到探索信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-197">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="cc5cb-198">**如何控制 eDiscovery 管理員可使用新工具進行搜尋的內容位置（例如信箱或網站）？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-198">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="cc5cb-199">Microsoft 365 規範中心也會使用[規範界限](set-up-compliance-boundaries.md)來控制 eDiscovery 管理員可搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-199">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="cc5cb-200">規範界限可用於政府機構內，但必須保持在代理商界限或具備地理位置 boarders 的多國公司。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-200">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="cc5cb-201">**如何將目前的搜尋和保留移動至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-201">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="cc5cb-202">您可以使用 PowerShell 從 EAC 遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-202">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="cc5cb-203">如需相關指示，請參閱將[搜尋和保留從 EAC 遷移至 Microsoft 365 規範中心](https://go.microsoft.com/fwlink/?linkid=2114224)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-203">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="cc5cb-204">\*-Get-mailboxsearch 程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cc5cb-204">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="cc5cb-205">根據在 Exchange 系統管理中心的2017年7月1日宣佈的原始宣告，In-Place eDiscovery & 保留功能和對應的\*\* \* get-mailboxsearch 程式\*\*Cmdlet 即將停用。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-205">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="cc5cb-206">這些 Cmdlet 可讓使用者搜尋、保留及匯出法律、法規及公開要求的信箱內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-206">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="cc5cb-207">由於這些功能現在可在[<span class="underline">Microsoft 365 規範中心</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)和 Office 365 安全性 & 合規性中心 PowerShell 取得，提高效能與擴充性，所以您應該使用這些改進的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-207">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="cc5cb-208">這些 Cmdlet 包括[<span class="underline"> \* -get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)、 [<span class="underline"> \* -new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)、 [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)、 [<span class="underline"> \* -new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)及[<span class="underline"> \* -new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-208">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="cc5cb-209">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="cc5cb-209">Scope of affected organizations</span></span>

- <span data-ttu-id="cc5cb-210">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-210">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="cc5cb-211">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-211">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="cc5cb-212">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="cc5cb-212">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="cc5cb-213">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="cc5cb-213">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="cc5cb-214">時間表</span><span class="sxs-lookup"><span data-stu-id="cc5cb-214">Timeline</span></span>

- <span data-ttu-id="cc5cb-215">2020年7月1日：您將無法使用**New-MailboxSearch**來建立新的 In-Place eDiscovery 搜尋和 In-Place 保留，但是您仍然可以使用 Cmdlet 來執行、編輯和刪除現有的搜尋，並以您自己的風險進行。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-215">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="cc5cb-216">Microsoft 支援人員將不再為這些類型的搜尋和保留提供協助。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-216">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="cc5cb-217">2020年10月1日：如先前所述，將 EAC 中的 In-Place eDiscovery & 保留功能會置於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-217">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="cc5cb-218">這也表示您將無法使用**New-MailboxSearch**、 **Start-MailboxSearch**或**Set-MailboxSearch** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-218">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="cc5cb-219">您只可以取得及移除現有的搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-219">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="cc5cb-220">替代工具</span><span class="sxs-lookup"><span data-stu-id="cc5cb-220">Alternative tools</span></span>

<span data-ttu-id="cc5cb-221">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-221">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cc5cb-222"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-222"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="cc5cb-223"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-223"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="cc5cb-224"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-224"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cc5cb-225">搜尋和匯出</span><span class="sxs-lookup"><span data-stu-id="cc5cb-225">Search and export</span></span></td>
<td><p><span data-ttu-id="cc5cb-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-228"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-228"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="cc5cb-229">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-229">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="cc5cb-230">您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-230">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="cc5cb-231">然後，您可以使用<strong>New-ComplianceSearchAction</strong> Cmdlet 來匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-231">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="cc5cb-232">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-232">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="cc5cb-233"><strong>附注：</strong>如果您使用這些 Cmdlet 來建立未與核心 eDiscovery 案例相關聯的搜尋，則這些搜尋會位於 Microsoft 365 規範中心的 [<strong>內容搜尋</strong>] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-233"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc5cb-234">保留信箱中的內容</span><span class="sxs-lookup"><span data-stu-id="cc5cb-234">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="cc5cb-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-237"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-237"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="cc5cb-238">Microsoft 365 規範中心的封存必須與 Get-compliancecase 相關聯。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-238">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="cc5cb-239">首先，建立規範案例，然後建立 CaseHoldPolicy 及 New-caseholdrule。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-239">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="cc5cb-240"><strong>附注：</strong>建立沒有建立 New-caseholdrule 的 CaseHoldPolicy，會在建立 New-caseholdrule 並與 CaseHoldPolicy 關聯之前，使保留無法運作。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-240"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="cc5cb-241">如需詳細資訊，請參閱 Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-241">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cc5cb-242">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-242">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="cc5cb-243">無</span><span class="sxs-lookup"><span data-stu-id="cc5cb-243">None</span></span></td>
<td><span data-ttu-id="cc5cb-244">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-244">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="cc5cb-245">請參閱下列常見問題，以取得其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-245">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="cc5cb-246">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-246">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="cc5cb-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="cc5cb-248">若要讓人員能夠存取另一個使用者的電子郵件（例如，當員工離開您的組織，而您需要讓其他人存取先前員工的電子郵件），建議您指派該人員存取先前員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-248">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="cc5cb-249">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-249">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="cc5cb-250">FAQs 關於 \***-get-mailboxsearch 程式**Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cc5cb-250">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="cc5cb-251">**我們使用「複製搜尋」來匯出電子郵件訊息或立即訊息，以供其他 eDiscovery 和法律調查之用。停用這些 Cmdlet 後，還有哪些其他選項？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-251">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="cc5cb-252">[<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph)提供許多方法，可讓您提取資料，以進行分析，以及與使用\*\* \* -get-mailboxsearch 程式\*\*指令程式相比更具彈性性及可擴充性的其他目的。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-252">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="cc5cb-253">**如何將搜尋遷移並保留至 Microsoft 365 規範中心？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-253">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="cc5cb-254">使用 PowerShell 腳本，可以從 Exchange 系統管理中心遷移 In-Place eDiscovery 搜尋和保留。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-254">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="cc5cb-255">如需詳細資訊，請參閱將[舊版 eDiscovery 搜尋和保留遷移至 Microsoft 365 規範中心](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-255">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="cc5cb-256">**在終止 Cmdlet 後，是否仍然可以移除或取回搜尋？**</span><span class="sxs-lookup"><span data-stu-id="cc5cb-256">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="cc5cb-257">是的，雖然我們正在移除建立及修改搜尋的能力，但您仍然可以使用**Get-MailboxSearch**和**Remove-MailboxSearch** ，直到進一步通知。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-257">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="cc5cb-258">不過，在退休日期之後使用這些 Cmdlet 會有您自己的風險，而且 Microsoft 支援將不再能夠提供協助。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-258">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="cc5cb-259">Search-Mailbox Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cc5cb-259">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="cc5cb-260">Exchange Online PowerShell 中的**Search-Mailbox** Cmdlet 會在 [正在撤銷] 中，于最初宣告的指令中的指令，于2018中從後傳回的指令。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-260">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="cc5cb-261">**Search-Mailbox** Cmdlet 最初是用來搜尋使用者的信箱，並清除惡意內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-261">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="cc5cb-262">建議您開始使用 Office 365 安全性 & 規範中心 PowerShell 的**New-ComplianceSearch**和**New-ComplianceSearchAction** Cmdlet，以搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-262">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="cc5cb-263">針對內建的安全性體驗， [<span class="underline">microsoft 365 的安全性功能</span>](https://docs.microsoft.com/microsoft-365/security/)可為電子郵件和許多其他 Microsoft 服務提供強健的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-263">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="cc5cb-264">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="cc5cb-264">Scope of affected organizations</span></span>

- <span data-ttu-id="cc5cb-265">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-265">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="cc5cb-266">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-266">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="cc5cb-267">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="cc5cb-267">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="cc5cb-268">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="cc5cb-268">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="cc5cb-269">時間表</span><span class="sxs-lookup"><span data-stu-id="cc5cb-269">Timeline</span></span>

-  <span data-ttu-id="cc5cb-270">2020年7月1日：將無法再使用**Search-Mailbox** Cmdlet，Microsoft 支援人員將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-270">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="cc5cb-271">替代工具</span><span class="sxs-lookup"><span data-stu-id="cc5cb-271">Alternative tools</span></span>

<span data-ttu-id="cc5cb-272">下表說明您可以用來取代即將淘汰之現有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-272">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cc5cb-273"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-273"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="cc5cb-274"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-274"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="cc5cb-275"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cb-275"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cc5cb-276">搜尋信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-276">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="cc5cb-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-278"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-278"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="cc5cb-279">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-279">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="cc5cb-280">您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-280">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="cc5cb-281">然後，您可以使用<strong>New-ComplianceSearchAction 匯出</strong>命令匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-281">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="cc5cb-282">您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-282">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc5cb-283">從信箱刪除大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="cc5cb-283">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="cc5cb-284"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">設定信箱的封存與刪除原則</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-284"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="cc5cb-285">系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-285">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc5cb-286">將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-286">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="cc5cb-287">這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-287">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="cc5cb-288">如需其他解決方案，請參閱<strong>\*-MailboxSearch Cmdlet</strong>區段中的 FAQs。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-288">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="cc5cb-289">將郵件從一個信箱複製到不同的信箱</span><span class="sxs-lookup"><span data-stu-id="cc5cb-289">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="cc5cb-290"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-290"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="cc5cb-291">若要讓人員能夠存取另一個使用者的電子郵件（例如，當員工離開您的組織，而您需要讓其他人存取先前員工的電子郵件），建議您指派該人員存取先前員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-291">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="cc5cb-292">因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-292">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="cc5cb-293">清除信箱中的郵件</span><span class="sxs-lookup"><span data-stu-id="cc5cb-293">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="cc5cb-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="cc5cb-295"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-295"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="cc5cb-296">New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋及清除內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-296">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="cc5cb-297">您可以使用<strong>New-ComplianceSearch</strong>和<strong>New-ComplianceSearch</strong> Cmdlet 來建立和執行搜尋，然後您可以使用<strong>New-ComplianceSearchAction-Purge PurgeType</strong>命令來清除內容。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-297">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="cc5cb-298">如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜尋並刪除郵件</span></a>。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-298">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="cc5cb-299">清除信箱中的郵件</span><span class="sxs-lookup"><span data-stu-id="cc5cb-299">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="cc5cb-300"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></span><span class="sxs-lookup"><span data-stu-id="cc5cb-300"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="cc5cb-301">若要清除信箱中的郵件，請指派管理員許可權來存取該員工的信箱。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-301">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="cc5cb-302">您可以在必要時刪除郵件並進行回收，以利用 Outlook 中內建的搜尋和觀賞功能。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-302">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="cc5cb-303">Exchange Web 服務 API 作業</span><span class="sxs-lookup"><span data-stu-id="cc5cb-303">Exchange Web Services API operations</span></span>

<span data-ttu-id="cc5cb-304">Exchange 系統管理中心的 In-Place eDiscovery & 保留功能，以及 Exchange Online PowerShell 中的對應\*\* \* get-mailboxsearch 程式\*\*Cmdlet 使用 EXCHANGE Web 服務 API 中的這些作業。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-304">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="cc5cb-305">當您淘汰其他舊版 eDiscovery 工具時，也會將其淘汰。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-305">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="cc5cb-306">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="cc5cb-306">Scope of affected organizations</span></span>

- <span data-ttu-id="cc5cb-307">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-307">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="cc5cb-308">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-308">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="cc5cb-309">Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="cc5cb-309">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="cc5cb-310">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="cc5cb-310">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="cc5cb-311">時間表</span><span class="sxs-lookup"><span data-stu-id="cc5cb-311">Timeline</span></span>

- <span data-ttu-id="cc5cb-312">2020年7月1日：將不再提供 GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 作業，而且 Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-312">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="cc5cb-313">Advanced eDiscovery v 1。0</span><span class="sxs-lookup"><span data-stu-id="cc5cb-313">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="cc5cb-314">Advanced ediscovery 1.0 版，也就是在核心 eDiscovery 案例中，您可以按一下 [**切換至高級 ediscovery**]，將會停用此版本的高級 ediscovery。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-314">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="cc5cb-315">其功能已由 Microsoft 365 規範中心內的新「[高級 eDiscovery」解決方案](https://aka.ms/edisco)所取代。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-315">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="cc5cb-316">若要判斷您的組織是否使用 Advanced eDiscovery 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-316">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="cc5cb-317">移至[Office 365 的安全性 & 規範中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-317">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="cc5cb-318">在安全性 & 規範中心的左功能窗格中，按一下 [ **ediscovery > ediscovery**，然後開啟核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-318">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="cc5cb-319">如果您看到 [**切換至「高級 ediscovery** 」按鈕，請按一下此按鈕將會帶您的1.0 版本的高級 ediscovery （即將淘汰）。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-319">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="cc5cb-320">在核心 eDiscovery 中建立及管理案例的功能將不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-320">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="cc5cb-321">只有在高級 eDiscovery 1.0 （按一下 [**切換成 Advanced eDiscovery**]）中新增及分析案例資料的功能，才會停用。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-321">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="cc5cb-322">Microsoft 365 （也稱為「 *Advanced ediscovery 2.0 2.0*」）中新的 [ediscovery 解決方案] 提供了原始解決方案的所有功能，但現在包含以保管人為基礎的方法，可識別其他 Microsoft 365 服務中的內容、收集該內容，然後將其新增至審閱集，以供檢閱者使用 fast search 查詢、標記和分析功能，協助挑選相關的檔。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-322">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="cc5cb-323">「高級 eDiscovery」現在包括 Microsoft 和非 Microsoft 檔案類型的增強的處理和原生檢視器、[這裡](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)是檔案類型的完整清單，以及支援的元資料欄位在[這裡](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-323">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="cc5cb-324">此外，新的高級 eDiscovery 解決方案提供功能強大的保管人功能，可讓您將保留套用至不同服務中的內容、通知使用者保留，以及追蹤保管人回應，全部都是在高級 eDiscovery 案例內。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-324">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="cc5cb-325">存取高級 eDiscovery 2.0：</span><span class="sxs-lookup"><span data-stu-id="cc5cb-325">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="cc5cb-326">移至[Microsoft 365 規範中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-326">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="cc5cb-327">在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Advanced**]。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-327">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="cc5cb-328">此時，我們建議您開始將 eDiscovery 工作流程轉換為新的高級 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-328">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="cc5cb-329">雖然您仍然可以存取現有案例中的 Advanced eDiscovery 1.0 版，但 Microsoft 支援不會在2020年10月1日之後提供支援。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="cc5cb-330">如需詳細資訊，請參閱下列時程表。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="cc5cb-331">受影響組織的範圍</span><span class="sxs-lookup"><span data-stu-id="cc5cb-331">Scope of affected organizations</span></span>

- <span data-ttu-id="cc5cb-332">Office 365 和 Microsoft 365 企業組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="cc5cb-333">Office 365 和 Microsoft 365 教育組織</span><span class="sxs-lookup"><span data-stu-id="cc5cb-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="cc5cb-334">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="cc5cb-334">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="cc5cb-335">時間表</span><span class="sxs-lookup"><span data-stu-id="cc5cb-335">Timeline</span></span>

- <span data-ttu-id="cc5cb-336">2020年7月1日：您將無法建立新的高級 eDiscovery 1.0 案例。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-336">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="cc5cb-337">2020年10月1日：您將無法在任何情況下新增資料（為高級 eDiscovery 準備搜尋結果）。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-337">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="cc5cb-338">您將能夠繼續使用現有案例中的資料，必須自行承擔。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-338">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="cc5cb-339">Microsoft 支援將不再提供協助。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-339">Microsoft Support will no longer provide assistance.</span></span> 

### <a name="alternative-tools"></a><span data-ttu-id="cc5cb-340">替代工具</span><span class="sxs-lookup"><span data-stu-id="cc5cb-340">Alternative tools</span></span>

<span data-ttu-id="cc5cb-341">Microsoft 365 規範中心的[高級 eDiscovery 解決方案](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="cc5cb-341">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
