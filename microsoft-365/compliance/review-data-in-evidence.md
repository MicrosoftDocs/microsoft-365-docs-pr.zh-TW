---
title: 檢閱辨識項中的資料
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
ms.openlocfilehash: 20ac1adb67014439110e355025b31753a4a6bcfe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078149"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="f74d5-102">檢閱辨識項中的資料</span><span class="sxs-lookup"><span data-stu-id="f74d5-102">Review the data in evidence</span></span>

<span data-ttu-id="f74d5-103">数据调查中的证据集中的数据是您收集并添加到证据集的搜索结果的快照。</span><span class="sxs-lookup"><span data-stu-id="f74d5-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="f74d5-104">将搜索结果添加到证据时，将触发一个进程，从搜索返回的项目中提取文件、元数据和文本。</span><span class="sxs-lookup"><span data-stu-id="f74d5-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="f74d5-105">然后，数据调查（预览）工具生成所有数据的新索引（通过称为*高级索引*的过程），并**添加到"证据"** 选项卡上设置的证据。</span><span class="sxs-lookup"><span data-stu-id="f74d5-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="f74d5-106">对于时间敏感的调查，这允许您通过删除位于原始数据源中的实际溢出或恶意数据来快速控制环境，同时允许您调查在隔离环境，在这种情况下，这是复制到证据集的数据）。</span><span class="sxs-lookup"><span data-stu-id="f74d5-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="f74d5-107">收集证据并将其添加到证据集后，可以查看各个文档的本机格式、文本格式或可用于对文档进行分文和编辑的接近本机格式。</span><span class="sxs-lookup"><span data-stu-id="f74d5-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="f74d5-108">此外，还可以运行查询以按时间范围、文件类型、数据所有者以及许多其他属性和搜索条件缩小数据集。</span><span class="sxs-lookup"><span data-stu-id="f74d5-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="f74d5-109">例如，通过使用"作者"、"发件人"或"收件人"条件，您可以快速识别事件所涉及的人员，以及组织中的任何数据是否已与外部用户共享。</span><span class="sxs-lookup"><span data-stu-id="f74d5-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="f74d5-110">有关在证据集中搜索数据的详细信息，请参阅[查询证据中的数据。](evidence-query.md)</span><span class="sxs-lookup"><span data-stu-id="f74d5-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="f74d5-111">要对文档进行分组并获取更多审核帮助，**请选择"证据"** 选项卡上设置的证据，然后单击"**管理证据"。**</span><span class="sxs-lookup"><span data-stu-id="f74d5-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="f74d5-112">在"**分析"** 磁贴中，**单击"重建整个集的分析"。**</span><span class="sxs-lookup"><span data-stu-id="f74d5-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="f74d5-113">这将运行高级分析，如重复检测、电子邮件线程和主题分析。</span><span class="sxs-lookup"><span data-stu-id="f74d5-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="f74d5-114">之后，您可以看到数据的一般主题，还可以通过电子邮件线程、接近重复项和精确重复项组织文档，以帮助您进行调查。</span><span class="sxs-lookup"><span data-stu-id="f74d5-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="f74d5-115">有关详细信息，请参阅[运行分析以加快调查](run-analytics-to-investigate-faster.md)速度。</span><span class="sxs-lookup"><span data-stu-id="f74d5-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="f74d5-116">查看证据文档</span><span class="sxs-lookup"><span data-stu-id="f74d5-116">View documents in evidence</span></span>

<span data-ttu-id="f74d5-117">数据调查（预览）允许您在多个不同的查看器中显示内容，每个查看器具有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="f74d5-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="f74d5-118">这些查看器是：</span><span class="sxs-lookup"><span data-stu-id="f74d5-118">These viewers are:</span></span>

- <span data-ttu-id="f74d5-119">文件元数据</span><span class="sxs-lookup"><span data-stu-id="f74d5-119">File metadata</span></span>
- <span data-ttu-id="f74d5-120">本机视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-120">Native view</span></span>
- <span data-ttu-id="f74d5-121">文本视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-121">Text view</span></span>
- <span data-ttu-id="f74d5-122">分名视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-122">Annotate view</span></span>

<span data-ttu-id="f74d5-123">要访问这些查看器中的任何一个，只需在证据集中选择文档。</span><span class="sxs-lookup"><span data-stu-id="f74d5-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="f74d5-124">文件元数据</span><span class="sxs-lookup"><span data-stu-id="f74d5-124">File metadata</span></span>

<span data-ttu-id="f74d5-125">此视图显示与所选文档关联的各种元数据属性。</span><span class="sxs-lookup"><span data-stu-id="f74d5-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="f74d5-126">您可以通过**单击"文件元数据"** 来打开和关闭此视图。</span><span class="sxs-lookup"><span data-stu-id="f74d5-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="f74d5-127">查看文档时，您可以查看文件元数据，但仍可在不同查看者之间进行更改。</span><span class="sxs-lookup"><span data-stu-id="f74d5-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="f74d5-128">下面是文档的文件元数据示例。</span><span class="sxs-lookup"><span data-stu-id="f74d5-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="f74d5-129">有关元数据字段的详细信息，请参阅[数据调查（预览）中的"文档元数据"字段。](document-metadata-fields.md)</span><span class="sxs-lookup"><span data-stu-id="f74d5-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![文件元数据面板](media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="f74d5-131">本机视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-131">Native view</span></span>

<span data-ttu-id="f74d5-132">本机查看器以本机格式显示文档的最准确视图。</span><span class="sxs-lookup"><span data-stu-id="f74d5-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="f74d5-133">本机视图支持数百种文件类型，旨在以尽可能真实的本机体验显示文档。</span><span class="sxs-lookup"><span data-stu-id="f74d5-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="f74d5-134">对于 Microsoft Office 文件，本机查看器使用 Office 应用的 Web 版本。</span><span class="sxs-lookup"><span data-stu-id="f74d5-134">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="f74d5-135">这允许您查看内容，如不同 Office 文档中的注释、Excel 中的公式和隐藏行/列，以及 PowerPoint 中的"注释"视图。</span><span class="sxs-lookup"><span data-stu-id="f74d5-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="f74d5-136">本机视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-136">Native view</span></span>
](media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="f74d5-137">文本视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-137">Text view</span></span>

<span data-ttu-id="f74d5-138">文本查看器提供文件提取文本的视图。</span><span class="sxs-lookup"><span data-stu-id="f74d5-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="f74d5-139">它忽略任何嵌入的图像和格式，但如果您尝试快速查看和理解文档中的内容，此视图非常有用。</span><span class="sxs-lookup"><span data-stu-id="f74d5-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="f74d5-140">文本视图还包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="f74d5-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="f74d5-141">行计数器，它便于引用文档的特定部分。</span><span class="sxs-lookup"><span data-stu-id="f74d5-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="f74d5-142">搜索点击突出显示文档中以及滚动条上的突出显示字词</span><span class="sxs-lookup"><span data-stu-id="f74d5-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="f74d5-143">差异视图提供比较视图，可在使用"**近重复"** 面板查看文档时突出显示文本差异。</span><span class="sxs-lookup"><span data-stu-id="f74d5-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="f74d5-144">**文本和滚动条中行计数器和搜索命中突出显示的示例**</span><span class="sxs-lookup"><span data-stu-id="f74d5-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="f74d5-145">文本视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-145">Text view</span></span>
](media/Reviewimage4.png)

<span data-ttu-id="f74d5-146">**差异视图示例**</span><span class="sxs-lookup"><span data-stu-id="f74d5-146">**Example of the diff view**</span></span>

![<span data-ttu-id="f74d5-147">差异视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-147">Diff view</span></span>
](media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="f74d5-148">分名视图</span><span class="sxs-lookup"><span data-stu-id="f74d5-148">Annotate view</span></span>

<span data-ttu-id="f74d5-149">"分号"视图提供功能，允许您在审阅过程中对文档应用标记;这包括这些工具：</span><span class="sxs-lookup"><span data-stu-id="f74d5-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="f74d5-150">**区域密文**– 您可以在文档上绘制隐藏敏感内容的不透明框。</span><span class="sxs-lookup"><span data-stu-id="f74d5-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="f74d5-151">**铅笔**– 您可以徒手绘制文档，以引起对内容某些部分的注意</span><span class="sxs-lookup"><span data-stu-id="f74d5-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="f74d5-152">**选择批注**- 您可以在文档中选择和删除批注。</span><span class="sxs-lookup"><span data-stu-id="f74d5-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="f74d5-153">**切换注释透明度**- 您可以切换注释的透明度（在不透明和半透明之间），以便查看注释背后的内容。</span><span class="sxs-lookup"><span data-stu-id="f74d5-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="f74d5-154">这包括切换铅笔注释和密文的透明度。</span><span class="sxs-lookup"><span data-stu-id="f74d5-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="f74d5-155">"分页"视图还提供以下导航功能：</span><span class="sxs-lookup"><span data-stu-id="f74d5-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="f74d5-156">**上一页，\*\*\*\*下一页，** 和**转到页面**导航控件，用于多页文档。</span><span class="sxs-lookup"><span data-stu-id="f74d5-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="f74d5-157">**缩放**= 在"批号"视图中增加或减小文档的大小。</span><span class="sxs-lookup"><span data-stu-id="f74d5-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="f74d5-158">**旋转**= 顺时针旋转文档。</span><span class="sxs-lookup"><span data-stu-id="f74d5-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="f74d5-159">**搜索**– 搜索文档中的关键字，然后使用"上一个"和"下一个"控件查看文档中的点击次数（突出显示）。</span><span class="sxs-lookup"><span data-stu-id="f74d5-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="f74d5-160">**批名视图示例**</span><span class="sxs-lookup"><span data-stu-id="f74d5-160">**Example of Annotate view**</span></span>

![分名视图](media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="f74d5-162">注释应用于添加到证据集的文档副本。</span><span class="sxs-lookup"><span data-stu-id="f74d5-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="f74d5-163">实时服务中的原始文档未作任何分号。</span><span class="sxs-lookup"><span data-stu-id="f74d5-163">The original documents in the live service aren't annotated.</span></span>
