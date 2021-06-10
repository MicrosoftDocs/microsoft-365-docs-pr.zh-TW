---
title: 適用于系統管理員的 Office 365 應用程式防護
keywords: application guard、protection、隔離、隔離的容器、硬體隔離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 取得最新的硬體隔離。 防止目前和新興的攻擊（如入侵或惡意連結）中斷員工生產力和企業安全性。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488308"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="5d7c6-105">適用于系統管理員的 Office 應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="5d7c6-106">**適用于：** Word、Excel 及 Microsoft 365 PowerPoint，Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="5d7c6-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="5d7c6-107">Microsoft Defender 應用程式防護 for Office (Application Guard for Office) 協助防止不可信的檔案存取受信任的資源，讓您的企業安全地抵禦新的和新興的攻擊。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="5d7c6-108">本文指導管理員如何針對 Office 的應用程式防護，設定可預覽的裝置。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-109">它提供有關系統需求和安裝步驟的資訊，以便在裝置上啟用 Office 的應用程式防護。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d7c6-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="5d7c6-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="5d7c6-111">最低硬體需求</span><span class="sxs-lookup"><span data-stu-id="5d7c6-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="5d7c6-112">**CPU**：64位、4核心 (實體或虛擬) 、虛擬化擴充 (Intel VT-x 或 AMD-V) 、Core i5 對等建議或更高版本的建議</span><span class="sxs-lookup"><span data-stu-id="5d7c6-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="5d7c6-113">**實體記憶體**： 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="5d7c6-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="5d7c6-114">**硬碟**：系統磁片磁碟機上有 10 GB 的可用空間 (SSD 建議) </span><span class="sxs-lookup"><span data-stu-id="5d7c6-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="5d7c6-115">基本軟體需求</span><span class="sxs-lookup"><span data-stu-id="5d7c6-115">Minimum software requirements</span></span>

* <span data-ttu-id="5d7c6-116">**Windows 10**： Windows 10 企業版 edition，用戶端組建版本 2004 (20H1) 組建19041或更新版本</span><span class="sxs-lookup"><span data-stu-id="5d7c6-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="5d7c6-117">**Office**： Office 目前通道和每月 Enterprise 通道，組建版本 2011 16.0.13530.10000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-117">**Office**: Office Current Channel and Monthly Enterprise Channel, Build version 2011 16.0.13530.10000 or later.</span></span> <span data-ttu-id="5d7c6-118">支援32位和64位版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-118">Both 32-bit and 64-bit versions of Office are supported.</span></span>
* <span data-ttu-id="5d7c6-119">**更新套件**： Windows 10 累計每月安全性更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="5d7c6-119">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="5d7c6-120">如需詳細的系統需求，請參閱[Microsoft Defender 應用程式防護的系統需求](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-120">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="5d7c6-121">此外，請參閱電腦製造商的指南，以瞭解如何啟用虛擬化技術。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-121">Also, please refer to your computer manufacturer's guides on how to enable virtualization technology.</span></span>
<span data-ttu-id="5d7c6-122">若要深入瞭解 Office 更新通道，請參閱[Microsoft 365 的更新通道](/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-122">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="5d7c6-123">授權需求</span><span class="sxs-lookup"><span data-stu-id="5d7c6-123">Licensing requirements</span></span>

* <span data-ttu-id="5d7c6-124">Microsoft 365 E5 或 Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="5d7c6-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="5d7c6-125">為 Office 部署應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="5d7c6-126">啟用 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="5d7c6-127">下載和安裝 **Windows 10 累計每月安全性更新 KB4571756**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="5d7c6-128">選取 [Windows 功能] 底下的 **Microsoft Defender 應用程式防護**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="5d7c6-129">啟用 Application Guard 功能時，會提示重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="5d7c6-130">您可以選擇 [現在] 或 [在步驟3之後重新開機]。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-130">You can choose to reboot now or after step 3.</span></span>

   ![Windows顯示 AG 的 [功能] 對話方塊](../../media/ag03-deploy.png)

   <span data-ttu-id="5d7c6-132">您也可以以系統管理員身分執行下列 PowerShell 命令，以啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="5d7c6-133">在「**受管理模式**」中搜尋 Microsoft Defender 應用程式防護，在 [電腦設定系統管理範本] 中的群組原則 **\\ \\ Windows 元件 \\ Microsoft Defender 應用程式防護**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-133">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="5d7c6-134">將 [選項] 底下的值設定為 [ **2** ] 或 [ **3**]，然後選取 **[確定] 或 [套用]** ，以開啟此原則。 </span><span class="sxs-lookup"><span data-stu-id="5d7c6-134">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![在受管理的模式中開啟 AG](../../media/ag04-deploy.png)

   <span data-ttu-id="5d7c6-136">相反地，您可以設定對應的 CSP 原則：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-136">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="5d7c6-137">OMA URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/設定/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="5d7c6-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="5d7c6-138">資料類型： **Integer**</span><span class="sxs-lookup"><span data-stu-id="5d7c6-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="5d7c6-139">值： **2**</span><span class="sxs-lookup"><span data-stu-id="5d7c6-139">Value: **2**</span></span>

4. <span data-ttu-id="5d7c6-140">重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-140">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="5d7c6-141">設定診斷 & 傳送完整資料的意見</span><span class="sxs-lookup"><span data-stu-id="5d7c6-141">Set Diagnostics & feedback to send full data</span></span>

> [!NOTE]
> <span data-ttu-id="5d7c6-142">不過，這不是必要的，但設定選用的診斷資料將有助於診斷報告的問題。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-142">This is not required, however, configuring optional diagnostics data will help diagnose reported issues.</span></span>

<span data-ttu-id="5d7c6-143">此步驟可確保識別和修正問題所需的資料是在 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-143">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="5d7c6-144">請遵循下列步驟，在 Windows 裝置上啟用診斷：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-144">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="5d7c6-145">從 [開始] 功能表開啟 **設定**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-145">Open **Settings** from the Start menu.</span></span>

   ![[開始] 功能表](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="5d7c6-147">在 **Windows 設定** 上，選取 [**隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-147">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 設定功能表](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="5d7c6-149">在 [隱私權] 底下，選取 [ **診斷 & 回饋** ]，然後選取 [ **選用診斷資料**]。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-149">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![診斷和回饋功能表](../../media/ag07a-diagnostic.png)

<span data-ttu-id="5d7c6-151">如需設定 Windows 診斷設定的詳細資訊，請參閱設定[組織中的 Windows 診斷資料](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-151">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="5d7c6-152">確認已啟用並運作 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-152">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="5d7c6-153">確認已啟用 Office 的應用程式防護之前，請在已部署原則的裝置上啟動 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-153">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="5d7c6-154">請確定已啟用 Office。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-154">Make sure Office is activated.</span></span> <span data-ttu-id="5d7c6-155">您可能需要先使用您的工作身分識別來啟用 Office 產品。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-155">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="5d7c6-156">若要確認已啟用 Office 的應用程式防護，請啟動 Word、Excel 或 PowerPoint，然後開啟不受信任的檔。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-156">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="5d7c6-157">例如，您可以開啟從網際網路下載的檔或來自組織外部人員的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-157">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="5d7c6-158">當您第一次開啟不受信任的檔案時，您可能會看到 Office 閃屏，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-158">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="5d7c6-159">它可能會在啟用 Office 的應用程式防護，且正在開啟檔案時顯示。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-159">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="5d7c6-160">後續的不受信任檔案的開口應該會更快。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-160">Subsequent openings of untrusted files should be faster.</span></span>

![Office 應用程式閃屏](../../media/ag08-confirm.png)

<span data-ttu-id="5d7c6-162">開啟檔案時，檔案應該會顯示一些視覺標記，指出檔案已在 Office 的應用程式防護中開啟：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-162">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="5d7c6-163">功能區中的標注</span><span class="sxs-lookup"><span data-stu-id="5d7c6-163">A callout in the ribbon</span></span>

  ![顯示小型應用程式防護附注的 Doc 檔案](../../media/ag09-confirm.png)

* <span data-ttu-id="5d7c6-165">在工作列中帶有盾牌的應用程式圖示</span><span class="sxs-lookup"><span data-stu-id="5d7c6-165">The application icon with a shield in the taskbar</span></span>

  ![工作列中的圖示](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="5d7c6-167">設定 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-167">Configure Application Guard for Office</span></span>

<span data-ttu-id="5d7c6-168">Office 支援下列原則，可讓您設定 Office 應用程式防護的功能。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-168">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-169">這些原則可以透過「群組原則」或「 [Office 雲端原則服務](/DeployOffice/overview-office-cloud-policy-service)」加以設定。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-169">These policies can be configured through Group policies or through the [Office cloud policy service](/DeployOffice/overview-office-cloud-policy-service).</span></span>
<span data-ttu-id="5d7c6-170">在 [使用者設定系統管理範本] 中檢查群組原則設定，以查看系統管理員設定的設定 **\\ \\ Microsoft Office 2016 \\ Security 設定 \\ 信任中心 \\ 應用程式防護**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-170">See configuration set by your administrator by reviewing group policy settings in  **User Configuration\\Administrative Templates\\Microsoft Office 2016\\Security Settings\\Trust Center\\Application Guard**.</span></span>


> [!NOTE]
> <span data-ttu-id="5d7c6-171">設定這些原則之後，便可對 Office 的應用程式防護中開啟的檔案停用某些功能。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-171">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="5d7c6-172">原則</span><span class="sxs-lookup"><span data-stu-id="5d7c6-172">Policy</span></span>|<span data-ttu-id="5d7c6-173">描述</span><span class="sxs-lookup"><span data-stu-id="5d7c6-173">Description</span></span>|
|---|---|
|<span data-ttu-id="5d7c6-174">不使用適用于 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-174">Don't use Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-175">啟用這個原則會強制 Word、Excel 和 PowerPoint 使用受保護的檢視隔離容器，而不是應用程式的 Office 防護。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-175">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-176">這項原則可以用來暫時停用 Office 的應用程式防護，當您在 Microsoft Edge 中啟用它時，就會發生問題。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-176">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="5d7c6-177">為 Office 容器預先建立設定 Application Guard</span><span class="sxs-lookup"><span data-stu-id="5d7c6-177">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="5d7c6-178">這個原則會判斷是否已預先建立用於隔離不受信任檔案的 Office 容器的應用程式防護，以提升執行時間效能。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-178">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="5d7c6-179">如果您啟用此設定，您可以指定繼續建立容器的天數，或讓 Office 內建的啟發式預先建立容器。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-179">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="5d7c6-180">不允許複製/貼上用於 Office 應用程式防護中開啟的 Office 檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="5d7c6-180">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-181">啟用此原則可防止使用者將內容從在應用程式防護開啟的檔中複製及貼上，以 Office 至其外開啟的檔。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-181">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="5d7c6-182">停用 Office 的應用程式防護中的硬體加速</span><span class="sxs-lookup"><span data-stu-id="5d7c6-182">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-183">這個原則會控制 Office 的應用程式防護是否會使用硬體加速呈現圖形。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-183">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="5d7c6-184">如果您啟用此設定，則 Office 的應用程式防護會使用以軟體為基礎的 (CPU) 轉譯，而且不會載入任何協力廠商的圖形驅動程式，也不會與任何連接的圖形硬體互動。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-184">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="5d7c6-185">停用 Office 的應用程式防護中不支援的檔案類型保護</span><span class="sxs-lookup"><span data-stu-id="5d7c6-185">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-186">此原則會控制 Office 的應用程式防護是否會封鎖未支援的檔案類型，或是否要啟用重新導向至受保護的檢視。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-186">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="5d7c6-187">關閉在 Office 的應用程式防護中開啟之檔的相機和麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="5d7c6-187">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-188">啟用這個原則將會移除 Office 對 Office 的應用程式防護中的相機及麥克風的存取權。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-188">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="5d7c6-189">限制在 Office 的應用程式防護中開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="5d7c6-189">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="5d7c6-190">啟用此原則會限制使用者可以從在 Office 的應用程式防護中開啟的檔案列印的印表機。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-190">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-191">例如，您可以使用這個原則來限制使用者只能列印為 PDF。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-191">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="5d7c6-192">防止使用者移除應用程式防護，以保護檔案上的 Office 檔</span><span class="sxs-lookup"><span data-stu-id="5d7c6-192">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="5d7c6-193">啟用此原則會在 Office 應用程式經驗) 中移除 (選項，以停用 Office 保護的應用程式防護，或開啟 Office 應用程式防護之外的檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-193">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="5d7c6-194">**附注：** 使用者仍可略過此原則，方法是手動移除檔案中的 web 標記，或是將檔移至信任位置。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-194">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5d7c6-195">下列原則將需要使用者登出並重新登入，才能讓 Windows 生效：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-195">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="5d7c6-196">停用 Office 的應用程式防護中開啟之檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="5d7c6-196">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="5d7c6-197">限制為 Office 的應用程式防護開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="5d7c6-197">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="5d7c6-198">關閉為 Office 的應用程式防護開啟的檔的相機和麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="5d7c6-198">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="5d7c6-199">提交意見反應</span><span class="sxs-lookup"><span data-stu-id="5d7c6-199">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="5d7c6-200">透過意見反應中心提交意見反應</span><span class="sxs-lookup"><span data-stu-id="5d7c6-200">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="5d7c6-201">如果您在為 Office 啟動應用程式防護時遇到任何問題，建議您透過意見反應中樞提交您的意見反應：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-201">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="5d7c6-202">開啟「 **回饋中樞」應用程式** 並登入。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-202">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="5d7c6-203">如果您在啟動應用程式防護時收到錯誤對話方塊，請在錯誤對話方塊中選取 [ **向 Microsoft 報告** ]，以啟動新的意見反應提交。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-203">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="5d7c6-204">否則，請流覽至 <https://aka.ms/mdagoffice-fb> 以選取正確的應用程式防護類別類別，然後選取 [在右上方附近 **+ &nbsp; 新增新的意見** 反應]。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-204">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="5d7c6-205">在 [摘要您的 **意見** 反應] 方塊中輸入摘要（如果尚未填入）。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-205">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="5d7c6-206">在 [詳細 **資料** ] 方塊中，輸入您所遇到問題的詳細描述和您採取的步驟，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-206">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="5d7c6-207">選取 [ **問題**] 旁邊的氣泡。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-207">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="5d7c6-208">請確定選取的類別是「**安全性和隱私權 \> Microsoft Defender 應用程式防護– Office**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-208">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="5d7c6-209">選取 [ **新增** 反應]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-209">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="5d7c6-210">收集有關問題的追蹤：</span><span class="sxs-lookup"><span data-stu-id="5d7c6-210">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="5d7c6-211">展開 [ **重新建立我的問題** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-211">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="5d7c6-212">如果您在執行應用程式防護時發生所遇到的問題，請開啟應用程式防護實例。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-212">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="5d7c6-213">開啟實例允許從應用程式防護容器內收集其他追蹤。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-213">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="5d7c6-214">選取 [ **開始錄製**]，等候拼貼停止旋轉，並說 *停止錄製*。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-214">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="5d7c6-215">使用應用程式防護完全再現問題。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-215">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="5d7c6-216">複製品可能包括嘗試啟動應用程式防護實例並等候失敗，或在執行中的應用程式防護實例中再現問題。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-216">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="5d7c6-217">選取 [ **停止錄製** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-217">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="5d7c6-218">保留任何執行中的應用程式防護 (實例) 開啟，甚至在提交之後幾分鐘後，也可以收集容器診斷。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-218">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="5d7c6-219">附加任何相關的螢幕擷取畫面或與問題相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-219">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="5d7c6-220">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-220">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="5d7c6-221">透過客戶語音 Office 提交意見反應</span><span class="sxs-lookup"><span data-stu-id="5d7c6-221">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="5d7c6-222">如果在應用程式防護中開啟 Office 檔時會發生問題，您也可以從 Office 提交意見反應。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-222">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="5d7c6-223">請參閱[Office 的預覽人員手冊](https://insider.office.com/handbook)以取得意見反應。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-223">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="5d7c6-224">與 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 整合</span><span class="sxs-lookup"><span data-stu-id="5d7c6-224">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="5d7c6-225">Office 的應用程式防護會與 Microsoft Defender for Endpoint 整合，以針對隔離環境中發生的惡意活動提供監控和警示。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-225">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="5d7c6-226">[Microsoft E365 E5 中的安全檔](/microsoft-365/security/office-365-security/safe-docs)是一種功能，可使用 microsoft Defender for Endpoint 掃描在 Office 的應用程式防護中開啟的檔。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-226">[Safe Documents in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) is a feature that uses Microsoft Defender for Endpoint to scan documents opened in Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-227">若為其他保護層級，使用者在決定掃描的結果之後，就無法在 Office 留下應用程式防護。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-227">For an additional layer of protection, users can't leave Application Guard for Office until the results of the scan have been determined.</span></span>

<span data-ttu-id="5d7c6-228">Microsoft Defender for Endpoint 是一種安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-228">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="5d7c6-229">如需此平臺的詳細資訊，請參閱 [Microsoft Defender For Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-229">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="5d7c6-230">若要深入瞭解如何將裝置上架至此平臺，請參閱 [在 Microsoft Defender For Endpoint service 中的板載裝置](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-230">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="5d7c6-231">您也可以將 Office 365 的 Microsoft Defender 設定為搭配使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-231">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="5d7c6-232">如需詳細資訊，請參閱[整合 Defender for Office 365 搭配 Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-232">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="5d7c6-233">限制和考慮</span><span class="sxs-lookup"><span data-stu-id="5d7c6-233">Limitations and considerations</span></span>

* <span data-ttu-id="5d7c6-234">Application Guard for Office 是一種受保護的模式，可隔離不受信任的檔，使其無法存取電腦上信任的公司資源、內部網路、使用者的身分識別及任意檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-234">Application Guard for Office is a protected mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="5d7c6-235">因此，如果使用者嘗試存取的功能具有對此存取的相依性（例如，從磁片上的本機檔案插入圖片），access 就會失敗，並產生如下列範例所示的提示。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-235">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="5d7c6-236">若要讓不可信的檔能夠存取受信任的資源，使用者必須從檔中移除 Application Guard protection。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-236">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![對話方塊說可協助您保護安全，但無法使用此功能](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="5d7c6-238">建議使用者只有在信任檔案及其來源或來源的位置時，才移除保護。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-238">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="5d7c6-239">在適用于 Office 的應用程式防護中，會停用像宏及 ActiveX 控制項等檔中的活動內容。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-239">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-240">使用者需要移除應用程式防護保護才能啟用 active 內容。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-240">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="5d7c6-241">在應用程式防護中以唯讀方式開啟從不同組織 OneDrive、商務用 OneDrive 或 SharePoint 線上之網路共用或檔案所共用的不受信任檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-241">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="5d7c6-242">使用者可以儲存這類檔案的本機副本，以繼續在容器中工作或移除保護，以直接使用原始檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-242">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="5d7c6-243">預設會封鎖受資訊版權管理 (IRM) 所保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-243">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="5d7c6-244">如果使用者想要在 [受保護的檢視] 中開啟這類檔案，系統管理員必須為組織設定不受支援的檔案類型的原則設定。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-244">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="5d7c6-245">在使用者登出和登入後，或在裝置重新開機之後，對 Office 應用程式防護中 Office 應用程式的任何自訂功能都不會保留。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-245">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="5d7c6-246">只有使用 UIA 架構的協助工具工具才能為 Office 的應用程式防護中開啟的檔案提供可存取的體驗。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-246">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="5d7c6-247">安裝後第一次啟動應用程式防護時，必須具備網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-247">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="5d7c6-248">為了讓應用程式防護驗證授權，必須連線。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-248">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="5d7c6-249">在檔的 [資訊] 區段中，[ *上次修改者* ] 屬性可能會以使用者的身分顯示 **WDAGUtilityAccount** 。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-249">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="5d7c6-250">WDAGUtilityAccount 是在 Application Guard 中設定的匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-250">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="5d7c6-251">桌面使用者的身分識別不會在應用程式防護容器內共用。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-251">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="5d7c6-252">Office 的應用程式防護效能優化</span><span class="sxs-lookup"><span data-stu-id="5d7c6-252">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="5d7c6-253">本節提供應用程式防護中用於 Office 之效能優化的概述。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-253">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="5d7c6-254">此資訊可協助系統管理員在啟用 Application Guard 時，向與 Office 或整體系統效能相關的使用者診斷報告。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-254">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="5d7c6-255">Application Guard 會使用虛擬容器，將不受信任的檔與系統隔離。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-255">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="5d7c6-256">建立容器及設定應用程式防護容器以開啟 Office 檔時，會有效能負荷，對使用者開啟不受信任的檔時，可能會對使用者的經驗造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-256">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="5d7c6-257">若要為使用者提供預期的檔案開啟體驗，當系統符合下列啟發時，Application Guard 會使用邏輯來預先建立容器：使用者已于過去28天內，在受保護的 View 或 Application Guard 中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-257">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="5d7c6-258">當符合此啟發時，Office 會在使用者登入 Windows 後，預先為使用者建立應用程式防護容器。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-258">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="5d7c6-259">在此預先建立作業進行中時，系統可能會遇到效能降低的情況，但在作業完成後，就會立即解決此影響。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-259">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="5d7c6-260">以使用者身分使用的方式 Office 應用程式，會產生試探法預先建立容器所需的暗示。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-260">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="5d7c6-261">若使用者在已啟用 Application Guard 的新系統上安裝 Office，Office 在使用者第一次開啟系統上的不受信任的檔之前，不會預先建立容器。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-261">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="5d7c6-262">使用者將會看到此第一個檔案在應用程式防護中所需的時間較長。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-262">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5d7c6-263">已知問題</span><span class="sxs-lookup"><span data-stu-id="5d7c6-263">Known issues</span></span>

* <span data-ttu-id="5d7c6-264">選取 [網路連結] (`http` 或 `https`) 並不會開啟瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-264">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="5d7c6-265">目前不支援在使用 Application Guard 所開啟 Office 檔中 (rtf) 內容或圖像貼上 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-265">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="5d7c6-266">不受支援的檔案類型保護原則的預設設定為封鎖開啟不受信任的資訊版權管理檔案類型 (IRM) 、CSV 或 HTML。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-266">The default setting for unsupported file types protection policy is to block opening untrusted unsupported file types of Information Rights Management (IRM), CSV, or HTML.</span></span>
* <span data-ttu-id="5d7c6-267">更新 .NET 可能會導致檔無法在應用程式防護中開啟。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-267">Updates to .NET might cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="5d7c6-268">作為解決方法，使用者可以在發生這種失敗時，重新開機其裝置。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-268">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="5d7c6-269">深入瞭解在[嘗試開啟 Windows Defender 應用程式防護或 Windows 沙箱時，收到錯誤訊息時](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)出現問題的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5d7c6-269">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
