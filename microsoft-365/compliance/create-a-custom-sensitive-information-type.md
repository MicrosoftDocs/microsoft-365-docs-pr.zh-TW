---
title: 在安全性與合規性中心建立自訂敏感性資訊類型
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
ms.openlocfilehash: 12a44fcc4fb5228f1e1d901502c1e6dd0e2582af
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806606"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="2b850-103">在安全性與合規性中心建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="2b850-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

## <a name="summary"></a><span data-ttu-id="2b850-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2b850-104">Summary</span></span>

<span data-ttu-id="2b850-105">閱讀本文，在安全性與合規性中心建立[自訂敏感性資訊類型](custom-sensitive-info-types.md) ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="2b850-105">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="2b850-106">透過使用此方法，您建立的自訂敏感性資訊類型會新增到名為 `Microsoft.SCCManaged.CustomRulePack` 的規則套件。</span><span class="sxs-lookup"><span data-stu-id="2b850-106">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="2b850-107">您也可以使用 PowerShell 和 Exact Data Match 功能建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-107">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="2b850-108">若要深入了解這些方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="2b850-108">To learn more about those methods, see:</span></span>
- <span data-ttu-id="2b850-109">[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2b850-109">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>
- <span data-ttu-id="2b850-110">[使用 Exact Data Match (EDM) 建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="2b850-110">See [Create a custom sensitive information type with Exact Data Match based classification (Preview)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2b850-111">開始之前...</span><span class="sxs-lookup"><span data-stu-id="2b850-111">Before you begin:</span></span>

> [!NOTE]
> <span data-ttu-id="2b850-112">您必須具備全域管理員或合規性系統管理員的權限，才能透過 UI 建立、測試及部署自訂的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-112">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="2b850-113">請參閱 Office 365 中的[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="2b850-113">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="2b850-114">您的組織必須擁有包括資料外洩防護 (DLP) 的訂用帳戶，例如 Office 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="2b850-114">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="2b850-115">請參閱[郵件原則及符合性](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="2b850-115">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="2b850-p105">自訂機密資訊類型需要熟悉規則運算式 (RegEx)。如需用於處理文字之 Boost.RegEx (先前稱為 RegEx++) 引擎的詳細資訊，請參閱 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p105">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="2b850-118">Microsoft 客戶服務及支援無法協助您建立自訂分類或規則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="2b850-118">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="2b850-119">支援工程師可以提供有限的功能支援，例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解，但無法保證任何自訂內容比對開發作業將符合您的需求或義務。</span><span class="sxs-lookup"><span data-stu-id="2b850-119">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="2b850-120">DLP 會使用搜尋檢索器識別及分類 SharePoint Online 和商務用 OneDrive 中網站中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="2b850-120">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="2b850-121">若要在所有現有內容中識別您的新自訂敏感性資訊類型，必須將內容重新編目。</span><span class="sxs-lookup"><span data-stu-id="2b850-121">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="2b850-122">內容會根據排程進行編目，但您可以手動重新編目網站集合、清單或文件庫的內容。</span><span class="sxs-lookup"><span data-stu-id="2b850-122">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="2b850-123">如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="2b850-123">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="2b850-124">在安全性與合規性中心建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="2b850-124">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="2b850-125">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="2b850-125">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="2b850-126">這些設定不言而喻，並會在精靈的關聯頁面上加以說明：</span><span class="sxs-lookup"><span data-stu-id="2b850-126">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="2b850-127">**名稱**</span><span class="sxs-lookup"><span data-stu-id="2b850-127">**Name**</span></span>

- <span data-ttu-id="2b850-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="2b850-128">**Description**</span></span>

- <span data-ttu-id="2b850-129">**近似值**</span><span class="sxs-lookup"><span data-stu-id="2b850-129">**Proximity**</span></span>

- <span data-ttu-id="2b850-130">**信賴等級**</span><span class="sxs-lookup"><span data-stu-id="2b850-130">**Confidence level**</span></span>

- <span data-ttu-id="2b850-131">**主要模式元素** (關鍵字、規則運算式或字典)</span><span class="sxs-lookup"><span data-stu-id="2b850-131">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="2b850-132">選用的**支援模式元素** (關鍵字、規則運算式或字典) 及其對應**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="2b850-132">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="2b850-p108">以下是案例：您想要一個自訂機密資訊類型，偵測內容中 9 位數的員工編號，以及關鍵字 "employee"、"ID" 及 "badge"。若要建立此自訂機密資訊類型，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2b850-p108">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="2b850-135">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="2b850-135">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![機密資訊類型及建立按鈕的位置](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="2b850-137">在開啟的 [選擇名稱和描述]\*\*\*\* 頁面中，輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="2b850-137">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="2b850-138">**名稱**：員工識別碼。</span><span class="sxs-lookup"><span data-stu-id="2b850-138">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="2b850-139">**描述**：偵測九位數 Contoso 員工編號。</span><span class="sxs-lookup"><span data-stu-id="2b850-139">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名稱與描述頁面](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="2b850-141">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-141">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="2b850-142">在 [比對需求]\*\*\*\* 頁面中，按一下 [新增元素]\*\*\*\* 來設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="2b850-142">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="2b850-143">**偵測包含下列項目的內容**：</span><span class="sxs-lookup"><span data-stu-id="2b850-143">**Detect content containing**:</span></span>
 
      <span data-ttu-id="2b850-p109">a 按一下 [其中任一個]\*\*\*\*，然後選取 [規則運算式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-p109">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="2b850-p110">b. 在規則運算式方塊中，輸入 `(\s)(\d{9})(\s)` (以空格括住九位數的號碼)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p110">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="2b850-148">**支援項目**：按一下 [新增支援項目]\*\*\*\*，然後選取 [包含此關鍵字清單]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-148">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="2b850-149">在出現的 [包含此關鍵字清單]\*\*\*\* 區域中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="2b850-149">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="2b850-150">**關鍵字清單**：輸入下列值：員工、識別碼、徽章。</span><span class="sxs-lookup"><span data-stu-id="2b850-150">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="2b850-151">**最小計數**：保留預設值 1。</span><span class="sxs-lookup"><span data-stu-id="2b850-151">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="2b850-152">保留預設**信賴等級**值 60。</span><span class="sxs-lookup"><span data-stu-id="2b850-152">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="2b850-153">保留預設**字元近似值** 300。</span><span class="sxs-lookup"><span data-stu-id="2b850-153">Leave the default **Character proximity** value 300.</span></span>

    ![比對要求頁面](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="2b850-155">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-155">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2b850-156">在開啟的 [檢閱並完成]\*\*\*\* 頁面上，檢閱設定並按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-156">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![檢閱並完成頁面](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="2b850-p111">下一個頁面鼓勵您藉由按一下 [是]\*\*\*\*，測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。如需稍後再測試規則，請按一下 [否]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-p111">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![測試建議頁面](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2b850-162">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="2b850-162">How do you know this worked?</span></span>

<span data-ttu-id="2b850-163">若要確認您已成功建立新的機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="2b850-163">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="2b850-164">移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，並確認已列出新的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-164">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="2b850-p112">測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p112">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="2b850-167">在安全性與合規性中心修改自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="2b850-167">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="2b850-168">**附註**：</span><span class="sxs-lookup"><span data-stu-id="2b850-168">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="2b850-p113">您只能修改自訂機密資訊類型，不能修改內建的機密資訊類型。但您可以使用 PowerShell 來匯出內建的自訂機密資訊類型、自訂它們，並將其匯入為自訂機密資訊類型。如需詳細資訊，請參閱[自訂內建的機密資訊類型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p113">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="2b850-p114">您只能修改在 UI 中建立的自訂機密資訊類型。如果您使用 [PowerShell 程序](create-a-custom-sensitive-information-type-in-scc-powershell.md)匯入自訂的機密資訊類型規則套件，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="2b850-p114">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="2b850-174">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，選取您想要修改的自訂機密資訊類型，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-174">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![機密資訊類型及編輯按鈕的位置](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="2b850-p115">這裡提供與您在安全性與合規性中心建立自訂機密資訊類型時相同的選項。如需詳細資訊，請參閱[在安全性與合規性中心建立自訂機密資訊類型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p115">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2b850-178">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="2b850-178">How do you know this worked?</span></span>

<span data-ttu-id="2b850-179">若要確認您已成功修改機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="2b850-179">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="2b850-180">移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，以驗證已修改之自訂機密資訊類型的內容。</span><span class="sxs-lookup"><span data-stu-id="2b850-180">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="2b850-p116">測試已修改的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p116">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="2b850-183">移除安全性與合規性中心的自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="2b850-183">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="2b850-184">**附註**：</span><span class="sxs-lookup"><span data-stu-id="2b850-184">**Notes**:</span></span>

- <span data-ttu-id="2b850-185">您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-185">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="2b850-186">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-186">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="2b850-187">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，然後選取一或多個您想要移除的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-187">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="2b850-188">在開啟的飛出視窗中，按一下 [刪除]\*\*\*\* (或 [刪除機密資訊類型]\*\*\*\*，如果您已選取多個的話)。</span><span class="sxs-lookup"><span data-stu-id="2b850-188">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![機密資訊類型及刪除按鈕的位置](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="2b850-190">在出現的警告訊息中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-190">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2b850-191">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="2b850-191">How do you know this worked?</span></span>

<span data-ttu-id="2b850-192">若要確認您已成功移除自訂機密資訊類型，請移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*，以確認不再列出自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2b850-192">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="2b850-193">在安全性與合規性中心測試自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="2b850-193">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="2b850-194">在安全性與合規性中心，移至 [分類]\*\*\*\* \> [機密資訊類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-194">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="2b850-p117">選取要測試的一或多個自訂機密資訊類型。在開啟的飛出視窗中，按一下 [測試類型]\*\*\*\* (或 [測試機密資訊類型]\*\*\*\*，如果您已選取多個的話)。</span><span class="sxs-lookup"><span data-stu-id="2b850-p117">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![機密資訊類型及測試按鈕的位置](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="2b850-198">在開啟的 [上傳檔案進行測試]\*\*\*\* 頁面上，拖放檔案或按一下 [瀏覽]\*\*\*\* 並選取檔案，來上傳要測試的文件。</span><span class="sxs-lookup"><span data-stu-id="2b850-198">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![上傳檔案進行測試頁面](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="2b850-200">按一下 [測試]\*\*\*\* 按鈕，來測試文件以在檔案中進行模式比對。</span><span class="sxs-lookup"><span data-stu-id="2b850-200">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="2b850-201">在 [比對結果]\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b850-201">On the **Match results** page, click **Finish**.</span></span>

    ![比對結果](media/scc-cust-sens-info-type-test-results.png)
