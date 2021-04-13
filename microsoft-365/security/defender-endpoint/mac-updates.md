---
title: 部署適用于 Mac 的 Microsoft Defender ATP 更新
description: 在企業環境中控制 Microsoft Defender ATP for Mac 的更新。
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
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689050"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="e72a4-104">在 macOS 上部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="e72a4-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e72a4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e72a4-105">**Applies to:**</span></span>

- [<span data-ttu-id="e72a4-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e72a4-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="e72a4-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e72a4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e72a4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e72a4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e72a4-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e72a4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e72a4-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e72a4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e72a4-111">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="e72a4-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="e72a4-112">若要在 macOS 上更新 Microsoft Defender for Endpoint，請使用名為 Microsoft AutoUpdate (MAU) 的程式。</span><span class="sxs-lookup"><span data-stu-id="e72a4-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="e72a4-113">根據預設，MAU 會每日自動檢查更新，但您可以將其變更為每週、每月或手動。</span><span class="sxs-lookup"><span data-stu-id="e72a4-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU 螢幕擷取畫面](images/MDATP-34-MAU.png)

<span data-ttu-id="e72a4-115">如果您決定使用軟體發佈工具來部署更新，則應該設定 MAU 以手動檢查軟體更新。</span><span class="sxs-lookup"><span data-stu-id="e72a4-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="e72a4-116">您可以部署偏好設定，以設定 MAU 檢查組織中 Mac 的更新的方式和時間。</span><span class="sxs-lookup"><span data-stu-id="e72a4-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="e72a4-117">使用 msupdate</span><span class="sxs-lookup"><span data-stu-id="e72a4-117">Use msupdate</span></span>

<span data-ttu-id="e72a4-118">MAU 包含一個名為 *msupdate* 的命令列工具，其專為 IT 系統管理員設計，讓使用者可以更精確地控制何時套用更新。</span><span class="sxs-lookup"><span data-stu-id="e72a4-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="e72a4-119">如何使用此工具的指示，可在 [使用 msupdate 的更新 Office For Mac](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)中找到。</span><span class="sxs-lookup"><span data-stu-id="e72a4-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="e72a4-120">在 MAU 中，Microsoft Defender for Endpoint on macOS 上的應用程式識別碼是 *WDAV00*。</span><span class="sxs-lookup"><span data-stu-id="e72a4-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="e72a4-121">若要在 macOS 上下載並安裝 Microsoft Defender for Endpoint 的最新更新，請從終端視窗執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e72a4-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="e72a4-122">設定 Microsoft AutoUpdate 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="e72a4-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="e72a4-123">本節說明可用於設定 MAU 的最常見偏好設定。</span><span class="sxs-lookup"><span data-stu-id="e72a4-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="e72a4-124">您可以透過企業使用的管理主控台，將這些設定部署為設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="e72a4-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="e72a4-125">以下各節將顯示設定設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="e72a4-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="e72a4-126">設定通道名稱</span><span class="sxs-lookup"><span data-stu-id="e72a4-126">Set the channel name</span></span>

<span data-ttu-id="e72a4-127">通道會判斷透過 MAU 提供的更新類型和頻率。</span><span class="sxs-lookup"><span data-stu-id="e72a4-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="e72a4-128">中的裝置 `Beta` 可在和中嘗試裝置之前的新功能 `Preview` `Current` 。</span><span class="sxs-lookup"><span data-stu-id="e72a4-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="e72a4-129">此 `Current` 通道包含最穩定的產品版本。</span><span class="sxs-lookup"><span data-stu-id="e72a4-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e72a4-130">在 Microsoft AutoUpdate 版本4.29 之前，通道具有不同的名稱：</span><span class="sxs-lookup"><span data-stu-id="e72a4-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="e72a4-131">`Beta` 名為 `InsiderFast` (有問必答 Fast) </span><span class="sxs-lookup"><span data-stu-id="e72a4-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="e72a4-132">`Preview` 名為 `External` (內幕人士慢速) </span><span class="sxs-lookup"><span data-stu-id="e72a4-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="e72a4-133">`Current` 命名為 `Production`</span><span class="sxs-lookup"><span data-stu-id="e72a4-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="e72a4-134">為了預覽新功能並提供及早的意見反應，建議您將企業中的一些裝置設定為 `Beta` 或 `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="e72a4-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="e72a4-135">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-135">Section</span></span>|<span data-ttu-id="e72a4-136">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-137">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-137">**Domain**</span></span> | <span data-ttu-id="e72a4-138">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-138">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-139">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-139">**Key**</span></span> | <span data-ttu-id="e72a4-140">ChannelName</span><span class="sxs-lookup"><span data-stu-id="e72a4-140">ChannelName</span></span> |
| <span data-ttu-id="e72a4-141">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-141">**Data type**</span></span> | <span data-ttu-id="e72a4-142">字串</span><span class="sxs-lookup"><span data-stu-id="e72a4-142">String</span></span> |
| <span data-ttu-id="e72a4-143">**可能值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-143">**Possible values**</span></span> | <span data-ttu-id="e72a4-144">Beta 版</span><span class="sxs-lookup"><span data-stu-id="e72a4-144">Beta</span></span> <br/> <span data-ttu-id="e72a4-145">預覽</span><span class="sxs-lookup"><span data-stu-id="e72a4-145">Preview</span></span> <br/> <span data-ttu-id="e72a4-146">目前</span><span class="sxs-lookup"><span data-stu-id="e72a4-146">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="e72a4-147">此設定會變更透過 Microsoft AutoUpdate 更新之所有應用程式的通道。</span><span class="sxs-lookup"><span data-stu-id="e72a4-147">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="e72a4-148">若要將 macOS 上的通道只變更為 Microsoft Defender for Endpoint，請在取代為 `[channel-name]` 所需的通道後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e72a4-148">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="e72a4-149">設定更新檢查頻率</span><span class="sxs-lookup"><span data-stu-id="e72a4-149">Set update check frequency</span></span>

<span data-ttu-id="e72a4-150">變更 MAU 搜尋更新的頻率。</span><span class="sxs-lookup"><span data-stu-id="e72a4-150">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="e72a4-151">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-151">Section</span></span>|<span data-ttu-id="e72a4-152">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-152">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-153">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-153">**Domain**</span></span> | <span data-ttu-id="e72a4-154">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-154">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-155">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-155">**Key**</span></span> | <span data-ttu-id="e72a4-156">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="e72a4-156">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="e72a4-157">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-157">**Data type**</span></span> | <span data-ttu-id="e72a4-158">整數</span><span class="sxs-lookup"><span data-stu-id="e72a4-158">Integer</span></span> |
| <span data-ttu-id="e72a4-159">**預設值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-159">**Default value**</span></span> | <span data-ttu-id="e72a4-160">720 (分鐘) </span><span class="sxs-lookup"><span data-stu-id="e72a4-160">720 (minutes)</span></span> |
| <span data-ttu-id="e72a4-161">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e72a4-161">**Comment**</span></span> | <span data-ttu-id="e72a4-162">此值是以分鐘為單位設定。</span><span class="sxs-lookup"><span data-stu-id="e72a4-162">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="e72a4-163">變更 MAU 與更新互動的方式</span><span class="sxs-lookup"><span data-stu-id="e72a4-163">Change how MAU interacts with updates</span></span>

<span data-ttu-id="e72a4-164">變更 MAU 搜尋更新的方式。</span><span class="sxs-lookup"><span data-stu-id="e72a4-164">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="e72a4-165">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-165">Section</span></span>|<span data-ttu-id="e72a4-166">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-166">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-167">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-167">**Domain**</span></span> | <span data-ttu-id="e72a4-168">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-168">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-169">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-169">**Key**</span></span> | <span data-ttu-id="e72a4-170">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="e72a4-170">HowToCheck</span></span> |
| <span data-ttu-id="e72a4-171">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-171">**Data type**</span></span> | <span data-ttu-id="e72a4-172">字串</span><span class="sxs-lookup"><span data-stu-id="e72a4-172">String</span></span> |
| <span data-ttu-id="e72a4-173">**可能值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-173">**Possible values**</span></span> | <span data-ttu-id="e72a4-174">手動</span><span class="sxs-lookup"><span data-stu-id="e72a4-174">Manual</span></span> <br/> <span data-ttu-id="e72a4-175">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="e72a4-175">AutomaticCheck</span></span> <br/> <span data-ttu-id="e72a4-176">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="e72a4-176">AutomaticDownload</span></span> |
| <span data-ttu-id="e72a4-177">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e72a4-177">**Comment**</span></span> |  <span data-ttu-id="e72a4-178">請注意，如果可能的話，AutomaticDownload 將會以靜默方式下載及安裝。</span><span class="sxs-lookup"><span data-stu-id="e72a4-178">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="e72a4-179">變更是否已啟用「檢查更新」按鈕</span><span class="sxs-lookup"><span data-stu-id="e72a4-179">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="e72a4-180">變更 [Microsoft AutoUpdate] 使用者介面中的「檢查更新」選項是否可供本機使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="e72a4-180">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="e72a4-181">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-181">Section</span></span>|<span data-ttu-id="e72a4-182">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-182">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-183">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-183">**Domain**</span></span> | <span data-ttu-id="e72a4-184">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-184">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-185">**Key**</span></span> | <span data-ttu-id="e72a4-186">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="e72a4-186">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="e72a4-187">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-187">**Data type**</span></span> | <span data-ttu-id="e72a4-188">布林值</span><span class="sxs-lookup"><span data-stu-id="e72a4-188">Boolean</span></span> |
| <span data-ttu-id="e72a4-189">**可能值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-189">**Possible values**</span></span> | <span data-ttu-id="e72a4-190">True (預設) </span><span class="sxs-lookup"><span data-stu-id="e72a4-190">True (default)</span></span> <br/> <span data-ttu-id="e72a4-191">False</span><span class="sxs-lookup"><span data-stu-id="e72a4-191">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="e72a4-192">停用「有問必答] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="e72a4-192">Disable Insider checkbox</span></span>

<span data-ttu-id="e72a4-193">設定為 true 可使「加入 Office 測試人員計畫 ...」核取方塊無法使用/向使用者顯示灰色。</span><span class="sxs-lookup"><span data-stu-id="e72a4-193">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="e72a4-194">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-194">Section</span></span>|<span data-ttu-id="e72a4-195">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-195">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-196">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-196">**Domain**</span></span> | <span data-ttu-id="e72a4-197">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-197">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-198">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-198">**Key**</span></span> | <span data-ttu-id="e72a4-199">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="e72a4-199">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="e72a4-200">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-200">**Data type**</span></span> | <span data-ttu-id="e72a4-201">布林值</span><span class="sxs-lookup"><span data-stu-id="e72a4-201">Boolean</span></span> |
| <span data-ttu-id="e72a4-202">**可能值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-202">**Possible values**</span></span> | <span data-ttu-id="e72a4-203">False (預設) </span><span class="sxs-lookup"><span data-stu-id="e72a4-203">False (default)</span></span> <br/> <span data-ttu-id="e72a4-204">對</span><span class="sxs-lookup"><span data-stu-id="e72a4-204">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="e72a4-205">限制從 MAU 傳送的遙測</span><span class="sxs-lookup"><span data-stu-id="e72a4-205">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="e72a4-206">設定為 false 以傳送最少的心跳資料、不使用應用程式，且沒有環境細節。</span><span class="sxs-lookup"><span data-stu-id="e72a4-206">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="e72a4-207">區段</span><span class="sxs-lookup"><span data-stu-id="e72a4-207">Section</span></span>|<span data-ttu-id="e72a4-208">值</span><span class="sxs-lookup"><span data-stu-id="e72a4-208">Value</span></span>|
|:--|:--|
| <span data-ttu-id="e72a4-209">**網域**</span><span class="sxs-lookup"><span data-stu-id="e72a4-209">**Domain**</span></span> | <span data-ttu-id="e72a4-210">autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e72a4-210">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e72a4-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="e72a4-211">**Key**</span></span> | <span data-ttu-id="e72a4-212">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="e72a4-212">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="e72a4-213">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e72a4-213">**Data type**</span></span> | <span data-ttu-id="e72a4-214">布林值</span><span class="sxs-lookup"><span data-stu-id="e72a4-214">Boolean</span></span> |
| <span data-ttu-id="e72a4-215">**可能值**</span><span class="sxs-lookup"><span data-stu-id="e72a4-215">**Possible values**</span></span> | <span data-ttu-id="e72a4-216">True (預設) </span><span class="sxs-lookup"><span data-stu-id="e72a4-216">True (default)</span></span> <br/> <span data-ttu-id="e72a4-217">False</span><span class="sxs-lookup"><span data-stu-id="e72a4-217">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="e72a4-218">設定檔範例</span><span class="sxs-lookup"><span data-stu-id="e72a4-218">Example configuration profile</span></span>

<span data-ttu-id="e72a4-219">下列設定檔用於：</span><span class="sxs-lookup"><span data-stu-id="e72a4-219">The following configuration profile is used to:</span></span>
- <span data-ttu-id="e72a4-220">將裝置放在 Beta 通道中</span><span class="sxs-lookup"><span data-stu-id="e72a4-220">Place the device in the Beta channel</span></span>
- <span data-ttu-id="e72a4-221">自動下載並安裝更新</span><span class="sxs-lookup"><span data-stu-id="e72a4-221">Automatically download and install updates</span></span>
- <span data-ttu-id="e72a4-222">啟用使用者介面中的「檢查更新」按鈕</span><span class="sxs-lookup"><span data-stu-id="e72a4-222">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="e72a4-223">允許裝置上的使用者登錄到內幕通道</span><span class="sxs-lookup"><span data-stu-id="e72a4-223">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="e72a4-224">JAMF</span><span class="sxs-lookup"><span data-stu-id="e72a4-224">JAMF</span></span>

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

### <a name="intune"></a><span data-ttu-id="e72a4-225">Intune</span><span class="sxs-lookup"><span data-stu-id="e72a4-225">Intune</span></span>

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

<span data-ttu-id="e72a4-226">若要設定 MAU，您可以從您的企業所使用的管理工具部署此設定設定檔：</span><span class="sxs-lookup"><span data-stu-id="e72a4-226">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="e72a4-227">從 JAMF 上載此設定設定檔，並將偏好設定網域設定為 *autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="e72a4-227">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="e72a4-228">在 Intune 上，上傳此設定設定檔，並將自訂設定檔名稱設定為 *autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="e72a4-228">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="e72a4-229">資源</span><span class="sxs-lookup"><span data-stu-id="e72a4-229">Resources</span></span>

- [<span data-ttu-id="e72a4-230">msupdate 參照</span><span class="sxs-lookup"><span data-stu-id="e72a4-230">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
