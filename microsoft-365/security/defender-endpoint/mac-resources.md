---
title: Mac 版 Microsoft Defender ATP 的資源
description: 適用于 Mac 的 Microsoft Defender ATP 資源，包括如何卸載，如何收集診斷記錄、CLI 命令及產品的已知問題。
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 336f85b41884a441d0967c7f242b69c4d0e4941f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058319"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2a93a-104">Mac 版端點的 Microsoft Defender 資源</span><span class="sxs-lookup"><span data-stu-id="2a93a-104">Resources for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a93a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2a93a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a93a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a93a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2a93a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a93a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a93a-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2a93a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a93a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2a93a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="2a93a-110">收集診斷資訊</span><span class="sxs-lookup"><span data-stu-id="2a93a-110">Collecting diagnostic information</span></span>

<span data-ttu-id="2a93a-111">如果您可以重現問題，請增加記錄層級、執行系統一段時間，並將記錄等級還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="2a93a-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="2a93a-112">提升記錄等級：</span><span class="sxs-lookup"><span data-stu-id="2a93a-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="2a93a-113">再現問題</span><span class="sxs-lookup"><span data-stu-id="2a93a-113">Reproduce the problem</span></span>

3. <span data-ttu-id="2a93a-114">執行 `sudo mdatp diagnostic create` 以備份 Microsoft Defender For Endpoint 記錄。</span><span class="sxs-lookup"><span data-stu-id="2a93a-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="2a93a-115">檔案會儲存在 .zip 封存中。</span><span class="sxs-lookup"><span data-stu-id="2a93a-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="2a93a-116">在作業成功之後，此命令也會將檔案路徑輸出到備份。</span><span class="sxs-lookup"><span data-stu-id="2a93a-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="2a93a-117">根據預設，診斷記錄會儲存至 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。</span><span class="sxs-lookup"><span data-stu-id="2a93a-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="2a93a-118">若要變更儲存診斷記錄的目錄，請傳送 `--path [directory]` 至下列命令，以 `[directory]` 所需的目錄取代。</span><span class="sxs-lookup"><span data-stu-id="2a93a-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="2a93a-119">還原記錄等級：</span><span class="sxs-lookup"><span data-stu-id="2a93a-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="2a93a-120">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="2a93a-120">Logging installation issues</span></span>

<span data-ttu-id="2a93a-121">若安裝時發生錯誤，安裝程式將只會報告一般失敗。</span><span class="sxs-lookup"><span data-stu-id="2a93a-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="2a93a-122">詳細記錄會儲存至 `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="2a93a-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="2a93a-123">如果您在安裝時發生問題，請將此檔案傳送給我們，讓我們能夠協助您診斷原因。</span><span class="sxs-lookup"><span data-stu-id="2a93a-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="2a93a-124">卸載</span><span class="sxs-lookup"><span data-stu-id="2a93a-124">Uninstalling</span></span>

<span data-ttu-id="2a93a-125">有幾種方式可以為 Mac 卸載 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2a93a-125">There are several ways to uninstall Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="2a93a-126">請注意，在 JAMF 中提供集中式管理的卸載時，Microsoft Intune 仍無法使用它。</span><span class="sxs-lookup"><span data-stu-id="2a93a-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="2a93a-127">互動式卸載</span><span class="sxs-lookup"><span data-stu-id="2a93a-127">Interactive uninstallation</span></span>

- <span data-ttu-id="2a93a-128">開啟 **Finder > 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="2a93a-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="2a93a-129">以滑鼠右鍵按一下 [ **Microsoft DEFENDER ATP > 移至 [垃圾桶**]。</span><span class="sxs-lookup"><span data-stu-id="2a93a-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="2a93a-130">從命令列</span><span class="sxs-lookup"><span data-stu-id="2a93a-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="2a93a-131">從命令列設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-131">Configuring from the command line</span></span>

<span data-ttu-id="2a93a-132">您可以從命令列完成重要的工作，例如控制產品設定及觸發隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="2a93a-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="2a93a-133">Group</span><span class="sxs-lookup"><span data-stu-id="2a93a-133">Group</span></span>        |<span data-ttu-id="2a93a-134">案例</span><span class="sxs-lookup"><span data-stu-id="2a93a-134">Scenario</span></span>                                   |<span data-ttu-id="2a93a-135">命令</span><span class="sxs-lookup"><span data-stu-id="2a93a-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="2a93a-136">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-136">Configuration</span></span>|<span data-ttu-id="2a93a-137">開啟/關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="2a93a-138">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-138">Configuration</span></span>|<span data-ttu-id="2a93a-139">開啟/關閉雲端保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="2a93a-140">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-140">Configuration</span></span>|<span data-ttu-id="2a93a-141">開啟/關閉產品診斷程式</span><span class="sxs-lookup"><span data-stu-id="2a93a-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="2a93a-142">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-142">Configuration</span></span>|<span data-ttu-id="2a93a-143">開啟/關閉自動範例提交</span><span class="sxs-lookup"><span data-stu-id="2a93a-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="2a93a-144">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-144">Configuration</span></span>|<span data-ttu-id="2a93a-145">新增威脅名稱至允許清單</span><span class="sxs-lookup"><span data-stu-id="2a93a-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="2a93a-146">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-146">Configuration</span></span>|<span data-ttu-id="2a93a-147">從允許的清單中移除威脅名稱</span><span class="sxs-lookup"><span data-stu-id="2a93a-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="2a93a-148">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-148">Configuration</span></span>|<span data-ttu-id="2a93a-149">列出所有允許的威脅名稱</span><span class="sxs-lookup"><span data-stu-id="2a93a-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="2a93a-150">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-150">Configuration</span></span>|<span data-ttu-id="2a93a-151">開啟 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="2a93a-152">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-152">Configuration</span></span>|<span data-ttu-id="2a93a-153">關閉 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="2a93a-154">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-154">Configuration</span></span>|<span data-ttu-id="2a93a-155">開啟 PUA 保護的審計模式</span><span class="sxs-lookup"><span data-stu-id="2a93a-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="2a93a-156">設定</span><span class="sxs-lookup"><span data-stu-id="2a93a-156">Configuration</span></span>|<span data-ttu-id="2a93a-157">開啟/關閉 passiveMode</span><span class="sxs-lookup"><span data-stu-id="2a93a-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="2a93a-158">診斷</span><span class="sxs-lookup"><span data-stu-id="2a93a-158">Diagnostics</span></span>  |<span data-ttu-id="2a93a-159">變更記錄層級</span><span class="sxs-lookup"><span data-stu-id="2a93a-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="2a93a-160">診斷</span><span class="sxs-lookup"><span data-stu-id="2a93a-160">Diagnostics</span></span>  |<span data-ttu-id="2a93a-161">產生診斷記錄</span><span class="sxs-lookup"><span data-stu-id="2a93a-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="2a93a-162">健康情況</span><span class="sxs-lookup"><span data-stu-id="2a93a-162">Health</span></span>       |<span data-ttu-id="2a93a-163">檢查產品的健康情況</span><span class="sxs-lookup"><span data-stu-id="2a93a-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="2a93a-164">健康情況</span><span class="sxs-lookup"><span data-stu-id="2a93a-164">Health</span></span>       |<span data-ttu-id="2a93a-165">檢查 spefic 產品屬性</span><span class="sxs-lookup"><span data-stu-id="2a93a-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="2a93a-166">保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-166">Protection</span></span>   |<span data-ttu-id="2a93a-167">掃描路徑</span><span class="sxs-lookup"><span data-stu-id="2a93a-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="2a93a-168">保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-168">Protection</span></span>   |<span data-ttu-id="2a93a-169">進行快速掃描</span><span class="sxs-lookup"><span data-stu-id="2a93a-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="2a93a-170">保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-170">Protection</span></span>   |<span data-ttu-id="2a93a-171">執行完整掃描</span><span class="sxs-lookup"><span data-stu-id="2a93a-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="2a93a-172">保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-172">Protection</span></span>   |<span data-ttu-id="2a93a-173">取消進行中的隨選掃描</span><span class="sxs-lookup"><span data-stu-id="2a93a-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="2a93a-174">保護</span><span class="sxs-lookup"><span data-stu-id="2a93a-174">Protection</span></span>   |<span data-ttu-id="2a93a-175">要求安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="2a93a-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="2a93a-176">EDR</span><span class="sxs-lookup"><span data-stu-id="2a93a-176">EDR</span></span>          |<span data-ttu-id="2a93a-177">Add group tag to to device。</span><span class="sxs-lookup"><span data-stu-id="2a93a-177">Add group tag to device.</span></span> <span data-ttu-id="2a93a-178">EDR 標記是用來管理裝置群組。</span><span class="sxs-lookup"><span data-stu-id="2a93a-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="2a93a-179">如需詳細資訊，請造訪 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="2a93a-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="2a93a-180">EDR</span><span class="sxs-lookup"><span data-stu-id="2a93a-180">EDR</span></span>          |<span data-ttu-id="2a93a-181">從裝置移除組標記</span><span class="sxs-lookup"><span data-stu-id="2a93a-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="2a93a-182">EDR</span><span class="sxs-lookup"><span data-stu-id="2a93a-182">EDR</span></span>          |<span data-ttu-id="2a93a-183">新增群組識別碼</span><span class="sxs-lookup"><span data-stu-id="2a93a-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="2a93a-184">如何啟用自動完成</span><span class="sxs-lookup"><span data-stu-id="2a93a-184">How to enable autocompletion</span></span>

<span data-ttu-id="2a93a-185">若要在 bash 中啟用自動完成功能，請執行下列命令，並重新啟動終端機會話：</span><span class="sxs-lookup"><span data-stu-id="2a93a-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="2a93a-186">若要在 zsh 中啟用自動執行：</span><span class="sxs-lookup"><span data-stu-id="2a93a-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="2a93a-187">檢查您的裝置是否已啟用自動完成功能：</span><span class="sxs-lookup"><span data-stu-id="2a93a-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="2a93a-188">如果上述命令沒有產生任何輸出，您可以使用下列命令來啟用自動完成功能：</span><span class="sxs-lookup"><span data-stu-id="2a93a-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="2a93a-189">執行下列命令以啟用 Microsoft Defender for Mac 的自動完成功能，並重新啟動終端會話：</span><span class="sxs-lookup"><span data-stu-id="2a93a-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint for Mac and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="2a93a-190">用戶端 Microsoft Defender 端點隔離目錄</span><span class="sxs-lookup"><span data-stu-id="2a93a-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="2a93a-191">`/Library/Application Support/Microsoft/Defender/quarantine/` 包含隔離的檔案 `mdatp` 。</span><span class="sxs-lookup"><span data-stu-id="2a93a-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="2a93a-192">檔案會在威脅 trackingId 之後命名。</span><span class="sxs-lookup"><span data-stu-id="2a93a-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="2a93a-193">目前的 trackingIds 會顯示 `mdatp threat list` 。</span><span class="sxs-lookup"><span data-stu-id="2a93a-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="2a93a-194">Microsoft Defender for Endpoint 入口網站資訊</span><span class="sxs-lookup"><span data-stu-id="2a93a-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="2a93a-195">[MacOS 的 EDR 功能現在已到達](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)，在 microsoft Defender for endpoint 博客上，提供 microsoft Defender For Endpoint Security Center 中預期內容的詳細指引。</span><span class="sxs-lookup"><span data-stu-id="2a93a-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
