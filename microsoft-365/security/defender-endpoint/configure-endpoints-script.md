---
title: 使用本機指令碼上線 Windows 10 裝置
description: 使用本機腳本在裝置上部署設定套件，使其可架至服務。
keywords: 使用本機腳本、裝置管理、設定 Microsoft Defender for Endpoint 裝置設定裝置
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
ms.technology: mde
ms.openlocfilehash: 2510fb1a187bbe136669e11bc73103438b51d811
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842167"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="a96f1-104">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="a96f1-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a96f1-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a96f1-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a96f1-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a96f1-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a96f1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="a96f1-108">您也可以將個別裝置手動上架到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="a96f1-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="a96f1-109">在您認可如何在您的網路中上架所有裝置之前測試服務時，您可能會想要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a96f1-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a96f1-110">此腳本已優化，最多可用於10個裝置。</span><span class="sxs-lookup"><span data-stu-id="a96f1-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="a96f1-111">若要以規模部署，請使用 [其他部署選項](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="a96f1-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="a96f1-112">例如，您可以使用群組原則，將上架腳本部署至生產環境中的超過10個裝置，並使該腳本可用於[板載 Windows 10 裝置](configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="a96f1-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="a96f1-113">將裝置上線</span><span class="sxs-lookup"><span data-stu-id="a96f1-113">Onboard devices</span></span> 

<span data-ttu-id="a96f1-114">[![顯示各種部署路徑的 PDF 影像](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a96f1-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="a96f1-115">請取出[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。</span><span class="sxs-lookup"><span data-stu-id="a96f1-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="a96f1-116">從服務上架嚮導中，開啟 (*WindowsDefenderATPOnboardingPackage.zip*) 的 GP configuration package .zip file。</span><span class="sxs-lookup"><span data-stu-id="a96f1-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="a96f1-117">您也可以從[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)取得套件：</span><span class="sxs-lookup"><span data-stu-id="a96f1-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="a96f1-118">在功能窗格中，選取 [**設定** 上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="a96f1-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="a96f1-119">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="a96f1-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="a96f1-120">在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。</span><span class="sxs-lookup"><span data-stu-id="a96f1-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="a96f1-121">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="a96f1-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="a96f1-122">將設定套件的內容解壓至您要板載 (裝置上的位置（例如，桌面) ）。</span><span class="sxs-lookup"><span data-stu-id="a96f1-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="a96f1-123">您應該會有一個名為 *WindowsDefenderATPLocalOnboardingScript* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="a96f1-123">You should have a file named *WindowsDefenderATPLocalOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="a96f1-124">在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：</span><span class="sxs-lookup"><span data-stu-id="a96f1-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="a96f1-125">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="a96f1-126">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![指向以系統管理員身分執行的視窗「開始」功能表](images/run-as-admin.png)

4.  <span data-ttu-id="a96f1-128">輸入指令檔的位置。</span><span class="sxs-lookup"><span data-stu-id="a96f1-128">Type the location of the script file.</span></span> <span data-ttu-id="a96f1-129">如果您已將檔案複製到桌面，請輸入： *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="a96f1-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="a96f1-130">按 **enter** 鍵或按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="a96f1-131">如需如何手動驗證裝置是否符合及正確報告感應器資料的相關資訊，請參閱 [疑難排解 Microsoft Defender For Endpoint 上架問題](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="a96f1-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="a96f1-132">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="a96f1-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="a96f1-133">如需詳細資訊，請參閱 [在新架的 Microsoft Defender For endpoint 端點上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="a96f1-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="a96f1-134">設定範例集合設定</span><span class="sxs-lookup"><span data-stu-id="a96f1-134">Configure sample collection settings</span></span>
<span data-ttu-id="a96f1-135">針對每個裝置，您可以設定設定值，以指出是否可以在要求透過 Microsoft Defender 資訊安全中心提交檔案進行深層分析時，從裝置收集範例。</span><span class="sxs-lookup"><span data-stu-id="a96f1-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="a96f1-136">您可以使用 *regedit* 來手動設定裝置的範例共用設定，或建立及執行 *.reg* 檔案。</span><span class="sxs-lookup"><span data-stu-id="a96f1-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="a96f1-137">設定是透過下列登錄機碼專案設定的：</span><span class="sxs-lookup"><span data-stu-id="a96f1-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="a96f1-138">其中：</span><span class="sxs-lookup"><span data-stu-id="a96f1-138">Where:</span></span><br>
<span data-ttu-id="a96f1-139">名稱類型為 D-字。</span><span class="sxs-lookup"><span data-stu-id="a96f1-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="a96f1-140">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="a96f1-140">Possible values are:</span></span>
- <span data-ttu-id="a96f1-141">0-不允許從此裝置共用範例</span><span class="sxs-lookup"><span data-stu-id="a96f1-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="a96f1-142">1-允許共用此裝置的所有檔案類型</span><span class="sxs-lookup"><span data-stu-id="a96f1-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="a96f1-143">當登錄機碼不存在時的預設值為1。</span><span class="sxs-lookup"><span data-stu-id="a96f1-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="a96f1-144">使用本機腳本的下架裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-144">Offboard devices using a local script</span></span>
<span data-ttu-id="a96f1-145">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="a96f1-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a96f1-146">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="a96f1-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="a96f1-147">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="a96f1-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a96f1-148">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="a96f1-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a96f1-149">從[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)取得脫離套件：</span><span class="sxs-lookup"><span data-stu-id="a96f1-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="a96f1-150">在功能窗格中，選取 [**設定**  >  **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="a96f1-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="a96f1-151">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="a96f1-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="a96f1-152">在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。</span><span class="sxs-lookup"><span data-stu-id="a96f1-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="a96f1-153">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="a96f1-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="a96f1-154">將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。</span><span class="sxs-lookup"><span data-stu-id="a96f1-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="a96f1-155">您應該有一個名為 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="a96f1-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="a96f1-156">在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：</span><span class="sxs-lookup"><span data-stu-id="a96f1-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="a96f1-157">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="a96f1-158">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![指向以系統管理員身分執行的視窗「開始」功能表](images/run-as-admin.png)

4.  <span data-ttu-id="a96f1-160">輸入指令檔的位置。</span><span class="sxs-lookup"><span data-stu-id="a96f1-160">Type the location of the script file.</span></span> <span data-ttu-id="a96f1-161">如果您已將檔案複製到桌面，請輸入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*</span><span class="sxs-lookup"><span data-stu-id="a96f1-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="a96f1-162">按 **enter** 鍵或按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a96f1-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a96f1-163">脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="a96f1-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="a96f1-164">監視裝置設定</span><span class="sxs-lookup"><span data-stu-id="a96f1-164">Monitor device configuration</span></span>
<span data-ttu-id="a96f1-165">您可以遵循上 [架問題疑難排解](troubleshoot-onboarding.md) 中的不同驗證步驟，確認腳本已成功完成且代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="a96f1-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="a96f1-166">監視也可以直接在入口網站上進行，或是使用不同的部署工具來執行。</span><span class="sxs-lookup"><span data-stu-id="a96f1-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="a96f1-167">使用入口網站監視裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="a96f1-168">移至 Microsoft Defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="a96f1-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="a96f1-169">按一下 [ **裝置清單**]。</span><span class="sxs-lookup"><span data-stu-id="a96f1-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="a96f1-170">驗證裝置是否出現。</span><span class="sxs-lookup"><span data-stu-id="a96f1-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a96f1-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="a96f1-171">Related topics</span></span>
- [<span data-ttu-id="a96f1-172">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="a96f1-173">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="a96f1-174">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="a96f1-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="a96f1-175">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="a96f1-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="a96f1-176">在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="a96f1-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="a96f1-177">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="a96f1-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
