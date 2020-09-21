---
title: 深入瞭解 Microsoft 365 端點資料外洩防護（預覽版）
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
- SPO_Content
search.appverid:
- MET150
description: 'Microsoft 365 端點資料外洩防護擴充監視檔案活動，和針對這些端點的檔案保護動作。 在 Microsoft 365 合規性中心解決方案中可看到檔案 '
ms.openlocfilehash: 7403f20fa7c97c63be0e5001e8d3f5b37b409eee
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131545"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="6b3e5-104">深入瞭解 Microsoft 365 端點資料外洩防護（預覽版）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="6b3e5-105">您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="6b3e5-106">如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="6b3e5-107">**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="6b3e5-108">將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="6b3e5-109">您可以監視和採取動作的端點活動</span><span class="sxs-lookup"><span data-stu-id="6b3e5-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="6b3e5-110">Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="6b3e5-111">這包括：</span><span class="sxs-lookup"><span data-stu-id="6b3e5-111">This includes:</span></span>


|<span data-ttu-id="6b3e5-112">專案上的活動</span><span class="sxs-lookup"><span data-stu-id="6b3e5-112">activity on item</span></span> |<span data-ttu-id="6b3e5-113">可稽核/可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="6b3e5-114">建立的</span><span class="sxs-lookup"><span data-stu-id="6b3e5-114">created</span></span>    | <span data-ttu-id="6b3e5-115">可稽核的</span><span class="sxs-lookup"><span data-stu-id="6b3e5-115">auditable</span></span>      |
|<span data-ttu-id="6b3e5-116">重新命名的</span><span class="sxs-lookup"><span data-stu-id="6b3e5-116">renamed</span></span>    |  <span data-ttu-id="6b3e5-117">可稽核的</span><span class="sxs-lookup"><span data-stu-id="6b3e5-117">auditable</span></span>       |
|<span data-ttu-id="6b3e5-118">複製到可移除式媒體或在上面建立</span><span class="sxs-lookup"><span data-stu-id="6b3e5-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="6b3e5-119">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-119">auditable and restrictable</span></span>|
|<span data-ttu-id="6b3e5-120">複製到網路共用，例如，\\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="6b3e5-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="6b3e5-121">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="6b3e5-122">列印的</span><span class="sxs-lookup"><span data-stu-id="6b3e5-122">printed</span></span> |    <span data-ttu-id="6b3e5-123">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="6b3e5-124">透過 Chromium Edge 複製到雲端</span><span class="sxs-lookup"><span data-stu-id="6b3e5-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="6b3e5-125">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="6b3e5-126">已遭不受允許的應用程式和瀏覽器存取</span><span class="sxs-lookup"><span data-stu-id="6b3e5-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="6b3e5-127">可稽核與可限制</span><span class="sxs-lookup"><span data-stu-id="6b3e5-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="6b3e5-128">端點 DLP 有何不同</span><span class="sxs-lookup"><span data-stu-id="6b3e5-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="6b3e5-129">在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="6b3e5-130">啟用裝置管理</span><span class="sxs-lookup"><span data-stu-id="6b3e5-130">Enabling Device management</span></span>

<span data-ttu-id="6b3e5-131">[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="6b3e5-132">在 DLP 原則中，您需登入您想要用作位置的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="6b3e5-134">您可以從 [裝置管理中心] 下載的腳本處理「登入和登出」。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="6b3e5-135">該中心含有下列每種部署方法的自訂腳本：</span><span class="sxs-lookup"><span data-stu-id="6b3e5-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="6b3e5-136">本機腳本（最多10台電腦）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="6b3e5-137">群組原則</span><span class="sxs-lookup"><span data-stu-id="6b3e5-137">Group policy</span></span>
- <span data-ttu-id="6b3e5-138">系統中心設定管理 (版本 1610 或更新版本)</span><span class="sxs-lookup"><span data-stu-id="6b3e5-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="6b3e5-139">行動裝置管理 / Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6b3e5-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="6b3e5-140">非持久電腦的 VDI 登入腳本</span><span class="sxs-lookup"><span data-stu-id="6b3e5-140">VDI onboarding scripts for non-persistent machines</span></span>

![裝置登入頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="6b3e5-142">使用 [開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 的程式以登入程式。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="6b3e5-143">如果您透過 [Microsoft Defender 進階威脅防護（Microsoft Defender ATP）](https://docs.microsoft.com/windows/security/threat-protection/) 登入裝置，這些裝置會自動顯示在裝置清單中。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="6b3e5-145">查看端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="6b3e5-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="6b3e5-146">[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能捕獲活動。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="6b3e5-147">在公用預覽中，可見全部：</span><span class="sxs-lookup"><span data-stu-id="6b3e5-147">At public preview it watches all:</span></span>

- <span data-ttu-id="6b3e5-148">Word 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-148">Word files</span></span>
- <span data-ttu-id="6b3e5-149">PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-149">PowerPoint files</span></span>
- <span data-ttu-id="6b3e5-150">Excel 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-150">Excel files</span></span>
- <span data-ttu-id="6b3e5-151">PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-151">PDF files</span></span>
- <span data-ttu-id="6b3e5-152">.csv 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-152">.csv files</span></span>
- <span data-ttu-id="6b3e5-153">.tsv 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-153">.tsv files</span></span>
- <span data-ttu-id="6b3e5-154">c 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-154">c files</span></span>
- <span data-ttu-id="6b3e5-155">課程檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-155">class files</span></span>
- <span data-ttu-id="6b3e5-156">cpp 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-156">cpp files</span></span>
- <span data-ttu-id="6b3e5-157">cs 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-157">cs files</span></span>
- <span data-ttu-id="6b3e5-158">h 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-158">h files</span></span>
- <span data-ttu-id="6b3e5-159">java 檔案</span><span class="sxs-lookup"><span data-stu-id="6b3e5-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="6b3e5-160">.txt 和原始程式碼檔案不會根據預設值稽核，DLP 會根據所套用的原則評估這些檔案，然後會相應地稽核或封鎖使用者動作。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="6b3e5-161">當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![[活動總管] 中的端點 DLP 資料](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="6b3e5-163">在稽核活動中，端點 DLP 會收集大量資訊。</span><span class="sxs-lookup"><span data-stu-id="6b3e5-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="6b3e5-164">例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：</span><span class="sxs-lookup"><span data-stu-id="6b3e5-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="6b3e5-165">活動類型</span><span class="sxs-lookup"><span data-stu-id="6b3e5-165">activity type</span></span>
- <span data-ttu-id="6b3e5-166">用戶端 IP</span><span class="sxs-lookup"><span data-stu-id="6b3e5-166">client IP</span></span>
- <span data-ttu-id="6b3e5-167">目標檔案路徑</span><span class="sxs-lookup"><span data-stu-id="6b3e5-167">target file path</span></span>
- <span data-ttu-id="6b3e5-168">時間戳記</span><span class="sxs-lookup"><span data-stu-id="6b3e5-168">happened timestamp</span></span>
- <span data-ttu-id="6b3e5-169">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6b3e5-169">file name</span></span>
- <span data-ttu-id="6b3e5-170">使用者</span><span class="sxs-lookup"><span data-stu-id="6b3e5-170">user</span></span>
- <span data-ttu-id="6b3e5-171">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="6b3e5-171">file extension</span></span>
- <span data-ttu-id="6b3e5-172">檔案大小</span><span class="sxs-lookup"><span data-stu-id="6b3e5-172">file size</span></span>
- <span data-ttu-id="6b3e5-173">敏感資訊類型 (若適用)</span><span class="sxs-lookup"><span data-stu-id="6b3e5-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="6b3e5-174">sha1 值</span><span class="sxs-lookup"><span data-stu-id="6b3e5-174">sha1 value</span></span>
- <span data-ttu-id="6b3e5-175">sha256 值</span><span class="sxs-lookup"><span data-stu-id="6b3e5-175">sha256 value</span></span>
- <span data-ttu-id="6b3e5-176">上一個檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6b3e5-176">previous file name</span></span>
- <span data-ttu-id="6b3e5-177">位置</span><span class="sxs-lookup"><span data-stu-id="6b3e5-177">location</span></span>
- <span data-ttu-id="6b3e5-178">母</span><span class="sxs-lookup"><span data-stu-id="6b3e5-178">parent</span></span>
- <span data-ttu-id="6b3e5-179">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="6b3e5-179">filepath</span></span>
- <span data-ttu-id="6b3e5-180">來源位置類型</span><span class="sxs-lookup"><span data-stu-id="6b3e5-180">source location type</span></span>
- <span data-ttu-id="6b3e5-181">平台</span><span class="sxs-lookup"><span data-stu-id="6b3e5-181">platform</span></span>
- <span data-ttu-id="6b3e5-182">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="6b3e5-182">device name</span></span>
- <span data-ttu-id="6b3e5-183">目的地位置類型</span><span class="sxs-lookup"><span data-stu-id="6b3e5-183">destination location type</span></span>
- <span data-ttu-id="6b3e5-184">執行複製的應用程式</span><span class="sxs-lookup"><span data-stu-id="6b3e5-184">application that performed the copy</span></span>
- <span data-ttu-id="6b3e5-185">適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)</span><span class="sxs-lookup"><span data-stu-id="6b3e5-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="6b3e5-186">可移除式媒體裝置製造商</span><span class="sxs-lookup"><span data-stu-id="6b3e5-186">removable media device manufacturer</span></span>
- <span data-ttu-id="6b3e5-187">可移除式裝置模型</span><span class="sxs-lookup"><span data-stu-id="6b3e5-187">removable media device model</span></span>
- <span data-ttu-id="6b3e5-188">可移除式裝置序號</span><span class="sxs-lookup"><span data-stu-id="6b3e5-188">removable media device serial number</span></span>

![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="6b3e5-190">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6b3e5-190">Next steps</span></span>

<span data-ttu-id="6b3e5-191">現在您已經瞭解了端點 DLP，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="6b3e5-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="6b3e5-192">Microsoft 端點資料外洩防護快速入門（預覽版）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="6b3e5-193">使用 Microsoft 端點資料外洩防護（預覽版）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="6b3e5-194">請參閱</span><span class="sxs-lookup"><span data-stu-id="6b3e5-194">See also</span></span>

- [<span data-ttu-id="6b3e5-195">Microsoft 端點資料外洩防護快速入門（預覽版）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="6b3e5-196">使用 Microsoft 端點資料外洩防護（預覽版）</span><span class="sxs-lookup"><span data-stu-id="6b3e5-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6b3e5-197">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="6b3e5-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="6b3e5-198">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="6b3e5-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6b3e5-199">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="6b3e5-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6b3e5-200">Microsoft Defender 進階威脅防護 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="6b3e5-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="6b3e5-201">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="6b3e5-201">Insider Risk management</span></span>](insider-risk-management.md)