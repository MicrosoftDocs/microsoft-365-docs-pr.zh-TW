---
title: 使用端點資料外洩防護 (預覽版)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 瞭解如何設定資料遺失防護（DLP）原則以使用 Microsoft 365 端點資料遺失防護（EPDLP）位置。
ms.openlocfilehash: c65b1f7ed97fc0400d88eecadfa2081a940bac41
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199959"
---
# <a name="using-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="bd600-103">使用端點資料外洩防護 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="bd600-103">Using Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="bd600-104">本文將逐步引導您建立及修改使用裝置作為位置的 DLP 原則的三種案例。</span><span class="sxs-lookup"><span data-stu-id="bd600-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="bd600-105">DLP 設定</span><span class="sxs-lookup"><span data-stu-id="bd600-105">DLP settings</span></span>

<span data-ttu-id="bd600-106">在您開始使用之前，您必須設定套用到所有裝置的 DLP 原則的 DLP 設定。</span><span class="sxs-lookup"><span data-stu-id="bd600-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="bd600-107">如果您想要建立可強制執行以下內容的原則，則您必須進行設定：</span><span class="sxs-lookup"><span data-stu-id="bd600-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="bd600-108">雲端輸出限制</span><span class="sxs-lookup"><span data-stu-id="bd600-108">cloud egress restrictions</span></span>
- <span data-ttu-id="bd600-109">不受允許的應用程式限制</span><span class="sxs-lookup"><span data-stu-id="bd600-109">unallowed apps restrictions</span></span>

<span data-ttu-id="bd600-110">或者</span><span class="sxs-lookup"><span data-stu-id="bd600-110">Or</span></span>

- <span data-ttu-id="bd600-111">如果您想從監控中排除雜訊檔案路徑</span><span class="sxs-lookup"><span data-stu-id="bd600-111">If you what to exclude noisy file paths from monitoring</span></span>

![DLP 設定](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a><span data-ttu-id="bd600-113">檔案路徑排除</span><span class="sxs-lookup"><span data-stu-id="bd600-113">File path exclusions</span></span>

<span data-ttu-id="bd600-114">您可能想在裝置上從 DLP 監控、DLP 警示 和 DLP 策略執行中排除某些太吵雜或不包含您感興趣的檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="bd600-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="bd600-115">這些位置中的檔案不會被稽核，且在那些位置中所建立或修改的任何檔案，都不會受到 DLP 原則強制的制約。</span><span class="sxs-lookup"><span data-stu-id="bd600-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="bd600-116">您可以在 DLP 設定中設定路徑排除。</span><span class="sxs-lookup"><span data-stu-id="bd600-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="bd600-117">您可以使用此邏輯來建立排除路徑：</span><span class="sxs-lookup"><span data-stu-id="bd600-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="bd600-118">以 ' \’ 結尾的有效檔案路徑，也就是直接位於 [資料夾] 底下的檔案。</span><span class="sxs-lookup"><span data-stu-id="bd600-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <span data-ttu-id="bd600-119">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="bd600-119">For example: C:\Temp</span></span>\
- <span data-ttu-id="bd600-120">以 ‘\*’ 結尾的有效檔案路徑，也就是除了直接位於 [資料夾] 底下的檔案外，只在 [子資料夾] 底下的檔案。</span><span class="sxs-lookup"><span data-stu-id="bd600-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <span data-ttu-id="bd600-121">例如：C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="bd600-121">For example: C:\Temp\*</span></span>
- <span data-ttu-id="bd600-122">以 ' \’ 或 ‘\*’ 結尾的有效檔案路徑，也就是直接位於 [資料夾] 和 [子資料夾] 底下的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="bd600-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <span data-ttu-id="bd600-123">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="bd600-123">For example: C:\Temp</span></span>
- <span data-ttu-id="bd600-124">兩側間帶有 ’\’ 的萬用字元之路徑。</span><span class="sxs-lookup"><span data-stu-id="bd600-124">A path with wildcard between ‘\’ from each side.</span></span> <span data-ttu-id="bd600-125">例如，C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="bd600-125">For example: C:\Users\*\Desktop</span></span>\
- <span data-ttu-id="bd600-126">兩側間帶有 ‘\’ 的萬用字元且以 ‘(數字)’ 提供精確數目的子資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="bd600-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <span data-ttu-id="bd600-127">例如： C:\Users\*（1） \Downloads</span><span class="sxs-lookup"><span data-stu-id="bd600-127">For example: C:\Users\*(1)\Downloads</span></span>\
- <span data-ttu-id="bd600-128">含有 [系統] 內容變數的路徑。</span><span class="sxs-lookup"><span data-stu-id="bd600-128">A path with SYSTEM environment variables.</span></span> <span data-ttu-id="bd600-129">例如：%SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="bd600-129">For example: %SystemDrive%\Test\*</span></span>
- <span data-ttu-id="bd600-130">以上所列的混合。</span><span class="sxs-lookup"><span data-stu-id="bd600-130">A mix of all the above.</span></span> <span data-ttu-id="bd600-131">例如：%SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="bd600-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="bd600-132">服務網域</span><span class="sxs-lookup"><span data-stu-id="bd600-132">Service domains</span></span>

<span data-ttu-id="bd600-133">您可以在此清單中新增在強制執行端點 DLP 原則雲端上傳存取限制時，Edge Chromium 會涉及的網域。</span><span class="sxs-lookup"><span data-stu-id="bd600-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="bd600-134">如果 [清單模式] 設為 **[封鎖]**，則使用者將無法將敏感性專案上傳到這些網域。</span><span class="sxs-lookup"><span data-stu-id="bd600-134">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="bd600-135">當由於專案符合 DLP 原則而封鎖上傳動作時，DLP 將會產生警告，或封鎖敏感性專案的上傳。</span><span class="sxs-lookup"><span data-stu-id="bd600-135">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="bd600-136">如果 [清單模式] 設為 **[允許]**，則使用者可以將敏感性專案 ***[僅]*** 上傳到那些網域，而不可將存取權上傳到其他網域。</span><span class="sxs-lookup"><span data-stu-id="bd600-136">If the list mode is set to **Allow**, then users will be able to upload sensitive items ***only*** to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="bd600-137">不受允許的應用程式</span><span class="sxs-lookup"><span data-stu-id="bd600-137">Unallowed apps</span></span>

<span data-ttu-id="bd600-138">當一項原則的 **不受允許的應用程式和瀏覽器之存取** 設定已開啟，且使用者嘗試使用這些應用程式存取受保護的檔案時，系統可以允許、封鎖或在封鎖活動下，但使用者仍可以覆寫限制。</span><span class="sxs-lookup"><span data-stu-id="bd600-138">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="bd600-139">所有活動都會經過稽核，並可在活動瀏覽器中查看。</span><span class="sxs-lookup"><span data-stu-id="bd600-139">All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="bd600-140">不受允許的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="bd600-140">Unallowed browsers</span></span>

<span data-ttu-id="bd600-141">您新增的瀏覽器是由其程式名稱所標識，這些瀏覽器將無法存取符合強制執行的 DLP 原則的檔案（其中的 [上傳到雲端服務限制] 已設定為 [封鎖] 或 [封鎖覆寫]）。</span><span class="sxs-lookup"><span data-stu-id="bd600-141">You add browsers, identified by their process names, that will be blocked from accessing files that match the conditions of an enforced  a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="bd600-142">當這些瀏覽器被禁止存取檔案時，終端使用者會看到快顯通知，要求其透過 Edge Chromium 開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="bd600-142">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="bd600-143">將 DLP 設定結合起來</span><span class="sxs-lookup"><span data-stu-id="bd600-143">Tying DLP settings together</span></span>

<span data-ttu-id="bd600-144">使用端點 DLP 和 Edge Chromium 網頁瀏覽器，您可以對不受允許的雲端應用程式和服務限制不願共用敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="bd600-144">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="bd600-145">Edge Chromium 瞭解，專案受端點 DLP 原則限制，並強制執行存取限制的狀況。</span><span class="sxs-lookup"><span data-stu-id="bd600-145">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="bd600-146">當您在正確設定的 DLP 原則和 [Edge] Chromium 瀏覽器中使用端點 DLP 做為位置時，您在這些設定中定義的不受允許的瀏覽器將無法存取符合您 DLP 原則控制項的敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="bd600-146">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="bd600-147">相反地， 使用者會被重新導向，以使用 Edge Chromium 而 Edge Chromium 則根據其對 DLP 的強加限制之理解，可在 DLP 原則中的條件符合時封鎖或限制活動。</span><span class="sxs-lookup"><span data-stu-id="bd600-147">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="bd600-148">若要使用這項限制，您需要設定三個重要的部分：</span><span class="sxs-lookup"><span data-stu-id="bd600-148">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="bd600-149">指定您想要防止敏感性專案被共用的位置（服務、網域、IP 位址）</span><span class="sxs-lookup"><span data-stu-id="bd600-149">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to</span></span>
2. <span data-ttu-id="bd600-150">當 DLP 原則相符時，新增不允許存取特定敏感性專案的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="bd600-150">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs</span></span>
3. <span data-ttu-id="bd600-151">設定 DLP 原則，透過開啟 **上傳至雲端服務** 和 **從不受允許的瀏覽器存取**，以定義敏感性專案上傳所應受限制的位置。</span><span class="sxs-lookup"><span data-stu-id="bd600-151">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="bd600-152">您可以繼續新增服務、應用程式和原則，以延伸並擴充您的限制，以符合您的業務需求並保護敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="bd600-152">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="bd600-153">這項設定可協助確保您的資料保持安全，同時也避免了防止或限制使用者存取及共用非敏感性專案的不必要限制。</span><span class="sxs-lookup"><span data-stu-id="bd600-153">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="bd600-154">端點 DLP 原則案例</span><span class="sxs-lookup"><span data-stu-id="bd600-154">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="bd600-155">為協助您熟悉端點 DLP 功能及其在 DLP 原則中的呈現方式，我們為您整理了一些可遵循的案例。</span><span class="sxs-lookup"><span data-stu-id="bd600-155">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="bd600-156">當端點 DLP 公開發行時，所有的端點 DLP 內容都會被折入主要 DLP 內容設定中。</span><span class="sxs-lookup"><span data-stu-id="bd600-156">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd600-157">這些端點 DLP 案例非建立和調整 DLP 原則的正式程式。</span><span class="sxs-lookup"><span data-stu-id="bd600-157">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="bd600-158">當您需要在一般情況下使用 DLP 原則時，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="bd600-158">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="bd600-159">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="bd600-159">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="bd600-160">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="bd600-160">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="bd600-161">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bd600-161">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="bd600-162">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bd600-162">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="bd600-163">案例1：從範本建立原則，僅限稽核</span><span class="sxs-lookup"><span data-stu-id="bd600-163">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="bd600-164">這些案例要求你已有上線裝置，並會向 [活動瀏覽器] 進行回報。</span><span class="sxs-lookup"><span data-stu-id="bd600-164">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="bd600-165">如果您還沒有上線裝置，請參閱 [開始使用端點資料外洩防護（預覽版）](endpoint-dlp-getting-started.md)。</span><span class="sxs-lookup"><span data-stu-id="bd600-165">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention (preview)](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="bd600-166">開啟 [[資料外洩防護] 頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="bd600-166">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="bd600-167">選擇 **[建立原則（預覽版）]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-167">Choose **Create policy (preview)**.</span></span>
3. <span data-ttu-id="bd600-168">在此案例中，請選擇 **[隱私權]**，然後 **[美國個人識別資訊（PII）資料]**，然後選擇 **[下一個]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-168">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>
4. <span data-ttu-id="bd600-169">將 **[裝置]** 以外的所有位置的 **[狀態]** 欄位切換為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="bd600-169">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="bd600-170">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-170">Choose **Next**.</span></span>
5. <span data-ttu-id="bd600-171">接受預設 **[查看並自訂範本中的設定]** 選項，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-171">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>
6. <span data-ttu-id="bd600-172">接受預設 **[偵測該內容被共用時]**，然後 **[與我的組織外部人員]** 選項 ，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-172">Accept the default **Detect when this content is shared** and **With people outside my organization** selections and choose **Next**.</span></span>
7. <span data-ttu-id="bd600-173">接受預設 **[保護動作]** 值，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-173">Accept the default **Protection actions** values and choose **Next**.</span></span>
8. <span data-ttu-id="bd600-174">選取 **[稽核或限制 Windows 裝置上的活動]**，並將動作設定為 **[僅限稽核]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-174">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="bd600-175">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-175">Choose **Next**.</span></span>
9. <span data-ttu-id="bd600-176">接受預設 **[我想先進行測試]** 值，然後選擇 **[在測試模式中顯示原則提示]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-176">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="bd600-177">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-177">Choose **Next**.</span></span>
10. <span data-ttu-id="bd600-178">查看您的設定，然後選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-178">Review your settings and choose **Submit**.</span></span>
11. <span data-ttu-id="bd600-179">新的 DLP 原則會顯示在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="bd600-179">The new DLP policy will appear in the policy list.</span></span>
12. <span data-ttu-id="bd600-180">在活動瀏覽器中檢查受監控端點的資料。</span><span class="sxs-lookup"><span data-stu-id="bd600-180">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="bd600-181">設定裝置的位置篩選並新增原則，然後依策略名稱篩選，以查看此原則的影響。</span><span class="sxs-lookup"><span data-stu-id="bd600-181">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="bd600-182">如有需要，請參閱 [啟動活動資源管理器](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="bd600-182">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>
13. <span data-ttu-id="bd600-183">嘗試與組織外部人員共用包含會觸發美國個人識別資訊（PII）資料條件之測試。</span><span class="sxs-lookup"><span data-stu-id="bd600-183">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="bd600-184">這應該會觸發該原則。</span><span class="sxs-lookup"><span data-stu-id="bd600-184">This should trigger the policy.</span></span>
14. <span data-ttu-id="bd600-185">查看活動的活動瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bd600-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="bd600-186">案例2：修改現有原則、設定通知</span><span class="sxs-lookup"><span data-stu-id="bd600-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="bd600-187">開啟 [[資料外洩防護] 頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="bd600-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="bd600-188">選擇您在案例1中建立的 **美國個人識別資訊（PII）資料** 原則 。</span><span class="sxs-lookup"><span data-stu-id="bd600-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>
3. <span data-ttu-id="bd600-189">選擇 **編輯原則（預覽）**。</span><span class="sxs-lookup"><span data-stu-id="bd600-189">Choose **edit policy (preview)**.</span></span>
4. <span data-ttu-id="bd600-190">移至 **[進階 DLP 規則]** 頁面，然後編輯 **偵測到少量的美國個人識別資訊**</span><span class="sxs-lookup"><span data-stu-id="bd600-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**</span></span>
5. <span data-ttu-id="bd600-191">向下移至 **[事件報告]** 區段，並設定 **[當規則符合時，傳送警示給系統管理員]** 為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-191">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="bd600-192">電子郵件警示將會自動傳送給系統管理員，以及您新增至收件者清單中的任何人。</span><span class="sxs-lookup"><span data-stu-id="bd600-192">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 
<span data-ttu-id="bd600-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="bd600-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
6. <span data-ttu-id="bd600-194">在此情況下，請選擇**每次當活動符合規則時，傳送警示**。</span><span class="sxs-lookup"><span data-stu-id="bd600-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>
7. <span data-ttu-id="bd600-195">選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-195">Choose **Save**.</span></span>
8. <span data-ttu-id="bd600-196">透過選擇 **[下一步]**，然後 **[提交]** 原則變更，以保留您先前的所有設定。</span><span class="sxs-lookup"><span data-stu-id="bd600-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>
9. <span data-ttu-id="bd600-197">嘗試與組織外部人員共用包含會觸發美國個人識別資訊（PII）資料條件之測試。</span><span class="sxs-lookup"><span data-stu-id="bd600-197">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="bd600-198">這應該會觸發該原則。</span><span class="sxs-lookup"><span data-stu-id="bd600-198">This should trigger the policy.</span></span>
10. <span data-ttu-id="bd600-199">查看活動的活動瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bd600-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="bd600-200">案例3：修改現有原則、封鎖 [允許覆寫] 動作</span><span class="sxs-lookup"><span data-stu-id="bd600-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="bd600-201">開啟 [[資料外洩防護] 頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="bd600-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="bd600-202">選擇您在案例1中建立的 **美國個人識別資訊（PII）資料** 原則 。</span><span class="sxs-lookup"><span data-stu-id="bd600-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>
3. <span data-ttu-id="bd600-203">選擇 **編輯原則（預覽）**。</span><span class="sxs-lookup"><span data-stu-id="bd600-203">Choose **edit policy (preview)**.</span></span>
4. <span data-ttu-id="bd600-204">移至 **[進階 DLP 規則]** 頁面，然後編輯 **偵測到少量的美國個人識別資訊**</span><span class="sxs-lookup"><span data-stu-id="bd600-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**</span></span>
5. <span data-ttu-id="bd600-205">向下移至 **[稽核或限制 Windows 裝置上的活動]** 區段，並針對每個活動設定對應的動作為 **[透過覆寫進行封鎖]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>
<span data-ttu-id="bd600-206">![設定[透過複寫進行封鎖]動作](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="bd600-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
6. <span data-ttu-id="bd600-207">選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bd600-207">Choose **Save**.</span></span>
7. <span data-ttu-id="bd600-208">針對 **偵測到大量美國個人識別資訊**時，重複執行步驟4-7。</span><span class="sxs-lookup"><span data-stu-id="bd600-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>
8. <span data-ttu-id="bd600-209">透過選擇 **[下一步]**，然後 **[提交]** 原則變更，以保留您先前的所有設定。</span><span class="sxs-lookup"><span data-stu-id="bd600-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>
9. <span data-ttu-id="bd600-210">嘗試與組織外部人員共用包含會觸發美國個人識別資訊（PII）資料條件之測試。</span><span class="sxs-lookup"><span data-stu-id="bd600-210">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="bd600-211">這應該會觸發該原則。</span><span class="sxs-lookup"><span data-stu-id="bd600-211">This should trigger the policy.</span></span>

<span data-ttu-id="bd600-212">在用戶端裝置上，您會看到像這樣的彈出提示：</span><span class="sxs-lookup"><span data-stu-id="bd600-212">You'll see a popup like this on the client device:</span></span>

![端點 dlp 用戶端封鎖覆寫通知](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. <span data-ttu-id="bd600-214">查看活動的活動瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bd600-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd600-215">請參閱</span><span class="sxs-lookup"><span data-stu-id="bd600-215">See also</span></span>

- [<span data-ttu-id="bd600-216">深入了解端點資料外洩防護 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="bd600-216">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="bd600-217">開始使用端點資料外洩防護（預覽版）</span><span class="sxs-lookup"><span data-stu-id="bd600-217">Get started with Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="bd600-218">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="bd600-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="bd600-219">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bd600-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- <span data-ttu-id="bd600-220">[開始使用活動總管](data-classification-activity-explorer.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="bd600-220">[Get started with Activity explorer](data-classification-activity-explorer.md)</span></span>
- [<span data-ttu-id="bd600-221">Microsoft Defender 進階威脅防護 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="bd600-221">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="bd600-222">[Windows 10 電腦上線的工具及方法 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="bd600-222">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="bd600-223">Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="bd600-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="bd600-224">已加入 Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="bd600-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="bd600-225">[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="bd600-225">[Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)</span></span>
- [<span data-ttu-id="bd600-226">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="bd600-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="bd600-227">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bd600-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)