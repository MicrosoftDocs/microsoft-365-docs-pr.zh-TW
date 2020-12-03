---
title: 搜尋及標記
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: 7afa106d07e60dfc297b90c25965dafeeb7337a7
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562930"
---
# <a name="search-and-tagging"></a><span data-ttu-id="b805a-104">搜尋及標記</span><span class="sxs-lookup"><span data-stu-id="b805a-104">Search and Tagging</span></span>

<span data-ttu-id="b805a-105">在 [Advanced eDiscovery] 中，[搜尋] 和 [標記] 模組可讓您在案例中搜尋、預覽及組織檔。</span><span class="sxs-lookup"><span data-stu-id="b805a-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="b805a-106">此模組目前已在 Beta 中。</span><span class="sxs-lookup"><span data-stu-id="b805a-106">Currently, this module is in beta.</span></span> <span data-ttu-id="b805a-107">如需搜尋及標記的簡短示範，請參閱 [使用高級 eDiscovery 影片管理您的資料](https://www.youtube.com/watch?v=VaPYL3DHP6I) 。</span><span class="sxs-lookup"><span data-stu-id="b805a-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="b805a-p103">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b805a-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="b805a-110">搜尋您案例中的檔</span><span class="sxs-lookup"><span data-stu-id="b805a-110">Search the documents in your case</span></span>

<span data-ttu-id="b805a-111">在高級 eDiscovery 案例中處理檔之後 (並選擇性地執行 [分析] 或 [相關性] 模組) ，您可以使用搜尋及加上標籤來進行搜尋，然後再套用案例特定標記 (也稱為標籤) 。</span><span class="sxs-lookup"><span data-stu-id="b805a-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="b805a-112">您可以使用所提供的條件卡，或是使用關鍵字條件卡中的類似 KQL 的查詢語言來定義搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="b805a-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="b805a-113">常見的 KQL 語法，例如 AND、OR、 (NOT) ，以及尾隨多字元萬用字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="b805a-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="b805a-114">下表列出您可以使用 KQL 關鍵字查詢進行搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="b805a-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="b805a-115">或者，您也可以在 [高級 eDiscovery 搜尋工具] 中使用條件卡，將選取的屬性) 的條件 (新增至搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="b805a-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="b805a-116">**屬性**</span><span class="sxs-lookup"><span data-stu-id="b805a-116">**Property**</span></span>|<span data-ttu-id="b805a-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="b805a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b805a-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="b805a-118">**caselabel**</span></span> <br/> | <span data-ttu-id="b805a-119">標記檔時所建立/套用的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="b805a-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="b805a-120">**託管**</span><span class="sxs-lookup"><span data-stu-id="b805a-120">**custodian**</span></span> <br/> | <span data-ttu-id="b805a-121">與檔相關聯的保管人;受到限制。</span><span class="sxs-lookup"><span data-stu-id="b805a-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="b805a-122">**date**</span><span class="sxs-lookup"><span data-stu-id="b805a-122">**date**</span></span> <br/> | <span data-ttu-id="b805a-123">電子郵件的傳送日期;網站檔的修改日期。</span><span class="sxs-lookup"><span data-stu-id="b805a-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="b805a-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="b805a-124">**fileid**</span></span> <br/> | <span data-ttu-id="b805a-125">案例中的檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="b805a-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="b805a-126">**類型**</span><span class="sxs-lookup"><span data-stu-id="b805a-126">**filetype**</span></span> <br/> | <span data-ttu-id="b805a-127">本機副檔名。</span><span class="sxs-lookup"><span data-stu-id="b805a-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="b805a-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="b805a-128">**fileclass**</span></span> <br/> | <span data-ttu-id="b805a-129">電子郵件、檔或附件。</span><span class="sxs-lookup"><span data-stu-id="b805a-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="b805a-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="b805a-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="b805a-131">電子郵件的寄件者;網站檔的作者。</span><span class="sxs-lookup"><span data-stu-id="b805a-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="b805a-132">**size**</span><span class="sxs-lookup"><span data-stu-id="b805a-132">**size**</span></span> <br/> | <span data-ttu-id="b805a-133">檔案的大小（以 KB 為單位）。</span><span class="sxs-lookup"><span data-stu-id="b805a-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="b805a-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="b805a-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="b805a-135">電子郵件的主旨;網站檔的標題。</span><span class="sxs-lookup"><span data-stu-id="b805a-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="b805a-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="b805a-136">**bcc**</span></span> <br/> | <span data-ttu-id="b805a-137">電子郵件的 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="b805a-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="b805a-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="b805a-138">**cc**</span></span> <br/> | <span data-ttu-id="b805a-139">電子郵件的 [副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="b805a-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="b805a-140">**參與者**</span><span class="sxs-lookup"><span data-stu-id="b805a-140">**participants**</span></span> <br/> | <span data-ttu-id="b805a-141">電子郵件線索中所有參與者的電子郵件地址，包含缺失的連結。</span><span class="sxs-lookup"><span data-stu-id="b805a-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="b805a-142">**收到**</span><span class="sxs-lookup"><span data-stu-id="b805a-142">**received**</span></span> <br/> | <span data-ttu-id="b805a-143">接收電子郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="b805a-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="b805a-144">**收件者**</span><span class="sxs-lookup"><span data-stu-id="b805a-144">**recipients**</span></span> <br/> | <span data-ttu-id="b805a-145">電子郵件的收件者，包含在 [收件者]、[抄送] 或 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="b805a-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="b805a-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="b805a-146">**sender**</span></span> <br/> | <span data-ttu-id="b805a-147">電子郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b805a-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="b805a-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="b805a-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="b805a-149">網站檔的上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="b805a-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="b805a-150">**送**</span><span class="sxs-lookup"><span data-stu-id="b805a-150">**sent**</span></span> <br/> | <span data-ttu-id="b805a-151">電子郵件的傳送日期。</span><span class="sxs-lookup"><span data-stu-id="b805a-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="b805a-152">**to**</span><span class="sxs-lookup"><span data-stu-id="b805a-152">**to**</span></span> <br/> | <span data-ttu-id="b805a-153">電子郵件的 [收件者] 欄位中所列的收件者。</span><span class="sxs-lookup"><span data-stu-id="b805a-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="b805a-154">**作者**</span><span class="sxs-lookup"><span data-stu-id="b805a-154">**author**</span></span> <br/> | <span data-ttu-id="b805a-155">網站檔的作者。</span><span class="sxs-lookup"><span data-stu-id="b805a-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="b805a-156">**title**</span><span class="sxs-lookup"><span data-stu-id="b805a-156">**title**</span></span> <br/> | <span data-ttu-id="b805a-157">網站檔的標題。</span><span class="sxs-lookup"><span data-stu-id="b805a-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="b805a-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="b805a-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="b805a-159">專案的主要主題。</span><span class="sxs-lookup"><span data-stu-id="b805a-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="b805a-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="b805a-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="b805a-161">與專案相關聯的主題。</span><span class="sxs-lookup"><span data-stu-id="b805a-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="b805a-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="b805a-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="b805a-163">針對 [issuenum] 所定義之問題的專案讀取百分比。</span><span class="sxs-lookup"><span data-stu-id="b805a-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="b805a-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="b805a-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="b805a-165">專案的相關性分數，針對 [issuenum] 所定義的問題。</span><span class="sxs-lookup"><span data-stu-id="b805a-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="b805a-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="b805a-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="b805a-167">如果已手動標示相關專案的相關專案，則 [標記] 所定義的標籤。</span><span class="sxs-lookup"><span data-stu-id="b805a-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="b805a-168">\* 只有在已執行 Themes 模組時才可用。</span><span class="sxs-lookup"><span data-stu-id="b805a-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="b805a-169">\*\* 只有在已執行相關性模組時才可用。</span><span class="sxs-lookup"><span data-stu-id="b805a-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="b805a-170">或者，您也可以使用 [高級 eDiscovery 搜尋工具] 中的條件卡，針對) 搜尋查詢的選取屬性新增條件 (。</span><span class="sxs-lookup"><span data-stu-id="b805a-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="b805a-171">下列螢幕擷取畫面顯示可以新增至查詢的條件。</span><span class="sxs-lookup"><span data-stu-id="b805a-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="b805a-172">**Group** 欄會指出屬性是套用至電子郵件、網站檔，還是這兩 (由值 *共同*) 所表示。</span><span class="sxs-lookup"><span data-stu-id="b805a-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="b805a-173">此欄位也會識別在您執行相關性模組後，可用的可搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="b805a-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高級 eDiscovery 搜尋工具中的搜尋條件](../media/AeDSearchConditions.png)

<span data-ttu-id="b805a-175">如需可搜尋屬性的詳細資訊，請參閱 [關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="b805a-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b805a-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="b805a-176">Related topics</span></span>

[<span data-ttu-id="b805a-177">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="b805a-177">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-178">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="b805a-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-179">標記與評估</span><span class="sxs-lookup"><span data-stu-id="b805a-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-180">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="b805a-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-181">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="b805a-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-182">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="b805a-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b805a-183">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="b805a-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

