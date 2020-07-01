---
title: 在 [高級 eDiscovery] 中設定 [忽略文字] 選項以進行分析
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 瞭解如何在使用高級 eDiscovery 中的 [分析與處理模組時，定義規則以忽略特定文字]。
ms.openlocfilehash: fd7b1f3236c88faf792a97146bbed35802f6c695
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936890"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a><span data-ttu-id="9353b-103">設定 [忽略文字] 選項，以在高級 eDiscovery （古典）中進行分析</span><span class="sxs-lookup"><span data-stu-id="9353b-103">Set Ignore Text option for Analyze in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="9353b-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="9353b-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="9353b-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="9353b-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="9353b-106">[忽略文字] 功能可以套用到下列所有或任何的高級 eDiscovery 模組：分析（近乎重複的電子郵件執行緒、主題）及相關性。</span><span class="sxs-lookup"><span data-stu-id="9353b-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="9353b-107">「相關性」顯示的檔案中不會顯示忽略的文字，而且分析/計算會捨棄忽略的文字。</span><span class="sxs-lookup"><span data-stu-id="9353b-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="9353b-108">如果先前已經為已執行的模組定義 [忽略文字] 功能，則 [忽略文字] 設定現在會受到保護，無法進行修改。</span><span class="sxs-lookup"><span data-stu-id="9353b-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="9353b-109">不過，相關性模組的 [忽略文字] 功能仍可在任何時間變更。</span><span class="sxs-lookup"><span data-stu-id="9353b-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="9353b-110">如何套用 Ignore 文字篩選</span><span class="sxs-lookup"><span data-stu-id="9353b-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="9353b-111">多個 Ignore Text 篩選依輸入的順序套用。</span><span class="sxs-lookup"><span data-stu-id="9353b-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="9353b-112">若要變更套用的順序，必須將它們刪除並以所需的順序重新輸入。</span><span class="sxs-lookup"><span data-stu-id="9353b-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="9353b-113">例如，如果文字內容是：「DAVE 小明小紅 CAROL 前夕」，下列為 Ignore Text entries 和 results 的範例：</span><span class="sxs-lookup"><span data-stu-id="9353b-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9353b-114">**忽略文字專案**</span><span class="sxs-lookup"><span data-stu-id="9353b-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="9353b-115">**Results**</span><span class="sxs-lookup"><span data-stu-id="9353b-115">**Results**</span></span> <br/> |
|<span data-ttu-id="9353b-116">"ALICE"，"小明 CAROL"</span><span class="sxs-lookup"><span data-stu-id="9353b-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="9353b-117">"DAVE 前夕"</span><span class="sxs-lookup"><span data-stu-id="9353b-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="9353b-118">"ALICE"，"小明 ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="9353b-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="9353b-119">"DAVE 小明 CAROL 前夕"</span><span class="sxs-lookup"><span data-stu-id="9353b-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="9353b-120">第二個 Ignore Text 專案並未執行，因為在套用第一個 Ignore 文字之後，就不會找到該字串。</span><span class="sxs-lookup"><span data-stu-id="9353b-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="9353b-121">定義忽略文字時使用正則運算式</span><span class="sxs-lookup"><span data-stu-id="9353b-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="9353b-122">定義 Ignore Text 時，支援使用正則運算式。</span><span class="sxs-lookup"><span data-stu-id="9353b-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="9353b-123">以下是正則運算式語法和用法的範例：</span><span class="sxs-lookup"><span data-stu-id="9353b-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="9353b-124">若要移除（ignore）文字，直到行尾為止：</span><span class="sxs-lookup"><span data-stu-id="9353b-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="9353b-125">其中，"Begin" 是此字串在該行中的初始出現次數。</span><span class="sxs-lookup"><span data-stu-id="9353b-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="9353b-126">例如，下列文字：</span><span class="sxs-lookup"><span data-stu-id="9353b-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="9353b-127">**這是第一個句子和第一行**</span><span class="sxs-lookup"><span data-stu-id="9353b-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="9353b-128">**這是第二個句子和第二行 "**</span><span class="sxs-lookup"><span data-stu-id="9353b-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="9353b-129">正則運算式 first （. \* ）$ 會產生：</span><span class="sxs-lookup"><span data-stu-id="9353b-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="9353b-130">**「這是**</span><span class="sxs-lookup"><span data-stu-id="9353b-130">**"This is**</span></span>
    
    <span data-ttu-id="9353b-131">**這是第二個句子和第二行 "**</span><span class="sxs-lookup"><span data-stu-id="9353b-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="9353b-132">若要移除在電子郵件執行緒結束時自動插入免責聲明和法律陳述：</span><span class="sxs-lookup"><span data-stu-id="9353b-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="9353b-133">其中，「開始」和「結束」是換行文欄位落的開頭和結尾的唯一字串。</span><span class="sxs-lookup"><span data-stu-id="9353b-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="9353b-134">例如，下列正則運算式將移除電子郵件執行緒中的開始和結束字串之間的免責聲明和法律聲明：</span><span class="sxs-lookup"><span data-stu-id="9353b-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="9353b-135">**此郵件包含機密資訊（. |\s） \* 如果需要驗證，請要求硬拷貝版本**</span><span class="sxs-lookup"><span data-stu-id="9353b-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="9353b-136">若要移除免責聲明（包括特殊字元）：</span><span class="sxs-lookup"><span data-stu-id="9353b-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="9353b-137">例如，下列文字（由 x 所代表的免責聲明）：</span><span class="sxs-lookup"><span data-stu-id="9353b-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="9353b-138">**/\*\ 此郵件包含機密資訊。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="9353b-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="9353b-139">**xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="9353b-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="9353b-140">\**xxxx xxxx 如果需要驗證，請要求硬拷貝版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="9353b-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="9353b-141">移除上述免責聲明的正則運算式應該是：</span><span class="sxs-lookup"><span data-stu-id="9353b-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="9353b-142">**\/\\*\\此郵件包含機密資訊 \. （. |\s） \* 如果需要驗證，請要求硬拷貝版本 \.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="9353b-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="9353b-143">正則運算式規則：</span><span class="sxs-lookup"><span data-stu-id="9353b-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="9353b-144">除了空格、"_" 和 "-" 以外的字母表以外的任何字元，都必須加上 " \" 。</span><span class="sxs-lookup"><span data-stu-id="9353b-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="9353b-145">一般 eExpression 欄位可以是無限長度。</span><span class="sxs-lookup"><span data-stu-id="9353b-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="9353b-146">如需正則運算式的說明和詳細語法，請參閱：[正則運算式語言-快速參考](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9353b-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="9353b-147">定義忽略文字規則</span><span class="sxs-lookup"><span data-stu-id="9353b-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="9353b-148">在 [**管理 \> 分析 \> 分析選項**] 索引標籤的 [**忽略文字**] 區段中，按一下 **+** 圖示以新增規則。</span><span class="sxs-lookup"><span data-stu-id="9353b-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="9353b-149">在 [**新增忽略文字**] 對話方塊的 [**名稱**] 欄位中，輸入 Ignore Text 規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="9353b-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![加入略過的文字](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="9353b-151">在**文字方塊**中，輸入要忽略的文字。</span><span class="sxs-lookup"><span data-stu-id="9353b-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="9353b-152">Text 欄位允許無限制數目的字元。</span><span class="sxs-lookup"><span data-stu-id="9353b-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9353b-153">如上表所示 **，按一下 [** 略過] 以查看 [忽略文字規則] 的常見語法指導方針。</span><span class="sxs-lookup"><span data-stu-id="9353b-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="9353b-154">如有需要，請選取 [**區分大小寫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9353b-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="9353b-155">在 [套用**至**] 清單中，選取要套用定義的高級 eDiscovery 模組。</span><span class="sxs-lookup"><span data-stu-id="9353b-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="9353b-156">如果您想要測試執行樣本文字，請在 [**輸入**] 文字方塊中輸入範例文字，然後按一下 [**測試**]。</span><span class="sxs-lookup"><span data-stu-id="9353b-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="9353b-157">結果會顯示在 [**輸出**] 文字方塊中。</span><span class="sxs-lookup"><span data-stu-id="9353b-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="9353b-158">按一下 **[確定]** 以儲存 [忽略文字] 規則。</span><span class="sxs-lookup"><span data-stu-id="9353b-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="9353b-159">已定義的 Ignore 文字規則隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="9353b-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![設定忽略文字名稱](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="9353b-161">請參閱</span><span class="sxs-lookup"><span data-stu-id="9353b-161">See also</span></span>

[<span data-ttu-id="9353b-162">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="9353b-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9353b-163">瞭解檔相似性</span><span class="sxs-lookup"><span data-stu-id="9353b-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9353b-164">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="9353b-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9353b-165">設定分析高級設定</span><span class="sxs-lookup"><span data-stu-id="9353b-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9353b-166">查看分析結果</span><span class="sxs-lookup"><span data-stu-id="9353b-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

