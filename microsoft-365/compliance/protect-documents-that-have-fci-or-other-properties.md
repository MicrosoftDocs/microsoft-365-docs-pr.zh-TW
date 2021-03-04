---
title: 建立 DLP 原則來保護具有 FCI 或其他屬性的文件
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用資料遺失防護 (DLP) 原則，以保護具有協力廠商系統屬性的檔。
ms.openlocfilehash: 971d2a1dd4f69f7bbd2598e31fc99c9c5cfe1eda
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423796"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="7c918-103">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="7c918-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="7c918-104">Microsoft 365 資料遺失防護 (DLP) 原則可以使用分類屬性或專案屬性來識別敏感專案。</span><span class="sxs-lookup"><span data-stu-id="7c918-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="7c918-105">例如，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="7c918-105">For example you can use:</span></span>

- <span data-ttu-id="7c918-106">Windows Server File 分類基礎結構 (FCI) 屬性</span><span class="sxs-lookup"><span data-stu-id="7c918-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="7c918-107">SharePoint 檔案屬性</span><span class="sxs-lookup"><span data-stu-id="7c918-107">SharePoint document properties</span></span>
- <span data-ttu-id="7c918-108">協力廠商的系統檔案屬性</span><span class="sxs-lookup"><span data-stu-id="7c918-108">third-party system document properties</span></span>

![圖表顯示 Office 365 及外部的分類系統](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="7c918-110">例如，您的組織可能會使用 Windows Server FCI 來識別具有個人資料（如社會保險號碼）的專案，然後根據檔中找到的個人資料類型和數量，將 [ **個人身分識別資訊** ] 屬性設定為 [ **高**]、[ **適中**]、[ **低**]、[ **公用**] 或 [ **不是 PII** ]，以分類檔。</span><span class="sxs-lookup"><span data-stu-id="7c918-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="7c918-111">在 Microsoft 365 中，您可以建立一個 DLP 原則，識別具有該屬性設定為特定值的檔，例如 [ **高** ] 和 [ **中**]，然後採取諸如封鎖對這些檔案的存取等動作。</span><span class="sxs-lookup"><span data-stu-id="7c918-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="7c918-112">如果屬性設定為 [ **低**] （例如傳送電子郵件通知），相同的原則可以有另一個規則採用其他的動作。</span><span class="sxs-lookup"><span data-stu-id="7c918-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="7c918-113">如此一來，DLP 便會與 Windows Server FCI 整合，並協助保護從 Windows Server 檔案伺服器上傳或共用至 Microsoft 365 的 Office 檔。</span><span class="sxs-lookup"><span data-stu-id="7c918-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="7c918-114">DLP 原則只會尋找特定的屬性名稱/值對。</span><span class="sxs-lookup"><span data-stu-id="7c918-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="7c918-115">只要屬性具有對應的 managed 屬性 SharePoint 搜尋，就可以使用任何檔案屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="7c918-116">例如，SharePoint 網站集合可能會使用名為「**客戶**」之必要欄位的「**行程報告**」內容類型。</span><span class="sxs-lookup"><span data-stu-id="7c918-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="7c918-117">每當人員建立行程報告時，他們必須輸入客戶名稱。</span><span class="sxs-lookup"><span data-stu-id="7c918-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="7c918-118">您也可以在 DLP 原則中使用此屬性名稱/值組，例如，如果您想要在 **客戶** 欄位包含 **Contoso** 時，封鎖檔存取權的規則。</span><span class="sxs-lookup"><span data-stu-id="7c918-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="7c918-119">如果您想要將 DLP 原則套用至特定 Microsoft 365 標籤的內容，請勿遵循這裡的步驟。</span><span class="sxs-lookup"><span data-stu-id="7c918-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="7c918-120">請改為了解如何 [使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="7c918-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="7c918-121">建立 DLP 原則之前</span><span class="sxs-lookup"><span data-stu-id="7c918-121">Before you create the DLP policy</span></span>

<span data-ttu-id="7c918-122">您必須先在 SharePoint 系統管理中心建立 managed 屬性，才能使用 DLP 原則中的 Windows Server FCI 屬性或其他屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="7c918-123">原因如下。</span><span class="sxs-lookup"><span data-stu-id="7c918-123">Here's why.</span></span>

<span data-ttu-id="7c918-124">在 SharePoint Online 和商務 OneDrive 中，搜尋索引會透過編目您網站上的內容來建立。</span><span class="sxs-lookup"><span data-stu-id="7c918-124">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites.</span></span> <span data-ttu-id="7c918-125">編目程式會以編目屬性的形式挑選檔中的內容和中繼資料。</span><span class="sxs-lookup"><span data-stu-id="7c918-125">The crawler picks up content and metadata from the documents in the form of crawled properties.</span></span> <span data-ttu-id="7c918-126">搜尋架構可協助編目程式決定要挑選的內容和中繼資料。</span><span class="sxs-lookup"><span data-stu-id="7c918-126">The search schema helps the crawler decide what content and metadata to pick up.</span></span> <span data-ttu-id="7c918-127">中繼資料的範例包括作者及檔的標題。</span><span class="sxs-lookup"><span data-stu-id="7c918-127">Examples of metadata are the author and the title of a document.</span></span> <span data-ttu-id="7c918-128">不過，若要將檔中的內容和中繼資料取得搜尋索引，編目屬性必須對應至 managed 屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-128">However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties.</span></span> <span data-ttu-id="7c918-129">只有 managed 屬性會保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="7c918-129">Only managed properties are kept in the index.</span></span> <span data-ttu-id="7c918-130">例如，與 author 相關的編目屬性會對應至與 author 相關的 managed 屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-130">For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

> [!NOTE]
> <span data-ttu-id="7c918-131">使用條件建立 DLP 規則時，請務必使用 managed 屬性名稱，而不是編目屬性名稱 `ContentPropertyContainsWords` 。</span><span class="sxs-lookup"><span data-stu-id="7c918-131">Be sure to use a managed property name and not a crawled property name when creating DLP rules using the `ContentPropertyContainsWords` condition.</span></span>

<span data-ttu-id="7c918-132">這一點很重要，因為 DLP 會使用搜尋編目程式來識別和分類您網站上的機密資訊，然後將該機密資訊儲存在搜尋索引的安全部分。</span><span class="sxs-lookup"><span data-stu-id="7c918-132">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="7c918-133">當您將檔上傳至 Office 365 時，SharePoint 會根據檔案屬性，自動建立編目屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-133">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="7c918-134">不過，若要使用 DLP 原則中的 FCI 或其他屬性，該編目屬性必須對應至 managed 屬性，這樣該屬性的內容就會保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="7c918-134">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="7c918-135">如需搜尋及 managed 屬性的詳細資訊，請參閱 [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454)。</span><span class="sxs-lookup"><span data-stu-id="7c918-135">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="7c918-136">步驟1：將具有必要屬性的檔上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="7c918-136">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="7c918-137">您必須先將檔上傳至您要在 DLP 原則中參考的屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-137">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="7c918-138">Microsoft 365 會偵測屬性，並自動從該屬性建立編目屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-138">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="7c918-139">在下一個步驟中，您將建立 managed 屬性，然後將 managed 屬性對應至此編目屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-139">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="7c918-140">步驟2：建立 managed 屬性</span><span class="sxs-lookup"><span data-stu-id="7c918-140">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="7c918-141">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7c918-141">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="7c918-142">在左側導覽中，選擇 [系統 **管理中心**] \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="7c918-142">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="7c918-143">You're now in the SharePoint admin center.</span><span class="sxs-lookup"><span data-stu-id="7c918-143">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="7c918-144">在左側導覽中，選擇 \> [搜尋 **管理**] 頁面上的 [搜尋] [ \> **管理搜尋架構**]。</span><span class="sxs-lookup"><span data-stu-id="7c918-144">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![SharePoint 系統管理中心的搜尋管理頁面](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="7c918-146">在 [ **Managed 屬性** ] 頁面的 [ \> **新增 managed 屬性**]。</span><span class="sxs-lookup"><span data-stu-id="7c918-146">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="7c918-148">輸入屬性的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="7c918-148">Enter a name and description for the property.</span></span> <span data-ttu-id="7c918-149">此名稱會顯示在您的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="7c918-149">This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="7c918-150">針對 [ **類型**]，選擇 [ **文字**]。</span><span class="sxs-lookup"><span data-stu-id="7c918-150">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="7c918-151">在 [ **主要特性**] 底下，選取 [可 **查詢** 及可 **檢索**]。</span><span class="sxs-lookup"><span data-stu-id="7c918-151">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="7c918-152">在 [對應至編目屬性] 底下 **，** \> **新增對應**。</span><span class="sxs-lookup"><span data-stu-id="7c918-152">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="7c918-153">在 [編目 **屬性選項** ] 對話方塊中 \> ，尋找並選取對應至您將在 DLP 原則 OK 中使用的 Windows Server FCI 屬性或其他屬性的編目屬性 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c918-153">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![選取編目屬性對話方塊](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="7c918-155">在頁面底部的 \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7c918-155">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="7c918-156">建立使用 FCI 屬性或其他屬性的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7c918-156">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="7c918-157">在此範例中，組織在其 Windows 伺服器型檔案伺服器上使用 FCI;具體而言，他們使用的是名為 **個人身分識別資訊** 的 FCI 分類屬性，其可能的值為 **High**、 **適中**、 **低**、 **公有** 和 **非 PII**。</span><span class="sxs-lookup"><span data-stu-id="7c918-157">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="7c918-158">現在，他們想要在 Office 365 的 DLP 原則中使用其現有的 FCI 分類。</span><span class="sxs-lookup"><span data-stu-id="7c918-158">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="7c918-159">首先，他們會依照上述步驟，在 SharePoint Online 中建立 managed 屬性，該屬性會對應至自動從 FCI 屬性建立的編目屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-159">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="7c918-160">接下來，他們會建立一個 DLP 原則，其中兩個規則都使用條件 **檔案屬性包含下列任一值**：</span><span class="sxs-lookup"><span data-stu-id="7c918-160">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="7c918-161">**FCI PII 內容-高、適中** 第一個規則會限制存取檔如果 FCI 分類屬性 **個人識別資訊** 等於 **高** 或 **適中** ，而且檔與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="7c918-161">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="7c918-162">**FCI PII 內容-低** 第二個規則會在 FCI 分類屬性 **個人識別資訊** 等於 **低** ，且與組織外部人員共用檔時，將通知傳送給檔擁有者。</span><span class="sxs-lookup"><span data-stu-id="7c918-162">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="7c918-163">使用 PowerShell 建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7c918-163">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="7c918-164">條件 **檔案屬性包含這些值中的任何一個** 暫時無法在安全性與合規性中心的 UI 中使用 &amp; ，但是您仍然可以使用 PowerShell 來使用此條件。</span><span class="sxs-lookup"><span data-stu-id="7c918-164">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="7c918-165">您可以使用  `New\Set\Get-DlpCompliancePolicy` Cmdlet 來使用 DLP 原則，並搭配參數使用 Cmdlet，  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` 以新增條件 **檔案屬性包含這些值中的任何一個**。</span><span class="sxs-lookup"><span data-stu-id="7c918-165">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="7c918-166">如需這些 Cmdlet 的詳細資訊，請參閱 [安全性 &amp; 規範中心 Cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7c918-166">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>

1. [<span data-ttu-id="7c918-167">&amp;使用遠端 PowerShell 連接至安全規範中心</span><span class="sxs-lookup"><span data-stu-id="7c918-167">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="7c918-168">使用建立原則  `New-DlpCompliancePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="7c918-168">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="7c918-169">此 PowerShell 會建立套用至所有位置的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="7c918-169">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="7c918-170">使用 `New-DlpComplianceRule` 其中一個規則是 **低** 值的規則，而另一個規則是用於 **高低** 值，以建立上述的兩個規則 。</span><span class="sxs-lookup"><span data-stu-id="7c918-170">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="7c918-171">以下是建立這兩個規則的 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="7c918-171">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="7c918-172">屬性名稱/值對會以引號括住，屬性名稱可以指定多個以逗號分隔的多個值，不含空格，例如  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="7c918-172">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="7c918-173">Windows Server FCI 包含許多內建的屬性，包括本範例中所用的 **個人身分識別資訊** 。</span><span class="sxs-lookup"><span data-stu-id="7c918-173">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="7c918-174">每個組織可能會有不同的屬性值。</span><span class="sxs-lookup"><span data-stu-id="7c918-174">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="7c918-175">這裡使用的 [ **高**]、[ **適中**] 和 [ **低** ] 值都只是範例。</span><span class="sxs-lookup"><span data-stu-id="7c918-175">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="7c918-176">針對您的組織，您可以在 Windows Server 檔案伺服器的檔案伺服器資源管理員中，以其可能的值來查看 Windows Server FCI 的分類屬性。</span><span class="sxs-lookup"><span data-stu-id="7c918-176">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="7c918-177">如需詳細資訊，請參閱 [建立分類屬性](https://go.microsoft.com/fwlink/p/?LinkID=627456)。</span><span class="sxs-lookup"><span data-stu-id="7c918-177">For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>

<span data-ttu-id="7c918-178">當您完成時，您的原則應該會有兩個新規則，都使用 **檔案屬性包含這些值的任何** 條件。</span><span class="sxs-lookup"><span data-stu-id="7c918-178">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="7c918-179">此條件不會出現在 UI 中，但會顯示其他條件、動作和設定。</span><span class="sxs-lookup"><span data-stu-id="7c918-179">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="7c918-180">一個規則會封鎖 **個人身分識別資訊** 屬性等於 **High** 或 **適中** 的內容存取權。</span><span class="sxs-lookup"><span data-stu-id="7c918-180">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="7c918-181">第二個規則會傳送有關 **個人身分識別資訊** 屬性等於 **Low** 的內容通知。</span><span class="sxs-lookup"><span data-stu-id="7c918-181">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="7c918-183">建立 DLP 原則之後</span><span class="sxs-lookup"><span data-stu-id="7c918-183">After you create the DLP policy</span></span>

<span data-ttu-id="7c918-184">執行上述各節中的步驟，將會建立一個 DLP 原則，它會使用該屬性快速偵測內容，但只有在該內容已新近上傳時 (，這樣內容的索引) ，或是該內容已過時，但只是編輯 (，這樣內容就會重新編制索引) 。</span><span class="sxs-lookup"><span data-stu-id="7c918-184">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="7c918-185">若要在任何地方使用該屬性偵測內容，您可能想要手動要求您的文件庫、網站或網站集合重新編制索引，以便 DLP 原則知道具有該屬性的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7c918-185">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property.</span></span> <span data-ttu-id="7c918-186">在 [SharePoint 線上] 中，會根據定義的編目排程自動編目內容。</span><span class="sxs-lookup"><span data-stu-id="7c918-186">In SharePoint Online, content is automatically crawled based on a defined crawl schedule.</span></span> <span data-ttu-id="7c918-187">編目程式會挑選自上次編目後已變更的內容，並更新索引。</span><span class="sxs-lookup"><span data-stu-id="7c918-187">The crawler picks up content that has changed since the last crawl and updates the index.</span></span> <span data-ttu-id="7c918-188">如果您需要 DLP 原則在下一個排程編目之前保護內容，您可以採取下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7c918-188">If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="7c918-189">重新編制網站索引可能會導致搜尋系統負載大幅。</span><span class="sxs-lookup"><span data-stu-id="7c918-189">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="7c918-190">除非您的案例絕對需要，否則不要重新建立網站索引。</span><span class="sxs-lookup"><span data-stu-id="7c918-190">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="7c918-191">如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://go.microsoft.com/fwlink/p/?LinkID=627457)。</span><span class="sxs-lookup"><span data-stu-id="7c918-191">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="7c918-192">為網站重新編制索引 (選用) </span><span class="sxs-lookup"><span data-stu-id="7c918-192">Reindex a site (optional)</span></span>

1. <span data-ttu-id="7c918-193">在網站上，選擇右上角) \> **網站設定** (齒輪圖示的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="7c918-193">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="7c918-194">在 [ **搜尋**] 底下，選擇 [ **搜尋及離線可用性** 重新 \> **索引網站**]。</span><span class="sxs-lookup"><span data-stu-id="7c918-194">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="7c918-195">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7c918-195">More information</span></span>

- [<span data-ttu-id="7c918-196">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="7c918-196">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="7c918-197">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7c918-197">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="7c918-198">傳送通知並顯示 DLP 原則的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="7c918-198">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="7c918-199">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="7c918-199">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="7c918-200">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="7c918-200">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
