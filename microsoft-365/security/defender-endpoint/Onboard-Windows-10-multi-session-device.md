---
title: 在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線
description: 如需 Windows 虛擬機器中上架 Windows 10 多會話裝置的詳細資訊，請參閱本文。
keywords: Windows Virtual Desktop、WVD、microsoft defender、端點、板載
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
ms.openlocfilehash: 3f925fdc514c5e53b50f748d991f54d20fb49bd0
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488142"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="0646c-104">在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線</span><span class="sxs-lookup"><span data-stu-id="0646c-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="0646c-105">6分鐘可供讀取</span><span class="sxs-lookup"><span data-stu-id="0646c-105">6 minutes to read</span></span> 

<span data-ttu-id="0646c-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="0646c-106">Applies to:</span></span> 
- <span data-ttu-id="0646c-107">在 Windows 虛擬機器上執行的 windows 10 多會話 (WVD) </span><span class="sxs-lookup"><span data-stu-id="0646c-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="0646c-108">Microsoft Defender for Endpoint 支援同時監控 VDI 和 Windows 虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="0646c-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="0646c-109">根據組織的需求，您可能需要執行 VDI 或 Windows 虛擬桌面會話，以協助員工從未受管理的裝置、遠端位置或類似案例中存取公司資料和應用程式。</span><span class="sxs-lookup"><span data-stu-id="0646c-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="0646c-110">使用 Microsoft Defender for Endpoint，您可以監視這些虛擬機器，以進行反常的活動。</span><span class="sxs-lookup"><span data-stu-id="0646c-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="0646c-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="0646c-111">Before you begin</span></span>
<span data-ttu-id="0646c-112">熟悉 [非持久性 VDI 的考慮](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="0646c-112">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="0646c-113">雖然 [Windows 虛擬桌面](https://docs.microsoft.com/azure/virtual-desktop/overview) 不提供非持續性選項，但是它提供使用黃金 Windows 影像的方式，可用來布建新的主機和重新部署電腦。</span><span class="sxs-lookup"><span data-stu-id="0646c-113">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="0646c-114">這會增加環境中的變化程度，進而影響在 Microsoft Defender for Endpoint 入口網站中建立及維護的專案，可能會降低安全性分析分析員的知名度。</span><span class="sxs-lookup"><span data-stu-id="0646c-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="0646c-115">取決於您選擇的上架方法，裝置可以出現在端點入口網站的 Microsoft Defender 中，做為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="0646c-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="0646c-116">每個虛擬機器的單一專案</span><span class="sxs-lookup"><span data-stu-id="0646c-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="0646c-117">每個虛擬機器的多個專案</span><span class="sxs-lookup"><span data-stu-id="0646c-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="0646c-118">Microsoft 建議您將 Windows 虛擬機器上架為每個虛擬桌面的單一專案。</span><span class="sxs-lookup"><span data-stu-id="0646c-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="0646c-119">這可確保 Microsoft Defender 端點入口網站中的調查經驗是以電腦名稱稱為基礎的一個裝置的內容。</span><span class="sxs-lookup"><span data-stu-id="0646c-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="0646c-120">經常刪除及重新部署 WVD 主機的組織，應強烈考慮使用此方法，因為這會防止在 Microsoft Defender for Endpoint 入口網站中建立相同機器的多個物件。</span><span class="sxs-lookup"><span data-stu-id="0646c-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="0646c-121">這可能會在調查事件時造成混淆。</span><span class="sxs-lookup"><span data-stu-id="0646c-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="0646c-122">在測試或非易失環境中，您可以選擇不同的方式。</span><span class="sxs-lookup"><span data-stu-id="0646c-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="0646c-123">Microsoft 建議將 Microsoft Defender for Endpoint 上架腳本新增至 WVD 黃金影像。</span><span class="sxs-lookup"><span data-stu-id="0646c-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="0646c-124">如此一來，您就可以確定此上架腳本會在第一次啟動時立即執行。</span><span class="sxs-lookup"><span data-stu-id="0646c-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="0646c-125">它會在從 WVD 黃金影像布建的所有 WVD 電腦上第一次啟動時做為啟動腳本執行。</span><span class="sxs-lookup"><span data-stu-id="0646c-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="0646c-126">不過，如果您使用其中一個圖庫圖像但未修改，請將腳本放入共用位置，然後從本機或網域群組原則呼叫它。</span><span class="sxs-lookup"><span data-stu-id="0646c-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="0646c-127">WVD 黃金影像上的 VDI 上架啟動腳本的位置和設定會將其設定為啟動腳本，當 WVD 啟動時執行。</span><span class="sxs-lookup"><span data-stu-id="0646c-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="0646c-128">建議您不要以實際 WVD 黃金影像為架。</span><span class="sxs-lookup"><span data-stu-id="0646c-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="0646c-129">另一個考慮是用來執行腳本的方法。</span><span class="sxs-lookup"><span data-stu-id="0646c-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="0646c-130">它應盡可能在啟動/布建程式中執行，以減少可供接收會話和裝置上架至服務的機器之間的時間。</span><span class="sxs-lookup"><span data-stu-id="0646c-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="0646c-131">下列案例 1 & 2 會將此納入考慮。</span><span class="sxs-lookup"><span data-stu-id="0646c-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="0646c-132">案例</span><span class="sxs-lookup"><span data-stu-id="0646c-132">Scenarios</span></span>
<span data-ttu-id="0646c-133">有幾種方式可以將 WVD 主機電腦架上架：</span><span class="sxs-lookup"><span data-stu-id="0646c-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="0646c-134">在啟動期間) 從共用位置 (或從共用位置執行腳本。</span><span class="sxs-lookup"><span data-stu-id="0646c-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="0646c-135">使用管理工具來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="0646c-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="0646c-136">*案例1：使用本機組策略*</span><span class="sxs-lookup"><span data-stu-id="0646c-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="0646c-137">此案例需要將腳本放在黃金映射中，並使用本機組策略在啟動程式的初期執行。</span><span class="sxs-lookup"><span data-stu-id="0646c-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="0646c-138">使用 [板載非持久性虛擬桌面基礎結構 VDI 裝置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)中的指示。</span><span class="sxs-lookup"><span data-stu-id="0646c-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="0646c-139">遵循每個裝置的單一專案指示。</span><span class="sxs-lookup"><span data-stu-id="0646c-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="0646c-140">*案例2：使用網域群組原則*</span><span class="sxs-lookup"><span data-stu-id="0646c-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="0646c-141">此案例使用以網域為基礎的群組原則來執行集中放置的腳本。</span><span class="sxs-lookup"><span data-stu-id="0646c-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="0646c-142">您也可以將腳本放在黃金影像中，並以相同的方式執行。</span><span class="sxs-lookup"><span data-stu-id="0646c-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="0646c-143">**從 Windows Defender 安全中心下載 WindowsDefenderATPOnboardingPackage.zip 檔案**</span><span class="sxs-lookup"><span data-stu-id="0646c-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>
1. <span data-ttu-id="0646c-144">開啟 VDI configuration 套件 .zip 檔案 (WindowsDefenderATPOnboardingPackage.zip) </span><span class="sxs-lookup"><span data-stu-id="0646c-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  
    - <span data-ttu-id="0646c-145">在 Microsoft Defender 安全性中心導覽窗格中，選取 [**設定**] [上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="0646c-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    - <span data-ttu-id="0646c-146">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="0646c-146">Select Windows 10 as the operating system.</span></span> 
    - <span data-ttu-id="0646c-147">在 [ **部署方法** ] 欄位中，選取非持續端點的 VDI 上架腳本。</span><span class="sxs-lookup"><span data-stu-id="0646c-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    - <span data-ttu-id="0646c-148">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="0646c-148">Click **Download package** and save the .zip file.</span></span> 
2. <span data-ttu-id="0646c-149">將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。</span><span class="sxs-lookup"><span data-stu-id="0646c-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0646c-150">您應該會有一個稱為 **OptionalParamsPolicy** 的資料夾，以及檔案 **WindowsDefenderATPOnboardingScript** 和 **Onboard-NonPersistentMachine.ps1**。</span><span class="sxs-lookup"><span data-stu-id="0646c-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="0646c-151">**在虛擬機器啟動時使用群組原則管理主控台執行腳本**</span><span class="sxs-lookup"><span data-stu-id="0646c-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>
1. <span data-ttu-id="0646c-152">開啟「群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0646c-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>
1. <span data-ttu-id="0646c-153">在 [群組原則管理編輯器] 中，移至 [ **電腦** 設定 \> **偏好** 設定] [控制台 \> **設定**]。</span><span class="sxs-lookup"><span data-stu-id="0646c-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 
1. <span data-ttu-id="0646c-154">以滑鼠右鍵按一下 [ **排程任務**]，按一下 [ **新增**]，然後按一下 [ **立即** 工作 (至少) Windows 7]。</span><span class="sxs-lookup"><span data-stu-id="0646c-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 
1. <span data-ttu-id="0646c-155">在開啟的任務視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項** ] 底下，按一下 [ **變更使用者或群組** ，然後輸入系統]。</span><span class="sxs-lookup"><span data-stu-id="0646c-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="0646c-156">按一下 [ **檢查名稱** ]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="0646c-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="0646c-157">NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0646c-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 
1. <span data-ttu-id="0646c-158">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0646c-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 
1. <span data-ttu-id="0646c-159">移至 [ **動作** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="0646c-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="0646c-160">確定 [動作] 欄位中已選取 [ **啟動程式** ]。</span><span class="sxs-lookup"><span data-stu-id="0646c-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="0646c-161">輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="0646c-161">Enter the following:</span></span> 

> <span data-ttu-id="0646c-162">Action = "Start a program"</span><span class="sxs-lookup"><span data-stu-id="0646c-162">Action = "Start a program"</span></span> <br>
> <span data-ttu-id="0646c-163">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span><span class="sxs-lookup"><span data-stu-id="0646c-163">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span></span> <br>
> <span data-ttu-id="0646c-164">Add 引數 (optional) =-ExecutionPolicy 旁路-command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span><span class="sxs-lookup"><span data-stu-id="0646c-164">Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span></span>

<span data-ttu-id="0646c-165">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="0646c-165">Click **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="0646c-166">*案例3：使用管理工具上架*</span><span class="sxs-lookup"><span data-stu-id="0646c-166">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="0646c-167">如果您打算使用管理工具來管理您的機器，您可以使用 Microsoft 端點 Configuration Manager 將裝置上架在一起。</span><span class="sxs-lookup"><span data-stu-id="0646c-167">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="0646c-168">如需詳細資訊，請參閱： [使用 Configuration Manager 的板載 Windows 10 裝置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="0646c-168">For more information, see: [Onboard Windows 10 devices using Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> 

> [!WARNING]
> <span data-ttu-id="0646c-169">如果您想要使用 [攻擊面減少規則](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)，請注意，不應該使用「[從 PSExec 和 WMI 命令產生的](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)程式建立」原則，因為此規則會封鎖 Configuration manager 用戶端用來正確運作的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="0646c-169">If you plan to use [Attack Surface reduction Rules](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction), please note that rule “[Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used as it is incompatible with management through Microsoft Endpoint Configuration Manager because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="0646c-170">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="0646c-170">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="0646c-171">如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="0646c-171">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="0646c-172">在建立黃金影像時標記您的電腦</span><span class="sxs-lookup"><span data-stu-id="0646c-172">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="0646c-173">在您的上架中，您可能會想要考慮設定機器標記，以在 Microsoft 的「安全性中心」中更輕鬆地讓 WVD 電腦與眾不同。</span><span class="sxs-lookup"><span data-stu-id="0646c-173">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="0646c-174">如需詳細資訊，請參閱設定登錄機 [碼值以新增裝置標記](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="0646c-174">For more information, see [Add device tags by setting a registry key value](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="0646c-175">其他建議的設定</span><span class="sxs-lookup"><span data-stu-id="0646c-175">Other recommended configuration settings</span></span> 

<span data-ttu-id="0646c-176">當您建立黃金影像時，您可能也想要設定初始保護設定。</span><span class="sxs-lookup"><span data-stu-id="0646c-176">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="0646c-177">如需詳細資訊，請參閱 [其他建議的配置設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="0646c-177">For more information, see [Other recommended configuration settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="0646c-178">此外，如果您使用的是 FSlogix 的使用者設定檔，建議您從永遠開啟的保護中排除下列檔：</span><span class="sxs-lookup"><span data-stu-id="0646c-178">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="0646c-179">**排除檔案：**</span><span class="sxs-lookup"><span data-stu-id="0646c-179">**Exclude Files:**</span></span> 

> <span data-ttu-id="0646c-180">%ProgramFiles% \FSLogix\Apps\frxdrv.sys</span><span class="sxs-lookup"><span data-stu-id="0646c-180">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span></span> <br>
> <span data-ttu-id="0646c-181">%ProgramFiles% \FSLogix\Apps\frxdrvvt.sys</span><span class="sxs-lookup"><span data-stu-id="0646c-181">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span></span> <br>
> <span data-ttu-id="0646c-182">%ProgramFiles% \FSLogix\Apps\frxccd.sys</span><span class="sxs-lookup"><span data-stu-id="0646c-182">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span></span> <br>
> <span data-ttu-id="0646c-183">%TEMP% \* 。VHD</span><span class="sxs-lookup"><span data-stu-id="0646c-183">%TEMP%\*.VHD</span></span> <br>
> <span data-ttu-id="0646c-184">%TEMP% \* 。.VHDX</span><span class="sxs-lookup"><span data-stu-id="0646c-184">%TEMP%\*.VHDX</span></span> <br>
> <span data-ttu-id="0646c-185">%Windir%\TEMP \* 。VHD</span><span class="sxs-lookup"><span data-stu-id="0646c-185">%Windir%\TEMP\*.VHD</span></span> <br>
> <span data-ttu-id="0646c-186">%Windir%\TEMP \* 。.VHDX</span><span class="sxs-lookup"><span data-stu-id="0646c-186">%Windir%\TEMP\*.VHDX</span></span> <br>
> <span data-ttu-id="0646c-187">\\net\share \* \* 的 storageaccount。VHD</span><span class="sxs-lookup"><span data-stu-id="0646c-187">\\storageaccount.file.core.windows.net\share\*\*.VHD</span></span> <br>
> <span data-ttu-id="0646c-188">\\net\share \* \* 的 storageaccount。.VHDX</span><span class="sxs-lookup"><span data-stu-id="0646c-188">\\storageaccount.file.core.windows.net\share\*\*.VHDX</span></span> <br>

<span data-ttu-id="0646c-189">**排除處理常式：**</span><span class="sxs-lookup"><span data-stu-id="0646c-189">**Exclude Processes:**</span></span>

> <span data-ttu-id="0646c-190">%ProgramFiles% \FSLogix\Apps\frxccd.exe</span><span class="sxs-lookup"><span data-stu-id="0646c-190">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span></span> <br>
> <span data-ttu-id="0646c-191">%ProgramFiles% \FSLogix\Apps\frxccds.exe</span><span class="sxs-lookup"><span data-stu-id="0646c-191">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span></span> <br>
> <span data-ttu-id="0646c-192">%ProgramFiles% \FSLogix\Apps\frxsvc.exe</span><span class="sxs-lookup"><span data-stu-id="0646c-192">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span></span> <br>

#### <a name="licensing-requirements"></a><span data-ttu-id="0646c-193">授權需求</span><span class="sxs-lookup"><span data-stu-id="0646c-193">Licensing requirements</span></span> 

<span data-ttu-id="0646c-194">Windows 10 多重會話是用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="0646c-194">Windows 10 Multi-session is a client OS.</span></span> <span data-ttu-id="0646c-195">Microsoft Defender for endpoint 的授權需求可在下列位置找到： [授權要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="0646c-195">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>
