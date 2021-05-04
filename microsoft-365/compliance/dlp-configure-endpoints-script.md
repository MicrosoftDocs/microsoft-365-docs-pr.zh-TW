---
title: 使用本機指令碼上線 Windows 10 裝置
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
description: 使用本機腳本在裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893304"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="86750-103">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="86750-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="86750-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="86750-104">**Applies to:**</span></span>

- [<span data-ttu-id="86750-105">Microsoft 365端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="86750-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="86750-106">您也可以手動上架個別裝置，以 Microsoft 365 端點資料遺失防護。</span><span class="sxs-lookup"><span data-stu-id="86750-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="86750-107">在您認可如何在您的網路中上架所有裝置之前測試服務時，您可能會想要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="86750-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86750-108">此腳本已優化，最多可用於10個裝置。</span><span class="sxs-lookup"><span data-stu-id="86750-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="86750-109">若要以規模部署，請使用 [其他部署選項](dlp-configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="86750-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="86750-110">例如，您可以使用群組原則，將上架腳本部署至生產環境中的超過10個裝置，並使該腳本可用於[板載 Windows 10 裝置](dlp-configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="86750-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="86750-111">將裝置上線</span><span class="sxs-lookup"><span data-stu-id="86750-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="86750-112">從服務上架嚮導中，開啟 (*DeviceComplianceOnboardingPackage.zip*) 的 GP configuration package .zip file。</span><span class="sxs-lookup"><span data-stu-id="86750-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="86750-113">您也可以從[Microsoft 規範中心](https://compliance.microsoft.com)取得套件</span><span class="sxs-lookup"><span data-stu-id="86750-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="86750-114">在功能窗格中，選取 [**設定**  >  **裝置上架**]。</span><span class="sxs-lookup"><span data-stu-id="86750-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="86750-115">在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。</span><span class="sxs-lookup"><span data-stu-id="86750-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="86750-116">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="86750-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="86750-117">將設定套件的內容解壓至您要板載 (裝置上的位置（例如，桌面) ）。</span><span class="sxs-lookup"><span data-stu-id="86750-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="86750-118">您應該會有一個名為 *DeviceOnboardingScript* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="86750-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="86750-119">在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：</span><span class="sxs-lookup"><span data-stu-id="86750-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="86750-120">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="86750-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="86750-121">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="86750-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![指向以系統管理員身分執行的視窗「開始」功能表](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="86750-123">輸入指令檔的位置。</span><span class="sxs-lookup"><span data-stu-id="86750-123">Type the location of the script file.</span></span> <span data-ttu-id="86750-124">如果您已將檔案複製到桌面，請輸入： *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="86750-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="86750-125">按 **enter** 鍵或按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86750-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="86750-126">如需如何手動驗證裝置是否符合及正確報告感應器資料的詳細資訊，請參閱。 [Microsoft Defender 進階威脅防護上架問題進行疑難排解](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="86750-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="86750-127">使用本機腳本的下架裝置</span><span class="sxs-lookup"><span data-stu-id="86750-127">Offboard devices using a local script</span></span>
<span data-ttu-id="86750-128">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="86750-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="86750-129">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="86750-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="86750-130">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="86750-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="86750-131">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="86750-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="86750-132">從[Microsoft 規範中心](https://compliance.microsoft.com)取得脫離套件</span><span class="sxs-lookup"><span data-stu-id="86750-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="86750-133">在功能窗格中，選取 [**設定**  >  **裝置脫離**]。</span><span class="sxs-lookup"><span data-stu-id="86750-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="86750-134">在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。</span><span class="sxs-lookup"><span data-stu-id="86750-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="86750-135">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="86750-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="86750-136">將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。</span><span class="sxs-lookup"><span data-stu-id="86750-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="86750-137">您應該有一個名為 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="86750-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="86750-138">在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：</span><span class="sxs-lookup"><span data-stu-id="86750-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="86750-139">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="86750-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="86750-140">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="86750-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![指向以系統管理員身分執行的視窗「開始」功能表](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="86750-142">輸入指令檔的位置。</span><span class="sxs-lookup"><span data-stu-id="86750-142">Type the location of the script file.</span></span> <span data-ttu-id="86750-143">如果您已將檔案複製到桌面，請輸入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*</span><span class="sxs-lookup"><span data-stu-id="86750-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="86750-144">按 **enter** 鍵或按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86750-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86750-145">脫離會導致裝置停止將感應器資料傳送至入口網站。</span><span class="sxs-lookup"><span data-stu-id="86750-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="86750-146">監視裝置設定</span><span class="sxs-lookup"><span data-stu-id="86750-146">Monitor device configuration</span></span>
<span data-ttu-id="86750-147">您可以遵循 [疑難排解上架問題] ( (中的不同驗證步驟， https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 驗證腳本是否順利完成，且代理程式正在執行中。</span><span class="sxs-lookup"><span data-stu-id="86750-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="86750-148">監視也可以直接在入口網站上進行，或是使用不同的部署工具來執行。</span><span class="sxs-lookup"><span data-stu-id="86750-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="86750-149">使用入口網站監視裝置</span><span class="sxs-lookup"><span data-stu-id="86750-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="86750-150">移至[Microsoft 365 規範中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="86750-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="86750-151">選擇 [**設定**  >  **裝置上架**  >  **裝置**。</span><span class="sxs-lookup"><span data-stu-id="86750-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="86750-152">驗證裝置是否出現。</span><span class="sxs-lookup"><span data-stu-id="86750-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="86750-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="86750-153">Related topics</span></span>
- [<span data-ttu-id="86750-154">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="86750-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="86750-155">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="86750-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="86750-156">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="86750-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="86750-157">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="86750-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="86750-158">在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="86750-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="86750-159">疑難排解 Microsoft Defender 進階威脅防護上架問題</span><span class="sxs-lookup"><span data-stu-id="86750-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)