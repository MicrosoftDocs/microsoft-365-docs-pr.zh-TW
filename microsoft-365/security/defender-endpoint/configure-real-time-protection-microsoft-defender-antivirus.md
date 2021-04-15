---
title: 啟用並設定 Microsoft Defender 防防毒保護功能
description: 啟用並設定 Microsoft Defender 防毒軟體即時保護功能，例如行為監控、啟發式及機器學習
keywords: 防毒程式，即時保護，rtp，機器教學，行為監控，試探法
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 807348fcbf3ad4ef9698b11b194d752d8038b4c9
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765104"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="f5f85-104">在群組原則中啟用和設定 Microsoft Defender 防病毒的 always on 防護</span><span class="sxs-lookup"><span data-stu-id="f5f85-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f5f85-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f5f85-105">**Applies to:**</span></span>

- [<span data-ttu-id="f5f85-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f5f85-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f5f85-107">Always on 防護包含即時保護、行為監控和試探法，以根據已知的可疑和惡意活動來識別惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="f5f85-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="f5f85-108">這些活動包括事件（例如，對現有檔案進行非正常變更的處理常式）、修改或建立自動啟動登錄機碼和啟動位置 (也稱為自動啟動擴充點，或 ASEPs) ，以及其他對檔案系統或檔結構所做的變更。</span><span class="sxs-lookup"><span data-stu-id="f5f85-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="f5f85-109">啟用並設定群組原則中的 always on 保護</span><span class="sxs-lookup"><span data-stu-id="f5f85-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="f5f85-110">您可以使用 **本機組策略編輯器** ，啟用並設定 Microsoft Defender 防病毒永遠開啟防護設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="f5f85-111">啟用和設定 always on 保護：</span><span class="sxs-lookup"><span data-stu-id="f5f85-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="f5f85-112">開啟 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="f5f85-113">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="f5f85-113">To do this:</span></span>  

    1. <span data-ttu-id="f5f85-114">在您的 Windows 10 工作列搜尋方塊中，輸入 **gpedit.msc**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="f5f85-115">在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![Gpedit.msc 工作列搜尋結果](images/gpedit-search.png)

2. <span data-ttu-id="f5f85-117">在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦** 設定] 系統管理範本的樹狀目錄，以進行  >    >    >  **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="f5f85-118">設定 Microsoft Defender 防毒程式的反惡意程式碼服務原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="f5f85-119">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="f5f85-119">To do this:</span></span>  

    1. <span data-ttu-id="f5f85-120">在右側的 [ **Microsoft Defender 防病毒** 程式詳細資料] 窗格中，按兩下下清單格中所指定的原則設定：</span><span class="sxs-lookup"><span data-stu-id="f5f85-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="f5f85-121">設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-121">Setting</span></span> | <span data-ttu-id="f5f85-122">描述</span><span class="sxs-lookup"><span data-stu-id="f5f85-122">Description</span></span> | <span data-ttu-id="f5f85-123">預設設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="f5f85-124">允許反惡意程式碼服務以一般優先順序啟動</span><span class="sxs-lookup"><span data-stu-id="f5f85-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="f5f85-125">您可以降低 Microsoft Defender 防病毒引擎的優先順序，這在您想要讓啟動程式盡可能精益的輕型部署中非常有用。</span><span class="sxs-lookup"><span data-stu-id="f5f85-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="f5f85-126">這可能會影響端點的保護。</span><span class="sxs-lookup"><span data-stu-id="f5f85-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="f5f85-127">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-127">Enabled</span></span>
       | <span data-ttu-id="f5f85-128">允許反惡意程式碼服務持續保持執行狀態</span><span class="sxs-lookup"><span data-stu-id="f5f85-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="f5f85-129">如果已停用保護更新，您可以設定 Microsoft Defender 防毒軟體仍可執行。</span><span class="sxs-lookup"><span data-stu-id="f5f85-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="f5f85-130">這會降低對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="f5f85-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="f5f85-131">已停用</span><span class="sxs-lookup"><span data-stu-id="f5f85-131">Disabled</span></span> |
    
    1. <span data-ttu-id="f5f85-132">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="f5f85-133">針對表格中的每個設定，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="f5f85-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="f5f85-134">設定 Microsoft Defender 防病毒即時保護原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="f5f85-135">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="f5f85-135">To do this:</span></span>

    1. <span data-ttu-id="f5f85-136">在 [ **Microsoft Defender 防病毒** 程式詳細資料] 窗格中，按兩下 [ **即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="f5f85-137">或者，在左窗格上的 **Microsoft Defender 防病毒** 樹狀目錄中，按一下 [ **即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="f5f85-138">在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下下表所指定的原則設定：</span><span class="sxs-lookup"><span data-stu-id="f5f85-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="f5f85-139">設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-139">Setting</span></span> | <span data-ttu-id="f5f85-140">描述</span><span class="sxs-lookup"><span data-stu-id="f5f85-140">Description</span></span> | <span data-ttu-id="f5f85-141">預設設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="f5f85-142">開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="f5f85-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="f5f85-143">AV 引擎會監視檔案處理常式、檔案和登錄變更，以及終結點上的其他事件，以取得可疑和已知的惡意活動。</span><span class="sxs-lookup"><span data-stu-id="f5f85-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="f5f85-144">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-144">Enabled</span></span> |
       | <span data-ttu-id="f5f85-145">掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="f5f85-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="f5f85-146">會自動掃描下載的檔案和附件。</span><span class="sxs-lookup"><span data-stu-id="f5f85-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="f5f85-147">這除了 Windows Defender SmartScreen 篩選器以外，還會在下載之前和下載期間掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="f5f85-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="f5f85-148">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-148">Enabled</span></span> |
       | <span data-ttu-id="f5f85-149">監視電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="f5f85-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="f5f85-150">Microsoft Defender 防病毒引擎會記下所做的任何檔案變更，以 (檔案寫入作業，例如移動、複製或修改) 以及已開啟或執行的一般程式活動 (程式，而且會導致其他程式執行) 。</span><span class="sxs-lookup"><span data-stu-id="f5f85-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="f5f85-151">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-151">Enabled</span></span> |
       | <span data-ttu-id="f5f85-152">開啟原始大量寫入通知</span><span class="sxs-lookup"><span data-stu-id="f5f85-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="f5f85-153">有關原始磁片區寫入的資訊會透過行為監控進行分析。</span><span class="sxs-lookup"><span data-stu-id="f5f85-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="f5f85-154">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-154">Enabled</span></span> |
       | <span data-ttu-id="f5f85-155">在啟用即時保護時開啟處理常式掃描</span><span class="sxs-lookup"><span data-stu-id="f5f85-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="f5f85-156">您可以個別啟用 Microsoft Defender 防病毒引擎，以掃描正在執行的程式，以進行可疑的修改或行為。</span><span class="sxs-lookup"><span data-stu-id="f5f85-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="f5f85-157">如果您暫時停用即時保護，且想要自動掃描已停用的處理常式，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="f5f85-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="f5f85-158">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-158">Enabled</span></span> |
       | <span data-ttu-id="f5f85-159">定義要掃描的下載檔案和附件大小上限</span><span class="sxs-lookup"><span data-stu-id="f5f85-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="f5f85-160">您可以定義大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="f5f85-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="f5f85-161">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-161">Enabled</span></span> |
       | <span data-ttu-id="f5f85-162">設定本機設定超越開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="f5f85-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="f5f85-163">設定本機覆寫以設定行為監控的設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="f5f85-164">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f5f85-165">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="f5f85-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f5f85-166">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f5f85-167">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-167">Enabled</span></span> |
       | <span data-ttu-id="f5f85-168">設定本機設定覆寫以掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="f5f85-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="f5f85-169">設定本機覆寫以設定掃描所有已下載檔案和附件的設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="f5f85-170">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f5f85-171">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="f5f85-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f5f85-172">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f5f85-173">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-173">Enabled</span></span> |
       | <span data-ttu-id="f5f85-174">設定本機設定覆寫以監控電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="f5f85-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="f5f85-175">設定本機覆寫，以監視電腦上的檔案和程式活動。</span><span class="sxs-lookup"><span data-stu-id="f5f85-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="f5f85-176">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f5f85-177">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="f5f85-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f5f85-178">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f5f85-179">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-179">Enabled</span></span> |
       | <span data-ttu-id="f5f85-180">設定本機設定覆寫以開啟即時保護</span><span class="sxs-lookup"><span data-stu-id="f5f85-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="f5f85-181">設定本機覆寫設定，以開啟即時保護。</span><span class="sxs-lookup"><span data-stu-id="f5f85-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="f5f85-182">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f5f85-183">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="f5f85-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f5f85-184">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f5f85-185">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-185">Enabled</span></span> |
       | <span data-ttu-id="f5f85-186">設定針對內送和外寄檔案活動進行監視的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="f5f85-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="f5f85-187">設定本機覆寫，以監視傳入和傳出檔案活動的監視。</span><span class="sxs-lookup"><span data-stu-id="f5f85-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="f5f85-188">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f5f85-189">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="f5f85-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f5f85-190">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="f5f85-191">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-191">Enabled</span></span> |
       | <span data-ttu-id="f5f85-192">設定對內送和外寄檔案和程式活動的監控</span><span class="sxs-lookup"><span data-stu-id="f5f85-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="f5f85-193">指定監視是否應該發生在內送、撥出、兩者或兩者的方向。</span><span class="sxs-lookup"><span data-stu-id="f5f85-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="f5f85-194">這適用于您已定義特定伺服器或伺服器角色的 Windows Server 安裝，只會在一個方向上看到大量的檔案變更，且您想要提升網路效能。</span><span class="sxs-lookup"><span data-stu-id="f5f85-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="f5f85-195">完全更新的端點 (和伺服器) 在網路上，不論檔變更的數目或方向，都只會對效能造成影響。</span><span class="sxs-lookup"><span data-stu-id="f5f85-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="f5f85-196">已啟用兩個方向 () </span><span class="sxs-lookup"><span data-stu-id="f5f85-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="f5f85-197">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="f5f85-198">針對表格中的每個設定，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="f5f85-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="f5f85-199">設定 [Microsoft Defender 防病毒掃描原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="f5f85-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="f5f85-200">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="f5f85-200">To do this:</span></span>  

    1. <span data-ttu-id="f5f85-201">在左窗格的 [ **Microsoft Defender 防病毒** 樹狀目錄] 中，按一下 [ **掃描**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender 防病毒掃描選項](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="f5f85-203">在右側的 [ **掃描** 詳細資料] 窗格中，按兩下下清單格所指定的原則設定：</span><span class="sxs-lookup"><span data-stu-id="f5f85-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="f5f85-204">設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-204">Setting</span></span> | <span data-ttu-id="f5f85-205">描述</span><span class="sxs-lookup"><span data-stu-id="f5f85-205">Description</span></span> | <span data-ttu-id="f5f85-206">預設設定</span><span class="sxs-lookup"><span data-stu-id="f5f85-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="f5f85-207">開啟試探法</span><span class="sxs-lookup"><span data-stu-id="f5f85-207">Turn on heuristics</span></span> | <span data-ttu-id="f5f85-208">啟發式防護會在 Microsoft Defender 防病毒引擎要求偵測活動之前停用或封鎖可疑活動。</span><span class="sxs-lookup"><span data-stu-id="f5f85-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="f5f85-209">Enabled</span><span class="sxs-lookup"><span data-stu-id="f5f85-209">Enabled</span></span> |

    1. <span data-ttu-id="f5f85-210">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="f5f85-211">關閉 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="f5f85-212">停用群組原則中的即時保護</span><span class="sxs-lookup"><span data-stu-id="f5f85-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="f5f85-213">停用即時保護可大幅減少對端點的保護，所以不建議您這樣做。</span><span class="sxs-lookup"><span data-stu-id="f5f85-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="f5f85-214">預設會啟用主要即時保護功能，但您可以使用 [ **本機組策略編輯器**] 加以停用。</span><span class="sxs-lookup"><span data-stu-id="f5f85-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="f5f85-215">若要停用群組原則中的即時保護：</span><span class="sxs-lookup"><span data-stu-id="f5f85-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="f5f85-216">開啟 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="f5f85-217">在您的 Windows 10 工作列搜尋方塊中，輸入 **gpedit.msc**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="f5f85-218">在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="f5f85-219">在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦** 設定] 系統管理範本的樹狀目錄，以進行  >    >    >  **Microsoft Defender 防病毒**  >  **即時保護**。</span><span class="sxs-lookup"><span data-stu-id="f5f85-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="f5f85-220">在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下 [ **關閉即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![關閉即時保護](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="f5f85-222">在 [ **關閉即時保護** 設定] 視窗中，將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![關閉即時保護啟用](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="f5f85-224">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-224">Click **OK**.</span></span>

6. <span data-ttu-id="f5f85-225">關閉 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="f5f85-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f5f85-226">相關文章</span><span class="sxs-lookup"><span data-stu-id="f5f85-226">Related articles</span></span>

- [<span data-ttu-id="f5f85-227">設定行為、啟發式和即時保護</span><span class="sxs-lookup"><span data-stu-id="f5f85-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f5f85-228">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="f5f85-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)