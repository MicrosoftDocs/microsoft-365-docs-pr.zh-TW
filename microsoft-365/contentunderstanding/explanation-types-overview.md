---
title: 釋義類型
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft SharePoint Syntex 中的說明類型
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295770"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="fbefd-103">說明類型簡介</span><span class="sxs-lookup"><span data-stu-id="fbefd-103">Introduction to explanation types</span></span>

<span data-ttu-id="fbefd-104">使用說明來協助您定義要標籤的資訊，並在檔中解壓縮 Microsoft SharePoint Syntex 的知識模型。</span><span class="sxs-lookup"><span data-stu-id="fbefd-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="fbefd-105">當您建立說明時，請務必選取 [說明] 類型。</span><span class="sxs-lookup"><span data-stu-id="fbefd-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="fbefd-106">本文可協助您瞭解不同的說明類型及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="fbefd-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![釋義類型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="fbefd-108">可供使用的說明類型如下：</span><span class="sxs-lookup"><span data-stu-id="fbefd-108">These explanation types are available:</span></span>

- <span data-ttu-id="fbefd-109">**片語清單**：您可以在檔中使用的單字、片語、數位或其他字元的清單，或是您要解壓縮的資訊。</span><span class="sxs-lookup"><span data-stu-id="fbefd-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="fbefd-110">例如，文字字串 **引用位址** 是指您所識別的所有醫學參考檔。</span><span class="sxs-lookup"><span data-stu-id="fbefd-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="fbefd-111">[**模式] 清單**：列出數位、字母或其他字元的模式，您可以用來識別要解壓縮的資訊。</span><span class="sxs-lookup"><span data-stu-id="fbefd-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="fbefd-112">例如，您可以從所識別的所有醫學參考檔中，解開參考醫生的 **電話號碼** 。</span><span class="sxs-lookup"><span data-stu-id="fbefd-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="fbefd-113">**鄰近**性：說明彼此的接近說明。</span><span class="sxs-lookup"><span data-stu-id="fbefd-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="fbefd-114">例如，[街道 *號碼* 模式] 清單會在 [ *街道名稱* 片語] 清單的前面，而不是在 (您會瞭解本文稍後的標記) 中。</span><span class="sxs-lookup"><span data-stu-id="fbefd-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="fbefd-115">片語清單</span><span class="sxs-lookup"><span data-stu-id="fbefd-115">Phrase list</span></span>

<span data-ttu-id="fbefd-116">片語清單釋義類型通常是用來透過您的模型來識別和分類檔。</span><span class="sxs-lookup"><span data-stu-id="fbefd-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="fbefd-117">如 [ *引用位址* ] 標籤範例所述，它是您所識別檔中一致的文字、片語、數位或字元字串。</span><span class="sxs-lookup"><span data-stu-id="fbefd-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="fbefd-118">如果您所要取得的片語位於您的檔中一致的位置，您可以使用您的說明取得更好的成功。</span><span class="sxs-lookup"><span data-stu-id="fbefd-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="fbefd-119">例如，「 *引用位址* 」標籤可能一致地位於檔的第一個段落中。</span><span class="sxs-lookup"><span data-stu-id="fbefd-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="fbefd-120">如果識別標籤需要區分大小寫，則使用片語清單類型可讓您選取 **唯一的確切大小寫** 核取方塊，以在您的說明中指定。</span><span class="sxs-lookup"><span data-stu-id="fbefd-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![區分大小寫](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="fbefd-122">模式清單</span><span class="sxs-lookup"><span data-stu-id="fbefd-122">Pattern lists</span></span>

<span data-ttu-id="fbefd-123">當您建立說明，識別及提取檔中的資訊時，模式清單類型特別有用。</span><span class="sxs-lookup"><span data-stu-id="fbefd-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="fbefd-124">它通常會以不同的格式顯示，例如日期、電話號碼或信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="fbefd-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="fbefd-125">例如，可以使用不同的格式來顯示日期， (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="fbefd-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="fbefd-126">透過在您嘗試識別及解壓縮的資料中取得任何可能的變化，以定義 [模式] 清單，可讓您的說明更有效率。</span><span class="sxs-lookup"><span data-stu-id="fbefd-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="fbefd-127">在 [ **電話號碼** ] 範例中，從模型所識別的所有醫療參考檔中，抽出每一位參考醫生的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fbefd-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="fbefd-128">當您建立說明時，請選取 [模式] 清單類型以允許您預期傳回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="fbefd-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話號碼模式清單](../media/content-understanding/pattern-list.png)

<span data-ttu-id="fbefd-130">在此範例中，選取 [ **0-9 中的任何數位** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fbefd-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="fbefd-131">選取此項會將您的模式清單中所使用的每個「0」值都識別為從0到9的任何數位。</span><span class="sxs-lookup"><span data-stu-id="fbefd-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0-9 的任何數位](../media/content-understanding/digit-identity.png)

<span data-ttu-id="fbefd-133">同樣地，如果您建立包含文字字元的 [模式] 清單，請選取 [a-z] 核取方塊 **中的任何字母** 。</span><span class="sxs-lookup"><span data-stu-id="fbefd-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="fbefd-134">選取這種方式可辨識 pattern 清單中所用的每一個 "a" 字元，是從 "a" 到 "z" 的任何字元。</span><span class="sxs-lookup"><span data-stu-id="fbefd-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="fbefd-135">例如，如果您建立一個 **日期** 模式清單，而您想確定日期格式（例如 *1 月1日）* 可辨識為2020，您必須：</span><span class="sxs-lookup"><span data-stu-id="fbefd-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="fbefd-136">將 *aaa 0、0000* 和 *aaa 00，0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="fbefd-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="fbefd-137">請確定也選取 **了 a-z 中的任何字母** 。</span><span class="sxs-lookup"><span data-stu-id="fbefd-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A-z 中的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="fbefd-139">此外，如果您在 [您的模式] 清單中有大小寫需求，您可以選擇 **僅完全符合大小寫** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fbefd-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="fbefd-140">在日期範例中，如果您需要將月份的第一個字母大寫，您必須：</span><span class="sxs-lookup"><span data-stu-id="fbefd-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="fbefd-141">將 *Aaa 0、0000* 和 *Aaa 00，0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="fbefd-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="fbefd-142">請確定也 **只會選取完全大寫** 。</span><span class="sxs-lookup"><span data-stu-id="fbefd-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![只完全符合大小寫](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="fbefd-144">除了手動建立模式清單說明之外，您也可以使用 [說明] 連結 [庫]() ，針對一般模式清單（例如 *日期*、 *電話號碼*、 *信用卡號碼*等）使用預先進行的模式清單範本。</span><span class="sxs-lookup"><span data-stu-id="fbefd-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="fbefd-145">近似性</span><span class="sxs-lookup"><span data-stu-id="fbefd-145">Proximity</span></span> 

<span data-ttu-id="fbefd-146">「鄰近性說明類型可協助您的模型定義另一個資料的接近程度，以識別資料。</span><span class="sxs-lookup"><span data-stu-id="fbefd-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="fbefd-147">例如，在模型中，您已定義兩個說明，用以標示客戶的 *街道位址號碼* 和 *電話號碼*。</span><span class="sxs-lookup"><span data-stu-id="fbefd-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="fbefd-148">此外，您也會注意到客戶的電話號碼一定會出現在街道位址號碼之前。</span><span class="sxs-lookup"><span data-stu-id="fbefd-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="fbefd-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="fbefd-149">Alex Wilburn</span></span><br>
<span data-ttu-id="fbefd-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="fbefd-150">555-555-5555</span></span><br>
<span data-ttu-id="fbefd-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="fbefd-151">One Microsoft Way</span></span><br>
<span data-ttu-id="fbefd-152">Redmond，WA 98034</span><span class="sxs-lookup"><span data-stu-id="fbefd-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="fbefd-153">使用「鄰近性說明」來定義電話號碼說明的距離，以更好地識別檔中的街道位址號碼。</span><span class="sxs-lookup"><span data-stu-id="fbefd-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![鄰近性說明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="fbefd-155">何謂標記？</span><span class="sxs-lookup"><span data-stu-id="fbefd-155">What are tokens?</span></span>

<span data-ttu-id="fbefd-156">若要使用鄰近性說明類型，請瞭解 token 的含義，因為標記的數目就是近程說明如何測量對另一個說明之間的距離。</span><span class="sxs-lookup"><span data-stu-id="fbefd-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="fbefd-157">Token 是連續的 span (不會有空格或標點符號) 字母和數位。</span><span class="sxs-lookup"><span data-stu-id="fbefd-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="fbefd-158">空格不是標記。</span><span class="sxs-lookup"><span data-stu-id="fbefd-158">A space is NOT a token.</span></span> <span data-ttu-id="fbefd-159">每個標點符號都是一個標記符。</span><span class="sxs-lookup"><span data-stu-id="fbefd-159">Each punctuation character is a token.</span></span> <span data-ttu-id="fbefd-160">下表顯示如何決定片語中的標記數目的一些範例。</span><span class="sxs-lookup"><span data-stu-id="fbefd-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="fbefd-161">短語</span><span class="sxs-lookup"><span data-stu-id="fbefd-161">Phrase</span></span>|<span data-ttu-id="fbefd-162">標記數目</span><span class="sxs-lookup"><span data-stu-id="fbefd-162">Number of tokens</span></span>|<span data-ttu-id="fbefd-163">說明</span><span class="sxs-lookup"><span data-stu-id="fbefd-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="fbefd-164">1 </span><span class="sxs-lookup"><span data-stu-id="fbefd-164">1</span></span>|<span data-ttu-id="fbefd-165">單一單字沒有標點符號或空格。</span><span class="sxs-lookup"><span data-stu-id="fbefd-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="fbefd-166">1 </span><span class="sxs-lookup"><span data-stu-id="fbefd-166">1</span></span>|<span data-ttu-id="fbefd-167">記錄定位器編號。</span><span class="sxs-lookup"><span data-stu-id="fbefd-167">A record locator number.</span></span> <span data-ttu-id="fbefd-168">它可能會有數位和字母，但沒有任何標點。</span><span class="sxs-lookup"><span data-stu-id="fbefd-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="fbefd-169">5 </span><span class="sxs-lookup"><span data-stu-id="fbefd-169">5</span></span>|<span data-ttu-id="fbefd-170">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fbefd-170">A phone number.</span></span> <span data-ttu-id="fbefd-171">每個標點符號都是單一標記，所以  `425-555-5555` 為5個權杖：</span><span class="sxs-lookup"><span data-stu-id="fbefd-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="fbefd-172">7 </span><span class="sxs-lookup"><span data-stu-id="fbefd-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="fbefd-173">設定鄰近性釋義類型</span><span class="sxs-lookup"><span data-stu-id="fbefd-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="fbefd-174">在此範例中，設定近程設定，讓我們能夠定義 *電話號碼* 說明的標記數目的範圍（來自 *街道位址號碼* 說明）。</span><span class="sxs-lookup"><span data-stu-id="fbefd-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="fbefd-175">您應該會看到最小範圍為 "0"，因為電話號碼與街道位址號碼之間沒有任何標記。</span><span class="sxs-lookup"><span data-stu-id="fbefd-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="fbefd-176">不過，範例檔中的一些電話號碼會附加 \* (行動) \*。</span><span class="sxs-lookup"><span data-stu-id="fbefd-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="fbefd-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="fbefd-177">Nestor Wilke</span></span><br>
<span data-ttu-id="fbefd-178">111-111-1111 (mobile) </span><span class="sxs-lookup"><span data-stu-id="fbefd-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="fbefd-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="fbefd-179">One Microsoft Way</span></span><br>
<span data-ttu-id="fbefd-180">Redmond，WA 98034</span><span class="sxs-lookup"><span data-stu-id="fbefd-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="fbefd-181">\* (mobile) \*中有三個權杖：</span><span class="sxs-lookup"><span data-stu-id="fbefd-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="fbefd-182">短語</span><span class="sxs-lookup"><span data-stu-id="fbefd-182">Phrase</span></span>|<span data-ttu-id="fbefd-183">權杖計數</span><span class="sxs-lookup"><span data-stu-id="fbefd-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="fbefd-184">(</span><span class="sxs-lookup"><span data-stu-id="fbefd-184">(</span></span>|<span data-ttu-id="fbefd-185">1 </span><span class="sxs-lookup"><span data-stu-id="fbefd-185">1</span></span>|
|<span data-ttu-id="fbefd-186">移動</span><span class="sxs-lookup"><span data-stu-id="fbefd-186">mobile</span></span>|<span data-ttu-id="fbefd-187">2 </span><span class="sxs-lookup"><span data-stu-id="fbefd-187">2</span></span>|
|<span data-ttu-id="fbefd-188">)</span><span class="sxs-lookup"><span data-stu-id="fbefd-188">)</span></span>|<span data-ttu-id="fbefd-189">3 </span><span class="sxs-lookup"><span data-stu-id="fbefd-189">3</span></span>|

<span data-ttu-id="fbefd-190">將 [鄰近性] 設定設定為0到3的範圍。</span><span class="sxs-lookup"><span data-stu-id="fbefd-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![近程範例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="fbefd-192">使用說明程式庫</span><span class="sxs-lookup"><span data-stu-id="fbefd-192">Use the explanation library</span></span>

<span data-ttu-id="fbefd-193">雖然您可以手動新增各種模式清單值以供您的說明，但在說明程式庫中，使用預先建立的範本是很容易的。</span><span class="sxs-lookup"><span data-stu-id="fbefd-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="fbefd-194">例如，請使用已包含一些模式清單值的模式清單範本，而不是手動新增*日期*變化*的日期。*</span><span class="sxs-lookup"><span data-stu-id="fbefd-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![說明程式庫](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="fbefd-196">說明程式庫包含許多常用的模式清單說明，包括：</span><span class="sxs-lookup"><span data-stu-id="fbefd-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="fbefd-197">日期</span><span class="sxs-lookup"><span data-stu-id="fbefd-197">Date</span></span></br>
- <span data-ttu-id="fbefd-198">日期 (數值) </span><span class="sxs-lookup"><span data-stu-id="fbefd-198">Date (numeric)</span></span></br>
- <span data-ttu-id="fbefd-199">Time</span><span class="sxs-lookup"><span data-stu-id="fbefd-199">Time</span></span></br>
- <span data-ttu-id="fbefd-200">數字</span><span class="sxs-lookup"><span data-stu-id="fbefd-200">Number</span></span></br>
- <span data-ttu-id="fbefd-201">電話號碼</span><span class="sxs-lookup"><span data-stu-id="fbefd-201">Phone number</span></span></br>
- <span data-ttu-id="fbefd-202">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="fbefd-202">Zip code</span></span></br>
- <span data-ttu-id="fbefd-203">句子的第一個單字</span><span class="sxs-lookup"><span data-stu-id="fbefd-203">First word of sentence</span></span></br>
- <span data-ttu-id="fbefd-204">信用卡</span><span class="sxs-lookup"><span data-stu-id="fbefd-204">Credit card</span></span></br>
- <span data-ttu-id="fbefd-205">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="fbefd-205">Social security number</span></span></br>

<span data-ttu-id="fbefd-206">請注意，說明程式庫也包含片語清單說明的範本，包括：</span><span class="sxs-lookup"><span data-stu-id="fbefd-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="fbefd-207">句子結尾</span><span class="sxs-lookup"><span data-stu-id="fbefd-207">End of sentence</span></span>
- <span data-ttu-id="fbefd-208">貨幣</span><span class="sxs-lookup"><span data-stu-id="fbefd-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="fbefd-209">使用說明程式庫中的範本</span><span class="sxs-lookup"><span data-stu-id="fbefd-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="fbefd-210">從模型**訓練**頁面的 [**說明**] 區段中，選取 [**新增**]，然後選取 [**從範本**]。</span><span class="sxs-lookup"><span data-stu-id="fbefd-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![從範本建立](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="fbefd-212">在 [ **說明範本** ] 頁面上，選取您要使用的說明，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="fbefd-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![選取範本](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="fbefd-214">您所選取之範本的資訊會顯示在 [ **建立說明** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="fbefd-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="fbefd-215">如有需要，請編輯說明名稱，並在 [模式] 清單中新增或移除專案。</span><span class="sxs-lookup"><span data-stu-id="fbefd-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![編輯範本](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="fbefd-217">完成時，請選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="fbefd-217">When finished, select **Save**.</span></span>
