---
title: 為 Mac 部署 Microsoft Defender for Endpoint 的更新
description: 在企業環境中控制 Microsoft Defender for Mac 的端點的更新。
keywords: microsoft，defender，atp，mac，更新，部署
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9d373594771efe4eb647c007db3a26efe83e330e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860312"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="76a9d-104">在 macOS 上部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="76a9d-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76a9d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="76a9d-105">**Applies to:**</span></span>

- [<span data-ttu-id="76a9d-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="76a9d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="76a9d-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="76a9d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76a9d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76a9d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76a9d-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="76a9d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76a9d-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="76a9d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="76a9d-111">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="76a9d-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="76a9d-112">若要在 macOS 上更新 Microsoft Defender for Endpoint，請使用名為 Microsoft AutoUpdate (MAU) 的程式。</span><span class="sxs-lookup"><span data-stu-id="76a9d-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="76a9d-113">根據預設，MAU 會每日自動檢查更新，但您可以將其變更為每週、每月或手動。</span><span class="sxs-lookup"><span data-stu-id="76a9d-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU 螢幕擷取畫面](images/MDATP-34-MAU.png)

<span data-ttu-id="76a9d-115">如果您決定使用軟體發佈工具來部署更新，則應該設定 MAU 以手動檢查軟體更新。</span><span class="sxs-lookup"><span data-stu-id="76a9d-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="76a9d-116">您可以部署偏好設定，以設定 MAU 檢查組織中 Mac 的更新的方式和時間。</span><span class="sxs-lookup"><span data-stu-id="76a9d-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="76a9d-117">使用 msupdate</span><span class="sxs-lookup"><span data-stu-id="76a9d-117">Use msupdate</span></span>

<span data-ttu-id="76a9d-118">MAU 包含一個名為 *msupdate* 的命令列工具，其專為 IT 系統管理員設計，讓使用者可以更精確地控制何時套用更新。</span><span class="sxs-lookup"><span data-stu-id="76a9d-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="76a9d-119">如何使用此工具的指示，可在 [使用 msupdate 的更新 Office For Mac](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)中找到。</span><span class="sxs-lookup"><span data-stu-id="76a9d-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="76a9d-120">在 MAU 中，Microsoft Defender for Endpoint on macOS 上的應用程式識別碼是 *WDAV00*。</span><span class="sxs-lookup"><span data-stu-id="76a9d-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="76a9d-121">若要在 macOS 上下載並安裝 Microsoft Defender for Endpoint 的最新更新，請從終端視窗執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="76a9d-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="76a9d-122">設定 Microsoft AutoUpdate 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="76a9d-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="76a9d-123">本節說明可用於設定 MAU 的最常見偏好設定。</span><span class="sxs-lookup"><span data-stu-id="76a9d-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="76a9d-124">您可以透過企業使用的管理主控台，將這些設定部署為設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="76a9d-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="76a9d-125">以下各節將顯示設定設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="76a9d-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="76a9d-126">設定通道名稱</span><span class="sxs-lookup"><span data-stu-id="76a9d-126">Set the channel name</span></span>

<span data-ttu-id="76a9d-127">通道會判斷透過 MAU 提供的更新類型和頻率。</span><span class="sxs-lookup"><span data-stu-id="76a9d-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="76a9d-128">中的裝置 `Beta` 可在和中嘗試裝置之前的新功能 `Preview` `Current` 。</span><span class="sxs-lookup"><span data-stu-id="76a9d-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="76a9d-129">此 `Current` 通道包含最穩定的產品版本。</span><span class="sxs-lookup"><span data-stu-id="76a9d-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="76a9d-130">在 Microsoft AutoUpdate 版本4.29 之前，通道具有不同的名稱：</span><span class="sxs-lookup"><span data-stu-id="76a9d-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="76a9d-131">`Beta` 名為 `InsiderFast` (有問必答 Fast) </span><span class="sxs-lookup"><span data-stu-id="76a9d-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="76a9d-132">`Preview` 名為 `External` (內幕人士慢速) </span><span class="sxs-lookup"><span data-stu-id="76a9d-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="76a9d-133">`Current` 命名為 `Production`</span><span class="sxs-lookup"><span data-stu-id="76a9d-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="76a9d-134">為了預覽新功能並提供及早的意見反應，建議您將企業中的一些裝置設定為 `Beta` 或 `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="76a9d-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="76a9d-135">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-135">Section</span></span>|<span data-ttu-id="76a9d-136">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-137">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-138">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-138">**Key**</span></span> | <span data-ttu-id="76a9d-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="76a9d-139">ChannelName</span></span> |
| <span data-ttu-id="76a9d-140">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-140">**Data type**</span></span> | <span data-ttu-id="76a9d-141">字串</span><span class="sxs-lookup"><span data-stu-id="76a9d-141">String</span></span> |
| <span data-ttu-id="76a9d-142">**可能值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-142">**Possible values**</span></span> | <span data-ttu-id="76a9d-143">Beta 版</span><span class="sxs-lookup"><span data-stu-id="76a9d-143">Beta</span></span> <br/> <span data-ttu-id="76a9d-144">預覽</span><span class="sxs-lookup"><span data-stu-id="76a9d-144">Preview</span></span> <br/> <span data-ttu-id="76a9d-145">目前</span><span class="sxs-lookup"><span data-stu-id="76a9d-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="76a9d-146">此設定會變更透過 Microsoft AutoUpdate 更新之所有應用程式的通道。</span><span class="sxs-lookup"><span data-stu-id="76a9d-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="76a9d-147">若要將 macOS 上的通道只變更為 Microsoft Defender for Endpoint，請在取代為 `[channel-name]` 所需的通道後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="76a9d-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="76a9d-148">設定更新檢查頻率</span><span class="sxs-lookup"><span data-stu-id="76a9d-148">Set update check frequency</span></span>

<span data-ttu-id="76a9d-149">變更 MAU 搜尋更新的頻率。</span><span class="sxs-lookup"><span data-stu-id="76a9d-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="76a9d-150">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-150">Section</span></span>|<span data-ttu-id="76a9d-151">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-152">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-153">**Key**</span></span> | <span data-ttu-id="76a9d-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="76a9d-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="76a9d-155">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-155">**Data type**</span></span> | <span data-ttu-id="76a9d-156">整數</span><span class="sxs-lookup"><span data-stu-id="76a9d-156">Integer</span></span> |
| <span data-ttu-id="76a9d-157">**預設值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-157">**Default value**</span></span> | <span data-ttu-id="76a9d-158">720 (分鐘) </span><span class="sxs-lookup"><span data-stu-id="76a9d-158">720 (minutes)</span></span> |
| <span data-ttu-id="76a9d-159">**Comment**</span><span class="sxs-lookup"><span data-stu-id="76a9d-159">**Comment**</span></span> | <span data-ttu-id="76a9d-160">此值是以分鐘為單位設定。</span><span class="sxs-lookup"><span data-stu-id="76a9d-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="76a9d-161">變更 MAU 與更新互動的方式</span><span class="sxs-lookup"><span data-stu-id="76a9d-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="76a9d-162">變更 MAU 搜尋更新的方式。</span><span class="sxs-lookup"><span data-stu-id="76a9d-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="76a9d-163">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-163">Section</span></span>|<span data-ttu-id="76a9d-164">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-165">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-166">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-166">**Key**</span></span> | <span data-ttu-id="76a9d-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="76a9d-167">HowToCheck</span></span> |
| <span data-ttu-id="76a9d-168">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-168">**Data type**</span></span> | <span data-ttu-id="76a9d-169">字串</span><span class="sxs-lookup"><span data-stu-id="76a9d-169">String</span></span> |
| <span data-ttu-id="76a9d-170">**可能值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-170">**Possible values**</span></span> | <span data-ttu-id="76a9d-171">手動</span><span class="sxs-lookup"><span data-stu-id="76a9d-171">Manual</span></span> <br/> <span data-ttu-id="76a9d-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="76a9d-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="76a9d-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="76a9d-173">AutomaticDownload</span></span> |
| <span data-ttu-id="76a9d-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="76a9d-174">**Comment**</span></span> |  <span data-ttu-id="76a9d-175">請注意，如果可能的話，AutomaticDownload 將會以靜默方式下載及安裝。</span><span class="sxs-lookup"><span data-stu-id="76a9d-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="76a9d-176">變更是否已啟用「檢查更新」按鈕</span><span class="sxs-lookup"><span data-stu-id="76a9d-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="76a9d-177">變更 [Microsoft AutoUpdate] 使用者介面中的「檢查更新」選項是否可供本機使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="76a9d-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="76a9d-178">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-178">Section</span></span>|<span data-ttu-id="76a9d-179">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-180">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-181">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-181">**Key**</span></span> | <span data-ttu-id="76a9d-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="76a9d-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="76a9d-183">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-183">**Data type**</span></span> | <span data-ttu-id="76a9d-184">布林值</span><span class="sxs-lookup"><span data-stu-id="76a9d-184">Boolean</span></span> |
| <span data-ttu-id="76a9d-185">**可能值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-185">**Possible values**</span></span> | <span data-ttu-id="76a9d-186">True (預設) </span><span class="sxs-lookup"><span data-stu-id="76a9d-186">True (default)</span></span> <br/> <span data-ttu-id="76a9d-187">False</span><span class="sxs-lookup"><span data-stu-id="76a9d-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="76a9d-188">停用「有問必答] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="76a9d-188">Disable Insider checkbox</span></span>

<span data-ttu-id="76a9d-189">設定為 true 可使「加入 Office 測試人員計畫 ...」核取方塊無法使用/向使用者顯示灰色。</span><span class="sxs-lookup"><span data-stu-id="76a9d-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="76a9d-190">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-190">Section</span></span>|<span data-ttu-id="76a9d-191">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-192">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-193">**Key**</span></span> | <span data-ttu-id="76a9d-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="76a9d-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="76a9d-195">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-195">**Data type**</span></span> | <span data-ttu-id="76a9d-196">布林值</span><span class="sxs-lookup"><span data-stu-id="76a9d-196">Boolean</span></span> |
| <span data-ttu-id="76a9d-197">**可能值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-197">**Possible values**</span></span> | <span data-ttu-id="76a9d-198">False (預設) </span><span class="sxs-lookup"><span data-stu-id="76a9d-198">False (default)</span></span> <br/> <span data-ttu-id="76a9d-199">對</span><span class="sxs-lookup"><span data-stu-id="76a9d-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="76a9d-200">限制從 MAU 傳送的遙測</span><span class="sxs-lookup"><span data-stu-id="76a9d-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="76a9d-201">設定為 false 以傳送最少的心跳資料、不使用應用程式，且沒有環境細節。</span><span class="sxs-lookup"><span data-stu-id="76a9d-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="76a9d-202">區段</span><span class="sxs-lookup"><span data-stu-id="76a9d-202">Section</span></span>|<span data-ttu-id="76a9d-203">值</span><span class="sxs-lookup"><span data-stu-id="76a9d-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="76a9d-204">**網域**</span><span class="sxs-lookup"><span data-stu-id="76a9d-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="76a9d-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="76a9d-205">**Key**</span></span> | <span data-ttu-id="76a9d-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="76a9d-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="76a9d-207">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76a9d-207">**Data type**</span></span> | <span data-ttu-id="76a9d-208">布林值</span><span class="sxs-lookup"><span data-stu-id="76a9d-208">Boolean</span></span> |
| <span data-ttu-id="76a9d-209">**可能值**</span><span class="sxs-lookup"><span data-stu-id="76a9d-209">**Possible values**</span></span> | <span data-ttu-id="76a9d-210">True (預設) </span><span class="sxs-lookup"><span data-stu-id="76a9d-210">True (default)</span></span> <br/> <span data-ttu-id="76a9d-211">False</span><span class="sxs-lookup"><span data-stu-id="76a9d-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="76a9d-212">設定檔範例</span><span class="sxs-lookup"><span data-stu-id="76a9d-212">Example configuration profile</span></span>

<span data-ttu-id="76a9d-213">下列設定檔用於：</span><span class="sxs-lookup"><span data-stu-id="76a9d-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="76a9d-214">將裝置放在 Beta 通道中</span><span class="sxs-lookup"><span data-stu-id="76a9d-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="76a9d-215">自動下載並安裝更新</span><span class="sxs-lookup"><span data-stu-id="76a9d-215">Automatically download and install updates</span></span>
- <span data-ttu-id="76a9d-216">啟用使用者介面中的「檢查更新」按鈕</span><span class="sxs-lookup"><span data-stu-id="76a9d-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="76a9d-217">允許裝置上的使用者登錄到內幕通道</span><span class="sxs-lookup"><span data-stu-id="76a9d-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="76a9d-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="76a9d-218">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="76a9d-219">Intune</span><span class="sxs-lookup"><span data-stu-id="76a9d-219">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="76a9d-220">若要設定 MAU，您可以從您的企業所使用的管理工具部署此設定設定檔：</span><span class="sxs-lookup"><span data-stu-id="76a9d-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="76a9d-221">從 JAMF 上載此設定設定檔，並將偏好設定網域設定為 *autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="76a9d-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="76a9d-222">在 Intune 上，上傳此設定設定檔，並將自訂設定檔名稱設定為 *autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="76a9d-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="76a9d-223">資源</span><span class="sxs-lookup"><span data-stu-id="76a9d-223">Resources</span></span>

- [<span data-ttu-id="76a9d-224">msupdate 參照</span><span class="sxs-lookup"><span data-stu-id="76a9d-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
