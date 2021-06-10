---
title: 上線非持續 Virtual Desktop Infrastructure (VDI) 裝置
description: 在虛擬桌面基礎結構 (VDI) 裝置上部署設定套件，使其架至 Microsoft Defender for Endpoint service。
keywords: 設定虛擬桌面基礎結構 (VDI) 裝置、VDI、裝置管理、設定 Microsoft Defender for 端點、端點
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843207"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e40fe-104">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e40fe-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e40fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="e40fe-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e40fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e40fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e40fe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="e40fe-108">虛擬桌面基礎結構 (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="e40fe-109">Windows 10，Windows server 2019，Windows Server nm-winserver-2008r2-2nd/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="e40fe-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="e40fe-110">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e40fe-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e40fe-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e40fe-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e40fe-112">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="e40fe-113">用於端點的 Defender 支援非持續性的 VDI 會話上架。</span><span class="sxs-lookup"><span data-stu-id="e40fe-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="e40fe-114">上架 VDIs 時，可能會有相關的難題。</span><span class="sxs-lookup"><span data-stu-id="e40fe-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="e40fe-115">以下是此案例的常見挑戰：</span><span class="sxs-lookup"><span data-stu-id="e40fe-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="e40fe-116">立即上架短暫的會話，必須在實際布建之前，架至端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="e40fe-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="e40fe-117">裝置名稱通常會針對新的會話重複使用。</span><span class="sxs-lookup"><span data-stu-id="e40fe-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="e40fe-118">在端點入口網站中，VDI 裝置可以出現為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="e40fe-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="e40fe-119">每個裝置單一專案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e40fe-120">在此情況下，您必須在建立會話時設定 *相同* 的裝置名稱，例如使用無人值守的回應檔案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="e40fe-121">每個裝置的多個專案-每個會話一個。</span><span class="sxs-lookup"><span data-stu-id="e40fe-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="e40fe-122">下列步驟會引導您完成上架 VDI 裝置，並將會反白顯示單一和多個專案的步驟。</span><span class="sxs-lookup"><span data-stu-id="e40fe-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="e40fe-123">在資源設定較低的環境中，VDI 引導程式可能會降低端點感應器上架的 Defender 速度。</span><span class="sxs-lookup"><span data-stu-id="e40fe-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="e40fe-124">Windows 10 或 Windows 伺服器2019</span><span class="sxs-lookup"><span data-stu-id="e40fe-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="e40fe-125">從服務上架嚮導中，開啟 .zip 檔案 (*WindowsDefenderATPOnboardingPackage.zip*) 的 VDI 設定套件。</span><span class="sxs-lookup"><span data-stu-id="e40fe-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e40fe-126">您也可以從[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)取得套件：</span><span class="sxs-lookup"><span data-stu-id="e40fe-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="e40fe-127">在功能窗格中，選取 [**設定** 上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="e40fe-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="e40fe-128">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="e40fe-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="e40fe-129">在 [ **部署方法** ] 欄位中，選取 **非持續端點的 VDI 上架腳本**。</span><span class="sxs-lookup"><span data-stu-id="e40fe-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="e40fe-130">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="e40fe-131">將 WindowsDefenderATPOnboardingPackage 資料夾中解壓縮的檔案從 .zip 檔複製到路徑底下的 `golden/master` 圖像中 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="e40fe-132">如果您未針對每個裝置實施單一專案，請複製 WindowsDefenderATPOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="e40fe-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="e40fe-133">若要針對每個裝置實施單一專案，請同時複製 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="e40fe-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e40fe-134">如果您看不到 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 資料夾，它可能是隱藏的。</span><span class="sxs-lookup"><span data-stu-id="e40fe-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="e40fe-135">您必須選擇 [從檔案瀏覽器 **顯示隱藏的檔案和資料夾** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e40fe-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="e40fe-136">開啟 [本機群組原則編輯器] 視窗，並流覽至 [**電腦** 設定  >  **Windows 設定**  >  **腳本**  >  **啟動**]。</span><span class="sxs-lookup"><span data-stu-id="e40fe-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e40fe-137">網域群組原則也可用於上架非持續性的 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="e40fe-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="e40fe-138">請根據您想要執行的方法，遵循適當的步驟：</span><span class="sxs-lookup"><span data-stu-id="e40fe-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="e40fe-139">針對每個裝置的單一專案：</span><span class="sxs-lookup"><span data-stu-id="e40fe-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="e40fe-140">選取 [ **PowerShell 腳本**] 索引標籤，然後按一下 [**新增** (] Windows Explorer 會直接開啟您在先前複製上架腳本的路徑中) 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e40fe-141">流覽至上架 PowerShell script `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="e40fe-142">不需要指定另一個檔案，因為會自動觸發該檔案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="e40fe-143">針對每個裝置的多個專案：</span><span class="sxs-lookup"><span data-stu-id="e40fe-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="e40fe-144">選取 [**腳本**] 索引標籤，然後按一下 [**新增** (] Windows Explorer 會直接開啟您在先前複製上架腳本的路徑中) 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e40fe-145">流覽至上架 bash 腳本 `WindowsDefenderATPOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="e40fe-146">測試您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="e40fe-146">Test your solution:</span></span>

   1. <span data-ttu-id="e40fe-147">建立具有一個裝置的集區。</span><span class="sxs-lookup"><span data-stu-id="e40fe-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="e40fe-148">登入裝置。</span><span class="sxs-lookup"><span data-stu-id="e40fe-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="e40fe-149">從裝置登出。</span><span class="sxs-lookup"><span data-stu-id="e40fe-149">Logoff from device.</span></span>

   1. <span data-ttu-id="e40fe-150">使用另一位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="e40fe-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="e40fe-151">請根據您想要執行的方法，遵循適當的步驟：</span><span class="sxs-lookup"><span data-stu-id="e40fe-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="e40fe-152">針對每個裝置的單一專案：</span><span class="sxs-lookup"><span data-stu-id="e40fe-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="e40fe-153">只檢查 Microsoft Defender 資訊安全中心中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="e40fe-154">針對每個裝置的多個專案：</span><span class="sxs-lookup"><span data-stu-id="e40fe-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="e40fe-155">檢查 Microsoft Defender 資訊安全中心中的多個專案。</span><span class="sxs-lookup"><span data-stu-id="e40fe-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="e40fe-156">按一下功能窗格上的 [ **裝置] 清單** 。</span><span class="sxs-lookup"><span data-stu-id="e40fe-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="e40fe-157">輸入裝置名稱並選取 [ **裝置** ] 作為搜尋類型，即可使用搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="e40fe-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="e40fe-158">對於下層 SKUs</span><span class="sxs-lookup"><span data-stu-id="e40fe-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="e40fe-159">只有當瞄準是針對每個裝置建立單一專案時，才會與下列登錄相關。</span><span class="sxs-lookup"><span data-stu-id="e40fe-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="e40fe-160">將登錄值設定為：</span><span class="sxs-lookup"><span data-stu-id="e40fe-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="e40fe-161">或者使用命令列：</span><span class="sxs-lookup"><span data-stu-id="e40fe-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="e40fe-162">遵循 [伺服器上架](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)程式。</span><span class="sxs-lookup"><span data-stu-id="e40fe-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="e40fe-163">更新非持久性虛擬桌面基礎結構 (VDI) 影像</span><span class="sxs-lookup"><span data-stu-id="e40fe-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="e40fe-164">建議的最佳作法是使用離線服務工具來修補黃金/主映射。</span><span class="sxs-lookup"><span data-stu-id="e40fe-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="e40fe-165">例如，您可以使用下列命令來安裝更新，讓影像保持離線狀態：</span><span class="sxs-lookup"><span data-stu-id="e40fe-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="e40fe-166">如需 DISM 命令和離線服務的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e40fe-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="e40fe-167">使用 DISM 修改 Windows 影像</span><span class="sxs-lookup"><span data-stu-id="e40fe-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="e40fe-168">DISM 影像管理 Command-Line 選項</span><span class="sxs-lookup"><span data-stu-id="e40fe-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="e40fe-169">縮小離線 Windows 影像中的元件存放區大小</span><span class="sxs-lookup"><span data-stu-id="e40fe-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="e40fe-170">如果離線服務不是非持續性的 VDI 環境可行的選項，應採取下列步驟，以確保一致性及感應器的健全狀況：</span><span class="sxs-lookup"><span data-stu-id="e40fe-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="e40fe-171">在啟動線上服務或修補的主映射後，請執行脫離腳本，以關閉端點感應器的 Defender。</span><span class="sxs-lookup"><span data-stu-id="e40fe-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="e40fe-172">如需詳細資訊，請參閱 [使用本機腳本的下架裝置](configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="e40fe-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="e40fe-173">在 CMD 視窗中執行下列命令，以確定感應器已停止：</span><span class="sxs-lookup"><span data-stu-id="e40fe-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="e40fe-174">視需要為影像服務。</span><span class="sxs-lookup"><span data-stu-id="e40fe-174">Service the image as needed.</span></span>

4. <span data-ttu-id="e40fe-175">使用下列 PsExec.exe (執行下列命令 https://download.sysinternals.com/files/PSTools.zip) ，以清理自啟動後，感應器可能已積累的網路資料夾內容：</span><span class="sxs-lookup"><span data-stu-id="e40fe-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="e40fe-176">照常重新密封黃金/主映射。</span><span class="sxs-lookup"><span data-stu-id="e40fe-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e40fe-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="e40fe-177">Related topics</span></span>
- [<span data-ttu-id="e40fe-178">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="e40fe-179">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="e40fe-180">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="e40fe-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="e40fe-181">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e40fe-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="e40fe-182">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="e40fe-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
