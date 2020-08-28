---
title: 自行註冊現有裝置
description: 登錄已重新使用的裝置，使其可由 Microsoft 受管理的電腦進行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289136"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="ea3ab-103">自行註冊現有裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="ea3ab-104">本主題說明重新使用已有的裝置的步驟，並在 Microsoft 受管理的電腦中註冊這些裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ea3ab-105">如果您正在使用全新的裝置，請依照直接在 [Microsoft 管理的桌面中註冊新裝置](register-devices-self.md) 中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="ea3ab-106">合作夥伴的程式會記錄在協力廠商，以 [供協力廠商註冊裝置](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="ea3ab-107">Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="ea3ab-108">您可以使用 Microsoft Managed Desktop Admin 入口網站來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="ea3ab-109">準備註冊現有的裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-109">Prepare to register existing devices</span></span>


<span data-ttu-id="ea3ab-110">若要註冊現有的裝置，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="ea3ab-111">取得每個裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="ea3ab-112">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="ea3ab-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="ea3ab-113">[在 Microsoft 受管理的電腦中註冊裝置](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="ea3ab-114">再次確認映像是否正確。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="ea3ab-115">交付裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="ea3ab-116">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="ea3ab-116">Obtain the hardware hash</span></span>

<span data-ttu-id="ea3ab-117">Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="ea3ab-118">您有四個選項可從您已在使用的裝置取得此資訊：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="ea3ab-119">請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="ea3ab-120">在 [Microsoft 端點 Configuration Manager](#microsoft-endpoint-configuration-manager)中收集資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="ea3ab-121">在每個裝置上使用 [Active Directory](#active-directory-powershell-script-method) 或 [手動](#manual-powershell-script-method) 執行 Windows PowerShell script--並收集檔案中的結果。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="ea3ab-122">啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ea3ab-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ea3ab-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="ea3ab-124">您可以使用 Microsoft 端點 Configuration Manager 來收集您要使用 Microsoft Managed Desktop 註冊的現有裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea3ab-125">您要取得此資訊的任何裝置都必須執行 Windows 10、版本1703或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="ea3ab-126">如果您已符合所有這些必要條件，您可以遵循下列步驟來收集資訊：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="ea3ab-127">在 Configuration Manager 主控台中，選取 [ **監視**]。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="ea3ab-128">在 [監視] 工作區中，展開 [ **報告** ] 節點、[ **報告**]，然後選取 [ **硬體-一般** ] 節點。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="ea3ab-129">執行報告、 **Windows Autopilot 裝置資訊**，以及查看結果。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="ea3ab-130">在報表檢視器中，選取 [ **匯出** ] 圖示，然後選擇 \*\*CSV (逗點分隔) \*\* ] 選項。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="ea3ab-131">儲存檔案之後，您必須將結果篩選為您計畫向 Microsoft Managed Desktop 註冊的裝置，並將資料上傳至 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)，然後在左功能窗格中選取 [ **裝置** ]。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="ea3ab-132">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="ea3ab-133">如需詳細資訊，請參閱 [使用系統管理入口網站的註冊裝置](#register-devices-by-using-the-admin-portal) 。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="ea3ab-134">Active Directory PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="ea3ab-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="ea3ab-135">在 Active Directory 環境中，您可以使用 `Get-WindowsAutoPilotInfo` PowerShell Cmdlet，以遠端從 Active Directory 群組中的裝置，使用 WinRM 來收集資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="ea3ab-136">您也可以使用 `Get-AD Computer` Cmdlet，取得目錄中所含特定硬體模型名稱的篩選結果。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="ea3ab-137">若要這麼做，請先確認這些必要條件，然後繼續執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="ea3ab-138">已啟用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-138">WinRM is enabled.</span></span>
- <span data-ttu-id="ea3ab-139">您想要註冊的裝置會在網路 (上使用，也就是說，它們並未中斷連線或關閉) 。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="ea3ab-140">請確定您擁有的網域認證參數具有在裝置上遠端執行的許可權。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="ea3ab-141">請確定 Windows 防火牆允許存取 WMI。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="ea3ab-142">若要這麼做，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="ea3ab-143">開啟 [ **Windows Defender 防火牆** ] 控制台，然後選取 [ **允許透過 Windows defender 防火牆的應用程式或功能**]。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="ea3ab-144">找到 \*\*Windows Management Instrumentation (WMI) \*\* 在清單中，啟用 [ **私人] 和 [公用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="ea3ab-145">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="ea3ab-146">請執行下列其中 *一個* 腳本：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="ea3ab-147">存取任何可能具有裝置專案的目錄。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="ea3ab-148">從 *所有* 目錄中移除每個裝置的專案，包括 Windows Server Active Directory 網域服務和 Azure Active directory。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="ea3ab-149">請注意，此移除動作可能需要數小時才能完成處理。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="ea3ab-150">存取管理服務，其中可能有裝置的專案。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="ea3ab-151">從 *所有* 管理服務（包括 Microsoft Endpoint Configuration Manager、Microsoft Intune 及 Windows Autopilot）中移除每個裝置的專案。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="ea3ab-152">請注意，此移除動作可能需要數小時才能完成處理。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="ea3ab-153">現在您可以繼續 [註冊裝置](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="ea3ab-154">手動 PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="ea3ab-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="ea3ab-155">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="ea3ab-156">執行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="ea3ab-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="ea3ab-157">執行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ea3ab-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="ea3ab-158">合併雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="ea3ab-159">快閃磁碟機方法</span><span class="sxs-lookup"><span data-stu-id="ea3ab-159">Flash drive method</span></span>

1. <span data-ttu-id="ea3ab-160">在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="ea3ab-161">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="ea3ab-162">執行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="ea3ab-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="ea3ab-163">開啟您要註冊的裝置，但*請勿開始設定體驗*。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="ea3ab-164">如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="ea3ab-165">插入 USB 磁碟機，然後按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="ea3ab-166">以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="ea3ab-167">執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="ea3ab-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="ea3ab-168">執行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ea3ab-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="ea3ab-169">移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="ea3ab-170">合併雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="ea3ab-171">在您完成註冊前，請勿開啟您所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="ea3ab-172">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="ea3ab-172">Merge hash data</span></span>

<span data-ttu-id="ea3ab-173">如果您是由手動 PowerShell 或快閃記憶體磁片磁碟機方法收集硬體雜湊資料，您現在必須將 CSV 檔案中的資料組合成單一檔案，才能完成註冊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="ea3ab-174">以下是讓註冊變輕鬆的範例 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="ea3ab-175">將雜湊資料合併到一個 CSV 檔案中，您現在可以繼續 [註冊裝置](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="ea3ab-176">使用管理入口網站註冊裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="ea3ab-177">從 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)的左側流覽窗格中，選取 [ **裝置** ]。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="ea3ab-178">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="ea3ab-179">[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="ea3ab-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="ea3ab-180">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-180">Follow these steps:</span></span>

1. <span data-ttu-id="ea3ab-181">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="ea3ab-182">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-182">Select **Register devices**.</span></span> <span data-ttu-id="ea3ab-183">系統會將裝置新增至 **裝置**上的裝置清單，並標示為 **AutopilotRegistrationRequested**。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="ea3ab-184">登錄所需的時間通常不會超過10分鐘，當成功時，裝置會顯示為已就緒，可供 **使用者** 使用，且等候使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="ea3ab-185">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="ea3ab-186">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="ea3ab-186">Possible states reported there include:</span></span>

| <span data-ttu-id="ea3ab-187">狀態</span><span class="sxs-lookup"><span data-stu-id="ea3ab-187">State</span></span> | <span data-ttu-id="ea3ab-188">描述</span><span class="sxs-lookup"><span data-stu-id="ea3ab-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="ea3ab-189">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="ea3ab-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="ea3ab-190">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-190">Registration is not done yet.</span></span> <span data-ttu-id="ea3ab-191">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-191">Check back later.</span></span> |
| <span data-ttu-id="ea3ab-192">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="ea3ab-192">Registration failed</span></span> | <span data-ttu-id="ea3ab-193">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-193">Registration could not be completed.</span></span> <span data-ttu-id="ea3ab-194">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="ea3ab-195">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="ea3ab-195">Ready for user</span></span> | <span data-ttu-id="ea3ab-196">註冊成功，裝置現在可以傳遞給使用者。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-196">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="ea3ab-197">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="ea3ab-198">作用中</span><span class="sxs-lookup"><span data-stu-id="ea3ab-198">Active</span></span> | <span data-ttu-id="ea3ab-199">裝置已傳遞給使用者，且已向您的承租人註冊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-199">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ea3ab-200">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="ea3ab-201">非作用中</span><span class="sxs-lookup"><span data-stu-id="ea3ab-201">Inactive</span></span> | <span data-ttu-id="ea3ab-202">裝置已傳遞給使用者，且已向您的承租人註冊。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ea3ab-203">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="ea3ab-204">針對裝置註冊進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="ea3ab-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="ea3ab-205">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="ea3ab-205">Error message</span></span> | <span data-ttu-id="ea3ab-206">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ea3ab-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="ea3ab-207">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-207">Device not found</span></span> | <span data-ttu-id="ea3ab-208">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="ea3ab-209">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="ea3ab-210">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="ea3ab-210">Hardware hash not valid</span></span> | <span data-ttu-id="ea3ab-211">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="ea3ab-212">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="ea3ab-213">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="ea3ab-213">Device already registered</span></span> | <span data-ttu-id="ea3ab-214">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-214">This device is already registered to your organization.</span></span> <span data-ttu-id="ea3ab-215">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-215">No further action required.</span></span> |
| <span data-ttu-id="ea3ab-216">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-216">Device claimed by another organization</span></span> | <span data-ttu-id="ea3ab-217">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="ea3ab-218">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="ea3ab-219">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="ea3ab-219">Unexpected error</span></span> | <span data-ttu-id="ea3ab-220">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="ea3ab-221">連絡客戶支援並提供要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="ea3ab-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="ea3ab-222">檢查映像</span><span class="sxs-lookup"><span data-stu-id="ea3ab-222">Check the image</span></span>

<span data-ttu-id="ea3ab-223">如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="ea3ab-224">如果您想要的話，也歡迎您自行套用映像。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="ea3ab-225">若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="ea3ab-226">交付裝置</span><span class="sxs-lookup"><span data-stu-id="ea3ab-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea3ab-227">將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="ea3ab-228">如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。</span><span class="sxs-lookup"><span data-stu-id="ea3ab-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









