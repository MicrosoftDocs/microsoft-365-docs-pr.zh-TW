---
title: Windows 虛擬桌面中的板載 Windows 10 多會話裝置
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
ms.date: 09/10/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 30e664aed74ed01944c67b139e6268fc3340ada4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057172"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="29d84-104">Windows 虛擬桌面中的板載 Windows 10 多會話裝置</span><span class="sxs-lookup"><span data-stu-id="29d84-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="29d84-105">6分鐘可供讀取</span><span class="sxs-lookup"><span data-stu-id="29d84-105">6 minutes to read</span></span> 

<span data-ttu-id="29d84-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="29d84-106">Applies to:</span></span> 
- <span data-ttu-id="29d84-107">在 Windows 虛擬機器上執行的 windows 10 多會話 (WVD) </span><span class="sxs-lookup"><span data-stu-id="29d84-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="29d84-108">歡迎使用 Microsoft Defender for Endpoint，Microsoft Defender for Endpoint 的新名稱。</span><span class="sxs-lookup"><span data-stu-id="29d84-108">Welcome to Microsoft Defender for Endpoint, the new name for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="29d84-109">請參閱這裡以深入了解其他最新消息。</span><span class="sxs-lookup"><span data-stu-id="29d84-109">Read more about this and other updates here.</span></span> <span data-ttu-id="29d84-110">我們將於近期在產品和文件中更新名稱。</span><span class="sxs-lookup"><span data-stu-id="29d84-110">We'll be updating names in products and in the docs in the near future.</span></span>

> [!WARNING]
> <span data-ttu-id="29d84-111">Windows 虛擬桌面多會話案例的 Microsoft Defender for Endpoint 支援目前正在預覽中，且每個主機/VM 最多可同時限制25個同時會話。</span><span class="sxs-lookup"><span data-stu-id="29d84-111">Microsoft Defender for Endpoint support for Windows Virtual Desktop multi-session scenarios is currently in Preview and limited up to 25 concurrent sessions per host/VM.</span></span> <span data-ttu-id="29d84-112">不過，已完全支援 Windows 虛擬桌面上的單一會話案例。</span><span class="sxs-lookup"><span data-stu-id="29d84-112">However, single session scenarios on Windows Virtual Desktop are fully supported.</span></span>

<span data-ttu-id="29d84-113">Microsoft Defender for Endpoint 支援同時監控 VDI 和 Windows 虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="29d84-113">Microsoft Defender for Endpoint supports monitoring both VDI as well as Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="29d84-114">根據組織的需求，您可能需要執行 VDI 或 Windows 虛擬桌面會話，以協助員工從未受管理的裝置、遠端位置或類似案例中存取公司資料和應用程式。</span><span class="sxs-lookup"><span data-stu-id="29d84-114">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="29d84-115">使用 Microsoft Defender for Endpoint，您可以監視這些虛擬機器，以進行反常的活動。</span><span class="sxs-lookup"><span data-stu-id="29d84-115">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="29d84-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="29d84-116">Before you begin</span></span>
<span data-ttu-id="29d84-117">熟悉 [非持久性 VDI 的考慮](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="29d84-117">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="29d84-118">雖然 [Windows 虛擬桌面](https://docs.microsoft.com/azure/virtual-desktop/overview) 不提供非持續性選項，但是它提供使用黃金 Windows 影像的方式，可用來布建新的主機和重新部署電腦。</span><span class="sxs-lookup"><span data-stu-id="29d84-118">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) does not provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="29d84-119">這會增加環境中的變化程度，進而影響在 Microsoft Defender for Endpoint 入口網站中建立及維護的專案，可能會降低安全性分析分析員的知名度。</span><span class="sxs-lookup"><span data-stu-id="29d84-119">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="29d84-120">取決於您選擇的上架方法，裝置可以出現在端點入口網站的 Microsoft Defender 中，做為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="29d84-120">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="29d84-121">每個虛擬機器的單一專案</span><span class="sxs-lookup"><span data-stu-id="29d84-121">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="29d84-122">每個虛擬機器的多個專案</span><span class="sxs-lookup"><span data-stu-id="29d84-122">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="29d84-123">Microsoft 建議您將 Windows 虛擬機器上架為每個虛擬桌面的單一專案。</span><span class="sxs-lookup"><span data-stu-id="29d84-123">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="29d84-124">這可確保 Microsoft Defender 端點入口網站中的調查經驗是以電腦名稱稱為基礎的一個裝置的內容。</span><span class="sxs-lookup"><span data-stu-id="29d84-124">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="29d84-125">經常刪除及重新部署 WVD 主機的組織，應強烈考慮使用此方法，因為這會防止在 Microsoft Defender for Endpoint 入口網站中建立相同機器的多個物件。</span><span class="sxs-lookup"><span data-stu-id="29d84-125">Organizations that frequently delete and re-deploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="29d84-126">這可能會在調查事件時造成混淆。</span><span class="sxs-lookup"><span data-stu-id="29d84-126">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="29d84-127">在測試或非易失環境中，您可以選擇不同的方式。</span><span class="sxs-lookup"><span data-stu-id="29d84-127">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="29d84-128">Microsoft 建議將 Microsoft Defender for Endpoint 上架腳本新增至 WVD 黃金影像。</span><span class="sxs-lookup"><span data-stu-id="29d84-128">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="29d84-129">如此一來，您就可以確定此上架腳本會在第一次啟動時立即執行。</span><span class="sxs-lookup"><span data-stu-id="29d84-129">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="29d84-130">它會在從 WVD 黃金影像布建的所有 WVD 電腦上第一次啟動時做為啟動腳本執行。</span><span class="sxs-lookup"><span data-stu-id="29d84-130">It is executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="29d84-131">不過，如果您使用其中一個圖庫圖像但未修改，請將腳本放入共用位置，然後從本機或網域群組原則呼叫它。</span><span class="sxs-lookup"><span data-stu-id="29d84-131">However, if you are using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="29d84-132">WVD 黃金影像上的 VDI 上架啟動腳本的位置和設定會將其設定為啟動腳本，當 WVD 啟動時執行。</span><span class="sxs-lookup"><span data-stu-id="29d84-132">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="29d84-133">建議您不要以實際 WVD 黃金影像為架。</span><span class="sxs-lookup"><span data-stu-id="29d84-133">It is NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="29d84-134">另一個考慮是用來執行腳本的方法。</span><span class="sxs-lookup"><span data-stu-id="29d84-134">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="29d84-135">它應盡可能在啟動/布建程式中執行，以減少可供接收會話和裝置上架至服務的機器之間的時間。</span><span class="sxs-lookup"><span data-stu-id="29d84-135">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="29d84-136">下列案例 1 & 2 會將此納入考慮。</span><span class="sxs-lookup"><span data-stu-id="29d84-136">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="29d84-137">案例</span><span class="sxs-lookup"><span data-stu-id="29d84-137">Scenarios</span></span>
<span data-ttu-id="29d84-138">有幾種方式可以將 WVD 主機電腦架上架：</span><span class="sxs-lookup"><span data-stu-id="29d84-138">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="29d84-139">在啟動期間) 從共用位置 (或從共用位置執行腳本。</span><span class="sxs-lookup"><span data-stu-id="29d84-139">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="29d84-140">使用管理工具來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="29d84-140">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="29d84-141">*案例1：使用本機組策略*</span><span class="sxs-lookup"><span data-stu-id="29d84-141">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="29d84-142">此案例需要將腳本放在黃金映射中，並使用本機組策略在啟動程式的初期執行。</span><span class="sxs-lookup"><span data-stu-id="29d84-142">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="29d84-143">使用 [板載非持久性虛擬桌面基礎結構 VDI 裝置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)中的指示。</span><span class="sxs-lookup"><span data-stu-id="29d84-143">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="29d84-144">遵循每個裝置的單一專案指示。</span><span class="sxs-lookup"><span data-stu-id="29d84-144">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="29d84-145">*案例2：使用網域群組原則*</span><span class="sxs-lookup"><span data-stu-id="29d84-145">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="29d84-146">此案例使用以網域為基礎的群組原則來執行集中放置的腳本。</span><span class="sxs-lookup"><span data-stu-id="29d84-146">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="29d84-147">您也可以將腳本放在黃金影像中，並以相同的方式執行。</span><span class="sxs-lookup"><span data-stu-id="29d84-147">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="29d84-148">**從 Windows Defender 安全中心下載 WindowsDefenderATPOnboardingPackage.zip 檔案**</span><span class="sxs-lookup"><span data-stu-id="29d84-148">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>
1. <span data-ttu-id="29d84-149">開啟 VDI configuration 套件 .zip 檔案 (WindowsDefenderATPOnboardingPackage.zip) </span><span class="sxs-lookup"><span data-stu-id="29d84-149">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  
    - <span data-ttu-id="29d84-150">在 Microsoft Defender 安全性中心導覽窗格中，選取 [**設定**] [上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="29d84-150">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    - <span data-ttu-id="29d84-151">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="29d84-151">Select Windows 10 as the operating system.</span></span> 
    - <span data-ttu-id="29d84-152">在 [ **部署方法** ] 欄位中，選取非持續端點的 VDI 上架腳本。</span><span class="sxs-lookup"><span data-stu-id="29d84-152">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    - <span data-ttu-id="29d84-153">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="29d84-153">Click **Download package** and save the .zip file.</span></span> 
2. <span data-ttu-id="29d84-154">將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。</span><span class="sxs-lookup"><span data-stu-id="29d84-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="29d84-155">您應該會有一個稱為 **OptionalParamsPolicy** 的資料夾，以及檔案 **WindowsDefenderATPOnboardingScript** 和 **Onboard-NonPersistentMachine.ps1**。</span><span class="sxs-lookup"><span data-stu-id="29d84-155">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="29d84-156">**在虛擬機器啟動時使用群組原則管理主控台執行腳本**</span><span class="sxs-lookup"><span data-stu-id="29d84-156">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>
1. <span data-ttu-id="29d84-157">開啟「群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="29d84-157">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>
1. <span data-ttu-id="29d84-158">在 [群組原則管理編輯器] 中，移至 [ **電腦** 設定 \> **偏好** 設定] [控制台 \> **設定**]。</span><span class="sxs-lookup"><span data-stu-id="29d84-158">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 
1. <span data-ttu-id="29d84-159">以滑鼠右鍵按一下 [ **排程任務**]，按一下 [ **新增**]，然後按一下 [ **立即** 工作 (至少) Windows 7]。</span><span class="sxs-lookup"><span data-stu-id="29d84-159">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 
1. <span data-ttu-id="29d84-160">在開啟的任務視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項** ] 底下，按一下 [ **變更使用者或群組** ，然後輸入系統]。</span><span class="sxs-lookup"><span data-stu-id="29d84-160">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="29d84-161">按一下 [ **檢查名稱** ]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="29d84-161">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="29d84-162">NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="29d84-162">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 
1. <span data-ttu-id="29d84-163">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="29d84-163">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 
1. <span data-ttu-id="29d84-164">移至 [ **動作** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="29d84-164">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="29d84-165">確定 [動作] 欄位中已選取 [ **啟動程式** ]。</span><span class="sxs-lookup"><span data-stu-id="29d84-165">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="29d84-166">輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="29d84-166">Enter the following:</span></span> 

> <span data-ttu-id="29d84-167">Action = "Start a program"</span><span class="sxs-lookup"><span data-stu-id="29d84-167">Action = "Start a program"</span></span> <br>
> <span data-ttu-id="29d84-168">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span><span class="sxs-lookup"><span data-stu-id="29d84-168">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span></span> <br>
> <span data-ttu-id="29d84-169">Add 引數 (optional) =-ExecutionPolicy 旁路-command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span><span class="sxs-lookup"><span data-stu-id="29d84-169">Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span></span>

<span data-ttu-id="29d84-170">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="29d84-170">Click **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="29d84-171">*案例3：使用管理工具上架*</span><span class="sxs-lookup"><span data-stu-id="29d84-171">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="29d84-172">如果您打算使用管理工具來管理您的機器，您可以使用 Microsoft 端點 Configuration Manager 將裝置上架在一起。</span><span class="sxs-lookup"><span data-stu-id="29d84-172">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="29d84-173">如需詳細資訊，請參閱： [使用 Configuration Manager 的板載 Windows 10 裝置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="29d84-173">For more information, see: [Onboard Windows 10 devices using Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> 

> [!WARNING]
> <span data-ttu-id="29d84-174">如果您想要使用 [攻擊面減少規則](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)，請注意，不應該使用「[從 PSExec 和 WMI 命令產生的](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)程式建立」原則，因為此規則會封鎖 Configuration manager 用戶端用來正確運作的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="29d84-174">If you plan to use [Attack Surface reduction Rules](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction), please note that rule “[Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used as it is incompatible with management through Microsoft Endpoint Configuration Manager because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="29d84-175">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="29d84-175">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="29d84-176">如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="29d84-176">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="29d84-177">在建立黃金影像時標記您的電腦</span><span class="sxs-lookup"><span data-stu-id="29d84-177">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="29d84-178">在您的上架中，您可能會想要考慮設定機器標記，以在 Microsoft 的「安全性中心」中更輕鬆地讓 WVD 電腦與眾不同。</span><span class="sxs-lookup"><span data-stu-id="29d84-178">As part of your onboarding, you may want to consider setting a machine tag to be able to differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="29d84-179">如需詳細資訊，請參閱設定登錄機 [碼值以新增裝置標記](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="29d84-179">For more information, see [Add device tags by setting a registry key value](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="29d84-180">其他建議的設定</span><span class="sxs-lookup"><span data-stu-id="29d84-180">Other recommended configuration settings</span></span> 

<span data-ttu-id="29d84-181">當您建立黃金影像時，您可能也想要設定初始保護設定。</span><span class="sxs-lookup"><span data-stu-id="29d84-181">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="29d84-182">如需詳細資訊，請參閱 [其他建議的配置設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="29d84-182">For more information, see [Other recommended configuration settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="29d84-183">此外，如果您使用 FSlogix 的使用者設定檔，建議您從永遠開啟的保護中排除下列檔案：</span><span class="sxs-lookup"><span data-stu-id="29d84-183">In addition, if you are using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="29d84-184">**排除檔案：**</span><span class="sxs-lookup"><span data-stu-id="29d84-184">**Exclude Files:**</span></span> 

> <span data-ttu-id="29d84-185">%ProgramFiles% \FSLogix\Apps\frxdrv.sys</span><span class="sxs-lookup"><span data-stu-id="29d84-185">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span></span> <br>
> <span data-ttu-id="29d84-186">%ProgramFiles% \FSLogix\Apps\frxdrvvt.sys</span><span class="sxs-lookup"><span data-stu-id="29d84-186">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span></span> <br>
> <span data-ttu-id="29d84-187">%ProgramFiles% \FSLogix\Apps\frxccd.sys</span><span class="sxs-lookup"><span data-stu-id="29d84-187">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span></span> <br>
> <span data-ttu-id="29d84-188">%TEMP% \* 。VHD</span><span class="sxs-lookup"><span data-stu-id="29d84-188">%TEMP%\*.VHD</span></span> <br>
> <span data-ttu-id="29d84-189">%TEMP% \* 。.VHDX</span><span class="sxs-lookup"><span data-stu-id="29d84-189">%TEMP%\*.VHDX</span></span> <br>
> <span data-ttu-id="29d84-190">%Windir%\TEMP \* 。VHD</span><span class="sxs-lookup"><span data-stu-id="29d84-190">%Windir%\TEMP\*.VHD</span></span> <br>
> <span data-ttu-id="29d84-191">%Windir%\TEMP \* 。.VHDX</span><span class="sxs-lookup"><span data-stu-id="29d84-191">%Windir%\TEMP\*.VHDX</span></span> <br>
> <span data-ttu-id="29d84-192">\\net\share \* \* 的 storageaccount。VHD</span><span class="sxs-lookup"><span data-stu-id="29d84-192">\\storageaccount.file.core.windows.net\share\*\*.VHD</span></span> <br>
> <span data-ttu-id="29d84-193">\\net\share \* \* 的 storageaccount。.VHDX</span><span class="sxs-lookup"><span data-stu-id="29d84-193">\\storageaccount.file.core.windows.net\share\*\*.VHDX</span></span> <br>

<span data-ttu-id="29d84-194">**排除處理常式：**</span><span class="sxs-lookup"><span data-stu-id="29d84-194">**Exclude Processes:**</span></span>

> <span data-ttu-id="29d84-195">%ProgramFiles% \FSLogix\Apps\frxccd.exe</span><span class="sxs-lookup"><span data-stu-id="29d84-195">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span></span> <br>
> <span data-ttu-id="29d84-196">%ProgramFiles% \FSLogix\Apps\frxccds.exe</span><span class="sxs-lookup"><span data-stu-id="29d84-196">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span></span> <br>
> <span data-ttu-id="29d84-197">%ProgramFiles% \FSLogix\Apps\frxsvc.exe</span><span class="sxs-lookup"><span data-stu-id="29d84-197">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span></span> <br>

#### <a name="licensing-requirements"></a><span data-ttu-id="29d84-198">授權需求</span><span class="sxs-lookup"><span data-stu-id="29d84-198">Licensing requirements</span></span> 

<span data-ttu-id="29d84-199">Windows 10 多重會話是用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="29d84-199">Windows 10 Multi-session is a client OS.</span></span> <span data-ttu-id="29d84-200">Microsoft Defender for endpoint 的授權需求可在下列位置找到： [授權要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="29d84-200">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>
