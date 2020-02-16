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
description: ''
ms.openlocfilehash: cd622430df4a636a9529a4d10ddc90057548a810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080960"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="9724a-102">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="9724a-102">Tag documents in a review set</span></span>

<span data-ttu-id="9724a-103">組織中檢閱設定的內容很重要完成 eDiscovery 程序中的各種工作流程。</span><span class="sxs-lookup"><span data-stu-id="9724a-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="9724a-104">這包括：</span><span class="sxs-lookup"><span data-stu-id="9724a-104">This includes:</span></span>

-  <span data-ttu-id="9724a-105">挑選不必要的內容</span><span class="sxs-lookup"><span data-stu-id="9724a-105">Culling unnecessary content</span></span>

- <span data-ttu-id="9724a-106">識別相關的內容</span><span class="sxs-lookup"><span data-stu-id="9724a-106">Identifying relevant content</span></span>
 
-  <span data-ttu-id="9724a-107">識別必須由專家或律師檢閱的內容</span><span class="sxs-lookup"><span data-stu-id="9724a-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="9724a-108">當專家、 律師或其他使用者檢閱檢閱集合中的內容時，其相關內容的意見可以擷取使用標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="9724a-109">例如，如果目的是要 cull 不必要的內容，使用者可以具有標記，例如 「 非回應 「 標記文件。</span><span class="sxs-lookup"><span data-stu-id="9724a-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="9724a-110">檢閱並標記內容之後，檢閱設定搜尋可以建立排除標示為 「 非回應 」，以排除此內容中的 eDiscovery 工作流程的下一個步驟從任何內容。</span><span class="sxs-lookup"><span data-stu-id="9724a-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="9724a-111">[標記] 面板可以自訂每個案例，以便將標記可支援預定的檢閱 」 工作流程。</span><span class="sxs-lookup"><span data-stu-id="9724a-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="9724a-112">標記類型</span><span class="sxs-lookup"><span data-stu-id="9724a-112">Tag types</span></span>

<span data-ttu-id="9724a-113">進階電子文件提供兩種類型的標記：</span><span class="sxs-lookup"><span data-stu-id="9724a-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="9724a-114">**單一選擇標記**-會限制使用者可以選取群組內的單一標籤。</span><span class="sxs-lookup"><span data-stu-id="9724a-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="9724a-115">這可確保使用者不選取衝突的標記，例如 「 回應 」 及 「 非回應 」。</span><span class="sxs-lookup"><span data-stu-id="9724a-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> 

- <span data-ttu-id="9724a-116">**多重選擇標記**-允許使用者選取群組內的多個標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-116">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="9724a-117">標記結構</span><span class="sxs-lookup"><span data-stu-id="9724a-117">Tag structure</span></span>

<span data-ttu-id="9724a-118">標記類型，除了結構的標籤的 [標記] 面板中的組織的方式可用來進行更容易了解標記的文件。</span><span class="sxs-lookup"><span data-stu-id="9724a-118">In addition to the tag types, the structure of how tags are organization in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="9724a-119">標記分組章節。</span><span class="sxs-lookup"><span data-stu-id="9724a-119">Tags are grouped by sections.</span></span> <span data-ttu-id="9724a-120">檢閱設定搜尋支援搜尋由標記和標記] 區段中的功能。</span><span class="sxs-lookup"><span data-stu-id="9724a-120">review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="9724a-121">這表示您可以建立檢閱設定搜尋以擷取使用中] 區段中的任何標記來標記的文件。</span><span class="sxs-lookup"><span data-stu-id="9724a-121">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![在 [標籤] 面板中的標記區段](../media/Tagtypes.png)

<span data-ttu-id="9724a-123">標籤可以進一步組織由這些區段內的巢狀。</span><span class="sxs-lookup"><span data-stu-id="9724a-123">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="9724a-124">例如，如果目的是要找出並標記特殊權限的內容、 巢狀結構可以用來清楚，使用者可以標記為 「 權限 」 文件，並藉由檢查適當的巢狀的標記選取的權限類型。</span><span class="sxs-lookup"><span data-stu-id="9724a-124">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![標記區段內的巢狀的標記](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="9724a-126">套用標籤</span><span class="sxs-lookup"><span data-stu-id="9724a-126">Applying tags</span></span>

<span data-ttu-id="9724a-127">有幾種方式將標籤套用到內容。</span><span class="sxs-lookup"><span data-stu-id="9724a-127">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="9724a-128">標記單一文件</span><span class="sxs-lookup"><span data-stu-id="9724a-128">Tagging a single document</span></span>

<span data-ttu-id="9724a-129">當您檢視文件檢閱集中，您可以顯示檢閱可用**的編碼控制台]**，即可標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-129">When viewing a document in a review set, you can display the tags that a review can use by clicking **Coding panel**.</span></span>

![按一下 [標籤面板中顯示的標籤面板](../media/Singledoctag.png)

<span data-ttu-id="9724a-131">這可讓您將標籤套用至檢視器中顯示的文件。</span><span class="sxs-lookup"><span data-stu-id="9724a-131">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="9724a-132">大量標記</span><span class="sxs-lookup"><span data-stu-id="9724a-132">Bulk tagging</span></span>

<span data-ttu-id="9724a-133">大量標記可透過結果方格中選取多個檔案，然後使用**的編碼面板**類似標記單一文件中的 [標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-133">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Coding panel** similar to tagging single documents.</span></span> <span data-ttu-id="9724a-134">未標示的大量可以進行兩次; 選取標記第一次將套用標記，以及第二個選取項目可確保所有選取的檔案會清除標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-134">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![行動電話的螢幕擷取畫面會自動產生描述](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="9724a-136">大量標記時，[標記] 面板將面板中顯示的每個標籤的標記檔案計數。</span><span class="sxs-lookup"><span data-stu-id="9724a-136">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="9724a-137">在其他檢視] 面板中標記</span><span class="sxs-lookup"><span data-stu-id="9724a-137">Tagging in other review panels</span></span>

<span data-ttu-id="9724a-138">當檢閱文件，您可以使用其他檢閱面板檢閱結果方格中的文件的其他特性。</span><span class="sxs-lookup"><span data-stu-id="9724a-138">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="9724a-139">這包括檢閱其他相關的文件、 電子郵件執行緒，接近重複項目及雜湊重複項目。</span><span class="sxs-lookup"><span data-stu-id="9724a-139">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="9724a-140">例如，當您檢閱 （藉由使用 [**文件系列**檢閱] 面板） 相關的文件，您可以大幅減少檢閱時間大量標記相關的文件。</span><span class="sxs-lookup"><span data-stu-id="9724a-140">For example, when your reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="9724a-141">例如，如果電子郵件有幾個附件，而且您想要確保整個系列標記一致。</span><span class="sxs-lookup"><span data-stu-id="9724a-141">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="9724a-142">例如，以下是如何使用 [**文件系列**檢閱] 面板時顯示**的編碼控制台**：</span><span class="sxs-lookup"><span data-stu-id="9724a-142">For example, here's how to display the **Coding panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="9724a-143">使用檢閱] 面板開啟選取的文件 （如需範例，顯示相關內容的清單中**的文件系列**檢閱] 面板中，按一下 [**程式碼的文件**頂端的 [目前檢視] 面板。</span><span class="sxs-lookup"><span data-stu-id="9724a-143">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Code documents** at the top of the current review panel.</span></span>

   <span data-ttu-id="9724a-144">顯示 [編碼] 面板是快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="9724a-144">The Coding panel is displayed is a pop-up window.</span></span>

2. <span data-ttu-id="9724a-145">選擇要套用的所選的文件的一或多個標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-145">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="9724a-146">標記的所有文件、 選取**文件系列**面板中的所有文件，按一下 [**程式碼的文件**，，然後選擇要套用至文件的整個系列的標記。</span><span class="sxs-lookup"><span data-stu-id="9724a-146">To tag all documents, select all documents in the **Document family** panel, click **Code documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![社交媒體張貼描述自動產生的螢幕擷取畫面](../media/Relatedtag.png)
