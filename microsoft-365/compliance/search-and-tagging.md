---
title: 搜尋及標記
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 在 [Advanced eDiscovery] 中，[搜尋] 和 [標記] 模組可讓您在案例中搜尋、預覽及組織檔。 此模組目前已在 Beta 中。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eba95f4832e674bae0a26d3fa8466b0118a9715d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818892"
---
# <a name="search-and-tagging"></a><span data-ttu-id="13682-104">搜尋及標記</span><span class="sxs-lookup"><span data-stu-id="13682-104">Search and Tagging</span></span>

<span data-ttu-id="13682-105">在 [Advanced eDiscovery] 中，[搜尋] 和 [標記] 模組可讓您在案例中搜尋、預覽及組織檔。</span><span class="sxs-lookup"><span data-stu-id="13682-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="13682-106">此模組目前已在 Beta 中。</span><span class="sxs-lookup"><span data-stu-id="13682-106">Currently, this module is in beta.</span></span> <span data-ttu-id="13682-107">如需搜尋及標記的簡短示範，請參閱[使用高級 eDiscovery 影片管理您的資料](https://www.youtube.com/watch?v=VaPYL3DHP6I)。</span><span class="sxs-lookup"><span data-stu-id="13682-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="13682-108">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="13682-108">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="13682-109">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="13682-109">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="13682-110">搜尋您案例中的檔</span><span class="sxs-lookup"><span data-stu-id="13682-110">Search the documents in your case</span></span>

<span data-ttu-id="13682-111">在高級 eDiscovery 案例中處理檔（並選擇性地執行 [分析] 或 [相關性] 模組）之後，您可以使用搜尋及加上標記來搜尋檔，然後套用案例特有的標記（也稱為標籤）加以組織。</span><span class="sxs-lookup"><span data-stu-id="13682-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="13682-112">您可以使用所提供的條件卡，或是使用關鍵字條件卡中的類似 KQL 的查詢語言來定義搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="13682-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="13682-113">常見的 KQL 語法，例如 AND、OR、NOT 和 NEAR （n）都支援，以及尾隨多字元萬用字元（\*）。</span><span class="sxs-lookup"><span data-stu-id="13682-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="13682-114">下表列出您可以使用 KQL 關鍵字查詢進行搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="13682-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="13682-115">或者，您也可以在高級 eDiscovery 搜尋工具中使用條件卡，將條件（選取的屬性）新增至搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="13682-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="13682-116">**屬性**</span><span class="sxs-lookup"><span data-stu-id="13682-116">**Property**</span></span>|<span data-ttu-id="13682-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="13682-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13682-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="13682-118">**caselabel**</span></span> <br/> | <span data-ttu-id="13682-119">標記檔時所建立/套用的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="13682-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="13682-120">**託管**</span><span class="sxs-lookup"><span data-stu-id="13682-120">**custodian**</span></span> <br/> | <span data-ttu-id="13682-121">與檔相關聯的保管人;受到限制。</span><span class="sxs-lookup"><span data-stu-id="13682-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="13682-122">**date**</span><span class="sxs-lookup"><span data-stu-id="13682-122">**date**</span></span> <br/> | <span data-ttu-id="13682-123">電子郵件的傳送日期;網站檔的修改日期。</span><span class="sxs-lookup"><span data-stu-id="13682-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="13682-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="13682-124">**fileid**</span></span> <br/> | <span data-ttu-id="13682-125">案例中的檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="13682-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="13682-126">**類型**</span><span class="sxs-lookup"><span data-stu-id="13682-126">**filetype**</span></span> <br/> | <span data-ttu-id="13682-127">本機副檔名。</span><span class="sxs-lookup"><span data-stu-id="13682-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="13682-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="13682-128">**fileclass**</span></span> <br/> | <span data-ttu-id="13682-129">電子郵件、檔或附件。</span><span class="sxs-lookup"><span data-stu-id="13682-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="13682-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="13682-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="13682-131">電子郵件的寄件者;網站檔的作者。</span><span class="sxs-lookup"><span data-stu-id="13682-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="13682-132">**size**</span><span class="sxs-lookup"><span data-stu-id="13682-132">**size**</span></span> <br/> | <span data-ttu-id="13682-133">檔案的大小（以 KB 為單位）。</span><span class="sxs-lookup"><span data-stu-id="13682-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="13682-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="13682-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="13682-135">電子郵件的主旨;網站檔的標題。</span><span class="sxs-lookup"><span data-stu-id="13682-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="13682-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="13682-136">**bcc**</span></span> <br/> | <span data-ttu-id="13682-137">電子郵件的 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="13682-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="13682-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="13682-138">**cc**</span></span> <br/> | <span data-ttu-id="13682-139">電子郵件的 [副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="13682-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="13682-140">**參與者**</span><span class="sxs-lookup"><span data-stu-id="13682-140">**participants**</span></span> <br/> | <span data-ttu-id="13682-141">電子郵件線索中所有參與者的電子郵件地址，包含缺失的連結。</span><span class="sxs-lookup"><span data-stu-id="13682-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="13682-142">**收到**</span><span class="sxs-lookup"><span data-stu-id="13682-142">**received**</span></span> <br/> | <span data-ttu-id="13682-143">接收電子郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="13682-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="13682-144">**收件者**</span><span class="sxs-lookup"><span data-stu-id="13682-144">**recipients**</span></span> <br/> | <span data-ttu-id="13682-145">電子郵件的收件者，包含在 [收件者]、[抄送] 或 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="13682-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="13682-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="13682-146">**sender**</span></span> <br/> | <span data-ttu-id="13682-147">電子郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="13682-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="13682-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="13682-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="13682-149">網站檔的上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="13682-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="13682-150">**送**</span><span class="sxs-lookup"><span data-stu-id="13682-150">**sent**</span></span> <br/> | <span data-ttu-id="13682-151">電子郵件的傳送日期。</span><span class="sxs-lookup"><span data-stu-id="13682-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="13682-152">**to**</span><span class="sxs-lookup"><span data-stu-id="13682-152">**to**</span></span> <br/> | <span data-ttu-id="13682-153">電子郵件的 [收件者] 欄位中所列的收件者。</span><span class="sxs-lookup"><span data-stu-id="13682-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="13682-154">**作者**</span><span class="sxs-lookup"><span data-stu-id="13682-154">**author**</span></span> <br/> | <span data-ttu-id="13682-155">網站檔的作者。</span><span class="sxs-lookup"><span data-stu-id="13682-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="13682-156">**title**</span><span class="sxs-lookup"><span data-stu-id="13682-156">**title**</span></span> <br/> | <span data-ttu-id="13682-157">網站檔的標題。</span><span class="sxs-lookup"><span data-stu-id="13682-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="13682-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="13682-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="13682-159">專案的主要主題。</span><span class="sxs-lookup"><span data-stu-id="13682-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="13682-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="13682-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="13682-161">與專案相關聯的主題。</span><span class="sxs-lookup"><span data-stu-id="13682-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="13682-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="13682-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="13682-163">針對 [issuenum] 所定義之問題的專案讀取百分比。</span><span class="sxs-lookup"><span data-stu-id="13682-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="13682-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="13682-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="13682-165">專案的相關性分數，針對 [issuenum] 所定義的問題。</span><span class="sxs-lookup"><span data-stu-id="13682-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="13682-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="13682-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="13682-167">如果已手動標示相關專案的相關專案，則 [標記] 所定義的標籤。</span><span class="sxs-lookup"><span data-stu-id="13682-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="13682-168">\*只有在已執行 Themes 模組時才可用。</span><span class="sxs-lookup"><span data-stu-id="13682-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="13682-169">\*\*只有在已執行相關性模組時才可用。</span><span class="sxs-lookup"><span data-stu-id="13682-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="13682-170">或者，您可以使用高級 eDiscovery 搜尋工具中的條件卡，將條件（選取的屬性）新增至搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="13682-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="13682-171">下列螢幕擷取畫面顯示可以新增至查詢的條件。</span><span class="sxs-lookup"><span data-stu-id="13682-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="13682-172">**Group**欄會指出屬性是套用至電子郵件、網站檔或兩者（以*共同*的值來表示）。</span><span class="sxs-lookup"><span data-stu-id="13682-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="13682-173">此欄位也會識別在您執行相關性模組後，可用的可搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="13682-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高級 eDiscovery 搜尋工具中的搜尋條件](../media/AeDSearchConditions.png)

<span data-ttu-id="13682-175">如需可搜尋屬性的詳細資訊，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="13682-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="13682-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="13682-176">Related topics</span></span>

[<span data-ttu-id="13682-177">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="13682-177">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-178">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="13682-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-179">標記與評估</span><span class="sxs-lookup"><span data-stu-id="13682-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-180">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="13682-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-181">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="13682-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-182">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="13682-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="13682-183">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="13682-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

