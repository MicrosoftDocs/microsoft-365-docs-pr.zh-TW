---
title: Microsoft SharePoint Syntex 採用：快速入門
description: 瞭解如何在組織中使用和執行 SharePoint Syntex，以協助您解決業務問題。
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 62e65f9be25e2c482cca78577048d504ee93097a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698973"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="26bbd-103">Microsoft SharePoint Syntex 採用：快速入門</span><span class="sxs-lookup"><span data-stu-id="26bbd-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="26bbd-104">請將 SharePoint Syntex 中可用的智慧內容服務看作有三個部分：</span><span class="sxs-lookup"><span data-stu-id="26bbd-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="26bbd-105">**內容瞭解：** 建立無程式碼的 AI 模型，以分類及提取內容中的資訊，以自動套用中繼資料以進行知識探索和重複使用。</span><span class="sxs-lookup"><span data-stu-id="26bbd-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="26bbd-106">深入瞭解 [內容瞭解](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="26bbd-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="26bbd-107">**內容處理：** 自動化內容的捕獲、攝取和分類，並使用 Power Automate 簡化以內容為中心的流程。</span><span class="sxs-lookup"><span data-stu-id="26bbd-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="26bbd-108">深入瞭解 [內容處理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="26bbd-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="26bbd-109">**內容規範：** 控制和管理內容，以改進安全性和管理與 Microsoft 資訊保護的整合。</span><span class="sxs-lookup"><span data-stu-id="26bbd-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="26bbd-110">透過全新的 AI 服務和功能，您可以使用 SharePoint Syntex，將內容瞭解和分類應用程式直接組建至內容管理流程。</span><span class="sxs-lookup"><span data-stu-id="26bbd-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="26bbd-111">有兩種不同的方式可以瞭解您的內容。</span><span class="sxs-lookup"><span data-stu-id="26bbd-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="26bbd-112">您使用的模型類型是以檔案格式和使用案例為基礎：</span><span class="sxs-lookup"><span data-stu-id="26bbd-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="26bbd-113">表單處理</span><span class="sxs-lookup"><span data-stu-id="26bbd-113">Form processing</span></span> | <span data-ttu-id="26bbd-114">文件瞭解</span><span class="sxs-lookup"><span data-stu-id="26bbd-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="26bbd-115">從文件庫建立。</span><span class="sxs-lookup"><span data-stu-id="26bbd-115">Created from document library.</span></span> | <span data-ttu-id="26bbd-116">在內容中心建立，SharePoint Syntex 的一部分。</span><span class="sxs-lookup"><span data-stu-id="26bbd-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="26bbd-117">在 [AI 產生器] 中建立的模型。</span><span class="sxs-lookup"><span data-stu-id="26bbd-117">Model created in AI builder.</span></span> | <span data-ttu-id="26bbd-118">在原生介面中建立的模型。</span><span class="sxs-lookup"><span data-stu-id="26bbd-118">Model created in native interface.</span></span> |
| <span data-ttu-id="26bbd-119">用於半結構化檔案格式。</span><span class="sxs-lookup"><span data-stu-id="26bbd-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="26bbd-120">用於非結構化檔案格式。</span><span class="sxs-lookup"><span data-stu-id="26bbd-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="26bbd-121">可設定的分類器。</span><span class="sxs-lookup"><span data-stu-id="26bbd-121">Settable classifier.</span></span> | <span data-ttu-id="26bbd-122">Trainable 具有選用擷取器的分類器。</span><span class="sxs-lookup"><span data-stu-id="26bbd-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="26bbd-123">限制于單一文件庫。</span><span class="sxs-lookup"><span data-stu-id="26bbd-123">Restricted to a single library.</span></span> | <span data-ttu-id="26bbd-124">可以適用於多個文件庫。</span><span class="sxs-lookup"><span data-stu-id="26bbd-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="26bbd-125">在 PDF，JPG，PNG 格式，總 50 MB/500 pp 進行訓練。</span><span class="sxs-lookup"><span data-stu-id="26bbd-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="26bbd-126">訓練 5 到 10 個 PDF、Office 或電子郵件檔案，包括負面範例。</span><span class="sxs-lookup"><span data-stu-id="26bbd-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="26bbd-127">如需更完整的功能比較，請參閱 [檔瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="26bbd-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="26bbd-128">識別試驗性商務案例以進行優化</span><span class="sxs-lookup"><span data-stu-id="26bbd-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="26bbd-129">若要準備在組織中使用 SharePoint Syntex，您必須先瞭解其有用的案例。</span><span class="sxs-lookup"><span data-stu-id="26bbd-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="26bbd-130">「原因」會協助決定所需的模型，以及如何根據模型套用的位置來組織組織。</span><span class="sxs-lookup"><span data-stu-id="26bbd-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="26bbd-131">以下是一些檔理解可協助貴組織的案例：</span><span class="sxs-lookup"><span data-stu-id="26bbd-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="26bbd-132">**內容處理：** 處理合約、工作說明及其他類似表單的檔。</span><span class="sxs-lookup"><span data-stu-id="26bbd-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="26bbd-133">使用表單，訓練模型以瞭解和對應欄位，然後執行表單以自動收集資料。</span><span class="sxs-lookup"><span data-stu-id="26bbd-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="26bbd-134">如需詳細資訊，請參閱 [表單處理一覽](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="26bbd-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="26bbd-135">**發票分析：** 從發票拔出相關的詳細資料，確定他們遵循原則或進行適當處理。</span><span class="sxs-lookup"><span data-stu-id="26bbd-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="26bbd-136">請思考 SharePoint Syntex 可如何協助您的組織的方式：</span><span class="sxs-lookup"><span data-stu-id="26bbd-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="26bbd-137">自動化商務程式</span><span class="sxs-lookup"><span data-stu-id="26bbd-137">Automate business processes</span></span>
- <span data-ttu-id="26bbd-138">提高搜尋精確度</span><span class="sxs-lookup"><span data-stu-id="26bbd-138">Improve search accuracy</span></span>
- <span data-ttu-id="26bbd-139">管理規範風險</span><span class="sxs-lookup"><span data-stu-id="26bbd-139">Manage compliance risk</span></span>

<span data-ttu-id="26bbd-140">當您考慮要考慮的商務案例時，請詢問您下列問題：</span><span class="sxs-lookup"><span data-stu-id="26bbd-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="26bbd-141">是否會解決實際的問題？</span><span class="sxs-lookup"><span data-stu-id="26bbd-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="26bbd-142">是否會廣泛使用或會影響整體效果？</span><span class="sxs-lookup"><span data-stu-id="26bbd-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="26bbd-143">是否可獲得？</span><span class="sxs-lookup"><span data-stu-id="26bbd-143">Is it obtainable?</span></span>
- <span data-ttu-id="26bbd-144">您可以衡量是否成功？</span><span class="sxs-lookup"><span data-stu-id="26bbd-144">Can you measure success?</span></span>

<span data-ttu-id="26bbd-145">根據影響和簡化的執行排定案例的優先順序。</span><span class="sxs-lookup"><span data-stu-id="26bbd-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="26bbd-146">讓您的初始焦點區域可輕鬆實施，也是較高的影響案例。</span><span class="sxs-lookup"><span data-stu-id="26bbd-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="26bbd-147">取消的優先順序較低的影響案例很難實施。</span><span class="sxs-lookup"><span data-stu-id="26bbd-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="26bbd-148">使用[範例案例和使用案例](adoption-scenarios.md)，提示您如何在組織中使用 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="26bbd-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="26bbd-149">識別角色 & 責任</span><span class="sxs-lookup"><span data-stu-id="26bbd-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="26bbd-150">決定貴組織中誰將建立及管理模型？</span><span class="sxs-lookup"><span data-stu-id="26bbd-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="26bbd-151">可能包含下列角色：</span><span class="sxs-lookup"><span data-stu-id="26bbd-151">The following roles might be involved:</span></span>

| <span data-ttu-id="26bbd-152">SharePoint/Knowledge 系統管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="26bbd-153">Power 平台系統管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-153">Power Platform admin</span></span> | <span data-ttu-id="26bbd-154">知識管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-154">Knowledge manager</span></span> | <span data-ttu-id="26bbd-155">模型擁有者</span><span class="sxs-lookup"><span data-stu-id="26bbd-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="26bbd-156">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="26bbd-156">AAD role</span></span>| <span data-ttu-id="26bbd-157">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="26bbd-157">AAD role</span></span> | <span data-ttu-id="26bbd-158">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="26bbd-158">AAD role</span></span> | <span data-ttu-id="26bbd-159">風雲人物</span><span class="sxs-lookup"><span data-stu-id="26bbd-159">Champions</span></span> |
| <span data-ttu-id="26bbd-160">設定表單處理</span><span class="sxs-lookup"><span data-stu-id="26bbd-160">Configure form processing</span></span> | <span data-ttu-id="26bbd-161">設定一般資料服務環境進行表單處理</span><span class="sxs-lookup"><span data-stu-id="26bbd-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="26bbd-162">收集使用案例</span><span class="sxs-lookup"><span data-stu-id="26bbd-162">Gather use cases</span></span> | <span data-ttu-id="26bbd-163">收集商務使用案例</span><span class="sxs-lookup"><span data-stu-id="26bbd-163">Gather business use cases</span></span> |
| <span data-ttu-id="26bbd-164">管理內容中心和許可權</span><span class="sxs-lookup"><span data-stu-id="26bbd-164">Manage content centers and permissions</span></span>| <span data-ttu-id="26bbd-165">購買及分派 AIB 學分</span><span class="sxs-lookup"><span data-stu-id="26bbd-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="26bbd-166">建立最佳作法並回顧模型分析</span><span class="sxs-lookup"><span data-stu-id="26bbd-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="26bbd-167">建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="26bbd-167">Create and apply models</span></span> |

<span data-ttu-id="26bbd-168">知識管理員、商務程式擁有人和內容模型擁有者建立組織的範例模型和冠軍採用。</span><span class="sxs-lookup"><span data-stu-id="26bbd-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="26bbd-169">其他可能參與的人員：合規性管理員、分類法管理員。</span><span class="sxs-lookup"><span data-stu-id="26bbd-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="26bbd-170">他們會在何處建立及套用模型？</span><span class="sxs-lookup"><span data-stu-id="26bbd-170">Where will they build and apply the models?</span></span> <span data-ttu-id="26bbd-171">是否有現有的進程或存放庫可以增強？</span><span class="sxs-lookup"><span data-stu-id="26bbd-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="26bbd-172">表單處理：決定將取得表單處理動作的網站。</span><span class="sxs-lookup"><span data-stu-id="26bbd-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="26bbd-173">檔瞭解：您可以為不同的業務區域建立多個內容中心。</span><span class="sxs-lookup"><span data-stu-id="26bbd-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="26bbd-174">戰略定位</span><span class="sxs-lookup"><span data-stu-id="26bbd-174">Strategic positioning</span></span>

<span data-ttu-id="26bbd-175">與相關者合作，確定他們已對齊使用 SharePoint Syntex 的策略。</span><span class="sxs-lookup"><span data-stu-id="26bbd-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="26bbd-176">調查並提供下列資源，以協助此位置：</span><span class="sxs-lookup"><span data-stu-id="26bbd-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="26bbd-177">商務成果：</span><span class="sxs-lookup"><span data-stu-id="26bbd-177">Business outcomes:</span></span>
  - <span data-ttu-id="26bbd-178">潛在的會計結果</span><span class="sxs-lookup"><span data-stu-id="26bbd-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="26bbd-179">潛在的靈活性結果</span><span class="sxs-lookup"><span data-stu-id="26bbd-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="26bbd-180">商務成果範本</span><span class="sxs-lookup"><span data-stu-id="26bbd-180">Business outcome template</span></span>
- <span data-ttu-id="26bbd-181">專案關係人/Exec 承辦人購買/對齊</span><span class="sxs-lookup"><span data-stu-id="26bbd-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="26bbd-182">業務案例卡座</span><span class="sxs-lookup"><span data-stu-id="26bbd-182">Business case decks</span></span>
  - <span data-ttu-id="26bbd-183">財務模型</span><span class="sxs-lookup"><span data-stu-id="26bbd-183">Financial models</span></span>
  - <span data-ttu-id="26bbd-184">公司就緒性-文化</span><span class="sxs-lookup"><span data-stu-id="26bbd-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="26bbd-185">識別專案關係人</span><span class="sxs-lookup"><span data-stu-id="26bbd-185">Identify stakeholders</span></span>

<span data-ttu-id="26bbd-186">識別您專案的專案關係人。</span><span class="sxs-lookup"><span data-stu-id="26bbd-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="26bbd-187">角色</span><span class="sxs-lookup"><span data-stu-id="26bbd-187">Role</span></span> |<span data-ttu-id="26bbd-188">責任</span><span class="sxs-lookup"><span data-stu-id="26bbd-188">Responsibilities</span></span> |<span data-ttu-id="26bbd-189">部門</span><span class="sxs-lookup"><span data-stu-id="26bbd-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="26bbd-190">執行贊助者 (s) </span><span class="sxs-lookup"><span data-stu-id="26bbd-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="26bbd-191">向公司傳達高階願景和價值</span><span class="sxs-lookup"><span data-stu-id="26bbd-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="26bbd-192">執行領導</span><span class="sxs-lookup"><span data-stu-id="26bbd-192">Executive leadership</span></span>   |
| <span data-ttu-id="26bbd-193">Project 潛在客戶 (s) </span><span class="sxs-lookup"><span data-stu-id="26bbd-193">Project lead(s)</span></span> | <span data-ttu-id="26bbd-194">監督整個啟動的執行和推出程序</span><span class="sxs-lookup"><span data-stu-id="26bbd-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="26bbd-195">專案管理</span><span class="sxs-lookup"><span data-stu-id="26bbd-195">Project management</span></span> |
| <span data-ttu-id="26bbd-196">知識系統管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-196">Knowledge administrators</span></span>| <span data-ttu-id="26bbd-197">建立及管理內容中心</span><span class="sxs-lookup"><span data-stu-id="26bbd-197">Create and manage the content centers</span></span> | <span data-ttu-id="26bbd-198">IT 或其他部門</span><span class="sxs-lookup"><span data-stu-id="26bbd-198">IT or other department</span></span>|
| <span data-ttu-id="26bbd-199">內容管理員和模型擁有人</span><span class="sxs-lookup"><span data-stu-id="26bbd-199">Content managers and model owners</span></span>| <span data-ttu-id="26bbd-200">收集使用案例及建立及套用模型</span><span class="sxs-lookup"><span data-stu-id="26bbd-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="26bbd-201">任何部門</span><span class="sxs-lookup"><span data-stu-id="26bbd-201">Any department</span></span>|
| <span data-ttu-id="26bbd-202">風雲人物</span><span class="sxs-lookup"><span data-stu-id="26bbd-202">Champions</span></span> | <span data-ttu-id="26bbd-203">協助宣傳及管理異議處理</span><span class="sxs-lookup"><span data-stu-id="26bbd-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="26bbd-204">任何部門 (員工)</span><span class="sxs-lookup"><span data-stu-id="26bbd-204">Any department (staff)</span></span> |
| <span data-ttu-id="26bbd-205">租用戶系統管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-205">Tenant administrator</span></span> | <span data-ttu-id="26bbd-206">設定租用戶層級設定</span><span class="sxs-lookup"><span data-stu-id="26bbd-206">Configure tenant-level settings</span></span> | <span data-ttu-id="26bbd-207">IT 部門</span><span class="sxs-lookup"><span data-stu-id="26bbd-207">IT department</span></span>|
| <span data-ttu-id="26bbd-208">Power Platform 系統管理員</span><span class="sxs-lookup"><span data-stu-id="26bbd-208">Power Platform administrator</span></span>| <span data-ttu-id="26bbd-209">設定一般資料服務環境</span><span class="sxs-lookup"><span data-stu-id="26bbd-209">Configure common data services environment</span></span> | <span data-ttu-id="26bbd-210">IT 部門</span><span class="sxs-lookup"><span data-stu-id="26bbd-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="26bbd-211">雖然我們建議您在整個部署中完成上述每個角色，但您可能會發現您不需要所有這些角色即可開始使用已識別的解決方案。</span><span class="sxs-lookup"><span data-stu-id="26bbd-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="26bbd-212">準備工作表</span><span class="sxs-lookup"><span data-stu-id="26bbd-212">Readiness checklist</span></span>

<span data-ttu-id="26bbd-213">若要準備好執行 SharePoint Syntex，您必須執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="26bbd-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![內容瞭解的準備工作](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="26bbd-215">規劃結束狀態</span><span class="sxs-lookup"><span data-stu-id="26bbd-215">Plan the end state</span></span>
    - <span data-ttu-id="26bbd-216">檔理解模型是指這種方式，而不是結束。</span><span class="sxs-lookup"><span data-stu-id="26bbd-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="26bbd-217">規劃如何利用下列各項所提取之中繼資料的價值：</span><span class="sxs-lookup"><span data-stu-id="26bbd-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="26bbd-218">搜尋</span><span class="sxs-lookup"><span data-stu-id="26bbd-218">Search</span></span>
      - <span data-ttu-id="26bbd-219">篩選和查看格式設定</span><span class="sxs-lookup"><span data-stu-id="26bbd-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="26bbd-220">合規性</span><span class="sxs-lookup"><span data-stu-id="26bbd-220">Compliance</span></span>
      - <span data-ttu-id="26bbd-221">自動化</span><span class="sxs-lookup"><span data-stu-id="26bbd-221">Automation</span></span>
2. <span data-ttu-id="26bbd-222">識別</span><span class="sxs-lookup"><span data-stu-id="26bbd-222">Identify</span></span>
    - <span data-ttu-id="26bbd-223">瞭解現有的資訊架構和內容管理功能使用。</span><span class="sxs-lookup"><span data-stu-id="26bbd-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="26bbd-224">是否有任何現有的內容類型適合模型？</span><span class="sxs-lookup"><span data-stu-id="26bbd-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="26bbd-225">中繼資料會改善哪些現有的處理常式？</span><span class="sxs-lookup"><span data-stu-id="26bbd-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="26bbd-226">設計</span><span class="sxs-lookup"><span data-stu-id="26bbd-226">Design</span></span>
    - <span data-ttu-id="26bbd-227">設計您的資訊架構、受管理的中繼資料和內容類型的方法</span><span class="sxs-lookup"><span data-stu-id="26bbd-227">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="26bbd-228">設計定義、建立、管理的程式。</span><span class="sxs-lookup"><span data-stu-id="26bbd-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="26bbd-229">與您的組織合作</span><span class="sxs-lookup"><span data-stu-id="26bbd-229">Engage your organization</span></span>

1. <span data-ttu-id="26bbd-230">找出有序的持有者、確認案例，以及制定專案計劃。</span><span class="sxs-lookup"><span data-stu-id="26bbd-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="26bbd-231">設定並套用授權。</span><span class="sxs-lookup"><span data-stu-id="26bbd-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="26bbd-232">開始認知與訓練–招聘冠軍。</span><span class="sxs-lookup"><span data-stu-id="26bbd-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="26bbd-233">分階段進行。</span><span class="sxs-lookup"><span data-stu-id="26bbd-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="26bbd-234">收集意見反應並進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="26bbd-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="26bbd-235">根據需要，隨著流量成長對任何 AI 產生器的使用。</span><span class="sxs-lookup"><span data-stu-id="26bbd-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="26bbd-236">另請參閱</span><span class="sxs-lookup"><span data-stu-id="26bbd-236">See also</span></span>

[<span data-ttu-id="26bbd-237">SharePoint Syntex 的案例和使用案例</span><span class="sxs-lookup"><span data-stu-id="26bbd-237">Scenarios and use cases for SharePoint Syntex</span></span>](adoption-scenarios.md)