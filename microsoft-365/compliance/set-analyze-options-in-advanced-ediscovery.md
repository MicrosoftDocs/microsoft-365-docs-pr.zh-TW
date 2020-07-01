---
title: 在高級電子檔探索中設定分析選項
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 請參閱在高級 eDiscovery 中設定分析程式選項的步驟，包括近乎重複的電子郵件線索和主題。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d622e06cdfe9a46f470be46d1a5b9df98347cc0a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936880"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="c33b0-103">在高級 eDiscovery （古典）中設定分析選項</span><span class="sxs-lookup"><span data-stu-id="c33b0-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="c33b0-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="c33b0-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="c33b0-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c33b0-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c33b0-106">在 [Advanced eDiscovery] 中，設定 [分析] 選項，再執行 [分析]。</span><span class="sxs-lookup"><span data-stu-id="c33b0-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="c33b0-107">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="c33b0-107">Set Analyze options</span></span>

<span data-ttu-id="c33b0-108">開啟**準備 \> 分析** \> **設定**。</span><span class="sxs-lookup"><span data-stu-id="c33b0-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="c33b0-109">隨即會顯示下列視窗。</span><span class="sxs-lookup"><span data-stu-id="c33b0-109">The following window is displayed.</span></span>
  
![設定分析選項](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="c33b0-111">**近乎重複的電子郵件執行緒**如果您想要執行分析，請選取此方塊。</span><span class="sxs-lookup"><span data-stu-id="c33b0-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="c33b0-112">此為預設選取的選項。</span><span class="sxs-lookup"><span data-stu-id="c33b0-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="c33b0-113">**檔相似性**輸入接近重複的臨界值或接受預設值65%。</span><span class="sxs-lookup"><span data-stu-id="c33b0-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="c33b0-114">**主題**選取此方塊以處理所有檔案，並為其指定主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="c33b0-115">預設不會選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c33b0-115">By default, this check box is not selected.</span></span> <span data-ttu-id="c33b0-116">如果您想要執行主題處理，請輸入下列選項。</span><span class="sxs-lookup"><span data-stu-id="c33b0-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="c33b0-117">**主題數目上限**輸入或選取要建立的主題數目值。</span><span class="sxs-lookup"><span data-stu-id="c33b0-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="c33b0-118">預設值為 200。</span><span class="sxs-lookup"><span data-stu-id="c33b0-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c33b0-119">增加主題數目會影響效能，以及將主題的功能歸納為一般化。</span><span class="sxs-lookup"><span data-stu-id="c33b0-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="c33b0-120">主題的數量越高，其程度就越細微。</span><span class="sxs-lookup"><span data-stu-id="c33b0-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="c33b0-121">例如，如果一組50主題包含 "籃球，Spurs，Clippers，Lakers" 等主題，則300主題可以包含不同的主題： "Spurs"、"Clippers"、"Lakers"。</span><span class="sxs-lookup"><span data-stu-id="c33b0-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="c33b0-122">如果您不知道主題「籃球」，並將此功能用於 ECA，請參閱主題「籃球」會非常有用。</span><span class="sxs-lookup"><span data-stu-id="c33b0-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="c33b0-123">不過，如果處理過程中有太多主題，您可能永遠看不到「籃球」一詞，也可能不知道 Spurs 及 Clippers 是好的籃球主題可供審閱，而不是在開始時和用於頭髮的專案。</span><span class="sxs-lookup"><span data-stu-id="c33b0-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="c33b0-124">**建議主題**您可以建議主題文字，以控制主題處理。</span><span class="sxs-lookup"><span data-stu-id="c33b0-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="c33b0-125">「高級 eDiscovery」會將重點放在這些建議的文字上，並根據「主題最大數目」設定，嘗試建立一個或多個相關主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="c33b0-126">例如，如果建議的字為 "computer"，而您指定 "2" 做為「主題的最大數目」，則高級 eDiscovery 會嘗試產生與「電腦」有關的兩個主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="c33b0-127">例如，這兩個主題可能是 "電腦軟體" 和 "電腦硬體"。</span><span class="sxs-lookup"><span data-stu-id="c33b0-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![新增建議的佈景主題](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="c33b0-129">若要查看、新增或編輯建議的主題，請按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="c33b0-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="c33b0-130">在 [**建議的主題**] 面板中，按一下 [**新增** ![ 加入圖示] ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 圖示以新增主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="c33b0-131">在 [**新增建議的主題**] 面板中，加入以逗號分隔的字。</span><span class="sxs-lookup"><span data-stu-id="c33b0-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="c33b0-132">在 [**主題數目**] 中，選取一個值，以決定「主題」高級 eDiscovery 將嘗試為這些字詞產生的數目（預設為1個主題）。</span><span class="sxs-lookup"><span data-stu-id="c33b0-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="c33b0-133">按一下 [**儲存**]，然後關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c33b0-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c33b0-134">主題的總數包含建議的主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="c33b0-135">建議的主題總數不能超過整個主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="c33b0-136">如果有許多相對於整個主題的建議主題，系統只會偵測到一些「novel」主題，因為大多數主題都會專用於建議的主題。</span><span class="sxs-lookup"><span data-stu-id="c33b0-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="c33b0-137">**模式**從下拉式清單中，選取 [**主題**] 選項：</span><span class="sxs-lookup"><span data-stu-id="c33b0-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="c33b0-138">**建立及套用模型**：從一段檔的模型計算主題，然後在這些檔案之間散佈檔。</span><span class="sxs-lookup"><span data-stu-id="c33b0-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="c33b0-139">**建立模型**：計算來自一段檔的主題模型。</span><span class="sxs-lookup"><span data-stu-id="c33b0-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="c33b0-140">[套用分割檔] 的處理常式會個別于另一次完成。</span><span class="sxs-lookup"><span data-stu-id="c33b0-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="c33b0-141">套用**模型**：只有在先前建立的模型和尚未套用的模型時，才會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="c33b0-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="c33b0-142">這會根據主題來分割檔案。</span><span class="sxs-lookup"><span data-stu-id="c33b0-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="c33b0-143">您也可以[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)，並設定分析的 [[分析高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)]。</span><span class="sxs-lookup"><span data-stu-id="c33b0-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="c33b0-144">在您設定這些選項之後，請按一下 [**分析**] 以執行。</span><span class="sxs-lookup"><span data-stu-id="c33b0-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="c33b0-145">顯示 [ [View 分析結果](view-analyze-results-in-advanced-ediscovery.md)]。</span><span class="sxs-lookup"><span data-stu-id="c33b0-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c33b0-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="c33b0-146">Related topics</span></span>

[<span data-ttu-id="c33b0-147">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="c33b0-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c33b0-148">瞭解檔相似性</span><span class="sxs-lookup"><span data-stu-id="c33b0-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c33b0-149">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="c33b0-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c33b0-150">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="c33b0-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c33b0-151">View 分析結果</span><span class="sxs-lookup"><span data-stu-id="c33b0-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

