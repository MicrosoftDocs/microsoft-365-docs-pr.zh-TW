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
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全性與合規性中心的圖形使用者介面中建立、修改、移除及測試 DLP 的自訂敏感性資訊類型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f0f6b68e9f952e0d52ce7cb71ccf03913584f4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929349"
---
# <a name="get-started-with-custom-sensitive-information-types"></a><span data-ttu-id="c55ac-103">自訂敏感性資訊類型入門</span><span class="sxs-lookup"><span data-stu-id="c55ac-103">Get started with custom sensitive information types</span></span>

<span data-ttu-id="c55ac-104">如果預先設定的敏感性資訊類型不滿足您的需要，可以建立自己的自訂敏感性資訊類型，您可以完全定義這些類型，也可以複製其中一個預先設定的類型並進行修改。</span><span class="sxs-lookup"><span data-stu-id="c55ac-104">If the pre-configured sensitive information types don't meet your needs, you can create your own custom sensitive information types that you fully define or you can copy one of the pre-configured ones and modify it.</span></span>

<span data-ttu-id="c55ac-105">使用此方法建立的自訂敏感性資訊類型將新增到名為 `Microsoft.SCCManaged.CustomRulePack` 的規則套件中。</span><span class="sxs-lookup"><span data-stu-id="c55ac-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="c55ac-106">有兩種方法可以建立新的敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="c55ac-106">There are two ways to create a new sensitive information type:</span></span>

- [<span data-ttu-id="c55ac-107">從頭開始完全定義所有元素</span><span class="sxs-lookup"><span data-stu-id="c55ac-107">from scratch where you fully define all elements</span></span>](#create-a-custom-sensitive-information-type)
- [<span data-ttu-id="c55ac-108">複製和修改現有的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-108">copy and modify an existing sensitive information type</span></span>](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a><span data-ttu-id="c55ac-109">事前準備</span><span class="sxs-lookup"><span data-stu-id="c55ac-109">Before you begin</span></span>

- <span data-ttu-id="c55ac-110">應該熟悉敏感性資訊類型及其組成。</span><span class="sxs-lookup"><span data-stu-id="c55ac-110">You should be familiar with sensitive information types and what they are composed of.</span></span> <span data-ttu-id="c55ac-111">請參閱，[瞭解敏感性資訊類型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-111">See, [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span> <span data-ttu-id="c55ac-112">瞭解以下角色至關重要：</span><span class="sxs-lookup"><span data-stu-id="c55ac-112">It is critical to understand the roles of:</span></span>
    - <span data-ttu-id="c55ac-113">[規則運算式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感性資訊類型使用 Boost.RegEx 5.1.3 引擎</span><span class="sxs-lookup"><span data-stu-id="c55ac-113">[regular expressions](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 sensitive information types uses the Boost.RegEx 5.1.3 engine</span></span>
    - <span data-ttu-id="c55ac-114">關鍵字清單 - 可以在定義您的敏感性資訊類型或從現有關鍵字清單中選擇時建立自己的關鍵字清單</span><span class="sxs-lookup"><span data-stu-id="c55ac-114">keyword lists - you can create your own as you define your sensitive information type or choose from existing keyword lists</span></span>
    - [<span data-ttu-id="c55ac-115">關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="c55ac-115">keyword dictionary</span></span>](create-a-keyword-dictionary.md)
    - [<span data-ttu-id="c55ac-116">函數</span><span class="sxs-lookup"><span data-stu-id="c55ac-116">functions</span></span>](what-the-dlp-functions-look-for.md)
    - [<span data-ttu-id="c55ac-117">信賴等級</span><span class="sxs-lookup"><span data-stu-id="c55ac-117">confidence levels</span></span>](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- <span data-ttu-id="c55ac-118">您必須具備全域管理員或合規性系統管理員的權限，才能透過 UI 建立、測試及部署自訂的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-118">You must have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="c55ac-119">請參閱 Office 365 中的[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-119">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="c55ac-120">您的組織必須擁有包括資料外洩防護 (DLP) 的訂用帳戶，例如 Office 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="c55ac-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="c55ac-121">請參閱[郵件原則及符合性](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-121">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="c55ac-122">Microsoft 客戶服務及支援無法協助您建立自訂分類或規則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="c55ac-122">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="c55ac-123">支援工程師可以提供有限的功能支援，例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解，但無法保證任何自訂內容比對開發作業將符合您的需求或義務。</span><span class="sxs-lookup"><span data-stu-id="c55ac-123">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

## <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="c55ac-124">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-124">Create a custom sensitive information type</span></span>

<span data-ttu-id="c55ac-125">使用以下步驟可以建立完全定義的新敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-125">Use this procedure to create a new sensitive information type that you fully define.</span></span> 

1. <span data-ttu-id="c55ac-126">在 [合規性中心] 中，前往 **[資料分類]** \>**[敏感性資訊類型]**，然後選擇 **[建立資訊類型]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-126">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose **Create info type**.</span></span>
2. <span data-ttu-id="c55ac-127">填寫 **[名稱]** 和 **[描述]** 的值，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-127">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
3. <span data-ttu-id="c55ac-128">選擇 **[建立模式]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-128">Choose **Create pattern**.</span></span> <span data-ttu-id="c55ac-129">在定義新的敏感性資訊類型時，可以建立多個模式，每個模式具有不同的元素和信賴等級。</span><span class="sxs-lookup"><span data-stu-id="c55ac-129">You can create multiple patterns, each with different elements and confidence levels, as you define your new sensitive information type.</span></span>
4. <span data-ttu-id="c55ac-130">選擇模式的預設信賴等級。</span><span class="sxs-lookup"><span data-stu-id="c55ac-130">Choose the default confidence level for the pattern.</span></span> <span data-ttu-id="c55ac-131">這些值是 **[低信賴等級]**、**[中信賴等級]** 和 **[高信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-131">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
5. <span data-ttu-id="c55ac-132">選擇並定義 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-132">Choose and define **Primary element**.</span></span> <span data-ttu-id="c55ac-133">主要元素可以是帶有選用驗證程式的 **規則運算式**、**關鍵字清單**、**關鍵字字典** 或預先設定的 **函數** 之一。</span><span class="sxs-lookup"><span data-stu-id="c55ac-133">The primary element can be a **Regular expression** with an optional validator, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="c55ac-134">有關 DLP 功能的詳細資訊，請參閱 [DLP 功能尋找的項目](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-134">For more information on DLP functions, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
6. <span data-ttu-id="c55ac-135">填寫 **鄰近的字元** 的值。</span><span class="sxs-lookup"><span data-stu-id="c55ac-135">Fill in a value for **Character proximity**.</span></span>
7. <span data-ttu-id="c55ac-136">(選用) 新增支援元素 (如有)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-136">(Optional) Add supporting elements if you have any.</span></span> <span data-ttu-id="c55ac-137">支援元素可以是帶有選用驗證程式的規則運算式、關鍵字清單、關鍵字字典或預定義的函數之一。</span><span class="sxs-lookup"><span data-stu-id="c55ac-137">Supporting elements can be a regular expression with an optional validator, a keyword list, a keyword dictionary or one of the pre-defined functions.</span></span> 
8.  <span data-ttu-id="c55ac-138">(選用) 從可用檢查清單中新增其他檢查</span><span class="sxs-lookup"><span data-stu-id="c55ac-138">(Optional) Add additional checks from the list of available checks</span></span>
9. <span data-ttu-id="c55ac-139">選擇 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-139">Choose **Create**.</span></span>
10. <span data-ttu-id="c55ac-140">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-140">Choose **Next**.</span></span>
11. <span data-ttu-id="c55ac-141">為此敏感性資訊類型選擇 **[建議的信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-141">Choose the **recommended confidence level** for this sensitive information type.</span></span>
12. <span data-ttu-id="c55ac-142">檢查您的設定並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-142">Check your setting and choose **Submit**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c55ac-143">Microsoft 365 會使用搜尋檢索器識別及分類 SharePoint Online 和商務用 OneDrive 中網站中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="c55ac-143">Microsoft 365 uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="c55ac-144">若要在所有現有內容中識別您的新自訂敏感性資訊類型，必須將內容重新編目。</span><span class="sxs-lookup"><span data-stu-id="c55ac-144">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="c55ac-145">內容會根據排程進行編目，但您可以手動重新編目網站集合、清單或文件庫的內容。</span><span class="sxs-lookup"><span data-stu-id="c55ac-145">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="c55ac-146">如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-146">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

13. <span data-ttu-id="c55ac-147">在 **[資料分類]** 頁面上，將看到列出的所有敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-147">On the **Data classification** page, you'll see all the sensitive information types listed.</span></span> <span data-ttu-id="c55ac-148">選擇 **[重新整理]**，然後瀏覽或使用搜尋工具尋找剛剛建立的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-148">Choose **Refresh** and then browse for or use the search tool to find the sensitive information type you just created.</span></span>

## <a name="test-a-sensitive-information-type"></a><span data-ttu-id="c55ac-149">測試敏感資性訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-149">Test a sensitive information type</span></span>

<span data-ttu-id="c55ac-150">可以測試清單中的任何敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-150">You can test any sensitive information type in the list.</span></span> <span data-ttu-id="c55ac-151">我們建議在原則中使用之前，測試建立的每種敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-151">We suggest that you test every sensitive information type that you create before using it in a policy.</span></span>

1. <span data-ttu-id="c55ac-152">準備兩個檔案，比如 Word 文件。</span><span class="sxs-lookup"><span data-stu-id="c55ac-152">Prepare two files, like a Word document.</span></span> <span data-ttu-id="c55ac-153">一個包含與敏感性資訊類型中指定的元素相符的內容，另一個不相符。</span><span class="sxs-lookup"><span data-stu-id="c55ac-153">One with content that matches the elements you specified in your sensitive information type and one that doesn't match.</span></span>
2. <span data-ttu-id="c55ac-154">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從清單中選擇敏感性資訊類型，以開啟 [詳細資訊] 窗格並選擇 **[測試]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-154">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list to open the details pane and choose **Test**.</span></span>
3. <span data-ttu-id="c55ac-155">上傳檔案並選擇 **[測試]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-155">Upload a file and choose **Test**.</span></span>
4. <span data-ttu-id="c55ac-156">在 **[符合結果]** 頁面上，檢閱結果並選擇 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-156">On the **Matches results** page, review the results and choose **Finish**.</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="c55ac-157">在合規性中心內修改自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-157">Modify custom sensitive information types in the Compliance Center</span></span>

1. <span data-ttu-id="c55ac-158">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從要修改的清單中選擇敏感性資訊類型，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-158">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to modify choose **Edit**.</span></span>
2. <span data-ttu-id="c55ac-159">可以新增其他模式，其中包括唯一的主要元素和支援元素、信賴等級、鄰近的字元和其他檢查，或者編輯/移除現有的模式。</span><span class="sxs-lookup"><span data-stu-id="c55ac-159">You can add other patterns, with unique primary and supporting elements, confidence levels, character proximity, and additional checks or edit/remove the existing ones.</span></span> <span data-ttu-id="c55ac-160">有關詳細資訊，請參閱[建立自訂敏感性資訊類型](#create-a-custom-sensitive-information-type)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-160">For more information, see [Create a custom sensitive information type](#create-a-custom-sensitive-information-type).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="c55ac-161">移除合規性中心中的自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-161">Remove custom sensitive information types in the Compliance Center</span></span> 

> [!NOTE]
> <span data-ttu-id="c55ac-162">您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-162">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c55ac-163">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-163">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="c55ac-164">在 [合規性中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後從清單中選擇要移除的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-164">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to remove.</span></span>
2. <span data-ttu-id="c55ac-165">在開啟的飛出視窗中，選擇 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-165">In the fly-out that opens, choose **Delete**.</span></span>

## <a name="copy-and-modify-a-sensitive-information-type"></a><span data-ttu-id="c55ac-166">複製和修改敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-166">Copy and modify a sensitive information type</span></span>

<span data-ttu-id="c55ac-167">使用以下步驟可以建立以現有敏感性資訊類型爲依據的新敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-167">Use this procedure to create a new sensitive information type that is based on an existing sensitive information type.</span></span> 

1. <span data-ttu-id="c55ac-168">在 [合規行中心] 中，前往 **[資料分類]** \> **[敏感性資訊類型]**，然後選擇要複製的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-168">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type that you want to copy.</span></span>
2. <span data-ttu-id="c55ac-169">在飛出視窗中，選擇 **[複製]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-169">In the flyout, choose **Copy**.</span></span>
3. <span data-ttu-id="c55ac-170">在敏感性資訊類型清單中選擇 **[重新整理]**，然後瀏覽或搜尋剛剛建立的副本。</span><span class="sxs-lookup"><span data-stu-id="c55ac-170">Choose **Refresh** in the list of sensitive information types and either browse or search for the copy you just made.</span></span> <span data-ttu-id="c55ac-171">部分字串搜尋有用，所以可以只搜尋 `copy`，搜尋將退回名稱中包含 `copy` 文字的所有敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-171">Partial sting searches work, so you could just search for `copy` and search would return all the sensitive information types with the word `copy` in the name.</span></span> 
4. <span data-ttu-id="c55ac-172">填寫 **[名稱]** 和 **[描述]** 的值，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-172">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
5. <span data-ttu-id="c55ac-173">選擇敏感性資訊類型副本，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-173">Choose your sensitive information type copy and choose **Edit**.</span></span> 
6. <span data-ttu-id="c55ac-174">為新敏感性資訊類型提供新 **[名稱]** 和 **[描述]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-174">Give your new sensitive information type a new **Name** and **Description**.</span></span>
7. <span data-ttu-id="c55ac-175">您可以選擇編輯或移除現有模式，以及新增新模式。</span><span class="sxs-lookup"><span data-stu-id="c55ac-175">You can choose to edit or remove the existing patterns and add new ones.</span></span> <span data-ttu-id="c55ac-176">選擇新模式的預設信賴等級。</span><span class="sxs-lookup"><span data-stu-id="c55ac-176">Choose the default confidence level for the new pattern.</span></span> <span data-ttu-id="c55ac-177">這些值是 **[低信賴等級]**、**[中信賴等級]** 和 **[高信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-177">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
8. <span data-ttu-id="c55ac-178">選擇並定義 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-178">Choose and define **Primary element**.</span></span> <span data-ttu-id="c55ac-179">主要元素可以是 **規則運算式**、**關鍵字列表**、**關鍵字字典** 或預先配置的 **函數** 之一。</span><span class="sxs-lookup"><span data-stu-id="c55ac-179">The primary element can be a **Regular expression**, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="c55ac-180">請參閱，[DLP 功能搜尋的項目](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-180">See, [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
9. <span data-ttu-id="c55ac-181">填寫 **鄰近的字元** 的值。</span><span class="sxs-lookup"><span data-stu-id="c55ac-181">Fill in a value for **Character proximity**.</span></span>
10. <span data-ttu-id="c55ac-182">(選用) 如果有 **支援元素** 或任何 **其他檢查**，請新增它們。</span><span class="sxs-lookup"><span data-stu-id="c55ac-182">(Optional) If you have **Supporting elements** or any **Additional checks** add them.</span></span> <span data-ttu-id="c55ac-183">如果需要，可以將您的 **支援元素** 分組。</span><span class="sxs-lookup"><span data-stu-id="c55ac-183">If needed you can group your **Supporting elements**.</span></span>
11. <span data-ttu-id="c55ac-184">選擇 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-184">Choose **Create**.</span></span>
12. <span data-ttu-id="c55ac-185">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-185">Choose **Next**.</span></span>
13. <span data-ttu-id="c55ac-186">為此敏感性資訊類型選擇 **[建議的信賴等級]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-186">Choose the **recommended confidence level** for this sensitive information type.</span></span>
14. <span data-ttu-id="c55ac-187">檢查您的設定並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="c55ac-187">Check your setting and choose **Submit**.</span></span>

<span data-ttu-id="c55ac-188">您也可以使用 PowerShell 和 Exact Data Match 功能建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-188">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="c55ac-189">若要深入了解這些方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c55ac-189">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="c55ac-190">在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-190">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="c55ac-191">使用 Exact Data Match (EDM) 建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="c55ac-191">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
 
> [!NOTE]
> <span data-ttu-id="c55ac-192">Microsoft 365 資訊保護在預覽版中支援下列雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="c55ac-192">Microsoft 365 Information Protection supports, in preview, double byte character set languages for:</span></span>
> - <span data-ttu-id="c55ac-193">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="c55ac-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="c55ac-194">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="c55ac-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="c55ac-195">韓文</span><span class="sxs-lookup"><span data-stu-id="c55ac-195">Korean</span></span>
> - <span data-ttu-id="c55ac-196">日文</span><span class="sxs-lookup"><span data-stu-id="c55ac-196">Japanese</span></span>
>
><span data-ttu-id="c55ac-197">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c55ac-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="c55ac-198">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>