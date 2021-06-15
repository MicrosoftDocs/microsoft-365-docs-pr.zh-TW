---
title: 在特定事件之後套用 Microsoft Defender 防毒軟體更新
description: 管理在啟動或接收雲端傳送偵測報告之後，Microsoft Defender 防毒軟體套用安全性智慧更新的方式。
keywords: 更新、保護、強制更新、事件、啟動、檢查最近的通知
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926076"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="2441e-104">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="2441e-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2441e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2441e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2441e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2441e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2441e-107">Microsoft Defender 防毒軟體可讓您判斷是否 (應該在特定事件（例如啟動時）或從具備雲端功能的保護服務接收特定報告之後，) 發生更新。</span><span class="sxs-lookup"><span data-stu-id="2441e-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="2441e-108">在執行掃描之前檢查保護更新</span><span class="sxs-lookup"><span data-stu-id="2441e-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="2441e-109">您可以使用 Microsoft Endpoint Configuration Manager、群組原則、PowerShell Cmdlet 及 WMI，強制 Microsoft Defender 防毒軟體在執行排程掃描之前先檢查及下載保護更新。</span><span class="sxs-lookup"><span data-stu-id="2441e-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="2441e-110">使用 Configuration Manager 檢查保護更新，然後再執行掃描</span><span class="sxs-lookup"><span data-stu-id="2441e-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="2441e-111">在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[\*\*\*\*資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) </span><span class="sxs-lookup"><span data-stu-id="2441e-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="2441e-112">請移至 [**排程的掃描**] 區段，並在 **[是]\*\*\*\*執行掃描之前，設定檢查是否有最新的安全性情報更新**。</span><span class="sxs-lookup"><span data-stu-id="2441e-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="2441e-113">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-113">Click **OK**.</span></span>

4. <span data-ttu-id="2441e-114">[照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="2441e-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="2441e-115">使用群組原則檢查保護更新，然後再執行掃描</span><span class="sxs-lookup"><span data-stu-id="2441e-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="2441e-116">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2441e-117">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2441e-118">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="2441e-119">展開樹狀目錄，以 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **掃描** 的元件。</span><span class="sxs-lookup"><span data-stu-id="2441e-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="2441e-120">**在執行排程掃描之前，按兩下 [檢查最新的病毒和間諜軟體定義**]，然後將選項設定為 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="2441e-121">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="2441e-122">在執行掃描之前，使用 PowerShell Cmdlet 檢查保護更新</span><span class="sxs-lookup"><span data-stu-id="2441e-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="2441e-123">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2441e-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="2441e-124">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/index)。</span><span class="sxs-lookup"><span data-stu-id="2441e-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="2441e-125">在執行掃描之前，使用 Windows 管理指令 (WMI) 檢查保護更新</span><span class="sxs-lookup"><span data-stu-id="2441e-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="2441e-126">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="2441e-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="2441e-127">如需詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="2441e-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="2441e-128">在啟動時檢查保護更新</span><span class="sxs-lookup"><span data-stu-id="2441e-128">Check for protection updates on startup</span></span>

<span data-ttu-id="2441e-129">您可以使用群組原則，強制 Microsoft Defender 防毒軟體在機器啟動時，檢查及下載保護更新。</span><span class="sxs-lookup"><span data-stu-id="2441e-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="2441e-130">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2441e-131">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2441e-132">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="2441e-133">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。</span><span class="sxs-lookup"><span data-stu-id="2441e-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="2441e-134">按兩下 **[在啟動時檢查最近的病毒和間諜軟體定義** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="2441e-135">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-135">Click **OK**.</span></span>

<span data-ttu-id="2441e-136">您也可以使用「群組原則」、「PowerShell」或「WMI」，設定 Microsoft Defender 防毒軟體在啟動時檢查是否有更新，甚至是不執行。</span><span class="sxs-lookup"><span data-stu-id="2441e-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="2441e-137">Microsoft Defender 防毒軟體不存在時，使用群組原則下載更新</span><span class="sxs-lookup"><span data-stu-id="2441e-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="2441e-138">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2441e-139">使用 **群組原則管理編輯器**，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2441e-140">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="2441e-141">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。</span><span class="sxs-lookup"><span data-stu-id="2441e-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="2441e-142">按兩下 [ **啟動時啟動安全性智慧更新** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="2441e-143">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="2441e-144">在未出現 Microsoft Defender 防毒軟體時使用 PowerShell Cmdlet 下載更新</span><span class="sxs-lookup"><span data-stu-id="2441e-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="2441e-145">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2441e-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="2441e-146">如需詳細資訊，請參閱[use PowerShell Cmdlet to manage Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/index) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2441e-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="2441e-147">當 Microsoft Defender 防毒軟體不存在時，使用 Windows 管理指令 (WMI) 下載更新</span><span class="sxs-lookup"><span data-stu-id="2441e-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="2441e-148">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="2441e-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="2441e-149">如需詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="2441e-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="2441e-150">根據雲端提供的保護，允許特定變更的保護</span><span class="sxs-lookup"><span data-stu-id="2441e-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="2441e-151">Microsoft Defender AV 可根據雲端提供的保護，對其保護進行變更。</span><span class="sxs-lookup"><span data-stu-id="2441e-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="2441e-152">這類變更可能會發生在一般或排程的保護更新之外。</span><span class="sxs-lookup"><span data-stu-id="2441e-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="2441e-153">如果您已啟用雲端提供的保護，Microsoft Defender AV 會將可疑的檔案傳送至 Windows Defender 雲端。</span><span class="sxs-lookup"><span data-stu-id="2441e-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="2441e-154">如果雲端服務報告該檔案為惡意檔，且在最近的保護更新中偵測到該檔案，您可以使用群組原則來設定 Microsoft Defender AV，以自動接收該防護更新。</span><span class="sxs-lookup"><span data-stu-id="2441e-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="2441e-155">您也可以套用其他重要的保護更新。</span><span class="sxs-lookup"><span data-stu-id="2441e-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="2441e-156">使用群組原則，根據雲端提供的保護自動下載最近的更新</span><span class="sxs-lookup"><span data-stu-id="2441e-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="2441e-157">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2441e-158">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2441e-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2441e-159">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="2441e-160">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。</span><span class="sxs-lookup"><span data-stu-id="2441e-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="2441e-161">按兩下 [ **允許即時安全性智慧更新根據 MICROSOFT 地圖報告** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="2441e-162">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2441e-162">Then click **OK**.</span></span>

6. <span data-ttu-id="2441e-163">**允許通知以停用 MICROSOFT MAPS 的定義型報告** ，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2441e-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="2441e-164">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2441e-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2441e-165">**允許通知若停用以定義為基礎的報表** ，可讓 Microsoft MAPS 停用這些已知導致誤報的定義。</span><span class="sxs-lookup"><span data-stu-id="2441e-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="2441e-166">您必須將電腦設定為加入 Microsoft MAPS，此功能才能運作。</span><span class="sxs-lookup"><span data-stu-id="2441e-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="2441e-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2441e-167">See also</span></span>

- [<span data-ttu-id="2441e-168">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2441e-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2441e-169">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="2441e-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2441e-170">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="2441e-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2441e-171">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="2441e-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2441e-172">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="2441e-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2441e-173">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2441e-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)