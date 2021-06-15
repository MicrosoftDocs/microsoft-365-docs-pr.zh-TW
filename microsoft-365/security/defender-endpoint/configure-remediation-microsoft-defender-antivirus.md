---
title: 設定 Microsoft Defender 防毒軟體偵測的補救
description: 設定 Microsoft Defender 防毒軟體在偵測到威脅時應執行的動作，以及隔離檔案應該在隔離資料夾中保留多久
keywords: 修正、修正、移除、威脅、隔離、掃描、還原
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925572"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="9c076-104">設定 Microsoft Defender 防毒軟體偵測的補救</span><span class="sxs-lookup"><span data-stu-id="9c076-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>


<span data-ttu-id="9c076-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9c076-105">**Applies to:**</span></span>

- [<span data-ttu-id="9c076-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9c076-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9c076-107">當 Microsoft Defender 防毒軟體執行掃描時，它會嘗試修正或移除所偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="9c076-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="9c076-108">您可以設定 Microsoft Defender 防毒軟體應如何處理特定威脅、是否應該在修正之前建立還原點，以及何時應移除威脅。</span><span class="sxs-lookup"><span data-stu-id="9c076-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="9c076-109">本文說明如何使用群組原則來設定這些設定，但是您也可以使用[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)和[Microsoft Intune](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="9c076-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="9c076-110">您也可以使用[ `Set-MpPreference` PowerShell Cmdlet](/powershell/module/defender/set-mppreference)或[ `MSFT_MpPreference` WMI 類別](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="9c076-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="9c076-111">設定修正選項</span><span class="sxs-lookup"><span data-stu-id="9c076-111">Configure remediation options</span></span>

1. <span data-ttu-id="9c076-112">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="9c076-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9c076-113">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="9c076-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="9c076-114">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="9c076-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="9c076-115">使用下表，選取位置，然後視需要編輯原則。</span><span class="sxs-lookup"><span data-stu-id="9c076-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="9c076-116">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9c076-116">Select **OK**.</span></span>

|<span data-ttu-id="9c076-117">位置</span><span class="sxs-lookup"><span data-stu-id="9c076-117">Location</span></span> | <span data-ttu-id="9c076-118">設定</span><span class="sxs-lookup"><span data-stu-id="9c076-118">Setting</span></span> | <span data-ttu-id="9c076-119">描述</span><span class="sxs-lookup"><span data-stu-id="9c076-119">Description</span></span> | <span data-ttu-id="9c076-120">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="9c076-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="9c076-121">掃描</span><span class="sxs-lookup"><span data-stu-id="9c076-121">Scan</span></span> | <span data-ttu-id="9c076-122">建立系統還原點</span><span class="sxs-lookup"><span data-stu-id="9c076-122">Create a system restore point</span></span> | <span data-ttu-id="9c076-123">在嘗試清除或掃描之前每天都會建立系統還原點</span><span class="sxs-lookup"><span data-stu-id="9c076-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="9c076-124">停用</span><span class="sxs-lookup"><span data-stu-id="9c076-124">Disabled</span></span>|
|<span data-ttu-id="9c076-125">掃描</span><span class="sxs-lookup"><span data-stu-id="9c076-125">Scan</span></span> | <span data-ttu-id="9c076-126">開啟從掃描歷程記錄資料夾中移除專案</span><span class="sxs-lookup"><span data-stu-id="9c076-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="9c076-127">指定在掃描歷程記錄中應該保留的專案數天數</span><span class="sxs-lookup"><span data-stu-id="9c076-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="9c076-128">30 天</span><span class="sxs-lookup"><span data-stu-id="9c076-128">30 days</span></span> |
|<span data-ttu-id="9c076-129">根</span><span class="sxs-lookup"><span data-stu-id="9c076-129">Root</span></span> | <span data-ttu-id="9c076-130">關閉常式修復</span><span class="sxs-lookup"><span data-stu-id="9c076-130">Turn off routine remediation</span></span> | <span data-ttu-id="9c076-131">您可以指定 Microsoft Defender 防毒軟體是否會自動 remediates 威脅，或者是否應要求端點使用者執行的動作。</span><span class="sxs-lookup"><span data-stu-id="9c076-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="9c076-132">停用 (威脅會自動修正) </span><span class="sxs-lookup"><span data-stu-id="9c076-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="9c076-133">隔離</span><span class="sxs-lookup"><span data-stu-id="9c076-133">Quarantine</span></span> | <span data-ttu-id="9c076-134">設定從隔離資料夾中移除專案</span><span class="sxs-lookup"><span data-stu-id="9c076-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="9c076-135">指定專案應該保留在隔離之前多少天之後才能被移除</span><span class="sxs-lookup"><span data-stu-id="9c076-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="9c076-136">90 天</span><span class="sxs-lookup"><span data-stu-id="9c076-136">90 days</span></span> |
|<span data-ttu-id="9c076-137">威脅</span><span class="sxs-lookup"><span data-stu-id="9c076-137">Threats</span></span> | <span data-ttu-id="9c076-138">指定偵測到預設動作時不應該採取的威脅警示層級</span><span class="sxs-lookup"><span data-stu-id="9c076-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="9c076-139">Microsoft Defender 防毒軟體所偵測到的每個威脅都會被指派威脅層級 (低、中、高或嚴重的) 。</span><span class="sxs-lookup"><span data-stu-id="9c076-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="9c076-140">您可以使用此設定來定義每個威脅層級的所有威脅應如何補救 (隔離、移除或忽略) </span><span class="sxs-lookup"><span data-stu-id="9c076-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="9c076-141">不適用</span><span class="sxs-lookup"><span data-stu-id="9c076-141">Not applicable</span></span> |
|<span data-ttu-id="9c076-142">威脅</span><span class="sxs-lookup"><span data-stu-id="9c076-142">Threats</span></span> | <span data-ttu-id="9c076-143">指定當偵測到預設動作時不應該採取的威脅</span><span class="sxs-lookup"><span data-stu-id="9c076-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="9c076-144">指定應該修正 (使用威脅識別碼的特定威脅) 。</span><span class="sxs-lookup"><span data-stu-id="9c076-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="9c076-145">您可以指定是否應該隔離、移除或忽略特定威脅。</span><span class="sxs-lookup"><span data-stu-id="9c076-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="9c076-146">不適用</span><span class="sxs-lookup"><span data-stu-id="9c076-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="9c076-147">Microsoft Defender 防毒軟體會根據許多因素來偵測和 remediates 檔案。</span><span class="sxs-lookup"><span data-stu-id="9c076-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="9c076-148">在某些情況下，完成修復需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="9c076-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="9c076-149">即使後來判斷出的偵測是誤報，也必須完成重新開機，以確保已完成所有其他的修復步驟。</span><span class="sxs-lookup"><span data-stu-id="9c076-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="9c076-150">如果您以誤報的 Microsoft Defender 防毒軟體隔離檔案，您可以在裝置重新開機後，從隔離區還原檔案。</span><span class="sxs-lookup"><span data-stu-id="9c076-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="9c076-151">請參閱[在 Microsoft Defender 防毒軟體還原隔離的](restore-quarantined-files-microsoft-defender-antivirus.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="9c076-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="9c076-152">為了避免未來發生此問題，您可以從掃描中排除檔案。</span><span class="sxs-lookup"><span data-stu-id="9c076-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="9c076-153">請參閱[設定及驗證 Microsoft Defender 防毒軟體掃描的排除](configure-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="9c076-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9c076-154">另請參閱[設定修正-必要的排程完整 Microsoft Defender 防毒軟體掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)以取得更多修正相關設定。</span><span class="sxs-lookup"><span data-stu-id="9c076-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c076-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c076-155">See also</span></span>

- [<span data-ttu-id="9c076-156">設定 Microsoft Defender 防毒軟體掃描選項</span><span class="sxs-lookup"><span data-stu-id="9c076-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-157">設定排定的 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="9c076-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-158">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="9c076-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-159">設定端點顯示的通知</span><span class="sxs-lookup"><span data-stu-id="9c076-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-160">設定使用者 Microsoft Defender 防毒軟體互動</span><span class="sxs-lookup"><span data-stu-id="9c076-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-161">自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="9c076-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9c076-162">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="9c076-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
