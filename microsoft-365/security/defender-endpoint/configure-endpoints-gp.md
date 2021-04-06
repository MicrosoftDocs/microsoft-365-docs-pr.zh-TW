---
title: 透過群組原則將 Windows 10 裝置集成至 Microsoft Defender ATP
description: 使用群組原則在 Windows 10 裝置上部署設定套件，使其可架至服務。
keywords: 使用群組原則、裝置管理、設定 Windows ATP 裝置、板載 Microsoft Defender for Endpoint 裝置及群組原則來設定裝置
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: fc4b17ef96e85d3bacd4e83c2de3f4bb7fbfa5c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166165"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="909de-104">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="909de-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="909de-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="909de-105">**Applies to:**</span></span>

- <span data-ttu-id="909de-106">群組原則</span><span class="sxs-lookup"><span data-stu-id="909de-106">Group Policy</span></span>
- [<span data-ttu-id="909de-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="909de-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="909de-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="909de-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="909de-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="909de-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="909de-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="909de-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="909de-111">若要使用群組原則 (GP) 更新若要部署套件，您必須在 Windows Server 2008 R2 或更新版本上。</span><span class="sxs-lookup"><span data-stu-id="909de-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="909de-112">若為 Windows Server 2019，您可能需要使用「群組原則」偏好建立之 XML 檔案的 NT AUTHORITY\SYSTEM 取代 NT AUTHORITY\Well-Known-System-Account。</span><span class="sxs-lookup"><span data-stu-id="909de-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="909de-113">使用群組原則的板載裝置</span><span class="sxs-lookup"><span data-stu-id="909de-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="909de-114">[![顯示各種部署路徑的 PDF 影像](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="909de-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="909de-115">請取出 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  或  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。</span><span class="sxs-lookup"><span data-stu-id="909de-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="909de-116">從 [服務上架] 嚮導中，開啟已下載的 GP configuration 套件 .zip 檔案 (*WindowsDefenderATPOnboardingPackage.zip*) 。</span><span class="sxs-lookup"><span data-stu-id="909de-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="909de-117">您也可以從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得套件：</span><span class="sxs-lookup"><span data-stu-id="909de-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="909de-118">在功能窗格中，選取 [**設定**] [上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="909de-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="909de-119">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="909de-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="909de-120">在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。</span><span class="sxs-lookup"><span data-stu-id="909de-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="909de-121">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="909de-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="909de-122">將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。</span><span class="sxs-lookup"><span data-stu-id="909de-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="909de-123">您應該會有一個稱為 *OptionalParamsPolicy* 的資料夾，以及檔案 *WindowsDefenderATPOnboardingScript .cmd*。</span><span class="sxs-lookup"><span data-stu-id="909de-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="909de-124">開啟「 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="909de-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="909de-125">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]、[ **喜好** 設定] 及 [控制台 **設定**]。</span><span class="sxs-lookup"><span data-stu-id="909de-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="909de-126">以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即工作 (至少為 Windows 7)**。</span><span class="sxs-lookup"><span data-stu-id="909de-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="909de-127">在開啟的 **任務** 視窗中，移至 [**一般**] 索引標籤。在 [**安全性選項**] 底下，按一下 [**變更使用者或群組** 和類型系統]，然後按一下 [**檢查名稱** 然後按一下 **[確定]**</span><span class="sxs-lookup"><span data-stu-id="909de-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="909de-128">NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="909de-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="909de-129">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="909de-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="909de-130">移至 [**動作**] 索引標籤，然後按一下 [**新增 ...** ]確定 [**動作**] 欄位中已選取 [**啟動程式**]。</span><span class="sxs-lookup"><span data-stu-id="909de-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="909de-131">輸入共用 *WindowsDefenderATPOnboardingScript .cmd* 檔案的檔案名和位置。</span><span class="sxs-lookup"><span data-stu-id="909de-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="909de-132">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="909de-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="909de-133">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="909de-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="909de-134">如需詳細資訊，請參閱 [在新的架 Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="909de-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="909de-135">其他 Defender for Endpoint configuration 設定</span><span class="sxs-lookup"><span data-stu-id="909de-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="909de-136">針對每個裝置，您可以使用 Microsoft Defender Security Center 提交檔案進行深入分析時，判斷是否可以從裝置收集範例。</span><span class="sxs-lookup"><span data-stu-id="909de-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="909de-137">您可以使用「群組原則」 (GP) 設定設定，例如用於 deep analysis 功能的範例共用設定。</span><span class="sxs-lookup"><span data-stu-id="909de-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="909de-138">設定範例集合設定</span><span class="sxs-lookup"><span data-stu-id="909de-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="909de-139">在您的 GP 管理裝置上，從設定套件複製下列檔案：</span><span class="sxs-lookup"><span data-stu-id="909de-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="909de-140">將 _AtpConfiguration_ 複製到 _C： \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="909de-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="909de-141">將 _AtpConfiguration 複製 adml_ into _C： \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="909de-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="909de-142">如果您使用的是 [群組原則系統管理範本的中央存放區](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)，請從設定套件複製下列檔案：</span><span class="sxs-lookup"><span data-stu-id="909de-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="909de-143">將 _AtpConfiguration 中的 admx_ 複製到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 原則 \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="909de-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="909de-144">將 _AtpConfiguration_ 複製到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 原則 \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="909de-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="909de-145">開啟 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)，以滑鼠右鍵按一下您要設定的 GPO，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="909de-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="909de-146">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="909de-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="909de-147">按一下 [ **原則**]，然後按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="909de-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="909de-148">按一下 [ **windows 元件** ]，然後按一下 [ **windows Defender ATP**]。</span><span class="sxs-lookup"><span data-stu-id="909de-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="909de-149">選擇啟用或停用裝置的範例共用。</span><span class="sxs-lookup"><span data-stu-id="909de-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="909de-150">如果您未設定值，預設值為啟用範例集合。</span><span class="sxs-lookup"><span data-stu-id="909de-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="909de-151">其他建議的設定</span><span class="sxs-lookup"><span data-stu-id="909de-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="909de-152">更新 endpoint protection 設定</span><span class="sxs-lookup"><span data-stu-id="909de-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="909de-153">設定上架腳本後，請繼續編輯相同的群組原則，以新增 endpoint protection 設定。</span><span class="sxs-lookup"><span data-stu-id="909de-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="909de-154">從執行 Windows 10 或伺服器2019的系統執行群組原則編輯，以確保您具備所有必要的 Microsoft Defender 防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="909de-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="909de-155">您可能需要關閉並重新開啟群組原則物件，以登錄 Defender ATP 設定設定。</span><span class="sxs-lookup"><span data-stu-id="909de-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="909de-156">所有原則都位於 `Computer Configuration\Policies\Administrative Templates` 。</span><span class="sxs-lookup"><span data-stu-id="909de-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="909de-157">**原則位置：** \Windows \WINDOWS Defender ATP</span><span class="sxs-lookup"><span data-stu-id="909de-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="909de-158">原則</span><span class="sxs-lookup"><span data-stu-id="909de-158">Policy</span></span> | <span data-ttu-id="909de-159">設定</span><span class="sxs-lookup"><span data-stu-id="909de-159">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-160">Enable\Disable 範例集合</span><span class="sxs-lookup"><span data-stu-id="909de-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="909de-161">Enabled-「在機器上啟用範例集合」已檢查</span><span class="sxs-lookup"><span data-stu-id="909de-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="909de-162">**原則位置：**  \Windows \Windows Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="909de-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="909de-163">原則</span><span class="sxs-lookup"><span data-stu-id="909de-163">Policy</span></span> | <span data-ttu-id="909de-164">設定</span><span class="sxs-lookup"><span data-stu-id="909de-164">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-165">設定可能有害之應用程式的偵測</span><span class="sxs-lookup"><span data-stu-id="909de-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="909de-166">Enabled、Block</span><span class="sxs-lookup"><span data-stu-id="909de-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="909de-167">**原則位置：** \Windows \Windows Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="909de-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="909de-168">原則</span><span class="sxs-lookup"><span data-stu-id="909de-168">Policy</span></span> | <span data-ttu-id="909de-169">設定</span><span class="sxs-lookup"><span data-stu-id="909de-169">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-170">加入 Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="909de-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="909de-171">已啟用，高級地圖</span><span class="sxs-lookup"><span data-stu-id="909de-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="909de-172">需要進一步分析時傳送檔範例</span><span class="sxs-lookup"><span data-stu-id="909de-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="909de-173">已啟用，傳送安全範例</span><span class="sxs-lookup"><span data-stu-id="909de-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="909de-174">**原則位置：** \Windows \Windows Defender Antivirus\Real-time Protection</span><span class="sxs-lookup"><span data-stu-id="909de-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="909de-175">原則</span><span class="sxs-lookup"><span data-stu-id="909de-175">Policy</span></span> | <span data-ttu-id="909de-176">設定</span><span class="sxs-lookup"><span data-stu-id="909de-176">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-177">關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="909de-177">Turn off real-time protection</span></span>|<span data-ttu-id="909de-178">停用</span><span class="sxs-lookup"><span data-stu-id="909de-178">Disabled</span></span>
<span data-ttu-id="909de-179">開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="909de-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="909de-180">Enabled</span><span class="sxs-lookup"><span data-stu-id="909de-180">Enabled</span></span>
<span data-ttu-id="909de-181">掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="909de-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="909de-182">Enabled</span><span class="sxs-lookup"><span data-stu-id="909de-182">Enabled</span></span>
<span data-ttu-id="909de-183">監視電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="909de-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="909de-184">Enabled</span><span class="sxs-lookup"><span data-stu-id="909de-184">Enabled</span></span>

<br/>

<span data-ttu-id="909de-185">**原則位置：**  \Windows \Windows Defender Antivirus\Scan</span><span class="sxs-lookup"><span data-stu-id="909de-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="909de-186">這些設定會設定定期掃描端點。</span><span class="sxs-lookup"><span data-stu-id="909de-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="909de-187">建議您執行每週的快速掃描（效能允許）。</span><span class="sxs-lookup"><span data-stu-id="909de-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="909de-188">原則</span><span class="sxs-lookup"><span data-stu-id="909de-188">Policy</span></span> | <span data-ttu-id="909de-189">設定</span><span class="sxs-lookup"><span data-stu-id="909de-189">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-190">執行排程掃描之前，請先檢查是否有最新的病毒和間諜軟體安全性情報</span><span class="sxs-lookup"><span data-stu-id="909de-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="909de-191">Enabled</span><span class="sxs-lookup"><span data-stu-id="909de-191">Enabled</span></span>


<br/>

<span data-ttu-id="909de-192">**原則位置：** \Windows \Windows Defender Antivirus\Windows defender Exploit Guard\Attack Surface 減低</span><span class="sxs-lookup"><span data-stu-id="909de-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="909de-193">取得目前攻擊面減少 Guid 的清單，以 [自訂攻擊面降低規則](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="909de-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="909de-194">開啟 [ **設定攻擊面減少** 原則]。</span><span class="sxs-lookup"><span data-stu-id="909de-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="909de-195">選取 **已啟用**。</span><span class="sxs-lookup"><span data-stu-id="909de-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="909de-196">選取 [ **顯示** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="909de-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="909de-197">以值2將每個 GUID 新增至 [ **值名稱** ] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="909de-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="909de-198">這只會將每個設定為僅供審核。</span><span class="sxs-lookup"><span data-stu-id="909de-198">This will set each up for audit only.</span></span>

   ![攻擊面降低設定的影像](images/asr-guid.png)



<span data-ttu-id="909de-200">原則</span><span class="sxs-lookup"><span data-stu-id="909de-200">Policy</span></span> | <span data-ttu-id="909de-201">設定</span><span class="sxs-lookup"><span data-stu-id="909de-201">Setting</span></span> 
:---|:---
<span data-ttu-id="909de-202">設定受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="909de-202">Configure Controlled folder access</span></span>| <span data-ttu-id="909de-203">已啟用，稽核模式</span><span class="sxs-lookup"><span data-stu-id="909de-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="909de-204">使用群組原則的下架裝置</span><span class="sxs-lookup"><span data-stu-id="909de-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="909de-205">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="909de-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="909de-206">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="909de-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="909de-207">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="909de-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="909de-208">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="909de-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="909de-209">從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得脫離套件：</span><span class="sxs-lookup"><span data-stu-id="909de-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="909de-210">在功能窗格中，選取 [**設定**  >  **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="909de-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="909de-211">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="909de-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="909de-212">在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。</span><span class="sxs-lookup"><span data-stu-id="909de-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="909de-213">按一下 [ **下載套件** ] 並儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="909de-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="909de-214">將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。</span><span class="sxs-lookup"><span data-stu-id="909de-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="909de-215">您應該有一個名為 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="909de-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="909de-216">開啟「 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="909de-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="909de-217">在 [ **群組原則管理編輯器**] 中，移至 [電腦設定] **、** [ **喜好** 設定] 及 [控制台 **設定**]。</span><span class="sxs-lookup"><span data-stu-id="909de-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="909de-218">以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即** 工作]。</span><span class="sxs-lookup"><span data-stu-id="909de-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="909de-219">在開啟的 **任務** 視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項**] 底下，選擇 [ (BUILTIN\SYSTEM]) 的 [本機系統] 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="909de-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="909de-220">選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="909de-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="909de-221">移至 [**動作**] 索引標籤，然後按一下 [**新增 ...**]。確定 [**動作**] 欄位中已選取 [**啟動程式**]。</span><span class="sxs-lookup"><span data-stu-id="909de-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="909de-222">輸入共用  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 檔案的檔案名和位置。</span><span class="sxs-lookup"><span data-stu-id="909de-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="909de-223">按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。</span><span class="sxs-lookup"><span data-stu-id="909de-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="909de-224">脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="909de-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="909de-225">監視裝置設定</span><span class="sxs-lookup"><span data-stu-id="909de-225">Monitor device configuration</span></span>
<span data-ttu-id="909de-226">使用群組原則時，沒有任何選項可監視裝置上的原則部署。</span><span class="sxs-lookup"><span data-stu-id="909de-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="909de-227">監控可以直接在入口網站上進行，也可以使用不同的部署工具進行。</span><span class="sxs-lookup"><span data-stu-id="909de-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="909de-228">使用入口網站監視裝置</span><span class="sxs-lookup"><span data-stu-id="909de-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="909de-229">移至 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="909de-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="909de-230">按一下 [ **裝置清單**]。</span><span class="sxs-lookup"><span data-stu-id="909de-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="909de-231">驗證裝置是否出現。</span><span class="sxs-lookup"><span data-stu-id="909de-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="909de-232">在 [ **裝置] 清單** 上，裝置開始顯示可能需要幾天。</span><span class="sxs-lookup"><span data-stu-id="909de-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="909de-233">這包括將原則發佈至裝置所需的時間、使用者登入前所需的時間，以及結束報告端點所需的時間。</span><span class="sxs-lookup"><span data-stu-id="909de-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="909de-234">相關主題</span><span class="sxs-lookup"><span data-stu-id="909de-234">Related topics</span></span>
- [<span data-ttu-id="909de-235">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="909de-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="909de-236">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="909de-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="909de-237">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="909de-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="909de-238">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="909de-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="909de-239">在新架 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="909de-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="909de-240">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="909de-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)