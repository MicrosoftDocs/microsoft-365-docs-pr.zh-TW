---
title: 執行 Microsoft SharePoint Syntex 的試用版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
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
description: 瞭解如何規劃及執行組織中 SharePoint Syntex 的試用試驗計畫。
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327091"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="889df-103">執行 Microsoft SharePoint Syntex 的試用版</span><span class="sxs-lookup"><span data-stu-id="889df-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="889df-104">本文說明如何設定和執行試驗試驗計畫，以在您的組織中部署 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="889df-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="889df-105">此外，它也會建議試用版的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="889df-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="889df-106">註冊試用版</span><span class="sxs-lookup"><span data-stu-id="889df-106">Sign up for a trial</span></span>

<span data-ttu-id="889df-107">SharePoint Syntex 的試用版可讓300使用者存取30天。</span><span class="sxs-lookup"><span data-stu-id="889df-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="889df-108">在試用版中，最多可包含300個使用者，以確保自動新增 1000000 AI 產生器信用。</span><span class="sxs-lookup"><span data-stu-id="889df-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="889df-109">您不需要包含300使用者的試用版，即可成功試用。</span><span class="sxs-lookup"><span data-stu-id="889df-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="889df-110">您可以從下列其中一個來源取得試用版：</span><span class="sxs-lookup"><span data-stu-id="889df-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="889df-111">[SharePoint Syntex 產品頁面](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="889df-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="889df-112">[Microsoft 365 系統管理中心](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="889df-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="889df-113">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="889df-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="889df-114">移至 **帳單**  >  **購買服務**。</span><span class="sxs-lookup"><span data-stu-id="889df-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="889df-115">向下捲動至 **[附加元件]** 區段。</span><span class="sxs-lookup"><span data-stu-id="889df-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="889df-116">在 [SharePoint Syntex] 麻將牌上，選取 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="889df-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="889df-117">選取 **[取得免費試用版]**。</span><span class="sxs-lookup"><span data-stu-id="889df-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="889df-118">若要確認試用版，請遵循餘下的嚮導步驟。</span><span class="sxs-lookup"><span data-stu-id="889df-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="889df-119">您必須是 Microsoft 365 全域管理員或計費系統管理員，才能啟用試用版。</span><span class="sxs-lookup"><span data-stu-id="889df-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="889df-120">試用版中應包括神秘</span><span class="sxs-lookup"><span data-stu-id="889df-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="889df-121">角色</span><span class="sxs-lookup"><span data-stu-id="889df-121">Role</span></span>  |<span data-ttu-id="889df-122">活動</span><span class="sxs-lookup"><span data-stu-id="889df-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="889df-123">Microsoft 365 全域管理員或計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="889df-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="889df-124">啟動試用和指派授權</span><span class="sxs-lookup"><span data-stu-id="889df-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="889df-125">Microsoft 365 全域系統管理員或 SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="889df-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="889df-126">設定 SharePoint Syntex 及建立內容中心</span><span class="sxs-lookup"><span data-stu-id="889df-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="889df-127">商務使用者</span><span class="sxs-lookup"><span data-stu-id="889df-127">Business users</span></span>     |    <span data-ttu-id="889df-128">模型建立及測試</span><span class="sxs-lookup"><span data-stu-id="889df-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="889df-129">啟動試用之前</span><span class="sxs-lookup"><span data-stu-id="889df-129">Before you activate a trial</span></span>

<span data-ttu-id="889df-130">若要成功規劃 SharePoint Syntex 試用版，請考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="889df-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="889df-131">在「實際世界」案例和資料中完成最有意義的測試。</span><span class="sxs-lookup"><span data-stu-id="889df-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="889df-132">每個租使用者僅能啟用一次 SharePoint Syntex 試用版。</span><span class="sxs-lookup"><span data-stu-id="889df-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="889df-133">測試或演示程式租使用者可以做為「幹即用」，以逐步進行啟用步驟和系統管理控制。</span><span class="sxs-lookup"><span data-stu-id="889df-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="889df-134">但最好是評估實際執行租使用者上的模型建立。</span><span class="sxs-lookup"><span data-stu-id="889df-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="889df-135">若要讓實際執行租使用者的試用的價值最大化，規劃和商務服務是必要的。</span><span class="sxs-lookup"><span data-stu-id="889df-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="889df-136">您應接洽一或多個商務區域，以識別可能由 SharePoint Syntex 解決的三至六使用案例。</span><span class="sxs-lookup"><span data-stu-id="889df-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="889df-137">這些使用案例應該：</span><span class="sxs-lookup"><span data-stu-id="889df-137">These use cases should:</span></span>

- <span data-ttu-id="889df-138">包含可透過表單處理或檔理解模型解決的案例。</span><span class="sxs-lookup"><span data-stu-id="889df-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="889df-139">清楚瞭解任何解壓縮的中繼資料的用途;例如，使用 Power Automate 來查看格式設定或自動化。</span><span class="sxs-lookup"><span data-stu-id="889df-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="889df-140">雖然 SharePoint Syntex 專注于對檔進行分類及提取中繼資料，但要量化的值即為此中繼資料的啟用。</span><span class="sxs-lookup"><span data-stu-id="889df-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="889df-141">是以一組已定義的資料為基礎;例如，特定 SharePoint 網站或文件庫。</span><span class="sxs-lookup"><span data-stu-id="889df-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="889df-142">SharePoint Syntex 常見的誤解是一般用途模型可以套用到所有的組織內容。</span><span class="sxs-lookup"><span data-stu-id="889df-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="889df-143">更準確的觀點是建立模型，以協助解決目標位置中的特定業務問題。</span><span class="sxs-lookup"><span data-stu-id="889df-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="889df-144">所有這些使用案例可能不適合 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="889df-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="889df-145">品質試用的目標不會證明 SharePoint Syntex 會符合所有案例。</span><span class="sxs-lookup"><span data-stu-id="889df-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="889df-146">相反地，這項試用版應該可協助您更進一步瞭解產品的價值。</span><span class="sxs-lookup"><span data-stu-id="889df-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="889df-147">針對每個計畫的使用案例，識別為相關內容或程式中的主題專家的使用者。</span><span class="sxs-lookup"><span data-stu-id="889df-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="889df-148">建立 SharePoint Syntex 模型是專注于內容中的網域專家，而不是 IT 專業人員或開發人員資源。</span><span class="sxs-lookup"><span data-stu-id="889df-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="889df-149">啟動試用版</span><span class="sxs-lookup"><span data-stu-id="889df-149">Activate a trial</span></span>

<span data-ttu-id="889df-150">當您啟動試用版時，您必須：</span><span class="sxs-lookup"><span data-stu-id="889df-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="889df-151">將授權指派給相關的使用者。</span><span class="sxs-lookup"><span data-stu-id="889df-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="889df-152">執行[SharePoint Syntex 的其他設定](set-up-content-understanding.md)。</span><span class="sxs-lookup"><span data-stu-id="889df-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="889df-153">您可能想要 [建立其他內容中心](create-a-content-center.md)。</span><span class="sxs-lookup"><span data-stu-id="889df-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="889df-154">在啟動試用程式之後，您可以建立模型和處理檔。</span><span class="sxs-lookup"><span data-stu-id="889df-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="889df-155">請參閱 [建立模型的指導](create-a-content-center.md)方針。</span><span class="sxs-lookup"><span data-stu-id="889df-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="889df-156">在試用期間</span><span class="sxs-lookup"><span data-stu-id="889df-156">During a trial</span></span>

<span data-ttu-id="889df-157">試用期是有限的，所以最初重點在於 SharePoint Syntex 模型是否可以分類檔，以及提取定義的使用案例的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="889df-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="889df-158">試用期結束後，您就可以評估如何利用中繼資料。</span><span class="sxs-lookup"><span data-stu-id="889df-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="889df-159">試用後</span><span class="sxs-lookup"><span data-stu-id="889df-159">After a trial</span></span>

<span data-ttu-id="889df-160">根據試用的結果，您可以決定是否要繼續使用 SharePoint Syntex 的生產。</span><span class="sxs-lookup"><span data-stu-id="889df-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="889df-161">繼續使用實際執行環境</span><span class="sxs-lookup"><span data-stu-id="889df-161">Proceed to production use</span></span>

<span data-ttu-id="889df-162">為了確保服務的連續性，您必須購買必要數目的授權，並將這些授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="889df-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="889df-163">試用期間結束時未獲得完整授權的試用使用者，將無法充分利用 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="889df-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="889df-164">您可能需要估計您的表單處理的預期使用方式，並規劃預期的 AI 產生器信用量。</span><span class="sxs-lookup"><span data-stu-id="889df-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="889df-165">如需協助，請參閱 [預估適合您的 AI](https://powerapps.microsoft.com/ai-builder-calculator/)產生器容量。</span><span class="sxs-lookup"><span data-stu-id="889df-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="889df-166">請勿繼續實際執行使用</span><span class="sxs-lookup"><span data-stu-id="889df-166">Don't proceed to production use</span></span>

<span data-ttu-id="889df-167">如果您未在試用後購買授權：</span><span class="sxs-lookup"><span data-stu-id="889df-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="889df-168">您將無法建立新的模型。</span><span class="sxs-lookup"><span data-stu-id="889df-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="889df-169">執行模型的文件庫將不再自動分類檔案或提取模型。</span><span class="sxs-lookup"><span data-stu-id="889df-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="889df-170">任何先前分類的檔案或解壓縮的中繼資料都不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="889df-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="889df-171">內容中心和任何檔理解模型不會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="889df-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="889df-172">如果您決定以後購買授權，這些功能仍可供使用。</span><span class="sxs-lookup"><span data-stu-id="889df-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="889df-173">表單處理模型會儲存在預設的 Power 平臺環境 (CD) 實例中的一般資料服務中。</span><span class="sxs-lookup"><span data-stu-id="889df-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="889df-174">您可以將這些功能與未來授權搭配使用，以供 SharePoint Syntex 或使用電源平臺中的 AI 產生器功能使用。</span><span class="sxs-lookup"><span data-stu-id="889df-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="889df-175">請參閱</span><span class="sxs-lookup"><span data-stu-id="889df-175">See also</span></span>

[<span data-ttu-id="889df-176">Microsoft SharePoint Syntex 採用：快速入門</span><span class="sxs-lookup"><span data-stu-id="889df-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
