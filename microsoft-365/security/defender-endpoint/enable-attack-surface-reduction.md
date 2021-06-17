---
title: 啟用受攻擊面縮小規則
description: 啟用攻擊面減少 (ASR) 規則，保護您的裝置免受使用宏、腳本及一般插入技術的攻擊。
keywords: 攻擊面降減，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，啟用，開啟
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: b4040a60e59f3256b69f90d33af6f7543e50784e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984793"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="18aca-104">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="18aca-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="18aca-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="18aca-105">**Applies to:**</span></span>

- [<span data-ttu-id="18aca-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="18aca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="18aca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18aca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="18aca-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="18aca-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="18aca-109">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="18aca-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="18aca-110">[攻擊面減少規則](attack-surface-reduction.md) (ASR 規則) 協助防止惡意程式碼經常濫用裝置和網路遭到侵入的動作。</span><span class="sxs-lookup"><span data-stu-id="18aca-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="18aca-111">**需求** 您可以針對執行下列任何版本與 Windows 的裝置，設定攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="18aca-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="18aca-112">Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="18aca-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="18aca-113">Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="18aca-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="18aca-114">Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="18aca-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="18aca-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="18aca-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="18aca-116">雖然攻擊面降減規則不需要[Windows E5 授權](/windows/deployment/deploy-enterprise-licenses)，但如果您有 Windows E5，就會取得高級管理功能。</span><span class="sxs-lookup"><span data-stu-id="18aca-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="18aca-117">這些功能只能在 Windows E5 中包含用於[端點的](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)監控、分析和工作流程，以及[Microsoft 365 安全性中心](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)的報表和設定功能。</span><span class="sxs-lookup"><span data-stu-id="18aca-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="18aca-118">Windows Professional 或 Windows E3 授權無法使用這些高級功能;不過，如果您有這些授權，您可以使用「事件檢視器」和 Microsoft Defender 防毒軟體記錄檔，以查看攻擊面減少規則事件。</span><span class="sxs-lookup"><span data-stu-id="18aca-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="18aca-119">每個 ASR 規則都包含四個設定的其中一項：</span><span class="sxs-lookup"><span data-stu-id="18aca-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="18aca-120">**未設定**：停用 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="18aca-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="18aca-121">**封鎖**：啟用 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="18aca-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="18aca-122">**Audit**：評估 ASR 規則在啟用時會如何影響您的組織</span><span class="sxs-lookup"><span data-stu-id="18aca-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="18aca-123">**警告**：啟用 ASR 規則，但是允許使用者略過封鎖</span><span class="sxs-lookup"><span data-stu-id="18aca-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18aca-124">目前，當您在 Microsoft 端點管理員 (MEM) 中設定 asr 規則時，不支援三種 asr 規則的警告模式。</span><span class="sxs-lookup"><span data-stu-id="18aca-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="18aca-125">若要深入瞭解，請參閱 [不支援警告模式的案例](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="18aca-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="18aca-126">強烈建議使用具有 Windows E5 授權 (或類似授權 SKU) 的 ASR 規則，以利用[Microsoft Defender for](microsoft-defender-endpoint.md) endpoint (Defender for endpoint) 中提供的高級監控和報告功能。</span><span class="sxs-lookup"><span data-stu-id="18aca-126">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="18aca-127">不過，如果您有另一個授權（如 Windows Professional 或 Windows E3 未包含高級監控和報告功能），您可以在觸發 ASR 規則時，將您自己的監控和報告工具，放在每個端點上產生的事件之上 (例如，事件轉移) 。</span><span class="sxs-lookup"><span data-stu-id="18aca-127">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="18aca-128">若要深入瞭解 Windows 授權，請參閱[Windows 10 授權](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)並取得[Windows 10 的大量授權指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="18aca-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="18aca-129">您可以使用下列任何一種方法來啟用攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="18aca-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="18aca-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="18aca-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="18aca-131">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="18aca-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="18aca-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="18aca-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="18aca-133">群組原則</span><span class="sxs-lookup"><span data-stu-id="18aca-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="18aca-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="18aca-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="18aca-135">建議使用 Enterprise 層級管理（如 Intune 或 Microsoft 端點管理員）。</span><span class="sxs-lookup"><span data-stu-id="18aca-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="18aca-136">Enterprise 層級管理將覆寫任何衝突的群組原則或啟動時 PowerShell 設定。</span><span class="sxs-lookup"><span data-stu-id="18aca-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="18aca-137">從 ASR 規則中排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="18aca-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="18aca-138">您可以將檔案和資料夾排除在大多數攻擊面降低規則之外進行評估。</span><span class="sxs-lookup"><span data-stu-id="18aca-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="18aca-139">這表示即使 ASR 規則判斷的檔案或資料夾包含惡意行為，也不會封鎖該檔案執行。</span><span class="sxs-lookup"><span data-stu-id="18aca-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="18aca-140">這可能會允許不安全的檔案執行並感染您的裝置。</span><span class="sxs-lookup"><span data-stu-id="18aca-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="18aca-141">您也可以透過允許指定的 Defender for Endpoint file 和憑證指示器，排除從觸發憑證和檔案雜湊的 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="18aca-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="18aca-142"> (請參閱 [管理指示器](manage-indicators.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="18aca-142">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18aca-143">排除檔案或資料夾可能會大大降低 ASR 規則所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="18aca-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="18aca-144">將會允許執行排除的檔案，而且不會記錄任何報表或事件。</span><span class="sxs-lookup"><span data-stu-id="18aca-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="18aca-145">如果 ASR 規則偵測到您認為不應該偵測到的檔案，您應該 [先使用審計模式來測試規則](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="18aca-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="18aca-146">您可以指定個別的檔案或資料夾 (使用資料夾路徑或完全限定資源名稱) ，但您無法指定要套用排除的規則。</span><span class="sxs-lookup"><span data-stu-id="18aca-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="18aca-147">只有在已排除的應用程式或服務啟動時，才會套用排除。</span><span class="sxs-lookup"><span data-stu-id="18aca-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="18aca-148">例如，如果您為已在執行的更新服務新增排除，更新服務會繼續觸發事件，直到停止並重新啟動服務為止。</span><span class="sxs-lookup"><span data-stu-id="18aca-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="18aca-149">ASR 規則支援環境變數和萬用字元。</span><span class="sxs-lookup"><span data-stu-id="18aca-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="18aca-150">如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="18aca-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="18aca-151">下列啟用 ASR 規則的套裝程式括如何排除檔案和資料夾的指示。</span><span class="sxs-lookup"><span data-stu-id="18aca-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="18aca-152">Intune</span><span class="sxs-lookup"><span data-stu-id="18aca-152">Intune</span></span>

1. <span data-ttu-id="18aca-153">選取 [**裝置** 設定  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="18aca-154">選擇現有的 endpoint protection 設定檔，或建立一個新的 endpoint protection 設定檔。</span><span class="sxs-lookup"><span data-stu-id="18aca-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="18aca-155">若要建立新的設定檔，請選取 [ **建立設定檔** ]，然後輸入此設定檔的資訊。</span><span class="sxs-lookup"><span data-stu-id="18aca-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="18aca-156">在 [ **配置檔案類型**] 中，選取 [ **Endpoint protection**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="18aca-157">如果您已選取現有的設定檔，請選取 [**屬性**]，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="18aca-158">在 [ **Endpoint protection** ] 窗格中，選取 [ **Windows Defender Exploit Guard**]，然後選取 [**攻擊面減少**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="18aca-159">針對每個 ASR 規則選取所需的設定。</span><span class="sxs-lookup"><span data-stu-id="18aca-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="18aca-160">在 [ **攻擊面減少例外** 狀況] 底下，輸入個別的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="18aca-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="18aca-161">您也可以選取 [匯入 **]，匯** 入包含要從 ASR 規則排除的檔案和資料夾的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="18aca-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="18aca-162">CSV 檔案中的每一行都應該格式化如下：</span><span class="sxs-lookup"><span data-stu-id="18aca-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="18aca-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="18aca-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="18aca-164">在三個設定窗格上選取 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="18aca-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="18aca-165">如果您要建立新的 endpoint protection 檔案，請選取 [ **建立** ]，如果您要編輯現有的 endpoint protection 檔案，請選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="18aca-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="18aca-166">Mem</span><span class="sxs-lookup"><span data-stu-id="18aca-166">MEM</span></span>

<span data-ttu-id="18aca-167">您可以使用 Microsoft 端點管理員 (MEM) OMA URI 來設定自訂的 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="18aca-167">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="18aca-168">下列程式會使用此範例的規則 [封鎖濫用已利用漏洞的簽章驅動程式](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) 。</span><span class="sxs-lookup"><span data-stu-id="18aca-168">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="18aca-169">開啟 Microsoft 端點管理員 (MEM) 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="18aca-169">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="18aca-170">在 [ **主** ] 功能表中，按一下 [  **裝置**]，選取 [ **設定檔**]，然後按一下 [ **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-170">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-171">![MEM 建立設定檔](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-171">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="18aca-172">在 [ **建立設定檔**] 的下列兩個下拉式清單中，選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="18aca-172">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="18aca-173">在 [**平臺**] 中，選取 [ **Windows 10 和更新版本**]</span><span class="sxs-lookup"><span data-stu-id="18aca-173">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="18aca-174">在 [ **配置檔案類型**] 中，選取 **範本**</span><span class="sxs-lookup"><span data-stu-id="18aca-174">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="18aca-175">選取 [ **自訂**]，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-175">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-176">![MEM 規則配置檔案屬性](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-176">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="18aca-177">自訂範本工具隨即開啟至步驟 **1 基礎**。</span><span class="sxs-lookup"><span data-stu-id="18aca-177">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="18aca-178">在 [ **1 基礎**] 的 [ **名稱**] 中，輸入範本的名稱，然後在 [ **描述** ] 中輸入 (選用) 的描述。</span><span class="sxs-lookup"><span data-stu-id="18aca-178">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-179">![MEM 基本屬性](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-179">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="18aca-180">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-180">Click **Next**.</span></span> <span data-ttu-id="18aca-181">步驟 **2 設定設定** 隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="18aca-181">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="18aca-182">若為 OMA-URI 設定，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-182">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="18aca-183">現在會顯示兩個選項： [ **新增** ] 和 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-183">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-184">![記憶體配置設定](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-184">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="18aca-185">再按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="18aca-185">Click **Add** again.</span></span> <span data-ttu-id="18aca-186">[**新增列 OMA URI] 設定** 隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="18aca-186">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="18aca-187">在 [ **新增列**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="18aca-187">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="18aca-188">在 [ **名稱**] 中，輸入規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="18aca-188">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="18aca-189">在 [ **描述**] 中，輸入簡短描述。</span><span class="sxs-lookup"><span data-stu-id="18aca-189">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="18aca-190">在 **OMA uri** 中，輸入或貼上所要新增之規則的特定 oma-uri 連結。</span><span class="sxs-lookup"><span data-stu-id="18aca-190">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="18aca-191">在 [ **資料類型**] 中，選取 **字串**。</span><span class="sxs-lookup"><span data-stu-id="18aca-191">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="18aca-192">在 [ **值**] 中，輸入或貼上 guid 值， \= 不含空格的 sign 和 State 值 (_GUID = StateValue_) 。</span><span class="sxs-lookup"><span data-stu-id="18aca-192">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="18aca-193">其中： {0：停用 (停用 ASR rule) }，{1：封鎖 (啟用 ASR 規則) }，{2： Audit (評估 ASR 規則會如何影響您的組織如果已啟用) }，{6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) }</span><span class="sxs-lookup"><span data-stu-id="18aca-193">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-194">![MEM 的 OMA URI 設定](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-194">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="18aca-195">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-195">Click **Save**.</span></span> <span data-ttu-id="18aca-196">**新增列** 關閉。</span><span class="sxs-lookup"><span data-stu-id="18aca-196">**Add Row** closes.</span></span> <span data-ttu-id="18aca-197">在 [ **自訂** **] 按 [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-197">In **Custom**, click **Next**.</span></span> <span data-ttu-id="18aca-198">在步驟 **3 範圍標記** 中，範圍標記是選用的。</span><span class="sxs-lookup"><span data-stu-id="18aca-198">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="18aca-199">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="18aca-199">Do one of the following:</span></span>

   - <span data-ttu-id="18aca-200">按一下 [ **選取範圍** 標籤]，選取 [範圍] 標籤 (選用) 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-200">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="18aca-201">或按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="18aca-201">Or click **Next**</span></span>

7. <span data-ttu-id="18aca-202">在 [步驟 **4 指派**] 中，在 [ **包含的群組** ] 中，對您想要套用此規則的群組進行-從下列選項中選取：</span><span class="sxs-lookup"><span data-stu-id="18aca-202">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="18aca-203">**新增群組**</span><span class="sxs-lookup"><span data-stu-id="18aca-203">**Add groups**</span></span>
   - <span data-ttu-id="18aca-204">**新增所有使用者**</span><span class="sxs-lookup"><span data-stu-id="18aca-204">**Add all users**</span></span>
   - <span data-ttu-id="18aca-205">**新增所有裝置**</span><span class="sxs-lookup"><span data-stu-id="18aca-205">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-206">![MEM 指派](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-206">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="18aca-207">在 [ **排除的群組**] 中，選取您要從此規則中排除的任何群組，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-207">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="18aca-208">在 [步驟5下列設定的 **適用性規則** ] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="18aca-208">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="18aca-209">在 [**規則**] 中，選取 [**指派設定檔為**]，或 [**不指派設定檔**]</span><span class="sxs-lookup"><span data-stu-id="18aca-209">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="18aca-210">在 [ **屬性**] 中，選取您要套用此規則的屬性</span><span class="sxs-lookup"><span data-stu-id="18aca-210">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="18aca-211">在 [ **值**] 中，輸入適用的值或值範圍</span><span class="sxs-lookup"><span data-stu-id="18aca-211">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18aca-212">![MEM 適用性規則](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-212">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="18aca-213">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-213">Click **Next**.</span></span> <span data-ttu-id="18aca-214">在步驟 **6 中，複查 + 建立**、複查您已選取並輸入的設定和資訊，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-214">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="18aca-215">![記憶審閱和建立](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="18aca-215">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="18aca-216">規則會在幾分鐘內生效和即時。</span><span class="sxs-lookup"><span data-stu-id="18aca-216">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="18aca-217">衝突處理：</span><span class="sxs-lookup"><span data-stu-id="18aca-217">Conflict handling:</span></span>
>
> <span data-ttu-id="18aca-218">如果您指派裝置兩個不同的 ASR 原則，處理衝突的方式就是已指派不同狀態的規則，不會就地進行衝突管理，且結果為錯誤。</span><span class="sxs-lookup"><span data-stu-id="18aca-218">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="18aca-219">非衝突的規則不會導致錯誤，而且會正確套用規則。</span><span class="sxs-lookup"><span data-stu-id="18aca-219">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="18aca-220">結果是套用第一個規則，後續的非衝突規則會合並到原則中。</span><span class="sxs-lookup"><span data-stu-id="18aca-220">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="18aca-221">Mdm</span><span class="sxs-lookup"><span data-stu-id="18aca-221">MDM</span></span>

<span data-ttu-id="18aca-222">使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service PROVIDER (CSP) 以個別啟用和設定每個規則的模式。</span><span class="sxs-lookup"><span data-stu-id="18aca-222">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="18aca-223">下列為參考資料範例，其使用 [的是 ASR 規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="18aca-223">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="18aca-224">在稽核模式中，啟用 (區塊) 、停用、警告或啟用的值包括：</span><span class="sxs-lookup"><span data-stu-id="18aca-224">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="18aca-225">0：停用 (停用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="18aca-225">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="18aca-226">1：封鎖 (啟用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="18aca-226">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="18aca-227">2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) </span><span class="sxs-lookup"><span data-stu-id="18aca-227">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="18aca-228">6：警告 (啟用 ASR 規則，但是允許使用者略過區塊) 。</span><span class="sxs-lookup"><span data-stu-id="18aca-228">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="18aca-229">警告模式現在可用於大部分的 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="18aca-229">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="18aca-230">使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。</span><span class="sxs-lookup"><span data-stu-id="18aca-230">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="18aca-231">範例：</span><span class="sxs-lookup"><span data-stu-id="18aca-231">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="18aca-232">請務必輸入不含空格的 OMA URI 值。</span><span class="sxs-lookup"><span data-stu-id="18aca-232">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="18aca-233">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="18aca-233">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="18aca-234">在 Microsoft Endpoint Configuration Manager 中，移至 **資產及規範**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**。</span><span class="sxs-lookup"><span data-stu-id="18aca-234">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="18aca-235">選取 [**首頁**  >  **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-235">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="18aca-236">輸入名稱和描述，選取 [ **攻擊面減少**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-236">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="18aca-237">選擇會封鎖或審核動作的規則，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-237">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="18aca-238">複查設定，然後選取 **[下一步]** 建立原則。</span><span class="sxs-lookup"><span data-stu-id="18aca-238">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="18aca-239">建立原則之後， **關閉**。</span><span class="sxs-lookup"><span data-stu-id="18aca-239">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="18aca-240">群組原則</span><span class="sxs-lookup"><span data-stu-id="18aca-240">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="18aca-241">如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體將會覆寫啟動時的任何衝突的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="18aca-241">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="18aca-242">在您的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-242">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="18aca-243">在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="18aca-243">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="18aca-244">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Microsoft Defender 惡意探索防護**  >  **攻擊面降減**。</span><span class="sxs-lookup"><span data-stu-id="18aca-244">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="18aca-245">選取 [ **設定攻擊面減少規則** ]，然後選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-245">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="18aca-246">然後，您可以在 [選項] 區段中，為每個規則設定個別的狀態。</span><span class="sxs-lookup"><span data-stu-id="18aca-246">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="18aca-247">選取 [ **顯示 ...** ]，然後在 [值 **名稱** ] 欄中輸入規則識別碼，並在 [ **值** ] 欄中輸入您選擇的狀態，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18aca-247">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="18aca-248">0：停用 (停用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="18aca-248">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="18aca-249">1：封鎖 (啟用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="18aca-249">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="18aca-250">2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) </span><span class="sxs-lookup"><span data-stu-id="18aca-250">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="18aca-251">6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) </span><span class="sxs-lookup"><span data-stu-id="18aca-251">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="群組原則中的 ASR 規則":::

5. <span data-ttu-id="18aca-253">若要從 ASR 規則中排除檔案和資料夾，請選取 [ **從攻擊面減少規則排除檔案和路徑** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-253">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="18aca-254">選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="18aca-254">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="18aca-255">在 [**值**] 欄中，為每個專案輸入 **0** 。</span><span class="sxs-lookup"><span data-stu-id="18aca-255">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="18aca-256">請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。</span><span class="sxs-lookup"><span data-stu-id="18aca-256">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="18aca-257">PowerShell</span><span class="sxs-lookup"><span data-stu-id="18aca-257">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="18aca-258">如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體會在啟動時覆寫所有衝突的 PowerShell 設定。</span><span class="sxs-lookup"><span data-stu-id="18aca-258">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="18aca-259">若要讓使用者使用 PowerShell 定義值，請在管理平臺中使用規則的「使用者定義」選項。</span><span class="sxs-lookup"><span data-stu-id="18aca-259">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="18aca-260">在 [開始] 功能表中輸入 **powershell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="18aca-260">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="18aca-261">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-261">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="18aca-262">若要在稽核模式中啟用 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-262">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="18aca-263">若要在警告模式中啟用 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-263">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="18aca-264">若要啟用利用漏洞簽名驅動程式的 ASR 封鎖濫用，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-264">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="18aca-265">若要關閉 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-265">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="18aca-266">您必須個別指定每個規則的狀態，但是您可以將規則和狀態組合成以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="18aca-266">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="18aca-267">在下列範例中，會啟用前兩個規則，將會停用第三個規則，且會在審計模式中啟用第四個規則：</span><span class="sxs-lookup"><span data-stu-id="18aca-267">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="18aca-268">您也可以使用 `Add-MpPreference` PowerShell 謂詞將新的規則新增至現有清單。</span><span class="sxs-lookup"><span data-stu-id="18aca-268">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="18aca-269">`Set-MpPreference` 永遠會覆寫現有的規則集。</span><span class="sxs-lookup"><span data-stu-id="18aca-269">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="18aca-270">如果您想要新增至現有的集，請 `Add-MpPreference` 改用。</span><span class="sxs-lookup"><span data-stu-id="18aca-270">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="18aca-271">您可以使用來取得規則及其目前狀態的清單 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="18aca-271">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="18aca-272">若要從 ASR 規則中排除檔案和資料夾，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18aca-272">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="18aca-273">繼續使用將 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 更多檔案和資料夾新增至清單。</span><span class="sxs-lookup"><span data-stu-id="18aca-273">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="18aca-274">用於 `Add-MpPreference` 附加或新增應用程式至清單。</span><span class="sxs-lookup"><span data-stu-id="18aca-274">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="18aca-275">使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="18aca-275">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="18aca-276">相關文章</span><span class="sxs-lookup"><span data-stu-id="18aca-276">Related articles</span></span>

- [<span data-ttu-id="18aca-277">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="18aca-277">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="18aca-278">評估攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="18aca-278">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="18aca-279">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="18aca-279">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
