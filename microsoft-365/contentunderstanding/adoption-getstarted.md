---
title: Microsoft SharePoint Syntex 採用：快速入門
description: 瞭解如何在組織中使用和執行 SharePoint Syntex，以協助您解決業務問題。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597055"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="dbcae-103">Microsoft SharePoint Syntex 採用：快速入門</span><span class="sxs-lookup"><span data-stu-id="dbcae-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="dbcae-104">請將 SharePoint Syntex 中可用的智慧內容服務看作有三個部分：</span><span class="sxs-lookup"><span data-stu-id="dbcae-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="dbcae-105">**內容瞭解：** 建立無程式碼 AI 模型，以分類及提取內容中的資訊，以自動套用中繼資料以進行知識探索和重複使用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="dbcae-106">深入瞭解 [內容瞭解](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dbcae-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="dbcae-107">**內容處理：** 自動化內容的捕獲、攝取和分類，並使用 Power 自動化簡化以內容為中心的流程。</span><span class="sxs-lookup"><span data-stu-id="dbcae-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="dbcae-108">深入瞭解 [內容處理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dbcae-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="dbcae-109">**內容規範：** 控制和管理內容，以改進安全性和管理與 Microsoft 資訊保護的整合。</span><span class="sxs-lookup"><span data-stu-id="dbcae-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="dbcae-110">透過全新的 AI 服務和功能，您可以使用 SharePoint Syntex，將內容瞭解和分類應用程式直接組建至內容管理流程。</span><span class="sxs-lookup"><span data-stu-id="dbcae-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="dbcae-111">有兩種不同的方式可以瞭解您的內容。</span><span class="sxs-lookup"><span data-stu-id="dbcae-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="dbcae-112">您使用的模型類型是以檔案格式和使用案例為基礎：</span><span class="sxs-lookup"><span data-stu-id="dbcae-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="dbcae-113">表單處理</span><span class="sxs-lookup"><span data-stu-id="dbcae-113">Form processing</span></span> | <span data-ttu-id="dbcae-114">檔瞭解</span><span class="sxs-lookup"><span data-stu-id="dbcae-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="dbcae-115">從文件庫建立。</span><span class="sxs-lookup"><span data-stu-id="dbcae-115">Created from document library.</span></span> | <span data-ttu-id="dbcae-116">在內容中心建立，SharePoint Syntex 的一部分。</span><span class="sxs-lookup"><span data-stu-id="dbcae-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="dbcae-117">在 [AI 產生器] 中建立的模型。</span><span class="sxs-lookup"><span data-stu-id="dbcae-117">Model created in AI builder.</span></span> | <span data-ttu-id="dbcae-118">在原生介面中建立的模型。</span><span class="sxs-lookup"><span data-stu-id="dbcae-118">Model created in native interface.</span></span> |
| <span data-ttu-id="dbcae-119">用於半結構化檔案格式。</span><span class="sxs-lookup"><span data-stu-id="dbcae-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="dbcae-120">用於非結構化檔案格式。</span><span class="sxs-lookup"><span data-stu-id="dbcae-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="dbcae-121">可設定的分類器。</span><span class="sxs-lookup"><span data-stu-id="dbcae-121">Settable classifier.</span></span> | <span data-ttu-id="dbcae-122">Trainable 具有選用擷取器的分類器。</span><span class="sxs-lookup"><span data-stu-id="dbcae-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="dbcae-123">限制于單一文件庫。</span><span class="sxs-lookup"><span data-stu-id="dbcae-123">Restricted to a single library.</span></span> | <span data-ttu-id="dbcae-124">可套用至多個文件庫。</span><span class="sxs-lookup"><span data-stu-id="dbcae-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="dbcae-125">在 PDF，JPG，PNG 格式，總 50 MB/500 pp 進行訓練。</span><span class="sxs-lookup"><span data-stu-id="dbcae-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="dbcae-126">在 5-10 PDF、Office 或電子郵件檔上訓練，包含負的範例。</span><span class="sxs-lookup"><span data-stu-id="dbcae-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="dbcae-127">如需更完整的功能比較，請參閱 [檔瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="dbcae-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="dbcae-128">識別試驗性商務案例以進行優化</span><span class="sxs-lookup"><span data-stu-id="dbcae-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="dbcae-129">若要準備在組織中使用 SharePoint Syntex，您必須先瞭解其有用的案例。</span><span class="sxs-lookup"><span data-stu-id="dbcae-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="dbcae-130">「原因」會協助決定所需的模型，以及如何根據模型套用的位置來組織組織。</span><span class="sxs-lookup"><span data-stu-id="dbcae-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="dbcae-131">以下是一些檔理解可協助貴組織的案例：</span><span class="sxs-lookup"><span data-stu-id="dbcae-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="dbcae-132">**內容處理：** 處理合約、工作說明及其他類似表單的檔。</span><span class="sxs-lookup"><span data-stu-id="dbcae-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="dbcae-133">使用表單，訓練模型以瞭解和對應欄位，然後執行表單以自動收集資料。</span><span class="sxs-lookup"><span data-stu-id="dbcae-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="dbcae-134">如需詳細資訊，請參閱 [表單處理一覽](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dbcae-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="dbcae-135">**發票分析：** 從發票拔出相關的詳細資料，確定他們遵循原則或進行適當處理。</span><span class="sxs-lookup"><span data-stu-id="dbcae-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="dbcae-136">請思考 SharePoint Syntex 可如何協助您的組織的方式：</span><span class="sxs-lookup"><span data-stu-id="dbcae-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="dbcae-137">自動化商務程式</span><span class="sxs-lookup"><span data-stu-id="dbcae-137">Automate business processes</span></span>
- <span data-ttu-id="dbcae-138">提高搜尋精確度</span><span class="sxs-lookup"><span data-stu-id="dbcae-138">Improve search accuracy</span></span>
- <span data-ttu-id="dbcae-139">管理規範風險</span><span class="sxs-lookup"><span data-stu-id="dbcae-139">Manage compliance risk</span></span>

<span data-ttu-id="dbcae-140">當您考慮要考慮的商務案例時，請詢問您下列問題：</span><span class="sxs-lookup"><span data-stu-id="dbcae-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="dbcae-141">是否會解決實際的問題？</span><span class="sxs-lookup"><span data-stu-id="dbcae-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="dbcae-142">是否會廣泛使用或會影響整體效果？</span><span class="sxs-lookup"><span data-stu-id="dbcae-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="dbcae-143">是否可獲得？</span><span class="sxs-lookup"><span data-stu-id="dbcae-143">Is it obtainable?</span></span>
- <span data-ttu-id="dbcae-144">您可以衡量是否成功？</span><span class="sxs-lookup"><span data-stu-id="dbcae-144">Can you measure success?</span></span>

<span data-ttu-id="dbcae-145">根據影響和簡化的執行排定案例的優先順序。</span><span class="sxs-lookup"><span data-stu-id="dbcae-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="dbcae-146">讓您的初始焦點區域可輕鬆實施，也是較高的影響案例。</span><span class="sxs-lookup"><span data-stu-id="dbcae-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="dbcae-147">取消的優先順序較低的影響案例很難實施。</span><span class="sxs-lookup"><span data-stu-id="dbcae-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="dbcae-148">使用下列範例案例，提示您如何在組織中使用 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="dbcae-148">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

### <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="dbcae-149">案例：使用表單處理從發票追蹤資料</span><span class="sxs-lookup"><span data-stu-id="dbcae-149">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="dbcae-150">例如，您可以使用 SharePoint Syntex 和電源自動化功能來設定處理常式，以追蹤和監控發票。</span><span class="sxs-lookup"><span data-stu-id="dbcae-150">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="dbcae-151">設定儲存發票檔的文件庫。</span><span class="sxs-lookup"><span data-stu-id="dbcae-151">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="dbcae-152">訓練模型，以辨識檔中的欄位。</span><span class="sxs-lookup"><span data-stu-id="dbcae-152">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="dbcae-153">將您要追蹤的欄位解壓縮到清單中。</span><span class="sxs-lookup"><span data-stu-id="dbcae-153">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="dbcae-154">設定流程以通知您特定的事件，例如：</span><span class="sxs-lookup"><span data-stu-id="dbcae-154">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="dbcae-155">新增新的發票。</span><span class="sxs-lookup"><span data-stu-id="dbcae-155">A new invoice is added.</span></span>
    - <span data-ttu-id="dbcae-156">發票超過其到期日。</span><span class="sxs-lookup"><span data-stu-id="dbcae-156">An invoice is past its due date.</span></span>
    - <span data-ttu-id="dbcae-157">發票的數量大於您的自動核准金額。</span><span class="sxs-lookup"><span data-stu-id="dbcae-157">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 SharePoint Syntex 和電源自動化來追蹤和監控發票](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="dbcae-159">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="dbcae-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="dbcae-160">從發票自動提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="dbcae-160">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="dbcae-161">使用工作流程檢查發票，並在發生問題時通知您，以減少潛在的錯誤並確保更好的相容性。</span><span class="sxs-lookup"><span data-stu-id="dbcae-161">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="dbcae-162">案例：使用檔瞭解追蹤合同中的資訊</span><span class="sxs-lookup"><span data-stu-id="dbcae-162">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="dbcae-163">在另一個範例中，您可以設定處理常式，識別您的公司與其他公司或個人的合約。</span><span class="sxs-lookup"><span data-stu-id="dbcae-163">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="dbcae-164">設定模型，以從這些合約提取重要資訊，例如用戶端名稱、費用、日期或其他重要資訊，並將資訊新增至文件庫中，您可以快速查看這些欄位。</span><span class="sxs-lookup"><span data-stu-id="dbcae-164">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="dbcae-165">請將保留標籤套用到文件庫，以確保在適當的時間長度之前，不能刪除合約，以符合您的商務法規。</span><span class="sxs-lookup"><span data-stu-id="dbcae-165">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="dbcae-166">從內容中心開始，並建立新的檔瞭解合約模型。</span><span class="sxs-lookup"><span data-stu-id="dbcae-166">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="dbcae-167">上傳範例檔，以取得正值和消極的範例，然後執行訓練以識別合同檔，並檢查結果。</span><span class="sxs-lookup"><span data-stu-id="dbcae-167">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="dbcae-168">訓練解壓縮程式以識別合同中的欄位，例如用戶端名稱、費用和日期，然後測試解壓縮程式。</span><span class="sxs-lookup"><span data-stu-id="dbcae-168">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="dbcae-169">模型完成時，將模型套用至您可以上傳合同的文件庫。</span><span class="sxs-lookup"><span data-stu-id="dbcae-169">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="dbcae-170">將保留標籤套用至日期欄位，讓合同保留在文件庫中所需的時間長度。</span><span class="sxs-lookup"><span data-stu-id="dbcae-170">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![使用 SharePoint Syntex 和保留標籤來追蹤和監控合約](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="dbcae-172">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="dbcae-172">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="dbcae-173">自動從合約提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="dbcae-173">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="dbcae-174">使用保留標籤確保合約已正確保留，以確保更好地相容。</span><span class="sxs-lookup"><span data-stu-id="dbcae-174">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="dbcae-175">案例：根據 SharePoint Syntex，避免記錄管理、檔管理及規範程式的風險</span><span class="sxs-lookup"><span data-stu-id="dbcae-175">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="dbcae-176">降低風險是大多數公司的共同目標。</span><span class="sxs-lookup"><span data-stu-id="dbcae-176">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="dbcae-177">您可能需要：</span><span class="sxs-lookup"><span data-stu-id="dbcae-177">You might need:</span></span>

- <span data-ttu-id="dbcae-178">在您的租使用者中提供/強制執行資訊管理的更好方法。</span><span class="sxs-lookup"><span data-stu-id="dbcae-178">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="dbcae-179">若要改善檔的分類、電子郵件及其他形式的通訊視為專案的「記錄」的系統。</span><span class="sxs-lookup"><span data-stu-id="dbcae-179">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="dbcae-180">若要審核收據、合約等等，以確保符合公司原則。</span><span class="sxs-lookup"><span data-stu-id="dbcae-180">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="dbcae-181">確定專案具備法規遵從性所需的所有檔。</span><span class="sxs-lookup"><span data-stu-id="dbcae-181">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="dbcae-182">設定一些與 SharePoint Syntex 相容的處理常式，以取得及適當分類、審核和旗標需要更好的控管的檔和表單。</span><span class="sxs-lookup"><span data-stu-id="dbcae-182">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="dbcae-183">您可以依靠 SharePoint Syntex，自動將內容分類，而不需依賴使用者手動標記，或是合規性小組手動套用控管規則和封存。</span><span class="sxs-lookup"><span data-stu-id="dbcae-183">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="dbcae-184">而且，您可以啟用簡化的搜尋體驗、管理資料量、套用記錄管理和保留原則，以確保法規遵從性，以及最佳作法封存及清除作法。</span><span class="sxs-lookup"><span data-stu-id="dbcae-184">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="dbcae-185">當您自動化此案例時，您可以放心進行下列安全：</span><span class="sxs-lookup"><span data-stu-id="dbcae-185">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="dbcae-186">法規遵從性是 upheld 和降低風險。</span><span class="sxs-lookup"><span data-stu-id="dbcae-186">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="dbcae-187">分類和記錄管理的一致性及正確套用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-187">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="dbcae-188">控制內容量。</span><span class="sxs-lookup"><span data-stu-id="dbcae-188">Content volumes are controlled.</span></span>
- <span data-ttu-id="dbcae-189">員工可以輕鬆地在正確的內容中探索正確的資訊。</span><span class="sxs-lookup"><span data-stu-id="dbcae-189">Employees can easily discover the right information in the right context.</span></span>

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="dbcae-190">案例：從先前無法存取的檔捕獲資訊</span><span class="sxs-lookup"><span data-stu-id="dbcae-190">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="dbcae-191">大多數的組織都有大量的法律檔、原則、合約、HR 檔和控管指導方針。</span><span class="sxs-lookup"><span data-stu-id="dbcae-191">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="dbcae-192">請挖掘這些資料存放區，以解壓重要資訊，例如：專案、磁區、主題、人員、地理區域等等。</span><span class="sxs-lookup"><span data-stu-id="dbcae-192">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="dbcae-193">例如，HR director 必須快速存取所有人力資源檔，包括簡歷、HR 原則及其他表單。</span><span class="sxs-lookup"><span data-stu-id="dbcae-193">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="dbcae-194">他們想要從簡歷和其他 HR 相關檔快速識別必要的資訊，而不需透過檔手動 sifting。</span><span class="sxs-lookup"><span data-stu-id="dbcae-194">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="dbcae-195">他們在尋找一種解決方案，可讓他們快速找出所需的資訊，而不必手動搜尋數千個簡歷、HR 原則，以及可能分散于多個網站的其他檔。</span><span class="sxs-lookup"><span data-stu-id="dbcae-195">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="dbcae-196">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="dbcae-196">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="dbcae-197">從數位內容解除鎖定知識。</span><span class="sxs-lookup"><span data-stu-id="dbcae-197">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="dbcae-198">分類人力資源原則、簡歷、銷售檔、技術藍圖、帳戶計畫及提取資訊。</span><span class="sxs-lookup"><span data-stu-id="dbcae-198">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="dbcae-199">快速尋找您要尋找的正確資訊或檔。</span><span class="sxs-lookup"><span data-stu-id="dbcae-199">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="dbcae-200">立即獲得最新資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="dbcae-200">Get instant access to the latest information.</span></span>
- <span data-ttu-id="dbcae-201">縮短搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="dbcae-201">Reduce search times.</span></span>

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a><span data-ttu-id="dbcae-202">案例：改善資料處理以提供真知灼見 & analytics</span><span class="sxs-lookup"><span data-stu-id="dbcae-202">Scenario: Improve data processing to provide insights & analytics</span></span>

<span data-ttu-id="dbcae-203">例如，製藥公司可以使用 SharePoint Syntex，從 FDA 檔析取資訊，以回答他們的領導人所提出的問題。</span><span class="sxs-lookup"><span data-stu-id="dbcae-203">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="dbcae-204">讓答案變得更容易存取，可縮短產生這些回答所需的時間，並提高資料的可用性以產生更準確的領導問題答案。</span><span class="sxs-lookup"><span data-stu-id="dbcae-204">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="dbcae-205">例如，專案經理必須從我的領導小組快速為產品相關問題提供答案。</span><span class="sxs-lookup"><span data-stu-id="dbcae-205">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="dbcae-206">他們必須尋找與一個合併儀表板中的查詢相關的資訊和度量。</span><span class="sxs-lookup"><span data-stu-id="dbcae-206">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="dbcae-207">他們要尋找的解決方案會從產品標籤、產品 pamphlets 及其他材料提取所需的資訊，並產生整合報告，以供報告回其領導團隊時使用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-207">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="dbcae-208">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="dbcae-208">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="dbcae-209">縮短產生回應的時間。</span><span class="sxs-lookup"><span data-stu-id="dbcae-209">Reduce time to produce answers.</span></span>
- <span data-ttu-id="dbcae-210">提高資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="dbcae-210">Increase availability of data.</span></span>
- <span data-ttu-id="dbcae-211">提供更準確的答案。</span><span class="sxs-lookup"><span data-stu-id="dbcae-211">Provide more accurate answers.</span></span>

### <a name="scenario-automate-order-processing"></a><span data-ttu-id="dbcae-212">案例：自動化訂單處理</span><span class="sxs-lookup"><span data-stu-id="dbcae-212">Scenario: Automate order processing</span></span>

<span data-ttu-id="dbcae-213">使用 SharePoint Syntex，您可以縮短手動處理客戶訂單的時間。</span><span class="sxs-lookup"><span data-stu-id="dbcae-213">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="dbcae-214">例如，您可以使用 OCR 處理將訂單從傳真、電子郵件或紙張上傳至 SharePoint，然後從這些訂單中解壓縮中繼資料，以便您可以使用自動化程式來完成這些訂單。</span><span class="sxs-lookup"><span data-stu-id="dbcae-214">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="dbcae-215">例如，供應鏈管理員想要減少手動資料輸入所造成的錯誤。</span><span class="sxs-lookup"><span data-stu-id="dbcae-215">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="dbcae-216">他們想要避免以手動形式查看輸入客戶訂單的資料， (紙張、傳真或電子郵件) ，以降低業務系統的錯誤。</span><span class="sxs-lookup"><span data-stu-id="dbcae-216">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="dbcae-217">他們需要套用 AI 和機器學習技巧的解決方案，以驗證內送訂單資訊、提取核心資料，並自動將其推入 ERP 系統，以進行訂單履行和調解。</span><span class="sxs-lookup"><span data-stu-id="dbcae-217">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="dbcae-218">當您自動化此案例時，您可以確定：</span><span class="sxs-lookup"><span data-stu-id="dbcae-218">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="dbcae-219">訂單和運送的精確度增加。</span><span class="sxs-lookup"><span data-stu-id="dbcae-219">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="dbcae-220">減少與訂單或運送錯誤相關的費用或處罰。</span><span class="sxs-lookup"><span data-stu-id="dbcae-220">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="dbcae-221">縮短開票或付款的延遲。</span><span class="sxs-lookup"><span data-stu-id="dbcae-221">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="dbcae-222">減少人員成本。</span><span class="sxs-lookup"><span data-stu-id="dbcae-222">Personnel costs are reduced.</span></span>

### <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="dbcae-223">案例：簡化簽證更新程式</span><span class="sxs-lookup"><span data-stu-id="dbcae-223">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="dbcae-224">SharePoint Syntex 可協助您自動化重要合約資訊的提醒和續訂。</span><span class="sxs-lookup"><span data-stu-id="dbcae-224">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="dbcae-225">例如，HR 主管需要確定員工的簽證是最新的，且/或已在時間上更新。</span><span class="sxs-lookup"><span data-stu-id="dbcae-225">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="dbcae-226">他們想為人們提供簡單且直觀的處理常式來更新其簽證。</span><span class="sxs-lookup"><span data-stu-id="dbcae-226">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="dbcae-227">他們需要可從合約提取更新日期的解決方案，並在其更新日期接近時自動傳送員工提醒。</span><span class="sxs-lookup"><span data-stu-id="dbcae-227">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="dbcae-228">當您自動化此案例時，您可以確定：</span><span class="sxs-lookup"><span data-stu-id="dbcae-228">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="dbcae-229">減少非法規遵從性的層級。</span><span class="sxs-lookup"><span data-stu-id="dbcae-229">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="dbcae-230">已縮短手動提醒數目。</span><span class="sxs-lookup"><span data-stu-id="dbcae-230">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="dbcae-231">降低未達標的罰款數目。</span><span class="sxs-lookup"><span data-stu-id="dbcae-231">The number of fines for non-compliance is reduced.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="dbcae-232">識別角色 & 責任</span><span class="sxs-lookup"><span data-stu-id="dbcae-232">Identify roles & responsibilities</span></span>

<span data-ttu-id="dbcae-233">決定貴組織中誰將建立及管理模型？</span><span class="sxs-lookup"><span data-stu-id="dbcae-233">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="dbcae-234">可能包含下列角色：</span><span class="sxs-lookup"><span data-stu-id="dbcae-234">The following roles might be involved:</span></span>

| <span data-ttu-id="dbcae-235">SharePoint/知識系統管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-235">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="dbcae-236">電源平臺管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-236">Power Platform admin</span></span> | <span data-ttu-id="dbcae-237">知識管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-237">Knowledge manager</span></span> | <span data-ttu-id="dbcae-238">模型擁有者</span><span class="sxs-lookup"><span data-stu-id="dbcae-238">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="dbcae-239">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="dbcae-239">AAD role</span></span>| <span data-ttu-id="dbcae-240">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="dbcae-240">AAD role</span></span> | <span data-ttu-id="dbcae-241">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="dbcae-241">AAD role</span></span> | <span data-ttu-id="dbcae-242">風雲人物</span><span class="sxs-lookup"><span data-stu-id="dbcae-242">Champions</span></span> |
| <span data-ttu-id="dbcae-243">設定表單處理</span><span class="sxs-lookup"><span data-stu-id="dbcae-243">Configure form processing</span></span> | <span data-ttu-id="dbcae-244">設定一般資料服務環境進行表單處理</span><span class="sxs-lookup"><span data-stu-id="dbcae-244">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="dbcae-245">收集使用案例</span><span class="sxs-lookup"><span data-stu-id="dbcae-245">Gather use cases</span></span> | <span data-ttu-id="dbcae-246">收集商務使用案例</span><span class="sxs-lookup"><span data-stu-id="dbcae-246">Gather business use cases</span></span> |
| <span data-ttu-id="dbcae-247">管理內容中心和許可權</span><span class="sxs-lookup"><span data-stu-id="dbcae-247">Manage content centers and permissions</span></span>| <span data-ttu-id="dbcae-248">購買及分派 AIB 學分</span><span class="sxs-lookup"><span data-stu-id="dbcae-248">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="dbcae-249">建立最佳作法並回顧模型分析</span><span class="sxs-lookup"><span data-stu-id="dbcae-249">Establish best practices and review model analytics</span></span> | <span data-ttu-id="dbcae-250">建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="dbcae-250">Create and apply models</span></span> |

<span data-ttu-id="dbcae-251">知識管理員、商務程式擁有人和內容模型擁有者建立組織的範例模型和冠軍採用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-251">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="dbcae-252">其他可能參與的人員：合規性管理員、分類法管理員。</span><span class="sxs-lookup"><span data-stu-id="dbcae-252">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="dbcae-253">他們會在何處建立及套用模型？</span><span class="sxs-lookup"><span data-stu-id="dbcae-253">Where will they build and apply the models?</span></span> <span data-ttu-id="dbcae-254">是否有現有的進程或存放庫可以增強？</span><span class="sxs-lookup"><span data-stu-id="dbcae-254">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="dbcae-255">表單處理：決定將取得表單處理動作的網站。</span><span class="sxs-lookup"><span data-stu-id="dbcae-255">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="dbcae-256">檔瞭解：您可以為不同的業務區域建立多個內容中心。</span><span class="sxs-lookup"><span data-stu-id="dbcae-256">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="dbcae-257">戰略定位</span><span class="sxs-lookup"><span data-stu-id="dbcae-257">Strategic positioning</span></span>

<span data-ttu-id="dbcae-258">與相關者合作，確定他們已對齊使用 SharePoint Syntex 的策略。</span><span class="sxs-lookup"><span data-stu-id="dbcae-258">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="dbcae-259">調查並提供下列資源，以協助此位置：</span><span class="sxs-lookup"><span data-stu-id="dbcae-259">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="dbcae-260">商務成果：</span><span class="sxs-lookup"><span data-stu-id="dbcae-260">Business outcomes:</span></span>
  - <span data-ttu-id="dbcae-261">潛在的會計結果</span><span class="sxs-lookup"><span data-stu-id="dbcae-261">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="dbcae-262">潛在的靈活性結果</span><span class="sxs-lookup"><span data-stu-id="dbcae-262">Potential agility outcomes</span></span>
  - <span data-ttu-id="dbcae-263">商務成果範本</span><span class="sxs-lookup"><span data-stu-id="dbcae-263">Business outcome template</span></span>
- <span data-ttu-id="dbcae-264">專案關係人/Exec 承辦人購買/對齊</span><span class="sxs-lookup"><span data-stu-id="dbcae-264">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="dbcae-265">業務案例卡座</span><span class="sxs-lookup"><span data-stu-id="dbcae-265">Business case decks</span></span>
  - <span data-ttu-id="dbcae-266">財務模型</span><span class="sxs-lookup"><span data-stu-id="dbcae-266">Financial models</span></span>
  - <span data-ttu-id="dbcae-267">公司就緒性-文化</span><span class="sxs-lookup"><span data-stu-id="dbcae-267">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="dbcae-268">識別專案關係人</span><span class="sxs-lookup"><span data-stu-id="dbcae-268">Identify stakeholders</span></span>

<span data-ttu-id="dbcae-269">識別專案的利益關係人。</span><span class="sxs-lookup"><span data-stu-id="dbcae-269">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="dbcae-270">角色</span><span class="sxs-lookup"><span data-stu-id="dbcae-270">Role</span></span> |<span data-ttu-id="dbcae-271">責任</span><span class="sxs-lookup"><span data-stu-id="dbcae-271">Responsibilities</span></span> |<span data-ttu-id="dbcae-272">部門</span><span class="sxs-lookup"><span data-stu-id="dbcae-272">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="dbcae-273">執行贊助者 (s) </span><span class="sxs-lookup"><span data-stu-id="dbcae-273">Executive sponsor(s)</span></span>   | <span data-ttu-id="dbcae-274">向公司傳達高層遠景和價值</span><span class="sxs-lookup"><span data-stu-id="dbcae-274">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="dbcae-275">執行領導</span><span class="sxs-lookup"><span data-stu-id="dbcae-275">Executive leadership</span></span>   |
| <span data-ttu-id="dbcae-276">專案負責人 (s) </span><span class="sxs-lookup"><span data-stu-id="dbcae-276">Project lead(s)</span></span> | <span data-ttu-id="dbcae-277">監督整個啟動執行和部署程式</span><span class="sxs-lookup"><span data-stu-id="dbcae-277">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="dbcae-278">專案管理</span><span class="sxs-lookup"><span data-stu-id="dbcae-278">Project management</span></span> |
| <span data-ttu-id="dbcae-279">知識管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-279">Knowledge administrators</span></span>| <span data-ttu-id="dbcae-280">建立及管理內容中心</span><span class="sxs-lookup"><span data-stu-id="dbcae-280">Create and manage the content centers</span></span> | <span data-ttu-id="dbcae-281">IT 或其他部門</span><span class="sxs-lookup"><span data-stu-id="dbcae-281">IT or other department</span></span>|
| <span data-ttu-id="dbcae-282">內容管理員和模型擁有人</span><span class="sxs-lookup"><span data-stu-id="dbcae-282">Content managers and model owners</span></span>| <span data-ttu-id="dbcae-283">收集使用案例及建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="dbcae-283">Gather use cases and create and apply models</span></span> | <span data-ttu-id="dbcae-284">任何部門</span><span class="sxs-lookup"><span data-stu-id="dbcae-284">Any department</span></span>|
| <span data-ttu-id="dbcae-285">風雲人物</span><span class="sxs-lookup"><span data-stu-id="dbcae-285">Champions</span></span> | <span data-ttu-id="dbcae-286">協助 evangelize 及管理異議處理</span><span class="sxs-lookup"><span data-stu-id="dbcae-286">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="dbcae-287">任何部門 (人員) </span><span class="sxs-lookup"><span data-stu-id="dbcae-287">Any department (staff)</span></span> |
| <span data-ttu-id="dbcae-288">承租人管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-288">Tenant administrator</span></span> | <span data-ttu-id="dbcae-289">設定租使用者層級設定</span><span class="sxs-lookup"><span data-stu-id="dbcae-289">Configure tenant-level settings</span></span> | <span data-ttu-id="dbcae-290">IT 部門</span><span class="sxs-lookup"><span data-stu-id="dbcae-290">IT department</span></span>|
| <span data-ttu-id="dbcae-291">Power Platform 系統管理員</span><span class="sxs-lookup"><span data-stu-id="dbcae-291">Power Platform administrator</span></span>| <span data-ttu-id="dbcae-292">設定一般資料服務環境</span><span class="sxs-lookup"><span data-stu-id="dbcae-292">Configure common data services environment</span></span> | <span data-ttu-id="dbcae-293">IT 部門</span><span class="sxs-lookup"><span data-stu-id="dbcae-293">IT department</span></span>|

> [!Note]
> <span data-ttu-id="dbcae-294">雖然我們建議您在整個部署中完成上述每個角色，但您可能會發現您不需要所有這些角色即可開始使用已識別的解決方案。</span><span class="sxs-lookup"><span data-stu-id="dbcae-294">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="dbcae-295">準備工作表</span><span class="sxs-lookup"><span data-stu-id="dbcae-295">Readiness checklist</span></span>

<span data-ttu-id="dbcae-296">若要準備好執行 SharePoint Syntex，您必須執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="dbcae-296">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![內容瞭解的準備工作](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="dbcae-298">規劃結束狀態</span><span class="sxs-lookup"><span data-stu-id="dbcae-298">Plan the end state</span></span>
    - <span data-ttu-id="dbcae-299">檔理解模型是指這種方式，而不是結束。</span><span class="sxs-lookup"><span data-stu-id="dbcae-299">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="dbcae-300">規劃如何利用下列各項所提取之中繼資料的價值：</span><span class="sxs-lookup"><span data-stu-id="dbcae-300">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="dbcae-301">搜尋</span><span class="sxs-lookup"><span data-stu-id="dbcae-301">Search</span></span>
      - <span data-ttu-id="dbcae-302">篩選和查看格式設定</span><span class="sxs-lookup"><span data-stu-id="dbcae-302">Filtering and view formatting</span></span>
      - <span data-ttu-id="dbcae-303">合規性</span><span class="sxs-lookup"><span data-stu-id="dbcae-303">Compliance</span></span>
      - <span data-ttu-id="dbcae-304">自動化</span><span class="sxs-lookup"><span data-stu-id="dbcae-304">Automation</span></span>
2. <span data-ttu-id="dbcae-305">識別</span><span class="sxs-lookup"><span data-stu-id="dbcae-305">Identify</span></span>
    - <span data-ttu-id="dbcae-306">瞭解現有的資訊架構和內容管理功能使用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-306">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="dbcae-307">是否有任何現有的內容類型適合模型？</span><span class="sxs-lookup"><span data-stu-id="dbcae-307">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="dbcae-308">中繼資料會改善哪些現有的處理常式？</span><span class="sxs-lookup"><span data-stu-id="dbcae-308">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="dbcae-309">設計</span><span class="sxs-lookup"><span data-stu-id="dbcae-309">Design</span></span>
    - <span data-ttu-id="dbcae-310">設計您的資訊架構、受管理的中繼資料和內容類型的方法</span><span class="sxs-lookup"><span data-stu-id="dbcae-310">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="dbcae-311">設計定義、建立、管理的程式。</span><span class="sxs-lookup"><span data-stu-id="dbcae-311">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="dbcae-312">與您的組織合作</span><span class="sxs-lookup"><span data-stu-id="dbcae-312">Engage your organization</span></span>

1. <span data-ttu-id="dbcae-313">找出有序的持有者、確認案例，以及制定專案計劃。</span><span class="sxs-lookup"><span data-stu-id="dbcae-313">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="dbcae-314">設定並套用授權。</span><span class="sxs-lookup"><span data-stu-id="dbcae-314">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="dbcae-315">開始認知與訓練–招聘冠軍。</span><span class="sxs-lookup"><span data-stu-id="dbcae-315">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="dbcae-316">分階段進行。</span><span class="sxs-lookup"><span data-stu-id="dbcae-316">Roll out in stages.</span></span>  
1. <span data-ttu-id="dbcae-317">收集意見反應並進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="dbcae-317">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="dbcae-318">根據需要，隨著流量成長對任何 AI 產生器的使用。</span><span class="sxs-lookup"><span data-stu-id="dbcae-318">As usage grows plan for any AI Builder credits as needed.</span></span>
