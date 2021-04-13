---
title: Mac 版端點的 Microsoft Defender 新增功能
description: 瞭解舊版 Microsoft Defender for Mac 上版本的主要變更。
keywords: microsoft、defender、atp、mac、安裝、macos、whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 67bbc987dc339c0e1f0354e07d6d2db8c39ec8b9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689038"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="97cc3-104">Mac 版端點的 Microsoft Defender 新增功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97cc3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="97cc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="97cc3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97cc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="97cc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97cc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="97cc3-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="97cc3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97cc3-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="97cc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="97cc3-110">在 macOS 11 (Big Sur) 上，Microsoft Defender for Endpoint 需要其他設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="97cc3-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="97cc3-111">如果您是現有的客戶從舊版的 macOS 升級，請務必部署 [此頁面](mac-sysext-policies.md)所列的其他設定檔。</span><span class="sxs-lookup"><span data-stu-id="97cc3-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="97cc3-112">101.25.69 (20.121022.12569.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-112">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="97cc3-113">在 macOS 上的 Microsoft Defender for Endpoint 現在可供美國政府客戶預覽。</span><span class="sxs-lookup"><span data-stu-id="97cc3-113">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="97cc3-114">如需詳細資訊，請參閱 [適用于美國政府客戶的 Microsoft Defender For Endpoint](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="97cc3-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="97cc3-115">在使用 XCode 模擬器應用程式) & bug 修正時，特別針對狀況的效能增強 (</span><span class="sxs-lookup"><span data-stu-id="97cc3-115">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="97cc3-116">101.23.64 (20.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-116">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="97cc3-117">將新的選項新增至命令列工具，以查看上次隨選掃描的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="97cc3-117">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="97cc3-118">若要查看上次隨選掃描的相關資訊，請執行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="97cc3-118">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="97cc3-119">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-119">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="97cc3-120">101.22.79 (20.121012.12279.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-120">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="97cc3-121">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-121">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="97cc3-122">101.19.88 (20.121011.11988.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-122">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="97cc3-123">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-123">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="97cc3-124">101.19.48 (20.120121.11948.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-124">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="97cc3-125">舊的命令列工具語法已被取代，此版本已被取代。</span><span class="sxs-lookup"><span data-stu-id="97cc3-125">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="97cc3-126">如需新語法的詳細資訊，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="97cc3-126">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="97cc3-127">新增命令列參數，以停用網路分機： `mdatp system-extension network-filter disable` 。</span><span class="sxs-lookup"><span data-stu-id="97cc3-127">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="97cc3-128">此命令可用於疑難排解 Microsoft Defender for Mac 上可能相關的網路相關問題。</span><span class="sxs-lookup"><span data-stu-id="97cc3-128">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="97cc3-129">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-129">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="97cc3-130">101.19.21 (20.120101.11921.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-130">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="97cc3-131">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-131">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="97cc3-132">101.15.26 (20.120102.11526.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-132">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="97cc3-133">在 macOS 11 大 Sur 上執行時，增強代理程式的可靠性</span><span class="sxs-lookup"><span data-stu-id="97cc3-133">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="97cc3-134">在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) </span><span class="sxs-lookup"><span data-stu-id="97cc3-134">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="97cc3-135">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-135">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="97cc3-136">101.13.75 (20.120101.11375.0) </span><span class="sxs-lookup"><span data-stu-id="97cc3-136">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="97cc3-137">當 Microsoft Defender for Endpoint 觸發 macOS 11 (大型 Sur) bug，資訊清單進入內核緊急情況時，已移除條件</span><span class="sxs-lookup"><span data-stu-id="97cc3-137">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="97cc3-138">在 mac 11 上執行時，修正端點安全性系統分機中的記憶體洩漏 (大型 Sur) </span><span class="sxs-lookup"><span data-stu-id="97cc3-138">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="97cc3-139">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-139">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="97cc3-140">101.10.72</span><span class="sxs-lookup"><span data-stu-id="97cc3-140">101.10.72</span></span>

- <span data-ttu-id="97cc3-141">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-141">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="97cc3-142">101.09.61</span><span class="sxs-lookup"><span data-stu-id="97cc3-142">101.09.61</span></span>

- <span data-ttu-id="97cc3-143">新增受管理的首選項，以[停用傳送意見](mac-preferences.md#show--hide-option-to-send-feedback)反應的選項</span><span class="sxs-lookup"><span data-stu-id="97cc3-143">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="97cc3-144">「狀態」功能表圖示現在會顯示管理產品設定時的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="97cc3-144">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="97cc3-145">先前，[狀態] 功能表圖示會顯示警告或錯誤狀態，即使產品設定是由系統管理員管理，也是一樣。</span><span class="sxs-lookup"><span data-stu-id="97cc3-145">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="97cc3-146">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-146">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="97cc3-147">101.09.50</span><span class="sxs-lookup"><span data-stu-id="97cc3-147">101.09.50</span></span>

- <span data-ttu-id="97cc3-148">本產品版本已在 macOS 大型 Sur 11 Beta 9 上驗證</span><span class="sxs-lookup"><span data-stu-id="97cc3-148">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="97cc3-149">`mdatp`命令列工具的新語法現在是預設的語法。</span><span class="sxs-lookup"><span data-stu-id="97cc3-149">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="97cc3-150">如需新語法的詳細資訊，請參閱 [macOS 上的 Microsoft Defender For Endpoint 的資源](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="97cc3-150">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="97cc3-151">舊的命令列工具語法會在 **2021 年1月1日** 從產品中移除。</span><span class="sxs-lookup"><span data-stu-id="97cc3-151">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="97cc3-152">`mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄</span><span class="sxs-lookup"><span data-stu-id="97cc3-152">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="97cc3-153">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-153">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="97cc3-154">101.09.49</span><span class="sxs-lookup"><span data-stu-id="97cc3-154">101.09.49</span></span>

- <span data-ttu-id="97cc3-155">使用者介面的增強功能，可將由 IT 系統管理員所管理的排除專案與本機使用者定義的排除項加以增強</span><span class="sxs-lookup"><span data-stu-id="97cc3-155">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="97cc3-156">改進的隨選掃描的 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="97cc3-156">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="97cc3-157">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-157">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="97cc3-158">101.07.23</span><span class="sxs-lookup"><span data-stu-id="97cc3-158">101.07.23</span></span>

- <span data-ttu-id="97cc3-159">新增欄位至輸出中以 `mdatp --health` 檢查被動模式和 EDR 群組識別碼的狀態</span><span class="sxs-lookup"><span data-stu-id="97cc3-159">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="97cc3-160">`mdatp --health` 將 `mdatp health` 在未來的產品更新中取代。</span><span class="sxs-lookup"><span data-stu-id="97cc3-160">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="97cc3-161">修正了在使用者介面中未標示為受管理之自動範例提交的錯誤</span><span class="sxs-lookup"><span data-stu-id="97cc3-161">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="97cc3-162">新增設定，以控制防病毒掃描歷程記錄中專案的保留。</span><span class="sxs-lookup"><span data-stu-id="97cc3-162">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="97cc3-163">您現在可以[指定掃描記錄中的專案保留天數](mac-preferences.md#antivirus-scan-history-retention-in-days)，並[指定掃描歷程記錄中的專案數上限](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)。</span><span class="sxs-lookup"><span data-stu-id="97cc3-163">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="97cc3-164">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-164">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="97cc3-165">101.06.63</span><span class="sxs-lookup"><span data-stu-id="97cc3-165">101.06.63</span></span>

- <span data-ttu-id="97cc3-166">解決版本中引入的效能回歸 `101.05.17` 。</span><span class="sxs-lookup"><span data-stu-id="97cc3-166">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="97cc3-167">修正是隨修正一起引入，以消除某些客戶在存取 SMB 共用時所看到的內核緊急音。</span><span class="sxs-lookup"><span data-stu-id="97cc3-167">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="97cc3-168">我們已還原這段程式碼變更，並調查消除內核死機的替代方法。</span><span class="sxs-lookup"><span data-stu-id="97cc3-168">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="97cc3-169">101.05.17</span><span class="sxs-lookup"><span data-stu-id="97cc3-169">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97cc3-170">我們正在使用命令列工具的新的增強語法 `mdatp` 。</span><span class="sxs-lookup"><span data-stu-id="97cc3-170">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="97cc3-171">新的語法目前是內幕人士快速和有問必答緩慢更新通道的預設值。</span><span class="sxs-lookup"><span data-stu-id="97cc3-171">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="97cc3-172">我們鼓勵您使用這個新的語法來 famliliarize 您。</span><span class="sxs-lookup"><span data-stu-id="97cc3-172">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="97cc3-173">我們將繼續支援舊的語法，並以新的語法平行，並在未來的月份中提供更多關於舊語法的取代計畫。</span><span class="sxs-lookup"><span data-stu-id="97cc3-173">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="97cc3-174">解決當存取 SMB 檔案共用時，有時發生的內核死機</span><span class="sxs-lookup"><span data-stu-id="97cc3-174">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="97cc3-175">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-175">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="97cc3-176">101.05.16</span><span class="sxs-lookup"><span data-stu-id="97cc3-176">101.05.16</span></span>

- <span data-ttu-id="97cc3-177">改進快速掃描邏輯，以大幅減少掃描的檔案數目</span><span class="sxs-lookup"><span data-stu-id="97cc3-177">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="97cc3-178">新增命令列工具的自動完成[支援](mac-resources.md#how-to-enable-autocompletion)</span><span class="sxs-lookup"><span data-stu-id="97cc3-178">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="97cc3-179">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-179">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="97cc3-180">101.03.12</span><span class="sxs-lookup"><span data-stu-id="97cc3-180">101.03.12</span></span>

- <span data-ttu-id="97cc3-181">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-181">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="97cc3-182">101.01.54</span><span class="sxs-lookup"><span data-stu-id="97cc3-182">101.01.54</span></span>

- <span data-ttu-id="97cc3-183">與時間機器相容性的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-183">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="97cc3-184">協助工具改進</span><span class="sxs-lookup"><span data-stu-id="97cc3-184">Accessibility improvements</span></span>
- <span data-ttu-id="97cc3-185">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-185">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="97cc3-186">101.00.31</span><span class="sxs-lookup"><span data-stu-id="97cc3-186">101.00.31</span></span>

- <span data-ttu-id="97cc3-187">改進 [Intune 使用者的產品上架體驗](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="97cc3-187">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="97cc3-188">防病毒 [排除現在支援萬用字元](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="97cc3-188">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="97cc3-189">新增從 macOS 內容功能表觸發防病毒掃描的功能。</span><span class="sxs-lookup"><span data-stu-id="97cc3-189">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="97cc3-190">您現在可以在 Finder 中以滑鼠右鍵按一下檔案或資料夾，然後選取 [**使用 Microsoft Defender 做為端點掃描**]</span><span class="sxs-lookup"><span data-stu-id="97cc3-190">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="97cc3-191">就地產品降級現在已由安裝程式明確地禁止使用。</span><span class="sxs-lookup"><span data-stu-id="97cc3-191">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="97cc3-192">如果您需要降級，請先卸載現有版本，然後重新設定裝置</span><span class="sxs-lookup"><span data-stu-id="97cc3-192">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="97cc3-193">& 錯誤修正的其他效能增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-193">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="97cc3-194">100.90.27</span><span class="sxs-lookup"><span data-stu-id="97cc3-194">100.90.27</span></span>

- <span data-ttu-id="97cc3-195">您現在可以在不同于整個系統更新通道的 macOS 上，設定 Microsoft Defender for Endpoint 的 [更新通道](mac-updates.md#set-the-channel-name) 。</span><span class="sxs-lookup"><span data-stu-id="97cc3-195">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="97cc3-196">新產品圖示</span><span class="sxs-lookup"><span data-stu-id="97cc3-196">New product icon</span></span>
- <span data-ttu-id="97cc3-197">其他使用者經驗增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-197">Other user experience improvements</span></span>
- <span data-ttu-id="97cc3-198">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-198">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="97cc3-199">100.86.92</span><span class="sxs-lookup"><span data-stu-id="97cc3-199">100.86.92</span></span>

- <span data-ttu-id="97cc3-200">與時間機器相容性的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-200">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="97cc3-201">解決此問題：產品有時候未清除所有卸載時所下的檔案 `/Library/Application Support/Microsoft/Defender`</span><span class="sxs-lookup"><span data-stu-id="97cc3-201">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="97cc3-202">使用 Microsoft 更新 Microsoft 產品時，降低產品的 CPU 使用率 AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="97cc3-202">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="97cc3-203">& 錯誤修正的其他效能增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-203">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="97cc3-204">100.86.91</span><span class="sxs-lookup"><span data-stu-id="97cc3-204">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="97cc3-205">為確保您的 macOS 裝置的最大保護，以及將 macOS 原生安全性更新的 Apple 停止傳遞到舊于 [current – 2] 的作業系統版本，macOS 塞拉里昂 [10.12] 上不再支援 Mac 部署和更新的 MDATP。</span><span class="sxs-lookup"><span data-stu-id="97cc3-205">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="97cc3-206">MDATP for Mac 更新及增強功能將會傳送至執行版本 Catalina [10.15]、Mojave [10.14] 和 High 塞拉里昂 [10.13] 的裝置。</span><span class="sxs-lookup"><span data-stu-id="97cc3-206">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="97cc3-207">如果您已將 Mac 部署至您的塞拉里昂 [10.12] 裝置，請升級至最新的 macOS 版本，以避免遺失保護的風險。</span><span class="sxs-lookup"><span data-stu-id="97cc3-207">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="97cc3-208">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-208">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="97cc3-209">100.83.73</span><span class="sxs-lookup"><span data-stu-id="97cc3-209">100.83.73</span></span>

- <span data-ttu-id="97cc3-210">針對[排除管理](mac-preferences.md#exclusion-merge-policy)、[威脅類型設定的管理](mac-preferences.md#threat-type-settings-merge-policy)和不[允許的威脅動作](mac-preferences.md#disallowed-threat-actions)，新增更多 IT 系統管理員控制項</span><span class="sxs-lookup"><span data-stu-id="97cc3-210">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="97cc3-211">當裝置上沒有啟用完整磁片存取時，[狀態] 功能表中隨即會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="97cc3-211">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="97cc3-212">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-212">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="97cc3-213">100.82.60</span><span class="sxs-lookup"><span data-stu-id="97cc3-213">100.82.60</span></span>

- <span data-ttu-id="97cc3-214">解決此問題：產品無法開始遵循定義更新。</span><span class="sxs-lookup"><span data-stu-id="97cc3-214">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="97cc3-215">100.80.42</span><span class="sxs-lookup"><span data-stu-id="97cc3-215">100.80.42</span></span>

- <span data-ttu-id="97cc3-216">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-216">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="97cc3-217">100.79.42</span><span class="sxs-lookup"><span data-stu-id="97cc3-217">100.79.42</span></span>

- <span data-ttu-id="97cc3-218">已修正此問題： Mac 版的 Microsoft Defender Endpoint 有時候會干擾時間機器</span><span class="sxs-lookup"><span data-stu-id="97cc3-218">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="97cc3-219">新增切換至命令列公用程式，以測試與後端服務的連線能力</span><span class="sxs-lookup"><span data-stu-id="97cc3-219">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="97cc3-220">新增在使用者介面 (中查看完整威脅史的能力，可從 [ **保護歷史記錄** ] 視圖中存取) </span><span class="sxs-lookup"><span data-stu-id="97cc3-220">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="97cc3-221">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-221">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="97cc3-222">100.72.15</span><span class="sxs-lookup"><span data-stu-id="97cc3-222">100.72.15</span></span>

- <span data-ttu-id="97cc3-223">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="97cc3-223">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="97cc3-224">100.70.99</span><span class="sxs-lookup"><span data-stu-id="97cc3-224">100.70.99</span></span>

- <span data-ttu-id="97cc3-225">解決問題，會影響某些使用者在啟用即時保護時升級至 macOS Catalina 的能力。</span><span class="sxs-lookup"><span data-stu-id="97cc3-225">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="97cc3-226">這種偶發性的問題是 Microsoft Defender 在 Catalina 升級套件內針對端點鎖定檔案所造成，在掃描威脅時，這會導致升級順序失敗。</span><span class="sxs-lookup"><span data-stu-id="97cc3-226">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="97cc3-227">100.68.99</span><span class="sxs-lookup"><span data-stu-id="97cc3-227">100.68.99</span></span>

- <span data-ttu-id="97cc3-228">新增將防病毒功能設定為在[被動模式](mac-preferences.md#enable--disable-passive-mode)中執行的功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-228">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="97cc3-229">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-229">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="97cc3-230">100.65.28</span><span class="sxs-lookup"><span data-stu-id="97cc3-230">100.65.28</span></span>

- <span data-ttu-id="97cc3-231">新增 macOS Catalina 的支援</span><span class="sxs-lookup"><span data-stu-id="97cc3-231">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="97cc3-232">macOS 10.15 (Catalina) 包含新的安全性和隱私權增強功能。</span><span class="sxs-lookup"><span data-stu-id="97cc3-232">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="97cc3-233">從這個版本開始，依預設，應用程式無法存取磁片 (上的某些位置，例如檔、下載、桌面等 ) 不經明確同意。</span><span class="sxs-lookup"><span data-stu-id="97cc3-233">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="97cc3-234">在缺少這種同意的情況下，Microsoft Defender for Endpoint 無法完全保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="97cc3-234">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="97cc3-235">授與同意的機制取決於您部署 Microsoft Defender for Endpoint 的方式：</span><span class="sxs-lookup"><span data-stu-id="97cc3-235">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="97cc3-236">如需手動部署，請參閱 [手動部署](mac-install-manually.md#how-to-allow-full-disk-access) 主題中的更新指示。</span><span class="sxs-lookup"><span data-stu-id="97cc3-236">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="97cc3-237">針對受管理的部署，請參閱以 [JAMF 為基礎的部署](mac-install-with-jamf.md) 和 [Microsoft Intune 型部署](mac-install-with-intune.md#create-system-configuration-profiles) 主題中的更新指示。</span><span class="sxs-lookup"><span data-stu-id="97cc3-237">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="97cc3-238">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="97cc3-238">Performance improvements & bug fixes</span></span>
