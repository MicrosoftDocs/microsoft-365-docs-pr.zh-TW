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
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: db54ff053dcb1c9c1c608608ab1a37da8090cdb3
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087508"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="bbf8b-103">Microsoft SharePoint Syntex 採用：快速入門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="bbf8b-104">請將 SharePoint Syntex 中可用的智慧內容服務看作有三個部分：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="bbf8b-105">**內容瞭解：** 建立無程式碼 AI 模型，以分類及提取內容中的資訊，以自動套用中繼資料以進行知識探索和重複使用。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="bbf8b-106">深入瞭解 [內容瞭解](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="bbf8b-107">**內容處理：** 自動化內容的捕獲、攝取和分類，並使用 Power 自動化簡化以內容為中心的程式。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="bbf8b-108">深入瞭解 [內容處理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="bbf8b-109">**內容規範：** 控制和管理內容，以改進安全性和管理與 Microsoft 資訊保護的整合。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="bbf8b-110">透過全新的 AI 服務和功能，您可以使用 SharePoint Syntex，將內容瞭解和分類應用程式直接建立到內容管理流程中：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex:</span></span>

|<span data-ttu-id="bbf8b-111">手動輸入</span><span class="sxs-lookup"><span data-stu-id="bbf8b-111">Manual entry</span></span>| <span data-ttu-id="bbf8b-112">表單處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-112">Form processing</span></span> | <span data-ttu-id="bbf8b-113">檔瞭解</span><span class="sxs-lookup"><span data-stu-id="bbf8b-113">Document understanding</span></span> |
|:-------|:--------|:--------|
| <span data-ttu-id="bbf8b-114">任何內容的資料錄入和勞動密集型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-114">Data entry and labor-intensive on any content</span></span> | <span data-ttu-id="bbf8b-115">處理數位內容-相片、掃描、回執、名片、含 OCR 的影片 & 文字</span><span class="sxs-lookup"><span data-stu-id="bbf8b-115">Process digital content - photos, scans, receipts, business cards, videos with OCR & text</span></span> |  <span data-ttu-id="bbf8b-116">從合約、簡歷及其他結構化檔捕獲內容類型和中繼資料</span><span class="sxs-lookup"><span data-stu-id="bbf8b-116">Capture content types and  metadata from contracts, resumes, and other structured documents</span></span> |
| <span data-ttu-id="bbf8b-117">Interactive</span><span class="sxs-lookup"><span data-stu-id="bbf8b-117">Interactive</span></span>   | <span data-ttu-id="bbf8b-118">預先構建、自動化</span><span class="sxs-lookup"><span data-stu-id="bbf8b-118">Pre-built, automated</span></span>   | <span data-ttu-id="bbf8b-119">自訂、協助</span><span class="sxs-lookup"><span data-stu-id="bbf8b-119">Custom, assisted</span></span>   | <span data-ttu-id="bbf8b-120">自訂、相容性</span><span class="sxs-lookup"><span data-stu-id="bbf8b-120">Custom, compliant</span></span> |
| <span data-ttu-id="bbf8b-121">工作中的人員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-121">People doing the work</span></span> | <span data-ttu-id="bbf8b-122">由主題專家教授 (Sme) 。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-122">Taught by your subject matter experts (SMEs).</span></span> <span data-ttu-id="bbf8b-123">從合約、簡歷、其他非結構化檔捕獲內容類型和中繼資料。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-123">Capture content types and  metadata from contracts, resumes, other unstructured documents.</span></span> | <span data-ttu-id="bbf8b-124">Sme 的相關程度較低。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-124">SMEs are less involved.</span></span> <span data-ttu-id="bbf8b-125">從採購訂單、應用程式、其他半結構化及結構化檔</span><span class="sxs-lookup"><span data-stu-id="bbf8b-125">from purchase orders, applications, other semi structured and structured documents</span></span> |

<span data-ttu-id="bbf8b-126">下表說明當您使用 SharePoint Syntex 時所獲得的功能：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-126">The following table explains what you get when you use SharePoint Syntex:</span></span>

| <span data-ttu-id="bbf8b-127">表單處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-127">Form processing</span></span> | <span data-ttu-id="bbf8b-128">檔瞭解</span><span class="sxs-lookup"><span data-stu-id="bbf8b-128">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="bbf8b-129">適用于 APAC，澳大利亞，加拿大，EU，日本，拉丁美洲，UK，US</span><span class="sxs-lookup"><span data-stu-id="bbf8b-129">Available in APAC, Australia, Canada, EU, JP, LATAM, UK, US</span></span> | <span data-ttu-id="bbf8b-130">可用於所有地區</span><span class="sxs-lookup"><span data-stu-id="bbf8b-130">Available in all regions</span></span> |
| <span data-ttu-id="bbf8b-131">使用 AI Builder 學分-1M 學分 = 2000 頁面;消耗額是大約2000個發票 = 2 個單位。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-131">Uses AI Builder credits - 1M credits = 2000 pages; Consumption is about 2000 invoices=2 units.</span></span> <span data-ttu-id="bbf8b-132">需要電源自動化-如果您需要更多您可以新增它。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-132">Power Automate is required - if you need more you can add it.</span></span> <span data-ttu-id="bbf8b-133">為購買的300個以上的授權所指派的1M 學分。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-133">1M credits allocated for 300+ licenses purchased.</span></span> <span data-ttu-id="bbf8b-134">您也可以個別購買學分。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-134">You can also purchase credits separately.</span></span> | <span data-ttu-id="bbf8b-135">模型在所有拉丁字母表語言上都可以運作。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-135">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="bbf8b-136">除了英文：德文、瑞典文、法文、西班牙文、義大利文和葡萄牙文。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-136">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="bbf8b-137">針對預設的一般資料服務環境進行布建</span><span class="sxs-lookup"><span data-stu-id="bbf8b-137">Provisioned against the default common data service environment</span></span>| <span data-ttu-id="bbf8b-138">不具備容量限制。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-138">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="bbf8b-139">有兩種不同的方式可以瞭解您的內容。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-139">There are two different ways of understanding your content.</span></span> <span data-ttu-id="bbf8b-140">您使用的模型類型是以檔案格式和使用案例為基礎：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-140">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="bbf8b-141">表單處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-141">Form processing</span></span> | <span data-ttu-id="bbf8b-142">檔瞭解</span><span class="sxs-lookup"><span data-stu-id="bbf8b-142">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="bbf8b-143">從文件庫建立</span><span class="sxs-lookup"><span data-stu-id="bbf8b-143">Created from document library</span></span> | <span data-ttu-id="bbf8b-144">在內容中心建立，SharePoint Syntex 的一部分</span><span class="sxs-lookup"><span data-stu-id="bbf8b-144">Created in the content center, part of SharePoint Syntex</span></span> |
| <span data-ttu-id="bbf8b-145">在 AI 產生器中建立的模型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-145">Model created in AI builder</span></span> | <span data-ttu-id="bbf8b-146">在原生介面中建立的模型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-146">Model created in native interface</span></span> |
| <span data-ttu-id="bbf8b-147">用於半結構化檔案格式</span><span class="sxs-lookup"><span data-stu-id="bbf8b-147">Used for semi-structured file formats</span></span> | <span data-ttu-id="bbf8b-148">用於非結構化檔案格式</span><span class="sxs-lookup"><span data-stu-id="bbf8b-148">Used for unstructured file formats</span></span> |
| <span data-ttu-id="bbf8b-149">可設定的分類器</span><span class="sxs-lookup"><span data-stu-id="bbf8b-149">Settable classifier</span></span> | <span data-ttu-id="bbf8b-150">Trainable 具有選用擷取器的分類器</span><span class="sxs-lookup"><span data-stu-id="bbf8b-150">Trainable classifier with optional extractors</span></span> |
| <span data-ttu-id="bbf8b-151">限制于單一文件庫</span><span class="sxs-lookup"><span data-stu-id="bbf8b-151">Restricted to a single library</span></span> | <span data-ttu-id="bbf8b-152">可套用至多個文件庫</span><span class="sxs-lookup"><span data-stu-id="bbf8b-152">Can be applied to multiple libraries</span></span> |
| <span data-ttu-id="bbf8b-153">在 PDF，JPG，PNG 格式，總 50 MB/500 pp 進行訓練</span><span class="sxs-lookup"><span data-stu-id="bbf8b-153">Train on PDF, JPG, PNG format, total 50 MB/500 pp</span></span> | <span data-ttu-id="bbf8b-154">5-10 PDF、Office 或電子郵件檔案的火車，包含消極的範例</span><span class="sxs-lookup"><span data-stu-id="bbf8b-154">Train on 5-10 PDF, Office, or email files, including negative examples</span></span> |

<span data-ttu-id="bbf8b-155">SharePoint Syntex 與 Microsoft 365 規範功能整合，例如：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-155">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="bbf8b-156">根據檔保留或外來事件定義記錄原則的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-156">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="bbf8b-157">敏感度標籤，可設定 DLP、加密、共用及條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-157">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="bbf8b-158">使用者可以套用標籤，也可以 SharePoint Syntex AI 模型自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-158">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="bbf8b-159">分析和檔計畫提供標籤用法和原則的縮放式管理。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-159">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="bbf8b-160">識別試驗性商務案例以進行優化</span><span class="sxs-lookup"><span data-stu-id="bbf8b-160">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="bbf8b-161">若要準備在組織中使用 SharePoint Syntex，您必須先瞭解其有用的案例。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-161">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="bbf8b-162">原因可協助決定所需的模型，以及如何根據要套用模型的位置來組織組織。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-162">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="bbf8b-163">以下是一些檔理解可協助貴組織的案例：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-163">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="bbf8b-164">內容處理：處理合約、工作說明及其他類似表單的檔。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-164">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="bbf8b-165">使用表單，訓練模型以瞭解和對應欄位，然後執行表單以自動收集資料。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-165">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="bbf8b-166">如需詳細資訊，請參閱 [表單處理一覽](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-166">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="bbf8b-167">發票分析：從發票拔出相關的詳細資料，確定他們遵循原則或進行適當處理。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-167">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="bbf8b-168">請思考 SharePoint Syntex 可如何協助您的組織的方式：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-168">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="bbf8b-169">自動化商務程式</span><span class="sxs-lookup"><span data-stu-id="bbf8b-169">Automate business processes</span></span>
- <span data-ttu-id="bbf8b-170">提高搜尋精確度</span><span class="sxs-lookup"><span data-stu-id="bbf8b-170">Improve search accuracy</span></span>
- <span data-ttu-id="bbf8b-171">管理規範風險</span><span class="sxs-lookup"><span data-stu-id="bbf8b-171">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="bbf8b-172">表單處理案例範例</span><span class="sxs-lookup"><span data-stu-id="bbf8b-172">Form processing scenario example</span></span>

<span data-ttu-id="bbf8b-173">例如，您可以使用 SharePoint Syntex 和電源自動化功能來設定處理常式，以追蹤和監控發票。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-173">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="bbf8b-174">設定儲存發票檔的文件庫。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-174">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="bbf8b-175">訓練模型，以辨識檔中的欄位。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-175">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="bbf8b-176">將您要追蹤的欄位解壓縮到清單中。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-176">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="bbf8b-177">設定流程以通知您特定的事件，例如：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-177">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="bbf8b-178">新增新的發票。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-178">A new invoice is added.</span></span>
    - <span data-ttu-id="bbf8b-179">發票超過其到期日。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-179">An invoice is past its due date.</span></span>
    - <span data-ttu-id="bbf8b-180">發票的數量大於您的自動核准金額。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-180">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 SharePoint Syntex 和電源自動化來追蹤和監控發票](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="bbf8b-182">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-182">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="bbf8b-183">從發票自動提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-183">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="bbf8b-184">使用工作流程對發票採取動作，以減少潛在的錯誤並確保更好的相容性，並通知您有任何問題。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-184">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="bbf8b-185">檔瞭解案例範例</span><span class="sxs-lookup"><span data-stu-id="bbf8b-185">Document understanding scenario example</span></span>

<span data-ttu-id="bbf8b-186">在另一個範例中，您可以設定處理常式來識別貴公司與其他公司或個人的合約。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-186">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="bbf8b-187">您可以設定模型，以從這些合約提取重要資訊，例如用戶端名稱、費用、日期或其他重要資訊，並將其新增到文件庫中，您可以快速查看。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-187">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="bbf8b-188">您也可以在文件庫上套用保留標籤，以確保合約在特定時間長度之前不能刪除，以符合您的商務法規。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-188">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="bbf8b-189">從內容中心開始，並建立新的檔瞭解合約模型。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-189">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="bbf8b-190">上傳範例檔，以取得正值和消極的範例，然後執行訓練以識別合同檔，並檢查結果。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-190">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="bbf8b-191">訓練解壓縮程式以識別合同中的欄位，例如用戶端名稱、費用和日期，然後測試解壓縮程式。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-191">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="bbf8b-192">模型完成時，將模型套用至您可以上傳合同的文件庫。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-192">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="bbf8b-193">將保留標籤套用至 date 功能變數，以便在您的組織需要合同時，將合同保留在文件庫中。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-193">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![使用 SharePoint Syntex 和保留標籤來追蹤和監控合約](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="bbf8b-195">當您自動化此案例時，您可以：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-195">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="bbf8b-196">自動從合約提取資料，而不是手動提取資料，以節省時間和金錢。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-196">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="bbf8b-197">使用保留標籤確保合約已正確保留，以確保更好地相容。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-197">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="bbf8b-198">識別案例的秘訣</span><span class="sxs-lookup"><span data-stu-id="bbf8b-198">Tips for identifying scenarios</span></span>

<span data-ttu-id="bbf8b-199">當您考慮要考慮的商務案例時，請詢問您下列問題：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-199">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="bbf8b-200">是否會解決實際的問題？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-200">Does it solve a real problem?</span></span>
- <span data-ttu-id="bbf8b-201">是否會廣泛使用或會影響整體效果？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-201">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="bbf8b-202">是否可獲得？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-202">Is it obtainable?</span></span>
- <span data-ttu-id="bbf8b-203">您可以衡量是否成功？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-203">Can you measure success?</span></span>

<span data-ttu-id="bbf8b-204">根據影響和簡化的執行排定案例的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-204">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="bbf8b-205">讓您的初始焦點區域可輕鬆實施，也是較高的影響案例。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-205">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="bbf8b-206">取消的優先順序較低的影響案例很難實施。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-206">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="bbf8b-207">識別角色 & 責任</span><span class="sxs-lookup"><span data-stu-id="bbf8b-207">Identify roles & responsibilities</span></span>

<span data-ttu-id="bbf8b-208">決定貴組織中誰將建立及管理模型？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-208">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="bbf8b-209">可能包含下列角色：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-209">The following roles might be involved:</span></span>

| <span data-ttu-id="bbf8b-210">SharePoint/知識系統管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-210">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="bbf8b-211">電源平臺管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-211">Power Platform admin</span></span> | <span data-ttu-id="bbf8b-212">知識管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-212">Knowledge manager</span></span> | <span data-ttu-id="bbf8b-213">模型擁有者</span><span class="sxs-lookup"><span data-stu-id="bbf8b-213">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8b-214">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="bbf8b-214">AAD role</span></span>| <span data-ttu-id="bbf8b-215">新增角色</span><span class="sxs-lookup"><span data-stu-id="bbf8b-215">ADD role</span></span> | <span data-ttu-id="bbf8b-216">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="bbf8b-216">AAD role</span></span> | <span data-ttu-id="bbf8b-217">風雲人物</span><span class="sxs-lookup"><span data-stu-id="bbf8b-217">Champions</span></span> |
| <span data-ttu-id="bbf8b-218">設定表單處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-218">Configure form processing</span></span> | <span data-ttu-id="bbf8b-219">設定一般資料服務環境進行表單處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-219">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="bbf8b-220">收集使用案例</span><span class="sxs-lookup"><span data-stu-id="bbf8b-220">Gather use cases</span></span> | <span data-ttu-id="bbf8b-221">收集商務使用案例</span><span class="sxs-lookup"><span data-stu-id="bbf8b-221">Gather business use cases</span></span> |
| <span data-ttu-id="bbf8b-222">管理內容中心和許可權</span><span class="sxs-lookup"><span data-stu-id="bbf8b-222">Manage content centers and permissions</span></span>| <span data-ttu-id="bbf8b-223">購買及分派 AIB 學分</span><span class="sxs-lookup"><span data-stu-id="bbf8b-223">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="bbf8b-224">建立最佳作法並回顧模型分析</span><span class="sxs-lookup"><span data-stu-id="bbf8b-224">Establish best practices and review model analytics</span></span> | <span data-ttu-id="bbf8b-225">建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-225">Create and apply models</span></span> |

<span data-ttu-id="bbf8b-226">知識管理員、商務程式擁有人和內容模型擁有者建立組織的範例模型和冠軍採用。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-226">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="bbf8b-227">其他可能參與的人員：合規性管理員、分類法管理員。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-227">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="bbf8b-228">他們會在何處建立及套用模型？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-228">Where will they build and apply the models?</span></span> <span data-ttu-id="bbf8b-229">是否有現有的進程或存放庫可以增強？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-229">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="bbf8b-230">表單處理：決定將取得表單處理動作的網站。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-230">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="bbf8b-231">檔瞭解：您可以為不同的業務區域建立多個內容中心。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-231">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="bbf8b-232">戰略定位</span><span class="sxs-lookup"><span data-stu-id="bbf8b-232">Strategic positioning</span></span>

<span data-ttu-id="bbf8b-233">與相關者合作，確定他們已對齊使用 SharePoint Syntex 的策略。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-233">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="bbf8b-234">調查並提供下列資源，以協助此位置：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-234">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="bbf8b-235">商務成果：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-235">Business outcomes:</span></span>
  - <span data-ttu-id="bbf8b-236">潛在的會計結果</span><span class="sxs-lookup"><span data-stu-id="bbf8b-236">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="bbf8b-237">潛在的靈活性結果</span><span class="sxs-lookup"><span data-stu-id="bbf8b-237">Potential agility outcomes</span></span>
  - <span data-ttu-id="bbf8b-238">商務成果範本</span><span class="sxs-lookup"><span data-stu-id="bbf8b-238">Business outcome template</span></span>
- <span data-ttu-id="bbf8b-239">專案關係人/Exec 承辦人購買/對齊</span><span class="sxs-lookup"><span data-stu-id="bbf8b-239">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="bbf8b-240">業務案例卡座</span><span class="sxs-lookup"><span data-stu-id="bbf8b-240">Business case decks</span></span>
  - <span data-ttu-id="bbf8b-241">財務模型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-241">Financial models</span></span>
  - <span data-ttu-id="bbf8b-242">公司就緒性-文化</span><span class="sxs-lookup"><span data-stu-id="bbf8b-242">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="bbf8b-243">識別專案關係人</span><span class="sxs-lookup"><span data-stu-id="bbf8b-243">Identify stakeholders</span></span>

<span data-ttu-id="bbf8b-244">識別專案的利益關係人。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-244">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="bbf8b-245">角色</span><span class="sxs-lookup"><span data-stu-id="bbf8b-245">Role</span></span> |<span data-ttu-id="bbf8b-246">責任</span><span class="sxs-lookup"><span data-stu-id="bbf8b-246">Responsibilities</span></span> |<span data-ttu-id="bbf8b-247">部門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-247">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="bbf8b-248">執行贊助者 (s) </span><span class="sxs-lookup"><span data-stu-id="bbf8b-248">Executive sponsor(s)</span></span>   | <span data-ttu-id="bbf8b-249">向公司傳達高層遠景和價值</span><span class="sxs-lookup"><span data-stu-id="bbf8b-249">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="bbf8b-250">執行領導</span><span class="sxs-lookup"><span data-stu-id="bbf8b-250">Executive leadership</span></span>   |
| <span data-ttu-id="bbf8b-251">專案負責人 (s) </span><span class="sxs-lookup"><span data-stu-id="bbf8b-251">Project lead(s)</span></span> | <span data-ttu-id="bbf8b-252">監督整個啟動執行和部署程式</span><span class="sxs-lookup"><span data-stu-id="bbf8b-252">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="bbf8b-253">專案管理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-253">Project management</span></span> |
| <span data-ttu-id="bbf8b-254">知識管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-254">Knowledge administrators</span></span>| <span data-ttu-id="bbf8b-255">建立及管理內容中心</span><span class="sxs-lookup"><span data-stu-id="bbf8b-255">Create and manage the content centers</span></span> | <span data-ttu-id="bbf8b-256">IT 或其他部門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-256">IT or other department</span></span>|
| <span data-ttu-id="bbf8b-257">內容管理員和模型擁有人</span><span class="sxs-lookup"><span data-stu-id="bbf8b-257">Content managers and model owners</span></span>| <span data-ttu-id="bbf8b-258">收集使用案例及建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="bbf8b-258">Gather use cases and create and apply models</span></span> | <span data-ttu-id="bbf8b-259">任何部門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-259">Any department</span></span>|
| <span data-ttu-id="bbf8b-260">風雲人物</span><span class="sxs-lookup"><span data-stu-id="bbf8b-260">Champions</span></span> | <span data-ttu-id="bbf8b-261">協助 evangelize 及管理異議處理</span><span class="sxs-lookup"><span data-stu-id="bbf8b-261">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="bbf8b-262">任何部門 (人員) </span><span class="sxs-lookup"><span data-stu-id="bbf8b-262">Any department (staff)</span></span> |
| <span data-ttu-id="bbf8b-263">承租人管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-263">Tenant administrator</span></span> | <span data-ttu-id="bbf8b-264">設定租使用者層級設定</span><span class="sxs-lookup"><span data-stu-id="bbf8b-264">Configure tenant-level settings</span></span> | <span data-ttu-id="bbf8b-265">IT 部門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-265">IT department</span></span>|
| <span data-ttu-id="bbf8b-266">Power Platform 系統管理員</span><span class="sxs-lookup"><span data-stu-id="bbf8b-266">Power Platform administrator</span></span>| <span data-ttu-id="bbf8b-267">設定一般資料服務環境</span><span class="sxs-lookup"><span data-stu-id="bbf8b-267">Configure common data services environment</span></span> | <span data-ttu-id="bbf8b-268">IT 部門</span><span class="sxs-lookup"><span data-stu-id="bbf8b-268">IT department</span></span>|

> [!Note]
> <span data-ttu-id="bbf8b-269">雖然我們建議您在整個部署中完成上述每個角色，但您可能會發現您不需要所有這些角色即可開始使用已識別的解決方案。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-269">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="bbf8b-270">準備工作表</span><span class="sxs-lookup"><span data-stu-id="bbf8b-270">Readiness checklist</span></span>

<span data-ttu-id="bbf8b-271">若要準備好執行 SharePoint Syntex，您必須執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-271">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![內容瞭解的準備工作](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="bbf8b-273">規劃結束狀態</span><span class="sxs-lookup"><span data-stu-id="bbf8b-273">Plan the end state</span></span>
    - <span data-ttu-id="bbf8b-274">檔理解模型是指這種方式，而不是結束。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-274">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="bbf8b-275">規劃如何利用下列各項所提取之中繼資料的價值：</span><span class="sxs-lookup"><span data-stu-id="bbf8b-275">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="bbf8b-276">搜尋</span><span class="sxs-lookup"><span data-stu-id="bbf8b-276">Search</span></span>
      - <span data-ttu-id="bbf8b-277">篩選和查看格式設定</span><span class="sxs-lookup"><span data-stu-id="bbf8b-277">Filtering and view formatting</span></span>
      - <span data-ttu-id="bbf8b-278">合規性</span><span class="sxs-lookup"><span data-stu-id="bbf8b-278">Compliance</span></span>
      - <span data-ttu-id="bbf8b-279">自動化</span><span class="sxs-lookup"><span data-stu-id="bbf8b-279">Automation</span></span>
2. <span data-ttu-id="bbf8b-280">識別</span><span class="sxs-lookup"><span data-stu-id="bbf8b-280">Identify</span></span>
    - <span data-ttu-id="bbf8b-281">瞭解現有的資訊架構和內容管理功能使用。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-281">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="bbf8b-282">是否有任何現有的內容類型適合模型？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-282">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="bbf8b-283">中繼資料會改善哪些現有的處理常式？</span><span class="sxs-lookup"><span data-stu-id="bbf8b-283">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="bbf8b-284">Design</span><span class="sxs-lookup"><span data-stu-id="bbf8b-284">Design</span></span>
    - <span data-ttu-id="bbf8b-285">設計您的資訊架構、受管理的中繼資料和內容類型的方法</span><span class="sxs-lookup"><span data-stu-id="bbf8b-285">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="bbf8b-286">設計定義、建立、管理的程式。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-286">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="bbf8b-287">與您的組織合作</span><span class="sxs-lookup"><span data-stu-id="bbf8b-287">Engage your organization</span></span>

1. <span data-ttu-id="bbf8b-288">找出有序的持有者、確認案例，以及制定專案計劃。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-288">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="bbf8b-289">設定並套用授權。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-289">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="bbf8b-290">開始認知與訓練–招聘冠軍。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-290">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="bbf8b-291">分階段進行。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-291">Roll out in stages.</span></span>  
1. <span data-ttu-id="bbf8b-292">收集意見反應並進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-292">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="bbf8b-293">根據需要，隨著流量成長對任何 AI 產生器的使用。</span><span class="sxs-lookup"><span data-stu-id="bbf8b-293">As usage grows plan for any AI Builder credits as needed.</span></span>
