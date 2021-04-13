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
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689161"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="154d4-104">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="154d4-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="154d4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="154d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="154d4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="154d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="154d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="154d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="154d4-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="154d4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="154d4-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="154d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="154d4-110">[攻擊面減少規則](attack-surface-reduction.md) (ASR 規則) 協助防止惡意程式碼經常濫用裝置和網路遭到侵入的動作。</span><span class="sxs-lookup"><span data-stu-id="154d4-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="154d4-111">您可以為執行下列任何版本的 Windows 裝置設定 ASR 規則：</span><span class="sxs-lookup"><span data-stu-id="154d4-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="154d4-112">Windows 10 專業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="154d4-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="154d4-113">Windows 10 企業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="154d4-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="154d4-114">Windows Server， [版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="154d4-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="154d4-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="154d4-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="154d4-116">每個 ASR 規則都包含四個設定的其中一項：</span><span class="sxs-lookup"><span data-stu-id="154d4-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="154d4-117">**未設定**：停用 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="154d4-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="154d4-118">**封鎖**：啟用 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="154d4-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="154d4-119">**Audit**：評估 ASR 規則在啟用時會如何影響您的組織</span><span class="sxs-lookup"><span data-stu-id="154d4-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="154d4-120">**警告**：啟用 ASR 規則，但 alow 最終使用者以略過封鎖</span><span class="sxs-lookup"><span data-stu-id="154d4-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="154d4-121">目前，當您在 Microsoft 端點管理員 (MEM) 中設定 ASR 規則時，三種 ASR 規則不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="154d4-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="154d4-122">若要深入瞭解，請參閱 [不支援警告模式的案例](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="154d4-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="154d4-123">強烈建議您搭配 Windows E5 授權 (或類似授權 SKU) 使用 ASR 規則，以利用 [Microsoft defender for](https://docs.microsoft.com/windows/security/threat-protection) Endpoint (Defender for endpoint) 中可用的高級監控和報告功能。</span><span class="sxs-lookup"><span data-stu-id="154d4-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="154d4-124">不過，如果是其他授權（如 Windows Professional 或 E3）無法存取高級監控和報告功能，您可以在觸發 ASR 規則時，在每個端點上建立您自己的監控和報告工具，以在觸發 ASR 規則時產生 (例如，事件轉送) 。</span><span class="sxs-lookup"><span data-stu-id="154d4-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="154d4-125">若要深入瞭解 Windows 授權，請參閱 [windows 10 授權](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 並取得 [Windows 10 的大量授權指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="154d4-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="154d4-126">您可以使用下列任何一種方法來啟用攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="154d4-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="154d4-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="154d4-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="154d4-128">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="154d4-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="154d4-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="154d4-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="154d4-130">群組原則</span><span class="sxs-lookup"><span data-stu-id="154d4-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="154d4-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="154d4-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="154d4-132">建議使用企業層級管理（如 Intune 或 Microsoft 端點管理員）。</span><span class="sxs-lookup"><span data-stu-id="154d4-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="154d4-133">企業級管理將覆寫任何衝突的群組原則或啟動時 PowerShell 設定。</span><span class="sxs-lookup"><span data-stu-id="154d4-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="154d4-134">從 ASR 規則中排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="154d4-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="154d4-135">您可以將檔案和資料夾排除在大多數攻擊面降低規則之外進行評估。</span><span class="sxs-lookup"><span data-stu-id="154d4-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="154d4-136">這表示即使 ASR 規則判斷的檔案或資料夾包含惡意行為，也不會封鎖該檔案執行。</span><span class="sxs-lookup"><span data-stu-id="154d4-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="154d4-137">這可能會允許不安全的檔案執行並感染您的裝置。</span><span class="sxs-lookup"><span data-stu-id="154d4-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="154d4-138">您也可以透過允許指定的 Defender for Endpoint file 和憑證指示器，排除從觸發憑證和檔案雜湊的 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="154d4-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="154d4-139"> (請參閱 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。 ) </span><span class="sxs-lookup"><span data-stu-id="154d4-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="154d4-140">排除檔案或資料夾可能會大大降低 ASR 規則所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="154d4-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="154d4-141">將會允許執行排除的檔案，而且不會記錄任何報表或事件。</span><span class="sxs-lookup"><span data-stu-id="154d4-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="154d4-142">如果 ASR 規則偵測到您認為不應該偵測到的檔案，您應該 [先使用審計模式來測試規則](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="154d4-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="154d4-143">您可以指定個別的檔案或資料夾 (使用資料夾路徑或完全限定資源名稱) ，但您無法指定要套用排除的規則。</span><span class="sxs-lookup"><span data-stu-id="154d4-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="154d4-144">只有在已排除的應用程式或服務啟動時，才會套用排除。</span><span class="sxs-lookup"><span data-stu-id="154d4-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="154d4-145">例如，如果您為已在執行的更新服務新增排除，更新服務會繼續觸發事件，直到停止並重新啟動服務為止。</span><span class="sxs-lookup"><span data-stu-id="154d4-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="154d4-146">ASR 規則支援環境變數和萬用字元。</span><span class="sxs-lookup"><span data-stu-id="154d4-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="154d4-147">如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="154d4-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="154d4-148">下列啟用 ASR 規則的套裝程式括如何排除檔案和資料夾的指示。</span><span class="sxs-lookup"><span data-stu-id="154d4-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="154d4-149">Intune</span><span class="sxs-lookup"><span data-stu-id="154d4-149">Intune</span></span>

1. <span data-ttu-id="154d4-150">選取 [**裝置** 設定  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="154d4-151">選擇現有的 endpoint protection 設定檔，或建立一個新的 endpoint protection 設定檔。</span><span class="sxs-lookup"><span data-stu-id="154d4-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="154d4-152">若要建立新的設定檔，請選取 [ **建立設定檔** ]，然後輸入此設定檔的資訊。</span><span class="sxs-lookup"><span data-stu-id="154d4-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="154d4-153">在 [ **配置檔案類型**] 中，選取 [ **Endpoint protection**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="154d4-154">如果您已選取現有的設定檔，請選取 [ **屬性** ]，然後選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="154d4-155">在 [ **Endpoint protection** ] 窗格中，選取 [ **Windows Defender 利用防護**]，然後選取 [ **攻擊面減少**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="154d4-156">針對每個 ASR 規則選取所需的設定。</span><span class="sxs-lookup"><span data-stu-id="154d4-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="154d4-157">在 [ **攻擊面減少例外** 狀況] 底下，輸入個別的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="154d4-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="154d4-158">您也可以選取 [匯入 **]，匯** 入包含要從 ASR 規則排除的檔案和資料夾的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="154d4-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="154d4-159">CSV 檔案中的每一行都應該格式化如下：</span><span class="sxs-lookup"><span data-stu-id="154d4-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="154d4-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="154d4-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="154d4-161">在三個設定窗格上選取 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="154d4-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="154d4-162">如果您要建立新的 endpoint protection 檔案，請選取 [ **建立** ]，如果您要編輯現有的 endpoint protection 檔案，請選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="154d4-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="154d4-163">Mdm</span><span class="sxs-lookup"><span data-stu-id="154d4-163">MDM</span></span>

<span data-ttu-id="154d4-164">使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service PROVIDER (CSP) 以個別啟用和設定每個規則的模式。</span><span class="sxs-lookup"><span data-stu-id="154d4-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="154d4-165">下列為參考資料範例，其使用 [的是 ASR 規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="154d4-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="154d4-166">在稽核模式中，啟用 (區塊) 、停用、警告或啟用的值包括：</span><span class="sxs-lookup"><span data-stu-id="154d4-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="154d4-167">0：停用 (停用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="154d4-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="154d4-168">1：封鎖 (啟用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="154d4-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="154d4-169">2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) </span><span class="sxs-lookup"><span data-stu-id="154d4-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="154d4-170">6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) </span><span class="sxs-lookup"><span data-stu-id="154d4-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="154d4-171">使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。</span><span class="sxs-lookup"><span data-stu-id="154d4-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="154d4-172">範例：</span><span class="sxs-lookup"><span data-stu-id="154d4-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="154d4-173">請務必輸入不含空格的 OMA URI 值。</span><span class="sxs-lookup"><span data-stu-id="154d4-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="154d4-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="154d4-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="154d4-175">在 Microsoft 端點 Configuration Manager 中，移至 [**資產和合規性**  >  **端點防護**] 「  >  **Windows Defender 利用防護**」。</span><span class="sxs-lookup"><span data-stu-id="154d4-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="154d4-176">選取 [**首頁**  >  **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="154d4-177">輸入名稱和描述，選取 [ **攻擊面減少**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="154d4-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="154d4-178">選擇會封鎖或審核動作的規則，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="154d4-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="154d4-179">複查設定，然後選取 **[下一步]** 建立原則。</span><span class="sxs-lookup"><span data-stu-id="154d4-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="154d4-180">建立原則之後， **關閉**。</span><span class="sxs-lookup"><span data-stu-id="154d4-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="154d4-181">群組原則</span><span class="sxs-lookup"><span data-stu-id="154d4-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="154d4-182">如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體將會覆寫啟動時的任何衝突的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="154d4-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="154d4-183">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="154d4-184">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="154d4-185">將樹狀目錄展開為 **Windows 元件**  >  **microsoft defender 防病毒**  >  **microsoft defender 利用防護防護**  >  **攻擊面降減**。</span><span class="sxs-lookup"><span data-stu-id="154d4-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="154d4-186">選取 [ **設定攻擊面減少規則** ]，然後選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="154d4-187">然後，您可以在 [選項] 區段中，為每個規則設定個別的狀態。</span><span class="sxs-lookup"><span data-stu-id="154d4-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="154d4-188">選取 [ **顯示 ...** ]，然後在 [值 **名稱** ] 欄中輸入規則識別碼，並在 [ **值** ] 欄中輸入您選擇的狀態，如下所示：</span><span class="sxs-lookup"><span data-stu-id="154d4-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="154d4-189">0：停用 (停用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="154d4-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="154d4-190">1：封鎖 (啟用 ASR 規則) </span><span class="sxs-lookup"><span data-stu-id="154d4-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="154d4-191">2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) </span><span class="sxs-lookup"><span data-stu-id="154d4-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="154d4-192">6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) </span><span class="sxs-lookup"><span data-stu-id="154d4-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="群組原則中的 ASR 規則":::

5. <span data-ttu-id="154d4-194">若要從 ASR 規則中排除檔案和資料夾，請選取 [ **從攻擊面減少規則排除檔案和路徑** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="154d4-195">選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="154d4-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="154d4-196">在 [**值**] 欄中，為每個專案輸入 **0** 。</span><span class="sxs-lookup"><span data-stu-id="154d4-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="154d4-197">請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。</span><span class="sxs-lookup"><span data-stu-id="154d4-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="154d4-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="154d4-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="154d4-199">如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體會在啟動時覆寫所有衝突的 PowerShell 設定。</span><span class="sxs-lookup"><span data-stu-id="154d4-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="154d4-200">若要讓使用者使用 PowerShell 定義值，請在管理平臺中使用規則的「使用者定義」選項。</span><span class="sxs-lookup"><span data-stu-id="154d4-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="154d4-201">在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="154d4-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="154d4-202">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="154d4-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="154d4-203">若要在稽核模式中啟用 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="154d4-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="154d4-204">若要在警告模式中啟用 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="154d4-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="154d4-205">若要關閉 ASR 規則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="154d4-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="154d4-206">您必須個別指定每個規則的狀態，但是您可以將規則和狀態組合成以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="154d4-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="154d4-207">在下列範例中，會啟用前兩個規則，將會停用第三個規則，且會在審計模式中啟用第四個規則：</span><span class="sxs-lookup"><span data-stu-id="154d4-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="154d4-208">您也可以使用 `Add-MpPreference` PowerShell 謂詞將新的規則新增至現有清單。</span><span class="sxs-lookup"><span data-stu-id="154d4-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="154d4-209">`Set-MpPreference` 永遠會覆寫現有的規則集。</span><span class="sxs-lookup"><span data-stu-id="154d4-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="154d4-210">如果您想要新增至現有的集，請 `Add-MpPreference` 改用。</span><span class="sxs-lookup"><span data-stu-id="154d4-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="154d4-211">您可以使用來取得規則及其目前狀態的清單 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="154d4-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="154d4-212">若要從 ASR 規則中排除檔案和資料夾，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="154d4-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="154d4-213">繼續使用將 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 更多檔案和資料夾新增至清單。</span><span class="sxs-lookup"><span data-stu-id="154d4-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="154d4-214">用於 `Add-MpPreference` 附加或新增應用程式至清單。</span><span class="sxs-lookup"><span data-stu-id="154d4-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="154d4-215">使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="154d4-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="154d4-216">相關文章</span><span class="sxs-lookup"><span data-stu-id="154d4-216">Related articles</span></span>

- [<span data-ttu-id="154d4-217">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="154d4-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="154d4-218">評估攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="154d4-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="154d4-219">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="154d4-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
