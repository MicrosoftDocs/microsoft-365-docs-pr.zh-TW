---
title: 透過群組原則上線 Windows 10 裝置
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用群組原則在 Windows 10 裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893284"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="ef435-103">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="ef435-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ef435-104">**Applies to:**</span></span>

- [<span data-ttu-id="ef435-105">Microsoft 365端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="ef435-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="ef435-106">群組原則</span><span class="sxs-lookup"><span data-stu-id="ef435-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="ef435-107">若要使用群組原則 (GP) 更新若要部署套件，您必須位於 Windows Server 2008 R2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ef435-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="ef435-108">針對 Windows Server 2019，您可能需要將 nt AUTHORITY\Well-Known-System-Account 取代為群組原則喜好設定之 XML 檔案的 nt AUTHORITY\SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="ef435-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="ef435-109">使用群組原則將裝置上線</span><span class="sxs-lookup"><span data-stu-id="ef435-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="ef435-110">從服務上架嚮導中，開啟 (*DeviceComplianceOnboardingPackage.zip*) 的 GP configuration package .zip file。</span><span class="sxs-lookup"><span data-stu-id="ef435-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ef435-111">您也可以從[Microsoft 規範中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)取得套件</span><span class="sxs-lookup"><span data-stu-id="ef435-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="ef435-112">在功能窗格中，選取 [**設定**  >  **裝置上架**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="ef435-113">在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="ef435-114">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="ef435-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ef435-115">將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。</span><span class="sxs-lookup"><span data-stu-id="ef435-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="ef435-116">您應該會有一個稱為 *OptionalParamsPolicy* 的資料夾，以及檔案 *DeviceComplianceLocalOnboardingScript .cmd*。</span><span class="sxs-lookup"><span data-stu-id="ef435-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="ef435-117">開啟「 [群組原則管理主控台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="ef435-118">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]、[ **喜好** 設定] 及 [控制台 **設定**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="ef435-119">以滑鼠右鍵按一下 [**排程任務**]，指向 [**新增**]，然後按一下 [**立即工作 (至少 Windows 7)**。</span><span class="sxs-lookup"><span data-stu-id="ef435-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="ef435-120">在開啟的 **任務** 視窗中，移至 [**一般**] 索引標籤。在 [**安全性選項**] 底下，按一下 [**變更使用者或群組** 和類型系統]，然後按一下 [**檢查名稱** 然後按一下 **[確定]**</span><span class="sxs-lookup"><span data-stu-id="ef435-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="ef435-121">NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef435-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="ef435-122">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ef435-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="ef435-123">移至 [**動作**] 索引標籤，然後按一下 [**新增 ...** ]確定 [**動作**] 欄位中已選取 [**啟動程式**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="ef435-124">輸入共用 *WindowsDefenderATPOnboardingScript .cmd* 檔案的檔案名和位置。</span><span class="sxs-lookup"><span data-stu-id="ef435-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="ef435-125">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="ef435-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="ef435-126">使用群組原則的下架裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="ef435-127">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="ef435-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ef435-128">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="ef435-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="ef435-129">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="ef435-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="ef435-130">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="ef435-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="ef435-131">從 [Microsoft 規範中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)取得脫離套件。</span><span class="sxs-lookup"><span data-stu-id="ef435-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="ef435-132">在功能窗格中，選取 [**設定**  >  **//Device 上架**  >  **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="ef435-133">在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="ef435-134">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="ef435-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ef435-135">將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。</span><span class="sxs-lookup"><span data-stu-id="ef435-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="ef435-136">您應該有一個名為 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="ef435-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="ef435-137">開啟「 [群組原則管理主控台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="ef435-138">在 [ **群組原則管理編輯器**] 中，移至 [電腦設定] **、** [ **喜好** 設定] 及 [控制台 **設定**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="ef435-139">以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即** 工作]。</span><span class="sxs-lookup"><span data-stu-id="ef435-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="ef435-140">在開啟的 **任務** 視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項**] 底下，選擇 [ (BUILTIN\SYSTEM]) 的 [本機系統] 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef435-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="ef435-141">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ef435-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="ef435-142">移至 [**動作**] 索引標籤，然後按一下 [**新增 ...**]。確定 [**動作**] 欄位中已選取 [**啟動程式**]。</span><span class="sxs-lookup"><span data-stu-id="ef435-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="ef435-143">輸入共用  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 檔案的檔案名和位置。</span><span class="sxs-lookup"><span data-stu-id="ef435-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="ef435-144">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="ef435-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef435-145">脫離會導致裝置停止將感應器資料傳送至入口網站，但從裝置資料。</span><span class="sxs-lookup"><span data-stu-id="ef435-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="ef435-146">監視裝置設定</span><span class="sxs-lookup"><span data-stu-id="ef435-146">Monitor device configuration</span></span>
<span data-ttu-id="ef435-147">使用群組原則時，沒有任何選項可監視裝置上的原則部署。</span><span class="sxs-lookup"><span data-stu-id="ef435-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="ef435-148">監控可以直接在入口網站上進行，也可以使用不同的部署工具進行。</span><span class="sxs-lookup"><span data-stu-id="ef435-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="ef435-149">使用入口網站監視裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="ef435-150">移至 [Microsoft 規範中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ef435-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="ef435-151">按一下 [ **裝置** 清單]。</span><span class="sxs-lookup"><span data-stu-id="ef435-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="ef435-152">驗證裝置是否出現。</span><span class="sxs-lookup"><span data-stu-id="ef435-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="ef435-153">在 [ **裝置] 清單** 上，裝置開始顯示可能需要幾天。</span><span class="sxs-lookup"><span data-stu-id="ef435-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="ef435-154">這包括將原則發佈至裝置所需的時間、使用者登入前所需的時間，以及結束報告端點所需的時間。</span><span class="sxs-lookup"><span data-stu-id="ef435-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ef435-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="ef435-155">Related topics</span></span>
- [<span data-ttu-id="ef435-156">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="ef435-157">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="ef435-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ef435-158">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="ef435-159">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="ef435-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="ef435-160">在新架 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="ef435-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="ef435-161">疑難排解 Microsoft Defender 進階威脅防護上架問題</span><span class="sxs-lookup"><span data-stu-id="ef435-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)