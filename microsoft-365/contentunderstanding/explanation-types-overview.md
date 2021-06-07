---
title: Microsoft SharePoint Syntex 中的說明類型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 深入了解 Microsoft SharePoint Syntex 中的片語清單、規則運算式和鄰近說明類型。
ms.openlocfilehash: 8748b2fd33e20cf7e402d499db05f1f6722e735a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770862"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="549b2-103">Microsoft SharePoint Syntex 中的說明類型</span><span class="sxs-lookup"><span data-stu-id="549b2-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="549b2-104">說明可用來協助您定義要在 Microsoft SharePoint Syntex 中於您的文件瞭解模型中加標籤及摘錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="549b2-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="549b2-105">建立說明時，您必須選取說明類型。</span><span class="sxs-lookup"><span data-stu-id="549b2-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="549b2-106">本文可協助您了解不同的說明類型及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="549b2-106">This article helps you understand the different explanation types and how they're used.</span></span>

![[建立說明] 窗格的螢幕擷取畫面顯示出三種說明類型。](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="549b2-108">以下為可用的說明類型：</span><span class="sxs-lookup"><span data-stu-id="549b2-108">These explanation types are available:</span></span>

- <span data-ttu-id="549b2-109">[**片語清單**](#phrase-list)：您可以在要摘錄的文件或資訊中使用的單字、片語、數字或其他字元的清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="549b2-110">例如，文字字串 *[轉診醫生]* 位於所有您要識別的「醫學轉診」文件中。</span><span class="sxs-lookup"><span data-stu-id="549b2-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="549b2-111">或者來自您要識別的所有「醫學轉診」文件中，轉診醫生的 *電話號碼*。</span><span class="sxs-lookup"><span data-stu-id="549b2-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="549b2-112">[**規則運算式**](#regular-expression)：使用模式比對的標記法來尋找特定字元模式。</span><span class="sxs-lookup"><span data-stu-id="549b2-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="549b2-113">例如，您可以使用規則運算式來尋找一組文件中的 *電子郵件地址* 模式的所有實例。</span><span class="sxs-lookup"><span data-stu-id="549b2-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="549b2-114">[**鄰近**](#proximity): 描述彼此之間的說明有多接近。</span><span class="sxs-lookup"><span data-stu-id="549b2-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="549b2-115">例如，*街道號碼* 片語清單會位於 *街道名稱* 片語清單之前，它們之間沒有權杖 (您將在本文稍後了解權杖)。</span><span class="sxs-lookup"><span data-stu-id="549b2-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="549b2-116">使用鄰近類型時，要求在您的模型中至少有兩個說明，否則將停用該選項。</span><span class="sxs-lookup"><span data-stu-id="549b2-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="549b2-117">片語清單</span><span class="sxs-lookup"><span data-stu-id="549b2-117">Phrase list</span></span>

<span data-ttu-id="549b2-118">片語清單說明類型通常是用來透過您的模型來識別和分類文件。</span><span class="sxs-lookup"><span data-stu-id="549b2-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="549b2-119">如 *[轉診醫生]* 標籤範例中所述，它是在您要識別的文件中一致的單字、片語、數字或字元的字串。</span><span class="sxs-lookup"><span data-stu-id="549b2-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="549b2-120">雖然這並非一項要求，但如果您要擷取的片語位於您文件中的一致位置，則使用您的說明可以更成功。</span><span class="sxs-lookup"><span data-stu-id="549b2-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="549b2-121">例如，*[轉診醫生]* 標籤可能會一致地位於文件的第一個段落。</span><span class="sxs-lookup"><span data-stu-id="549b2-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="549b2-122">您也可以使用 **[[設定片語在文件中出現的位置]](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** 的進階設定來選取片語所在的特定區域，尤其是當片語可能出現在文件中多個位置時。</span><span class="sxs-lookup"><span data-stu-id="549b2-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="549b2-123">如果識別標籤時要求區分大小寫，使用片語清單類型可讓您在說明中加以指定，方法是選取 [僅完全符合大寫 **]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="549b2-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![區分大小寫](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="549b2-125">片語類型在建立說明時會特別有用，該說明可以識別和摘錄不同格式的資訊，例如日期、電話號碼和信用卡號。</span><span class="sxs-lookup"><span data-stu-id="549b2-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="549b2-126">例如，日期可以以許多不同的格式顯示 (1/1/2020、1-1-2020、01/01/20、01/01/2020 或 Jan 1,2020)。</span><span class="sxs-lookup"><span data-stu-id="549b2-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="549b2-127">定義片語清單可讓您的說明更有效率，方法是從您想要識別及摘錄的資料中，擷取任何可能的變化。</span><span class="sxs-lookup"><span data-stu-id="549b2-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="549b2-128">針對 *[電話號碼]* 範例，則會從模型識別的所有「醫學轉診」文件中，摘錄每位轉診醫生的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="549b2-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="549b2-129">建立說明時，輸入電話號碼可能會在文件中顯示的不同格式，以便您擷取可能的變化。</span><span class="sxs-lookup"><span data-stu-id="549b2-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![電話號碼片語模式](../media/content-understanding/pattern-list.png)

<span data-ttu-id="549b2-131">在這個範例中，請在 **[進階設定]** 選取 **[從 0 至 9 的任何數字]** 核取方塊，以將片語清單中使用的每個「0」值，識別為 0 到 9 之間的任何數字。</span><span class="sxs-lookup"><span data-stu-id="549b2-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![從 0 至 9 的任何數字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="549b2-133">同樣地，如果您建立包含文字字元的片語清單，請選取 **[從 a 至 z 的任何字母]** 核取方塊，以將片語清單中使用的每個「a」字元，識別為「a」到「z」的任何字元。</span><span class="sxs-lookup"><span data-stu-id="549b2-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="549b2-134">例如，如果您建立 **日期** 片語清單，而您想要確認可辨識日期格式 *Jan 1, 2020*，您必須：</span><span class="sxs-lookup"><span data-stu-id="549b2-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="549b2-135">將 *aaa 0, 0000* 和 *aaa 00, 0000* 新增至您的片語清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="549b2-136">確認您也已選取 [從 a-z 的任何字母 **]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![從 a-z 的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="549b2-138">如果您在片語清單中有大小寫需求，則可以選取 **[僅完全符合大寫]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="549b2-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="549b2-139">針對日期範例，如果您需要月份的第一個字母為大寫，您必須：</span><span class="sxs-lookup"><span data-stu-id="549b2-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="549b2-140">將 *Aaa 0, 0000* 和 *Aaa 00, 0000* 新增至您的片語清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="549b2-141">確認也選取 [僅完全符合大寫 **]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![僅完全符合大寫](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="549b2-143">不要手動建立片語清單說明，而是使用 [說明文件庫](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) 來使用針對常見片語清單的片語清單範本，例如 *日期*、*電話號碼* 或 *信用卡號碼*。</span><span class="sxs-lookup"><span data-stu-id="549b2-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="549b2-144">規則運算式</span><span class="sxs-lookup"><span data-stu-id="549b2-144">Regular expression</span></span>

<span data-ttu-id="549b2-145">規則運算式說明類型可讓您建立模式，協助尋找及識別文件中特定的文字字串。</span><span class="sxs-lookup"><span data-stu-id="549b2-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="549b2-146">您可以使用規則運算式，快速剖析大量的文字，以達成下列目標：</span><span class="sxs-lookup"><span data-stu-id="549b2-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="549b2-147">尋找特定字元模式。</span><span class="sxs-lookup"><span data-stu-id="549b2-147">Find specific character patterns.</span></span>
- <span data-ttu-id="549b2-148">驗證文字以確保其符合預先定義的模式 (例如電子郵件地址)。</span><span class="sxs-lookup"><span data-stu-id="549b2-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="549b2-149">解壓縮、編輯、取代或刪除文字子字串。</span><span class="sxs-lookup"><span data-stu-id="549b2-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="549b2-150">規則運算式類型在建立說明時會特別有用，該說明可以識別和摘錄類似格式的資訊，例如電子郵件地址、銀行帳戶號碼，或 URL。</span><span class="sxs-lookup"><span data-stu-id="549b2-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="549b2-151">例如，電子郵件地址 (例如 megan@contoso.com) 會以特定模式顯示 ("megan" 是第一部分，而 "com" 是最後一部分)。</span><span class="sxs-lookup"><span data-stu-id="549b2-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="549b2-152">電子郵件地址的規則運算式是：**[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**。</span><span class="sxs-lookup"><span data-stu-id="549b2-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="549b2-153">此運算式包含五個部分，順序為：</span><span class="sxs-lookup"><span data-stu-id="549b2-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="549b2-154">任何下列字元數:</span><span class="sxs-lookup"><span data-stu-id="549b2-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="549b2-p112">a. 從 a 到 z 的字母</span><span class="sxs-lookup"><span data-stu-id="549b2-p112">a. Letters from a to z</span></span>

   <span data-ttu-id="549b2-p113">b. 從 0-9 的數字</span><span class="sxs-lookup"><span data-stu-id="549b2-p113">b. Numbers from 0-9</span></span>

   <span data-ttu-id="549b2-p114">c. 句點、底線、百分比或虛線</span><span class="sxs-lookup"><span data-stu-id="549b2-p114">c. Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="549b2-161">@ 符號</span><span class="sxs-lookup"><span data-stu-id="549b2-161">The @ symbol</span></span>

3. <span data-ttu-id="549b2-162">任何與電子郵件地址的第一個部分相同的字元數</span><span class="sxs-lookup"><span data-stu-id="549b2-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="549b2-163">句點</span><span class="sxs-lookup"><span data-stu-id="549b2-163">A period</span></span>

5. <span data-ttu-id="549b2-164">兩到六個字母</span><span class="sxs-lookup"><span data-stu-id="549b2-164">Two to six letters</span></span>

<span data-ttu-id="549b2-165">若要新增規則運算式說明類型：</span><span class="sxs-lookup"><span data-stu-id="549b2-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="549b2-166">從 **[建立說明]** 窗格的 **[說明類型]** 下方，選取 **[規則運算式]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![顯示已選取 [規則運算式] 的 [建立說明] 窗格的螢幕擷取畫面。](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="549b2-168">您可以在 **[規則運算式]** 文字方塊中輸入解釋，或者選取 **[從範本中新增規則運算式]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="549b2-169">當您使用範本新增規則運算式時，它會自動將名稱和規則運算式新增到文字方塊。</span><span class="sxs-lookup"><span data-stu-id="549b2-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="549b2-170">例如，如果您選擇 **[電子郵件]** 範本，則會彈出 **[建立說明]** 窗格。</span><span class="sxs-lookup"><span data-stu-id="549b2-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![顯示已套用 [電子郵件範本] 的 [建立說明] 窗格的螢幕擷取畫面。](../media/content-understanding/create-regular-expression-email.png)

### <a name="limitations"></a><span data-ttu-id="549b2-172">限制</span><span class="sxs-lookup"><span data-stu-id="549b2-172">Limitations</span></span>

<span data-ttu-id="549b2-173">下表顯示目前無法用於規則運算式模式的內嵌字元選項。</span><span class="sxs-lookup"><span data-stu-id="549b2-173">The following table shows inline character options that currently are not available for use in regular expression patterns.</span></span> 

|<span data-ttu-id="549b2-174">選項</span><span class="sxs-lookup"><span data-stu-id="549b2-174">Option</span></span>  |<span data-ttu-id="549b2-175">狀態</span><span class="sxs-lookup"><span data-stu-id="549b2-175">State</span></span>  |<span data-ttu-id="549b2-176">目前功能</span><span class="sxs-lookup"><span data-stu-id="549b2-176">Current functionality</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="549b2-177">區分大小寫</span><span class="sxs-lookup"><span data-stu-id="549b2-177">Case sensitivity</span></span> | <span data-ttu-id="549b2-178">目前不支援。</span><span class="sxs-lookup"><span data-stu-id="549b2-178">Currently not supported.</span></span> | <span data-ttu-id="549b2-179">執行的所有符合項目不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="549b2-179">All matches performed are case-insensitive.</span></span>  |
|<span data-ttu-id="549b2-180">線條錨點</span><span class="sxs-lookup"><span data-stu-id="549b2-180">Line anchors</span></span>     | <span data-ttu-id="549b2-181">目前不支援。</span><span class="sxs-lookup"><span data-stu-id="549b2-181">Currently not supported.</span></span> | <span data-ttu-id="549b2-182">無法在必須相符的字串中指定特定位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-182">Unable to specify a specific position in a string where a match must occur.</span></span>   |

## <a name="proximity"></a><span data-ttu-id="549b2-183">鄰近</span><span class="sxs-lookup"><span data-stu-id="549b2-183">Proximity</span></span> 

<span data-ttu-id="549b2-184">鄰近說明類型可協助您的模型識別資料，方法是透過定義另一個資料片段與其相似程度。</span><span class="sxs-lookup"><span data-stu-id="549b2-184">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="549b2-185">例如，在您的模型中，您定義了兩個說明，可標記客戶的 *[街道地址號碼]* 和 *[電話號碼]*。</span><span class="sxs-lookup"><span data-stu-id="549b2-185">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="549b2-186">請注意，客戶的電話號碼永遠都出現在街道地址的前面。</span><span class="sxs-lookup"><span data-stu-id="549b2-186">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="549b2-187">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="549b2-187">Alex Wilburn</span></span><br>
<span data-ttu-id="549b2-188">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="549b2-188">555-555-5555</span></span><br>
<span data-ttu-id="549b2-189">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="549b2-189">One Microsoft Way</span></span><br>
<span data-ttu-id="549b2-190">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="549b2-190">Redmond, WA 98034</span></span><br>

<span data-ttu-id="549b2-191">使用鄰近說明來定義電話號碼說明的距離，以便更好地識別文件中的街道地址號碼。</span><span class="sxs-lookup"><span data-stu-id="549b2-191">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![鄰近說明](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="549b2-193">什麼是權杖？</span><span class="sxs-lookup"><span data-stu-id="549b2-193">What are tokens?</span></span>

<span data-ttu-id="549b2-194">若要使用鄰近說明類型，您必須瞭解權杖是什麼。</span><span class="sxs-lookup"><span data-stu-id="549b2-194">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="549b2-195">權杖的編號是鄰近說明測量一個說明與另一個說明之間距離的方式。</span><span class="sxs-lookup"><span data-stu-id="549b2-195">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="549b2-196">權杖是字母和數字的連續範圍 (不含空格或標點符號)。</span><span class="sxs-lookup"><span data-stu-id="549b2-196">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="549b2-197">下表顯示如何判斷片語中權杖數目的範例。</span><span class="sxs-lookup"><span data-stu-id="549b2-197">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="549b2-198">片語</span><span class="sxs-lookup"><span data-stu-id="549b2-198">Phrase</span></span>|<span data-ttu-id="549b2-199">權杖數目</span><span class="sxs-lookup"><span data-stu-id="549b2-199">Number of tokens</span></span>|<span data-ttu-id="549b2-200">說明</span><span class="sxs-lookup"><span data-stu-id="549b2-200">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="549b2-201">1</span><span class="sxs-lookup"><span data-stu-id="549b2-201">1</span></span>|<span data-ttu-id="549b2-202">沒有標點符號或空格的單字。</span><span class="sxs-lookup"><span data-stu-id="549b2-202">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="549b2-203">1</span><span class="sxs-lookup"><span data-stu-id="549b2-203">1</span></span>|<span data-ttu-id="549b2-204">記錄定位器號碼。</span><span class="sxs-lookup"><span data-stu-id="549b2-204">A record locator number.</span></span> <span data-ttu-id="549b2-205">其中可能含有數字和字母，但沒有標點符號。</span><span class="sxs-lookup"><span data-stu-id="549b2-205">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="549b2-206">5</span><span class="sxs-lookup"><span data-stu-id="549b2-206">5</span></span>|<span data-ttu-id="549b2-207">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="549b2-207">A phone number.</span></span> <span data-ttu-id="549b2-208">每個標點符號都是單一權杖，因此 `425-555-5555` 會是 5 個權杖：</span><span class="sxs-lookup"><span data-stu-id="549b2-208">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="549b2-209">7</span><span class="sxs-lookup"><span data-stu-id="549b2-209">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="549b2-210">設定鄰近說明類型</span><span class="sxs-lookup"><span data-stu-id="549b2-210">Configure the proximity explanation type</span></span>

<span data-ttu-id="549b2-211">針對此範例，請設定鄰近設定，以定義來自 *[街道地址號碼]* 說明的 *[電話號碼]* 說明之權杖數目的範圍。</span><span class="sxs-lookup"><span data-stu-id="549b2-211">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="549b2-212">請注意，最小範圍為「0」，因為電話號碼和街道地址號碼之間沒有權杖。</span><span class="sxs-lookup"><span data-stu-id="549b2-212">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="549b2-213">但範例文件中的部分電話號碼會附加 *(行動裝置)*。</span><span class="sxs-lookup"><span data-stu-id="549b2-213">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="549b2-214">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="549b2-214">Nestor Wilke</span></span><br>
<span data-ttu-id="549b2-215">111-111-1111 (行動電話)</span><span class="sxs-lookup"><span data-stu-id="549b2-215">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="549b2-216">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="549b2-216">One Microsoft Way</span></span><br>
<span data-ttu-id="549b2-217">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="549b2-217">Redmond, WA 98034</span></span><br>

<span data-ttu-id="549b2-218">*(行動裝置)* 中有三個權杖：</span><span class="sxs-lookup"><span data-stu-id="549b2-218">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="549b2-219">片語</span><span class="sxs-lookup"><span data-stu-id="549b2-219">Phrase</span></span>|<span data-ttu-id="549b2-220">權杖計數</span><span class="sxs-lookup"><span data-stu-id="549b2-220">Token count</span></span>|
|--|--|
|<span data-ttu-id="549b2-221">(</span><span class="sxs-lookup"><span data-stu-id="549b2-221">(</span></span>|<span data-ttu-id="549b2-222">1</span><span class="sxs-lookup"><span data-stu-id="549b2-222">1</span></span>|
|<span data-ttu-id="549b2-223">行動電話</span><span class="sxs-lookup"><span data-stu-id="549b2-223">mobile</span></span>|<span data-ttu-id="549b2-224">2</span><span class="sxs-lookup"><span data-stu-id="549b2-224">2</span></span>|
|<span data-ttu-id="549b2-225">)</span><span class="sxs-lookup"><span data-stu-id="549b2-225">)</span></span>|<span data-ttu-id="549b2-226">3</span><span class="sxs-lookup"><span data-stu-id="549b2-226">3</span></span>|

<span data-ttu-id="549b2-227">將鄰近設定設為範圍 0 到 3。</span><span class="sxs-lookup"><span data-stu-id="549b2-227">Configure the proximity setting to have a range of 0 through 3.</span></span>

![鄰近範例](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="549b2-229">設定文件中出現片語的位置</span><span class="sxs-lookup"><span data-stu-id="549b2-229">Configure where phrases occur in the document</span></span>

<span data-ttu-id="549b2-230">當您建立說明時，系統預設在整份文件中搜尋您要摘錄的片語。</span><span class="sxs-lookup"><span data-stu-id="549b2-230">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="549b2-231">不過，您可以使用 **[這些片語出現的位置]** 進階設定，協助隔離文件中片語出現的特定位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-231">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="549b2-232">當片語的類似實例可能出現在文件中的其他位置，而您想要確認已正確選取時，這項設定便是很實用的方法。</span><span class="sxs-lookup"><span data-stu-id="549b2-232">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="549b2-233">參照我們的醫學轉診文件範例，本文件第一段每次都提及 *「轉診醫生」*。</span><span class="sxs-lookup"><span data-stu-id="549b2-233">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="549b2-234">使用 **[這些片語出現的位置]** 設定，在這個範例中，您可以設定您的說明，只在文件的開頭一節，或其他任何可能出現的位置搜尋此標籤。</span><span class="sxs-lookup"><span data-stu-id="549b2-234">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![這些片語出現的位置設定](../media/content-understanding/phrase-location.png)

<span data-ttu-id="549b2-236">此設定有以下三個選項供您選擇：</span><span class="sxs-lookup"><span data-stu-id="549b2-236">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="549b2-237">檔案中的任何位置：搜尋整份文件中的片語。</span><span class="sxs-lookup"><span data-stu-id="549b2-237">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="549b2-238">檔案開頭：從開頭到片語位置搜尋文件。</span><span class="sxs-lookup"><span data-stu-id="549b2-238">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![檔案開頭](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="549b2-240">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-240">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="549b2-241">**[結束位置]** 值將會更新，以顯示您選取區域包含的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="549b2-241">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="549b2-242">您可以更新 **[結束位置]** 值，並調整選取的區域。</span><span class="sxs-lookup"><span data-stu-id="549b2-242">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![[檔案位置的開頭] 方塊](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="549b2-244">檔案結尾：從結尾到片語位置搜尋文件。</span><span class="sxs-lookup"><span data-stu-id="549b2-244">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![檔案結尾](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="549b2-246">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-246">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="549b2-247">**[起始位置]** 值將會更新，以顯示您選取區域包含的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="549b2-247">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="549b2-248">您可以更新 [起始位置] 值，並調整選取的區域。</span><span class="sxs-lookup"><span data-stu-id="549b2-248">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![[檔案結尾] 方塊](../media/content-understanding/end-box.png)

- <span data-ttu-id="549b2-250">自訂範圍：在文件的指定範圍内搜尋片語的位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-250">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![自訂範圍](../media/content-understanding/custom-file.png)

    <span data-ttu-id="549b2-252">在檢視器中，您可以手動調整選取方塊，以包含該階段所在的位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-252">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="549b2-253">在此設定中，您必須選取 **[開始]** ，以及 **[結束]** 位置。</span><span class="sxs-lookup"><span data-stu-id="549b2-253">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="549b2-254">這些值代表從文件開頭算起的的語彙基元數目。</span><span class="sxs-lookup"><span data-stu-id="549b2-254">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="549b2-255">當您可以手動輸入這些值，在檢視器中手動調整選取方塊就變得更容易。</span><span class="sxs-lookup"><span data-stu-id="549b2-255">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="549b2-256">使用說明範本</span><span class="sxs-lookup"><span data-stu-id="549b2-256">Use explanation templates</span></span>

<span data-ttu-id="549b2-257">雖然您可以為您的說明手動新增各種片語清單值，但使用說明文件庫中所提供的範本會輕鬆得多。</span><span class="sxs-lookup"><span data-stu-id="549b2-257">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="549b2-258">例如，不要手動新增 *[日期]* 的所有變化，而是可以使用 *[日期]* 的片語清單範本，因為其中已包含許多片語清單值：</span><span class="sxs-lookup"><span data-stu-id="549b2-258">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![說明文件庫](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="549b2-260&quot;>說明文件庫包含常用的 *片語清單* 說明，包括：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;549b2-260&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;549b2-261&quot;>日期：行事曆日期，所有格式。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;549b2-261&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;549b2-262&quot;>包含文字和數字 (例如，&quot;2020 年 12 月 9 日")。</span><span class="sxs-lookup"><span data-stu-id="549b2-262">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="549b2-263">日期 (數字)：行事曆日期，所有格式。</span><span class="sxs-lookup"><span data-stu-id="549b2-263">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="549b2-264">包含數字 (例如，1-11-2020)。</span><span class="sxs-lookup"><span data-stu-id="549b2-264">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="549b2-265">時間：12 小時和 24 小時格式。</span><span class="sxs-lookup"><span data-stu-id="549b2-265">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="549b2-266">數字：最多兩位數的正數和負數。</span><span class="sxs-lookup"><span data-stu-id="549b2-266">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="549b2-267">百分比：代表百分比的模式清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-267">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="549b2-268">例如，1%、11%、100% 或 11.11%。</span><span class="sxs-lookup"><span data-stu-id="549b2-268">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="549b2-269">電話號碼：通用美國及國際格式。</span><span class="sxs-lookup"><span data-stu-id="549b2-269">Phone number: Common US and International formats.</span></span> <span data-ttu-id="549b2-270">例如，000 000 0000、000-000-0000、(000)000-0000 或 (000) 000-0000。</span><span class="sxs-lookup"><span data-stu-id="549b2-270">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="549b2-271">郵遞區號：美國郵遞區號格式。</span><span class="sxs-lookup"><span data-stu-id="549b2-271">Zip code: US Zip code formats.</span></span> <span data-ttu-id="549b2-272">例如，11111、11111-1111。</span><span class="sxs-lookup"><span data-stu-id="549b2-272">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="549b2-273">句子的第一個單字：最多九個字元的文字常用模式。</span><span class="sxs-lookup"><span data-stu-id="549b2-273">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="549b2-274">句子結尾：句子結尾的常用標點符號。</span><span class="sxs-lookup"><span data-stu-id="549b2-274">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="549b2-275">信用卡：常用信用卡號碼格式。</span><span class="sxs-lookup"><span data-stu-id="549b2-275">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="549b2-276">例如，1111-1111-1111-1111。</span><span class="sxs-lookup"><span data-stu-id="549b2-276">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="549b2-p132">社會安全號碼：美國社會安全號碼格式。例如，111-11-1111。</span><span class="sxs-lookup"><span data-stu-id="549b2-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="549b2-279">核取方塊：代表填入核取方塊上變化的片語清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-279">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="549b2-280">例如，_X_、_ _X_。</span><span class="sxs-lookup"><span data-stu-id="549b2-280">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="549b2-281">貨幣：主要國際符號。</span><span class="sxs-lookup"><span data-stu-id="549b2-281">Currency: Major international symbols.</span></span> <span data-ttu-id="549b2-282">例如，$。</span><span class="sxs-lookup"><span data-stu-id="549b2-282">For example, $.</span></span> 
- <span data-ttu-id="549b2-283">電子郵件副本：帶有 'CC:' 一詞的片語清單，通常可在傳送郵件的其他人員或群組的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="549b2-283">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="549b2-284">電子郵件日期：帶有 'Sent on:' 一詞的片語清單，通常可在傳送郵件的日期附近找到。</span><span class="sxs-lookup"><span data-stu-id="549b2-284">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="549b2-285">電子郵件問候語：電子郵件的常用開場白。</span><span class="sxs-lookup"><span data-stu-id="549b2-285">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="549b2-286">電子郵件收件者：帶有 'To:' 一詞的片語清單，通常可在傳送郵件的人員或群組的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="549b2-286">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="549b2-287">電子郵件寄件者：帶有 'From:' 一詞的片語清單，通常可在寄件者的名稱或電子郵件地址附近找到。</span><span class="sxs-lookup"><span data-stu-id="549b2-287">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="549b2-288">電子郵件主旨：帶有 'Subject:' 一詞的片語清單，通常可在電子郵件的主旨附近找到。</span><span class="sxs-lookup"><span data-stu-id="549b2-288">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="549b2-289">說明文件庫也包含常用的 *[規則運算式]* 說明，包括：</span><span class="sxs-lookup"><span data-stu-id="549b2-289">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="549b2-290">6 到 17 位數的數位：符合任何從 6 到 17 位數長的數位。</span><span class="sxs-lookup"><span data-stu-id="549b2-290">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="549b2-291">美國銀行帳戶號碼符合此模式。</span><span class="sxs-lookup"><span data-stu-id="549b2-291">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="549b2-292">電子郵件：符合一般類型的電子郵件地址，例如 meganb@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="549b2-292">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="549b2-293">美國納稅人識別碼：符合以 9 開頭的三位數字，然後符合以 7 或 8 開頭的 6 位數字。</span><span class="sxs-lookup"><span data-stu-id="549b2-293">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="549b2-294">網址 (URL)：符合網址的格式，開頭為 http:// or https://。</span><span class="sxs-lookup"><span data-stu-id="549b2-294">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="549b2-295">此外，說明文件庫包含三個自動範本類型，可以搭配您在範例檔案中標示的資料：</span><span class="sxs-lookup"><span data-stu-id="549b2-295">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="549b2-296">標籤後面：範例檔案中標籤後面的文字或字元。</span><span class="sxs-lookup"><span data-stu-id="549b2-296">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="549b2-297">標籤前面：範例檔案中標籤前面的文字或字元。</span><span class="sxs-lookup"><span data-stu-id="549b2-297">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="549b2-298">標籤：範例檔案的最多前 10 個標籤。</span><span class="sxs-lookup"><span data-stu-id="549b2-298">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="549b2-299">為了提供您自動範本如何運作的範例，我們會在下列範例檔案中使用「標籤前面」說明範本，協助為模型提供更多資訊，以取得更準確的相符項目。</span><span class="sxs-lookup"><span data-stu-id="549b2-299">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![範例檔案](../media/content-understanding/before-label.png)

<span data-ttu-id="549b2-301">當您選取「標籤前面」說明範本時，它會尋找您的範例檔案中標籤前面出現的第一組文字。</span><span class="sxs-lookup"><span data-stu-id="549b2-301">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="549b2-302">範例中在第一個範例檔案中識別的文字是 "As of"。</span><span class="sxs-lookup"><span data-stu-id="549b2-302">In the example, the words that are identified in the first example file is "As of".</span></span>

![標籤前面範本](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="549b2-304">您可以選取 [**新增**] 從範本建立說明。</span><span class="sxs-lookup"><span data-stu-id="549b2-304">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="549b2-305">隨著您新增更多範例檔案，將會識別出其他字詞，並將其新增至片語清單。</span><span class="sxs-lookup"><span data-stu-id="549b2-305">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![新增標籤](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="549b2-307">使用來自說明文件庫的範本</span><span class="sxs-lookup"><span data-stu-id="549b2-307">To use a template from the explanation library</span></span>

1. <span data-ttu-id="549b2-308">從模型 [訓練 **]** 頁面的 [說明 **]** 區段，選取 [新增 **]**，然後選取 [從範本 **]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-308">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![在標籤前面新增](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="549b2-310">在 [說明範本 **]** 頁面上，選取您要使用的說明，然後選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-310">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![選取範本](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="549b2-312">您選取的範本資訊會顯示在 [建立說明 **]** 頁面上。</span><span class="sxs-lookup"><span data-stu-id="549b2-312">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="549b2-313">視需要編輯說明名稱，然後從片語清單新增或移除項目。</span><span class="sxs-lookup"><span data-stu-id="549b2-313">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![編輯範本](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="549b2-315">完成後，選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="549b2-315">When finished, select **Save**.</span></span>