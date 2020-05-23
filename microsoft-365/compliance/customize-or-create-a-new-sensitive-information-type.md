---
title: 自訂或建立新的敏感資訊類型
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: 了解如何為一般資料保護規定 (GDPR) 修改或建立新的 Office 365 敏感資訊類型。
ms.openlocfilehash: 70ce61f582cbc952811d01cccc7b958bf1b52dbb
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224630"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="cbdc0-103">自訂或建立新的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="cbdc0-104">本文提供三個範例，示範如何為 GDPR 修改或建立新敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-104">This article provides three examples to demonstrate how to modify or create new sensitive information types for GDPR.</span></span>

- <span data-ttu-id="cbdc0-105">修改現有的敏感資訊類型 — 歐盟轉帳卡卡號</span><span class="sxs-lookup"><span data-stu-id="cbdc0-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="cbdc0-106">建立新的敏感資訊類型 — 電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="cbdc0-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="cbdc0-107">利用 XML 檔案範例建立新的敏感資訊類型 — Contoso 客戶編號</span><span class="sxs-lookup"><span data-stu-id="cbdc0-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="cbdc0-108">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-108">Also see:</span></span>

- [<span data-ttu-id="cbdc0-109">使用 PowerShell 建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-109">Create a custom sensitive information type using PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="cbdc0-110">自訂內建的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="cbdc0-111">修改敏感資訊類型以提高精確度</span><span class="sxs-lookup"><span data-stu-id="cbdc0-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="cbdc0-112">如果您使用的是內容搜尋，以利用敏感資訊類型搜尋個人資訊，而且並未傳回預期的結果，或查詢傳回太多誤判，請考慮修改敏感資訊類型，以更有效地使用您的環境。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-112">If you're using Content Search to search for personal data using sensitive information types and you're not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="cbdc0-p101">建立或自訂敏感資訊類型的最佳做法是根據現有的敏感資訊類型建立新的敏感資訊類型，同時為它提供唯一名稱和識別碼。比方說，如果您想要調整「歐盟轉帳卡卡號」敏感資訊類型的參數，您可以將該規則的複本命名為「歐盟轉帳卡加強版」，以與正本區別。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the "EU Debit Card Number" sensitive information type, you could name your copy of that rule "EU Debit Card Enhanced" to distinguish it from the original.</span></span>

<span data-ttu-id="cbdc0-p102">在新的敏感資訊類型中，只需修改您想要變更以提高其精確度的值。一旦完成，就上傳新的敏感資訊類型，並建立新的 DLP 規則 (或修改現有的 DLP 規則)，來使用您剛新增的敏感資訊類型。修改敏感資訊類型的精確度需要反復試驗，所有保留原始類型的複本可讓您在未來需要時回到最初狀態。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="cbdc0-118">若要自訂敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="cbdc0-119">匯出 Office 365 中內建的敏感資訊類型的現有 Microsoft 規則套件。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="cbdc0-120">重新命名此 XML 檔案，並在您最愛的 XML 編輯器中開啟。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="cbdc0-121">隔離敏感資訊類型，並移除所有其他敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="cbdc0-122">使用 PowerShell 為您正在修改的敏感資訊類型產生兩個新的 GUID。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="cbdc0-123">修改識別碼和其他基本元素，讓敏感資訊類型成為唯一的 (這包括將兩個 GUID 取代為您產生的新 GUID)。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="cbdc0-124">調整比對需求以改善精確度。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="cbdc0-125">鄰近修改 — 修改字元模式鄰近，以展開或縮小必須在其中根據敏感資訊類型尋找關鍵字的視窗。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="cbdc0-p103">關鍵字修改 — 將關鍵字新增至其中一個 \<Keywords\> 元素，提供我們的敏感資訊類型更特定的補強證據，以便表示根據此規則進行比對。或是，移除將造成誤判的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="cbdc0-128">信賴度修改 — 修改敏感資訊類型必須符合其定義中指定之準則，然後才能發出並報告相符項目的信賴度。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="cbdc0-129">上傳新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="cbdc0-p104">重新編目內容以識別敏感資訊。請參閱[手動要求重新編目網站和重新編製網站檢索](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="cbdc0-132">範例：修改「歐盟轉帳卡卡號」敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-132">Example: modify the 'EU Debit Card Number' sensitive information type</span></span>

<span data-ttu-id="cbdc0-p105">在任何系統中改善 DLP 規則的精準度，需要測試範例資料集，而且可能需要反復修改和測試以進行微調。本範例示範如何修改「歐盟轉帳卡卡號」敏感資訊類型來改善其精確度。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the 'EU Debit Card Number' sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="cbdc0-p106">在我們的範例中搜尋歐盟轉帳卡卡號時，該卡號的定義會使用複雜模式嚴格定義為 16 位數，並取決於總和檢查碼的驗證。由於此敏感資訊類型的字串定義，我們無法變更此模式。不過，我們可以進行下列調整，以改善 DLP 在 Office 365 內尋找敏感資訊類型的精確度。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="cbdc0-138">鄰近修改</span><span class="sxs-lookup"><span data-stu-id="cbdc0-138">Proximity modification</span></span>

<span data-ttu-id="cbdc0-p107">我們將縮小視窗，方法為將 \<Entity\> 元素中的 patternProximity 值從 300 個字元修改為 150 個字元。這表示我們的補強證據或關鍵字必須更接近敏感資訊類型，才能表示根據此規則進行比對。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="cbdc0-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="cbdc0-142">關鍵字修改</span><span class="sxs-lookup"><span data-stu-id="cbdc0-142">Keyword modifications</span></span>

<span data-ttu-id="cbdc0-p108">某些關鍵字可能會導致誤判。因而，您可能想要移除關鍵字。以下是這個範例的關鍵字：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="cbdc0-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="cbdc0-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-147">\<Group\></span></span>

<span data-ttu-id="cbdc0-148">\<Term\>corporate card\</Term\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="cbdc0-149">\<Term\>organization card\</Term\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="cbdc0-150">\<Term\>acct nbr\</Term\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="cbdc0-151">\<Term\>acct num\</Term\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="cbdc0-152">\<Term\>acct no\</Term\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="cbdc0-153">…</span><span class="sxs-lookup"><span data-stu-id="cbdc0-153">…</span></span>

<span data-ttu-id="cbdc0-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-154">\</Group\></span></span>

<span data-ttu-id="cbdc0-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="cbdc0-156">信賴度修改</span><span class="sxs-lookup"><span data-stu-id="cbdc0-156">Confidence modifications</span></span>

<span data-ttu-id="cbdc0-p109">如果從定義中移除關鍵字，則您通常想要降低此值，調整您對找到此敏感資訊類型的信賴度。歐盟轉帳卡卡號類型的預設層級是 85。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="cbdc0-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="cbdc0-160">\<Pattern confidenceLevel="85"\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="cbdc0-161">…</span><span class="sxs-lookup"><span data-stu-id="cbdc0-161">…</span></span>

<span data-ttu-id="cbdc0-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-162">\</Pattern\></span></span>

<span data-ttu-id="cbdc0-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="cbdc0-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="cbdc0-164">建立新的自訂敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="cbdc0-165">若要建立新的自訂敏感資訊類型，請先使用內容搜尋：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="cbdc0-166">最佳化 KQL 查詢</span><span class="sxs-lookup"><span data-stu-id="cbdc0-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="cbdc0-167">查看哪些關鍵字最有用</span><span class="sxs-lookup"><span data-stu-id="cbdc0-167">See which keywords are most useful</span></span>

<span data-ttu-id="cbdc0-p110">使用這些結果來建立新的敏感資訊類型。然後，為您的環境最佳化新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="cbdc0-p111">附註： 對於歐盟國家中的個人資料，即將推出許多新的敏感資訊類型。如果您需要建立新的敏感資訊類型，請先對準您環境的自訂資料。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="cbdc0-172">步驟 1 — 使用 KQL 查詢和關鍵字，在您的環境中尋找額外資料</span><span class="sxs-lookup"><span data-stu-id="cbdc0-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="cbdc0-p112">您可能需要建立額外的查詢，以尋找受到 GDPR 約束的個人資料。內容搜尋會使用關鍵字查詢語言 (KQL) 來尋找資料。若沒有敏感資訊類型，無法只使用 KQL，精確地偵測到最敏感的資料。因此，目標是使用內容搜尋來測試和最佳化 KQL 字串，然後使用這些以建立並調整新的敏感資訊類型，在這裡您甚至可以達到更高的精確度。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can't be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="cbdc0-177">使用下列資源，利用 KQL 來制訂和最佳化查詢：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-177">Use these resources to formulate and optimize queries using KQL:</span></span>

- [<span data-ttu-id="cbdc0-178">關鍵字查詢語言 (KQL) 語法參考 (DMC)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [<span data-ttu-id="cbdc0-179">執行內容搜尋</span><span class="sxs-lookup"><span data-stu-id="cbdc0-179">Run a Content Search</span></span>](content-search.md)

<span data-ttu-id="cbdc0-p113">內容搜尋提供另一種資源，協助您開發 KQL 查詢及敏感資訊類型 — 關鍵字。為什麼使用關鍵字清單？您可以取得統計資料，顯示多少個項目比對每一個關鍵字的。這可協助您快速識別哪些關鍵字的效率最好 (最差)。如需搜尋統計資料的詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search)。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).</span></span>

<span data-ttu-id="cbdc0-p114">每一列上的關鍵字是藉由所建立的搜尋查詢中的 OR 運算子來連線。您也可以連續使用關鍵字片語 (以括號括住)。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="cbdc0-187">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-187">For more information, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="cbdc0-188">範例 — 使用內容搜尋來識別電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="cbdc0-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="cbdc0-p115">電子郵件地址會被視為與資料主旨相關的敏感資訊。這是一個簡單範例，示範如何協助內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="cbdc0-p116">無法同時使用 KQL 和關鍵字。分別使用這些工具來調整您的查詢，並判斷可能有助於敏感資訊類型的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p116">KQL and keywords can't be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="cbdc0-193">KQL 查詢</span><span class="sxs-lookup"><span data-stu-id="cbdc0-193">KQL query</span></span>

<span data-ttu-id="cbdc0-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="cbdc0-195">附註：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-195">Notes:</span></span>

-   <span data-ttu-id="cbdc0-196">您可以使用 NEAR 進行鄰近搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-196">You can use NEAR for proximity searches.</span></span>

-   <span data-ttu-id="cbdc0-197">很遺憾，KQL 不支援具有 Regex 類別的查詢 (例如：IdRef="Regex\_email\_address")</span><span class="sxs-lookup"><span data-stu-id="cbdc0-197">Unfortunately, KQL doesn't support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="cbdc0-198">關鍵字</span><span class="sxs-lookup"><span data-stu-id="cbdc0-198">Keywords</span></span>

<span data-ttu-id="cbdc0-p117">在個別行中輸入每一個關鍵字。範例關鍵字：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="cbdc0-201">email address</span><span class="sxs-lookup"><span data-stu-id="cbdc0-201">email address</span></span>

-   <span data-ttu-id="cbdc0-202">mail</span><span class="sxs-lookup"><span data-stu-id="cbdc0-202">mail</span></span>

-   <span data-ttu-id="cbdc0-203">contact</span><span class="sxs-lookup"><span data-stu-id="cbdc0-203">contact</span></span>

-   <span data-ttu-id="cbdc0-204">sender</span><span class="sxs-lookup"><span data-stu-id="cbdc0-204">sender</span></span>

-   <span data-ttu-id="cbdc0-205">recipient</span><span class="sxs-lookup"><span data-stu-id="cbdc0-205">recipient</span></span>

-   <span data-ttu-id="cbdc0-206">cc</span><span class="sxs-lookup"><span data-stu-id="cbdc0-206">cc</span></span>

-   <span data-ttu-id="cbdc0-207">bcc</span><span class="sxs-lookup"><span data-stu-id="cbdc0-207">bcc</span></span>

<span data-ttu-id="cbdc0-208">在此範例中，您可能了解關鍵字不是必要的，並產生許多誤判結果。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="cbdc0-209">步驟 2 — 建立新的自訂敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="cbdc0-p118">在使用 KQL 查詢和關鍵字來識別敏感資訊之後，請使用這些來建立新的自訂敏感資訊類型。在許多情況下，您將需要精密的敏感資訊類型，才能達到正確的精確層級。然後，您可以在 DLP 原則和其他工具中，以及在其他 KQL 查詢內，使用這些自訂的敏感資訊類型與內容搜尋搭配。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you'll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="cbdc0-p119">最佳做法是根據現有的敏感資訊類型建立新的敏感資訊類型。請使用本文稍早所述的相同程序。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="cbdc0-215">範例 — 為電子郵件地址建立新的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="cbdc0-p120">我們將繼續使用電子郵件地址做為範例，因為它使用簡單。下表詳述針對新電子郵件敏感資訊類型的修改建議。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p120">We'll continue with the email address as an example because it's simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cbdc0-218"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-218"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="cbdc0-219"><strong>修改</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="cbdc0-220"><strong>XML 語法範例</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-220"><strong>Example XML syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-221">1</span><span class="sxs-lookup"><span data-stu-id="cbdc0-221">1</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-222">設定 IdRef 屬性</span><span class="sxs-lookup"><span data-stu-id="cbdc0-222">Set the IdRef property</span></span>
<p><span data-ttu-id="cbdc0-p121">在 &lt;Entity&gt; 元素內，修改 &lt;IdMatch&gt; 元素，以便將 idRef 屬性 = 唯一值。此值將指向定義規則運算式以尋找電子郵件地址的元素。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="cbdc0-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-226">2</span><span class="sxs-lookup"><span data-stu-id="cbdc0-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-227">Proximity 屬性</span><span class="sxs-lookup"><span data-stu-id="cbdc0-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="cbdc0-228">在 &lt;Entity&gt; 元素中，patternProximity 的值將從 300 開始。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="cbdc0-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-230">3</span><span class="sxs-lookup"><span data-stu-id="cbdc0-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-231">信賴等級</span><span class="sxs-lookup"><span data-stu-id="cbdc0-231">Confidence level</span></span></p>
<p><span data-ttu-id="cbdc0-p122">將 recommendedConfidence 屬性設為您覺得有信心找到確切相符項目的值。這可能需要利用具有代表性的資料集進行測試，以取得精確結果。請將此值設為 75，做為初始設定。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cbdc0-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-236">前三個項目合併所產生的 XML 如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="cbdc0-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-245">4</span><span class="sxs-lookup"><span data-stu-id="cbdc0-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-246">Regex 元素</span><span class="sxs-lookup"><span data-stu-id="cbdc0-246">Regex element</span></span></p>
<p><span data-ttu-id="cbdc0-247">在 &lt;Entity&gt; 元素下方立即新增 &lt;Regex&gt; 元素，其會定義用來識別電子郵件地址的規則運算式。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="cbdc0-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-249">5</span><span class="sxs-lookup"><span data-stu-id="cbdc0-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-250">關鍵字</span><span class="sxs-lookup"><span data-stu-id="cbdc0-250">Keywords</span></span></p>
<p><span data-ttu-id="cbdc0-p123">在 &lt;Regex&gt; 元素下方新增 &lt;Keyword&gt; 元素，其會定義電子郵件相關之關鍵字的清單。請確保 &lt;Keyword&gt; 元素的 id 值符合 &lt;Entity&gt;&lt;Pattern&gt;元素中的 &lt;Match idRef&gt; 值。必要時，您可以繼續新增自己的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="cbdc0-p124">關鍵字不一定包含在電子郵件的機密資訊類型中。我們提供下列關鍵字做為範例。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cbdc0-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-258">&lt;Term&gt;email&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-259">&lt;Term&gt;email address&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-260">&lt;Term&gt;contact&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-263">6</span><span class="sxs-lookup"><span data-stu-id="cbdc0-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-264">LocalizedStrings 元素</span><span class="sxs-lookup"><span data-stu-id="cbdc0-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="cbdc0-265">在 &lt;LocalizedStrings&gt;&lt;Resource&gt; 元素中，確認您有唯一名稱，可識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cbdc0-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="cbdc0-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="cbdc0-272">利用 PowerShell 和 XML 檔案範例建立新的敏感資訊類型 — Contoso 客戶編號</span><span class="sxs-lookup"><span data-stu-id="cbdc0-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="cbdc0-p125">Contoso 使用 Contoso 客戶編號 (CCN) 來識別其客戶資料庫中的每一個客戶。CCN 由下列分類法組成：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="cbdc0-p126">兩位數，代表建立記錄的年份。Contoso 成立於 2002。因此，最早的可能值是 02。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="cbdc0-p127">三位數，代表建立記錄的夥伴機構。可能的機構值範圍從 000 到 999。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="cbdc0-p128">一個字母字元，代表行業。可能值為 a 到 z，而且應該不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="cbdc0-p129">一個四位數序號。可能的序號值範圍從 0000 到 9999。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="cbdc0-283">CCN 範例：</span><span class="sxs-lookup"><span data-stu-id="cbdc0-283">Example CCNs:</span></span>

> <span data-ttu-id="cbdc0-284">15080P9562</span><span class="sxs-lookup"><span data-stu-id="cbdc0-284">15080P9562</span></span>
>
> <span data-ttu-id="cbdc0-285">14040O1119</span><span class="sxs-lookup"><span data-stu-id="cbdc0-285">14040O1119</span></span>
>
> <span data-ttu-id="cbdc0-286">15020J8317</span><span class="sxs-lookup"><span data-stu-id="cbdc0-286">15020J8317</span></span>
>
> <span data-ttu-id="cbdc0-287">14050E2330</span><span class="sxs-lookup"><span data-stu-id="cbdc0-287">14050E2330</span></span>
>
> <span data-ttu-id="cbdc0-288">16050E2166</span><span class="sxs-lookup"><span data-stu-id="cbdc0-288">16050E2166</span></span>
>
> <span data-ttu-id="cbdc0-289">17040O1118</span><span class="sxs-lookup"><span data-stu-id="cbdc0-289">17040O1118</span></span>

<span data-ttu-id="cbdc0-290">Contoso 一律在內部通信、外部通信、文件等使用 CCN 來表示客戶。他們想要建立自訂的敏感資訊類型，來偵測 CCN 的使用情形，以便可在使用此形式的個人資料時套用保護。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="cbdc0-291">為 Contoso 客戶編號建立新的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="cbdc0-291">Create a new sensitive information type for Contoso customer number</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cbdc0-292"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-292"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="cbdc0-293"><strong>動作</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="cbdc0-294"><strong>結果</strong></span><span class="sxs-lookup"><span data-stu-id="cbdc0-294"><strong>Result</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-295">1</span><span class="sxs-lookup"><span data-stu-id="cbdc0-295">1</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-296">Contoso 使用 PowerShell 和內容搜尋，來尋找符合 CCN 範例集的文件。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="cbdc0-297">#連線到安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="cbdc0-297">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="cbdc0-298">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="cbdc0-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="cbdc0-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="cbdc0-300">#建立並開始搜尋範例資料</span><span class="sxs-lookup"><span data-stu-id="cbdc0-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="cbdc0-301">$searchName = &quot;Sample Customer Information Search&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="cbdc0-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="cbdc0-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="cbdc0-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="cbdc0-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="cbdc0-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-305">2</span><span class="sxs-lookup"><span data-stu-id="cbdc0-305">2</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-p130">Contoso 分析結果。每次使用 CCN，就會使用歐盟格式的日期，也會在鄰近的 300 個字元內使用這些關鍵字的其中一個。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-308">customer number、customer no、customer #、customer#、Contoso customer</span><span class="sxs-lookup"><span data-stu-id="cbdc0-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-309">3</span><span class="sxs-lookup"><span data-stu-id="cbdc0-309">3</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-310">Contoso 已開發下列規則運算式 (RegEx) 模式來識別其 CCN。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="cbdc0-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-312">4</span><span class="sxs-lookup"><span data-stu-id="cbdc0-312">4</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-313">Contoso 已開發下列規則運算式 (RegEx) 模式，以其各個子公司所使用的格式識別歐盟日期。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-314">5</span><span class="sxs-lookup"><span data-stu-id="cbdc0-314">5</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-315">Contoso 使用 PowerShell 來產生三個唯一的 GUID。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-316">#為 RulePack Id、Publisher Id 及 Entity Id 產生唯一的 GUID</span><span class="sxs-lookup"><span data-stu-id="cbdc0-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-317">6</span><span class="sxs-lookup"><span data-stu-id="cbdc0-317">6</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-318">Contoso 為其敏感資訊類型規則定義下列參數。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-319">名稱：Contoso 客戶編號 (CCN)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="cbdc0-320">描述：尋找其他關鍵字和歐盟格式日期的 Contoso 客戶編號 (CCN)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cbdc0-321">7</span><span class="sxs-lookup"><span data-stu-id="cbdc0-321">7</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-322">Contoso 為新的敏感資訊類型建立 XML 檔案，以偵測 Contoso 客戶編號 (CCN)，並使用 UTF-8 編碼方式，在本機檔案系統將此值儲存為 C:\Scripts\ContosoCCN.xml。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-323">請參閱本表下方的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cbdc0-324">8</span><span class="sxs-lookup"><span data-stu-id="cbdc0-324">8</span></span></td>
<td align="left"><span data-ttu-id="cbdc0-325">Contoso 使用下列 PowerShell 建立自訂的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="cbdc0-326">#連線到安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="cbdc0-326">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="cbdc0-327">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="cbdc0-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="cbdc0-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="cbdc0-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="cbdc0-329">#建立新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cbdc0-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="cbdc0-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="cbdc0-331">新的敏感資訊類型的 XML 檔案範例 (步驟 7)</span><span class="sxs-lookup"><span data-stu-id="cbdc0-331">Example XML file for the new sensitive information type (step 7)</span></span>
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
