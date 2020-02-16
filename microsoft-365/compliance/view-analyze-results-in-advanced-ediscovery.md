---
title: 在 Office 365 進階電子文件探索中檢視分析結果
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解要檢視 Office 365 進階電子文件探索，包括顯示的工作選項的定義中的分析處理的結果。  '
ms.openlocfilehash: bac173beebe2fdf3d07122bfca04cbaaee6410e6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069176"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="39d10-103">在 Office 365 進階電子文件探索中檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="39d10-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="39d10-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="39d10-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="39d10-106">在 [進階電子文件，進度和分析處理程序的結果可以檢視中顯示各種如下所示。</span><span class="sxs-lookup"><span data-stu-id="39d10-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="39d10-107">檢視分析工作狀態</span><span class="sxs-lookup"><span data-stu-id="39d10-107">View Analyze task status</span></span>

<span data-ttu-id="39d10-108">在 [**準備\>分析\>結果\>任務狀態**、 期間和之後分析處理程序執行，會顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="39d10-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![分析工作狀態](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="39d10-110">顯示的工作會視所選取的選項而異。</span><span class="sxs-lookup"><span data-stu-id="39d10-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="39d10-111">**ND/ET： 安裝程式**： 準備來執行，例如，設定執行與案例的參數。</span><span class="sxs-lookup"><span data-stu-id="39d10-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="39d10-112">**ND/ET: ND 計算**： 程序近似重複分析的檔案。</span><span class="sxs-lookup"><span data-stu-id="39d10-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="39d10-113">**ND/ET: ET 計算**： 執行電子郵件執行緒分析對整個電子郵件設定。</span><span class="sxs-lookup"><span data-stu-id="39d10-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="39d10-114">**ND/ET： 樞紐分析表和相似之處**： 執行樞紐分析表和檔案相似性處理。</span><span class="sxs-lookup"><span data-stu-id="39d10-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="39d10-115">**ND/ET： 中繼資料更新**： 完成在資料庫中的檔案上收集到的新資料。</span><span class="sxs-lookup"><span data-stu-id="39d10-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="39d10-116">**佈景主題： 佈景主題計算**： 執行佈景主題分析。</span><span class="sxs-lookup"><span data-stu-id="39d10-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="39d10-117">（顯示唯有在選取了）。</span><span class="sxs-lookup"><span data-stu-id="39d10-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="39d10-118">**工作狀態**： 這一行顯示在工作完成之後。</span><span class="sxs-lookup"><span data-stu-id="39d10-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="39d10-119">執行工作時，會顯示執行的持續時間。</span><span class="sxs-lookup"><span data-stu-id="39d10-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="39d10-120">近似重複項目和電子郵件執行緒 （ND 和 ED） 的分析結果套用至可進行處理的文件數目。</span><span class="sxs-lookup"><span data-stu-id="39d10-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="39d10-121">它不包含完全重複的檔案。</span><span class="sxs-lookup"><span data-stu-id="39d10-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="39d10-122">檢視接近重複項目和電子郵件執行緒狀態</span><span class="sxs-lookup"><span data-stu-id="39d10-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="39d10-123">**目標**母體結果會顯示目標母體中的文件、 電子郵件、 附件及錯誤數目。</span><span class="sxs-lookup"><span data-stu-id="39d10-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="39d10-124">**文件**結果顯示樞紐分析表、 唯一近似重複項目，並完全重複的檔案的數目。</span><span class="sxs-lookup"><span data-stu-id="39d10-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="39d10-125">**電子郵件**結果會顯示數目 （含），內含減唯一內含的副本，以及電子郵件的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="39d10-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="39d10-126">不同類型的電子郵件的結果是：</span><span class="sxs-lookup"><span data-stu-id="39d10-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="39d10-127">**Inclusive**: （含） 的電子郵件是在電子郵件執行緒中的終止節點，且包含該執行緒的所有舊的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="39d10-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="39d10-128">因此，檢閱者可以放心地專注於 （含） 的電子郵件，而不需要讀取在執行緒中舊的郵件。</span><span class="sxs-lookup"><span data-stu-id="39d10-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="39d10-129">**減 Inclusive**: （含） 的電子郵件會被指定為內含減號如果沒有父項 （含） 的郵件相關聯的一個或多個不同的附件。</span><span class="sxs-lookup"><span data-stu-id="39d10-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="39d10-130">在這個內容、 向上位於電子郵件執行緒或交談的郵件都使用父系字詞包含在該特定 （含） 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="39d10-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="39d10-131">檢閱者可以使用內含減為訊號的指示，雖然不可能需要檢閱 （含） 的電子郵件家長的內容，可能很有用來檢閱 （含） 的路徑家長相關聯的附件。</span><span class="sxs-lookup"><span data-stu-id="39d10-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="39d10-132">**內含的複本**： （含） 的電子郵件指定作為內含複製如果它是另一個郵件副本標示為 （含） 或減號 （含）。</span><span class="sxs-lookup"><span data-stu-id="39d10-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="39d10-133">換句話說，此訊息有相同的主體和主體為另一個 （含） 的郵件，因此共同位於相同的節點。</span><span class="sxs-lookup"><span data-stu-id="39d10-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="39d10-134">內含複製郵件包含相同的內容，因為他們可以通常會略過檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="39d10-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="39d10-135">**其餘**： 這表示不包含任何唯一的內容，因此不屬於任何先前的三種類別的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="39d10-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="39d10-136">這些電子郵件訊息不需要檢閱。</span><span class="sxs-lookup"><span data-stu-id="39d10-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="39d10-137">如果郵件包含不在稍後內含電子郵件的附件，可能需要檢閱的附件。</span><span class="sxs-lookup"><span data-stu-id="39d10-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="39d10-138">這被指定的電子郵件執行緒內減去 （含） 存在。</span><span class="sxs-lookup"><span data-stu-id="39d10-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="39d10-139">**附件**結果會顯示附件，根據這類為唯一的類型和重複項目數目。</span><span class="sxs-lookup"><span data-stu-id="39d10-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![近似重複項目和電子郵件執行緒](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="39d10-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39d10-141">See also</span></span>

[<span data-ttu-id="39d10-142">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="39d10-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="39d10-143">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="39d10-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39d10-144">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="39d10-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39d10-145">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="39d10-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39d10-146">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="39d10-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

