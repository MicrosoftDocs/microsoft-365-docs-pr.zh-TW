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
ms.openlocfilehash: d4a3fef03322912bf169cd195984a17d8dfe3b17
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907047"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="2843c-104">深入了解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2843c-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="2843c-105">您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。</span><span class="sxs-lookup"><span data-stu-id="2843c-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="2843c-106">如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2843c-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="2843c-107">**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="2843c-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="2843c-108">將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="2843c-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="2843c-109">您可以監視和採取動作的端點活動</span><span class="sxs-lookup"><span data-stu-id="2843c-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="2843c-110">Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。</span><span class="sxs-lookup"><span data-stu-id="2843c-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="2843c-111">活動</span><span class="sxs-lookup"><span data-stu-id="2843c-111">activity</span></span> |<span data-ttu-id="2843c-112">描述</span><span class="sxs-lookup"><span data-stu-id="2843c-112">description</span></span>  | <span data-ttu-id="2843c-113">可稽核的/可限制的</span><span class="sxs-lookup"><span data-stu-id="2843c-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="2843c-114">上傳到雲端服務，或透過不允許的瀏覽器存取</span><span class="sxs-lookup"><span data-stu-id="2843c-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="2843c-115">使用者嘗試將項目上載到受限服務域或透過瀏覽器存取項目時偵測。</span><span class="sxs-lookup"><span data-stu-id="2843c-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="2843c-116">如果他們使用的瀏覽器在 DLP 中列為不允許使用的瀏覽器，則上載活動將被封鎖，使用者將被重新導向到使用Edge Chromium。</span><span class="sxs-lookup"><span data-stu-id="2843c-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="2843c-117">然後，Edge Chromium 將基於 DLP 原則設定允許或封鎖上載或存取</span><span class="sxs-lookup"><span data-stu-id="2843c-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="2843c-118">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-118">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-119">複製到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="2843c-119">copy to other app</span></span>    |<span data-ttu-id="2843c-120">使用者嘗試從受保護項目複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。</span><span class="sxs-lookup"><span data-stu-id="2843c-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="2843c-121">此活動不會偵測到在同一應用程式、流程或項目中複製和貼上資訊。</span><span class="sxs-lookup"><span data-stu-id="2843c-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="2843c-122">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-122">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-123">複製到 USB 卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="2843c-123">copy to USB removable media</span></span> |<span data-ttu-id="2843c-124">使用者嘗試將項目或資訊複製到卸除式媒體或 USB 裝置時偵測。</span><span class="sxs-lookup"><span data-stu-id="2843c-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="2843c-125">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-125">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-126">複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="2843c-126">copy to a network share</span></span>    |<span data-ttu-id="2843c-127">使用者嘗試將項目複製到網路共用或對應的網路磁碟機時偵測</span><span class="sxs-lookup"><span data-stu-id="2843c-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="2843c-128">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-128">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-129">列印文件</span><span class="sxs-lookup"><span data-stu-id="2843c-129">print a document</span></span>    |<span data-ttu-id="2843c-130">當使用者試圖將受保護的項目列印到本機或網路列印機時偵測。</span><span class="sxs-lookup"><span data-stu-id="2843c-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="2843c-131">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="2843c-132">複製到遠端工作階段</span><span class="sxs-lookup"><span data-stu-id="2843c-132">copy to a remote session</span></span>|<span data-ttu-id="2843c-133">偵測使用者何時嘗試將項目複製到遠端桌面工作階段</span><span class="sxs-lookup"><span data-stu-id="2843c-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="2843c-134">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-134">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-135">複製到藍牙裝置</span><span class="sxs-lookup"><span data-stu-id="2843c-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="2843c-136">偵測使用者何時嘗試將項目複製到不允許的藍牙應用程式 (如端點 DLP 設定中不允許的藍牙應用程式清單中所定義)。</span><span class="sxs-lookup"><span data-stu-id="2843c-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="2843c-137">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="2843c-137">auditable and restrictable</span></span>|
|<span data-ttu-id="2843c-138">建立項目</span><span class="sxs-lookup"><span data-stu-id="2843c-138">create an item</span></span>|<span data-ttu-id="2843c-139">當使用者建立項時偵測</span><span class="sxs-lookup"><span data-stu-id="2843c-139">Detects when a user creates an item</span></span>| <span data-ttu-id="2843c-140">可稽核的</span><span class="sxs-lookup"><span data-stu-id="2843c-140">auditable</span></span>|
|<span data-ttu-id="2843c-141">重新命名項目</span><span class="sxs-lookup"><span data-stu-id="2843c-141">rename an item</span></span>|<span data-ttu-id="2843c-142">當使用者重新命名項時偵測</span><span class="sxs-lookup"><span data-stu-id="2843c-142">Detects when a user renames an item</span></span>| <span data-ttu-id="2843c-143">可稽核的</span><span class="sxs-lookup"><span data-stu-id="2843c-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="2843c-144">受監視的檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-144">Monitored files</span></span>

<span data-ttu-id="2843c-145">端點 DLP 支援監視下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="2843c-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="2843c-146">Word 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-146">Word files</span></span>
- <span data-ttu-id="2843c-147">PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-147">PowerPoint files</span></span>
- <span data-ttu-id="2843c-148">Excel 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-148">Excel files</span></span>
- <span data-ttu-id="2843c-149">PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-149">PDF files</span></span>
- <span data-ttu-id="2843c-150">.csv 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-150">.csv files</span></span>
- <span data-ttu-id="2843c-151">.tsv 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-151">.tsv files</span></span>
- <span data-ttu-id="2843c-152">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-152">.txt files</span></span>
- <span data-ttu-id="2843c-153">.rtf 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-153">.rtf files</span></span>
- <span data-ttu-id="2843c-154">.c 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-154">.c files</span></span>
- <span data-ttu-id="2843c-155">.class 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-155">.class files</span></span>
- <span data-ttu-id="2843c-156">.cpp 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-156">.cpp files</span></span>
- <span data-ttu-id="2843c-157">.cs 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-157">.cs files</span></span>
- <span data-ttu-id="2843c-158">.h 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-158">.h files</span></span>
- <span data-ttu-id="2843c-159">.java 檔案</span><span class="sxs-lookup"><span data-stu-id="2843c-159">.java files</span></span>
 
<span data-ttu-id="2843c-160">根據預設，端點 DLP 會稽核這些檔案類型的活動（即使沒有相符原則）。</span><span class="sxs-lookup"><span data-stu-id="2843c-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="2843c-161">如果您只想要從相符原則監控資料，您可以關閉端點 DLP 全域設定中的 **[一律稽核裝置的檔案活動]**。</span><span class="sxs-lookup"><span data-stu-id="2843c-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="2843c-162">無論如何，Word、PowerPoint、Excel、PDF 和 .csv 檔案中的相符活動都將一律受到稽核。</span><span class="sxs-lookup"><span data-stu-id="2843c-162">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="2843c-163">[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能截取活動。</span><span class="sxs-lookup"><span data-stu-id="2843c-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="2843c-164">端點 DLP 有何不同</span><span class="sxs-lookup"><span data-stu-id="2843c-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="2843c-165">在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="2843c-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="2843c-166">啟用裝置管理</span><span class="sxs-lookup"><span data-stu-id="2843c-166">Enabling Device management</span></span>

<span data-ttu-id="2843c-167">[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="2843c-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="2843c-168">在 DLP 原則中，您需登入您想要用作位置的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="2843c-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2843c-169">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2843c-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="2843c-170">您可以從 [裝置管理中心] 下載的腳本處理「登入和登出」。</span><span class="sxs-lookup"><span data-stu-id="2843c-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="2843c-171">該中心含有下列每種部署方法的自訂腳本：</span><span class="sxs-lookup"><span data-stu-id="2843c-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="2843c-172">本機腳本（最多10台電腦）</span><span class="sxs-lookup"><span data-stu-id="2843c-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="2843c-173">群組原則</span><span class="sxs-lookup"><span data-stu-id="2843c-173">Group policy</span></span>
- <span data-ttu-id="2843c-174">系統中心設定管理 (版本 1610 或更新版本)</span><span class="sxs-lookup"><span data-stu-id="2843c-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="2843c-175">行動裝置管理 / Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2843c-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="2843c-176">非持久電腦的 VDI 登入腳本</span><span class="sxs-lookup"><span data-stu-id="2843c-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2843c-177">![裝置上線頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="2843c-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="2843c-178">使用 [開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 的程式以登入程式。</span><span class="sxs-lookup"><span data-stu-id="2843c-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="2843c-179">如果您透過[適用於端點的 Microsoft Defender](/windows/security/threat-protection/) 上線裝置，這些裝置會自動顯示在裝置清單中。</span><span class="sxs-lookup"><span data-stu-id="2843c-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2843c-180">![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="2843c-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="2843c-181">查看端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="2843c-181">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="2843c-182">您可以移至 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)，檢視與在端點裝置上強制執行的 DLP 原則相關的警示。</span><span class="sxs-lookup"><span data-stu-id="2843c-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警示資訊](../media/Alert-info-1.png)

<span data-ttu-id="2843c-184">您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2843c-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![活動資訊](../media/Event-info-1.png)

<span data-ttu-id="2843c-186">當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="2843c-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2843c-187">![活動總管中的端點 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="2843c-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="2843c-188">在稽核活動中，端點 DLP 會收集大量資訊。</span><span class="sxs-lookup"><span data-stu-id="2843c-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="2843c-189">例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：</span><span class="sxs-lookup"><span data-stu-id="2843c-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="2843c-190">活動類型</span><span class="sxs-lookup"><span data-stu-id="2843c-190">activity type</span></span>
- <span data-ttu-id="2843c-191">用戶端 IP</span><span class="sxs-lookup"><span data-stu-id="2843c-191">client IP</span></span>
- <span data-ttu-id="2843c-192">目標檔案路徑</span><span class="sxs-lookup"><span data-stu-id="2843c-192">target file path</span></span>
- <span data-ttu-id="2843c-193">時間戳記</span><span class="sxs-lookup"><span data-stu-id="2843c-193">happened timestamp</span></span>
- <span data-ttu-id="2843c-194">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="2843c-194">file name</span></span>
- <span data-ttu-id="2843c-195">使用者</span><span class="sxs-lookup"><span data-stu-id="2843c-195">user</span></span>
- <span data-ttu-id="2843c-196">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="2843c-196">file extension</span></span>
- <span data-ttu-id="2843c-197">檔案大小</span><span class="sxs-lookup"><span data-stu-id="2843c-197">file size</span></span>
- <span data-ttu-id="2843c-198">敏感資訊類型 (若適用)</span><span class="sxs-lookup"><span data-stu-id="2843c-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="2843c-199">sha1 值</span><span class="sxs-lookup"><span data-stu-id="2843c-199">sha1 value</span></span>
- <span data-ttu-id="2843c-200">sha256 值</span><span class="sxs-lookup"><span data-stu-id="2843c-200">sha256 value</span></span>
- <span data-ttu-id="2843c-201">上一個檔案名稱</span><span class="sxs-lookup"><span data-stu-id="2843c-201">previous file name</span></span>
- <span data-ttu-id="2843c-202">位置</span><span class="sxs-lookup"><span data-stu-id="2843c-202">location</span></span>
- <span data-ttu-id="2843c-203">母</span><span class="sxs-lookup"><span data-stu-id="2843c-203">parent</span></span>
- <span data-ttu-id="2843c-204">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="2843c-204">filepath</span></span>
- <span data-ttu-id="2843c-205">來源位置類型</span><span class="sxs-lookup"><span data-stu-id="2843c-205">source location type</span></span>
- <span data-ttu-id="2843c-206">平台</span><span class="sxs-lookup"><span data-stu-id="2843c-206">platform</span></span>
- <span data-ttu-id="2843c-207">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="2843c-207">device name</span></span>
- <span data-ttu-id="2843c-208">目的地位置類型</span><span class="sxs-lookup"><span data-stu-id="2843c-208">destination location type</span></span>
- <span data-ttu-id="2843c-209">執行複製的應用程式</span><span class="sxs-lookup"><span data-stu-id="2843c-209">application that performed the copy</span></span>
- <span data-ttu-id="2843c-210">適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)</span><span class="sxs-lookup"><span data-stu-id="2843c-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="2843c-211">可移除式媒體裝置製造商</span><span class="sxs-lookup"><span data-stu-id="2843c-211">removable media device manufacturer</span></span>
- <span data-ttu-id="2843c-212">可移除式裝置模型</span><span class="sxs-lookup"><span data-stu-id="2843c-212">removable media device model</span></span>
- <span data-ttu-id="2843c-213">可移除式裝置序號</span><span class="sxs-lookup"><span data-stu-id="2843c-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2843c-214">![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="2843c-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2843c-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2843c-215">Next steps</span></span>

<span data-ttu-id="2843c-216">現在您已經瞭解了端點 DLP，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="2843c-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="2843c-217">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="2843c-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="2843c-218">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2843c-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="2843c-219">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2843c-219">See also</span></span>

- [<span data-ttu-id="2843c-220">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="2843c-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="2843c-221">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2843c-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="2843c-222">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="2843c-222">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2843c-223">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2843c-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2843c-224">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="2843c-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2843c-225">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2843c-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="2843c-226">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="2843c-226">Insider Risk management</span></span>](insider-risk-management.md)