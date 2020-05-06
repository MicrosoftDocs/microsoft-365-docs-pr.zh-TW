---
title: 標記檢閱集中的文件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在審閱集中標記檔可協助移除不必要的內容，並在高級 eDiscovery 案例中識別相關的內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 445bf9a0ee5959c4972920a74e7bd1596d9edca1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034547"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="4b98e-103">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="4b98e-103">Tag documents in a review set</span></span>

<span data-ttu-id="4b98e-104">在「檢查」集中組織內容對於在 eDiscovery 程式中完成各種工作流程很重要。</span><span class="sxs-lookup"><span data-stu-id="4b98e-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="4b98e-105">這包括：</span><span class="sxs-lookup"><span data-stu-id="4b98e-105">This includes:</span></span>

- <span data-ttu-id="4b98e-106">挑選不必要的內容</span><span class="sxs-lookup"><span data-stu-id="4b98e-106">Culling unnecessary content</span></span>

- <span data-ttu-id="4b98e-107">識別相關的內容</span><span class="sxs-lookup"><span data-stu-id="4b98e-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="4b98e-108">識別必須由專家或律師審閱的內容</span><span class="sxs-lookup"><span data-stu-id="4b98e-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="4b98e-109">當專家、律師或其他使用者查看審閱集中的內容時，可以使用標記來捕獲其與內容相關的觀點。</span><span class="sxs-lookup"><span data-stu-id="4b98e-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="4b98e-110">例如，若要挑選不必要的內容，使用者可以使用標記（如「沒有回應」）來標記檔。</span><span class="sxs-lookup"><span data-stu-id="4b98e-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="4b98e-111">在審閱及標記內容之後，您可以建立審閱集搜尋，以排除標記為「無回應」的任何內容，這會在 eDiscovery 工作流程的後續步驟中消除此內容。</span><span class="sxs-lookup"><span data-stu-id="4b98e-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="4b98e-112">您可以針對每個案例自訂標記面板，使標記能夠支援預定的審閱工作流程。</span><span class="sxs-lookup"><span data-stu-id="4b98e-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="4b98e-113">標記類型</span><span class="sxs-lookup"><span data-stu-id="4b98e-113">Tag types</span></span>

<span data-ttu-id="4b98e-114">「高級 eDiscovery」提供兩種類型的標記：</span><span class="sxs-lookup"><span data-stu-id="4b98e-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="4b98e-115">**單一選擇標記**-限制使用者選取群組內的單一標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="4b98e-116">這可確保使用者不會選取「已回應」和「無回應」等衝突標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="4b98e-117">這些會顯示為選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b98e-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="4b98e-118">**多重選取標記**-允許使用者選取群組中的多個標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="4b98e-119">這些會顯示為核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4b98e-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="4b98e-120">標記結構</span><span class="sxs-lookup"><span data-stu-id="4b98e-120">Tag structure</span></span>

<span data-ttu-id="4b98e-121">除了標記類型之外，標記在標記面板中的組織方式也可以用來讓標記檔更直觀。</span><span class="sxs-lookup"><span data-stu-id="4b98e-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="4b98e-122">標記是依區段群組。</span><span class="sxs-lookup"><span data-stu-id="4b98e-122">Tags are grouped by sections.</span></span> <span data-ttu-id="4b98e-123">「複查設定搜尋」支援依標籤及依標籤進行搜尋的功能] 區段。</span><span class="sxs-lookup"><span data-stu-id="4b98e-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="4b98e-124">這表示您可以建立「複查集搜尋」，以檢索標記為區段中任何標記的檔。</span><span class="sxs-lookup"><span data-stu-id="4b98e-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![標記面板中的標記區段](../media/Tagtypes.png)

<span data-ttu-id="4b98e-126">您可以透過將標記嵌入區段中進一步組織標籤。</span><span class="sxs-lookup"><span data-stu-id="4b98e-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="4b98e-127">例如，如果要識別及標記特權內容，可以使用嵌套來明確指出使用者可以將檔標記為「特權」，並檢查適當的嵌套標記，以選取特權類型。</span><span class="sxs-lookup"><span data-stu-id="4b98e-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![標記區段中的嵌套標記](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="4b98e-129">套用標記</span><span class="sxs-lookup"><span data-stu-id="4b98e-129">Applying tags</span></span>

<span data-ttu-id="4b98e-130">有幾種方式可以將標記套用至內容。</span><span class="sxs-lookup"><span data-stu-id="4b98e-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="4b98e-131">標記單一檔</span><span class="sxs-lookup"><span data-stu-id="4b98e-131">Tagging a single document</span></span>

<span data-ttu-id="4b98e-132">在審閱集中查看檔時，您可以按一下 [**標記] 面板**來顯示可供審閱使用的標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![按一下 [標記面板] 以顯示標記面板](../media/Singledoctag.png)

<span data-ttu-id="4b98e-134">這可讓您將標記套用至顯示在檢視器中的檔。</span><span class="sxs-lookup"><span data-stu-id="4b98e-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="4b98e-135">大量標記</span><span class="sxs-lookup"><span data-stu-id="4b98e-135">Bulk tagging</span></span>

<span data-ttu-id="4b98e-136">您可以在結果格線中選取多個檔案，然後使用 [標記]**面板**中的標記，類似于 [標記單一檔]，以完成大量標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="4b98e-137">您可以透過選取標記兩次來執行大量取消標籤，第一次按一下會套用標籤，第二個選取範圍會確定已清除所有選取檔案的標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![自動產生之儲存格電話描述的螢幕擷取畫面](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="4b98e-139">大量標記時，[標記] 面板將會顯示為面板中每一個標記標記的檔案計數。</span><span class="sxs-lookup"><span data-stu-id="4b98e-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="4b98e-140">在其他審閱面板中標記</span><span class="sxs-lookup"><span data-stu-id="4b98e-140">Tagging in other review panels</span></span>

<span data-ttu-id="4b98e-141">當您審閱檔時，您可以使用其他的「審閱」面板來查看結果格線中檔的其他特性。</span><span class="sxs-lookup"><span data-stu-id="4b98e-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="4b98e-142">這包括複查其他相關的檔、電子郵件執行緒、接近重複專案及雜湊重複專案。</span><span class="sxs-lookup"><span data-stu-id="4b98e-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="4b98e-143">例如，當您檢查相關的檔時（使用 [**檔系列**檢查] 面板），您可以透過大量標記相關檔大幅減少審閱時間。</span><span class="sxs-lookup"><span data-stu-id="4b98e-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="4b98e-144">例如，如果電子郵件訊息有數個附件，而您想確定整個系列都以一致的方式標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="4b98e-145">例如，以下是使用 [**檔系列**檢查] 面板時，顯示 [**標記] 面板**的方式：</span><span class="sxs-lookup"><span data-stu-id="4b98e-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="4b98e-146">在 [審閱] 面板開啟選取檔時（例如，在 [**檔系列**檢查] 面板中顯示相關內容的清單），按一下 [檔系列檢查面板] 底下的 [**標記檔**]。</span><span class="sxs-lookup"><span data-stu-id="4b98e-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="4b98e-147">[標記] 面板會顯示為快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="4b98e-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="4b98e-148">選擇一個或多個要套用選取檔的標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="4b98e-149">若要標記所有檔，請選取 [檔] [**系列**] 面板中的 [所有檔]，然後按一下 [**標記檔**]，然後選擇要套用至整個檔系列的標記。</span><span class="sxs-lookup"><span data-stu-id="4b98e-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![自動產生社交媒體發佈描述的螢幕擷取畫面](../media/Relatedtag.png)
