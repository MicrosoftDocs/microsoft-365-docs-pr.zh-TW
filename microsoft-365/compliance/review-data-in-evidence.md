---
title: 檢閱辨識項中的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何查看您的證據中的資料，例如以原生、文字或近乎原生格式查看的方法。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9335b95cc57add69660b707577829caef1ad8183
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285379"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="a9faf-103">檢閱辨識項中的資料</span><span class="sxs-lookup"><span data-stu-id="a9faf-103">Review the data in evidence</span></span>

<span data-ttu-id="a9faf-104">資料調查中的證據集中的資料是您收集並新增至證據集之搜尋結果的快照。</span><span class="sxs-lookup"><span data-stu-id="a9faf-104">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="a9faf-105">當您將搜尋結果新增至證據時，會觸發處理常式，以從搜尋傳回的專案提取檔、中繼資料和文字。</span><span class="sxs-lookup"><span data-stu-id="a9faf-105">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="a9faf-106">然後，資料調查 (預覽) 工具會建立新的索引 (由稱為「 *高級索引* 」) 的所有資料，並新增至 [ **證據** ] 索引標籤上的證據集。</span><span class="sxs-lookup"><span data-stu-id="a9faf-106">Then the Data Investigations (preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="a9faf-107">針對時間敏感調查，這可讓您刪除位於原始資料來源中的實際濺入或惡意資料，同時也可讓您調查隔離環境中重新建立的證據，在此情況下，會將資料複製到證據集) 。</span><span class="sxs-lookup"><span data-stu-id="a9faf-107">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="a9faf-108">收集證據並將證據新增至證據集之後，您可以查看以原生格式、文字格式或原始格式的個別檔，以供您用來批註及密文的檔。</span><span class="sxs-lookup"><span data-stu-id="a9faf-108">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="a9faf-109">此外，您可以執行查詢來縮小資料集的時間範圍、檔案類型、資料擁有人，以及許多其他屬性和搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="a9faf-109">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="a9faf-110">例如，使用作者、寄件者或收件者條件，您可以快速識別事件中涉及的人員，以及您的組織中是否有任何與外部使用者共用的資料。</span><span class="sxs-lookup"><span data-stu-id="a9faf-110">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="a9faf-111">如需搜尋證據集中資料的詳細資訊，請參閱 [查詢證據中的資料](evidence-query.md)。</span><span class="sxs-lookup"><span data-stu-id="a9faf-111">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="a9faf-112">若要群組檔並取得更多您的評論協助，請選取 [ **證據** ] 索引標籤上的證據集，然後按一下 [ **管理證據**]。</span><span class="sxs-lookup"><span data-stu-id="a9faf-112">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="a9faf-113">在 [ **分析** ] 磚中，按一下 **[重新建立整個集的分析**]。</span><span class="sxs-lookup"><span data-stu-id="a9faf-113">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="a9faf-114">這會執行高級分析，例如重複偵測、電子郵件執行緒及主題分析。</span><span class="sxs-lookup"><span data-stu-id="a9faf-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="a9faf-115">之後，您就可以查看資料的一般主題，也可以透過電子郵件執行緒、接近重複專案以及完全重複的方式來組織檔，以協助您進行調查。</span><span class="sxs-lookup"><span data-stu-id="a9faf-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="a9faf-116">如需詳細資訊，請參閱 [執行分析以更快速地進行調查](run-analytics-to-investigate-faster.md)。</span><span class="sxs-lookup"><span data-stu-id="a9faf-116">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="a9faf-117">在證據中查看檔</span><span class="sxs-lookup"><span data-stu-id="a9faf-117">View documents in evidence</span></span>

<span data-ttu-id="a9faf-118">「資料調查」 (預覽) 工具可讓您在多個不同的檢視器中顯示內容，每個檢視器各有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="a9faf-118">The Data Investigations (preview) tool allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="a9faf-119">這些檢視器包括：</span><span class="sxs-lookup"><span data-stu-id="a9faf-119">These viewers are:</span></span>

- <span data-ttu-id="a9faf-120">檔中繼資料</span><span class="sxs-lookup"><span data-stu-id="a9faf-120">File metadata</span></span>
- <span data-ttu-id="a9faf-121">原生視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-121">Native view</span></span>
- <span data-ttu-id="a9faf-122">文字視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-122">Text view</span></span>
- <span data-ttu-id="a9faf-123">批註視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-123">Annotate view</span></span>

<span data-ttu-id="a9faf-124">若要存取這些檢視器，只要選取證據集中的檔。</span><span class="sxs-lookup"><span data-stu-id="a9faf-124">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="a9faf-125">檔中繼資料</span><span class="sxs-lookup"><span data-stu-id="a9faf-125">File metadata</span></span>

<span data-ttu-id="a9faf-126">這個視圖會顯示與選取檔相關聯的各種中繼資料屬性。</span><span class="sxs-lookup"><span data-stu-id="a9faf-126">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="a9faf-127">您可以按一下 [檔案 **中繼資料**] 開啟和關閉此視圖。</span><span class="sxs-lookup"><span data-stu-id="a9faf-127">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="a9faf-128">當您審閱檔時，您可以在不同的檢視器之間查看檔案中繼資料，但仍然可以變更。</span><span class="sxs-lookup"><span data-stu-id="a9faf-128">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="a9faf-129">以下是一份檔的檔案中繼資料範例。</span><span class="sxs-lookup"><span data-stu-id="a9faf-129">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="a9faf-130">如需元資料欄位的詳細資訊，請參閱 [資料調查中的檔元資料欄位 (預覽) ](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="a9faf-130">For more information about the metadata fields, see [Document metadata fields in Data Investigations (preview)](document-metadata-fields.md).</span></span>

![檔中繼資料面板](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="a9faf-132">原生視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-132">Native view</span></span>

<span data-ttu-id="a9faf-133">原生檢視器會以原生格式顯示檔的最準確的視圖。</span><span class="sxs-lookup"><span data-stu-id="a9faf-133">The Native viewer displays the most accurate view of a document in its native format.</span></span> <span data-ttu-id="a9faf-134">數百種檔案類型支援原生模式，其可讓您以 truest 原生體驗顯示檔。</span><span class="sxs-lookup"><span data-stu-id="a9faf-134">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="a9faf-135">針對 Microsoft Office 檔案，原生檢視器會使用 web 版本的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a9faf-135">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="a9faf-136">這可讓您在 Excel 中查看不同 Office 檔、公式和隱藏列/欄中的批註等內容，以及 PowerPoint 中的 [附注] 視圖。</span><span class="sxs-lookup"><span data-stu-id="a9faf-136">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="a9faf-137">原生視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-137">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="a9faf-138">文字視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-138">Text view</span></span>

<span data-ttu-id="a9faf-139">文字檢視器提供檔的解壓縮文字的視圖。</span><span class="sxs-lookup"><span data-stu-id="a9faf-139">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="a9faf-140">它會忽略任何內嵌的圖像和格式設定，但是如果您嘗試快速查看並瞭解檔中的內容，此視圖會很有用。</span><span class="sxs-lookup"><span data-stu-id="a9faf-140">It ignores any embedded images and formatting, but this view is useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="a9faf-141">文字視圖也包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="a9faf-141">Text view also includes these features:</span></span>

  - <span data-ttu-id="a9faf-142">行計數器，可讓您更輕鬆地參考檔的特定部分。</span><span class="sxs-lookup"><span data-stu-id="a9faf-142">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="a9faf-143">在檔中和捲軸上突出顯示字詞的搜尋順序醒目提示</span><span class="sxs-lookup"><span data-stu-id="a9faf-143">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="a9faf-144">在使用 [ **臨近重複** ] 面板來查看檔時，比較視圖會提供比較視圖，以強調文字差異。</span><span class="sxs-lookup"><span data-stu-id="a9faf-144">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="a9faf-145">**文字和捲軸中的行計數器及搜尋順序醒目提示範例**</span><span class="sxs-lookup"><span data-stu-id="a9faf-145">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="a9faf-146">文字視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-146">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="a9faf-147">**Diff view 的範例**</span><span class="sxs-lookup"><span data-stu-id="a9faf-147">**Example of the diff view**</span></span>

![<span data-ttu-id="a9faf-148">比較視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-148">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="a9faf-149">批註視圖</span><span class="sxs-lookup"><span data-stu-id="a9faf-149">Annotate view</span></span>

<span data-ttu-id="a9faf-150">[批註] 視圖提供的功能可讓您在審閱過程中對檔套用標記;這包括下列工具：</span><span class="sxs-lookup"><span data-stu-id="a9faf-150">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="a9faf-151">**區域密文** –您可以在隱藏敏感內容的檔中繪製不透明的方塊。</span><span class="sxs-lookup"><span data-stu-id="a9faf-151">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="a9faf-152">**鉛筆** –您可以在檔上自由手繪出內容的某些部分，以引起注意</span><span class="sxs-lookup"><span data-stu-id="a9faf-152">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="a9faf-153">**選取批註** -您可以選取及刪除檔中的批註。</span><span class="sxs-lookup"><span data-stu-id="a9faf-153">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="a9faf-154">**切換批註透明性** –您可以在不透明和半透明) 之間切換批註的透明度 (，以便您可以查看批註背後的內容。</span><span class="sxs-lookup"><span data-stu-id="a9faf-154">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent) so you can view the content behind the annotation.</span></span> <span data-ttu-id="a9faf-155">這包括切換鉛筆批註和密文的透明度。</span><span class="sxs-lookup"><span data-stu-id="a9faf-155">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="a9faf-156">[批註] 視圖也提供下列導覽功能：</span><span class="sxs-lookup"><span data-stu-id="a9faf-156">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="a9faf-157">**上一頁**、 **下一頁**，然後移至多分頁檔使用的 **頁面** 導覽控制項。</span><span class="sxs-lookup"><span data-stu-id="a9faf-157">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="a9faf-158">**縮放** –以批註模式增加或減少檔案大小。</span><span class="sxs-lookup"><span data-stu-id="a9faf-158">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="a9faf-159">**旋轉** –順時針旋轉檔。</span><span class="sxs-lookup"><span data-stu-id="a9faf-159">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="a9faf-160">**搜尋** –搜尋檔中的關鍵字，然後使用 [上一個] 和 [下一步] 控制項，以查看檔中) 醒目提示 (的點擊順序。</span><span class="sxs-lookup"><span data-stu-id="a9faf-160">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="a9faf-161">**批註視圖的範例**</span><span class="sxs-lookup"><span data-stu-id="a9faf-161">**Example of Annotate view**</span></span>

![批註視圖](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="a9faf-163">將批註套用至已新增至證據集的檔副本。</span><span class="sxs-lookup"><span data-stu-id="a9faf-163">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="a9faf-164">Live service 中的原始檔案沒有批註。</span><span class="sxs-lookup"><span data-stu-id="a9faf-164">The original documents in the live service aren't annotated.</span></span>
