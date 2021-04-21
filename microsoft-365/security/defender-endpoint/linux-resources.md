---
title: Linux 資源上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 描述 Linux 上的 Microsoft Defender for Endpoint 的資源，包括如何卸載，如何收集診斷記錄、CLI 命令，以及產品的已知問題。
keywords: microsoft，defender，atp，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: de2602bdc94507d27236b939553a6567b2587f36
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903139"
---
# <a name="resources"></a><span data-ttu-id="f7765-104">資源</span><span class="sxs-lookup"><span data-stu-id="f7765-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7765-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f7765-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7765-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f7765-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7765-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7765-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7765-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f7765-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7765-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f7765-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="f7765-110">收集診斷資訊</span><span class="sxs-lookup"><span data-stu-id="f7765-110">Collect diagnostic information</span></span>

<span data-ttu-id="f7765-111">如果您可以重現問題，請先增加記錄層級，在一段時間執行系統，然後將記錄等級還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="f7765-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="f7765-112">提升記錄等級：</span><span class="sxs-lookup"><span data-stu-id="f7765-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="f7765-113">再現問題。</span><span class="sxs-lookup"><span data-stu-id="f7765-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="f7765-114">執行下列命令以備份端點記錄的 Defender。</span><span class="sxs-lookup"><span data-stu-id="f7765-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="f7765-115">檔案會儲存在 .zip 封存中。</span><span class="sxs-lookup"><span data-stu-id="f7765-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="f7765-116">在作業成功後，此命令也會將檔案路徑輸出到備份：</span><span class="sxs-lookup"><span data-stu-id="f7765-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="f7765-117">還原記錄等級：</span><span class="sxs-lookup"><span data-stu-id="f7765-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="f7765-118">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="f7765-118">Log installation issues</span></span>

<span data-ttu-id="f7765-119">若安裝時發生錯誤，安裝程式將只會報告一般失敗。</span><span class="sxs-lookup"><span data-stu-id="f7765-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="f7765-120">詳細記錄會儲存至 `/var/log/microsoft/mdatp_install.log` 。</span><span class="sxs-lookup"><span data-stu-id="f7765-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="f7765-121">如果您在安裝時發生問題，請將此檔案傳送給我們，讓我們能夠協助您診斷原因。</span><span class="sxs-lookup"><span data-stu-id="f7765-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="f7765-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="f7765-122">Uninstall</span></span>

<span data-ttu-id="f7765-123">有幾種方式可以為 Linux 卸載 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f7765-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="f7765-124">如果您使用的是設定工具（例如 Puppet），請遵循設定工具的套件卸載指示。</span><span class="sxs-lookup"><span data-stu-id="f7765-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="f7765-125">手動卸載</span><span class="sxs-lookup"><span data-stu-id="f7765-125">Manual uninstallation</span></span>

- <span data-ttu-id="f7765-126">`sudo yum remove mdatp` 對於 RHEL 和 variant (CentOS 和 Oracle Linux) 。</span><span class="sxs-lookup"><span data-stu-id="f7765-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="f7765-127">`sudo zypper remove mdatp` 用於 SLES 和變種。</span><span class="sxs-lookup"><span data-stu-id="f7765-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="f7765-128">`sudo apt-get purge mdatp` 適用于 Ubuntu 和 Debian 系統。</span><span class="sxs-lookup"><span data-stu-id="f7765-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="f7765-129">從命令列設定</span><span class="sxs-lookup"><span data-stu-id="f7765-129">Configure from the command line</span></span>

<span data-ttu-id="f7765-130">您可以從命令列完成重要的工作，例如控制產品設定及觸發隨選的掃描。</span><span class="sxs-lookup"><span data-stu-id="f7765-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="f7765-131">全域選項</span><span class="sxs-lookup"><span data-stu-id="f7765-131">Global options</span></span>

<span data-ttu-id="f7765-132">命令列工具預設會以人類可讀取的格式來輸出結果。</span><span class="sxs-lookup"><span data-stu-id="f7765-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="f7765-133">此外，此工具也支援將結果輸出為 JSON，這對自動化案例很有用。</span><span class="sxs-lookup"><span data-stu-id="f7765-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="f7765-134">若要將輸出變更為 JSON，請傳遞 `--output json` 至下列任何命令。</span><span class="sxs-lookup"><span data-stu-id="f7765-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="f7765-135">支援的命令</span><span class="sxs-lookup"><span data-stu-id="f7765-135">Supported commands</span></span>

<span data-ttu-id="f7765-136">下表列出一些最常見案例的命令。</span><span class="sxs-lookup"><span data-stu-id="f7765-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="f7765-137">`mdatp help`從終端執行，以查看完整的支援命令清單。</span><span class="sxs-lookup"><span data-stu-id="f7765-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="f7765-138">Group</span><span class="sxs-lookup"><span data-stu-id="f7765-138">Group</span></span>                 |<span data-ttu-id="f7765-139">案例</span><span class="sxs-lookup"><span data-stu-id="f7765-139">Scenario</span></span>                                                |<span data-ttu-id="f7765-140">命令</span><span class="sxs-lookup"><span data-stu-id="f7765-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="f7765-141">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-141">Configuration</span></span>         |<span data-ttu-id="f7765-142">開啟/關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="f7765-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="f7765-143">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-143">Configuration</span></span>         |<span data-ttu-id="f7765-144">開啟/關閉行為監控</span><span class="sxs-lookup"><span data-stu-id="f7765-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="f7765-145">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-145">Configuration</span></span>         |<span data-ttu-id="f7765-146">開啟/關閉雲端保護</span><span class="sxs-lookup"><span data-stu-id="f7765-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="f7765-147">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-147">Configuration</span></span>         |<span data-ttu-id="f7765-148">開啟/關閉產品診斷程式</span><span class="sxs-lookup"><span data-stu-id="f7765-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="f7765-149">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-149">Configuration</span></span>         |<span data-ttu-id="f7765-150">開啟/關閉自動範例提交</span><span class="sxs-lookup"><span data-stu-id="f7765-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="f7765-151">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-151">Configuration</span></span>         |<span data-ttu-id="f7765-152">開啟/關閉 AV 被動式模式</span><span class="sxs-lookup"><span data-stu-id="f7765-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="f7765-153">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-153">Configuration</span></span>         |<span data-ttu-id="f7765-154">新增/移除副檔名的防病毒排除</span><span class="sxs-lookup"><span data-stu-id="f7765-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="f7765-155">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-155">Configuration</span></span>         |<span data-ttu-id="f7765-156">新增/移除檔案的防病毒排除</span><span class="sxs-lookup"><span data-stu-id="f7765-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="f7765-157">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-157">Configuration</span></span>         |<span data-ttu-id="f7765-158">新增/移除目錄的防病毒排除</span><span class="sxs-lookup"><span data-stu-id="f7765-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="f7765-159">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-159">Configuration</span></span>         |<span data-ttu-id="f7765-160">新增/移除處理常式的防病毒排除</span><span class="sxs-lookup"><span data-stu-id="f7765-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="f7765-161">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-161">Configuration</span></span>         |<span data-ttu-id="f7765-162">列出所有防病毒排除</span><span class="sxs-lookup"><span data-stu-id="f7765-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="f7765-163">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-163">Configuration</span></span>         |<span data-ttu-id="f7765-164">新增威脅名稱至允許清單</span><span class="sxs-lookup"><span data-stu-id="f7765-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="f7765-165">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-165">Configuration</span></span>         |<span data-ttu-id="f7765-166">從允許的清單中移除威脅名稱</span><span class="sxs-lookup"><span data-stu-id="f7765-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="f7765-167">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-167">Configuration</span></span>         |<span data-ttu-id="f7765-168">列出所有允許的威脅名稱</span><span class="sxs-lookup"><span data-stu-id="f7765-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="f7765-169">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-169">Configuration</span></span>         |<span data-ttu-id="f7765-170">開啟 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f7765-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="f7765-171">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-171">Configuration</span></span>         |<span data-ttu-id="f7765-172">關閉 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f7765-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="f7765-173">組態</span><span class="sxs-lookup"><span data-stu-id="f7765-173">Configuration</span></span>         |<span data-ttu-id="f7765-174">開啟 PUA 保護的審計模式</span><span class="sxs-lookup"><span data-stu-id="f7765-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="f7765-175">診斷</span><span class="sxs-lookup"><span data-stu-id="f7765-175">Diagnostics</span></span>           |<span data-ttu-id="f7765-176">變更記錄層級</span><span class="sxs-lookup"><span data-stu-id="f7765-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="f7765-177">診斷</span><span class="sxs-lookup"><span data-stu-id="f7765-177">Diagnostics</span></span>           |<span data-ttu-id="f7765-178">產生診斷記錄</span><span class="sxs-lookup"><span data-stu-id="f7765-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="f7765-179">健康情況</span><span class="sxs-lookup"><span data-stu-id="f7765-179">Health</span></span>                |<span data-ttu-id="f7765-180">檢查產品的健康情況</span><span class="sxs-lookup"><span data-stu-id="f7765-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="f7765-181">保護</span><span class="sxs-lookup"><span data-stu-id="f7765-181">Protection</span></span>            |<span data-ttu-id="f7765-182">掃描路徑</span><span class="sxs-lookup"><span data-stu-id="f7765-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="f7765-183">保護</span><span class="sxs-lookup"><span data-stu-id="f7765-183">Protection</span></span>            |<span data-ttu-id="f7765-184">進行快速掃描</span><span class="sxs-lookup"><span data-stu-id="f7765-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="f7765-185">保護</span><span class="sxs-lookup"><span data-stu-id="f7765-185">Protection</span></span>            |<span data-ttu-id="f7765-186">執行完整掃描</span><span class="sxs-lookup"><span data-stu-id="f7765-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="f7765-187">保護</span><span class="sxs-lookup"><span data-stu-id="f7765-187">Protection</span></span>            |<span data-ttu-id="f7765-188">取消進行中的隨選掃描</span><span class="sxs-lookup"><span data-stu-id="f7765-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="f7765-189">保護</span><span class="sxs-lookup"><span data-stu-id="f7765-189">Protection</span></span>            |<span data-ttu-id="f7765-190">要求安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="f7765-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="f7765-191">保護歷程記錄</span><span class="sxs-lookup"><span data-stu-id="f7765-191">Protection history</span></span>    |<span data-ttu-id="f7765-192">列印完整保護歷程記錄</span><span class="sxs-lookup"><span data-stu-id="f7765-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="f7765-193">保護歷程記錄</span><span class="sxs-lookup"><span data-stu-id="f7765-193">Protection history</span></span>    |<span data-ttu-id="f7765-194">取得威脅詳細資料</span><span class="sxs-lookup"><span data-stu-id="f7765-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="f7765-195">隔離管理</span><span class="sxs-lookup"><span data-stu-id="f7765-195">Quarantine management</span></span> |<span data-ttu-id="f7765-196">列出所有隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="f7765-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="f7765-197">隔離管理</span><span class="sxs-lookup"><span data-stu-id="f7765-197">Quarantine management</span></span> |<span data-ttu-id="f7765-198">從隔離區移除所有檔案</span><span class="sxs-lookup"><span data-stu-id="f7765-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="f7765-199">隔離管理</span><span class="sxs-lookup"><span data-stu-id="f7765-199">Quarantine management</span></span> |<span data-ttu-id="f7765-200">新增已偵測到隔離威脅的檔案</span><span class="sxs-lookup"><span data-stu-id="f7765-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="f7765-201">隔離管理</span><span class="sxs-lookup"><span data-stu-id="f7765-201">Quarantine management</span></span> |<span data-ttu-id="f7765-202">從隔離區中移除被偵測為威脅的檔案</span><span class="sxs-lookup"><span data-stu-id="f7765-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="f7765-203">隔離管理</span><span class="sxs-lookup"><span data-stu-id="f7765-203">Quarantine management</span></span> |<span data-ttu-id="f7765-204">從隔離區還原檔案</span><span class="sxs-lookup"><span data-stu-id="f7765-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="f7765-205">端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="f7765-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="f7765-206">設定早期預覽 (未使用) </span><span class="sxs-lookup"><span data-stu-id="f7765-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="f7765-207">端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="f7765-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="f7765-208">設定群組識別碼</span><span class="sxs-lookup"><span data-stu-id="f7765-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="f7765-209">端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="f7765-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="f7765-210">設定/移除標籤，只 `GROUP` 支援</span><span class="sxs-lookup"><span data-stu-id="f7765-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="f7765-211">端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="f7765-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="f7765-212">列出排除 (根) </span><span class="sxs-lookup"><span data-stu-id="f7765-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="f7765-213">Microsoft Defender for Endpoint 入口網站資訊</span><span class="sxs-lookup"><span data-stu-id="f7765-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="f7765-214">在 [Defender for Endpoint] 入口網站中，您將會看到兩類資訊：</span><span class="sxs-lookup"><span data-stu-id="f7765-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="f7765-215">防病毒警示，包括：</span><span class="sxs-lookup"><span data-stu-id="f7765-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="f7765-216">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f7765-216">Severity</span></span>
  - <span data-ttu-id="f7765-217">掃描類型</span><span class="sxs-lookup"><span data-stu-id="f7765-217">Scan type</span></span>
  - <span data-ttu-id="f7765-218">裝置資訊 (主機名稱、裝置識別碼、租使用者識別碼、應用程式版本及作業系統類型) </span><span class="sxs-lookup"><span data-stu-id="f7765-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="f7765-219">檔案資訊 (名稱、路徑、大小和雜湊) </span><span class="sxs-lookup"><span data-stu-id="f7765-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="f7765-220">威脅資訊 (名稱、類型及狀態) </span><span class="sxs-lookup"><span data-stu-id="f7765-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="f7765-221">裝置資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="f7765-221">Device information, including:</span></span>
  - <span data-ttu-id="f7765-222">裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="f7765-222">Device identifier</span></span>
  - <span data-ttu-id="f7765-223">租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="f7765-223">Tenant identifier</span></span>
  - <span data-ttu-id="f7765-224">應用程式版本</span><span class="sxs-lookup"><span data-stu-id="f7765-224">App version</span></span>
  - <span data-ttu-id="f7765-225">主機名稱</span><span class="sxs-lookup"><span data-stu-id="f7765-225">Hostname</span></span>
  - <span data-ttu-id="f7765-226">作業系統類型</span><span class="sxs-lookup"><span data-stu-id="f7765-226">OS type</span></span>
  - <span data-ttu-id="f7765-227">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="f7765-227">OS version</span></span>
  - <span data-ttu-id="f7765-228">電腦模型</span><span class="sxs-lookup"><span data-stu-id="f7765-228">Computer model</span></span>
  - <span data-ttu-id="f7765-229">處理器架構</span><span class="sxs-lookup"><span data-stu-id="f7765-229">Processor architecture</span></span>
  - <span data-ttu-id="f7765-230">裝置是否為虛擬機器</span><span class="sxs-lookup"><span data-stu-id="f7765-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7765-231">已知問題</span><span class="sxs-lookup"><span data-stu-id="f7765-231">Known issues</span></span>

- <span data-ttu-id="f7765-232">在 Microsoft Defender 安全中心入口網站的 [機器資訊] 頁面上，即使產品如預期般運作，您也可能會看到「沒有感應器資料、受損的通訊」。</span><span class="sxs-lookup"><span data-stu-id="f7765-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="f7765-233">我們正在努力解決此問題。</span><span class="sxs-lookup"><span data-stu-id="f7765-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="f7765-234">登入的使用者不會出現在 Microsoft Defender Security Center 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="f7765-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="f7765-235">在 SUSE 分配中，如果 *libatomic1* 安裝失敗，您應該確認您的作業系統已登錄：</span><span class="sxs-lookup"><span data-stu-id="f7765-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
