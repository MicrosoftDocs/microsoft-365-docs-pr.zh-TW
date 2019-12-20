---
title: 在 Office 365 進階電子文件探索中設定分析選項
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '檢閱步驟以設定 Office 365 進階電子文件探索，包括近似重複項目、 電子郵件執行緒，以及佈景主題中的分析處理程序的選項。  '
ms.openlocfilehash: b6155814a4540f4cc619382d82cee34c471390d1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802736"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="3569b-103">在 Office 365 進階電子文件探索中設定分析選項</span><span class="sxs-lookup"><span data-stu-id="3569b-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="3569b-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3569b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="3569b-106">在進階電子文件探索中設定分析選項之前執行分析。</span><span class="sxs-lookup"><span data-stu-id="3569b-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="3569b-107">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="3569b-107">Set Analyze options</span></span>

<span data-ttu-id="3569b-108">開啟**準備\>分析** \> **安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="3569b-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="3569b-109">會顯示下列視窗。</span><span class="sxs-lookup"><span data-stu-id="3569b-109">The following window is displayed.</span></span>
  
![設定分析選項](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="3569b-111">**近似重複項目和電子郵件執行緒**如果您想要執行分析，請核取此方塊。</span><span class="sxs-lookup"><span data-stu-id="3569b-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="3569b-112">此為預設選取的選項。</span><span class="sxs-lookup"><span data-stu-id="3569b-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="3569b-113">**文件相似性**輸入 Near 重複的臨界值，或接受預設值是 65%。</span><span class="sxs-lookup"><span data-stu-id="3569b-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="3569b-114">**佈景主題**核取此方塊可處理所有檔案，並將佈景主題指派給他們。</span><span class="sxs-lookup"><span data-stu-id="3569b-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="3569b-115">根據預設，不會選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3569b-115">By default, this check box is not selected.</span></span> <span data-ttu-id="3569b-116">如果您想要執行處理的佈景主題，請輸入下列選項。</span><span class="sxs-lookup"><span data-stu-id="3569b-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="3569b-117">**佈景主題的最大數目**輸入或選取要建立的佈景主題數目的值。</span><span class="sxs-lookup"><span data-stu-id="3569b-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="3569b-118">預設值為 200。</span><span class="sxs-lookup"><span data-stu-id="3569b-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3569b-119">增加的佈景主題數目會影響效能，以及佈景主題一般化的能力。</span><span class="sxs-lookup"><span data-stu-id="3569b-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="3569b-120">佈景主題數目愈高，更細微它們是。</span><span class="sxs-lookup"><span data-stu-id="3569b-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="3569b-121">例如，如果 50 個佈景主題的一組包括 「 籃球、 Spurs、 Clippers，Lakers 」; 例如佈景主題300 佈景主題可能會包含不同的佈景主題: 「 Spurs 」、 「 Clippers 」、 「 Lakers 」。</span><span class="sxs-lookup"><span data-stu-id="3569b-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="3569b-122">如果您不有任何認知佈景主題的 「 籃球 」，並使用 ECA 這項功能，看到佈景主題 」 籃球 」 可能是很有用。</span><span class="sxs-lookup"><span data-stu-id="3569b-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="3569b-123">但是，如果處理有太多的佈景主題，您可能永遠不會看到 「 籃球 」 這個字後，可能不知道，Spurs 和 Clippers 是很好的籃球佈景主題，若要檢閱，而非移入的項目會開機並用於字形。</span><span class="sxs-lookup"><span data-stu-id="3569b-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="3569b-124">**建議的佈景主題**您可以建議來控制處理的佈景主題的佈景主題文字。</span><span class="sxs-lookup"><span data-stu-id="3569b-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="3569b-125">進階電子文件探索會專注於這些建議的字詞，並嘗試建立一或多個相關的佈景主題，根據 「 最大的佈景主題的數字 」 的設定。</span><span class="sxs-lookup"><span data-stu-id="3569b-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="3569b-126">例如，如果建議的單字"computer"，且您指定作為 」 主題數目上限 「"2"，進階電子文件會嘗試產生關聯到 「 電腦 」 這個字的兩個佈景主題。</span><span class="sxs-lookup"><span data-stu-id="3569b-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="3569b-127">佈景主題的兩個可能會 「 電腦軟體 」 和 「 電腦硬體 」，例如。</span><span class="sxs-lookup"><span data-stu-id="3569b-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![新增建議的佈景主題](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="3569b-129">若要檢視、 新增或編輯建議的佈景主題，按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="3569b-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="3569b-130">在 [**建議追蹤的佈景主題**] 面板中，按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)圖示以新增佈景主題。</span><span class="sxs-lookup"><span data-stu-id="3569b-130">In the **Suggested themes** panel, click the **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="3569b-131">在 [**新增建議的佈景主題**] 面板中，新增字詞，以逗號隔開。</span><span class="sxs-lookup"><span data-stu-id="3569b-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="3569b-132">**佈景主題數目**，選取一個值來判斷進階電子文件會嘗試將產生的 （預設值為 1 佈景主題） 這些字詞的佈景主題數目。</span><span class="sxs-lookup"><span data-stu-id="3569b-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="3569b-133">按一下 [**儲存**]，然後關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3569b-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3569b-134">總數的佈景主題包含建議的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="3569b-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="3569b-135">總數的建議的佈景主題不能超過總佈景主題。</span><span class="sxs-lookup"><span data-stu-id="3569b-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="3569b-136">如果有許多的建議的佈景主題，相對於總佈景主題，只有幾個 「 小說 」 佈景主題會偵測系統，因為大部分的佈景主題會專用於建議的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="3569b-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="3569b-137">**模式**從下拉式清單中選取**佈景主題**選項：</span><span class="sxs-lookup"><span data-stu-id="3569b-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="3569b-138">**建立並套用模型**： 計算的模型檔案的線段的佈景主題，並再將它們之間的檔案。</span><span class="sxs-lookup"><span data-stu-id="3569b-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="3569b-139">**建立模型**： 計算從檔案的線段的佈景主題模型。</span><span class="sxs-lookup"><span data-stu-id="3569b-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="3569b-140">在其他時候分別完成的分割檔案套用程序。</span><span class="sxs-lookup"><span data-stu-id="3569b-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="3569b-141">**套用模型**： 是否先前建立及尚未套用模型，僅會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="3569b-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="3569b-142">這會將佈景主題為基礎的檔案。</span><span class="sxs-lookup"><span data-stu-id="3569b-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="3569b-143">您也可以[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)，並[設定分析進階設定]](set-analyze-advanced-settings-in-advanced-ediscovery.md)的分析。</span><span class="sxs-lookup"><span data-stu-id="3569b-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="3569b-144">您已設定這些選項之後，按一下 [**分析**]，以執行。</span><span class="sxs-lookup"><span data-stu-id="3569b-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="3569b-145">[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)會顯示。</span><span class="sxs-lookup"><span data-stu-id="3569b-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3569b-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3569b-146">See also</span></span>

[<span data-ttu-id="3569b-147">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="3569b-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3569b-148">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="3569b-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3569b-149">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="3569b-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3569b-150">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="3569b-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3569b-151">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="3569b-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

