---
title: 預覽電子文件探索搜尋的結果
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
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 預覽由 Microsoft 365 合規性中心中內容搜尋或核心電子文件探索搜尋所傳回的結果範例。
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538581"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="80a0f-103">預覽電子文件探索搜尋結果</span><span class="sxs-lookup"><span data-stu-id="80a0f-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="80a0f-104">執行內容搜尋或與核心電子文件探索案例相關的搜尋之後，您可以預覽搜尋所傳回結果的範例。</span><span class="sxs-lookup"><span data-stu-id="80a0f-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="80a0f-105">預覽搜尋查詢所傳回的項目可協助判斷搜尋是否正傳回您期待的結果，或是否需要變更搜尋查詢並重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="80a0f-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="80a0f-106">若要預覽搜尋所傳回的結果範例:</span><span class="sxs-lookup"><span data-stu-id="80a0f-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="80a0f-107">在 Microsoft 365 合規性中心，前往內容搜尋頁面或核心電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="80a0f-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="80a0f-108">選取搜尋以顯示飛出視窗頁面。</span><span class="sxs-lookup"><span data-stu-id="80a0f-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="80a0f-109">在飛出視窗頁面底部，按一下 [檢閱範例 **]**。</span><span class="sxs-lookup"><span data-stu-id="80a0f-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![按一下飛出視窗頁面上的 [檢閱範例] 以預覽結果](../media/PreviewSearchResults1.png)

   <span data-ttu-id="80a0f-111">包含搜尋結果範例的頁面會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="80a0f-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="80a0f-112">選取項目以在讀取窗格中檢視其內容。</span><span class="sxs-lookup"><span data-stu-id="80a0f-112">Select an item to view its contents in the reading pane.</span></span>

   ![在讀取窗格中預覽項目](../media/PreviewSearchResults2.png)

   <span data-ttu-id="80a0f-114">在上一個螢幕擷取畫面中，請注意，當您預覽項目時，來自搜尋查詢的關鍵字會強調顯示。</span><span class="sxs-lookup"><span data-stu-id="80a0f-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="80a0f-115">如何選取搜尋結果範例</span><span class="sxs-lookup"><span data-stu-id="80a0f-115">How the search result samples are selected</span></span>

<span data-ttu-id="80a0f-116">最多可預覽 1,000 個隨機選取的項目。</span><span class="sxs-lookup"><span data-stu-id="80a0f-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="80a0f-117">除了隨機選取之外，可供預覽的項目也必須符合下列準則：</span><span class="sxs-lookup"><span data-stu-id="80a0f-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="80a0f-118">最多可預覽來自單一內容位置 (信箱或網站) 的 100 個項目。</span><span class="sxs-lookup"><span data-stu-id="80a0f-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="80a0f-119">這表示可供預覽的項目可能少於 1,000 個。</span><span class="sxs-lookup"><span data-stu-id="80a0f-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="80a0f-120">例如，如果您搜尋四個信箱，而搜尋傳回 1,500 個估計項目，則只有 400 個可供預覽，因為每個信箱只能預覽 100 個項目。</span><span class="sxs-lookup"><span data-stu-id="80a0f-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="80a0f-121">針對信箱項目，只有電子郵件訊息可供預覽。</span><span class="sxs-lookup"><span data-stu-id="80a0f-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="80a0f-122">無法預覽工作、行事曆項目和連絡人等項目。</span><span class="sxs-lookup"><span data-stu-id="80a0f-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="80a0f-123">針對網站項目，只有文偉可供預覽。</span><span class="sxs-lookup"><span data-stu-id="80a0f-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="80a0f-124">無法預覽資料夾、清單或清單附件等項目。</span><span class="sxs-lookup"><span data-stu-id="80a0f-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="80a0f-125">預覽搜尋結果時支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="80a0f-125">File types supported when previewing search results</span></span>

<span data-ttu-id="80a0f-126">您可以在預覽窗格中預覽支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="80a0f-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="80a0f-127">如果是系統不支援的檔案類型，您必須下載檔案的副本到您的本機電腦 (按一下 [下載原始項目 **]**)。</span><span class="sxs-lookup"><span data-stu-id="80a0f-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="80a0f-128">.aspx 網頁會包含網頁的 URL，不過您可能並沒有存取該網頁的權限。</span><span class="sxs-lookup"><span data-stu-id="80a0f-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="80a0f-129">未編製索引的項目無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="80a0f-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="80a0f-130">支援下列檔案類型，並且可在搜尋結果窗格中預覽。</span><span class="sxs-lookup"><span data-stu-id="80a0f-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="80a0f-131">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="80a0f-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="80a0f-132">.eml</span><span class="sxs-lookup"><span data-stu-id="80a0f-132">.eml</span></span>

- <span data-ttu-id="80a0f-133">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="80a0f-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="80a0f-134">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="80a0f-134">.pptm, .pptx</span></span>

- <span data-ttu-id="80a0f-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="80a0f-135">.pdf</span></span>

<span data-ttu-id="80a0f-136">還支援下列檔案容器類型。</span><span class="sxs-lookup"><span data-stu-id="80a0f-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="80a0f-137">您可以在預覽窗格的容器中檢視檔案的清單。</span><span class="sxs-lookup"><span data-stu-id="80a0f-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="80a0f-138">.zip</span><span class="sxs-lookup"><span data-stu-id="80a0f-138">.zip</span></span>

- <span data-ttu-id="80a0f-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="80a0f-139">.gzip</span></span>