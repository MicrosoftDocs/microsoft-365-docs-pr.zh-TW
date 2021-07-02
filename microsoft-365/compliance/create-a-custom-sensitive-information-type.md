---
title: 自訂敏感性資訊類型入門
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何在安全性 & 合規性中心建立、修改、移除及測試 DLP 的自訂機密資訊類型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e067bc502267e918bd355d9bf8a1982795255846
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256720"
---
# <a name="get-started-with-custom-sensitive-information-types"></a><span data-ttu-id="4fef9-103">自訂敏感性資訊類型入門</span><span class="sxs-lookup"><span data-stu-id="4fef9-103">Get started with custom sensitive information types</span></span>

<span data-ttu-id="4fef9-104">如果預先設定的敏感性資訊類型不滿足您的需要，可以建立自己的自訂敏感性資訊類型，您可以完全定義這些類型，也可以複製其中一個預先設定的類型並進行修改。</span><span class="sxs-lookup"><span data-stu-id="4fef9-104">If the pre-configured sensitive information types don't meet your needs, you can create your own custom sensitive information types that you fully define or you can copy one of the pre-configured ones and modify it.</span></span>

<span data-ttu-id="4fef9-105">使用此方法建立的自訂敏感性資訊類型將新增到名為 `Microsoft.SCCManaged.CustomRulePack` 的規則套件中。</span><span class="sxs-lookup"><span data-stu-id="4fef9-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="4fef9-106">有兩種方法可以建立新的敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="4fef9-106">There are two ways to create a new sensitive information type:</span></span>

- [<span data-ttu-id="4fef9-107">從頭開始完全定義所有元素</span><span class="sxs-lookup"><span data-stu-id="4fef9-107">from scratch where you fully define all elements</span></span>](#create-a-custom-sensitive-information-type)
- [<span data-ttu-id="4fef9-108">複製和修改現有的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-108">copy and modify an existing sensitive information type</span></span>](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a><span data-ttu-id="4fef9-109">事前準備</span><span class="sxs-lookup"><span data-stu-id="4fef9-109">Before you begin</span></span>

- <span data-ttu-id="4fef9-110">應該熟悉敏感性資訊類型及其組成。</span><span class="sxs-lookup"><span data-stu-id="4fef9-110">You should be familiar with sensitive information types and what they are composed of.</span></span> <span data-ttu-id="4fef9-111">請參閱，[瞭解敏感性資訊類型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-111">See, [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span> <span data-ttu-id="4fef9-112">瞭解以下角色至關重要：</span><span class="sxs-lookup"><span data-stu-id="4fef9-112">It is critical to understand the roles of:</span></span>
    - <span data-ttu-id="4fef9-113">[規則運算式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感性資訊類型使用 Boost.RegEx 5.1.3 引擎</span><span class="sxs-lookup"><span data-stu-id="4fef9-113">[regular expressions](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 sensitive information types uses the Boost.RegEx 5.1.3 engine</span></span>
    - <span data-ttu-id="4fef9-114">關鍵字清單 - 可以在定義您的敏感性資訊類型或從現有關鍵字清單中選擇時建立自己的關鍵字清單</span><span class="sxs-lookup"><span data-stu-id="4fef9-114">keyword lists - you can create your own as you define your sensitive information type or choose from existing keyword lists</span></span>
    - [<span data-ttu-id="4fef9-115">關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="4fef9-115">keyword dictionary</span></span>](create-a-keyword-dictionary.md)
    - [<span data-ttu-id="4fef9-116">函數</span><span class="sxs-lookup"><span data-stu-id="4fef9-116">functions</span></span>](what-the-dlp-functions-look-for.md)
    - [<span data-ttu-id="4fef9-117">信賴等級</span><span class="sxs-lookup"><span data-stu-id="4fef9-117">confidence levels</span></span>](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- <span data-ttu-id="4fef9-118">您必須具備全域管理員或合規性系統管理員的權限，才能透過 UI 建立、測試及部署自訂的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-118">You must have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="4fef9-119">請參閱 Office 365 中的[關於系統管理員角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-119">See [About admin roles](/office365/admin/add-users/about-admin-roles) in Office 365.</span></span>

- <span data-ttu-id="4fef9-120">您的組織必須擁有包括資料外洩防護 (DLP) 的訂用帳戶，例如 Office 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="4fef9-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="4fef9-121">請參閱[郵件原則及符合性](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-121">See [Messaging Policy and Compliance ServiceDescription](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="4fef9-122">Microsoft 客戶服務及支援無法協助您建立自訂分類或規則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-122">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="4fef9-123">支援工程師可以提供有限的功能支援，例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解，但無法保證任何自訂內容比對開發作業將符合您的需求或義務。</span><span class="sxs-lookup"><span data-stu-id="4fef9-123">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

## <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="4fef9-124">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-124">Create a custom sensitive information type</span></span>

<span data-ttu-id="4fef9-125">使用以下步驟可以建立完全定義的新敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-125">Use this procedure to create a new sensitive information type that you fully define.</span></span> 

1. <span data-ttu-id="4fef9-126">在 [合規性中心] 中，前往 **[資料分類]** \>**[敏感性資訊類型]**，然後選擇 **[建立資訊類型]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-126">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose **Create info type**.</span></span>
2. <span data-ttu-id="4fef9-127">填寫 **[名稱]** 和 **[描述]** 的值，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-127">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
3. <span data-ttu-id="4fef9-128">選擇 **[建立模式]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-128">Choose **Create pattern**.</span></span> <span data-ttu-id="4fef9-129">在定義新的敏感性資訊類型時，可以建立多個模式，每個模式具有不同的元素和信賴等級。</span><span class="sxs-lookup"><span data-stu-id="4fef9-129">You can create multiple patterns, each with different elements and confidence levels, as you define your new sensitive information type.</span></span>
4. <span data-ttu-id="4fef9-130">選擇模式的預設信賴等級。</span><span class="sxs-lookup"><span data-stu-id="4fef9-130">Choose the default confidence level for the pattern.</span></span> <span data-ttu-id="4fef9-131">這些值是 **[低信賴等級]**、**[中信賴等級]** 和 **[高信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-131">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
5. <span data-ttu-id="4fef9-132">選擇並定義 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-132">Choose and define **Primary element**.</span></span> <span data-ttu-id="4fef9-133">主要元素可以是帶有選用驗證程式的 **規則運算式**、**關鍵字清單**、**關鍵字字典** 或預先設定的 **函數** 之一。</span><span class="sxs-lookup"><span data-stu-id="4fef9-133">The primary element can be a **Regular expression** with an optional validator, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="4fef9-134">有關 DLP 功能的詳細資訊，請參閱 [DLP 功能尋找的項目](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-134">For more information on DLP functions, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span> <span data-ttu-id="4fef9-135">如需日期及校驗和驗證程式的詳細資訊，請參閱 [正則運算式驗證程式的詳細資訊](#more-information-on-regular-expression-validators)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-135">For more information on the date and the checksum validators, see [More information on regular expression validators](#more-information-on-regular-expression-validators).</span></span>
6. <span data-ttu-id="4fef9-136">填寫 **鄰近的字元** 的值。</span><span class="sxs-lookup"><span data-stu-id="4fef9-136">Fill in a value for **Character proximity**.</span></span>
7. <span data-ttu-id="4fef9-137">(選用) 新增支援元素 (如有)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-137">(Optional) Add supporting elements if you have any.</span></span> <span data-ttu-id="4fef9-138">支援元素可以是帶有選用驗證程式的規則運算式、關鍵字清單、關鍵字字典或預定義的函數之一。</span><span class="sxs-lookup"><span data-stu-id="4fef9-138">Supporting elements can be a regular expression with an optional validator, a keyword list, a keyword dictionary or one of the pre-defined functions.</span></span> <span data-ttu-id="4fef9-139">支援元素可以有自己的 **字元臨近** 設定。</span><span class="sxs-lookup"><span data-stu-id="4fef9-139">Supporting elements can have their own **Character proximity** configuration.</span></span> 
8. <span data-ttu-id="4fef9-140">(選用) 從可用檢查清單中新增 [**其他檢查**](#more-information-on-additional-checks)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-140">(Optional) Add any [**additional checks**](#more-information-on-additional-checks) from the list of available checks.</span></span>
9. <span data-ttu-id="4fef9-141">選擇 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-141">Choose **Create**.</span></span>
10. <span data-ttu-id="4fef9-142">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-142">Choose **Next**.</span></span>
11. <span data-ttu-id="4fef9-143">為此敏感性資訊類型選擇 **[建議的信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-143">Choose the **recommended confidence level** for this sensitive information type.</span></span>
12. <span data-ttu-id="4fef9-144">檢查您的設定並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-144">Check your setting and choose **Submit**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fef9-145">Microsoft 365 會使用搜尋檢索器識別及分類 SharePoint Online 和商務用 OneDrive 中網站中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="4fef9-145">Microsoft 365 uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="4fef9-146">若要在所有現有內容中識別您的新自訂敏感性資訊類型，必須將內容重新編目。</span><span class="sxs-lookup"><span data-stu-id="4fef9-146">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="4fef9-147">內容會根據排程進行編目，但您可以手動重新編目網站集合、清單或文件庫的內容。</span><span class="sxs-lookup"><span data-stu-id="4fef9-147">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="4fef9-148">如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-148">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>

13. <span data-ttu-id="4fef9-149">在 **[資料分類]** 頁面上，將看到列出的所有敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-149">On the **Data classification** page, you'll see all the sensitive information types listed.</span></span> <span data-ttu-id="4fef9-150">選擇 **[重新整理]**，然後瀏覽或使用搜尋工具尋找剛剛建立的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-150">Choose **Refresh** and then browse for or use the search tool to find the sensitive information type you created.</span></span>

## <a name="test-a-sensitive-information-type"></a><span data-ttu-id="4fef9-151">測試敏感資性訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-151">Test a sensitive information type</span></span>

<span data-ttu-id="4fef9-152">可以測試清單中的任何敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-152">You can test any sensitive information type in the list.</span></span> <span data-ttu-id="4fef9-153">我們建議在原則中使用之前，測試建立的每種敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-153">We suggest that you test every sensitive information type that you create before using it in a policy.</span></span>

1. <span data-ttu-id="4fef9-154">準備兩個檔案，比如 Word 文件。</span><span class="sxs-lookup"><span data-stu-id="4fef9-154">Prepare two files, like a Word document.</span></span> <span data-ttu-id="4fef9-155">一個包含與敏感性資訊類型中指定的元素相符的內容，另一個不相符。</span><span class="sxs-lookup"><span data-stu-id="4fef9-155">One with content that matches the elements you specified in your sensitive information type and one that doesn't match.</span></span>
2. <span data-ttu-id="4fef9-156">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從清單中選擇敏感性資訊類型，以開啟 [詳細資訊] 窗格並選擇 **[測試]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-156">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list to open the details pane and choose **Test**.</span></span>
3. <span data-ttu-id="4fef9-157">上傳檔案並選擇 **[測試]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-157">Upload a file and choose **Test**.</span></span>
4. <span data-ttu-id="4fef9-158">在 **[符合結果]** 頁面上，檢閱結果並選擇 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-158">On the **Matches results** page, review the results and choose **Finish**.</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="4fef9-159">在合規性中心內修改自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-159">Modify custom sensitive information types in the Compliance Center</span></span>

1. <span data-ttu-id="4fef9-160">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從要修改的清單中選擇敏感性資訊類型，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-160">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to modify choose **Edit**.</span></span>
2. <span data-ttu-id="4fef9-161">您可以新增其他模式，其中包括唯一的主要元素和支援元素、信賴等級、鄰近的字元和 [**其他檢查**](#more-information-on-additional-checks)，或者編輯/移除現有的模式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-161">You can add other patterns, with unique primary and supporting elements, confidence levels, character proximity, and [**additional checks**](#more-information-on-additional-checks) or edit/remove the existing ones.</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="4fef9-162">移除合規性中心中的自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-162">Remove custom sensitive information types in the Compliance Center</span></span> 

> [!NOTE]
> <span data-ttu-id="4fef9-163">您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-163">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fef9-164">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-164">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="4fef9-165">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從清單中選擇要移除的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-165">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to remove.</span></span>
2. <span data-ttu-id="4fef9-166">在開啟的飛出視窗中，選擇 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-166">In the fly-out that opens, choose **Delete**.</span></span>

## <a name="copy-and-modify-a-sensitive-information-type"></a><span data-ttu-id="4fef9-167">複製和修改敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-167">Copy and modify a sensitive information type</span></span>

<span data-ttu-id="4fef9-168">使用以下步驟可以建立以現有敏感性資訊類型爲依據的新敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-168">Use this procedure to create a new sensitive information type that is based on an existing sensitive information type.</span></span> 

1. <span data-ttu-id="4fef9-169">在 [合規行中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後選擇要複製的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-169">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type that you want to copy.</span></span>
2. <span data-ttu-id="4fef9-170">在飛出視窗中，選擇 **[複製]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-170">In the flyout, choose **Copy**.</span></span>
3. <span data-ttu-id="4fef9-171">在敏感性資訊類型清單中選擇 **[重新整理]**，然後瀏覽或搜尋剛剛建立的副本。</span><span class="sxs-lookup"><span data-stu-id="4fef9-171">Choose **Refresh** in the list of sensitive information types and either browse or search for the copy you just made.</span></span> <span data-ttu-id="4fef9-172">部分字串搜尋有用，所以可以只搜尋 `copy`，搜尋將退回名稱中包含 `copy` 文字的所有敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-172">Partial sting searches work, so you could just search for `copy` and search would return all the sensitive information types with the word `copy` in the name.</span></span> 
4. <span data-ttu-id="4fef9-173">填寫 **[名稱]** 和 **[描述]** 的值，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-173">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
5. <span data-ttu-id="4fef9-174">選擇敏感性資訊類型副本，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-174">Choose your sensitive information type copy and choose **Edit**.</span></span> 
6. <span data-ttu-id="4fef9-175">為新敏感性資訊類型提供新 **[名稱]** 和 **[描述]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-175">Give your new sensitive information type a new **Name** and **Description**.</span></span>
7. <span data-ttu-id="4fef9-176">您可以選擇編輯或移除現有模式，以及新增新模式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-176">You can choose to edit or remove the existing patterns and add new ones.</span></span> <span data-ttu-id="4fef9-177">選擇新模式的預設信賴等級。</span><span class="sxs-lookup"><span data-stu-id="4fef9-177">Choose the default confidence level for the new pattern.</span></span> <span data-ttu-id="4fef9-178">這些值是 **[低信賴等級]**、**[中信賴等級]** 和 **[高信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-178">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
8. <span data-ttu-id="4fef9-179">選擇並定義 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-179">Choose and define **Primary element**.</span></span> <span data-ttu-id="4fef9-180">主要元素可以是 **規則運算式**、**關鍵字列表**、**關鍵字字典** 或預先配置的 **函數** 之一。</span><span class="sxs-lookup"><span data-stu-id="4fef9-180">The primary element can be a **Regular expression**, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="4fef9-181">請參閱，[DLP 功能搜尋的項目](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-181">See, [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
9. <span data-ttu-id="4fef9-182">填寫 **鄰近的字元** 的值。</span><span class="sxs-lookup"><span data-stu-id="4fef9-182">Fill in a value for **Character proximity**.</span></span>
10. <span data-ttu-id="4fef9-183">(選用) 如果有 **支援元素** 或任何 [**其他檢查**](#more-information-on-additional-checks)，請新增它們。</span><span class="sxs-lookup"><span data-stu-id="4fef9-183">(Optional) If you have **Supporting elements** or any [**Additional checks**](#more-information-on-additional-checks) add them.</span></span> <span data-ttu-id="4fef9-184">如果需要，可以將您的 **支援元素** 分組。</span><span class="sxs-lookup"><span data-stu-id="4fef9-184">If needed you can group your **Supporting elements**.</span></span>
11. <span data-ttu-id="4fef9-185">選擇 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-185">Choose **Create**.</span></span>
12. <span data-ttu-id="4fef9-186">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-186">Choose **Next**.</span></span>
13. <span data-ttu-id="4fef9-187">為此敏感性資訊類型選擇 **[建議的信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-187">Choose the **recommended confidence level** for this sensitive information type.</span></span>
14. <span data-ttu-id="4fef9-188">檢查您的設定並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="4fef9-188">Check your setting and choose **Submit**.</span></span>

<span data-ttu-id="4fef9-189">您也可以使用 PowerShell 和 Exact Data Match 功能建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-189">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="4fef9-190">若要深入了解這些方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4fef9-190">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="4fef9-191">在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-191">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="4fef9-192">使用 Exact Data Match (EDM) 建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fef9-192">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-regular-expression-validators"></a><span data-ttu-id="4fef9-193">正則運算式驗證程式的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4fef9-193">More information on regular expression validators</span></span>

### <a name="checksum-validator"></a><span data-ttu-id="4fef9-194">Checksum 驗證程式</span><span class="sxs-lookup"><span data-stu-id="4fef9-194">Checksum validator</span></span>

<span data-ttu-id="4fef9-195">如果您需要在正則運算式中的數位上執行校驗和，您可以使用 *checksum 驗證* 程式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-195">If you need to run a checksum on a digit in a regular expression, you can use the *checksum validator*.</span></span> <span data-ttu-id="4fef9-196">例如，假設您需要為八位數授權號碼建立 SIT，其中最後一個數位是使用 mod 9 計算驗證的校驗和數位。</span><span class="sxs-lookup"><span data-stu-id="4fef9-196">For example, say you need to create a SIT for an eight digit license number where the last digit is a checksum digit that is validated using a mod 9 calculation.</span></span> <span data-ttu-id="4fef9-197">您已設定校驗和演算法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fef9-197">You've set up the checksum algorithm like this:</span></span>
 
<span data-ttu-id="4fef9-198">Sum = 數位 1 \* 加權 1 + number 2 \* 加權 2 + 數位 3 \* 加權 3 + 數位 4 \* 重量 4 + 數位 5 \* 加權 5 + 數位 6 \* 加權 6 + 3 \* 加權 7 + 數位 8 \* 加權 8 Mod 值 = Sum %9 If Mod value = = 2-1 = 1，</span><span class="sxs-lookup"><span data-stu-id="4fef9-198">Sum = digit 1 \* Weight 1 + digit 2 \* weight 2 + digit 3 \* weight 3 + digit 4 \* weight 4 + digit 5 \* weight 5 + digit 6 \* weight 6 + digit 7 \* weight 7 + digit 8 \* weight 8 Mod value = Sum % 9 If Mod value == digit 8 Account number is valid If Mod value != digit 8 Account number is invalid</span></span>

1. <span data-ttu-id="4fef9-199">使用此正則運算式定義主要元素：</span><span class="sxs-lookup"><span data-stu-id="4fef9-199">Define the primary element with this regular expression:</span></span>

`\d{8}`

2. <span data-ttu-id="4fef9-200">然後新增校驗和驗證程式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-200">Then add the checksum validator.</span></span>
3. <span data-ttu-id="4fef9-201">新增以逗號分隔的權重值，檢查碼的位置和 Mod 值的位置。</span><span class="sxs-lookup"><span data-stu-id="4fef9-201">Add the weight values separated by commas, the position of the check digit and the Mod value.</span></span> <span data-ttu-id="4fef9-202">如需模運算的詳細資訊，請參閱 [模數](https://en.wikipedia.org/wiki/Modulo_operation)作業。</span><span class="sxs-lookup"><span data-stu-id="4fef9-202">For more information on the Modulo operation, see [Modulo operation](https://en.wikipedia.org/wiki/Modulo_operation).</span></span>

> [!NOTE]
> <span data-ttu-id="4fef9-203">如果檢查碼不是校驗和計算的一部分，請使用0做為檢查碼的權重。</span><span class="sxs-lookup"><span data-stu-id="4fef9-203">If the check digit is not part of the checksum calculation then use 0 as the weight for the check digit.</span></span> <span data-ttu-id="4fef9-204">例如，在上述的情況下，如果檢查碼不是用來計算檢查碼碼，就會等於0。</span><span class="sxs-lookup"><span data-stu-id="4fef9-204">For example, in the above case weight 8 will be equal to 0 if the check digit is not to be used for calculating the check digit.</span></span>  <span data-ttu-id="4fef9-205">Modulo_operation) 。</span><span class="sxs-lookup"><span data-stu-id="4fef9-205">Modulo_operation).</span></span>

![已設定校驗和驗證程式的螢幕擷取畫面](../media/checksum-validator.png)

### <a name="date-validator"></a><span data-ttu-id="4fef9-207">日期驗證程式</span><span class="sxs-lookup"><span data-stu-id="4fef9-207">Date validator</span></span>

<span data-ttu-id="4fef9-208">如果內嵌在正則運算式中的日期值為您建立的新模式的一部分，您可以使用 *日期驗證* 程式來測試它是否符合您的準則。</span><span class="sxs-lookup"><span data-stu-id="4fef9-208">If a date value that is embedded in regular expression is part of a new pattern you are creating, you can use the *date validator* to test that it meets your criteria.</span></span> <span data-ttu-id="4fef9-209">例如，假設您想要為九位數的雇員識別碼建立 SIT。</span><span class="sxs-lookup"><span data-stu-id="4fef9-209">For example, say you want to create a SIT for a nine digit employee identification number.</span></span> <span data-ttu-id="4fef9-210">前六位數位是以 DDMMYY 格式雇用的日期，最後三個是隨機產生的數位。</span><span class="sxs-lookup"><span data-stu-id="4fef9-210">The first six digits are the date of hire in DDMMYY format and the last three are randomly generated numbers.</span></span> <span data-ttu-id="4fef9-211">驗證前六位數是否為正確的格式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-211">To validate that the first six digits are in the correct format.</span></span> 

1. <span data-ttu-id="4fef9-212">使用此正則運算式定義主要元素：</span><span class="sxs-lookup"><span data-stu-id="4fef9-212">Define the primary element with this regular expression:</span></span>

`\d{9}`

2. <span data-ttu-id="4fef9-213">然後新增日期驗證程式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-213">Then add the date validator.</span></span>
3. <span data-ttu-id="4fef9-214">選取日期格式及起始位移。</span><span class="sxs-lookup"><span data-stu-id="4fef9-214">Select the date format and the start offset.</span></span> <span data-ttu-id="4fef9-215">因為日期字串是前六位數，所以位移是 `0` 。</span><span class="sxs-lookup"><span data-stu-id="4fef9-215">Since the date string is the first six digits, the offset is `0`.</span></span>

![設定之日期驗證程式的螢幕擷取畫面](../media/date-validator.png)

### <a name="functional-processors-as-validators"></a><span data-ttu-id="4fef9-217">功能處理器為驗證程式</span><span class="sxs-lookup"><span data-stu-id="4fef9-217">Functional processors as validators</span></span>

<span data-ttu-id="4fef9-218">您可以使用函數處理器，作為一些最常用的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-218">You can use function processors for some of the most commonly used SITs as validators.</span></span> <span data-ttu-id="4fef9-219">這可讓您定義您自己的正則運算式，同時確保它們會透過 SIT 所需的其他檢查。</span><span class="sxs-lookup"><span data-stu-id="4fef9-219">This allows you to define your own regular expression while ensuring they pass the additional checks required by the SIT.</span></span> <span data-ttu-id="4fef9-220">例如，Func_India_Aadhar 會確定您所定義的自訂正則運算式已傳遞印度 Aadhar 卡片所需的驗證邏輯。</span><span class="sxs-lookup"><span data-stu-id="4fef9-220">For example, Func_India_Aadhar will ensure that the custom regular expression defined by you passes the validation logic required for Indian Aadhar card.</span></span> <span data-ttu-id="4fef9-221">如需可用作驗證程式之 DLP 功能的詳細資訊，請參閱 [dlp 功能的尋找目標](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-221">For more information on DLP functions that can be used as validators, see [What the DLP functions look for](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for).</span></span> 

### <a name="luhn-check-validator"></a><span data-ttu-id="4fef9-222">Luhn 檢查驗證程式</span><span class="sxs-lookup"><span data-stu-id="4fef9-222">Luhn check validator</span></span>

<span data-ttu-id="4fef9-223">如果您有自訂的機密資訊類型，且包含應傳遞 [Luhn 演算法](https://en.wikipedia.org/wiki/Luhn_algorithm)的正則運算式，您可以使用 Luhn 檢查驗證程式。</span><span class="sxs-lookup"><span data-stu-id="4fef9-223">You can use the Luhn check validator if you have a custom Sensitive information type that includes a regular expression which should pass the [Luhn algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm).</span></span>

## <a name="more-information-on-additional-checks"></a><span data-ttu-id="4fef9-224">其他檢查的其他資訊</span><span class="sxs-lookup"><span data-stu-id="4fef9-224">More information on additional checks</span></span>

<span data-ttu-id="4fef9-225">以下是可用其他檢查的定義和一些範例。</span><span class="sxs-lookup"><span data-stu-id="4fef9-225">Here are the definitions and some examples for the available additional checks.</span></span>

<span data-ttu-id="4fef9-226">**排除特定相符項目**：這項檢查可讓您定義在偵測所編輯模式的相符項目時要排除的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="4fef9-226">**Exclude specific matches**: This check lets you define keywords to exclude when detecting matches for the pattern you are editing.</span></span> <span data-ttu-id="4fef9-227">例如，您可以排除測試信用卡號碼 (例如 '4111111111111111')，讓這些號碼無法相符為有效的號碼。</span><span class="sxs-lookup"><span data-stu-id="4fef9-227">For example, you might exclude test credit card numbers like '4111111111111111' so that they're not matched as a valid number.</span></span>

<span data-ttu-id="4fef9-228">**以字元開頭或不以字元開頭**：這項檢查可讓您定義相符項目必須或不能以哪些字元開頭。</span><span class="sxs-lookup"><span data-stu-id="4fef9-228">**Starts or doesn't start with characters**: This check lets you define the characters that the matched items must or must not start with.</span></span> <span data-ttu-id="4fef9-229">例如，如果您希望模式只偵測開頭為 41、42 或 43 的信用卡號碼，請選取 **[開頭為]**，然後新增 41、42 和 43 到清單中，以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="4fef9-229">For example, if you want the pattern to detect only credit card numbers that start with 41, 42, or 43, select **Starts with** and add 41, 42, and 43 to the list, separated by commas.</span></span> 

<span data-ttu-id="4fef9-230">**以字元結束或不以字元結束**：這項檢查可讓您定義相符項目必須或不能以哪些字元結束。</span><span class="sxs-lookup"><span data-stu-id="4fef9-230">**Ends or doesn't end with characters**: This check lets you define the characters that the matched items must or must not end with.</span></span> <span data-ttu-id="4fef9-231">例如，如果您的員工識別碼的結尾不能是 0 或 1，請選取 **[結尾不是]**，然後新增 0 和 1 到清單中，以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="4fef9-231">For example, if your Employee ID number cannot end with 0 or 1, select **Doesn't end with** and add 0 and 1 to the list, separated by commas.</span></span>

<span data-ttu-id="4fef9-232">**排除重複字元**：此檢查可讓您忽略所有數字都相同的相符項目。</span><span class="sxs-lookup"><span data-stu-id="4fef9-232">**Exclude duplicate characters**: This check lets you ignore matches in which all the digits are the same.</span></span> <span data-ttu-id="4fef9-233">例如，如果六位數的員工識別碼不能使用所有數字都相同的識別碼，您可以選取 **[排除重複字元]**，從員工識別碼的有效相符項目清單中排除 111111、222222、333333、444444、555555、666666、777777、888888、999999 和 000000。</span><span class="sxs-lookup"><span data-stu-id="4fef9-233">For example, if the six digit employee ID number cannot have all the digits be the same, you can select **Exclude duplicate characters** to exclude 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999, and 000000 from the list of valid matches for the employee ID.</span></span>

<span data-ttu-id="4fef9-234">**包含或排除首碼**：此檢查可讓您定義在相符實體之前必須立即找到或不能立即找到的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="4fef9-234">**Include or exclude prefixes**: This check lets you define the keywords that must or must not be found immediately before the matching entity.</span></span> <span data-ttu-id="4fef9-235">根據您的選項，如果實體前面有您在這裡指定的首碼，則實體會相符或不相符。</span><span class="sxs-lookup"><span data-stu-id="4fef9-235">Depending on your selection, entities will be matched or not matched if they're preceded by the prefixes you include here.</span></span> <span data-ttu-id="4fef9-236">例如，如果您 **排除** 首碼 **GUID:**，則 **GUID:** 前的任何實體不會被視為相符項目。</span><span class="sxs-lookup"><span data-stu-id="4fef9-236">For example, if you **Exclude** the prefix **GUID:**, any entity that's preceded by **GUID:** won't be considered a match.</span></span>

<span data-ttu-id="4fef9-237">**包含或排除尾碼**：此檢查可讓您定義在相符實體之後必須立即找到或不能立即找到的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="4fef9-237">**Include or exclude suffixes** This check lets you define the keywords that must or must not be found immediately after the matching entity.</span></span> <span data-ttu-id="4fef9-238">根據您的選項，如果實體後面接著您在這裡指定的尾碼，則實體會相符或不相符。</span><span class="sxs-lookup"><span data-stu-id="4fef9-238">Depending on your selection, entities will be matched or not matched if they're followed by the suffixes you include here.</span></span> <span data-ttu-id="4fef9-239">例如，如果您 **排除** 尾碼 **GUID:**，則 **GUID:** 後面接著的文字不會被視為相符項目。</span><span class="sxs-lookup"><span data-stu-id="4fef9-239">For example, if you **Exclude** the suffix **:GUID**, any text that's followed by **:GUID** won't be matched.</span></span>


> [!NOTE]
> <span data-ttu-id="4fef9-240">Microsoft 365資訊保護支援雙位元組字元組語言：</span><span class="sxs-lookup"><span data-stu-id="4fef9-240">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
> - <span data-ttu-id="4fef9-241">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="4fef9-241">Chinese (simplified)</span></span>
> - <span data-ttu-id="4fef9-242">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="4fef9-242">Chinese (traditional)</span></span>
> - <span data-ttu-id="4fef9-243">韓文</span><span class="sxs-lookup"><span data-stu-id="4fef9-243">Korean</span></span>
> - <span data-ttu-id="4fef9-244">日文</span><span class="sxs-lookup"><span data-stu-id="4fef9-244">Japanese</span></span>
>
><span data-ttu-id="4fef9-245">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fef9-245">This support is available for sensitive information types.</span></span> <span data-ttu-id="4fef9-246">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="4fef9-246">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="4fef9-247">若要偵測包含中文/日文字元和單一位元組字元的模式，或是偵測包含中文/日語和英文的模式，請定義關鍵字或 RegEx 的兩個變體。</span><span class="sxs-lookup"><span data-stu-id="4fef9-247">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span> <span data-ttu-id="4fef9-248">例如，若要偵測關鍵字（如 "機密的document"），請使用關鍵字的兩個變體;一個具有介於日文和英文文字之間的空格，另一個在日文和英文文字之間沒有空格的空格。</span><span class="sxs-lookup"><span data-stu-id="4fef9-248">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="4fef9-249">因此，在 SIT 中新增的關鍵字應該是 "機密的 document" 和 "機密的document"。</span><span class="sxs-lookup"><span data-stu-id="4fef9-249">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="4fef9-250">同樣地，若要偵測片語 "東京オリンピック 2020"，應使用兩個變體;"東京オリンピック 2020" 和 "東京オリンピック 2020"。</span><span class="sxs-lookup"><span data-stu-id="4fef9-250">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> <span data-ttu-id="4fef9-251">使用雙位元組連字號或雙位元組句點建立 RegEx 時，請務必要對像是一個字元的轉義符，以在 RegEx 中轉義連字號或句點。</span><span class="sxs-lookup"><span data-stu-id="4fef9-251">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="4fef9-252">以下是範例參考的範例：</span><span class="sxs-lookup"><span data-stu-id="4fef9-252">Here is a sample regex for reference:</span></span>
    - <span data-ttu-id="4fef9-253"> (？ <！ \d)  ( [4] [0-9] {3} [ \- ？ \-\t]\ * [0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="4fef9-253">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
> <span data-ttu-id="4fef9-254">我們建議您在關鍵字清單中使用字串比對，而不是字相符。</span><span class="sxs-lookup"><span data-stu-id="4fef9-254">We recommend using a string match instead of a word match in a keyword list.</span></span>
