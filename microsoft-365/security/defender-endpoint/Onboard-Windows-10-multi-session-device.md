---
title: 在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線
description: 如需有關在 Windows 虛擬桌面上架 Windows 10 多會話裝置的資訊，請參閱本文中的更多內容。
keywords: Windows虛擬桌面、WVD、microsoft defender、端點、板載
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7ade1ae1e045cb52f48d231acbc1712e753b6bc3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841843"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="df753-104">在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線</span><span class="sxs-lookup"><span data-stu-id="df753-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="df753-105">6分鐘可供讀取</span><span class="sxs-lookup"><span data-stu-id="df753-105">6 minutes to read</span></span> 

<span data-ttu-id="df753-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="df753-106">Applies to:</span></span> 
- <span data-ttu-id="df753-107">在 Windows 虛擬機器上執行的 Windows 10 多個會話 (WVD) </span><span class="sxs-lookup"><span data-stu-id="df753-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="df753-108">Microsoft Defender for Endpoint 支援監控 VDI 和 Windows 虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="df753-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="df753-109">根據組織的需求，您可能需要執行 VDI 或 Windows 虛擬機器會話，以協助員工從未受管理的裝置、遠端位置或類似案例中存取公司資料和應用程式。</span><span class="sxs-lookup"><span data-stu-id="df753-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="df753-110">使用 Microsoft Defender for Endpoint，您可以監視這些虛擬機器，以進行反常的活動。</span><span class="sxs-lookup"><span data-stu-id="df753-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="df753-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="df753-111">Before you begin</span></span>
<span data-ttu-id="df753-112">熟悉 [非持久性 VDI 的考慮](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="df753-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="df753-113">雖然[Windows 虛擬桌面](/azure/virtual-desktop/overview)不提供非持續性選項，但是它提供使用黃金 Windows 影像的方式，可用來布建新的主機和重新部署電腦。</span><span class="sxs-lookup"><span data-stu-id="df753-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="df753-114">這會增加環境中的變化程度，進而影響在 Microsoft Defender for Endpoint 入口網站中建立及維護的專案，可能會降低安全性分析分析員的知名度。</span><span class="sxs-lookup"><span data-stu-id="df753-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="df753-115">取決於您選擇的上架方法，裝置可以出現在端點入口網站的 Microsoft Defender 中，做為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="df753-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="df753-116">每個虛擬機器的單一專案</span><span class="sxs-lookup"><span data-stu-id="df753-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="df753-117">每個虛擬機器的多個專案</span><span class="sxs-lookup"><span data-stu-id="df753-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="df753-118">Microsoft 建議將 Windows 虛擬機器上架成每個虛擬桌面的單一專案。</span><span class="sxs-lookup"><span data-stu-id="df753-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="df753-119">這可確保 Microsoft Defender 端點入口網站中的調查經驗是以電腦名稱稱為基礎的一個裝置的內容。</span><span class="sxs-lookup"><span data-stu-id="df753-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="df753-120">經常刪除及重新部署 WVD 主機的組織，應強烈考慮使用此方法，因為這會防止在 Microsoft Defender for Endpoint 入口網站中建立相同機器的多個物件。</span><span class="sxs-lookup"><span data-stu-id="df753-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="df753-121">這可能會在調查事件時造成混淆。</span><span class="sxs-lookup"><span data-stu-id="df753-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="df753-122">在測試或非易失環境中，您可以選擇不同的方式。</span><span class="sxs-lookup"><span data-stu-id="df753-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="df753-123">Microsoft 建議將 Microsoft Defender for Endpoint 上架腳本新增至 WVD 黃金影像。</span><span class="sxs-lookup"><span data-stu-id="df753-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="df753-124">如此一來，您就可以確定此上架腳本會在第一次啟動時立即執行。</span><span class="sxs-lookup"><span data-stu-id="df753-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="df753-125">它會在從 WVD 黃金影像布建的所有 WVD 電腦上第一次啟動時做為啟動腳本執行。</span><span class="sxs-lookup"><span data-stu-id="df753-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="df753-126">不過，如果您使用其中一個圖庫圖像但未修改，請將腳本放入共用位置，然後從本機或網域群組原則呼叫它。</span><span class="sxs-lookup"><span data-stu-id="df753-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="df753-127">WVD 黃金影像上的 VDI 上架啟動腳本的位置和設定會將其設定為啟動腳本，當 WVD 啟動時執行。</span><span class="sxs-lookup"><span data-stu-id="df753-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="df753-128">建議您不要以實際 WVD 黃金影像為架。</span><span class="sxs-lookup"><span data-stu-id="df753-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="df753-129">另一個考慮是用來執行腳本的方法。</span><span class="sxs-lookup"><span data-stu-id="df753-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="df753-130">它應盡可能在啟動/布建程式中執行，以減少可供接收會話和裝置上架至服務的機器之間的時間。</span><span class="sxs-lookup"><span data-stu-id="df753-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="df753-131">下列案例 1 & 2 會將此納入考慮。</span><span class="sxs-lookup"><span data-stu-id="df753-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="df753-132">案例</span><span class="sxs-lookup"><span data-stu-id="df753-132">Scenarios</span></span>
<span data-ttu-id="df753-133">有幾種方式可以將 WVD 主機電腦架上架：</span><span class="sxs-lookup"><span data-stu-id="df753-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="df753-134">在啟動期間) 從共用位置 (或從共用位置執行腳本。</span><span class="sxs-lookup"><span data-stu-id="df753-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="df753-135">使用管理工具來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="df753-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="df753-136">*案例1：使用本機組策略*</span><span class="sxs-lookup"><span data-stu-id="df753-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="df753-137">此案例需要將腳本放在黃金映射中，並使用本機組策略在啟動程式的初期執行。</span><span class="sxs-lookup"><span data-stu-id="df753-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="df753-138">使用 [板載非持久性虛擬桌面基礎結構 VDI 裝置](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)中的指示。</span><span class="sxs-lookup"><span data-stu-id="df753-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="df753-139">遵循每個裝置的單一專案指示。</span><span class="sxs-lookup"><span data-stu-id="df753-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="df753-140">*案例2：使用網域群組原則*</span><span class="sxs-lookup"><span data-stu-id="df753-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="df753-141">此案例使用以網域為基礎的群組原則來執行集中放置的腳本。</span><span class="sxs-lookup"><span data-stu-id="df753-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="df753-142">您也可以將腳本放在黃金影像中，並以相同的方式執行。</span><span class="sxs-lookup"><span data-stu-id="df753-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="df753-143">**從 Windows Defender 安全中心下載 WindowsDefenderATPOnboardingPackage.zip 檔案**</span><span class="sxs-lookup"><span data-stu-id="df753-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="df753-144">開啟 VDI 設定套件 .zip 檔案 (WindowsDefenderATPOnboardingPackage.zip) </span><span class="sxs-lookup"><span data-stu-id="df753-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="df753-145">在 [Microsoft Defender 資訊安全中心] 導覽窗格中，選取 [**設定** 上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="df753-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="df753-146">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="df753-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="df753-147">在 [ **部署方法** ] 欄位中，選取非持續端點的 VDI 上架腳本。</span><span class="sxs-lookup"><span data-stu-id="df753-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="df753-148">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="df753-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="df753-149">將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。</span><span class="sxs-lookup"><span data-stu-id="df753-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="df753-150">您應該會有一個稱為 **OptionalParamsPolicy** 的資料夾，以及檔案 **WindowsDefenderATPOnboardingScript** 和 **Onboard-NonPersistentMachine.ps1**。</span><span class="sxs-lookup"><span data-stu-id="df753-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="df753-151">**在虛擬機器啟動時使用群組原則管理主控台執行腳本**</span><span class="sxs-lookup"><span data-stu-id="df753-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="df753-152">開啟「群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="df753-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="df753-153">在 [群組原則管理編輯器] 中，移至 [ **電腦** 設定 \> **偏好** 設定] [控制台 \> **設定**]。</span><span class="sxs-lookup"><span data-stu-id="df753-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="df753-154">以滑鼠右鍵按一下 [**排程任務**]，按一下 [**新增**]，然後按一下 [**立即** 工作 (至少 Windows 7) 。</span><span class="sxs-lookup"><span data-stu-id="df753-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="df753-155">在開啟的任務視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項** ] 底下，按一下 [ **變更使用者或群組** ，然後輸入系統]。</span><span class="sxs-lookup"><span data-stu-id="df753-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="df753-156">按一下 [ **檢查名稱** ]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="df753-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="df753-157">NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="df753-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="df753-158">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="df753-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="df753-159">移至 [ **動作** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="df753-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="df753-160">確定 [動作] 欄位中已選取 [ **啟動程式** ]。</span><span class="sxs-lookup"><span data-stu-id="df753-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="df753-161">輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="df753-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="df753-162">然後選取 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="df753-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="df753-163">*案例3：使用管理工具上架*</span><span class="sxs-lookup"><span data-stu-id="df753-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="df753-164">如果您打算使用管理工具來管理機器，您可以使用 Microsoft Endpoint Configuration Manager 板載裝置。</span><span class="sxs-lookup"><span data-stu-id="df753-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="df753-165">如需詳細資訊，請參閱[使用 Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)。</span><span class="sxs-lookup"><span data-stu-id="df753-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="df753-166">如果您打算使用[攻擊面減少規則](attack-surface-reduction.md)，請注意，不應該使用規則「[封鎖從 PSExec 和 WMI 命令](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)產生的程式建立」，因為該規則與透過 Microsoft Endpoint Configuration Manager 的管理不相容。</span><span class="sxs-lookup"><span data-stu-id="df753-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="df753-167">規則會封鎖 Configuration Manager 用戶端用來正確運作的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="df753-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="df753-168">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="df753-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="df753-169">如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="df753-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="df753-170">在建立黃金影像時標記您的電腦</span><span class="sxs-lookup"><span data-stu-id="df753-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="df753-171">在您的上架中，您可能會想要考慮設定機器標記，以在 Microsoft 的「安全性中心」中更輕鬆地讓 WVD 電腦與眾不同。</span><span class="sxs-lookup"><span data-stu-id="df753-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="df753-172">如需詳細資訊，請參閱設定登錄機 [碼值以新增裝置標記](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="df753-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="df753-173">其他建議的設定</span><span class="sxs-lookup"><span data-stu-id="df753-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="df753-174">當您建立黃金影像時，您可能也想要設定初始保護設定。</span><span class="sxs-lookup"><span data-stu-id="df753-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="df753-175">如需詳細資訊，請參閱 [其他建議的配置設定](configure-endpoints-gp.md#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="df753-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="df753-176">此外，如果您使用的是 FSlogix 的使用者設定檔，建議您從永遠開啟的保護中排除下列檔：</span><span class="sxs-lookup"><span data-stu-id="df753-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="df753-177">**排除檔案：**</span><span class="sxs-lookup"><span data-stu-id="df753-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="df753-178">**排除處理常式：**</span><span class="sxs-lookup"><span data-stu-id="df753-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="df753-179">授權需求</span><span class="sxs-lookup"><span data-stu-id="df753-179">Licensing requirements</span></span> 

<span data-ttu-id="df753-180">授權時請注意：使用 Windows 10 企業版多個會話時，您可以選擇以每位使用者的端點 (所有使用者授權的所有使用者) 、Windows Enterprise E5、Microsoft 365 安全性或 Microsoft 365 E5，或讓 VM 透過 Azure Defender 授權。</span><span class="sxs-lookup"><span data-stu-id="df753-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="df753-181">Microsoft Defender for endpoint 的授權需求可在下列位置找到： [授權要求](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="df753-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
