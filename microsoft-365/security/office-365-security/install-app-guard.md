---
title: '適用于系統管理員的 Office 365 應用程式防護 (公開預覽) '
keywords: application guard、protection、隔離、隔離的容器、硬體隔離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 取得最新的硬體隔離。 防止目前和新興的攻擊（如入侵或惡意連結）中斷員工生產力和企業安全性。
ms.openlocfilehash: d0a89e8f8874c9ad298bf862384019b9e1ace0bf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867371"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="db503-105">適用于系統管理員的 Office 的應用程式防護 (公開預覽) </span><span class="sxs-lookup"><span data-stu-id="db503-105">Application Guard for Office (public preview) for admins</span></span>


<span data-ttu-id="db503-106">**適用于：** Microsoft 365，Windows 10 企業版的 Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="db503-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

>[!IMPORTANT]
><span data-ttu-id="db503-107">有些資訊與 prereleased 產品有關，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="db503-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="db503-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="db503-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="db503-109">Microsoft Defender Application Guard for office (Application Guard) 協助防止不可信的檔案存取受信任的資源，讓您的企業安全地抵禦新的和新興的攻擊。</span><span class="sxs-lookup"><span data-stu-id="db503-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="db503-110">本文指導管理員如何針對 Office 的應用程式防護，設定可預覽的裝置。</span><span class="sxs-lookup"><span data-stu-id="db503-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="db503-111">它提供有關系統需求和安裝步驟的資訊，以便在裝置上啟用 Office 的應用程式防護功能。</span><span class="sxs-lookup"><span data-stu-id="db503-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db503-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="db503-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="db503-113">基本硬體需求</span><span class="sxs-lookup"><span data-stu-id="db503-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="db503-114">**CPU**：64位、4核心 (實體或虛擬) 、虛擬化擴充 (Intel VT-x 或 AMD-V) 、Core i5 對等建議或更高版本的建議</span><span class="sxs-lookup"><span data-stu-id="db503-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="db503-115">**實體記憶體**： 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="db503-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="db503-116">**硬碟**：系統磁片磁碟機上有 10 GB 的可用空間 (SSD 建議) </span><span class="sxs-lookup"><span data-stu-id="db503-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="db503-117">基本軟體需求</span><span class="sxs-lookup"><span data-stu-id="db503-117">Minimum software requirements</span></span>

* <span data-ttu-id="db503-118">**Windows 10**： Windows 10 Enterprise Edition，Client Build version 2004 (20H1) 組建19041</span><span class="sxs-lookup"><span data-stu-id="db503-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="db503-119">**Office**： Office Beta 通道組建版本 2008 16.0.13212 或更新版本</span><span class="sxs-lookup"><span data-stu-id="db503-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="db503-120">**更新套件**： Windows 10 累計每月安全性更新 [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782)</span><span class="sxs-lookup"><span data-stu-id="db503-120">**Update package**: Windows 10 cumulative monthly security updates [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782)</span></span> 

<span data-ttu-id="db503-121">如需詳細的系統需求，請參閱 [Microsoft Defender Application Guard 的系統需求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="db503-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="db503-122">若要深入瞭解 Office 測試人員預覽組建，請參閱 [部署 office 測試人員組建的快速入門](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="db503-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="db503-123">授權需求</span><span class="sxs-lookup"><span data-stu-id="db503-123">Licensing requirements</span></span>
* <span data-ttu-id="db503-124">Microsoft 365 E5 或 Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="db503-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="db503-125">部署 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="db503-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="db503-126">啟用適用于 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="db503-126">Enable Application Guard for Office</span></span>

1.  <span data-ttu-id="db503-127">下載及安裝 **Windows 10 累計每月安全性更新 KB4566782**。</span><span class="sxs-lookup"><span data-stu-id="db503-127">Download and install **Windows 10 cumulative monthly security updates KB4566782**.</span></span> 

2. <span data-ttu-id="db503-128">下載並安裝 [**Office 的應用程式防護功能啟用套件**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi)。</span><span class="sxs-lookup"><span data-stu-id="db503-128">Download and install [**Application Guard for Office Feature enablement package**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi).</span></span> <span data-ttu-id="db503-129">此套件會在 [ **電腦 Configuration\Administrative 範本**] 底下安裝名為 "KB4559004 Issue 001 Preview" 的群組原則。</span><span class="sxs-lookup"><span data-stu-id="db503-129">This package installs a group policy called "KB4559004 Issue 001 Preview" under **Computer Configuration\Administrative Templates**.</span></span> <span data-ttu-id="db503-130">將此群組原則設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="db503-130">Set this group policy  to **Enabled**.</span></span>
     <span data-ttu-id="db503-131">![本機群組原則編輯器](../../media/ag01-deploy.png)</span><span class="sxs-lookup"><span data-stu-id="db503-131">![Local Group Policy Editor](../../media/ag01-deploy.png)</span></span>

     ![KB4559004 Issue 001 預覽](../../media/ag02-deploy.png)

    <span data-ttu-id="db503-133">您也可以直接設定下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="db503-133">You can also directly set the following reg keys:</span></span> 
    
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 3457697930 /t REG_DWORD /d 1 
    ```
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 94539402 /t REG_DWORD /d 1 
    ```
    <span data-ttu-id="db503-134">然後，請執行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="db503-134">Then, run this PowerShell command:</span></span> 
    
    ```powershell
    Get-ScheduledTask -TaskName "ReconcileFeatures" -TaskPath "\Microsoft\Windows\Flighting\FeatureConfig\" | Start-ScheduledTask 
    ```

3.  <span data-ttu-id="db503-135">選取 [Windows 功能] 底下的 [ **Microsoft Defender 應用程式防護** ] 並選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="db503-135">Select **Microsoft Defender Application Guard** under Windows Features and select **OK**.</span></span> <span data-ttu-id="db503-136">啟用 Application Guard 功能時，會提示重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="db503-136">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="db503-137">您可以選擇 [現在] 或 [在步驟4之後重新開機]。</span><span class="sxs-lookup"><span data-stu-id="db503-137">You can choose to reboot now or after step 4.</span></span>

    ![顯示 AG 的 [Windows 功能] 對話方塊](../../media/ag03-deploy.png)
    
    <span data-ttu-id="db503-139">您也可以以系統管理員身分執行下列 PowerShell 命令，以啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="db503-139">The feature can also be enabled by running the following PowerShell command as administrator:</span></span> 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

4.  <span data-ttu-id="db503-140">在 [電腦設定] 系統管理範本的「管理模式」群組原則中尋找 Microsoft Defender Application Guard \*\* \\ \\ \\ microsoft defender application guard\*\*。</span><span class="sxs-lookup"><span data-stu-id="db503-140">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="db503-141">在 [選項為**2**或**3**時設定值]，然後選取 **[確定] 或 [套用]** ，以開啟此**原則。**</span><span class="sxs-lookup"><span data-stu-id="db503-141">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

    ![在受管理的模式中開啟 AG](../../media/ag04-deploy.png)
  
    <span data-ttu-id="db503-143">或者，您也可以設定對應的 CSP 原則：</span><span class="sxs-lookup"><span data-stu-id="db503-143">Alternatively, you can set the corresponding CSP policy:</span></span> 

    <span data-ttu-id="db503-144">OMA URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span><span class="sxs-lookup"><span data-stu-id="db503-144">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span></span><br><span data-ttu-id="db503-145">資料類型： **Integer** 
</span><span class="sxs-lookup"><span data-stu-id="db503-145">Data type: **Integer** 
</span></span><br><span data-ttu-id="db503-146">值： **2**</span><span class="sxs-lookup"><span data-stu-id="db503-146">Value: **2**</span></span>


5.  <span data-ttu-id="db503-147">重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="db503-147">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="db503-148">設定診斷 & 傳送完整資料的意見</span><span class="sxs-lookup"><span data-stu-id="db503-148">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="db503-149">此步驟可確保識別和修正問題所需的資料是在 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="db503-149">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="db503-150">請遵循下列步驟，在 Windows 裝置上啟用診斷：</span><span class="sxs-lookup"><span data-stu-id="db503-150">Follow these steps to enable diagnostics on your Windows device:</span></span>

1.  <span data-ttu-id="db503-151">開啟 [開始] 功能表中的 **設定** 。</span><span class="sxs-lookup"><span data-stu-id="db503-151">Open **Settings** from the Start menu.</span></span>

    ![[開始] 功能表](../../media/ag05-diagnostic.png)

2.  <span data-ttu-id="db503-153">在 [ **Windows 設定**] 上，選取 [ **隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="db503-153">On **Windows Settings**, select **Privacy**.</span></span>

    ![Windows 設定功能表](../../media/ag06-diagnostic.png)

3.  <span data-ttu-id="db503-155">在 [隱私權] 底下，選取 [ **診斷 & 回饋** ]，然後選取 [ **選用診斷資料**]。</span><span class="sxs-lookup"><span data-stu-id="db503-155">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

    ![診斷和回饋功能表](../../media/ag07a-diagnostic.png)

<span data-ttu-id="db503-157">如需設定 Windows 診斷設定的詳細資訊，請參閱設定 [組織中的 Windows 診斷資料](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="db503-157">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="db503-158">確認 Office 的應用程式防護已啟用且正常運作</span><span class="sxs-lookup"><span data-stu-id="db503-158">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="db503-159">確認已啟用 Office 的應用程式防護功能之後，在已部署原則的裝置上啟動 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="db503-159">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="db503-160">請確定已啟用 Office。</span><span class="sxs-lookup"><span data-stu-id="db503-160">Make sure Office is activated.</span></span> <span data-ttu-id="db503-161">您可能需要先使用您的工作身分識別來啟用 Office 產品。</span><span class="sxs-lookup"><span data-stu-id="db503-161">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="db503-162">若要確認 Office 的應用程式防護現在已啟用，請啟動 Word、Excel 或 PowerPoint，然後開啟不受信任的檔。</span><span class="sxs-lookup"><span data-stu-id="db503-162">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="db503-163">例如，您可以開啟從網際網路下載的檔或來自組織外部人員的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="db503-163">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="db503-164">在第一次啟動不受信任的檔案時，您可能會看到如下的 Office 閃屏畫面。</span><span class="sxs-lookup"><span data-stu-id="db503-164">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="db503-165">在啟動 Office 的應用程式防護，且正在開啟檔案時，它可能會顯示一段時間。</span><span class="sxs-lookup"><span data-stu-id="db503-165">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="db503-166">後續啟動不受信任的檔案應該會更快。</span><span class="sxs-lookup"><span data-stu-id="db503-166">Subsequent launches of untrusted files should be faster.</span></span>

![Office 應用程式啟動畫面](../../media/ag08-confirm.png)


<span data-ttu-id="db503-168">開啟檔案時，該檔案應該會顯示一些視覺標記，指出檔案已在 Office 的應用程式防護中開啟：</span><span class="sxs-lookup"><span data-stu-id="db503-168">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="db503-169">功能區中的標注</span><span class="sxs-lookup"><span data-stu-id="db503-169">A callout in the ribbon</span></span>

    ![顯示小型應用程式防護附注的 Doc 檔案](../../media/ag09-confirm.png)
* <span data-ttu-id="db503-171">在工作列中帶有盾牌的應用程式圖示</span><span class="sxs-lookup"><span data-stu-id="db503-171">The application icon with a shield in the taskbar</span></span> 

    ![工作列中的圖示](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a><span data-ttu-id="db503-173">設定 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="db503-173">Configure Application Guard for Office</span></span>
<span data-ttu-id="db503-174">Office 支援下列原則，可讓您設定 Office 應用程式防護的功能。</span><span class="sxs-lookup"><span data-stu-id="db503-174">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="db503-175">您可以透過「群組原則」或 Office cloud policy service 來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="db503-175">These policies can be configured through Group policies or through the Office cloud policy service.</span></span> 

>[!NOTE] 
> <span data-ttu-id="db503-176">這些原則即將推出。</span><span class="sxs-lookup"><span data-stu-id="db503-176">These policies will become available soon.</span></span>
><span data-ttu-id="db503-177">此外，設定這些原則也可以停用 Office 的應用程式防護中開啟檔案的某些功能。</span><span class="sxs-lookup"><span data-stu-id="db503-177">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

| <span data-ttu-id="db503-178">原則</span><span class="sxs-lookup"><span data-stu-id="db503-178">Policy</span></span>                                                                          | <span data-ttu-id="db503-179">描述</span><span class="sxs-lookup"><span data-stu-id="db503-179">Description</span></span>                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="db503-180">停用 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="db503-180">Disable Application Guard for Office</span></span>                                            | <span data-ttu-id="db503-181">啟用這個原則會強制 Word、Excel 及 PowerPoint 使用受保護的檢視隔離容器，而不是 Office 的應用程式防護。</span><span class="sxs-lookup"><span data-stu-id="db503-181">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="db503-182">這項原則可用於暫時停用 Office 的應用程式防護時，如果有問題仍可讓其啟用 Edge。</span><span class="sxs-lookup"><span data-stu-id="db503-182">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>                                  |
| <span data-ttu-id="db503-183">停用應用程式防護中開啟之檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="db503-183">Disable copy/paste for documents opened in Application Guard</span></span>                    | <span data-ttu-id="db503-184">啟用這個原則可防止使用者從 Office 應用程式防護中開啟的檔，將內容複寫並貼到在其外部開啟的檔中。</span><span class="sxs-lookup"><span data-stu-id="db503-184">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>                                                                                                                                   |
| <span data-ttu-id="db503-185">防止使用者移除檔上的應用程式防護保護</span><span class="sxs-lookup"><span data-stu-id="db503-185">Prevent users from removing Application Guard protection on files</span></span>               | <span data-ttu-id="db503-186">啟用此原則將會移除 Office 應用程式經驗) 中的選項 (，以停用應用程式防護保護或開啟應用程式防護之外的檔案。</span><span class="sxs-lookup"><span data-stu-id="db503-186">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <br><br><span data-ttu-id="db503-187">**附注：** 使用者仍可略過此原則，方法是手動移除檔案中的 web 標記，或是將檔移至信任位置。</span><span class="sxs-lookup"><span data-stu-id="db503-187">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span> |
| <span data-ttu-id="db503-188">限制從應用程式防護開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="db503-188">Restrict printing from documents opened in Application Guard</span></span>                    | <span data-ttu-id="db503-189">啟用此原則會限制使用者可以從 Office 的應用程式防護開啟的檔案列印的印表機。</span><span class="sxs-lookup"><span data-stu-id="db503-189">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="db503-190">例如，您可以使用這個原則來限制使用者只能列印為 PDF。</span><span class="sxs-lookup"><span data-stu-id="db503-190">For example, you can use this policy to restrict users to only print to PDF.</span></span>                              |
| <span data-ttu-id="db503-191">關閉在應用程式防護中開啟之檔的相機及麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="db503-191">Turn off camera and microphone access for documents opened in Application Guard</span></span> | <span data-ttu-id="db503-192">啟用此原則將會在 Office 的應用程式防護中移除對相機及麥克風的 Office 存取。</span><span class="sxs-lookup"><span data-stu-id="db503-192">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>                                                                                                                                                                                                     |
>[!NOTE] 
><span data-ttu-id="db503-193">下列原則將需要使用者登出並重新登入 Windows，才會生效：</span><span class="sxs-lookup"><span data-stu-id="db503-193">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
> 
> *  <span data-ttu-id="db503-194">停用應用程式防護中開啟之檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="db503-194">Disable copy/paste for documents opened in Application Guard</span></span>
>*  <span data-ttu-id="db503-195">限制在應用程式防護中開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="db503-195">Restrict printing for documents opened in Application Guard</span></span>
> *  <span data-ttu-id="db503-196">關閉在應用程式防護中開啟的檔的相機及麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="db503-196">Turn off camera and mic access to documents opened in Application Guard</span></span>


## <a name="submit-feedback"></a><span data-ttu-id="db503-197">提交意見反應</span><span class="sxs-lookup"><span data-stu-id="db503-197">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="db503-198">透過意見反應中心提交意見反應</span><span class="sxs-lookup"><span data-stu-id="db503-198">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="db503-199">如果您在啟動 Office 的應用程式防護時遇到任何問題，建議您透過意見反應中心提交您的意見反應：</span><span class="sxs-lookup"><span data-stu-id="db503-199">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1.  <span data-ttu-id="db503-200">開啟「 **回饋中樞」應用程式** 並登入。</span><span class="sxs-lookup"><span data-stu-id="db503-200">Open the **Feedback Hub app** and sign in.</span></span>

2.  <span data-ttu-id="db503-201">如果您在啟動應用程式防護時收到錯誤對話方塊，請在錯誤對話方塊中選取 [ **向 Microsoft 報告** ]，以啟動新的意見反應提交。</span><span class="sxs-lookup"><span data-stu-id="db503-201">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="db503-202">否則，請流覽至 <https://aka.ms/wdagoffice-fb> 以選取正確的應用程式防護類別類別，然後選取 [+ 在右上方 **新增新的意見** 反應]。</span><span class="sxs-lookup"><span data-stu-id="db503-202">Otherwise, navigate to <https://aka.ms/wdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3.  <span data-ttu-id="db503-203">若尚未填入您的意見反應摘要，請填入 **您的意見** 反應。</span><span class="sxs-lookup"><span data-stu-id="db503-203">Fill in the **Summarize your feedback** box if it isn’t already filled in for you.</span></span>

4.  <span data-ttu-id="db503-204">在 [ **詳細資料** ] 方塊中填入您所遇到問題的詳細描述以及您採取的步驟，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db503-204">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5.  <span data-ttu-id="db503-205">選取 [問題] 旁邊的氣泡。</span><span class="sxs-lookup"><span data-stu-id="db503-205">Select the bubble next to Problem.</span></span> <span data-ttu-id="db503-206">確定選取的類別為 **安全性和隱私權 \> Microsoft Defender 應用程式防護-Office**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db503-206">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6.  <span data-ttu-id="db503-207">選取 [ **新增**反應]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db503-207">Select **New feedback**, then **Next**.</span></span>

7.  <span data-ttu-id="db503-208">收集有關問題的追蹤：</span><span class="sxs-lookup"><span data-stu-id="db503-208">Collect traces about the issue:</span></span>

    1. <span data-ttu-id="db503-209">展開 [ **重新建立我的問題** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="db503-209">Expand the **Recreate my problem** tile.</span></span>

    2.  <span data-ttu-id="db503-210">如果您在執行應用程式防護時發生所遇到的問題，請開啟應用程式防護實例。</span><span class="sxs-lookup"><span data-stu-id="db503-210">If the issue you’re experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="db503-211">這樣做允許從應用程式防護容器內收集其他追蹤。</span><span class="sxs-lookup"><span data-stu-id="db503-211">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

    3.  <span data-ttu-id="db503-212">選取 [ **開始錄製** ] 並等候磚停止旋轉，並說 [ *停止錄製*]。</span><span class="sxs-lookup"><span data-stu-id="db503-212">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

    4.  <span data-ttu-id="db503-213">使用應用程式防護完全再現問題。</span><span class="sxs-lookup"><span data-stu-id="db503-213">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="db503-214">這可能包括嘗試啟動應用程式防護實例並等候失敗，或在執行中的應用程式防護實例中再現問題。</span><span class="sxs-lookup"><span data-stu-id="db503-214">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

    5.  <span data-ttu-id="db503-215">選取 [ **停止錄製** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="db503-215">Select the **Stop recording** tile.</span></span>

    6.  <span data-ttu-id="db503-216">保留任何執行中的應用程式防護實例/s 開啟，甚至在提交後的幾分鐘後，也可以收集容器診斷。</span><span class="sxs-lookup"><span data-stu-id="db503-216">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8.  <span data-ttu-id="db503-217">附加任何相關的螢幕擷取畫面或與問題相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="db503-217">Attach any relevant screenshots or files related to the problem.</span></span>

9.  <span data-ttu-id="db503-218">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="db503-218">Select **Submit**.</span></span>



### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="db503-219">透過 Office 客戶語音提交意見反應</span><span class="sxs-lookup"><span data-stu-id="db503-219">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="db503-220">您也可以從 Office 提交意見，如果在應用程式防護中開啟 Office 檔時會發生問題。</span><span class="sxs-lookup"><span data-stu-id="db503-220">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="db503-221">請參閱 [Office 預覽人員手冊](https://insider.office.com/handbook) 以取得意見反應。</span><span class="sxs-lookup"><span data-stu-id="db503-221">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a><span data-ttu-id="db503-222">與 Microsoft Defender ATP 和 Office ATP 整合</span><span class="sxs-lookup"><span data-stu-id="db503-222">Integration with Microsoft Defender ATP and Office ATP</span></span>

<span data-ttu-id="db503-223">適用于 Office 的應用程式防護會與 Microsoft Defender 高級威脅防護 (ATP) 整合，針對隔離環境中發生的惡意活動提供監控和警示。</span><span class="sxs-lookup"><span data-stu-id="db503-223">Application Guard for Office is integrated with Microsoft Defender Advance Threat Protection (ATP) to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="db503-224">Microsoft Defender ATP 是一種安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="db503-224">Microsoft Defender ATP is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="db503-225">如需此平臺的詳細資訊，請造訪 [Microsoft Defender 高級威脅防護](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 頁面。</span><span class="sxs-lookup"><span data-stu-id="db503-225">For more details about this platform, visit the [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="db503-226">深入瞭解在板載裝置上的此平臺上 [的板載裝置至 Microsoft DEFENDER ATP 服務](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="db503-226">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender ATP service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="db503-227">您也可以將 Office 365 ATP 設定為與 Microsoft Defender ATP 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="db503-227">You can also configure Office 365 ATP to work with Microsoft Defender ATP.</span></span> <span data-ttu-id="db503-228">請參閱將 [Office 365 Atp 整合至 Microsoft DEFENDER atp](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="db503-228">Refer to [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="db503-229">限制和考慮</span><span class="sxs-lookup"><span data-stu-id="db503-229">Limitations and considerations</span></span>

* <span data-ttu-id="db503-230">適用于 Office 的應用程式防護是一種限制模式，可隔離不受信任的公司資源、內部網路、使用者的身分識別，以及電腦上顯示的任意檔案。</span><span class="sxs-lookup"><span data-stu-id="db503-230">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="db503-231">因此，如果使用者嘗試存取對此類存取有相依性的功能（例如，從磁片上的本機檔案插入圖片），它會失敗，並產生如下所示的提示。</span><span class="sxs-lookup"><span data-stu-id="db503-231">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="db503-232">若要讓不可信的檔能夠存取受信任的資源，使用者必須從檔中移除 Application Guard protection。</span><span class="sxs-lookup"><span data-stu-id="db503-232">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

    ![對話方塊說可協助您保護安全，但無法使用此功能](../../media/ag10-limitations.png)

    >[!NOTE]    
    ><span data-ttu-id="db503-234">建議使用者只有在信任檔案及其來源或來源的位置時，才移除保護。</span><span class="sxs-lookup"><span data-stu-id="db503-234">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="db503-235">在 Office 的應用程式防護中，諸如宏和 ActiveX 控制項等檔中的作用中內容會停用。</span><span class="sxs-lookup"><span data-stu-id="db503-235">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="db503-236">使用者需要移除應用程式防護保護才能啟用 active 內容。</span><span class="sxs-lookup"><span data-stu-id="db503-236">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="db503-237">從網路共用或從 OneDrive OneDrive 共用的檔案，或從不同組織 SharePoint 線上的檔案開啟的不受信任檔案會在應用程式防護中開啟為唯讀。</span><span class="sxs-lookup"><span data-stu-id="db503-237">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="db503-238">使用者可以儲存這類檔案的本機副本，以繼續在容器中工作或移除保護，以直接使用原始檔案。</span><span class="sxs-lookup"><span data-stu-id="db503-238">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="db503-239">受資訊版權管理 (IRM 保護的檔案，) 會繼續在受保護的檢視中開啟。</span><span class="sxs-lookup"><span data-stu-id="db503-239">Files that are protected by Information Rights Management (IRM) continue to   open in Protected View.</span></span>
* <span data-ttu-id="db503-240">在使用者登入和登入或重新開機裝置後，Office 應用程式的 office 應用程式防護中的任何自訂功能都不會保留。</span><span class="sxs-lookup"><span data-stu-id="db503-240">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span> 

* <span data-ttu-id="db503-241">只有使用 UIA 架構的協助工具工具才能為 Office 的應用程式防護中開啟的檔案提供可存取的經驗。</span><span class="sxs-lookup"><span data-stu-id="db503-241">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="db503-242">安裝後第一次啟動應用程式防護時，必須具備網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="db503-242">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="db503-243">這是應用程式防護驗證授權所需的。</span><span class="sxs-lookup"><span data-stu-id="db503-243">This is required for Application Guard to validate the license.</span></span>
* <span data-ttu-id="db503-244">在檔的 [資訊] 區段中，[ *上次修改者* ] 屬性可能會以使用者的身分顯示 WDAGUtilityAccount。</span><span class="sxs-lookup"><span data-stu-id="db503-244">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="db503-245">這是在 Application Guard 中設定的匿名使用者，因為桌面使用者的身分識別不會在應用程式防護容器內共用。</span><span class="sxs-lookup"><span data-stu-id="db503-245">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span> 

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="db503-246">Application Guard 的效能優化</span><span class="sxs-lookup"><span data-stu-id="db503-246">Performance optimizations for Application Guard</span></span> 

<span data-ttu-id="db503-247">本節提供適用于 Office 的應用程式防護中所使用之效能優化的概述。</span><span class="sxs-lookup"><span data-stu-id="db503-247">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="db503-248">此資訊可協助系統管理員在啟用 Application Guard 時，向與 Office 效能或整體系統相關的使用者診斷報告。</span><span class="sxs-lookup"><span data-stu-id="db503-248">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span> 

<span data-ttu-id="db503-249">Application Guard 會使用虛擬容器，將不受信任的檔與系統隔離。</span><span class="sxs-lookup"><span data-stu-id="db503-249">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="db503-250">建立容器及設定應用程式防護容器以開啟 Office 檔的程式，在使用者開啟不受信任的檔時，可能會對使用者經驗造成負面影響的效能負荷。</span><span class="sxs-lookup"><span data-stu-id="db503-250">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span> 


<span data-ttu-id="db503-251">若要為使用者提供預期的檔案開啟體驗，Application Guard 會在系統上滿足下列試探法時，使用邏輯來預先建立容器：使用者已于過去28天內，于受保護的 View 或 Application Guard 中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="db503-251">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span> 

<span data-ttu-id="db503-252">當符合此啟發時，Office 會在使用者登入 Windows 後，預先為使用者建立應用程式防護容器。</span><span class="sxs-lookup"><span data-stu-id="db503-252">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="db503-253">當此預先建立作業進行中時，系統可能會經歷很低的效能。</span><span class="sxs-lookup"><span data-stu-id="db503-253">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="db503-254">這會在作業完成時立即解決。</span><span class="sxs-lookup"><span data-stu-id="db503-254">This will resolve as soon as the operation completes.</span></span> 


>[!NOTE] 
><span data-ttu-id="db503-255">用於預先建立容器的啟發所需的提示是由 Office 應用程式在使用者使用時產生。</span><span class="sxs-lookup"><span data-stu-id="db503-255">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="db503-256">若使用者在已啟用 Application Guard 的新系統上安裝 Office，除非使用者第一次在系統上開啟不受信任的檔，否則 Office 將不會預先建立容器。</span><span class="sxs-lookup"><span data-stu-id="db503-256">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="db503-257">使用者將會看到此第一個檔案在應用程式防護中所需的時間較長。</span><span class="sxs-lookup"><span data-stu-id="db503-257">The user will observe that this first file takes longer to open in Application Guard.</span></span> 

## <a name="known-issues-in-preview"></a><span data-ttu-id="db503-258">預覽中的已知問題</span><span class="sxs-lookup"><span data-stu-id="db503-258">Known issues in preview</span></span>

* <span data-ttu-id="db503-259">按一下 [網頁連結] (```http``` 或 ```https```) 並不會開啟瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="db503-259">Clicking on web links (```http``` or ```https```) does not open the browser.</span></span> 
* <span data-ttu-id="db503-260">.NET 更新導致檔無法在應用程式防護中開啟。</span><span class="sxs-lookup"><span data-stu-id="db503-260">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="db503-261">作為變通方法，當您遇到此問題時，使用者可以重新開機其裝置。</span><span class="sxs-lookup"><span data-stu-id="db503-261">As a workaround, users can reboot their device when this issue is encountered.</span></span>
    <span data-ttu-id="db503-262">深入瞭解 [當嘗試開啟 Windows Defender 應用程式防護或 Windows 沙箱時，收到錯誤訊息時](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)，有關問題的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="db503-262">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>