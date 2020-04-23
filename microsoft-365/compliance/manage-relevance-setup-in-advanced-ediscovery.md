---
title: 在進階電子文件探索中管理相關性設定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: 閱讀在進階電子文件探索設定相關性訓練的建議，依其相關性為檔案評分，並產生分析結果。
ms.openlocfilehash: fa7a8a4bd87f91d3417183a5713f5c3c06f01ebe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632968"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="1650e-103">在 Office 365 進階電子文件探索 (傳統版) 中管理相關性設定</span><span class="sxs-lookup"><span data-stu-id="1650e-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="1650e-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1650e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="1650e-p102">進階電子文件探索相關技術採用專家引導的軟體，以依其相關性為檔案評分。進階電子文件探索相關性可用於早期案例評估 (ECA)、揀選，以及檔案範例檢閱。</span><span class="sxs-lookup"><span data-stu-id="1650e-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="1650e-p103">進階電子文件探索包含的元件用於相關性訓練和標記與案例相關的檔案。進階電子文件探索可從相關與不相關檔案的訓練範例中學習，以提供每個檔案的相關性分數，並產生可在檢閱檔案期間和之後使用的分析結果。</span><span class="sxs-lookup"><span data-stu-id="1650e-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="1650e-110">設定相關性訓練的指導方針</span><span class="sxs-lookup"><span data-stu-id="1650e-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="1650e-p104">在進階電子文件探索的 [案例]\*\*\*\* 視窗中，選取案例，然後按一下 [移至案例]\*\*\*\*。按一下 [相關性]\*\*\*\* \> [相關性設定]\*\*\*\*。請遵循建議的指導方針來設定相關性。</span><span class="sxs-lookup"><span data-stu-id="1650e-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="1650e-114">**標記**：反覆相關性訓練程序的效率取決於專家精確且一致標記檔案範例的能力。</span><span class="sxs-lookup"><span data-stu-id="1650e-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="1650e-115">**案例問題**：</span><span class="sxs-lookup"><span data-stu-id="1650e-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="1650e-p105">對於每一個問題，請在整個相關性訓練程序中使用相同的專家。不允許同時透過多個專家標記相同的問題。</span><span class="sxs-lookup"><span data-stu-id="1650e-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="1650e-118">判斷每個檔案群組是否僅與特定問題相關。</span><span class="sxs-lookup"><span data-stu-id="1650e-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="1650e-p106">如果問題的定義過於籠統，則進階電子文件探索可能會產生太多實際上不相關的檔案。如果問題的定義過於狹窄，則相關性訓練程序可能需要更多的時間。</span><span class="sxs-lookup"><span data-stu-id="1650e-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="1650e-121">在每個相關性訓練週期，進階電子文件探索會專注於單一作用中問題，並會相應地顯示過渡的範例結果。</span><span class="sxs-lookup"><span data-stu-id="1650e-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="1650e-p107">在多問題案例中，取樣模式可讓您選取要在處理中包含的問題。不會處理定義為「關閉」的問題，除非變更了它們的取樣模式。對於只有一個專家來說，問題可能是「閒置」或「開啟」。</span><span class="sxs-lookup"><span data-stu-id="1650e-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="1650e-p108">進階電子文件探索可以用來產生候選權限檔案。設定權限的個別問題。可能的話，請先訓練並揀選相關性，然後僅對揀選的集合訓練權限 (重新載入揀選的集合做為個別案例)。</span><span class="sxs-lookup"><span data-stu-id="1650e-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="1650e-p109">只在沒有開啟的範例時，才能執行批次計算 (按一下 [批次計算] 時，將顯示一個清單，列出使用者與開啟的範例)。若要「關閉」其他使用者的範例 (只在這些使用者不是標記這些範例時，才應該執行此動作)，系統管理員可以使用「修改相關性」公用程式與「所有使用者範例」選項搭配。</span><span class="sxs-lookup"><span data-stu-id="1650e-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="1650e-p110">**中繼資料**：進階電子文件探索專注於內容。它不會將中繼資料視為相關性準則的一部分。</span><span class="sxs-lookup"><span data-stu-id="1650e-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="1650e-132">**豐富性**：如果問題的豐富在評估之後小於 3%，請考慮將已知的相關和不相關檔案植入相關性訓練中。</span><span class="sxs-lookup"><span data-stu-id="1650e-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="1650e-p111">**檔案大小**：在相關性中，會忽略大型檔案 (擷取的文字超過 5,242,880 個字元)。這些檔案不會參與相關性訓練程序，而且在批次計算之後也不會收到相關性分數。評估集可以包含超過 5MB 的檔案。</span><span class="sxs-lookup"><span data-stu-id="1650e-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="1650e-136">設定案例問題</span><span class="sxs-lookup"><span data-stu-id="1650e-136">Setting up case issues</span></span>

<span data-ttu-id="1650e-137">本節所述的參數可用於進階電子文件探索的 [相關性]\*\*\*\* \> [相關性設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1650e-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="1650e-138">問題必須指派給將訓練檔案的使用者。</span><span class="sxs-lookup"><span data-stu-id="1650e-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="1650e-139">然後，匯入的檔案必須新增至正在處理的負載。</span><span class="sxs-lookup"><span data-stu-id="1650e-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="1650e-140">仔細定義並組織問題，因為這可能會影響相關性訓練結果。</span><span class="sxs-lookup"><span data-stu-id="1650e-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="1650e-141">在設定參數之後，檢閱者/專家可以開始訓練 [相關性]\*\*\*\* 索引標籤中的檔案。</span><span class="sxs-lookup"><span data-stu-id="1650e-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1650e-142">請參閱</span><span class="sxs-lookup"><span data-stu-id="1650e-142">See also</span></span>

[<span data-ttu-id="1650e-143">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="1650e-143">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1650e-144">定義問題並指派使用者</span><span class="sxs-lookup"><span data-stu-id="1650e-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="1650e-145">設定負載以新增匯入的檔案</span><span class="sxs-lookup"><span data-stu-id="1650e-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="1650e-146">定義反白顯示的關鍵字和進階選項</span><span class="sxs-lookup"><span data-stu-id="1650e-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

