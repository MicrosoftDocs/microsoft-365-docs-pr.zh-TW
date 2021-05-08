---
title: Microsoft Defender 防毒軟體虛擬桌面基礎結構部署指南
description: 瞭解如何在虛擬桌面環境中部署 Microsoft Defender 防毒軟體，以取得保護與效能之間的最佳平衡。
keywords: vdi，hyper-v，vm，虛擬機器，windows defender，防毒程式，av，虛擬桌面機，rds，遠端桌面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275249"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="656bf-104">虛擬桌面基礎結構 (VDI) 環境中 Microsoft Defender 防毒軟體的部署指南</span><span class="sxs-lookup"><span data-stu-id="656bf-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="656bf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="656bf-105">**Applies to:**</span></span>

- [<span data-ttu-id="656bf-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="656bf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="656bf-107">除了標準的內部部署或硬體設定之外，您也可以使用遠端桌面 (RDS) 或虛擬桌面基礎結構 (VDI) 環境中的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="656bf-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="656bf-108">如需 Microsoft 遠端桌面服務和 VDI 支援的詳細資訊，請參閱[Windows 虛擬機器檔](/azure/virtual-desktop)。</span><span class="sxs-lookup"><span data-stu-id="656bf-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="656bf-109">如需 azure 虛擬機器，請參閱[在 azure Defender 中安裝 Endpoint Protection](/azure/security-center/security-center-install-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="656bf-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="656bf-110">透過輕鬆將更新部署至 VDIs 中執行的 Vm 的功能，我們已縮短此指南，以著重于您可以快速輕鬆地在電腦上更新的方式。</span><span class="sxs-lookup"><span data-stu-id="656bf-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="656bf-111">您不再需要定期建立及密封黃金影像，因為更新會擴充至主伺服器上的元件位，然後在開啟時直接下載至 VM。</span><span class="sxs-lookup"><span data-stu-id="656bf-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="656bf-112">本指南說明如何設定您的 Vm 以取得最佳保護和效能，包括如何進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="656bf-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="656bf-113">為安全性情報更新設定專用的 VDI 檔案共用</span><span class="sxs-lookup"><span data-stu-id="656bf-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="656bf-114">隨機化排程掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="656bf-115">使用快速掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="656bf-116">防止通知</span><span class="sxs-lookup"><span data-stu-id="656bf-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="656bf-117">停用每次更新後所發生的掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="656bf-118">掃描已離線一段時間的過時機器或機器</span><span class="sxs-lookup"><span data-stu-id="656bf-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="656bf-119">套用排除專案</span><span class="sxs-lookup"><span data-stu-id="656bf-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="656bf-120">您也可以[在虛擬桌面基礎結構上](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)下載白皮書 Microsoft Defender 防毒軟體，它會看看新的共用安全情報更新功能，也就是如何在您自己的 VDI 上測試防病毒效能的效能測試及指導方針。</span><span class="sxs-lookup"><span data-stu-id="656bf-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="656bf-121">雖然 VDI 可以主控于 Windows Server 2012 或 Windows Server 2016 上，但虛擬機器 (vm) 應該至少執行 Windows 10 1607，因為在舊版的 Windows 中已增加的保護技術和功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="656bf-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="656bf-122">在 Windows 10 內幕機預覽、組建 18323 (和更新) 版本中，Microsoft Defender AV 對虛擬機器的運作方式，具有效能及功能的增強功能。</span><span class="sxs-lookup"><span data-stu-id="656bf-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="656bf-123">如果您需要使用內部使用者預覽組建，我們會在此指南中識別。若未指定，則最佳保護和效能所需的最低版本為 Windows 10 1607。</span><span class="sxs-lookup"><span data-stu-id="656bf-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="656bf-124">設定專用的 VDI 檔案共用</span><span class="sxs-lookup"><span data-stu-id="656bf-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="656bf-125">在 Windows 10 版本1903中，我們引進了共用安全性智慧功能，以將下載的安全性情報更新解除至主機機，進而儲存個別電腦上的 CPU、磁片和記憶體資源。</span><span class="sxs-lookup"><span data-stu-id="656bf-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="656bf-126">這項功能已經過回溯，現在可在 Windows 10 版本1703和更新版本中運作。</span><span class="sxs-lookup"><span data-stu-id="656bf-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="656bf-127">您可以使用群組原則或 PowerShell 來設定此功能。</span><span class="sxs-lookup"><span data-stu-id="656bf-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="656bf-128">使用群組原則來啟用共用的安全性智慧功能：</span><span class="sxs-lookup"><span data-stu-id="656bf-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="656bf-129">在您的群組原則管理電腦上，開啟 [群組原則管理主控台]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="656bf-130">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="656bf-131">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="656bf-132">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。</span><span class="sxs-lookup"><span data-stu-id="656bf-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="656bf-133">按兩下 [ **定義 VDI 用戶端的安全性智慧位置**]，然後將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="656bf-134">會自動顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="656bf-134">A field automatically appears.</span></span>

6. <span data-ttu-id="656bf-135">輸入 `\\<sharedlocation\>\wdav-update` 此值的說明 (，請參閱 [下載和解開](#download-and-unpackage-the-latest-updates)) 。</span><span class="sxs-lookup"><span data-stu-id="656bf-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="656bf-136">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-136">Click **OK**.</span></span>

8. <span data-ttu-id="656bf-137">將 GPO 部署至您要測試的 Vm。</span><span class="sxs-lookup"><span data-stu-id="656bf-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="656bf-138">使用 PowerShell 啟用共用安全性智慧功能</span><span class="sxs-lookup"><span data-stu-id="656bf-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="656bf-139">使用下列 Cmdlet 來啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="656bf-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="656bf-140">您通常需要將 PowerShell 型設定原則推入 Vm，就像往常一樣：</span><span class="sxs-lookup"><span data-stu-id="656bf-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="656bf-141">請參閱 [下載及解壓縮](#download-and-unpackage-the-latest-updates) 區段，以瞭解 \<shared location\> 將會有哪些專案。</span><span class="sxs-lookup"><span data-stu-id="656bf-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="656bf-142">下載並解開最新的更新</span><span class="sxs-lookup"><span data-stu-id="656bf-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="656bf-143">現在，您可以開始下載及安裝新的更新。</span><span class="sxs-lookup"><span data-stu-id="656bf-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="656bf-144">我們為您建立了範例 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="656bf-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="656bf-145">此腳本是下載新更新並為您的 Vm 做好準備的最簡單方式。</span><span class="sxs-lookup"><span data-stu-id="656bf-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="656bf-146">然後，您應該使用計畫的工作 (，將腳本設定為在管理電腦上的特定時間執行; 如果您很熟悉在 Azure、Intune 或 SCCM 中使用 PowerShell 腳本，也可以) 使用這些腳本。</span><span class="sxs-lookup"><span data-stu-id="656bf-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="656bf-147">您可以將排定的任務設定為一天執行一次，這樣每當下載並解壓縮套件時，Vm 都會收到新的更新。</span><span class="sxs-lookup"><span data-stu-id="656bf-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="656bf-148">我們建議您一天開始一次，但您應嘗試增加或減少頻率，以瞭解影響。</span><span class="sxs-lookup"><span data-stu-id="656bf-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="656bf-149">安全性智慧套件通常每三至四個小時發佈一次。</span><span class="sxs-lookup"><span data-stu-id="656bf-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="656bf-150">設定頻率短于四小時的頻率不會被告知，因為這會增加管理電腦上沒有任何好處的網路開銷。</span><span class="sxs-lookup"><span data-stu-id="656bf-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="656bf-151">設定計劃任務以執行 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="656bf-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="656bf-152">在管理電腦上，開啟 [開始] 功能表，然後輸入 [ **任務** 排程器]。</span><span class="sxs-lookup"><span data-stu-id="656bf-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="656bf-153">開啟它，然後選取 [ **建立任務 ...]。**</span><span class="sxs-lookup"><span data-stu-id="656bf-153">Open it and select **Create task…**</span></span> <span data-ttu-id="656bf-154">在側面面板上。</span><span class="sxs-lookup"><span data-stu-id="656bf-154">on the side panel.</span></span>

2. <span data-ttu-id="656bf-155">輸入名稱作為 **安全性情報 unpacker**。</span><span class="sxs-lookup"><span data-stu-id="656bf-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="656bf-156">移至 [**觸發器**] 索引標籤。選取 [**新增 ...** ]</span><span class="sxs-lookup"><span data-stu-id="656bf-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="656bf-157"> > [**每日**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="656bf-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="656bf-158">移至 [**動作**] 索引標籤。選取 [**新增 ...** ]</span><span class="sxs-lookup"><span data-stu-id="656bf-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="656bf-159">在 [**程式/腳本**] 欄位中輸入 **PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="656bf-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="656bf-160">`-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1`在 [**新增引數**] 欄位中輸入。</span><span class="sxs-lookup"><span data-stu-id="656bf-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="656bf-161">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-161">Select **OK**.</span></span>

4. <span data-ttu-id="656bf-162">您可以視需要選擇設定其他設定。</span><span class="sxs-lookup"><span data-stu-id="656bf-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="656bf-163">選取 **[確定]** 以儲存排程的任務。</span><span class="sxs-lookup"><span data-stu-id="656bf-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="656bf-164">您可以手動啟動更新，方法是以滑鼠右鍵按一下任務，然後按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="656bf-165">手動下載和解開</span><span class="sxs-lookup"><span data-stu-id="656bf-165">Download and unpackage manually</span></span>

<span data-ttu-id="656bf-166">如果您想要手動執行所有動作，以下是複製腳本行為的方法：</span><span class="sxs-lookup"><span data-stu-id="656bf-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="656bf-167">在稱為儲存情報更新的系統根目錄上建立新的資料夾 `wdav_update` ，例如，建立資料夾 `c:\wdav_update` 。</span><span class="sxs-lookup"><span data-stu-id="656bf-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="656bf-168">使用 GUID 名稱在 *wdav_update* 底下建立子資料夾，例如 `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="656bf-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="656bf-169">範例如下： `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="656bf-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="656bf-170">在腳本中，我們會設定它，使 GUID 的最後12位數成為下載檔案的年、月、日和時間，以便每次建立新的資料夾。</span><span class="sxs-lookup"><span data-stu-id="656bf-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="656bf-171">您可以變更此方式，每次將檔案下載至相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="656bf-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="656bf-172">從 GUID 資料夾下載安全性智慧套件 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  。</span><span class="sxs-lookup"><span data-stu-id="656bf-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="656bf-173">該檔案應該是以檔案名命名 `mpam-fe.exe` 。</span><span class="sxs-lookup"><span data-stu-id="656bf-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="656bf-174">開啟 cmd 命令提示字元視窗，並流覽至您建立的 GUID 資料夾。</span><span class="sxs-lookup"><span data-stu-id="656bf-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="656bf-175">例如，使用 **/x** 解壓縮命令解壓縮檔案 `mpam-fe.exe /X` 。</span><span class="sxs-lookup"><span data-stu-id="656bf-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="656bf-176">每當使用解壓縮的更新套件建立新的 GUID 資料夾時，或在使用新的解壓縮套件更新現有的資料夾時，Vm 都會拾取更新的套件。</span><span class="sxs-lookup"><span data-stu-id="656bf-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="656bf-177">隨機化排程掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-177">Randomize scheduled scans</span></span>

<span data-ttu-id="656bf-178">除了 [即時保護及掃描](configure-real-time-protection-microsoft-defender-antivirus.md)之外，還會執行排程掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="656bf-179">掃描本身的開始時間仍以排程的掃描原則為基礎， (**ScheduleDay**、 **ScheduleTime** 及 **ScheduleQuickScanTime**) 。</span><span class="sxs-lookup"><span data-stu-id="656bf-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="656bf-180">隨機會使 Microsoft Defender 防毒軟體從排定的掃描時間設定之4小時內的每一部電腦上開始掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="656bf-181">請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 以取得可用於排程掃描的其他配置選項。</span><span class="sxs-lookup"><span data-stu-id="656bf-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="656bf-182">使用快速掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-182">Use quick scans</span></span>

<span data-ttu-id="656bf-183">您可以指定在排程掃描期間應執行的掃描類型。</span><span class="sxs-lookup"><span data-stu-id="656bf-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="656bf-184">快速掃描是一種慣用方式，其設計目的是要尋找惡意程式碼所在的所有位置，以供使用中的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="656bf-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="656bf-185">下列程式說明如何使用「群組原則」設定快速掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="656bf-186">在 [群組原則編輯器] 中，移至 [系統 **管理範本**]  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="656bf-187">選取 **[指定要用於排程掃描的掃描類型** ]，然後編輯原則設定。</span><span class="sxs-lookup"><span data-stu-id="656bf-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="656bf-188">將原則設定為 [ **啟用**]，然後在 [ **選項**] 下，選取 [  **快速掃描**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="656bf-189">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-189">Select **OK**.</span></span> 

5. <span data-ttu-id="656bf-190">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="656bf-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="656bf-191">防止通知</span><span class="sxs-lookup"><span data-stu-id="656bf-191">Prevent notifications</span></span>

<span data-ttu-id="656bf-192">在某些情況下，Microsoft Defender 防毒軟體通知可能會傳送至或持續傳送至多個會話。</span><span class="sxs-lookup"><span data-stu-id="656bf-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="656bf-193">為了將此問題降至最低，您可以鎖定 Microsoft Defender 防毒軟體使用者介面。</span><span class="sxs-lookup"><span data-stu-id="656bf-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="656bf-194">下列程式說明如何使用群組原則來抑制通知。</span><span class="sxs-lookup"><span data-stu-id="656bf-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="656bf-195">在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="656bf-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="656bf-196">選取 [ **抑制所有通知** ]，然後編輯原則設定。</span><span class="sxs-lookup"><span data-stu-id="656bf-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="656bf-197">將原則設定為 [ **啟用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="656bf-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="656bf-198">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="656bf-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="656bf-199">抑制通知，可防止在執行掃描時 Windows 10 的「動作中心」或進行修正動作時，Microsoft Defender 防毒軟體中顯示的通知。</span><span class="sxs-lookup"><span data-stu-id="656bf-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="656bf-200">不過，您的安全性運作小組會在 Microsoft Defender 資訊安全中心 () 中看到掃描的結果 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="656bf-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="656bf-201">若要在 Windows 10 上開啟「行動中心」，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="656bf-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="656bf-202">在工作列的右端，選取 [動作中心] 圖示。</span><span class="sxs-lookup"><span data-stu-id="656bf-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="656bf-203">按 Windows 標誌鍵按鈕 + A。</span><span class="sxs-lookup"><span data-stu-id="656bf-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="656bf-204">在觸控式螢幕裝置上，從畫面的右邊緣輕掃。</span><span class="sxs-lookup"><span data-stu-id="656bf-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="656bf-205">在更新後停用掃描</span><span class="sxs-lookup"><span data-stu-id="656bf-205">Disable scans after an update</span></span>

<span data-ttu-id="656bf-206">在更新後停用掃描會使掃描在接收到更新後發生。</span><span class="sxs-lookup"><span data-stu-id="656bf-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="656bf-207">您可以在建立基底影像時套用此設定（如果您同時執行快速掃描）。</span><span class="sxs-lookup"><span data-stu-id="656bf-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="656bf-208">如此一來，您就可以在建立基本影像) 時，防止新更新的 VM 重新執行掃描 (已掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="656bf-209">在更新後執行掃描會協助確保您的 Vm 受到最新安全性情報更新的保護。</span><span class="sxs-lookup"><span data-stu-id="656bf-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="656bf-210">停用此選項將會降低 Vm 的保護層級，只應該在第一次建立或部署基底影像時使用。</span><span class="sxs-lookup"><span data-stu-id="656bf-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="656bf-211">在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="656bf-212">選取 [ **在安全性智慧更新後開啟掃描** ]，然後編輯原則設定。</span><span class="sxs-lookup"><span data-stu-id="656bf-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="656bf-213">將原則設定為 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="656bf-214">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-214">Select **OK**.</span></span>

5. <span data-ttu-id="656bf-215">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="656bf-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="656bf-216">這個原則可防止在更新之後立即執行掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="656bf-217">掃描已離線的 Vm</span><span class="sxs-lookup"><span data-stu-id="656bf-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="656bf-218">在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="656bf-219">選取 [ **開啟追趕快速掃描** ]，然後編輯原則設定。</span><span class="sxs-lookup"><span data-stu-id="656bf-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="656bf-220">將原則設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="656bf-221">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-221">Select **OK**.</span></span>

5. <span data-ttu-id="656bf-222">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="656bf-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="656bf-223">如果 VM 已錯過兩個或多個連續排程掃描，此原則會強制進行掃描。</span><span class="sxs-lookup"><span data-stu-id="656bf-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="656bf-224">啟用無周邊 UI 模式</span><span class="sxs-lookup"><span data-stu-id="656bf-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="656bf-225">在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="656bf-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="656bf-226">選取 [ **啟用無周邊 UI 模式]** ，然後編輯原則。</span><span class="sxs-lookup"><span data-stu-id="656bf-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="656bf-227">將原則設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="656bf-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="656bf-228">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="656bf-228">Click **OK**.</span></span>

5. <span data-ttu-id="656bf-229">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="656bf-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="656bf-230">這個原則會從您組織中的使用者隱藏整個 Microsoft Defender 防毒軟體使用者介面。</span><span class="sxs-lookup"><span data-stu-id="656bf-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="656bf-231">排除項目</span><span class="sxs-lookup"><span data-stu-id="656bf-231">Exclusions</span></span>

<span data-ttu-id="656bf-232">您可以新增、移除或自訂排除專案，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="656bf-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="656bf-233">如需詳細資訊，請參閱[Configure Microsoft Defender 防毒軟體 Windows Server 上的排除](configure-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="656bf-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="656bf-234">其他資源</span><span class="sxs-lookup"><span data-stu-id="656bf-234">Additional resources</span></span>

- [<span data-ttu-id="656bf-235">技術 Community 博客：針對非 persistent VDI 機器設定 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="656bf-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="656bf-236">在遠端桌面服務和 VDI 上 TechNet 論壇</span><span class="sxs-lookup"><span data-stu-id="656bf-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="656bf-237">SignatureDownloadCustomTask PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="656bf-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)