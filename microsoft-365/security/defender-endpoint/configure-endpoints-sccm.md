---
title: 使用 Configuration Manager 上線 Windows 10 裝置
description: 使用 Configuration Manager 在裝置上部署設定套件，使其可架至服務。
keywords: 使用 sccm 的板載裝置，裝置管理，設定 Microsoft Defender for Endpoint 裝置
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: e919f697048840b0eb7bffd34914328fe233f823
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935158"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="e87ff-104">使用 Configuration Manager 上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e87ff-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e87ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="e87ff-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e87ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e87ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e87ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="e87ff-108">Microsoft 端點 Configuration Manager 目前的分支</span><span class="sxs-lookup"><span data-stu-id="e87ff-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="e87ff-109">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e87ff-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="e87ff-110">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e87ff-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e87ff-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e87ff-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="e87ff-112">支援的用戶端作業系統</span><span class="sxs-lookup"><span data-stu-id="e87ff-112">Supported client operating systems</span></span>

<span data-ttu-id="e87ff-113">根據您所執行的 Configuration Manager 版本，可以架下列用戶端作業系統：</span><span class="sxs-lookup"><span data-stu-id="e87ff-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="e87ff-114">Configuration Manager 版本1910及更早版本</span><span class="sxs-lookup"><span data-stu-id="e87ff-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="e87ff-115">執行 Windows 10 的用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="e87ff-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="e87ff-116">Configuration Manager 版本2002和更新版本</span><span class="sxs-lookup"><span data-stu-id="e87ff-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="e87ff-117">從 Configuration Manager 2002 版開始，您可以在下列作業系統上架上架：</span><span class="sxs-lookup"><span data-stu-id="e87ff-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="e87ff-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e87ff-118">Windows 8.1</span></span>
- <span data-ttu-id="e87ff-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e87ff-119">Windows 10</span></span>
- <span data-ttu-id="e87ff-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e87ff-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="e87ff-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e87ff-121">Windows Server 2016</span></span>
- <span data-ttu-id="e87ff-122">Windows Server 2016，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="e87ff-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="e87ff-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e87ff-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="e87ff-124">如需有關如何將 Windows Server 2012 R2、Windows Server 2016 及 Windows Server 2019 上架上的詳細資訊，請參閱 [板載 Windows](configure-server-endpoints.md)server。</span><span class="sxs-lookup"><span data-stu-id="e87ff-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="e87ff-125">使用 System Center Configuration Manager 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="e87ff-126">[![顯示各種部署路徑的 PDF 影像](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e87ff-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="e87ff-127">請取出 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  或  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Microsoft Defender for Endpoint 中的各種路徑。</span><span class="sxs-lookup"><span data-stu-id="e87ff-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="e87ff-128">從 [服務上架] 嚮導中，開啟您從 [服務上架] 的 [設定套件 .zip 檔案] (*WindowsDefenderATPOnboardingPackage.zip*) 。</span><span class="sxs-lookup"><span data-stu-id="e87ff-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e87ff-129">您也可以從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得套件：</span><span class="sxs-lookup"><span data-stu-id="e87ff-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="e87ff-130">在功能窗格中，選取 [**設定**] [上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="e87ff-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="e87ff-131">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="e87ff-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="e87ff-132">在 [ **部署方法** ] 欄位中，選取 **System Center Configuration Manager 2012/2012 R2/1511/1602**。</span><span class="sxs-lookup"><span data-stu-id="e87ff-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="e87ff-133">選取 [ **下載套件**]，然後儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="e87ff-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="e87ff-134">將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。</span><span class="sxs-lookup"><span data-stu-id="e87ff-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="e87ff-135">您應該會有一個名為 *WindowsDefenderATPOnboardingScript* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="e87ff-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="e87ff-136">遵循 [System Center 2012 R2 Configuration Manager 文章中的套件和程式](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步驟，部署套件。</span><span class="sxs-lookup"><span data-stu-id="e87ff-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="e87ff-137">a.</span><span class="sxs-lookup"><span data-stu-id="e87ff-137">a.</span></span> <span data-ttu-id="e87ff-138">選擇要將套件部署至其中的預先定義的裝置集合。</span><span class="sxs-lookup"><span data-stu-id="e87ff-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="e87ff-139">在 [) 全新體驗 (OOBE ](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 階段中，端點不支援上架。</span><span class="sxs-lookup"><span data-stu-id="e87ff-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="e87ff-140">請確定使用者在執行 Windows 安裝或升級後完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="e87ff-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="e87ff-141">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="e87ff-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="e87ff-142">如需詳細資訊，請參閱 [在新的架 Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="e87ff-143">請注意，您可以在 Configuration Manager 應用程式上建立偵測規則，以持續檢查裝置是否已架。</span><span class="sxs-lookup"><span data-stu-id="e87ff-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="e87ff-144">應用程式是不同于套件和程式的物件類型。</span><span class="sxs-lookup"><span data-stu-id="e87ff-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="e87ff-145">如果裝置尚未架 (由於是未決的 OOBE 完成或任何其他原因) ，Configuration Manager 會重試裝置上架裝置，直到規則偵測到狀態變更為止。</span><span class="sxs-lookup"><span data-stu-id="e87ff-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="e87ff-146">如果 "OnboardingState" 登錄值 (類型 REG_DWORD) = 1，則可以建立偵測規則檢查，以完成此行為。</span><span class="sxs-lookup"><span data-stu-id="e87ff-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="e87ff-147">此登錄值位於 "HKLM\SOFTWARE\Microsoft\Windows Advanced 威脅 Protection\Status" 底下。</span><span class="sxs-lookup"><span data-stu-id="e87ff-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="e87ff-148">如需詳細資訊，請參閱 [Configure 偵測方法 In System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="e87ff-149">設定範例集合設定</span><span class="sxs-lookup"><span data-stu-id="e87ff-149">Configure sample collection settings</span></span>

<span data-ttu-id="e87ff-150">針對每個裝置，您可以設定設定值，以指出當您透過 Microsoft Defender Security Center 提交檔案進行深入分析時，是否可以從裝置收集範例。</span><span class="sxs-lookup"><span data-stu-id="e87ff-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="e87ff-151">這些設定設定通常是透過 Configuration Manager 進行。</span><span class="sxs-lookup"><span data-stu-id="e87ff-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="e87ff-152">您可以為 Configuration Manager 中的設定專案設定符合性規則，以變更裝置上的範例共用設定。</span><span class="sxs-lookup"><span data-stu-id="e87ff-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="e87ff-153">此規則應該是 *修正* 相容性規則設定專案，它會在目標裝置上設定登錄機碼的值，以確定他們的投訴。</span><span class="sxs-lookup"><span data-stu-id="e87ff-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="e87ff-154">設定是透過下列登錄機碼專案設定的：</span><span class="sxs-lookup"><span data-stu-id="e87ff-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="e87ff-155">其中：</span><span class="sxs-lookup"><span data-stu-id="e87ff-155">Where:</span></span><br>
<span data-ttu-id="e87ff-156">金鑰類型是 WORD。</span><span class="sxs-lookup"><span data-stu-id="e87ff-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="e87ff-157">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="e87ff-157">Possible values are:</span></span>
- <span data-ttu-id="e87ff-158">0-不允許從此裝置共用範例</span><span class="sxs-lookup"><span data-stu-id="e87ff-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="e87ff-159">1-允許共用此裝置的所有檔案類型</span><span class="sxs-lookup"><span data-stu-id="e87ff-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="e87ff-160">當登錄機碼不存在時的預設值為1。</span><span class="sxs-lookup"><span data-stu-id="e87ff-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="e87ff-161">如需 System Center Configuration Manager 合規性的詳細資訊，請參閱 [System center 2012 R2 Configuration Manager 中的規範設定簡介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="e87ff-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="e87ff-162">其他建議的設定</span><span class="sxs-lookup"><span data-stu-id="e87ff-162">Other recommended configuration settings</span></span>
<span data-ttu-id="e87ff-163">將裝置上架至服務後，請務必使用下列建議的設定設定，以充分運用包含的威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="e87ff-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="e87ff-164">裝置集合設定</span><span class="sxs-lookup"><span data-stu-id="e87ff-164">Device collection configuration</span></span>
<span data-ttu-id="e87ff-165">如果您使用端點設定管理員（版本2002或更新版本），您可以選擇拓寬部署以包含伺服器或低層次的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e87ff-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="e87ff-166">下一代保護設定</span><span class="sxs-lookup"><span data-stu-id="e87ff-166">Next generation protection configuration</span></span>
<span data-ttu-id="e87ff-167">建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="e87ff-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="e87ff-168">**掃描**</span><span class="sxs-lookup"><span data-stu-id="e87ff-168">**Scan**</span></span> <br>
- <span data-ttu-id="e87ff-169">掃描可移動儲存裝置（例如 USB 磁片磁碟機）：是</span><span class="sxs-lookup"><span data-stu-id="e87ff-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="e87ff-170">**即時保護**</span><span class="sxs-lookup"><span data-stu-id="e87ff-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="e87ff-171">啟用行為監視：是</span><span class="sxs-lookup"><span data-stu-id="e87ff-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="e87ff-172">在下載時和安裝之前，針對可能不需要的應用程式啟用防護：是</span><span class="sxs-lookup"><span data-stu-id="e87ff-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="e87ff-173">**Cloud Protection Service**</span><span class="sxs-lookup"><span data-stu-id="e87ff-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="e87ff-174">Cloud Protection Service 成員資格類型：高級成員資格</span><span class="sxs-lookup"><span data-stu-id="e87ff-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="e87ff-175">**攻擊面減少** 設定所有可用的規則以進行審核。</span><span class="sxs-lookup"><span data-stu-id="e87ff-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="e87ff-176">封鎖這些活動可能會中斷合法的商務程式。</span><span class="sxs-lookup"><span data-stu-id="e87ff-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="e87ff-177">最佳方法是設定要審核的內容，識別哪些專案可以安全地開啟，然後在沒有誤報的端點上啟用這些設定。</span><span class="sxs-lookup"><span data-stu-id="e87ff-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="e87ff-178">**網路保護**</span><span class="sxs-lookup"><span data-stu-id="e87ff-178">**Network protection**</span></span> <br>
<span data-ttu-id="e87ff-179">在啟用網路保護的「審核」或「封鎖模式」之前，請確定您已安裝反惡意軟體平臺更新，可從 [ [支援] 頁面](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)取得。</span><span class="sxs-lookup"><span data-stu-id="e87ff-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="e87ff-180">**受控資料夾存取權**</span><span class="sxs-lookup"><span data-stu-id="e87ff-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="e87ff-181">至少30天內啟用 [稽核模式] 中的功能。</span><span class="sxs-lookup"><span data-stu-id="e87ff-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="e87ff-182">在此期間之後，請複查偵測，並建立允許寫入受保護目錄的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="e87ff-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="e87ff-183">如需詳細資訊，請參閱 [評估受控資料夾存取權](evaluate-controlled-folder-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="e87ff-184">使用 Configuration Manager 的下架裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="e87ff-185">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="e87ff-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="e87ff-186">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="e87ff-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="e87ff-187">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="e87ff-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="e87ff-188">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="e87ff-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="e87ff-189">使用 Microsoft 端點管理員的下架裝置目前的分支</span><span class="sxs-lookup"><span data-stu-id="e87ff-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="e87ff-190">如果您使用 Microsoft 端點管理員的 [目前] 分支，請參閱 [建立脫離設定檔](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="e87ff-191">使用 System Center 2012 R2 Configuration Manager 下架裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="e87ff-192">從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得脫離套件：</span><span class="sxs-lookup"><span data-stu-id="e87ff-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="e87ff-193">在功能窗格中，選取 [**設定**  >   **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="e87ff-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="e87ff-194">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="e87ff-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="e87ff-195">在 [ **部署方法** ] 欄位中，選取 **System Center Configuration Manager 2012/2012 R2/1511/1602**。</span><span class="sxs-lookup"><span data-stu-id="e87ff-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="e87ff-196">選取 [ **下載套件**]，然後儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="e87ff-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="e87ff-197">將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。</span><span class="sxs-lookup"><span data-stu-id="e87ff-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="e87ff-198">您應該有一個名為 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="e87ff-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="e87ff-199">遵循 [System Center 2012 R2 Configuration Manager 文章中的套件和程式](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步驟，部署套件。</span><span class="sxs-lookup"><span data-stu-id="e87ff-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="e87ff-200">a.</span><span class="sxs-lookup"><span data-stu-id="e87ff-200">a.</span></span> <span data-ttu-id="e87ff-201">選擇要將套件部署至其中的預先定義的裝置集合。</span><span class="sxs-lookup"><span data-stu-id="e87ff-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e87ff-202">脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="e87ff-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="e87ff-203">監視裝置設定</span><span class="sxs-lookup"><span data-stu-id="e87ff-203">Monitor device configuration</span></span>

<span data-ttu-id="e87ff-204">如果您使用的是 Microsoft 端點管理員目前的分支，請在 Configuration Manager 主控台中使用內建的 Defender for Endpoint 儀表板。</span><span class="sxs-lookup"><span data-stu-id="e87ff-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="e87ff-205">如需詳細資訊，請參閱 [適用于 Endpoint Monitor 的 Defender](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-205">For more information, see [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="e87ff-206">如果您使用的是 System Center 2012 R2 Configuration Manager，監控會包含兩個部分：</span><span class="sxs-lookup"><span data-stu-id="e87ff-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="e87ff-207">確認設定套件已正確部署，且正在執行 (或已在您的網路上的裝置上成功執行) 。</span><span class="sxs-lookup"><span data-stu-id="e87ff-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="e87ff-208">檢查裝置是否符合 Endpoint service 的 Defender service (這樣可確保裝置能夠完成上架程式，並且可以繼續向服務) 報告資料。</span><span class="sxs-lookup"><span data-stu-id="e87ff-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="e87ff-209">確認已正確部署設定套件</span><span class="sxs-lookup"><span data-stu-id="e87ff-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="e87ff-210">在 Configuration Manager 主控台中，按一下功能窗格底部的 [ **監視** ]。</span><span class="sxs-lookup"><span data-stu-id="e87ff-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="e87ff-211">選取 **[概述** ]，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="e87ff-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="e87ff-212">使用套件名稱，選取 [部署]。</span><span class="sxs-lookup"><span data-stu-id="e87ff-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="e87ff-213">檢查 [ **完成統計資料]** 和 [ **內容狀態**] 底下的狀態指示器。</span><span class="sxs-lookup"><span data-stu-id="e87ff-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="e87ff-214">如果部署失敗 (裝置 **發生錯誤**、 **未滿足需求**，或「 **失敗的狀態** 」) ，您可能需要對裝置進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="e87ff-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="e87ff-215">如需詳細資訊，請參閱 [疑難排解 Microsoft Defender For Endpoint 上架問題](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="e87ff-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![顯示沒有錯誤之成功部署的 Configuration Manager](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="e87ff-217">檢查裝置是否符合 Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="e87ff-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="e87ff-218">您可以設定 System Center 2012 R2 Configuration Manager 中設定專案的符合性規則，以監視您的部署。</span><span class="sxs-lookup"><span data-stu-id="e87ff-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="e87ff-219">此規則應該 *是非補救* 性規則設定專案，可監視目標裝置上之登錄機碼的值。</span><span class="sxs-lookup"><span data-stu-id="e87ff-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="e87ff-220">監視下列登錄機碼專案：</span><span class="sxs-lookup"><span data-stu-id="e87ff-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="e87ff-221">如需詳細資訊，請參閱 [System Center 2012 R2 Configuration Manager 中的規範設定簡介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="e87ff-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e87ff-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="e87ff-222">Related topics</span></span>
- [<span data-ttu-id="e87ff-223">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="e87ff-224">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="e87ff-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="e87ff-225">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="e87ff-226">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="e87ff-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="e87ff-227">在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="e87ff-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="e87ff-228">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="e87ff-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
