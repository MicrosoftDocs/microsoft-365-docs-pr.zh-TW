---
title: 板載非持久性虛擬桌面基礎結構 (VDI) 裝置
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 在虛擬桌面基礎結構 (VDI) 裝置上部署設定套件，使其架至 Microsoft 365 端點資料遺失防護服務。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769400"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="54fd2-103">板載非持久性虛擬桌面基礎結構 (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="54fd2-104">適用於： </span><span class="sxs-lookup"><span data-stu-id="54fd2-104">**Applies to:**</span></span>
- [<span data-ttu-id="54fd2-105">Microsoft 365 端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="54fd2-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="54fd2-106">虛擬桌面基礎結構 (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="54fd2-107">Windows 虛擬桌面的 Microsoft 365 端點資料遺失防護支援可支援單一會話案例。</span><span class="sxs-lookup"><span data-stu-id="54fd2-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="54fd2-108">目前不支援 Windows 虛擬桌面上的多重會話案例。</span><span class="sxs-lookup"><span data-stu-id="54fd2-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="54fd2-109">板載 VDI 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-109">Onboard VDI devices</span></span>

<span data-ttu-id="54fd2-110">Microsoft 365 端點資料遺失防護功能支援非持續性的 VDI 會話上架。</span><span class="sxs-lookup"><span data-stu-id="54fd2-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="54fd2-111">若要進行板載非持續的 VDI 會話，VDI 裝置必須在 Windows 10 1809 或更新版本上。</span><span class="sxs-lookup"><span data-stu-id="54fd2-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="54fd2-112">上架 VDIs 時，可能會有相關的難題。</span><span class="sxs-lookup"><span data-stu-id="54fd2-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="54fd2-113">以下是此案例的常見挑戰：</span><span class="sxs-lookup"><span data-stu-id="54fd2-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="54fd2-114">立即上架短暫的會話，在實際布建之前，必須架至 Microsoft 365 端點資料遺失防護。</span><span class="sxs-lookup"><span data-stu-id="54fd2-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="54fd2-115">裝置名稱通常會針對新的會話重複使用。</span><span class="sxs-lookup"><span data-stu-id="54fd2-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="54fd2-116">VDI 裝置可以出現在 Microsoft 365 規範中心，您可以：</span><span class="sxs-lookup"><span data-stu-id="54fd2-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="54fd2-117">每個裝置單一專案。</span><span class="sxs-lookup"><span data-stu-id="54fd2-117">Single entry for each device.</span></span>  
<span data-ttu-id="54fd2-118">請注意，在此情況下，建立會話時必須設定 *相同* 的裝置名稱，例如使用自動回應檔案。</span><span class="sxs-lookup"><span data-stu-id="54fd2-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="54fd2-119">每個裝置的多個專案-每個會話一個。</span><span class="sxs-lookup"><span data-stu-id="54fd2-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="54fd2-120">下列步驟會引導您完成上架 VDI 裝置，並將會反白顯示單一和多個專案的步驟。</span><span class="sxs-lookup"><span data-stu-id="54fd2-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="54fd2-121">對於資源設定低的環境，VDI 引導程式可能會降低 Microsoft 365 端點資料遺失防護上架的速度。</span><span class="sxs-lookup"><span data-stu-id="54fd2-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="54fd2-122">從服務上架嚮導中，開啟 [VDI 設定套件 .zip 檔案] ( *DeviceCompliancePackage.zip* 所下載的) 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="54fd2-123">在功能窗格中，選取 [ **設定** 裝置上架] 上  >  **Device onboarding**  >  **架** 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="54fd2-124">在 [ **部署方法** ] 欄位中，選取 **非持續端點的 VDI 上架腳本** 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="54fd2-125">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="54fd2-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="54fd2-126">將檔案從 .zip 檔案解壓縮至路徑底下的 DeviceCompliancePackage 資料夾中 `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="54fd2-127">如果您未針對每個裝置實施單一專案，請複製 DeviceComplianceOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="54fd2-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="54fd2-128">若要針對每個裝置實施單一專案，請同時複製 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="54fd2-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54fd2-129">如果您看不到 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 資料夾，它可能是隱藏的。</span><span class="sxs-lookup"><span data-stu-id="54fd2-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="54fd2-130">您必須選擇 [從檔案瀏覽器 **顯示隱藏的檔案和資料夾** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="54fd2-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="54fd2-131">開啟 [本機群組原則編輯器] 視窗，並流覽至 [ **電腦** 設定] [  >  **Windows 設定**  >  **腳本**  >  **啟動** ]。</span><span class="sxs-lookup"><span data-stu-id="54fd2-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="54fd2-132">網域群組原則也可用於上架非持續性的 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="54fd2-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="54fd2-133">請根據您想要執行的方法，遵循適當的步驟：</span><span class="sxs-lookup"><span data-stu-id="54fd2-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="54fd2-134">**每個裝置的單一專案**</span><span class="sxs-lookup"><span data-stu-id="54fd2-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="54fd2-135">選取 [ **PowerShell 腳本** ] 索引標籤，然後按一下 [ **新增** (Windows Explorer 會直接開啟您在先前複製上架腳本的路徑中) 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="54fd2-136">流覽至上架 PowerShell script `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="54fd2-137">**針對每個裝置的多個專案** ：</span><span class="sxs-lookup"><span data-stu-id="54fd2-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="54fd2-138">選取 [ **腳本** ] 索引標籤，然後按一下 [ **新增** ] (Windows Explorer 會直接在您先前複製上架腳本的路徑中開啟) 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="54fd2-139">流覽至上架 bash 腳本 `DeviceComplianceOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="54fd2-140">測試您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="54fd2-140">Test your solution:</span></span>

   1. <span data-ttu-id="54fd2-141">建立具有一個裝置的集區。</span><span class="sxs-lookup"><span data-stu-id="54fd2-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="54fd2-142">登入裝置。</span><span class="sxs-lookup"><span data-stu-id="54fd2-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="54fd2-143">從裝置登出。</span><span class="sxs-lookup"><span data-stu-id="54fd2-143">Logoff from device.</span></span>

   1. <span data-ttu-id="54fd2-144">使用另一位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="54fd2-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="54fd2-145">**針對每個裝置的單一專案** ：請檢查 Microsoft Defender Security Center 中只有一個專案。</span><span class="sxs-lookup"><span data-stu-id="54fd2-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="54fd2-146">**針對每個裝置的多個專案** ：檢查 Microsoft Defender Security Center 中的多個專案。</span><span class="sxs-lookup"><span data-stu-id="54fd2-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="54fd2-147">按一下功能窗格上的 [ **裝置] 清單** 。</span><span class="sxs-lookup"><span data-stu-id="54fd2-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="54fd2-148">輸入裝置名稱並選取 [ **裝置** ] 作為搜尋類型，即可使用搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="54fd2-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="54fd2-149">更新非持久性虛擬桌面基礎結構 (VDI) 影像</span><span class="sxs-lookup"><span data-stu-id="54fd2-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="54fd2-150">建議的最佳作法是使用離線服務工具來修補黃金/主映射。</span><span class="sxs-lookup"><span data-stu-id="54fd2-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="54fd2-151">例如，您可以使用下列命令來安裝更新，讓影像保持離線狀態：</span><span class="sxs-lookup"><span data-stu-id="54fd2-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="54fd2-152">如需 DISM 命令和離線服務的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="54fd2-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="54fd2-153">使用 DISM 修改 Windows 映像</span><span class="sxs-lookup"><span data-stu-id="54fd2-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="54fd2-154">DISM 影像管理 Command-Line 選項</span><span class="sxs-lookup"><span data-stu-id="54fd2-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="54fd2-155">縮小離線 Windows 映像中元件存放區的大小</span><span class="sxs-lookup"><span data-stu-id="54fd2-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="54fd2-156">如果離線服務不是非持續性的 VDI 環境可行的選項，應採取下列步驟，以確保一致性及感應器的健全狀況：</span><span class="sxs-lookup"><span data-stu-id="54fd2-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="54fd2-157">在啟動線上服務或修補的主映射後，請執行脫離腳本，關閉 Microsoft 365 端點資料遺失防護感應器。</span><span class="sxs-lookup"><span data-stu-id="54fd2-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="54fd2-158">如需詳細資訊，請參閱 [使用本機腳本的下架裝置](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="54fd2-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="54fd2-159">在 CMD 視窗中執行下列命令，以確定感應器已停止：</span><span class="sxs-lookup"><span data-stu-id="54fd2-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="54fd2-160">視需要為影像服務。</span><span class="sxs-lookup"><span data-stu-id="54fd2-160">Service the image as needed.</span></span>

4. <span data-ttu-id="54fd2-161">使用下列 PsExec.exe (執行下列命令 https://download.sysinternals.com/files/PSTools.zip) ，以清理自啟動後，感應器可能已積累的網路資料夾內容：</span><span class="sxs-lookup"><span data-stu-id="54fd2-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="54fd2-162">照常重新密封黃金/主映射。</span><span class="sxs-lookup"><span data-stu-id="54fd2-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54fd2-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="54fd2-163">Related topics</span></span>
- [<span data-ttu-id="54fd2-164">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="54fd2-165">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="54fd2-166">使用行動裝置管理工具的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="54fd2-167">使用本機腳本的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="54fd2-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="54fd2-168">疑難排解 Microsoft Defender 高級威脅防護上架問題</span><span class="sxs-lookup"><span data-stu-id="54fd2-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
