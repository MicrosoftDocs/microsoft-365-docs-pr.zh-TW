---
title: Microsoft SharePoint Syntex 案例和使用案例
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 尋找有關如何在組織中使用 SharePoint Syntex 的案例。
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697056"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a><span data-ttu-id="10363-103">Microsoft SharePoint Syntex 案例和使用案例</span><span class="sxs-lookup"><span data-stu-id="10363-103">Scenarios and use cases for Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="10363-104">使用下列範例案例，提示您如何在組織中使用 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="10363-104">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

- [<span data-ttu-id="10363-105">案例：使用表單處理從發票追蹤資料</span><span class="sxs-lookup"><span data-stu-id="10363-105">Scenario: Track data from invoices with form processing</span></span>](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [<span data-ttu-id="10363-106">案例：使用檔瞭解追蹤合同中的資訊</span><span class="sxs-lookup"><span data-stu-id="10363-106">Scenario: Track information from contracts with document understanding</span></span>](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [<span data-ttu-id="10363-107">案例：根據 SharePoint Syntex，避免記錄管理、檔管理及規範程式的風險</span><span class="sxs-lookup"><span data-stu-id="10363-107">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [<span data-ttu-id="10363-108">案例：從先前無法存取的檔捕獲資訊</span><span class="sxs-lookup"><span data-stu-id="10363-108">Scenario: Capture information from previously inaccessible documents</span></span>](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [<span data-ttu-id="10363-109">案例：改善資料處理以提供真知灼見和分析</span><span class="sxs-lookup"><span data-stu-id="10363-109">Scenario: Improve data processing to provide insights and analytics</span></span>](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [<span data-ttu-id="10363-110">案例：自動化訂單處理</span><span class="sxs-lookup"><span data-stu-id="10363-110">Scenario: Automate order processing</span></span>](adoption-scenarios.md#scenario-automate-order-processing)
- [<span data-ttu-id="10363-111">案例：簡化簽證更新程式</span><span class="sxs-lookup"><span data-stu-id="10363-111">Scenario: Simplify visa renewal process</span></span>](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="10363-112">案例：使用表單處理從發票追蹤資料</span><span class="sxs-lookup"><span data-stu-id="10363-112">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="10363-113">例如，您可以使用 SharePoint Syntex 和 Power Automate 功能來設定處理常式，以追蹤和監控發票。</span><span class="sxs-lookup"><span data-stu-id="10363-113">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="10363-114">設定儲存發票檔的文件庫。</span><span class="sxs-lookup"><span data-stu-id="10363-114">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="10363-115">訓練模型，以辨識檔中的欄位。</span><span class="sxs-lookup"><span data-stu-id="10363-115">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="10363-116">將您要追蹤的欄位解壓縮到清單中。</span><span class="sxs-lookup"><span data-stu-id="10363-116">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="10363-117">設定流程以通知您特定的事件，例如：</span><span class="sxs-lookup"><span data-stu-id="10363-117">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="10363-118">新增新的發票。</span><span class="sxs-lookup"><span data-stu-id="10363-118">A new invoice is added.</span></span>
    - <span data-ttu-id="10363-119">發票超過其到期日。</span><span class="sxs-lookup"><span data-stu-id="10363-119">An invoice is past its due date.</span></span>
    - <span data-ttu-id="10363-120">發票的數量大於您的自動核准金額。</span><span class="sxs-lookup"><span data-stu-id="10363-120">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 SharePoint Syntex 和 Power Automate 來追蹤和監控發票](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="10363-122">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="10363-122">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="10363-123">從發票自動提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="10363-123">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="10363-124">使用工作流程檢查發票，並在發生問題時通知您，以減少潛在的錯誤並確保更好的相容性。</span><span class="sxs-lookup"><span data-stu-id="10363-124">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="10363-125">案例：使用檔瞭解追蹤合同中的資訊</span><span class="sxs-lookup"><span data-stu-id="10363-125">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="10363-126">在另一個範例中，您可以設定處理常式，識別您的公司與其他公司或個人的合約。</span><span class="sxs-lookup"><span data-stu-id="10363-126">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="10363-127">設定模型，以從這些合約提取重要資訊，例如用戶端名稱、費用、日期或其他重要資訊，並將資訊新增至文件庫中，您可以快速查看這些欄位。</span><span class="sxs-lookup"><span data-stu-id="10363-127">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="10363-128">請將保留標籤套用到文件庫，以確保在適當的時間長度之前，不能刪除合約，以符合您的商務法規。</span><span class="sxs-lookup"><span data-stu-id="10363-128">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="10363-129">從內容中心開始，並建立新的檔瞭解合約模型。</span><span class="sxs-lookup"><span data-stu-id="10363-129">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="10363-130">Upload 範例檔，以取得正值和消極的範例，然後執行訓練以識別合同檔，並檢查結果。</span><span class="sxs-lookup"><span data-stu-id="10363-130">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="10363-131">訓練解壓縮程式以識別合同中的欄位，例如用戶端名稱、費用和日期，然後測試解壓縮程式。</span><span class="sxs-lookup"><span data-stu-id="10363-131">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="10363-132">模型完成時，將模型套用至您可以上傳合同的文件庫。</span><span class="sxs-lookup"><span data-stu-id="10363-132">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="10363-133">將保留標籤套用至日期欄位，讓合同保留在文件庫中所需的時間長度。</span><span class="sxs-lookup"><span data-stu-id="10363-133">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![使用 SharePoint Syntex 和保留標籤來追蹤和監控合約](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="10363-135">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="10363-135">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="10363-136">自動從合約提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="10363-136">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="10363-137">使用保留標籤確保合約已正確保留，以確保更好地相容。</span><span class="sxs-lookup"><span data-stu-id="10363-137">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="10363-138">案例：根據 SharePoint Syntex，避免記錄管理、檔管理及規範程式的風險</span><span class="sxs-lookup"><span data-stu-id="10363-138">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="10363-139">降低風險是大多數公司的共同目標。</span><span class="sxs-lookup"><span data-stu-id="10363-139">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="10363-140">您可能需要：</span><span class="sxs-lookup"><span data-stu-id="10363-140">You might need:</span></span>

- <span data-ttu-id="10363-141">在您的租使用者中提供/強制執行資訊管理的更好方法。</span><span class="sxs-lookup"><span data-stu-id="10363-141">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="10363-142">若要改善檔的分類、電子郵件及其他形式的通訊視為專案的「記錄」的系統。</span><span class="sxs-lookup"><span data-stu-id="10363-142">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="10363-143">若要審核收據、合約等等，以確保符合公司原則。</span><span class="sxs-lookup"><span data-stu-id="10363-143">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="10363-144">確定專案具備法規遵從性所需的所有檔。</span><span class="sxs-lookup"><span data-stu-id="10363-144">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="10363-145">設定一些與 SharePoint Syntex 相容的處理常式，以取得及適當分類、審核和旗標需要更好的控管的檔和表單。</span><span class="sxs-lookup"><span data-stu-id="10363-145">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="10363-146">您可以依靠 SharePoint Syntex，自動將內容分類，而不需依賴使用者手動標記，或是合規性小組手動套用控管規則和封存。</span><span class="sxs-lookup"><span data-stu-id="10363-146">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="10363-147">而且，您可以啟用簡化的搜尋體驗、管理資料量、套用記錄管理和保留原則，以確保法規遵從性，以及最佳作法封存及清除作法。</span><span class="sxs-lookup"><span data-stu-id="10363-147">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="10363-148">當您自動化此案例時，您可以放心進行下列安全：</span><span class="sxs-lookup"><span data-stu-id="10363-148">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="10363-149">法規遵從性是 upheld 和降低風險。</span><span class="sxs-lookup"><span data-stu-id="10363-149">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="10363-150">分類和記錄管理的一致性及正確套用。</span><span class="sxs-lookup"><span data-stu-id="10363-150">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="10363-151">控制內容量。</span><span class="sxs-lookup"><span data-stu-id="10363-151">Content volumes are controlled.</span></span>
- <span data-ttu-id="10363-152">員工可以輕鬆地在正確的內容中探索正確的資訊。</span><span class="sxs-lookup"><span data-stu-id="10363-152">Employees can easily discover the right information in the right context.</span></span>

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="10363-153">案例：從先前無法存取的檔捕獲資訊</span><span class="sxs-lookup"><span data-stu-id="10363-153">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="10363-154">大多數的組織都有大量的法律檔、原則、合約、HR 檔和控管指導方針。</span><span class="sxs-lookup"><span data-stu-id="10363-154">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="10363-155">請挖掘這些資料存放區，以解壓重要資訊，例如：專案、磁區、主題、人員、地理區域等等。</span><span class="sxs-lookup"><span data-stu-id="10363-155">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="10363-156">例如，HR director 必須快速存取所有人力資源檔，包括簡歷、HR 原則及其他表單。</span><span class="sxs-lookup"><span data-stu-id="10363-156">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="10363-157">他們想要從簡歷和其他 HR 相關檔快速識別必要的資訊，而不需透過檔手動 sifting。</span><span class="sxs-lookup"><span data-stu-id="10363-157">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="10363-158">他們在尋找一種解決方案，可讓他們快速找出所需的資訊，而不必手動搜尋數千個簡歷、HR 原則，以及可能分散于多個網站的其他檔。</span><span class="sxs-lookup"><span data-stu-id="10363-158">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="10363-159">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="10363-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="10363-160">從數位內容解除鎖定知識。</span><span class="sxs-lookup"><span data-stu-id="10363-160">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="10363-161">分類人力資源原則、簡歷、銷售檔、技術藍圖、帳戶計畫及提取資訊。</span><span class="sxs-lookup"><span data-stu-id="10363-161">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="10363-162">快速尋找您要尋找的正確資訊或檔。</span><span class="sxs-lookup"><span data-stu-id="10363-162">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="10363-163">立即獲得最新資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="10363-163">Get instant access to the latest information.</span></span>
- <span data-ttu-id="10363-164">縮短搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="10363-164">Reduce search times.</span></span>

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a><span data-ttu-id="10363-165">案例：改善資料處理以提供真知灼見和分析</span><span class="sxs-lookup"><span data-stu-id="10363-165">Scenario: Improve data processing to provide insights and analytics</span></span>

<span data-ttu-id="10363-166">例如，製藥公司可以使用 SharePoint Syntex，從 FDA 檔析取資訊，以回答他們的領導人所提出的問題。</span><span class="sxs-lookup"><span data-stu-id="10363-166">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="10363-167">讓答案變得更容易存取，可縮短產生這些回答所需的時間，並提高資料的可用性以產生更準確的領導問題答案。</span><span class="sxs-lookup"><span data-stu-id="10363-167">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="10363-168">例如，專案經理必須從我的領導小組快速為產品相關問題提供答案。</span><span class="sxs-lookup"><span data-stu-id="10363-168">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="10363-169">他們必須尋找與一個合併儀表板中的查詢相關的資訊和度量。</span><span class="sxs-lookup"><span data-stu-id="10363-169">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="10363-170">他們要尋找的解決方案會從產品標籤、產品 pamphlets 及其他材料提取所需的資訊，並產生整合報告，以供報告回其領導團隊時使用。</span><span class="sxs-lookup"><span data-stu-id="10363-170">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="10363-171">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="10363-171">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="10363-172">縮短產生回應的時間。</span><span class="sxs-lookup"><span data-stu-id="10363-172">Reduce time to produce answers.</span></span>
- <span data-ttu-id="10363-173">提高資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="10363-173">Increase availability of data.</span></span>
- <span data-ttu-id="10363-174">提供更準確的答案。</span><span class="sxs-lookup"><span data-stu-id="10363-174">Provide more accurate answers.</span></span>

## <a name="scenario-automate-order-processing"></a><span data-ttu-id="10363-175">案例：自動化訂單處理</span><span class="sxs-lookup"><span data-stu-id="10363-175">Scenario: Automate order processing</span></span>

<span data-ttu-id="10363-176">使用 SharePoint Syntex，您可以縮短手動處理客戶訂單的時間。</span><span class="sxs-lookup"><span data-stu-id="10363-176">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="10363-177">例如，您可以使用 OCR 處理將訂單從傳真、電子郵件或紙張上傳至 SharePoint，然後從這些訂單中解壓縮中繼資料，以便您可以使用自動化程式來完成這些訂單。</span><span class="sxs-lookup"><span data-stu-id="10363-177">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="10363-178">例如，供應鏈管理員想要減少手動資料輸入所造成的錯誤。</span><span class="sxs-lookup"><span data-stu-id="10363-178">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="10363-179">他們想要避免以手動形式查看輸入客戶訂單的資料， (紙張、傳真或電子郵件) ，以降低業務系統的錯誤。</span><span class="sxs-lookup"><span data-stu-id="10363-179">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="10363-180">他們需要套用 AI 和機器學習技巧的解決方案，以驗證內送訂單資訊、提取核心資料，並自動將其推入 ERP 系統，以進行訂單履行和調解。</span><span class="sxs-lookup"><span data-stu-id="10363-180">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="10363-181">當您自動化此案例時，您可以確定：</span><span class="sxs-lookup"><span data-stu-id="10363-181">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="10363-182">訂單和運送的精確度增加。</span><span class="sxs-lookup"><span data-stu-id="10363-182">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="10363-183">減少與訂單或運送錯誤相關的費用或處罰。</span><span class="sxs-lookup"><span data-stu-id="10363-183">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="10363-184">縮短開票或付款的延遲。</span><span class="sxs-lookup"><span data-stu-id="10363-184">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="10363-185">減少人員成本。</span><span class="sxs-lookup"><span data-stu-id="10363-185">Personnel costs are reduced.</span></span>

## <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="10363-186">案例：簡化簽證更新程式</span><span class="sxs-lookup"><span data-stu-id="10363-186">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="10363-187">SharePointSyntex 可協助您自動化重要合約資訊的提醒和續訂。</span><span class="sxs-lookup"><span data-stu-id="10363-187">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="10363-188">例如，HR 主管需要確定員工的簽證是最新的，且/或已在時間上更新。</span><span class="sxs-lookup"><span data-stu-id="10363-188">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="10363-189">他們想為人們提供簡單且直觀的處理常式來更新其簽證。</span><span class="sxs-lookup"><span data-stu-id="10363-189">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="10363-190">他們需要可從合約提取更新日期的解決方案，並在其更新日期接近時自動傳送員工提醒。</span><span class="sxs-lookup"><span data-stu-id="10363-190">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="10363-191">當您自動化此案例時，您可以確定：</span><span class="sxs-lookup"><span data-stu-id="10363-191">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="10363-192">減少非法規遵從性的層級。</span><span class="sxs-lookup"><span data-stu-id="10363-192">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="10363-193">已縮短手動提醒數目。</span><span class="sxs-lookup"><span data-stu-id="10363-193">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="10363-194">降低未達標的罰款數目。</span><span class="sxs-lookup"><span data-stu-id="10363-194">The number of fines for non-compliance is reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="10363-195">另請參閱</span><span class="sxs-lookup"><span data-stu-id="10363-195">See also</span></span>

[<span data-ttu-id="10363-196">Microsoft SharePoint Syntex 採用：快速入門</span><span class="sxs-lookup"><span data-stu-id="10363-196">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)