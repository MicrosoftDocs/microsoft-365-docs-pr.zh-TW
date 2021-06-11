---
title: 使用 Microsoft Defender 防毒軟體安排一般快速和完整掃描
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879685"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="4873c-104">設定排程的快速或完整 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="4873c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4873c-105">**Applies to:**</span></span>

- [<span data-ttu-id="4873c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4873c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4873c-107">除了永遠開啟、即時保護及 [隨選防病毒](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定定期、排程的防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-107">In addition to always-on, real-time protection and [on-demand antivirus](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled antivirus scans.</span></span> <span data-ttu-id="4873c-108">您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 或未使用端點時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-108">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or when an endpoint is not being used.</span></span> <span data-ttu-id="4873c-109">您也可以視需要設定特殊的掃描，以完成修復動作。</span><span class="sxs-lookup"><span data-stu-id="4873c-109">You can also set up special scans to complete remediation actions if needed.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="4873c-110">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="4873c-110">What do you want to do?</span></span>

- [<span data-ttu-id="4873c-111">深入瞭解快速掃描、完整掃描及自訂掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-111">Learn about quick scans, full scans, and custom scans</span></span>](#quick-scan-full-scan-and-custom-scan)
- [<span data-ttu-id="4873c-112">使用群組原則來排程防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-112">Use Group Policy to schedule antivirus scans</span></span>](schedule-antivirus-scans-group-policy.md)
- [<span data-ttu-id="4873c-113">使用 Windows PowerShell 來排程防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-113">Use Windows PowerShell to Schedule antivirus scans</span></span>](schedule-antivirus-scans-powershell.md)
- [<span data-ttu-id="4873c-114">使用 Windows 管理工具來排程防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-114">Use Windows Management Instrumentation to schedule antivirus scans</span></span>](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="4873c-115">請記住下列幾點</span><span class="sxs-lookup"><span data-stu-id="4873c-115">Keep the following points in mind</span></span>

- <span data-ttu-id="4873c-116">根據預設，Microsoft Defender 防毒軟體會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。</span><span class="sxs-lookup"><span data-stu-id="4873c-116">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="4873c-117">您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。</span><span class="sxs-lookup"><span data-stu-id="4873c-117">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

- <span data-ttu-id="4873c-118">如果在排程完整掃描期間，裝置已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。</span><span class="sxs-lookup"><span data-stu-id="4873c-118">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="4873c-119">Microsoft Defender 防毒軟體會在下一個排程的時間執行完整掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-119">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

## <a name="quick-scan-full-scan-and-custom-scan"></a><span data-ttu-id="4873c-120">快速掃描、完整掃描及自訂掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-120">Quick scan, full scan, and custom scan</span></span>

<span data-ttu-id="4873c-121">當您設定排程掃描時，您可以指定掃描是否應為完整或快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-121">When you set up scheduled scans, you can specify whether the scan should be a full or quick scan.</span></span> <span data-ttu-id="4873c-122">在大多數情況下，建議使用快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-122">In most cases, a quick scan is recommended.</span></span> 

| <span data-ttu-id="4873c-123">快速掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-123">Quick scan</span></span>  | <span data-ttu-id="4873c-124">完整掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-124">Full scan</span></span>  | <span data-ttu-id="4873c-125">自訂掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-125">Custom scan</span></span> |
|---------|---------|---------|
| <span data-ttu-id="4873c-126">建議的 () 快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知的 Windows startup 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4873c-126">(Recommended) A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="4873c-127">結合 always on 即時保護，可在開啟及關閉檔時對其進行審閱; 每當使用者流覽至資料夾時，快速掃描可協助對以系統和內核層級惡意程式碼開頭的惡意程式碼提供強防護。</span><span class="sxs-lookup"><span data-stu-id="4873c-127">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <p><span data-ttu-id="4873c-128">在大多數情況下，快速掃描足以滿足計畫掃描的建議選項。</span><span class="sxs-lookup"><span data-stu-id="4873c-128">In most cases, a quick scan is sufficient and is the recommended option for scheduled scans.</span></span> | <span data-ttu-id="4873c-129">完整掃描會從執行快速掃描開始，繼續執行所有已裝載固定磁片及移除/網路磁碟機的連續檔案掃描 (如果完整掃描已設定為執行此作業) 。</span><span class="sxs-lookup"><span data-stu-id="4873c-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="4873c-130">根據需要掃描的資料量和類型，完整掃描可能需要數小時或數天才能完成。</span><span class="sxs-lookup"><span data-stu-id="4873c-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="4873c-131">完成完整掃描之後，就可以使用新的安全性智慧，並必須進行新的掃描，以確保不會以新的安全性情報偵測到其他威脅。</span><span class="sxs-lookup"><span data-stu-id="4873c-131">When the full scan is complete, new security intelligence is available, and a new scan is then required to make sure that no other threats are detected with the new security intelligence.</span></span> <p><span data-ttu-id="4873c-132">由於完整掃描所涉及的時間和資源，在一般情況下，Microsoft 不建議排程完整掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-132">Because of the time and resources involved in a full scan, in general, Microsoft does not recommend scheduling full scans.</span></span>  | <span data-ttu-id="4873c-133">自訂掃描是在您指定的檔案和資料夾上執行的快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-133">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="4873c-134">例如，您可以選擇掃描 USB 磁片磁碟機，或裝置的本機磁片磁碟機上的特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="4873c-134">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

> [!NOTE]
> <span data-ttu-id="4873c-135">根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-135">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="4873c-136">如何知道要選擇的掃描類型為何？</span><span class="sxs-lookup"><span data-stu-id="4873c-136">How do I know which scan type to choose?</span></span>

<span data-ttu-id="4873c-137">請使用下表選擇掃描類型。</span><span class="sxs-lookup"><span data-stu-id="4873c-137">Use the following table to choose a scan type.</span></span>

| <span data-ttu-id="4873c-138">案例</span><span class="sxs-lookup"><span data-stu-id="4873c-138">Scenario</span></span>  | <span data-ttu-id="4873c-139">建議的掃描類型</span><span class="sxs-lookup"><span data-stu-id="4873c-139">Recommended scan type</span></span>  |
|---------|---------|
| <span data-ttu-id="4873c-140">您想要設定定期、排程掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-140">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="4873c-141">快速掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-141">Quick scan</span></span> <p><span data-ttu-id="4873c-142">快速掃描會檢查裝置上的處理常式、記憶體、設定檔及特定位置。</span><span class="sxs-lookup"><span data-stu-id="4873c-142">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="4873c-143">[！注意] 結合了 [always on 即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)，快速掃描可為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="4873c-143">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="4873c-144">即時保護會在開啟及關閉檔時查看檔案，以及每當使用者流覽至資料夾時，就會檢查檔案。</span><span class="sxs-lookup"><span data-stu-id="4873c-144">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
| <span data-ttu-id="4873c-145">在個別裝置上偵測到威脅（如惡意程式碼）</span><span class="sxs-lookup"><span data-stu-id="4873c-145">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="4873c-146">快速掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-146">Quick scan</span></span> <p><span data-ttu-id="4873c-147">在大多數情況下，快速掃描會捕捉並清除偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="4873c-147">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
| <span data-ttu-id="4873c-148">您想要執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4873c-148">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="4873c-149">快速掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-149">Quick scan</span></span>       |
| <span data-ttu-id="4873c-150">您想確定可擕式裝置（例如 USB 磁片磁碟機）不包含惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="4873c-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="4873c-151">自訂掃描</span><span class="sxs-lookup"><span data-stu-id="4873c-151">Custom scan</span></span> <p><span data-ttu-id="4873c-152">自訂掃描可讓您選取特定位置、資料夾或檔案，並執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-152">A custom scan enables you to select specific locations, folders, or files, and runs a quick scan.</span></span> |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="4873c-153">若要瞭解快速和完整掃描，還需要瞭解什麼？</span><span class="sxs-lookup"><span data-stu-id="4873c-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="4873c-154">惡意檔案可以儲存在快速掃描中未包含的位置。</span><span class="sxs-lookup"><span data-stu-id="4873c-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="4873c-155">不過，always on 即時保護會檢查開啟和關閉的所有檔案，以及使用者可存取之資料夾中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="4873c-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="4873c-156">即時保護和快速掃描的組合，可協助抵禦惡意程式碼的加強防護。</span><span class="sxs-lookup"><span data-stu-id="4873c-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="4873c-157">以 [雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md) 的存取保護，可協助確保已使用最新的安全性情報和雲端機教學模型掃描系統上存取的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="4873c-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="4873c-158">當即時保護偵測到惡意程式碼，且不會最初決定受影響的檔案的程度時，Microsoft Defender 防毒軟體會在修復程式中啟動完整掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="4873c-159">完整掃描可偵測其他掃描未偵測到的惡意檔，例如快速掃描。</span><span class="sxs-lookup"><span data-stu-id="4873c-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="4873c-160">不過，完整掃描可能需要一段時間，並使用寶貴的系統資源完成。</span><span class="sxs-lookup"><span data-stu-id="4873c-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="4873c-161">如果裝置離線一段時間，則完整掃描可能需要較長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="4873c-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

