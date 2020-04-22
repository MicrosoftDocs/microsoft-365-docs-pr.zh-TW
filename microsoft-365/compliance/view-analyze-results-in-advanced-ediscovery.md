---
title: 在高級電子檔探索中查看分析結果
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
description: '瞭解在高級 eDiscovery 中查看分析程式結果的位置，包括所顯示之任務選項的定義。  '
ms.openlocfilehash: 09bb682e753730a4c01581e71f05b5b8ef3d4779
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626359"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="91496-103">在高級 eDiscovery （古典）中查看分析結果</span><span class="sxs-lookup"><span data-stu-id="91496-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="91496-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="91496-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="91496-106">在 [高級 eDiscovery] 中，分析程式的進度和結果可以透過如下所述的各種顯示器加以查看。</span><span class="sxs-lookup"><span data-stu-id="91496-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="91496-107">View 分析任務狀態</span><span class="sxs-lookup"><span data-stu-id="91496-107">View Analyze task status</span></span>

<span data-ttu-id="91496-108">在 **[ \>準備\>分析\>結果**] 工作狀態中，會在分析程式執行期間和之後顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="91496-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![分析工作狀態](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="91496-110">顯示的工作可能會隨選取的選項而異。</span><span class="sxs-lookup"><span data-stu-id="91496-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="91496-111">**ND/ET： setup**：為執行做好準備，例如設定 run 和 case 參數。</span><span class="sxs-lookup"><span data-stu-id="91496-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="91496-112">**Nd/ET： nd 計算**：處理檔案的接近重複的分析。</span><span class="sxs-lookup"><span data-stu-id="91496-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="91496-113">**ND/ET： ET 計算**：對整個電子郵件集執行電子郵件執行緒分析。</span><span class="sxs-lookup"><span data-stu-id="91496-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="91496-114">**ND/ET：旋轉及類似**點：執行 pivot 及檔相似性處理。</span><span class="sxs-lookup"><span data-stu-id="91496-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="91496-115">**ND/ET：中繼資料更新**：完成資料庫中檔案上收集的新資料。</span><span class="sxs-lookup"><span data-stu-id="91496-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="91496-116">**主題：主題計算**：執行主題分析。</span><span class="sxs-lookup"><span data-stu-id="91496-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="91496-117">（只有選取時才顯示）。</span><span class="sxs-lookup"><span data-stu-id="91496-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="91496-118">工作**狀態**：在任務完成後會顯示此行。</span><span class="sxs-lookup"><span data-stu-id="91496-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="91496-119">在執行工作時，會顯示 [執行持續時間]。</span><span class="sxs-lookup"><span data-stu-id="91496-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91496-120">「近期重複」和「電子郵件執行緒」（ND 和 ED）的分析結果會套用到要處理的檔數目。</span><span class="sxs-lookup"><span data-stu-id="91496-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="91496-121">不會包含完全重複的檔案。</span><span class="sxs-lookup"><span data-stu-id="91496-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="91496-122">查看接近重複和電子郵件的執行緒狀態</span><span class="sxs-lookup"><span data-stu-id="91496-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="91496-123">**目標**人口結果會顯示目標人口中的檔、電子郵件、附件及錯誤數目。</span><span class="sxs-lookup"><span data-stu-id="91496-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="91496-124">**檔**結果會顯示轉動的數目、唯一接近重複的專案，以及完全重複的檔案。</span><span class="sxs-lookup"><span data-stu-id="91496-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="91496-125">**電子**郵件結果會顯示包含、包含減去包含的唯一包含副本，以及其餘的電子郵件訊息的數目。</span><span class="sxs-lookup"><span data-stu-id="91496-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="91496-126">不同類型的電子郵件結果如下：</span><span class="sxs-lookup"><span data-stu-id="91496-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="91496-127">**包含**：包含電子郵件是電子郵件線索中的終止節點，且包含該執行緒先前的所有歷史。</span><span class="sxs-lookup"><span data-stu-id="91496-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="91496-128">因此，檢閱者可以安全地著重于包含的電子郵件，而不需要先讀取執行緒中的先前訊息。</span><span class="sxs-lookup"><span data-stu-id="91496-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="91496-129">**包括減號**：若有一個或多個不同的附件與包含的郵件的父代相關聯，則指定為包含的非獨佔電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91496-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="91496-130">在此內容中，「父項」是用於向上的電子郵件線索或該特定包含電子郵件中所含之交談的郵件。</span><span class="sxs-lookup"><span data-stu-id="91496-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="91496-131">檢閱者可以使用包括減號表示做為信號，雖然可能不需要複查包含的電子郵件父代的內容，但審閱與包含的路徑父系相關聯的附件可能很有用。</span><span class="sxs-lookup"><span data-stu-id="91496-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="91496-132">**包含副本**：若包含的電子郵件是另一封標記為包含或包含減號的郵件複本，則指定為包含副本。</span><span class="sxs-lookup"><span data-stu-id="91496-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="91496-133">換句話說，這封郵件與另一個包含的郵件有相同的主旨和內文，所以共同位於相同的節點。</span><span class="sxs-lookup"><span data-stu-id="91496-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="91496-134">由於包含的副本郵件包含相同的內容，因此通常可以在審核程式中略過。</span><span class="sxs-lookup"><span data-stu-id="91496-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="91496-135">**Rest**：這表示不含任何唯一內容的電子郵件，因此不屬於上述任何一種類別。</span><span class="sxs-lookup"><span data-stu-id="91496-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="91496-136">不需要檢查這些電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="91496-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="91496-137">如果郵件包含附件，但不在後續包含的電子郵件中，可能需要檢查附件。</span><span class="sxs-lookup"><span data-stu-id="91496-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="91496-138">這會線上程記憶體在非獨佔減去電子郵件的指示。</span><span class="sxs-lookup"><span data-stu-id="91496-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="91496-139">[**附件**] 結果會顯示附件的數目，根據這種類型的唯一和重複。</span><span class="sxs-lookup"><span data-stu-id="91496-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![近似重複項目和電子郵件執行緒](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="91496-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="91496-141">See also</span></span>

[<span data-ttu-id="91496-142">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="91496-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="91496-143">瞭解檔相似性</span><span class="sxs-lookup"><span data-stu-id="91496-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91496-144">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="91496-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91496-145">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="91496-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91496-146">設定分析高級設定</span><span class="sxs-lookup"><span data-stu-id="91496-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

