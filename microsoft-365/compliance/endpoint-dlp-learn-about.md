---
title: 深入了解 Microsoft 365 端點資料外洩防護
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 端點資料外洩防護可擴充檔案活動的監視以及這些檔案到端點的保護動作。 在 Microsoft 365 合規性中心解決方案中可看到檔案 '
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279307"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="be27d-104">深入了解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="be27d-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="be27d-105">您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。</span><span class="sxs-lookup"><span data-stu-id="be27d-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="be27d-106">如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="be27d-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="be27d-107">**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="be27d-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="be27d-108">將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="be27d-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="be27d-109">您可以監視和採取動作的端點活動</span><span class="sxs-lookup"><span data-stu-id="be27d-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="be27d-110">Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。</span><span class="sxs-lookup"><span data-stu-id="be27d-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="be27d-111">活動</span><span class="sxs-lookup"><span data-stu-id="be27d-111">activity</span></span> |<span data-ttu-id="be27d-112">描述</span><span class="sxs-lookup"><span data-stu-id="be27d-112">description</span></span>  | <span data-ttu-id="be27d-113">可稽核的/可限制的</span><span class="sxs-lookup"><span data-stu-id="be27d-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="be27d-114">上傳到雲端服務，或透過不允許的瀏覽器存取</span><span class="sxs-lookup"><span data-stu-id="be27d-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="be27d-115">使用者嘗試將項目上載到受限服務域或透過瀏覽器存取項目時偵測。</span><span class="sxs-lookup"><span data-stu-id="be27d-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="be27d-116">如果他們使用的瀏覽器在 DLP 中列為不允許使用的瀏覽器，則上載活動將被封鎖，使用者將被重新導向到使用Edge Chromium。</span><span class="sxs-lookup"><span data-stu-id="be27d-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="be27d-117">然後，Edge Chromium 將基於 DLP 原則設定允許或封鎖上載或存取</span><span class="sxs-lookup"><span data-stu-id="be27d-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="be27d-118">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="be27d-118">auditable and restrictable</span></span>|
|<span data-ttu-id="be27d-119">複製到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="be27d-119">copy to other app</span></span>    |<span data-ttu-id="be27d-120">使用者嘗試從受保護項目複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。</span><span class="sxs-lookup"><span data-stu-id="be27d-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="be27d-121">此活動不會偵測到在同一應用程式、流程或項目中複製和貼上資訊。</span><span class="sxs-lookup"><span data-stu-id="be27d-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="be27d-122">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="be27d-122">auditable and restrictable</span></span>|
|<span data-ttu-id="be27d-123">複製到 USB 卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="be27d-123">copy to USB removable media</span></span> |<span data-ttu-id="be27d-124">使用者嘗試將項目或資訊複製到卸除式媒體或 USB 裝置時偵測。</span><span class="sxs-lookup"><span data-stu-id="be27d-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="be27d-125">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="be27d-125">auditable and restrictable</span></span>|
|<span data-ttu-id="be27d-126">複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="be27d-126">copy to a network share</span></span>    |<span data-ttu-id="be27d-127">使用者嘗試將項目複製到網路共用或對應的網路磁碟機時偵測</span><span class="sxs-lookup"><span data-stu-id="be27d-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="be27d-128">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="be27d-128">auditable and restrictable</span></span>|
|<span data-ttu-id="be27d-129">列印文件</span><span class="sxs-lookup"><span data-stu-id="be27d-129">print a document</span></span>    |<span data-ttu-id="be27d-130">當使用者試圖將受保護的項目列印到本機或網路列印機時偵測。</span><span class="sxs-lookup"><span data-stu-id="be27d-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="be27d-131">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="be27d-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="be27d-132">建立項目</span><span class="sxs-lookup"><span data-stu-id="be27d-132">create an item</span></span>|<span data-ttu-id="be27d-133">當使用者建立項時偵測</span><span class="sxs-lookup"><span data-stu-id="be27d-133">Detects when a user creates an item</span></span>| <span data-ttu-id="be27d-134">可稽核的</span><span class="sxs-lookup"><span data-stu-id="be27d-134">auditable</span></span>|
|<span data-ttu-id="be27d-135">重新命名項目</span><span class="sxs-lookup"><span data-stu-id="be27d-135">rename an item</span></span>|<span data-ttu-id="be27d-136">當使用者重新命名項時偵測</span><span class="sxs-lookup"><span data-stu-id="be27d-136">Detects when a user renames an item</span></span>| <span data-ttu-id="be27d-137">可稽核的</span><span class="sxs-lookup"><span data-stu-id="be27d-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="be27d-138">受監視的檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-138">Monitored files</span></span>

<span data-ttu-id="be27d-139">端點 DLP 支援監視下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="be27d-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="be27d-140">Word 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-140">Word files</span></span>
- <span data-ttu-id="be27d-141">PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-141">PowerPoint files</span></span>
- <span data-ttu-id="be27d-142">Excel 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-142">Excel files</span></span>
- <span data-ttu-id="be27d-143">PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-143">PDF files</span></span>
- <span data-ttu-id="be27d-144">.csv 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-144">.csv files</span></span>
- <span data-ttu-id="be27d-145">.tsv 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-145">.tsv files</span></span>
- <span data-ttu-id="be27d-146">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-146">.txt files</span></span>
- <span data-ttu-id="be27d-147">.rtf 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-147">.rtf files</span></span>
- <span data-ttu-id="be27d-148">.c 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-148">.c files</span></span>
- <span data-ttu-id="be27d-149">.class 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-149">.class files</span></span>
- <span data-ttu-id="be27d-150">.cpp 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-150">.cpp files</span></span>
- <span data-ttu-id="be27d-151">.cs 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-151">.cs files</span></span>
- <span data-ttu-id="be27d-152">.h 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-152">.h files</span></span>
- <span data-ttu-id="be27d-153">.java 檔案</span><span class="sxs-lookup"><span data-stu-id="be27d-153">.java files</span></span>
 
<span data-ttu-id="be27d-154">根據預設，端點 DLP 會稽核這些檔案類型的活動（即使沒有相符原則）。</span><span class="sxs-lookup"><span data-stu-id="be27d-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="be27d-155">如果您只想要從相符原則監控資料，您可以關閉端點 DLP 全域設定中的 **[一律稽核裝置的檔案活動]**。</span><span class="sxs-lookup"><span data-stu-id="be27d-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="be27d-156">無論如何，Word、PowerPoint、Excel、PDF 和 .csv 檔案中的相符活動都將一律受到稽核。</span><span class="sxs-lookup"><span data-stu-id="be27d-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="be27d-157">[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能截取活動。</span><span class="sxs-lookup"><span data-stu-id="be27d-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="be27d-158">端點 DLP 有何不同</span><span class="sxs-lookup"><span data-stu-id="be27d-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="be27d-159">在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="be27d-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="be27d-160">啟用裝置管理</span><span class="sxs-lookup"><span data-stu-id="be27d-160">Enabling Device management</span></span>

<span data-ttu-id="be27d-161">[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="be27d-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="be27d-162">在 DLP 原則中，您需登入您想要用作位置的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="be27d-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be27d-163">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="be27d-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="be27d-164">您可以從 [裝置管理中心] 下載的腳本處理「登入和登出」。</span><span class="sxs-lookup"><span data-stu-id="be27d-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="be27d-165">該中心含有下列每種部署方法的自訂腳本：</span><span class="sxs-lookup"><span data-stu-id="be27d-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="be27d-166">本機腳本（最多10台電腦）</span><span class="sxs-lookup"><span data-stu-id="be27d-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="be27d-167">群組原則</span><span class="sxs-lookup"><span data-stu-id="be27d-167">Group policy</span></span>
- <span data-ttu-id="be27d-168">系統中心設定管理 (版本 1610 或更新版本)</span><span class="sxs-lookup"><span data-stu-id="be27d-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="be27d-169">行動裝置管理 / Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="be27d-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="be27d-170">非持久電腦的 VDI 登入腳本</span><span class="sxs-lookup"><span data-stu-id="be27d-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be27d-171">![裝置上線頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="be27d-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="be27d-172">使用 [開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 的程式以登入程式。</span><span class="sxs-lookup"><span data-stu-id="be27d-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="be27d-173">如果您透過[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) 上線裝置，這些裝置會自動顯示在裝置清單中。</span><span class="sxs-lookup"><span data-stu-id="be27d-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be27d-174">![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="be27d-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="be27d-175">查看端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="be27d-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="be27d-176">您可以移至 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)，檢視與在端點裝置上強制執行的 DLP 原則相關的警示。</span><span class="sxs-lookup"><span data-stu-id="be27d-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警示資訊](../media/Alert-info-1.png)

<span data-ttu-id="be27d-178">您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="be27d-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![活動資訊](../media/Event-info-1.png)

<span data-ttu-id="be27d-180">當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="be27d-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be27d-181">![活動總管中的端點 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="be27d-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="be27d-182">在稽核活動中，端點 DLP 會收集大量資訊。</span><span class="sxs-lookup"><span data-stu-id="be27d-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="be27d-183">例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：</span><span class="sxs-lookup"><span data-stu-id="be27d-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="be27d-184">活動類型</span><span class="sxs-lookup"><span data-stu-id="be27d-184">activity type</span></span>
- <span data-ttu-id="be27d-185">用戶端 IP</span><span class="sxs-lookup"><span data-stu-id="be27d-185">client IP</span></span>
- <span data-ttu-id="be27d-186">目標檔案路徑</span><span class="sxs-lookup"><span data-stu-id="be27d-186">target file path</span></span>
- <span data-ttu-id="be27d-187">時間戳記</span><span class="sxs-lookup"><span data-stu-id="be27d-187">happened timestamp</span></span>
- <span data-ttu-id="be27d-188">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="be27d-188">file name</span></span>
- <span data-ttu-id="be27d-189">使用者</span><span class="sxs-lookup"><span data-stu-id="be27d-189">user</span></span>
- <span data-ttu-id="be27d-190">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="be27d-190">file extension</span></span>
- <span data-ttu-id="be27d-191">檔案大小</span><span class="sxs-lookup"><span data-stu-id="be27d-191">file size</span></span>
- <span data-ttu-id="be27d-192">敏感資訊類型 (若適用)</span><span class="sxs-lookup"><span data-stu-id="be27d-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="be27d-193">sha1 值</span><span class="sxs-lookup"><span data-stu-id="be27d-193">sha1 value</span></span>
- <span data-ttu-id="be27d-194">sha256 值</span><span class="sxs-lookup"><span data-stu-id="be27d-194">sha256 value</span></span>
- <span data-ttu-id="be27d-195">上一個檔案名稱</span><span class="sxs-lookup"><span data-stu-id="be27d-195">previous file name</span></span>
- <span data-ttu-id="be27d-196">位置</span><span class="sxs-lookup"><span data-stu-id="be27d-196">location</span></span>
- <span data-ttu-id="be27d-197">母</span><span class="sxs-lookup"><span data-stu-id="be27d-197">parent</span></span>
- <span data-ttu-id="be27d-198">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="be27d-198">filepath</span></span>
- <span data-ttu-id="be27d-199">來源位置類型</span><span class="sxs-lookup"><span data-stu-id="be27d-199">source location type</span></span>
- <span data-ttu-id="be27d-200">平台</span><span class="sxs-lookup"><span data-stu-id="be27d-200">platform</span></span>
- <span data-ttu-id="be27d-201">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="be27d-201">device name</span></span>
- <span data-ttu-id="be27d-202">目的地位置類型</span><span class="sxs-lookup"><span data-stu-id="be27d-202">destination location type</span></span>
- <span data-ttu-id="be27d-203">執行複製的應用程式</span><span class="sxs-lookup"><span data-stu-id="be27d-203">application that performed the copy</span></span>
- <span data-ttu-id="be27d-204">適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)</span><span class="sxs-lookup"><span data-stu-id="be27d-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="be27d-205">可移除式媒體裝置製造商</span><span class="sxs-lookup"><span data-stu-id="be27d-205">removable media device manufacturer</span></span>
- <span data-ttu-id="be27d-206">可移除式裝置模型</span><span class="sxs-lookup"><span data-stu-id="be27d-206">removable media device model</span></span>
- <span data-ttu-id="be27d-207">可移除式裝置序號</span><span class="sxs-lookup"><span data-stu-id="be27d-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be27d-208">![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="be27d-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="be27d-209">後續步驟</span><span class="sxs-lookup"><span data-stu-id="be27d-209">Next steps</span></span>

<span data-ttu-id="be27d-210">現在您已經瞭解了端點 DLP，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="be27d-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="be27d-211">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="be27d-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="be27d-212">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="be27d-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="be27d-213">另請參閱</span><span class="sxs-lookup"><span data-stu-id="be27d-213">See also</span></span>

- [<span data-ttu-id="be27d-214">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="be27d-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="be27d-215">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="be27d-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="be27d-216">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="be27d-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="be27d-217">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="be27d-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="be27d-218">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="be27d-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="be27d-219">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="be27d-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="be27d-220">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="be27d-220">Insider Risk management</span></span>](insider-risk-management.md)
