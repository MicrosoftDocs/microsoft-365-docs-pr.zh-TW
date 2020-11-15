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
description: 'Microsoft 365 端點資料外洩防護可擴充檔案活動的監視以及這些檔案到端點的保護動作。在 Microsoft 365 合規性中心解決方案中可看到檔案 '
ms.openlocfilehash: e469872dac19db08f7b525c8a5ada725c75bfa10
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072972"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="6ed26-104">深入了解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="6ed26-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="6ed26-p102">您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6ed26-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="6ed26-p103">**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在 [活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="6ed26-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="6ed26-109">您可以監視和採取動作的端點活動</span><span class="sxs-lookup"><span data-stu-id="6ed26-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="6ed26-p104">Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。其中包括：</span><span class="sxs-lookup"><span data-stu-id="6ed26-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="6ed26-112">專案上的活動</span><span class="sxs-lookup"><span data-stu-id="6ed26-112">activity on item</span></span> |<span data-ttu-id="6ed26-113">可稽核/可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="6ed26-114">建立的</span><span class="sxs-lookup"><span data-stu-id="6ed26-114">created</span></span>    | <span data-ttu-id="6ed26-115">可稽核的</span><span class="sxs-lookup"><span data-stu-id="6ed26-115">auditable</span></span>      |
|<span data-ttu-id="6ed26-116">重新命名的</span><span class="sxs-lookup"><span data-stu-id="6ed26-116">renamed</span></span>    |  <span data-ttu-id="6ed26-117">可稽核的</span><span class="sxs-lookup"><span data-stu-id="6ed26-117">auditable</span></span>       |
|<span data-ttu-id="6ed26-118">複製到可移除式媒體或在上面建立</span><span class="sxs-lookup"><span data-stu-id="6ed26-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="6ed26-119">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-119">auditable and restrictable</span></span>|
|<span data-ttu-id="6ed26-120">複製到網路共用，例如，\\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="6ed26-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="6ed26-121">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="6ed26-122">列印的</span><span class="sxs-lookup"><span data-stu-id="6ed26-122">printed</span></span> |    <span data-ttu-id="6ed26-123">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="6ed26-124">透過 Chromium Edge 複製到雲端</span><span class="sxs-lookup"><span data-stu-id="6ed26-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="6ed26-125">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="6ed26-126">已遭不受允許的應用程式和瀏覽器存取</span><span class="sxs-lookup"><span data-stu-id="6ed26-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="6ed26-127">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6ed26-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="6ed26-128">端點 DLP 有何不同</span><span class="sxs-lookup"><span data-stu-id="6ed26-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="6ed26-129">在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="6ed26-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="6ed26-130">啟用裝置管理</span><span class="sxs-lookup"><span data-stu-id="6ed26-130">Enabling Device management</span></span>

<span data-ttu-id="6ed26-p105">[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。在 DLP 原則中，您需登入您想要用作位置的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="6ed26-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ed26-133">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="6ed26-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="6ed26-p106">您可以透過從 [裝置管理中心] 下載的指令碼處理上線和下線。該中心含有下列每種部署方法的自訂腳本：</span><span class="sxs-lookup"><span data-stu-id="6ed26-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="6ed26-136">本機腳本（最多10台電腦）</span><span class="sxs-lookup"><span data-stu-id="6ed26-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="6ed26-137">群組原則</span><span class="sxs-lookup"><span data-stu-id="6ed26-137">Group policy</span></span>
- <span data-ttu-id="6ed26-138">系統中心設定管理 (版本 1610 或更新版本)</span><span class="sxs-lookup"><span data-stu-id="6ed26-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="6ed26-139">行動裝置管理 / Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6ed26-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="6ed26-140">非持續電腦的 VDI 上線指令碼</span><span class="sxs-lookup"><span data-stu-id="6ed26-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ed26-141">![裝置上線頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="6ed26-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="6ed26-142">使用[開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 中的程序以上線裝置。</span><span class="sxs-lookup"><span data-stu-id="6ed26-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="6ed26-143">如果您透過[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) 上線裝置，這些裝置會自動顯示在裝置清單中。</span><span class="sxs-lookup"><span data-stu-id="6ed26-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ed26-144">![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="6ed26-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="6ed26-145">檢視端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="6ed26-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="6ed26-p107">[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能捕獲活動。在公用預覽中，可見全部：</span><span class="sxs-lookup"><span data-stu-id="6ed26-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="6ed26-148">Word 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-148">Word files</span></span>
- <span data-ttu-id="6ed26-149">PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-149">PowerPoint files</span></span>
- <span data-ttu-id="6ed26-150">Excel 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-150">Excel files</span></span>
- <span data-ttu-id="6ed26-151">PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-151">PDF files</span></span>
- <span data-ttu-id="6ed26-152">.csv 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-152">.csv files</span></span>
- <span data-ttu-id="6ed26-153">.tsv 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-153">.tsv files</span></span>
- <span data-ttu-id="6ed26-154">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-154">.txt files</span></span>
- <span data-ttu-id="6ed26-155">.rtf 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-155">.rtf files</span></span>
- <span data-ttu-id="6ed26-156">.c 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-156">.c files</span></span>
- <span data-ttu-id="6ed26-157">.class 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-157">.class files</span></span>
- <span data-ttu-id="6ed26-158">.cpp 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-158">.cpp files</span></span>
- <span data-ttu-id="6ed26-159">.cs 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-159">.cs files</span></span>
- <span data-ttu-id="6ed26-160">.h 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-160">.h files</span></span>
- <span data-ttu-id="6ed26-161">.java 檔案</span><span class="sxs-lookup"><span data-stu-id="6ed26-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="6ed26-p108">端點 DLP 會根據 DLP 原則評估以上所有類型的檔案，並相應地套用保護動作。系統會針對所有支援的動作稽核符合 DLP 原則的所有檔案，即使它們不受封鎖。另外，根據預設，將對在任何 Word、PowerPoint、Excel、PDF和 .csv 檔案上執行的檔案活動進行稽核，這與 DLP 原則是否存在或符合這些檔案無關。</span><span class="sxs-lookup"><span data-stu-id="6ed26-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="6ed26-165">您可以移至 [DLP 警報管理儀表板](dlp-configure-view-alerts-policies.md)，檢視與在端點裝置上強制執行的 DLP 原則相關的警示。。</span><span class="sxs-lookup"><span data-stu-id="6ed26-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警示資訊](../media/Alert-info-1.png)

<span data-ttu-id="6ed26-167">您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6ed26-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![活動資訊](../media/Event-info-1.png)

<span data-ttu-id="6ed26-169">當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="6ed26-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ed26-170">![活動總管中的端點 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="6ed26-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="6ed26-171">在稽核活動中，端點 DLP 會收集大量資訊。</span><span class="sxs-lookup"><span data-stu-id="6ed26-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="6ed26-172">例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：</span><span class="sxs-lookup"><span data-stu-id="6ed26-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="6ed26-173">活動類型</span><span class="sxs-lookup"><span data-stu-id="6ed26-173">activity type</span></span>
- <span data-ttu-id="6ed26-174">用戶端 IP</span><span class="sxs-lookup"><span data-stu-id="6ed26-174">client IP</span></span>
- <span data-ttu-id="6ed26-175">目標檔案路徑</span><span class="sxs-lookup"><span data-stu-id="6ed26-175">target file path</span></span>
- <span data-ttu-id="6ed26-176">時間戳記</span><span class="sxs-lookup"><span data-stu-id="6ed26-176">happened timestamp</span></span>
- <span data-ttu-id="6ed26-177">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6ed26-177">file name</span></span>
- <span data-ttu-id="6ed26-178">使用者</span><span class="sxs-lookup"><span data-stu-id="6ed26-178">user</span></span>
- <span data-ttu-id="6ed26-179">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="6ed26-179">file extension</span></span>
- <span data-ttu-id="6ed26-180">檔案大小</span><span class="sxs-lookup"><span data-stu-id="6ed26-180">file size</span></span>
- <span data-ttu-id="6ed26-181">敏感資訊類型 (若適用)</span><span class="sxs-lookup"><span data-stu-id="6ed26-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="6ed26-182">sha1 值</span><span class="sxs-lookup"><span data-stu-id="6ed26-182">sha1 value</span></span>
- <span data-ttu-id="6ed26-183">sha256 值</span><span class="sxs-lookup"><span data-stu-id="6ed26-183">sha256 value</span></span>
- <span data-ttu-id="6ed26-184">上一個檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6ed26-184">previous file name</span></span>
- <span data-ttu-id="6ed26-185">位置</span><span class="sxs-lookup"><span data-stu-id="6ed26-185">location</span></span>
- <span data-ttu-id="6ed26-186">母</span><span class="sxs-lookup"><span data-stu-id="6ed26-186">parent</span></span>
- <span data-ttu-id="6ed26-187">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="6ed26-187">filepath</span></span>
- <span data-ttu-id="6ed26-188">來源位置類型</span><span class="sxs-lookup"><span data-stu-id="6ed26-188">source location type</span></span>
- <span data-ttu-id="6ed26-189">平台</span><span class="sxs-lookup"><span data-stu-id="6ed26-189">platform</span></span>
- <span data-ttu-id="6ed26-190">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="6ed26-190">device name</span></span>
- <span data-ttu-id="6ed26-191">目的地位置類型</span><span class="sxs-lookup"><span data-stu-id="6ed26-191">destination location type</span></span>
- <span data-ttu-id="6ed26-192">執行複製的應用程式</span><span class="sxs-lookup"><span data-stu-id="6ed26-192">application that performed the copy</span></span>
- <span data-ttu-id="6ed26-193">適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)</span><span class="sxs-lookup"><span data-stu-id="6ed26-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="6ed26-194">可移除式媒體裝置製造商</span><span class="sxs-lookup"><span data-stu-id="6ed26-194">removable media device manufacturer</span></span>
- <span data-ttu-id="6ed26-195">可移除式裝置模型</span><span class="sxs-lookup"><span data-stu-id="6ed26-195">removable media device model</span></span>
- <span data-ttu-id="6ed26-196">可移除式裝置序號</span><span class="sxs-lookup"><span data-stu-id="6ed26-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ed26-197">![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="6ed26-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ed26-198">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6ed26-198">Next steps</span></span>

<span data-ttu-id="6ed26-199">現在您已經瞭解了端點 DLP，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="6ed26-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="6ed26-200">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="6ed26-200">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="6ed26-201">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="6ed26-201">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="6ed26-202">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ed26-202">See also</span></span>

- [<span data-ttu-id="6ed26-203">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="6ed26-203">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="6ed26-204">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="6ed26-204">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6ed26-205">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="6ed26-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="6ed26-206">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="6ed26-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6ed26-207">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="6ed26-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6ed26-208">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6ed26-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="6ed26-209">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="6ed26-209">Insider Risk management</span></span>](insider-risk-management.md)
