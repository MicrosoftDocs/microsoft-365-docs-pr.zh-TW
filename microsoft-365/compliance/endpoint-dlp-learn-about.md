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
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682624"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="d7684-104">深入了解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="d7684-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="d7684-105">您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。</span><span class="sxs-lookup"><span data-stu-id="d7684-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="d7684-106">如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d7684-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="d7684-107">**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="d7684-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="d7684-108">將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="d7684-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="d7684-109">您可以監視和採取動作的端點活動</span><span class="sxs-lookup"><span data-stu-id="d7684-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="d7684-110">Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。</span><span class="sxs-lookup"><span data-stu-id="d7684-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>


|<span data-ttu-id="d7684-111">活動</span><span class="sxs-lookup"><span data-stu-id="d7684-111">activity</span></span> |<span data-ttu-id="d7684-112">描述</span><span class="sxs-lookup"><span data-stu-id="d7684-112">description</span></span>  | <span data-ttu-id="d7684-113">可稽核的/可限制的</span><span class="sxs-lookup"><span data-stu-id="d7684-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d7684-114">上傳到雲端服務，或透過不允許的瀏覽器存取</span><span class="sxs-lookup"><span data-stu-id="d7684-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="d7684-115">使用者嘗試將項目上載到受限服務域或透過瀏覽器存取項目時偵測。</span><span class="sxs-lookup"><span data-stu-id="d7684-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="d7684-116">如果他們使用的瀏覽器在 DLP 中列為不允許使用的瀏覽器，則上載活動將被封鎖，使用者將被重新導向到使用Edge Chromium。</span><span class="sxs-lookup"><span data-stu-id="d7684-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="d7684-117">然後，Edge Chromium 將基於 DLP 原則設定允許或封鎖上載或存取</span><span class="sxs-lookup"><span data-stu-id="d7684-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="d7684-118">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="d7684-118">auditable and restrictable</span></span>|
|<span data-ttu-id="d7684-119">複製到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="d7684-119">copy to other app</span></span>    |<span data-ttu-id="d7684-120">使用者嘗試從受保護項目複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。</span><span class="sxs-lookup"><span data-stu-id="d7684-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="d7684-121">此活動不會偵測到在同一應用程式、流程或項目中複製和貼上資訊。</span><span class="sxs-lookup"><span data-stu-id="d7684-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="d7684-122">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="d7684-122">auditable and restrictable</span></span>|
|<span data-ttu-id="d7684-123">複製到 USB 卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="d7684-123">copy to USB removable media</span></span> |<span data-ttu-id="d7684-124">使用者嘗試將項目或資訊複製到卸除式媒體或 USB 裝置時偵測。</span><span class="sxs-lookup"><span data-stu-id="d7684-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="d7684-125">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="d7684-125">auditable and restrictable</span></span>|
|<span data-ttu-id="d7684-126">複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="d7684-126">copy to a network share</span></span>    |<span data-ttu-id="d7684-127">使用者嘗試將項目複製到網路共用或對應的網路磁碟機時偵測</span><span class="sxs-lookup"><span data-stu-id="d7684-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="d7684-128">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="d7684-128">auditable and restrictable</span></span>|
|<span data-ttu-id="d7684-129">列印文件</span><span class="sxs-lookup"><span data-stu-id="d7684-129">print a document</span></span>    |<span data-ttu-id="d7684-130">當使用者試圖將受保護的項目列印到本機或網路列印機時偵測。</span><span class="sxs-lookup"><span data-stu-id="d7684-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="d7684-131">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="d7684-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="d7684-132">建立項目</span><span class="sxs-lookup"><span data-stu-id="d7684-132">create an item</span></span>|<span data-ttu-id="d7684-133">當使用者建立項時偵測</span><span class="sxs-lookup"><span data-stu-id="d7684-133">Detects when a user creates an item</span></span>| <span data-ttu-id="d7684-134">可稽核的</span><span class="sxs-lookup"><span data-stu-id="d7684-134">auditable</span></span>|
|<span data-ttu-id="d7684-135">重新命名項目</span><span class="sxs-lookup"><span data-stu-id="d7684-135">rename an item</span></span>|<span data-ttu-id="d7684-136">當使用者重新命名項時偵測</span><span class="sxs-lookup"><span data-stu-id="d7684-136">Detects when a user renames an item</span></span>| <span data-ttu-id="d7684-137">可稽核的</span><span class="sxs-lookup"><span data-stu-id="d7684-137">auditable</span></span>|


## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="d7684-138">端點 DLP 有何不同</span><span class="sxs-lookup"><span data-stu-id="d7684-138">What's different in Endpoint DLP</span></span>

<span data-ttu-id="d7684-139">在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="d7684-139">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="d7684-140">啟用裝置管理</span><span class="sxs-lookup"><span data-stu-id="d7684-140">Enabling Device management</span></span>

<span data-ttu-id="d7684-141">[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="d7684-141">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="d7684-142">在 DLP 原則中，您需登入您想要用作位置的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="d7684-142">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7684-143">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="d7684-143">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="d7684-144">您可以從 [裝置管理中心] 下載的腳本處理「登入和登出」。</span><span class="sxs-lookup"><span data-stu-id="d7684-144">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="d7684-145">該中心含有下列每種部署方法的自訂腳本：</span><span class="sxs-lookup"><span data-stu-id="d7684-145">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="d7684-146">本機腳本（最多10台電腦）</span><span class="sxs-lookup"><span data-stu-id="d7684-146">local script (up to 10 machines)</span></span>
- <span data-ttu-id="d7684-147">群組原則</span><span class="sxs-lookup"><span data-stu-id="d7684-147">Group policy</span></span>
- <span data-ttu-id="d7684-148">系統中心設定管理 (版本 1610 或更新版本)</span><span class="sxs-lookup"><span data-stu-id="d7684-148">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="d7684-149">行動裝置管理 / Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d7684-149">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="d7684-150">非持久電腦的 VDI 登入腳本</span><span class="sxs-lookup"><span data-stu-id="d7684-150">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7684-151">![裝置上線頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="d7684-151">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="d7684-152">使用 [開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 的程式以登入程式。</span><span class="sxs-lookup"><span data-stu-id="d7684-152">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="d7684-153">如果您透過[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) 上線裝置，這些裝置會自動顯示在裝置清單中。</span><span class="sxs-lookup"><span data-stu-id="d7684-153">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7684-154">![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="d7684-154">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="d7684-155">查看端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="d7684-155">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="d7684-156">[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能截取活動。</span><span class="sxs-lookup"><span data-stu-id="d7684-156">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="d7684-157">目前還支援下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="d7684-157">At this time the following file types are supported:</span></span>

- <span data-ttu-id="d7684-158">Word 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-158">Word files</span></span>
- <span data-ttu-id="d7684-159">PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-159">PowerPoint files</span></span>
- <span data-ttu-id="d7684-160">Excel 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-160">Excel files</span></span>
- <span data-ttu-id="d7684-161">PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-161">PDF files</span></span>
- <span data-ttu-id="d7684-162">.csv 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-162">.csv files</span></span>
- <span data-ttu-id="d7684-163">.tsv 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-163">.tsv files</span></span>
- <span data-ttu-id="d7684-164">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-164">.txt files</span></span>
- <span data-ttu-id="d7684-165">.rtf 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-165">.rtf files</span></span>
- <span data-ttu-id="d7684-166">.c 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-166">.c files</span></span>
- <span data-ttu-id="d7684-167">.class 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-167">.class files</span></span>
- <span data-ttu-id="d7684-168">.cpp 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-168">.cpp files</span></span>
- <span data-ttu-id="d7684-169">.cs 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-169">.cs files</span></span>
- <span data-ttu-id="d7684-170">.h 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-170">.h files</span></span>
- <span data-ttu-id="d7684-171">.java 檔案</span><span class="sxs-lookup"><span data-stu-id="d7684-171">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="d7684-172">端點 DLP 會根據 DLP 原則評估以上所有類型的檔案，並相應地套用保護動作。</span><span class="sxs-lookup"><span data-stu-id="d7684-172">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="d7684-173">系統會針對所有支援的動作稽核符合 DLP 原則的所有檔案，即使它們不受封鎖。</span><span class="sxs-lookup"><span data-stu-id="d7684-173">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="d7684-174">另外，根據預設，將對在任何 Word、PowerPoint、Excel、PDF 和 .csv 檔案上執行的檔案活動進行稽核，這與 DLP 原則是否存在或符合這些檔案無關。</span><span class="sxs-lookup"><span data-stu-id="d7684-174">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="d7684-175">您可以移至 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)，檢視與在端點裝置上強制執行的 DLP 原則相關的警示。</span><span class="sxs-lookup"><span data-stu-id="d7684-175">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警示資訊](../media/Alert-info-1.png)

<span data-ttu-id="d7684-177">您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d7684-177">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![活動資訊](../media/Event-info-1.png)

<span data-ttu-id="d7684-179">當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="d7684-179">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7684-180">![活動總管中的端點 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="d7684-180">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="d7684-181">在稽核活動中，端點 DLP 會收集大量資訊。</span><span class="sxs-lookup"><span data-stu-id="d7684-181">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="d7684-182">例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：</span><span class="sxs-lookup"><span data-stu-id="d7684-182">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="d7684-183">活動類型</span><span class="sxs-lookup"><span data-stu-id="d7684-183">activity type</span></span>
- <span data-ttu-id="d7684-184">用戶端 IP</span><span class="sxs-lookup"><span data-stu-id="d7684-184">client IP</span></span>
- <span data-ttu-id="d7684-185">目標檔案路徑</span><span class="sxs-lookup"><span data-stu-id="d7684-185">target file path</span></span>
- <span data-ttu-id="d7684-186">時間戳記</span><span class="sxs-lookup"><span data-stu-id="d7684-186">happened timestamp</span></span>
- <span data-ttu-id="d7684-187">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="d7684-187">file name</span></span>
- <span data-ttu-id="d7684-188">使用者</span><span class="sxs-lookup"><span data-stu-id="d7684-188">user</span></span>
- <span data-ttu-id="d7684-189">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="d7684-189">file extension</span></span>
- <span data-ttu-id="d7684-190">檔案大小</span><span class="sxs-lookup"><span data-stu-id="d7684-190">file size</span></span>
- <span data-ttu-id="d7684-191">敏感資訊類型 (若適用)</span><span class="sxs-lookup"><span data-stu-id="d7684-191">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="d7684-192">sha1 值</span><span class="sxs-lookup"><span data-stu-id="d7684-192">sha1 value</span></span>
- <span data-ttu-id="d7684-193">sha256 值</span><span class="sxs-lookup"><span data-stu-id="d7684-193">sha256 value</span></span>
- <span data-ttu-id="d7684-194">上一個檔案名稱</span><span class="sxs-lookup"><span data-stu-id="d7684-194">previous file name</span></span>
- <span data-ttu-id="d7684-195">位置</span><span class="sxs-lookup"><span data-stu-id="d7684-195">location</span></span>
- <span data-ttu-id="d7684-196">母</span><span class="sxs-lookup"><span data-stu-id="d7684-196">parent</span></span>
- <span data-ttu-id="d7684-197">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="d7684-197">filepath</span></span>
- <span data-ttu-id="d7684-198">來源位置類型</span><span class="sxs-lookup"><span data-stu-id="d7684-198">source location type</span></span>
- <span data-ttu-id="d7684-199">平台</span><span class="sxs-lookup"><span data-stu-id="d7684-199">platform</span></span>
- <span data-ttu-id="d7684-200">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="d7684-200">device name</span></span>
- <span data-ttu-id="d7684-201">目的地位置類型</span><span class="sxs-lookup"><span data-stu-id="d7684-201">destination location type</span></span>
- <span data-ttu-id="d7684-202">執行複製的應用程式</span><span class="sxs-lookup"><span data-stu-id="d7684-202">application that performed the copy</span></span>
- <span data-ttu-id="d7684-203">適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)</span><span class="sxs-lookup"><span data-stu-id="d7684-203">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="d7684-204">可移除式媒體裝置製造商</span><span class="sxs-lookup"><span data-stu-id="d7684-204">removable media device manufacturer</span></span>
- <span data-ttu-id="d7684-205">可移除式裝置模型</span><span class="sxs-lookup"><span data-stu-id="d7684-205">removable media device model</span></span>
- <span data-ttu-id="d7684-206">可移除式裝置序號</span><span class="sxs-lookup"><span data-stu-id="d7684-206">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7684-207">![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="d7684-207">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7684-208">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d7684-208">Next steps</span></span>

<span data-ttu-id="d7684-209">現在您已經瞭解了端點 DLP，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="d7684-209">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="d7684-210">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="d7684-210">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="d7684-211">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="d7684-211">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="d7684-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d7684-212">See also</span></span>

- [<span data-ttu-id="d7684-213">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="d7684-213">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="d7684-214">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="d7684-214">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="d7684-215">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="d7684-215">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="d7684-216">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="d7684-216">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="d7684-217">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="d7684-217">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d7684-218">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d7684-218">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="d7684-219">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="d7684-219">Insider Risk management</span></span>](insider-risk-management.md)
