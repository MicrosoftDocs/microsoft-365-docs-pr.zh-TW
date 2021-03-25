---
title: 疑難排解攻擊面減少規則的問題
description: 用於疑難排解 Microsoft Defender for Endpoint 中的攻擊面降低規則問題的資源和範例程式碼。
keywords: 疑難排解，錯誤，修正，windows defender 例如，asr，rules，hips，疑難排解，審核，排除，錯誤正值，已中斷，封鎖，microsoft defender for endpoint，microsoft defender 高級威脅防護
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d483c098f221e2d4d2e61a10393154b8f5d1498d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198738"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="84d2a-104">疑難排解攻擊面降低規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="84d2a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="84d2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="84d2a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="84d2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="84d2a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84d2a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="84d2a-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="84d2a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="84d2a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="84d2a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="84d2a-110">當您使用 [攻擊面降減規則](attack-surface-reduction.md) 時，您可能會遇到問題，例如：</span><span class="sxs-lookup"><span data-stu-id="84d2a-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="84d2a-111">規則會封鎖檔案、處理常式或執行某些其他的動作，但不應 (false 正值) </span><span class="sxs-lookup"><span data-stu-id="84d2a-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="84d2a-112">規則不會如所述那樣運作，也不會封鎖檔案或處理應該 (false 的處理常式) </span><span class="sxs-lookup"><span data-stu-id="84d2a-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="84d2a-113">疑難排解這些問題有四個步驟：</span><span class="sxs-lookup"><span data-stu-id="84d2a-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="84d2a-114">確認必要條件</span><span class="sxs-lookup"><span data-stu-id="84d2a-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="84d2a-115">使用稽核模式來測試規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="84d2a-116">針對誤報) [新增指定之規則](#add-exclusions-for-a-false-positive) (的排除</span><span class="sxs-lookup"><span data-stu-id="84d2a-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="84d2a-117">提交支援記錄檔</span><span class="sxs-lookup"><span data-stu-id="84d2a-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="84d2a-118">確認必要條件</span><span class="sxs-lookup"><span data-stu-id="84d2a-118">Confirm prerequisites</span></span>

<span data-ttu-id="84d2a-119">攻擊面減少規則只會在裝置上運作，但有下列情況：</span><span class="sxs-lookup"><span data-stu-id="84d2a-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="84d2a-120">端點正在執行 Windows 10 企業版，版本 1709 (也稱為「秋季建立者更新) 。</span><span class="sxs-lookup"><span data-stu-id="84d2a-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="84d2a-121">端點使用 Microsoft Defender 防病毒作為獨立的防防毒保護應用程式。</span><span class="sxs-lookup"><span data-stu-id="84d2a-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="84d2a-122">[使用任何其他防病毒應用程式會使 Microsoft DEFENDER AV 自行自行停用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="84d2a-123">已啟用[即時保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="84d2a-124">未啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="84d2a-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="84d2a-125">使用群組原則將規則設定為 **停用** (值： **0**) 如 [啟用攻擊面降低規則](enable-attack-surface-reduction.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="84d2a-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="84d2a-126">如果已符合這些必要條件，請繼續進行下一個步驟，以審計模式測試規則。</span><span class="sxs-lookup"><span data-stu-id="84d2a-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="84d2a-127">使用稽核模式來測試規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="84d2a-128">您可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Windows Defender Test 基礎網站，以確認攻擊面降低規則一般會在裝置上預先設定的案例和程式中運作，也可以使用審計模式，啟用僅限報告的規則。</span><span class="sxs-lookup"><span data-stu-id="84d2a-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="84d2a-129">請遵循下列指示， [使用示範工具來查看攻擊面降低規則的運作方式](evaluate-attack-surface-reduction.md) ，以測試您所遇到之問題的特定規則。</span><span class="sxs-lookup"><span data-stu-id="84d2a-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="84d2a-130">針對您想要測試的特定規則，啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="84d2a-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="84d2a-131">使用群組原則將規則設定為「 **稽核模式** 」 (值： **2**) 如 [啟用攻擊面降低規則](enable-attack-surface-reduction.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="84d2a-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="84d2a-132">稽核模式允許規則報告檔或程式，但仍允許它執行。</span><span class="sxs-lookup"><span data-stu-id="84d2a-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="84d2a-133">執行導致問題的活動 (例如，開啟或執行應該封鎖但允許的檔案或處理常式) 。</span><span class="sxs-lookup"><span data-stu-id="84d2a-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="84d2a-134">[檢查攻擊面減少規則事件記錄](attack-surface-reduction.md) 檔，以查看規則是否會封鎖檔或處理常式（如果規則已設定為 **啟用**）。</span><span class="sxs-lookup"><span data-stu-id="84d2a-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="84d2a-135">如果規則未封鎖您預期會封鎖的檔案或進程，請先檢查是否已啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="84d2a-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="84d2a-136">已啟用稽核模式，以測試另一個功能，或透過自動化的 PowerShell 腳本，在測試完成後可能尚未停用。</span><span class="sxs-lookup"><span data-stu-id="84d2a-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="84d2a-137">如果您已使用示範工具和審計模式來測試規則，而攻擊面降低規則正在處理預先設定的案例，但是規則未如預期運作，請根據您的情況繼續執行下列其中一節：</span><span class="sxs-lookup"><span data-stu-id="84d2a-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="84d2a-138">如果攻擊面降減規則封鎖不應該封鎖的專案 (又稱為誤報) ，您可以 [先新增攻擊面降減規則排除](#add-exclusions-for-a-false-positive)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="84d2a-139">如果攻擊面降低規則不會封鎖應該封鎖 (又稱為誤報) 的專案，則可以立即繼續進行最後一個步驟， [收集診斷資料並將問題提交給我們](#collect-diagnostic-data-for-file-submissions)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="84d2a-140">新增誤報的排除</span><span class="sxs-lookup"><span data-stu-id="84d2a-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="84d2a-141">如果攻擊面降減規則封鎖不應該封鎖的專案 (也稱為誤報) ，您可以新增排除專案，以防止攻擊面不足規則評估排除的檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="84d2a-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="84d2a-142">若要新增排除，請參閱 [自訂攻擊面降減](customize-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="84d2a-143">您可以指定要排除的個別檔案和資料夾，但不能指定個別規則。</span><span class="sxs-lookup"><span data-stu-id="84d2a-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="84d2a-144">這表示排除的任何檔案或資料夾都會從所有 ASR 規則中排除。</span><span class="sxs-lookup"><span data-stu-id="84d2a-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="84d2a-145">報告誤報或 false 負數</span><span class="sxs-lookup"><span data-stu-id="84d2a-145">Report a false positive or false negative</span></span>

<span data-ttu-id="84d2a-146">使用 [Windows Defender 安全性情報 web 型提交表單](https://www.microsoft.com/wdsi/filesubmission) ，針對網路保護報告虛假的負數或假正值。</span><span class="sxs-lookup"><span data-stu-id="84d2a-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="84d2a-147">使用 Windows E5 訂閱，您也可以 [提供任何相關聯警示的連結](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="84d2a-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="84d2a-148">收集診斷資料以取得檔提交</span><span class="sxs-lookup"><span data-stu-id="84d2a-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="84d2a-149">當您報告攻擊面減少規則的問題時，系統會要求您收集並提交可供 Microsoft 支援人員和工程團隊使用的診斷資料，以協助疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="84d2a-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="84d2a-150">開啟提升許可權的命令提示字元，並變更為 Windows Defender 目錄：</span><span class="sxs-lookup"><span data-stu-id="84d2a-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="84d2a-151">執行下列命令以產生診斷記錄：</span><span class="sxs-lookup"><span data-stu-id="84d2a-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="84d2a-152">根據預設，會將其儲存至 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="84d2a-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="84d2a-153">將檔案附加到提交表單。</span><span class="sxs-lookup"><span data-stu-id="84d2a-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="84d2a-154">相關文章</span><span class="sxs-lookup"><span data-stu-id="84d2a-154">Related articles</span></span>

- [<span data-ttu-id="84d2a-155">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="84d2a-156">啟用攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="84d2a-157">評估攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="84d2a-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
