---
title: 搜尋與標記
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
description: 進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，及組織您的案例中的文件。 目前，此模組處於 beta 版。
ms.openlocfilehash: 012154e117e0d2b800f0e1077d43f2e1c1d10b0e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557803"
---
# <a name="search-and-tagging"></a><span data-ttu-id="78970-104">搜尋與標記</span><span class="sxs-lookup"><span data-stu-id="78970-104">Search and Tagging</span></span>

<span data-ttu-id="78970-105">進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，及組織您的案例中的文件。</span><span class="sxs-lookup"><span data-stu-id="78970-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="78970-106">目前，此模組處於 beta 版。</span><span class="sxs-lookup"><span data-stu-id="78970-106">Currently, this module is in beta.</span></span> <span data-ttu-id="78970-107">搜尋及標記的簡短示範，請參閱[管理您的資料與進階電子文件](https://www.youtube.com/watch?v=VaPYL3DHP6I)影片。</span><span class="sxs-lookup"><span data-stu-id="78970-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="78970-p103">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="78970-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="78970-110">搜尋您的案例中的文件</span><span class="sxs-lookup"><span data-stu-id="78970-110">Search the documents in your case</span></span>

<span data-ttu-id="78970-111">在處理進階電子文件探索案例中的文件 （並選擇性地執行分析或相關性模組後），您可以使用標記與搜尋來搜尋文件並再將它們組織藉由套用特定案例的標記 （也稱為標籤）。</span><span class="sxs-lookup"><span data-stu-id="78970-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="78970-112">您可以定義搜尋查詢中使用提供的條件卡或利用 KQL 類似的查詢語言中的關鍵字條件卡片。</span><span class="sxs-lookup"><span data-stu-id="78970-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="78970-113">常見的 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （\*）。</span><span class="sxs-lookup"><span data-stu-id="78970-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="78970-114">下表列出您可以搜尋使用 KQL 關鍵字查詢的屬性。</span><span class="sxs-lookup"><span data-stu-id="78970-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="78970-115">或者，您可以使用進階 eDiscovery 搜尋工具中的條件卡片，若要新增至搜尋查詢的條件 （選取的內容）。</span><span class="sxs-lookup"><span data-stu-id="78970-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="78970-116">**屬性**</span><span class="sxs-lookup"><span data-stu-id="78970-116">**Property**</span></span>|<span data-ttu-id="78970-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="78970-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78970-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="78970-118">**caselabel**</span></span> <br/> | <span data-ttu-id="78970-119">標記的名稱建立/時套用標記的文件。</span><span class="sxs-lookup"><span data-stu-id="78970-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="78970-120">**custodian**</span><span class="sxs-lookup"><span data-stu-id="78970-120">**custodian**</span></span> <br/> | <span data-ttu-id="78970-121">相關聯的文件; custodian受到限制。</span><span class="sxs-lookup"><span data-stu-id="78970-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="78970-122">**date**</span><span class="sxs-lookup"><span data-stu-id="78970-122">**date**</span></span> <br/> | <span data-ttu-id="78970-123">傳送電子郵件; 日期網站文件的修改的日期。</span><span class="sxs-lookup"><span data-stu-id="78970-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="78970-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="78970-124">**fileid**</span></span> <br/> | <span data-ttu-id="78970-125">在 case 檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="78970-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="78970-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="78970-126">**filetype**</span></span> <br/> | <span data-ttu-id="78970-127">原生檔案的副檔名。</span><span class="sxs-lookup"><span data-stu-id="78970-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="78970-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="78970-128">**fileclass**</span></span> <br/> | <span data-ttu-id="78970-129">電子郵件、 文件或附件。</span><span class="sxs-lookup"><span data-stu-id="78970-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="78970-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="78970-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="78970-131">寄件者的電子郵件;網站文件的作者。</span><span class="sxs-lookup"><span data-stu-id="78970-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="78970-132">**size**</span><span class="sxs-lookup"><span data-stu-id="78970-132">**size**</span></span> <br/> | <span data-ttu-id="78970-133">Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="78970-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="78970-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="78970-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="78970-135">電子郵件; 主旨網站文件的標題。</span><span class="sxs-lookup"><span data-stu-id="78970-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="78970-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="78970-136">**bcc**</span></span> <br/> | <span data-ttu-id="78970-137">電子郵件的密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="78970-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="78970-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="78970-138">**cc**</span></span> <br/> | <span data-ttu-id="78970-139">電子郵件 [副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="78970-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="78970-140">**參與者**</span><span class="sxs-lookup"><span data-stu-id="78970-140">**participants**</span></span> <br/> | <span data-ttu-id="78970-141">電子郵件執行緒，包括缺少連結中的所有參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="78970-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="78970-142">**接收**</span><span class="sxs-lookup"><span data-stu-id="78970-142">**received**</span></span> <br/> | <span data-ttu-id="78970-143">已收到一封電子郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="78970-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="78970-144">**收件者**</span><span class="sxs-lookup"><span data-stu-id="78970-144">**recipients**</span></span> <br/> | <span data-ttu-id="78970-145">收件者的電子郵件，包含在收件者]、 [副本] 或 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="78970-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="78970-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="78970-146">**sender**</span></span> <br/> | <span data-ttu-id="78970-147">電子郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="78970-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="78970-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="78970-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="78970-149">上次修改日期的網站文件。</span><span class="sxs-lookup"><span data-stu-id="78970-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="78970-150">**傳送**</span><span class="sxs-lookup"><span data-stu-id="78970-150">**sent**</span></span> <br/> | <span data-ttu-id="78970-151">電子郵件傳送的日期。</span><span class="sxs-lookup"><span data-stu-id="78970-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="78970-152">**to**</span><span class="sxs-lookup"><span data-stu-id="78970-152">**to**</span></span> <br/> | <span data-ttu-id="78970-153">電子郵件] 欄位中所列的收件者。</span><span class="sxs-lookup"><span data-stu-id="78970-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="78970-154">**作者**</span><span class="sxs-lookup"><span data-stu-id="78970-154">**author**</span></span> <br/> | <span data-ttu-id="78970-155">網站文件的作者。</span><span class="sxs-lookup"><span data-stu-id="78970-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="78970-156">**title**</span><span class="sxs-lookup"><span data-stu-id="78970-156">**title**</span></span> <br/> | <span data-ttu-id="78970-157">網站文件的標題。</span><span class="sxs-lookup"><span data-stu-id="78970-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="78970-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="78970-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="78970-159">項目與基準佈景主題。</span><span class="sxs-lookup"><span data-stu-id="78970-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="78970-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="78970-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="78970-161">項目相關聯的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="78970-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="78970-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="78970-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="78970-163">讀取百分位數的項目，如 [issuenum] 所定義的問題。</span><span class="sxs-lookup"><span data-stu-id="78970-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="78970-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="78970-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="78970-165">項目，由 [issuenum] 定義問題相關性分數。</span><span class="sxs-lookup"><span data-stu-id="78970-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="78970-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="78970-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="78970-167">如果項目有已手動標示相關性，[tagname] 所定義的標籤。</span><span class="sxs-lookup"><span data-stu-id="78970-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="78970-168">\*如果已經執行 [佈景主題模組才可用。</span><span class="sxs-lookup"><span data-stu-id="78970-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="78970-169">\*\*如果已經執行 [相關性模組才可用。</span><span class="sxs-lookup"><span data-stu-id="78970-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="78970-170">或者，您可以使用進階 eDiscovery 搜尋工具中的條件卡片，新增至搜尋查詢的條件 （選取的內容）。</span><span class="sxs-lookup"><span data-stu-id="78970-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="78970-171">下列螢幕擷取畫面顯示可以新增至查詢的條件。</span><span class="sxs-lookup"><span data-stu-id="78970-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="78970-172">[**群組**] 欄會指出屬性是否適用於電子郵件、 網站文件，或兩者 （由*常見*的值來表示）。</span><span class="sxs-lookup"><span data-stu-id="78970-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="78970-173">此資料行也會識別之後執行相關性模組都是可用的可搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="78970-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![在 [進階電子文件探索搜尋工具中的搜尋條件](../media/AeDSearchConditions.png)

<span data-ttu-id="78970-175">如需可搜尋屬性的詳細資訊，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="78970-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78970-176">請參閱</span><span class="sxs-lookup"><span data-stu-id="78970-176">See also</span></span>

[<span data-ttu-id="78970-177">進階電子文件 （傳統）</span><span class="sxs-lookup"><span data-stu-id="78970-177">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-178">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="78970-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-179">標記與評估</span><span class="sxs-lookup"><span data-stu-id="78970-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-180">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="78970-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-181">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="78970-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-182">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="78970-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="78970-183">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="78970-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

