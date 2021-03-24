---
title: 說明類型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 深入了解 Microsoft SharePoint Syntex 中的說明類型
ms.openlocfilehash: b34de9ffc565e3d1a17cac05084e4e4b4113a3c6
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994625"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="f382f-103">說明類型簡介</span><span class="sxs-lookup"><span data-stu-id="f382f-103">Introduction to explanation types</span></span>

<span data-ttu-id="f382f-104">說明可用來協助您定義要在 Microsoft SharePoint Syntex 中於您的文件瞭解模型中加標籤及摘錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="f382f-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="f382f-105">建立說明時，您必須選取說明類型。</span><span class="sxs-lookup"><span data-stu-id="f382f-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="f382f-106">本文協助您了解不同的說明類型及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="f382f-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![說明類型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="f382f-108">以下為可用的說明類型：</span><span class="sxs-lookup"><span data-stu-id="f382f-108">These explanation types are available:</span></span>

- <span data-ttu-id="f382f-109">**片語清單**：您可以在要摘錄的文件或資訊中使用的單字、片語、數字或其他字元的清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="f382f-110">例如，文字字串 **轉診醫生** 位於所有您要識別的「醫學轉診」文件中。</span><span class="sxs-lookup"><span data-stu-id="f382f-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="f382f-111">**模式清單**：列出可用來識別您要摘錄的資訊的數字、字母或其他字元的模式。</span><span class="sxs-lookup"><span data-stu-id="f382f-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="f382f-112">例如，您可以從您要識別的所有「醫學轉診」文件中，摘錄轉診醫生的 **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="f382f-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="f382f-113">**鄰近**：描述說明彼此之間的相近程度。</span><span class="sxs-lookup"><span data-stu-id="f382f-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="f382f-114">例如，*街道號碼* 模式清單會位於 *街道名稱* 片語之前，它們之間沒有權杖 (您將在本文稍後了解權杖)。</span><span class="sxs-lookup"><span data-stu-id="f382f-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="f382f-115">使用鄰近類型時，要求在您的模型中至少有兩個說明，否則將停用該選項。</span><span class="sxs-lookup"><span data-stu-id="f382f-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="f382f-116">片語清單</span><span class="sxs-lookup"><span data-stu-id="f382f-116">Phrase list</span></span>

<span data-ttu-id="f382f-117">片語清單說明類型通常是用來透過您的模型來識別和分類文件。</span><span class="sxs-lookup"><span data-stu-id="f382f-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="f382f-118">如 *轉診醫生* 標籤範例中所述，它是在您要識別的文件中一致的單字、片語、數字或字元的字串。</span><span class="sxs-lookup"><span data-stu-id="f382f-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="f382f-119">雖然這並非一項要求，但如果您要擷取的片語位於您文件中的一致位置，則使用您的說明可以更成功。</span><span class="sxs-lookup"><span data-stu-id="f382f-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="f382f-120">例如，*轉診醫生* 標籤可能會一致地位於文件的第一個段落。</span><span class="sxs-lookup"><span data-stu-id="f382f-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="f382f-121">如果識別標籤時要求區分大小寫，使用片語清單類型可讓您在說明中加以指定，方法是選取 [僅完全符合大寫 **]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f382f-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![區分大小寫](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="f382f-123">模式清單</span><span class="sxs-lookup"><span data-stu-id="f382f-123">Pattern lists</span></span>

<span data-ttu-id="f382f-124">建立可識別及摘錄文件中資訊的說明時，模式清單類型特別實用。</span><span class="sxs-lookup"><span data-stu-id="f382f-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="f382f-125">它通常會以不同的格式呈現，例如日期、電話號碼和信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="f382f-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="f382f-126">例如，日期可以以許多不同的格式顯示 (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1,2020 等)。</span><span class="sxs-lookup"><span data-stu-id="f382f-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="f382f-127">定義模式清單可讓您的說明更有效率，方法是擷取您想要識別及摘錄的資料中的任何可能變化。</span><span class="sxs-lookup"><span data-stu-id="f382f-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="f382f-128">針對 **電話號碼** 範例，則會從模型識別的所有「醫學轉診」文件中，摘錄每位轉診醫生的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f382f-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="f382f-129">建立說明時，請選取 [模式清單] 類型，以允許您預期傳回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話號碼模式清單](../media/content-understanding/pattern-list.png)

<span data-ttu-id="f382f-131">在這個範例中，請選取 **從 0 至 9 的任何數字**，核取方塊，以將模式清單中使用的每個「0」值，識別為 0 到 9 之間的任何數字。</span><span class="sxs-lookup"><span data-stu-id="f382f-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![從 0 至 9 的任何數字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="f382f-133">同樣地，如果您建立包含文字字元的模式清單，請選取 **從 a 至 z 的任何字母** 核取方塊，以將模式清單中使用的每個「a」字元，識別為「a」到「z」的任何字元。</span><span class="sxs-lookup"><span data-stu-id="f382f-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="f382f-134">例如，如果您建立 **日期** 模式清單，而您想要確認可辨識日期格式 *Jan 1, 2020*，您必須：</span><span class="sxs-lookup"><span data-stu-id="f382f-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="f382f-135">將 *aaa 0, 0000* 和 *aaa 00, 0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="f382f-136">確認您也已選取 [從 a-z 的任何字母 **]**。</span><span class="sxs-lookup"><span data-stu-id="f382f-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![從 a-z 的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="f382f-138">此外，如果您在模式清單中有大小寫需求，則會有選項可選取 [僅完全符合大寫 **]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f382f-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="f382f-139">對於日期範例，如果您需要月份的第一個字母為大寫，您必須：</span><span class="sxs-lookup"><span data-stu-id="f382f-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="f382f-140">將 *Aaa 0, 0000* 和 *Aaa 00, 0000* 新增至您的模式清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="f382f-141">確認也選取 [僅完全符合大寫 **]**。</span><span class="sxs-lookup"><span data-stu-id="f382f-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![僅完全符合大寫](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="f382f-143">不要手動建立模式清單說明，而是使用 [說明文件庫](#use-explanation-templates) 來使用針對常見模式清單的模式清單範本，例如 *日期*、*電話號碼*、*信用卡號碼* 等等。</span><span class="sxs-lookup"><span data-stu-id="f382f-143">Instead of manually creating a pattern list explanation, use the [explanation library](#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="f382f-144">鄰近</span><span class="sxs-lookup"><span data-stu-id="f382f-144">Proximity</span></span> 

<span data-ttu-id="f382f-145">鄰近說明類型可協助您的模型識別資料，方法是透過定義另一個資料片段與其相似程度。</span><span class="sxs-lookup"><span data-stu-id="f382f-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="f382f-146">例如，在您的模型中，您定義了兩個說明，可標記客戶的 *街道地址號碼* 和 *電話號碼*。</span><span class="sxs-lookup"><span data-stu-id="f382f-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="f382f-147">請注意，客戶的電話號碼永遠都出現在街道地址的前面。</span><span class="sxs-lookup"><span data-stu-id="f382f-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="f382f-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="f382f-148">Alex Wilburn</span></span><br>
<span data-ttu-id="f382f-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="f382f-149">555-555-5555</span></span><br>
<span data-ttu-id="f382f-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="f382f-150">One Microsoft Way</span></span><br>
<span data-ttu-id="f382f-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="f382f-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="f382f-152">使用鄰近說明來定義電話號碼說明的距離，以便更好地識別文件中的街道地址號碼。</span><span class="sxs-lookup"><span data-stu-id="f382f-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![鄰近說明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="f382f-154">什麼是權杖？</span><span class="sxs-lookup"><span data-stu-id="f382f-154">What are tokens?</span></span>

<span data-ttu-id="f382f-155">若要使用鄰近說明類型，您需要瞭解權杖的含義，因為權杖的編號是鄰近說明測量一個說明與另一個說明之間距離的方式。</span><span class="sxs-lookup"><span data-stu-id="f382f-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="f382f-156">權杖是字母和數字的連續範圍 (不含空格或標點符號)。</span><span class="sxs-lookup"><span data-stu-id="f382f-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="f382f-157">下表顯示如何判斷片語中權杖數目的範例。</span><span class="sxs-lookup"><span data-stu-id="f382f-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="f382f-158">片語</span><span class="sxs-lookup"><span data-stu-id="f382f-158">Phrase</span></span>|<span data-ttu-id="f382f-159">權杖數目</span><span class="sxs-lookup"><span data-stu-id="f382f-159">Number of tokens</span></span>|<span data-ttu-id="f382f-160">說明</span><span class="sxs-lookup"><span data-stu-id="f382f-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="f382f-161">1</span><span class="sxs-lookup"><span data-stu-id="f382f-161">1</span></span>|<span data-ttu-id="f382f-162">沒有標點符號或空格的單字。</span><span class="sxs-lookup"><span data-stu-id="f382f-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="f382f-163">1</span><span class="sxs-lookup"><span data-stu-id="f382f-163">1</span></span>|<span data-ttu-id="f382f-164">記錄定位器號碼。</span><span class="sxs-lookup"><span data-stu-id="f382f-164">A record locator number.</span></span> <span data-ttu-id="f382f-165">其中可能含有數字和字母，但沒有標點符號。</span><span class="sxs-lookup"><span data-stu-id="f382f-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="f382f-166">5</span><span class="sxs-lookup"><span data-stu-id="f382f-166">5</span></span>|<span data-ttu-id="f382f-167">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f382f-167">A phone number.</span></span> <span data-ttu-id="f382f-168">每個標點符號都是單一權杖，因此 `425-555-5555` 會是 5 個權杖：</span><span class="sxs-lookup"><span data-stu-id="f382f-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="f382f-169">7</span><span class="sxs-lookup"><span data-stu-id="f382f-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="f382f-170">設定鄰近說明類型</span><span class="sxs-lookup"><span data-stu-id="f382f-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="f382f-171">針對此範例，請設定鄰近設定，以定義來自 *街道地址號碼* 說明的 *電話號碼* 說明之權杖數目的範圍。</span><span class="sxs-lookup"><span data-stu-id="f382f-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="f382f-172">請注意，最小範圍為「0」，因為電話號碼和街道地址號碼之間沒有權杖。</span><span class="sxs-lookup"><span data-stu-id="f382f-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="f382f-173">但範例文件中的部分電話號碼會附加 *(行動裝置)*。</span><span class="sxs-lookup"><span data-stu-id="f382f-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="f382f-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="f382f-174">Nestor Wilke</span></span><br>
<span data-ttu-id="f382f-175">111-111-1111 (行動電話)</span><span class="sxs-lookup"><span data-stu-id="f382f-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="f382f-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="f382f-176">One Microsoft Way</span></span><br>
<span data-ttu-id="f382f-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="f382f-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="f382f-178">*(行動裝置)* 中有三個權杖：</span><span class="sxs-lookup"><span data-stu-id="f382f-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="f382f-179">片語</span><span class="sxs-lookup"><span data-stu-id="f382f-179">Phrase</span></span>|<span data-ttu-id="f382f-180">權杖計數</span><span class="sxs-lookup"><span data-stu-id="f382f-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="f382f-181">(</span><span class="sxs-lookup"><span data-stu-id="f382f-181">(</span></span>|<span data-ttu-id="f382f-182">1</span><span class="sxs-lookup"><span data-stu-id="f382f-182">1</span></span>|
|<span data-ttu-id="f382f-183">行動電話</span><span class="sxs-lookup"><span data-stu-id="f382f-183">mobile</span></span>|<span data-ttu-id="f382f-184">2</span><span class="sxs-lookup"><span data-stu-id="f382f-184">2</span></span>|
|<span data-ttu-id="f382f-185">)</span><span class="sxs-lookup"><span data-stu-id="f382f-185">)</span></span>|<span data-ttu-id="f382f-186">3</span><span class="sxs-lookup"><span data-stu-id="f382f-186">3</span></span>|

<span data-ttu-id="f382f-187">將鄰近設定設為範圍 0 到 3。</span><span class="sxs-lookup"><span data-stu-id="f382f-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![鄰近範例](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="f382f-189">設定文件中出現片語的位置</span><span class="sxs-lookup"><span data-stu-id="f382f-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="f382f-190">當您建立說明時，系統預設在整份文件中搜尋您要摘錄的片語。</span><span class="sxs-lookup"><span data-stu-id="f382f-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="f382f-191">不過，您可以使用 <b>[這些片語出現的位置]</b> 進階設定，協助隔離文件中片語出現的特定位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="f382f-192">當片語的類似實例可能出現在文件中的其他位置，而您想要確認已正確選取時，這是很實用的方法。</span><span class="sxs-lookup"><span data-stu-id="f382f-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="f382f-193">參照我們的醫學轉診文件範例，本文件第一段每次都提及 **「轉診醫生」**。</span><span class="sxs-lookup"><span data-stu-id="f382f-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="f382f-194">使用 <b>[這些片語出現的位置]</b> 設定，在這個範例中，您可以設定您的說明，只在文件的開頭一節，或其他任何可能出現的位置搜尋此標籤。</span><span class="sxs-lookup"><span data-stu-id="f382f-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![這些片語出現的位置設定](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="f382f-196">此設定有以下三個選項供您選擇：</span><span class="sxs-lookup"><span data-stu-id="f382f-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="f382f-197">檔案中的任何位置：搜尋整份文件中的片語。</span><span class="sxs-lookup"><span data-stu-id="f382f-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="f382f-198">檔案開頭：從開頭到片語位置搜尋文件。</span><span class="sxs-lookup"><span data-stu-id="f382f-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="f382f-199">![檔案開頭](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="f382f-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="f382f-200">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="f382f-201"><b>[結束位置]</b> 值將會更新，以顯示您選取區域包含的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="f382f-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="f382f-202">請注意，您可以更新 [結束位置] 值，並調整選取的區域。</span><span class="sxs-lookup"><span data-stu-id="f382f-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="f382f-203">![[檔案位置的開頭] 方塊](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="f382f-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="f382f-204">檔案結尾：從結尾到片語位置搜尋文件。</span><span class="sxs-lookup"><span data-stu-id="f382f-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="f382f-205">![檔案結尾](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="f382f-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="f382f-206">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="f382f-207"><b>[起始位置]</b> 值將會更新，以顯示您選取區域包含的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="f382f-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="f382f-208">請注意，您可以更新 [起始位置] 值，並調整選取的區域。</span><span class="sxs-lookup"><span data-stu-id="f382f-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="f382f-209">![[檔案結尾] 方塊](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="f382f-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="f382f-210">自訂範圍：在文件中的指定範圍搜尋該文件中的片語位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="f382f-211">![自訂範圍](../media/content-understanding/custom-file.png)。</span><span class="sxs-lookup"><span data-stu-id="f382f-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="f382f-212">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="f382f-213">在此設定中，您必須選取 <b>[開始]</b> ，以及 <b>[結束]</b> 位置。</span><span class="sxs-lookup"><span data-stu-id="f382f-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="f382f-214">這些值代表從文件開頭算起的的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="f382f-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="f382f-215">當您可以手動輸入這些值，在檢視器中手動調整選取方塊就變得更容易。</span><span class="sxs-lookup"><span data-stu-id="f382f-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="f382f-216">使用說明範本</span><span class="sxs-lookup"><span data-stu-id="f382f-216">Use explanation templates</span></span>

<span data-ttu-id="f382f-217">雖然您可以為您的說明手動新增各種片語清單值，但使用說明文件庫中所提供的範本會輕鬆得多。</span><span class="sxs-lookup"><span data-stu-id="f382f-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="f382f-218">例如，不要手動新增 *日期* 的所有變化，而是可以使用 *日期* 的片語清單範本，因為其中已包含一些片語清單值：</span><span class="sxs-lookup"><span data-stu-id="f382f-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![說明文件庫](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="f382f-220">說明文件庫包含常用的片語清單說明，包括：</span><span class="sxs-lookup"><span data-stu-id="f382f-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="f382f-221">日期：行事曆日期，所有格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-221">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="f382f-222">包含文字和數字 (例如，"2020 年 12 月 9 日")。</span><span class="sxs-lookup"><span data-stu-id="f382f-222">Includes text and numbers (for example, "Dec 9, 2020").</span></span></br>
- <span data-ttu-id="f382f-223">日期 (數字)：行事曆日期，所有格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-223">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="f382f-224">包含數字 (例如，1-11-2020)。</span><span class="sxs-lookup"><span data-stu-id="f382f-224">Includes numbers (for example 1-11-2020).</span></span></br>
- <span data-ttu-id="f382f-225">時間：12 小時和 24 小時格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-225">Time: 12 and 24 hour formats.</span></span></br>
- <span data-ttu-id="f382f-226">數字：最多 2 位數的正數和負數。</span><span class="sxs-lookup"><span data-stu-id="f382f-226">Number: Positive and negative numbers up to 2 decimals.</span></span> </br>
- <span data-ttu-id="f382f-227">百分比：代表百分比的模式清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-227">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="f382f-228">例如，1%、11%、100%、11.11% 等等。</span><span class="sxs-lookup"><span data-stu-id="f382f-228">For example, 1%, 11%, 100%, 11.11%, etc.</span></span></br>
- <span data-ttu-id="f382f-229">電話號碼：通用美國及國際格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-229">Phone number: Common US and International formats.</span></span> <span data-ttu-id="f382f-230">例如，000 000 0000、000-000-0000、(000)000-0000、(000) 000-0000 等等。</span><span class="sxs-lookup"><span data-stu-id="f382f-230">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span></br>
- <span data-ttu-id="f382f-231">郵遞區號：美國郵遞區號格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-231">Zip code: US Zip code formats.</span></span> <span data-ttu-id="f382f-232">例如，11111、11111-1111。</span><span class="sxs-lookup"><span data-stu-id="f382f-232">For example, 11111, 11111-1111.</span></span></br>
- <span data-ttu-id="f382f-233">句子的第一個單字：最多 9 個字元的文字常用模式。</span><span class="sxs-lookup"><span data-stu-id="f382f-233">First word of sentence: Common patterns for words up to 9 characters.</span></span> </br>
- <span data-ttu-id="f382f-234">句子結尾：句子結尾的常用標點符號</span><span class="sxs-lookup"><span data-stu-id="f382f-234">End of sentence: Common punctuation for end of a sentence</span></span></br>
- <span data-ttu-id="f382f-235">信用卡：常用信用卡號碼格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-235">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="f382f-236">例如，1111-1111-1111-1111。</span><span class="sxs-lookup"><span data-stu-id="f382f-236">For example, 1111-1111-1111-1111.</span></span> </br>
- <span data-ttu-id="f382f-237">社會安全號碼：美國社會安全號碼格式。</span><span class="sxs-lookup"><span data-stu-id="f382f-237">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="f382f-238">例如，111-11-1111。</span><span class="sxs-lookup"><span data-stu-id="f382f-238">For example, 111-11-1111.</span></span> </br>
- <span data-ttu-id="f382f-239">核取方塊：代表填入核取方塊上變化的片語清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-239">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="f382f-240">例如，_X_、_ _X_ 等等。</span><span class="sxs-lookup"><span data-stu-id="f382f-240">For example, _X_, _ _X_, etc.</span></span></br>
- <span data-ttu-id="f382f-241">貨幣：主要國際符號。</span><span class="sxs-lookup"><span data-stu-id="f382f-241">Currency: Major international symbols.</span></span> <span data-ttu-id="f382f-242">例如，$。</span><span class="sxs-lookup"><span data-stu-id="f382f-242">For example, $.</span></span> </br>
- <span data-ttu-id="f382f-243">電子郵件副本：帶有 'CC:' 一詞的片語清單，通常可在傳送郵件的其他人員或群組的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="f382f-243">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span></br>
- <span data-ttu-id="f382f-244">電子郵件日期：帶有 'Sent on:' 一詞的片語清單，通常可在傳送郵件的日期附近找到。</span><span class="sxs-lookup"><span data-stu-id="f382f-244">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span></br>
- <span data-ttu-id="f382f-245">電子郵件問候語：電子郵件的常用開場白。</span><span class="sxs-lookup"><span data-stu-id="f382f-245">Email greeting: Common opening lines for emails.</span></span></br>
- <span data-ttu-id="f382f-246">電子郵件收件者：帶有 'To:' 一詞的片語清單，通常可在傳送郵件的人員或群組的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="f382f-246">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> </br>
- <span data-ttu-id="f382f-247">電子郵件寄件者：帶有 'From:' 一詞的片語清單，通常可在寄件者的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="f382f-247">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> </br>
- <span data-ttu-id="f382f-248">電子郵件主旨：帶有 'Subject:' 一詞的片語清單，通常可在電子郵件的主旨附近找到。</span><span class="sxs-lookup"><span data-stu-id="f382f-248">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> </br>

<span data-ttu-id="f382f-249">說明文件庫也包含三個自動範本類型，可以搭配您在範例檔案中標示的資料：</span><span class="sxs-lookup"><span data-stu-id="f382f-249">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="f382f-250">標籤後面：範例檔案中標籤後面的文字或字元。</span><span class="sxs-lookup"><span data-stu-id="f382f-250">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="f382f-251">標籤前面：範例檔案中標籤前面的文字或字元。</span><span class="sxs-lookup"><span data-stu-id="f382f-251">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="f382f-252">標籤：範例檔案的最多前 10 個標籤。</span><span class="sxs-lookup"><span data-stu-id="f382f-252">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="f382f-253">為了提供您自動範本如何運作的範例，我們會在下列範例檔案中使用「標籤前面」說明範本，協助為模型提供更多資訊，以取得更準確的相符項目。</span><span class="sxs-lookup"><span data-stu-id="f382f-253">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![範例檔案](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="f382f-255">當您選取「標籤前面」說明範本時，它會尋找您的範例檔案中標籤前面出現的第一組文字。</span><span class="sxs-lookup"><span data-stu-id="f382f-255">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="f382f-256">範例中在第一個範例檔案中識別的文字是 "As of"。</span><span class="sxs-lookup"><span data-stu-id="f382f-256">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![標籤前面範本](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="f382f-258">您可以選取 [<b>新增</b>] 從範本建立說明。</span><span class="sxs-lookup"><span data-stu-id="f382f-258">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="f382f-259">隨著您新增更多範例檔案，將會識別出其他字詞，並將其新增至片語清單。</span><span class="sxs-lookup"><span data-stu-id="f382f-259">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![新增標籤](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="f382f-261">使用來自說明文件庫的範本</span><span class="sxs-lookup"><span data-stu-id="f382f-261">To use a template from the explanation library</span></span>

1. <span data-ttu-id="f382f-262">從模型 [訓練 **]** 頁面的 [說明 **]** 區段，選取 [新增 **]**，然後選取 [從範本 **]**。</span><span class="sxs-lookup"><span data-stu-id="f382f-262">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![在標籤前面新增](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="f382f-264">在 [說明範本 **]** 頁面上，選取您要使用的說明，然後選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="f382f-264">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![選取範本](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="f382f-266">您選取的範本資訊會顯示在 [建立說明 **]** 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f382f-266">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="f382f-267">視需要編輯說明名稱，然後從片語清單新增或移除項目。</span><span class="sxs-lookup"><span data-stu-id="f382f-267">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![編輯範本](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="f382f-269">完成後，選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="f382f-269">When finished, select **Save**.</span></span>