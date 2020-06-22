---
title: 在安全性與合規性中心建立自訂敏感性資訊類型
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
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818062"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="ba64f-103">在安全性與合規性中心建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="ba64f-104">閱讀本文，在安全性與合規性中心建立[自訂敏感性資訊類型](custom-sensitive-info-types.md) ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="ba64f-104">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="ba64f-105">透過使用此方法，您建立的自訂敏感性資訊類型會新增到名為 `Microsoft.SCCManaged.CustomRulePack` 的規則套件。</span><span class="sxs-lookup"><span data-stu-id="ba64f-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="ba64f-106">您也可以使用 PowerShell 和 Exact Data Match 功能建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="ba64f-107">若要深入了解這些方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ba64f-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="ba64f-108">在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="ba64f-109">使用 Exact Data Match (EDM) 建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="ba64f-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="ba64f-110">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="ba64f-111">您必須具備全域管理員或合規性系統管理員的權限，才能透過 UI 建立、測試及部署自訂的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-111">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="ba64f-112">請參閱 Office 365 中的[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="ba64f-112">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="ba64f-113">您的組織必須擁有包括資料外洩防護 (DLP) 的訂用帳戶，例如 Office 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="ba64f-113">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="ba64f-114">請參閱[郵件原則及符合性](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="ba64f-114">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="ba64f-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span><span class="sxs-lookup"><span data-stu-id="ba64f-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span></span> <span data-ttu-id="ba64f-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="ba64f-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="ba64f-117">Microsoft 客戶服務及支援無法協助您建立自訂分類或規則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="ba64f-117">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="ba64f-118">支援工程師可以提供有限的功能支援，例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解，但無法保證任何自訂內容比對開發作業將符合您的需求或義務。</span><span class="sxs-lookup"><span data-stu-id="ba64f-118">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="ba64f-119">DLP 會使用搜尋檢索器識別及分類 SharePoint Online 和商務用 OneDrive 中網站中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="ba64f-119">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="ba64f-120">若要在所有現有內容中識別您的新自訂敏感性資訊類型，必須將內容重新編目。</span><span class="sxs-lookup"><span data-stu-id="ba64f-120">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="ba64f-121">內容會根據排程進行編目，但您可以手動重新編目網站集合、清單或文件庫的內容。</span><span class="sxs-lookup"><span data-stu-id="ba64f-121">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="ba64f-122">如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="ba64f-122">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="ba64f-123">在安全性與合規性中心建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-123">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="ba64f-124">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="ba64f-124">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="ba64f-125">這些設定不言而喻，並會在精靈的關聯頁面上加以說明：</span><span class="sxs-lookup"><span data-stu-id="ba64f-125">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="ba64f-126">**名稱**</span><span class="sxs-lookup"><span data-stu-id="ba64f-126">**Name**</span></span>

- <span data-ttu-id="ba64f-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="ba64f-127">**Description**</span></span>

- <span data-ttu-id="ba64f-128">**近似值**</span><span class="sxs-lookup"><span data-stu-id="ba64f-128">**Proximity**</span></span>

- <span data-ttu-id="ba64f-129">**信賴等級**</span><span class="sxs-lookup"><span data-stu-id="ba64f-129">**Confidence level**</span></span>

- <span data-ttu-id="ba64f-130">**主要模式元素** (關鍵字、規則運算式或字典)</span><span class="sxs-lookup"><span data-stu-id="ba64f-130">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="ba64f-131">選用的**支援模式元素** (關鍵字、規則運算式或字典) 及其對應**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="ba64f-131">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="ba64f-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span><span class="sxs-lookup"><span data-stu-id="ba64f-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span></span> <span data-ttu-id="ba64f-133">To create this custom sensitive information type, do the following steps:</span><span class="sxs-lookup"><span data-stu-id="ba64f-133">To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="ba64f-134">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="ba64f-134">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![機密資訊類型及建立按鈕的位置](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="ba64f-136">在開啟的 [選擇名稱和描述]\*\*\*\* 頁面中，輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="ba64f-136">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="ba64f-137">**名稱**：員工識別碼。</span><span class="sxs-lookup"><span data-stu-id="ba64f-137">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="ba64f-138">**描述**：偵測九位數 Contoso 員工編號。</span><span class="sxs-lookup"><span data-stu-id="ba64f-138">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名稱與描述頁面](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="ba64f-140">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-140">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="ba64f-141">在 [比對需求]\*\*\*\* 頁面中，按一下 [新增元素]\*\*\*\* 來設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ba64f-141">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="ba64f-142">**偵測包含下列項目的內容**：</span><span class="sxs-lookup"><span data-stu-id="ba64f-142">**Detect content containing**:</span></span>
 
      <span data-ttu-id="ba64f-143">a.</span><span class="sxs-lookup"><span data-stu-id="ba64f-143">a.</span></span> <span data-ttu-id="ba64f-144">Click **Any of these** and select **Regular expression**.</span><span class="sxs-lookup"><span data-stu-id="ba64f-144">Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="ba64f-145">b.</span><span class="sxs-lookup"><span data-stu-id="ba64f-145">b.</span></span> <span data-ttu-id="ba64f-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span><span class="sxs-lookup"><span data-stu-id="ba64f-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="ba64f-147">**支援項目**：按一下 [新增支援項目]\*\*\*\*，然後選取 [包含此關鍵字清單]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-147">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="ba64f-148">在出現的 [包含此關鍵字清單]\*\*\*\* 區域中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ba64f-148">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="ba64f-149">**關鍵字清單**：輸入下列值：員工、識別碼、徽章。</span><span class="sxs-lookup"><span data-stu-id="ba64f-149">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="ba64f-150">**最小計數**：保留預設值 1。</span><span class="sxs-lookup"><span data-stu-id="ba64f-150">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="ba64f-151">保留預設**信賴等級**值 60。</span><span class="sxs-lookup"><span data-stu-id="ba64f-151">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="ba64f-152">保留預設**字元近似值** 300。</span><span class="sxs-lookup"><span data-stu-id="ba64f-152">Leave the default **Character proximity** value 300.</span></span>

    ![比對要求頁面](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="ba64f-154">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ba64f-155">在開啟的 [檢閱並完成]\*\*\*\* 頁面上，檢閱設定並按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-155">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![檢閱並完成頁面](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="ba64f-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span><span class="sxs-lookup"><span data-stu-id="ba64f-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span></span> <span data-ttu-id="ba64f-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="ba64f-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span> <span data-ttu-id="ba64f-159">To test the rule later, click **No**.</span><span class="sxs-lookup"><span data-stu-id="ba64f-159">To test the rule later, click **No**.</span></span>

    ![測試建議頁面](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ba64f-161">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="ba64f-161">How do you know this worked?</span></span>

<span data-ttu-id="ba64f-162">若要確認您已成功建立新的機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="ba64f-162">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="ba64f-163">移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，並確認已列出新的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-163">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="ba64f-164">Test the new custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="ba64f-164">Test the new custom sensitive information type.</span></span> <span data-ttu-id="ba64f-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="ba64f-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="ba64f-166">在安全性與合規性中心修改自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-166">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="ba64f-167">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ba64f-167">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="ba64f-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="ba64f-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span></span> <span data-ttu-id="ba64f-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="ba64f-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span></span> <span data-ttu-id="ba64f-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="ba64f-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="ba64f-171">You can only modify custom sensitive information types that you created in the UI.</span><span class="sxs-lookup"><span data-stu-id="ba64f-171">You can only modify custom sensitive information types that you created in the UI.</span></span> <span data-ttu-id="ba64f-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span><span class="sxs-lookup"><span data-stu-id="ba64f-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="ba64f-173">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，選取您想要修改的自訂機密資訊類型，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-173">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![機密資訊類型及編輯按鈕的位置](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="ba64f-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ba64f-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span></span> <span data-ttu-id="ba64f-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="ba64f-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ba64f-177">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="ba64f-177">How do you know this worked?</span></span>

<span data-ttu-id="ba64f-178">若要確認您已成功修改機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="ba64f-178">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="ba64f-179">移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，以驗證已修改之自訂機密資訊類型的內容。</span><span class="sxs-lookup"><span data-stu-id="ba64f-179">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="ba64f-180">Test the modified custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="ba64f-180">Test the modified custom sensitive information type.</span></span> <span data-ttu-id="ba64f-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="ba64f-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="ba64f-182">移除安全性與合規性中心的自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-182">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="ba64f-183">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ba64f-183">**Notes**:</span></span>

- <span data-ttu-id="ba64f-184">您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-184">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="ba64f-185">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-185">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="ba64f-186">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，然後選取一或多個您想要移除的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-186">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="ba64f-187">在開啟的飛出視窗中，按一下 [刪除]\*\*\*\* (或 [刪除機密資訊類型]\*\*\*\*，如果您已選取多個的話)。</span><span class="sxs-lookup"><span data-stu-id="ba64f-187">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![機密資訊類型及刪除按鈕的位置](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="ba64f-189">在出現的警告訊息中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-189">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ba64f-190">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="ba64f-190">How do you know this worked?</span></span>

<span data-ttu-id="ba64f-191">若要確認您已成功移除自訂機密資訊類型，請移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，以確認不再列出自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ba64f-191">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="ba64f-192">在安全性與合規性中心測試自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="ba64f-192">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ba64f-193">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="ba64f-194">Select one or more custom sensitive information types to test.</span><span class="sxs-lookup"><span data-stu-id="ba64f-194">Select one or more custom sensitive information types to test.</span></span> <span data-ttu-id="ba64f-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span><span class="sxs-lookup"><span data-stu-id="ba64f-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![機密資訊類型及測試按鈕的位置](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="ba64f-197">在開啟的 [上傳檔案進行測試]\*\*\*\* 頁面上，拖放檔案或按一下 [瀏覽]\*\*\*\* 並選取檔案，來上傳要測試的文件。</span><span class="sxs-lookup"><span data-stu-id="ba64f-197">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![上傳檔案進行測試頁面](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="ba64f-199">按一下 [測試]\*\*\*\* 按鈕，來測試文件以在檔案中進行模式比對。</span><span class="sxs-lookup"><span data-stu-id="ba64f-199">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="ba64f-200">在 [比對結果]\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba64f-200">On the **Match results** page, click **Finish**.</span></span>

    ![比對結果](../media/scc-cust-sens-info-type-test-results.png)
