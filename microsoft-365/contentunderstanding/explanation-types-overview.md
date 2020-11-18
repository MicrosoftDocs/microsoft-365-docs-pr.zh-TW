---
title: 說明類型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 深入了解 Microsoft SharePoint Syntex 中的說明類型
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087640"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="3b2f9-103">說明類型簡介</span><span class="sxs-lookup"><span data-stu-id="3b2f9-103">Introduction to explanation types</span></span>

<span data-ttu-id="3b2f9-p101">說明可用來協助您定義要在 Microsoft SharePoint Syntex 中於您的文件瞭解模型中標記及摘錄的資訊。建立說明時，您必須選取說明類型。本文協助您了解不同的說明類型及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p101">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex. When creating an explanation, you need to select an explanation type. This article helps you understand the different explanation types and how they are used.</span></span> 

   ![說明類型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="3b2f9-108">以下為可用的說明類型：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-108">These explanation types are available:</span></span>

- <span data-ttu-id="3b2f9-p102">**片語清單**：您可以在要摘錄的文件或資訊中使用的單字、片語、數字或其他字元的清單。例如，文字字串 **轉診醫生** 在所有您要識別的「醫療轉診」文件中。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p102">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting. For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="3b2f9-p103">**模式清單**：列出可用來識別您要摘錄的資訊之數字、字母或其他字元的模式。例如，您可以從所有要識別的「醫療轉診」文件中，摘錄轉診醫生的 **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p103">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting. For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="3b2f9-p104">**鄰近**：描述說明彼此之間的相近程度。例如，*街道號碼* 模式清單在 *街道名稱* 片語清單之前，而中間沒有權杖 (您將在本文後面了解權杖)。使用鄰近類型時，要求在您的模型中至少有兩個說明，否則將停用該選項。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p104">**Proximity**: Describes how close explanations are to each other. For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article). Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="3b2f9-116">片語清單</span><span class="sxs-lookup"><span data-stu-id="3b2f9-116">Phrase list</span></span>

<span data-ttu-id="3b2f9-p105">片語清單說明類型通常是用來透過您的模型來識別和分類文件。如 *轉診醫生* 標籤範例中所述，它是在您要識別的文件中一致的單字、片語、數字或字元之字串。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p105">A phrase list explanation type is typically used to identify and classify a document through your model. As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="3b2f9-p106">雖然這不是一項要求，但如果您要擷取的片語位於文件中的一致位置，則可以經由說明來達到更好的成功。例如，*轉診醫生* 標籤可能會一致地位於文件的第一個段落。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p106">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document. For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="3b2f9-121">如果識別標籤時要求區分大小寫，使用片語清單類型可讓您在說明中加以指定，方法是選取 [僅完全符合大寫 **]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![區分大小寫](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="3b2f9-123">模式清單</span><span class="sxs-lookup"><span data-stu-id="3b2f9-123">Pattern lists</span></span>

<span data-ttu-id="3b2f9-p107">建立可識別及摘錄文件中資訊的說明時，模式清單類型特別實用。它通常會以不同的格式呈現，例如日期、電話號碼和信用卡號碼。例如，日期可以以許多不同的格式顯示 (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1,2020 等)。定義模式清單可讓您的說明更有效率，方法是擷取您想要識別及摘錄資料中的任何可能變化。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p107">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document. It is typically presented in different formats, such as dates, phone numbers, and credit card numbers. For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.). Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="3b2f9-p108">針對 **電話號碼** 範例，則會從模型識別的所有「醫療轉診」文件中，摘錄每位轉診醫生的電話號碼。建立說明時，請選取 [模式清單] 類型，以允許您預期傳回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p108">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies. When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話號碼模式清單](../media/content-understanding/pattern-list.png)

<span data-ttu-id="3b2f9-131">在這個範例中，請選取 **從 0 至 9 的任何數字**，核取方塊，以將模式清單中使用的每個「0」值，識別為 0 到 9 之間的任何數字。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![從 0 至 9 的任何數字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="3b2f9-133">同樣地，如果您建立包含文字字元的模式清單，請選取 **從 a 至 z 的任何字母** 核取方塊，以將模式清單中使用的每個「a」字元，識別為「a」到「z」的任何字元。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="3b2f9-134">例如，如果您建立 **日期** 模式清單，而您想要確認例如 *Jan 1, 2020* 的日期格式可被識別，您必須：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="3b2f9-135">將 *aaa 0, 0000* 和 *aaa 00, 0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3b2f9-136">確認您也已選取 [從 a-z 的任何字母 **]**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![從 a-z 的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="3b2f9-p109">此外，如果您在模式清單中有大小寫需求，則會有選項可選取 [僅完全符合大寫 **]** 核取方塊。對於日期範例，如果您需要月份的第一個字母為大寫，您必須：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p109">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox. For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="3b2f9-140">將 *Aaa 0, 0000* 和 *Aaa 00, 0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3b2f9-141">確認也選取 [僅完全符合大寫 **]**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![僅完全符合大寫](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="3b2f9-143">不要手動建立模式清單說明，而是使用 [說明文件庫](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) (英文) 來使用針對常見模式清單的模式清單範本，例如 *日期*、*電話號碼*、*信用卡號碼* 等等。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="3b2f9-144">鄰近</span><span class="sxs-lookup"><span data-stu-id="3b2f9-144">Proximity</span></span> 

<span data-ttu-id="3b2f9-p110">鄰近說明類型可協助您的模型識別資料，方法是透過定義另一個資料片段與其相似程度。例如，在您的模型中，您定義了兩個說明，分別標記客戶的 *街道地址號碼* 和 *電話號碼*。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p110">The proximity explanation type helps your model identify data by defining how close another piece of data is to it. For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="3b2f9-147">請注意，客戶的電話號碼永遠都出現在街道地址號碼的前面。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="3b2f9-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="3b2f9-148">Alex Wilburn</span></span><br>
<span data-ttu-id="3b2f9-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="3b2f9-149">555-555-5555</span></span><br>
<span data-ttu-id="3b2f9-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3b2f9-150">One Microsoft Way</span></span><br>
<span data-ttu-id="3b2f9-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3b2f9-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3b2f9-152">使用鄰近說明來定義電話號碼說明的距離，以便更好地識別文件中的街道地址號碼。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![鄰近說明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="3b2f9-154">什麼是權杖？</span><span class="sxs-lookup"><span data-stu-id="3b2f9-154">What are tokens?</span></span>

<span data-ttu-id="3b2f9-p111">若要使用鄰近說明類型，您需要瞭解權杖的含義，因為權杖的編號是鄰近說明測量一個說明與另一個說明之間距離的方式。權杖是字母和數字的連續範圍 (不含空格或標點符號)。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p111">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another. A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="3b2f9-157">下表顯示如何判斷片語中權杖數目的範例。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="3b2f9-158">片語</span><span class="sxs-lookup"><span data-stu-id="3b2f9-158">Phrase</span></span>|<span data-ttu-id="3b2f9-159">權杖數目</span><span class="sxs-lookup"><span data-stu-id="3b2f9-159">Number of tokens</span></span>|<span data-ttu-id="3b2f9-160">說明</span><span class="sxs-lookup"><span data-stu-id="3b2f9-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="3b2f9-161">1</span><span class="sxs-lookup"><span data-stu-id="3b2f9-161">1</span></span>|<span data-ttu-id="3b2f9-162">沒有標點符號或空格的單字。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="3b2f9-163">1</span><span class="sxs-lookup"><span data-stu-id="3b2f9-163">1</span></span>|<span data-ttu-id="3b2f9-p112">訂位紀錄代號。其中可能含有數字和字母，但沒有標點符號。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p112">A record locator number. It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="3b2f9-166">5</span><span class="sxs-lookup"><span data-stu-id="3b2f9-166">5</span></span>|<span data-ttu-id="3b2f9-p113">電話號碼。每個標點符號都是單一權杖，因此 `425-555-5555` 會是 5 個權杖：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p113">A phone number. Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="3b2f9-169">7</span><span class="sxs-lookup"><span data-stu-id="3b2f9-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="3b2f9-170">設定鄰近說明類型</span><span class="sxs-lookup"><span data-stu-id="3b2f9-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="3b2f9-p114">針對此範例，請設定鄰近設定，以定義來自 *街道地址號碼* 說明的 *電話號碼* 說明之權杖數目的範圍。請注意，最小範圍為「0」，因為電話號碼和街道地址號碼之間沒有權杖。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p114">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation. Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="3b2f9-173">但範例文件中的部分電話號碼會附加 *(行動電話)*。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="3b2f9-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="3b2f9-174">Nestor Wilke</span></span><br>
<span data-ttu-id="3b2f9-175">111-111-1111 (行動電話)</span><span class="sxs-lookup"><span data-stu-id="3b2f9-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="3b2f9-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3b2f9-176">One Microsoft Way</span></span><br>
<span data-ttu-id="3b2f9-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3b2f9-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3b2f9-178">*(行動裝置)* 中有三個權杖：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="3b2f9-179">片語</span><span class="sxs-lookup"><span data-stu-id="3b2f9-179">Phrase</span></span>|<span data-ttu-id="3b2f9-180">權杖計數</span><span class="sxs-lookup"><span data-stu-id="3b2f9-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="3b2f9-181">(</span><span class="sxs-lookup"><span data-stu-id="3b2f9-181">(</span></span>|<span data-ttu-id="3b2f9-182">1</span><span class="sxs-lookup"><span data-stu-id="3b2f9-182">1</span></span>|
|<span data-ttu-id="3b2f9-183">行動電話</span><span class="sxs-lookup"><span data-stu-id="3b2f9-183">mobile</span></span>|<span data-ttu-id="3b2f9-184">2</span><span class="sxs-lookup"><span data-stu-id="3b2f9-184">2</span></span>|
|<span data-ttu-id="3b2f9-185">)</span><span class="sxs-lookup"><span data-stu-id="3b2f9-185">)</span></span>|<span data-ttu-id="3b2f9-186">3</span><span class="sxs-lookup"><span data-stu-id="3b2f9-186">3</span></span>|

<span data-ttu-id="3b2f9-187">將鄰近設定設為範圍 0 到 3。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![鄰近範例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="3b2f9-189">使用說明範本</span><span class="sxs-lookup"><span data-stu-id="3b2f9-189">Use explanation templates</span></span>

<span data-ttu-id="3b2f9-190">雖然您可以為您的說明手動新增各種模式清單值，但使用說明文件庫中所提供的範本會輕鬆得多。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="3b2f9-191">例如，不要手動新增 *日期* 的所有變化，而是可以使用 *日期* 的模式清單範本，因為其中已包含一些模式清單值：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![說明文件庫](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="3b2f9-193">說明文件庫包含常用的模式清單說明，包括：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="3b2f9-194">日期</span><span class="sxs-lookup"><span data-stu-id="3b2f9-194">Date</span></span></br>
- <span data-ttu-id="3b2f9-195">日期 (數字)</span><span class="sxs-lookup"><span data-stu-id="3b2f9-195">Date (numeric)</span></span></br>
- <span data-ttu-id="3b2f9-196">時間</span><span class="sxs-lookup"><span data-stu-id="3b2f9-196">Time</span></span></br>
- <span data-ttu-id="3b2f9-197">數字</span><span class="sxs-lookup"><span data-stu-id="3b2f9-197">Number</span></span></br>
- <span data-ttu-id="3b2f9-198">電話號碼</span><span class="sxs-lookup"><span data-stu-id="3b2f9-198">Phone number</span></span></br>
- <span data-ttu-id="3b2f9-199">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="3b2f9-199">Zip code</span></span></br>
- <span data-ttu-id="3b2f9-200">句子的第一個單字</span><span class="sxs-lookup"><span data-stu-id="3b2f9-200">First word of sentence</span></span></br>
- <span data-ttu-id="3b2f9-201">信用卡</span><span class="sxs-lookup"><span data-stu-id="3b2f9-201">Credit card</span></span></br>
- <span data-ttu-id="3b2f9-202">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3b2f9-202">Social security number</span></span></br>

<span data-ttu-id="3b2f9-203">請注意，說明文件庫也包含用於片語清單說明的範本：</span><span class="sxs-lookup"><span data-stu-id="3b2f9-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="3b2f9-204">句子結尾</span><span class="sxs-lookup"><span data-stu-id="3b2f9-204">End of sentence</span></span>
- <span data-ttu-id="3b2f9-205">貨幣</span><span class="sxs-lookup"><span data-stu-id="3b2f9-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="3b2f9-206">使用來自說明文件庫的範本</span><span class="sxs-lookup"><span data-stu-id="3b2f9-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="3b2f9-207">從模型 [訓練 **]** 頁面的 [說明 **]** 區段，選取 [新增 **]**，然後選取 [從範本 **]**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![從範本建立](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="3b2f9-209">在 [說明範本 **]** 頁面上，選取您要使用的說明，然後選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![選取範本](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="3b2f9-p115">您選取的範本資訊會顯示在 [建立說明 **]** 頁面上。視需要編輯說明名稱，然後從模式清單新增或移除項目。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-p115">The information for the template you selected displays on the **Create an explanation** page. If needed, edit the explanation name and add or remove items from the pattern list. </span></span></br> 

   ![編輯範本](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="3b2f9-214">完成後，選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="3b2f9-214">When finished, select **Save**.</span></span>
