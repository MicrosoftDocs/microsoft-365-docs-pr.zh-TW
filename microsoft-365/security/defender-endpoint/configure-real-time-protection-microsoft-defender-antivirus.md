---
title: 啟用和設定 Microsoft Defender 防毒軟體保護功能
description: 啟用和設定 Microsoft Defender 防毒軟體即時保護功能，例如行為監控、啟發式及機器學習）
keywords: 防毒程式，即時保護，rtp，機器教學，行為監控，試探法
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
ms.date: 12/16/2019
manager: dansimp
ms.custom: nextgen
ms.openlocfilehash: 313646c69417082583b27bcfbab540131043ce76
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926664"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="329b9-104">在群組原則中啟用和設定 Microsoft Defender 防毒軟體一律開啟保護</span><span class="sxs-lookup"><span data-stu-id="329b9-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>


<span data-ttu-id="329b9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="329b9-105">**Applies to:**</span></span>

- [<span data-ttu-id="329b9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="329b9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="329b9-107">Always on 防護包含即時保護、行為監控和試探法，以根據已知的可疑和惡意活動來識別惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="329b9-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="329b9-108">這些活動包括事件（例如，對現有檔案進行非正常變更的處理常式）、修改或建立自動啟動登錄機碼和啟動位置 (也稱為自動啟動擴充點，或 ASEPs) ，以及其他對檔案系統或檔結構所做的變更。</span><span class="sxs-lookup"><span data-stu-id="329b9-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="329b9-109">啟用並設定群組原則中的 always on 保護</span><span class="sxs-lookup"><span data-stu-id="329b9-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="329b9-110">您可以使用 **本機組策略編輯器**，啟用和設定 Microsoft Defender 防毒軟體 always on 防護設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="329b9-111">啟用和設定 always on 保護：</span><span class="sxs-lookup"><span data-stu-id="329b9-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="329b9-112">開啟 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="329b9-113">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="329b9-113">To do this:</span></span>  

    1. <span data-ttu-id="329b9-114">在 [Windows 10 的工作列] 搜尋方塊中，輸入 **gpedit.msc**。</span><span class="sxs-lookup"><span data-stu-id="329b9-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="329b9-115">在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。</span><span class="sxs-lookup"><span data-stu-id="329b9-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![Gpedit.msc 工作列搜尋結果](images/gpedit-search.png)

2. <span data-ttu-id="329b9-117">在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體** 的樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="329b9-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="329b9-118">設定 Microsoft Defender 防毒軟體的反惡意程式碼服務原則設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="329b9-119">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="329b9-119">To do this:</span></span>  

    1. <span data-ttu-id="329b9-120">在右側的 [ **Microsoft Defender 防毒軟體** 詳細資料] 窗格中，按兩下 [原則] 設定，如下表所指定：</span><span class="sxs-lookup"><span data-stu-id="329b9-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="329b9-121">設定</span><span class="sxs-lookup"><span data-stu-id="329b9-121">Setting</span></span> | <span data-ttu-id="329b9-122">描述</span><span class="sxs-lookup"><span data-stu-id="329b9-122">Description</span></span> | <span data-ttu-id="329b9-123">預設設定</span><span class="sxs-lookup"><span data-stu-id="329b9-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="329b9-124">允許反惡意程式碼服務以一般優先順序啟動</span><span class="sxs-lookup"><span data-stu-id="329b9-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="329b9-125">您可以降低 Microsoft Defender 防毒軟體引擎的優先順序，這在您想要讓啟動程式盡可能精益的輕量部署中非常有用。</span><span class="sxs-lookup"><span data-stu-id="329b9-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="329b9-126">這可能會影響端點的保護。</span><span class="sxs-lookup"><span data-stu-id="329b9-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="329b9-127">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-127">Enabled</span></span>
       | <span data-ttu-id="329b9-128">允許反惡意程式碼服務持續保持執行狀態</span><span class="sxs-lookup"><span data-stu-id="329b9-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="329b9-129">如果已停用保護更新，您可以將 Microsoft Defender 防毒軟體設定為仍然執行。</span><span class="sxs-lookup"><span data-stu-id="329b9-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="329b9-130">這會降低對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="329b9-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="329b9-131">停用</span><span class="sxs-lookup"><span data-stu-id="329b9-131">Disabled</span></span> |
    
    1. <span data-ttu-id="329b9-132">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="329b9-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="329b9-133">針對表格中的每個設定，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="329b9-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="329b9-134">設定 Microsoft Defender 防毒軟體即時保護原則設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="329b9-135">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="329b9-135">To do this:</span></span>

    1. <span data-ttu-id="329b9-136">在 [ **Microsoft Defender 防毒軟體** 詳細資料] 窗格中，按兩下 [**即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="329b9-137">或者，在左窗格的 **Microsoft Defender 防毒軟體** 樹狀目錄中，按一下 [**即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="329b9-138">在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下下表所指定的原則設定：</span><span class="sxs-lookup"><span data-stu-id="329b9-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="329b9-139">設定</span><span class="sxs-lookup"><span data-stu-id="329b9-139">Setting</span></span> | <span data-ttu-id="329b9-140">描述</span><span class="sxs-lookup"><span data-stu-id="329b9-140">Description</span></span> | <span data-ttu-id="329b9-141">預設設定</span><span class="sxs-lookup"><span data-stu-id="329b9-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="329b9-142">開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="329b9-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="329b9-143">AV 引擎會監視檔案處理常式、檔案和登錄變更，以及終結點上的其他事件，以取得可疑和已知的惡意活動。</span><span class="sxs-lookup"><span data-stu-id="329b9-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="329b9-144">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-144">Enabled</span></span> |
       | <span data-ttu-id="329b9-145">掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="329b9-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="329b9-146">會自動掃描下載的檔案和附件。</span><span class="sxs-lookup"><span data-stu-id="329b9-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="329b9-147">這項作業除了 Windows Defender SmartScreen 篩選之外，它會在下載之前和下載期間掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="329b9-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="329b9-148">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-148">Enabled</span></span> |
       | <span data-ttu-id="329b9-149">監視電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="329b9-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="329b9-150">Microsoft Defender 防毒軟體引擎會記下所 (做的任何檔案變更，例如移動、副本或) 修改， (已開啟或執行的一般程式活動，以及導致其他程式執行) 的程式。</span><span class="sxs-lookup"><span data-stu-id="329b9-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="329b9-151">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-151">Enabled</span></span> |
       | <span data-ttu-id="329b9-152">開啟原始大量寫入通知</span><span class="sxs-lookup"><span data-stu-id="329b9-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="329b9-153">有關原始磁片區寫入的資訊會透過行為監控進行分析。</span><span class="sxs-lookup"><span data-stu-id="329b9-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="329b9-154">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-154">Enabled</span></span> |
       | <span data-ttu-id="329b9-155">在啟用即時保護時開啟處理常式掃描</span><span class="sxs-lookup"><span data-stu-id="329b9-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="329b9-156">您可以個別啟用 Microsoft Defender 防毒軟體引擎，以掃描正在執行的程式，以進行可疑的修改或行為。</span><span class="sxs-lookup"><span data-stu-id="329b9-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="329b9-157">如果您暫時停用即時保護，且想要自動掃描已停用的處理常式，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="329b9-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="329b9-158">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-158">Enabled</span></span> |
       | <span data-ttu-id="329b9-159">定義要掃描的下載檔案和附件大小上限</span><span class="sxs-lookup"><span data-stu-id="329b9-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="329b9-160">您可以定義大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="329b9-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="329b9-161">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-161">Enabled</span></span> |
       | <span data-ttu-id="329b9-162">設定本機設定超越開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="329b9-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="329b9-163">設定本機覆寫以設定行為監控的設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="329b9-164">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="329b9-165">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="329b9-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="329b9-166">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="329b9-167">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-167">Enabled</span></span> |
       | <span data-ttu-id="329b9-168">設定本機設定覆寫以掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="329b9-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="329b9-169">設定本機覆寫以設定掃描所有已下載檔案和附件的設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="329b9-170">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="329b9-171">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="329b9-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="329b9-172">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="329b9-173">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-173">Enabled</span></span> |
       | <span data-ttu-id="329b9-174">設定本機設定覆寫以監控電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="329b9-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="329b9-175">設定本機覆寫，以監視電腦上的檔案和程式活動。</span><span class="sxs-lookup"><span data-stu-id="329b9-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="329b9-176">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="329b9-177">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="329b9-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="329b9-178">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="329b9-179">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-179">Enabled</span></span> |
       | <span data-ttu-id="329b9-180">設定本機設定覆寫以開啟即時保護</span><span class="sxs-lookup"><span data-stu-id="329b9-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="329b9-181">設定本機覆寫設定，以開啟即時保護。</span><span class="sxs-lookup"><span data-stu-id="329b9-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="329b9-182">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="329b9-183">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="329b9-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="329b9-184">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="329b9-185">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-185">Enabled</span></span> |
       | <span data-ttu-id="329b9-186">設定針對內送和外寄檔案活動進行監視的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="329b9-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="329b9-187">設定本機覆寫，以監視傳入和傳出檔案活動的監視。</span><span class="sxs-lookup"><span data-stu-id="329b9-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="329b9-188">此設定只可由「群組原則」設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="329b9-189">如果您啟用此設定，則本機偏好設定會優先于「群組原則」。</span><span class="sxs-lookup"><span data-stu-id="329b9-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="329b9-190">如果您停用或未設定此設定，群組原則將優先于本機偏好設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="329b9-191">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-191">Enabled</span></span> |
       | <span data-ttu-id="329b9-192">設定對內送和外寄檔案和程式活動的監控</span><span class="sxs-lookup"><span data-stu-id="329b9-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="329b9-193">指定監視是否應該發生在內送、撥出、兩者或兩者的方向。</span><span class="sxs-lookup"><span data-stu-id="329b9-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="329b9-194">這適用于您已定義特定伺服器或伺服器角色的 Windows 伺服器安裝，只會在一個方向上看到大量的檔案變更，且您想要提升網路效能。</span><span class="sxs-lookup"><span data-stu-id="329b9-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="329b9-195">完全更新的端點 (和伺服器) 在網路上，不論檔變更的數目或方向，都只會對效能造成影響。</span><span class="sxs-lookup"><span data-stu-id="329b9-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="329b9-196">已啟用兩個方向 () </span><span class="sxs-lookup"><span data-stu-id="329b9-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="329b9-197">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="329b9-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="329b9-198">針對表格中的每個設定，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="329b9-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="329b9-199">設定 Microsoft Defender 防毒軟體掃描原則設定。</span><span class="sxs-lookup"><span data-stu-id="329b9-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="329b9-200">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="329b9-200">To do this:</span></span>  

    1. <span data-ttu-id="329b9-201">在左窗格的 [ **Microsoft Defender 防毒軟體**] 樹狀目錄中，按一下 [**掃描**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender 防毒軟體掃描選項](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="329b9-203">在右側的 [ **掃描** 詳細資料] 窗格中，按兩下下清單格所指定的原則設定：</span><span class="sxs-lookup"><span data-stu-id="329b9-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="329b9-204">設定</span><span class="sxs-lookup"><span data-stu-id="329b9-204">Setting</span></span> | <span data-ttu-id="329b9-205">描述</span><span class="sxs-lookup"><span data-stu-id="329b9-205">Description</span></span> | <span data-ttu-id="329b9-206">預設設定</span><span class="sxs-lookup"><span data-stu-id="329b9-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="329b9-207">開啟試探法</span><span class="sxs-lookup"><span data-stu-id="329b9-207">Turn on heuristics</span></span> | <span data-ttu-id="329b9-208">啟發式防護會在要求 Microsoft Defender 防毒軟體引擎偵測活動之前停用或封鎖可疑活動。</span><span class="sxs-lookup"><span data-stu-id="329b9-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="329b9-209">啟用</span><span class="sxs-lookup"><span data-stu-id="329b9-209">Enabled</span></span> |

    1. <span data-ttu-id="329b9-210">設定適當的設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="329b9-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="329b9-211">關閉 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="329b9-212">停用群組原則中的即時保護</span><span class="sxs-lookup"><span data-stu-id="329b9-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="329b9-213">停用即時保護可大幅減少對端點的保護，所以不建議您這樣做。</span><span class="sxs-lookup"><span data-stu-id="329b9-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="329b9-214">預設會啟用主要即時保護功能，但您可以使用 [ **本機組策略編輯器**] 加以停用。</span><span class="sxs-lookup"><span data-stu-id="329b9-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="329b9-215">若要停用群組原則中的即時保護：</span><span class="sxs-lookup"><span data-stu-id="329b9-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="329b9-216">開啟 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="329b9-217">在 [Windows 10 的工作列] 搜尋方塊中，輸入 **gpedit.msc**。</span><span class="sxs-lookup"><span data-stu-id="329b9-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="329b9-218">在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。</span><span class="sxs-lookup"><span data-stu-id="329b9-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="329b9-219">在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **即時保護** 的樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="329b9-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="329b9-220">在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下 [ **關閉即時保護**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![關閉即時保護](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="329b9-222">在 [ **關閉即時保護** 設定] 視窗中，將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![關閉即時保護啟用](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="329b9-224">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="329b9-224">Click **OK**.</span></span>

6. <span data-ttu-id="329b9-225">關閉 [ **本機群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="329b9-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="329b9-226">相關文章</span><span class="sxs-lookup"><span data-stu-id="329b9-226">Related articles</span></span>

- [<span data-ttu-id="329b9-227">設定行為、啟發學習法和即時保護</span><span class="sxs-lookup"><span data-stu-id="329b9-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="329b9-228">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="329b9-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
