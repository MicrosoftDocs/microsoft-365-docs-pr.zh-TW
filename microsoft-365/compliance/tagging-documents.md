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
ms.openlocfilehash: 1c0eaed5d5971a55e4e9851bac3133bcd961eb36
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557693"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="5bf33-102">標記檢閱集中的文件</span><span class="sxs-lookup"><span data-stu-id="5bf33-102">Tag documents in a review set</span></span>

<span data-ttu-id="5bf33-103">組織中檢閱設定的內容很重要完成 eDiscovery 程序中的各種工作流程。</span><span class="sxs-lookup"><span data-stu-id="5bf33-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="5bf33-104">這包括：</span><span class="sxs-lookup"><span data-stu-id="5bf33-104">This includes:</span></span>

- <span data-ttu-id="5bf33-105">挑選不必要的內容</span><span class="sxs-lookup"><span data-stu-id="5bf33-105">Culling unnecessary content</span></span>

- <span data-ttu-id="5bf33-106">識別相關的內容</span><span class="sxs-lookup"><span data-stu-id="5bf33-106">Identifying relevant content</span></span>
 
- <span data-ttu-id="5bf33-107">識別必須由專家或律師檢閱的內容</span><span class="sxs-lookup"><span data-stu-id="5bf33-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="5bf33-108">當專家、 律師或其他使用者檢閱檢閱集合中的內容時，其相關內容的意見可以擷取使用標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="5bf33-109">例如，如果目的是要 cull 不必要的內容，使用者可以具有標記，例如 「 非回應 「 標記文件。</span><span class="sxs-lookup"><span data-stu-id="5bf33-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="5bf33-110">檢閱並標記內容之後，檢閱設定搜尋可以建立排除標示為 「 非回應 」，以排除此內容中的 eDiscovery 工作流程的下一個步驟從任何內容。</span><span class="sxs-lookup"><span data-stu-id="5bf33-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="5bf33-111">[標記] 面板可以自訂每個案例，以便將標記可支援預定的檢閱 」 工作流程。</span><span class="sxs-lookup"><span data-stu-id="5bf33-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="5bf33-112">標記類型</span><span class="sxs-lookup"><span data-stu-id="5bf33-112">Tag types</span></span>

<span data-ttu-id="5bf33-113">進階電子文件提供兩種類型的標記：</span><span class="sxs-lookup"><span data-stu-id="5bf33-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="5bf33-114">**單一選擇標記**-會限制使用者可以選取群組內的單一標籤。</span><span class="sxs-lookup"><span data-stu-id="5bf33-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="5bf33-115">這可確保使用者不選取衝突的標記，例如 「 回應 」 及 「 非回應 」。</span><span class="sxs-lookup"><span data-stu-id="5bf33-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> <span data-ttu-id="5bf33-116">這些會顯示為選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="5bf33-116">These will appear as radio buttons.</span></span>

- <span data-ttu-id="5bf33-117">**多重選擇標記**-允許使用者選取群組內的多個標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-117">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="5bf33-118">這些會顯示為] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5bf33-118">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="5bf33-119">標記結構</span><span class="sxs-lookup"><span data-stu-id="5bf33-119">Tag structure</span></span>

<span data-ttu-id="5bf33-120">標記類型，除了結構的標記 [標記] 面板中的組織方式可用來進行更容易了解標記的文件。</span><span class="sxs-lookup"><span data-stu-id="5bf33-120">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="5bf33-121">標記分組章節。</span><span class="sxs-lookup"><span data-stu-id="5bf33-121">Tags are grouped by sections.</span></span> <span data-ttu-id="5bf33-122">檢閱設定搜尋支援搜尋由標記和標記] 區段中的功能。</span><span class="sxs-lookup"><span data-stu-id="5bf33-122">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="5bf33-123">這表示您可以建立檢閱設定搜尋以擷取使用中] 區段中的任何標記來標記的文件。</span><span class="sxs-lookup"><span data-stu-id="5bf33-123">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![在 [標籤] 面板中的標記區段](../media/Tagtypes.png)

<span data-ttu-id="5bf33-125">標籤可以進一步組織由這些區段內的巢狀。</span><span class="sxs-lookup"><span data-stu-id="5bf33-125">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="5bf33-126">例如，如果目的是要找出並標記特殊權限的內容、 巢狀結構可以用來清楚，使用者可以標記為 「 權限 」 文件，並藉由檢查適當的巢狀的標記選取的權限類型。</span><span class="sxs-lookup"><span data-stu-id="5bf33-126">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![標記區段內的巢狀的標記](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="5bf33-128">套用標籤</span><span class="sxs-lookup"><span data-stu-id="5bf33-128">Applying tags</span></span>

<span data-ttu-id="5bf33-129">有幾種方式將標籤套用到內容。</span><span class="sxs-lookup"><span data-stu-id="5bf33-129">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="5bf33-130">標記單一文件</span><span class="sxs-lookup"><span data-stu-id="5bf33-130">Tagging a single document</span></span>

<span data-ttu-id="5bf33-131">當您檢視文件檢閱集中，您可以顯示檢閱可以**標記面板**，即可使用標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-131">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![按一下 [標籤面板中顯示的標籤面板](../media/Singledoctag.png)

<span data-ttu-id="5bf33-133">這可讓您將標籤套用至檢視器中顯示的文件。</span><span class="sxs-lookup"><span data-stu-id="5bf33-133">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="5bf33-134">大量標記</span><span class="sxs-lookup"><span data-stu-id="5bf33-134">Bulk tagging</span></span>

<span data-ttu-id="5bf33-135">大量標記可透過結果方格中選取多個檔案，然後使用**標記面板**類似標記單一文件中的 [標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-135">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="5bf33-136">未標示的大量可以進行兩次; 選取標記第一次將套用標記，以及第二個選取項目可確保所有選取的檔案會清除標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-136">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![行動電話的螢幕擷取畫面會自動產生描述](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="5bf33-138">大量標記時，[標記] 面板將面板中顯示的每個標籤的標記檔案計數。</span><span class="sxs-lookup"><span data-stu-id="5bf33-138">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="5bf33-139">在其他檢視] 面板中標記</span><span class="sxs-lookup"><span data-stu-id="5bf33-139">Tagging in other review panels</span></span>

<span data-ttu-id="5bf33-140">當檢閱文件，您可以使用其他檢閱面板檢閱結果方格中的文件的其他特性。</span><span class="sxs-lookup"><span data-stu-id="5bf33-140">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="5bf33-141">這包括檢閱其他相關的文件、 電子郵件執行緒，接近重複項目及雜湊重複項目。</span><span class="sxs-lookup"><span data-stu-id="5bf33-141">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="5bf33-142">例如，當您要檢閱相關的文件 （藉由使用 [**文件系列**檢閱] 面板），您可以大幅減少檢閱時間大量標記相關的文件。</span><span class="sxs-lookup"><span data-stu-id="5bf33-142">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="5bf33-143">例如，如果電子郵件有幾個附件，而且您想要確保整個系列標記一致。</span><span class="sxs-lookup"><span data-stu-id="5bf33-143">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="5bf33-144">例如，以下是如何使用 [**文件系列**檢閱] 面板時顯示**標記面板**：</span><span class="sxs-lookup"><span data-stu-id="5bf33-144">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="5bf33-145">使用檢閱] 面板開啟選取的文件 （如需範例，顯示相關內容的清單中**的文件系列**檢閱] 面板中，按一下文件家庭檢閱面板下的 [使用**標記的文件**]。</span><span class="sxs-lookup"><span data-stu-id="5bf33-145">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="5bf33-146">為快顯視窗顯示標記] 面板。</span><span class="sxs-lookup"><span data-stu-id="5bf33-146">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="5bf33-147">選擇要套用的所選的文件的一或多個標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-147">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="5bf33-148">若要標記的所有文件，選取**文件系列**面板中的所有文件、 按一下**標籤文件**，然後選擇 [套用至文件的整個系列的標記。</span><span class="sxs-lookup"><span data-stu-id="5bf33-148">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![社交媒體張貼描述自動產生的螢幕擷取畫面](../media/Relatedtag.png)
