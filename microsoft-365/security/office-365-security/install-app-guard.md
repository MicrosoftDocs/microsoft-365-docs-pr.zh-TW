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
ms.openlocfilehash: 9a9c9270f61661982108da518d1bf24d2a717b6a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029723"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="d06d9-105">適用于系統管理員的 Office 應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="d06d9-106">**適用于：** Microsoft 365，Windows 10 企業版的 Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d06d9-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="d06d9-107">Microsoft Defender Application Guard for office (Application Guard) 協助防止不可信的檔案存取受信任的資源，讓您的企業安全地抵禦新的和新興的攻擊。</span><span class="sxs-lookup"><span data-stu-id="d06d9-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="d06d9-108">本文指導管理員如何針對 Office 的應用程式防護，設定可預覽的裝置。</span><span class="sxs-lookup"><span data-stu-id="d06d9-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="d06d9-109">它提供有關系統需求和安裝步驟的資訊，以便在裝置上啟用 Office 的應用程式防護功能。</span><span class="sxs-lookup"><span data-stu-id="d06d9-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d06d9-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="d06d9-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="d06d9-111">基本硬體需求</span><span class="sxs-lookup"><span data-stu-id="d06d9-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="d06d9-112">**CPU**：64位、4核心 (實體或虛擬) 、虛擬化擴充 (Intel VT-x 或 AMD-V) 、Core i5 對等建議或更高版本的建議</span><span class="sxs-lookup"><span data-stu-id="d06d9-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="d06d9-113">**實體記憶體**： 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="d06d9-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="d06d9-114">**硬碟**：系統磁片磁碟機上有 10 GB 的可用空間 (SSD 建議) </span><span class="sxs-lookup"><span data-stu-id="d06d9-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="d06d9-115">基本軟體需求</span><span class="sxs-lookup"><span data-stu-id="d06d9-115">Minimum software requirements</span></span>

* <span data-ttu-id="d06d9-116">**Windows 10**： Windows 10 Enterprise Edition，Client Build version 2004 (20H1) 組建19041或更新版本</span><span class="sxs-lookup"><span data-stu-id="d06d9-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="d06d9-117">**Office**： Office Current 通道組建版本 2011 16.0.13530.10000 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d06d9-117">**Office**: Office Current Channel Build version 2011 16.0.13530.10000 or later</span></span>
* <span data-ttu-id="d06d9-118">**更新套件**： Windows 10 累計每月安全性更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="d06d9-118">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="d06d9-119">如需詳細的系統需求，請參閱 [Microsoft Defender Application Guard 的系統需求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-119">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="d06d9-120">若要深入瞭解 Office 更新通道，請參閱 [Microsoft 365 的更新通道一覽](https://docs.microsoft.com/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-120">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="d06d9-121">授權需求</span><span class="sxs-lookup"><span data-stu-id="d06d9-121">Licensing requirements</span></span>

* <span data-ttu-id="d06d9-122">Microsoft 365 E5 或 Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="d06d9-122">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="d06d9-123">部署 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-123">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="d06d9-124">啟用適用于 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-124">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="d06d9-125">下載及安裝 **Windows 10 累計每月安全性更新 KB4571756**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-125">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="d06d9-126">選取 [Windows 功能] 底下的 [ **Microsoft Defender 應用程式防護** ] 並選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-126">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="d06d9-127">啟用 Application Guard 功能時，會提示重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="d06d9-127">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="d06d9-128">您可以選擇 [現在] 或 [在步驟3之後重新開機]。</span><span class="sxs-lookup"><span data-stu-id="d06d9-128">You can choose to reboot now or after step 3.</span></span>

   ![顯示 AG 的 [Windows 功能] 對話方塊](../../media/ag03-deploy.png)

   <span data-ttu-id="d06d9-130">您也可以以系統管理員身分執行下列 PowerShell 命令，以啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="d06d9-130">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="d06d9-131">搜尋 **Microsoft Defender Application guard In Managed Mode**，a **Computer Configuration 系統管理範本中的群組原則 \\ \\ Windows 元件 \\ Microsoft Defender 應用程式防護**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-131">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="d06d9-132">將 [選項] 底下的值設定為 [ **2** ] 或 [ **3**]，然後選取 **[確定] 或 [套用]** ，以開啟此原則。 </span><span class="sxs-lookup"><span data-stu-id="d06d9-132">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![在受管理的模式中開啟 AG](../../media/ag04-deploy.png)

   <span data-ttu-id="d06d9-134">相反地，您可以設定對應的 CSP 原則：</span><span class="sxs-lookup"><span data-stu-id="d06d9-134">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="d06d9-135">OMA URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="d06d9-135">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="d06d9-136">資料類型： **Integer**</span><span class="sxs-lookup"><span data-stu-id="d06d9-136">Data type: **Integer**</span></span> <br> <span data-ttu-id="d06d9-137">值： **2**</span><span class="sxs-lookup"><span data-stu-id="d06d9-137">Value: **2**</span></span>

4. <span data-ttu-id="d06d9-138">重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="d06d9-138">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="d06d9-139">設定診斷 & 傳送完整資料的意見</span><span class="sxs-lookup"><span data-stu-id="d06d9-139">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="d06d9-140">此步驟可確保識別和修正問題所需的資料是在 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d06d9-140">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="d06d9-141">請遵循下列步驟，在 Windows 裝置上啟用診斷：</span><span class="sxs-lookup"><span data-stu-id="d06d9-141">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="d06d9-142">開啟 [開始] 功能表中的 **設定** 。</span><span class="sxs-lookup"><span data-stu-id="d06d9-142">Open **Settings** from the Start menu.</span></span>

   ![[開始] 功能表](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="d06d9-144">在 [ **Windows 設定**] 上，選取 [ **隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="d06d9-144">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 設定功能表](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="d06d9-146">在 [隱私權] 底下，選取 [ **診斷 & 回饋** ]，然後選取 [ **選用診斷資料**]。</span><span class="sxs-lookup"><span data-stu-id="d06d9-146">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![診斷和回饋功能表](../../media/ag07a-diagnostic.png)

<span data-ttu-id="d06d9-148">如需設定 Windows 診斷設定的詳細資訊，請參閱設定 [組織中的 Windows 診斷資料](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-148">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="d06d9-149">確認 Office 的應用程式防護已啟用且正常運作</span><span class="sxs-lookup"><span data-stu-id="d06d9-149">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="d06d9-150">確認已啟用 Office 的應用程式防護功能之前，請在已部署原則的裝置上啟動 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="d06d9-150">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="d06d9-151">請確定已啟用 Office。</span><span class="sxs-lookup"><span data-stu-id="d06d9-151">Make sure Office is activated.</span></span> <span data-ttu-id="d06d9-152">您可能需要先使用您的工作身分識別來啟用 Office 產品。</span><span class="sxs-lookup"><span data-stu-id="d06d9-152">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="d06d9-153">若要確認已啟用 Office 的應用程式防護，請啟動 Word、Excel 或 PowerPoint，然後開啟不受信任的檔。</span><span class="sxs-lookup"><span data-stu-id="d06d9-153">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="d06d9-154">例如，您可以開啟從網際網路下載的檔或來自組織外部人員的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="d06d9-154">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="d06d9-155">當您第一次開啟不受信任的檔案時，您可能會看到 Office 閃屏，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="d06d9-155">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="d06d9-156">在啟動 Office 的應用程式防護，且正在開啟檔案時，它可能會顯示一段時間。</span><span class="sxs-lookup"><span data-stu-id="d06d9-156">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="d06d9-157">後續的不受信任檔案的開口應該會更快。</span><span class="sxs-lookup"><span data-stu-id="d06d9-157">Subsequent openings of untrusted files should be faster.</span></span>

![Office 應用程式啟動畫面](../../media/ag08-confirm.png)

<span data-ttu-id="d06d9-159">開啟檔案時，該檔案應該會顯示一些視覺標記，指出檔案已在 Office 的應用程式防護中開啟：</span><span class="sxs-lookup"><span data-stu-id="d06d9-159">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="d06d9-160">功能區中的標注</span><span class="sxs-lookup"><span data-stu-id="d06d9-160">A callout in the ribbon</span></span>

  ![顯示小型應用程式防護附注的 Doc 檔案](../../media/ag09-confirm.png)

* <span data-ttu-id="d06d9-162">在工作列中帶有盾牌的應用程式圖示</span><span class="sxs-lookup"><span data-stu-id="d06d9-162">The application icon with a shield in the taskbar</span></span>

  ![工作列中的圖示](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="d06d9-164">設定 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-164">Configure Application Guard for Office</span></span>

<span data-ttu-id="d06d9-165">Office 支援下列原則，可讓您設定 Office 應用程式防護的功能。</span><span class="sxs-lookup"><span data-stu-id="d06d9-165">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="d06d9-166">您可以透過「群組原則」或 Office cloud policy service 來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="d06d9-166">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="d06d9-167">設定這些原則可以停用 Office 的應用程式防護中開啟檔案的某些功能。</span><span class="sxs-lookup"><span data-stu-id="d06d9-167">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="d06d9-168">原則</span><span class="sxs-lookup"><span data-stu-id="d06d9-168">Policy</span></span>|<span data-ttu-id="d06d9-169">描述</span><span class="sxs-lookup"><span data-stu-id="d06d9-169">Description</span></span>|
|---|---|
|<span data-ttu-id="d06d9-170">不使用適用于 Office 的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-170">Don't use Application Guard for Office</span></span>|<span data-ttu-id="d06d9-171">啟用這個原則會強制 Word、Excel 及 PowerPoint 使用受保護的檢視隔離容器，而不是 Office 的應用程式防護。</span><span class="sxs-lookup"><span data-stu-id="d06d9-171">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="d06d9-172">這項原則可用於暫時停用 Office 的應用程式防護時，如果有問題仍可讓 Microsoft Edge 啟用它。</span><span class="sxs-lookup"><span data-stu-id="d06d9-172">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="d06d9-173">設定 Office 容器預先建立的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-173">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="d06d9-174">此原則會判斷是否已預先建立 Office 的應用程式防護容器（用於隔離不可信的檔案），以提升執行時間效能。</span><span class="sxs-lookup"><span data-stu-id="d06d9-174">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="d06d9-175">如果您啟用此設定，您可以指定繼續建立容器的天數，或讓 Office 內建啟發式預先建立容器。</span><span class="sxs-lookup"><span data-stu-id="d06d9-175">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="d06d9-176">不允許在適用于 Office 的應用程式防護中開啟 Office 檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="d06d9-176">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="d06d9-177">啟用這個原則可防止使用者將內容從開啟于 Office 應用程式防護的檔中複製並貼到其外開啟的檔。</span><span class="sxs-lookup"><span data-stu-id="d06d9-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="d06d9-178">停用 Office 應用程式防護中的硬體加速</span><span class="sxs-lookup"><span data-stu-id="d06d9-178">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="d06d9-179">此原則控制 Office 的應用程式防護是否會使用硬體加速呈現圖形。</span><span class="sxs-lookup"><span data-stu-id="d06d9-179">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="d06d9-180">如果您啟用此設定，Office 的應用程式防護會使用以軟體為基礎的 (CPU) 轉譯，而且不會載入任何協力廠商圖形驅動程式或與任何連接的圖形硬體互動。</span><span class="sxs-lookup"><span data-stu-id="d06d9-180">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="d06d9-181">停用 Office 應用程式防護中不支援的檔案類型保護</span><span class="sxs-lookup"><span data-stu-id="d06d9-181">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="d06d9-182">此原則控制 Office 的應用程式防護是否會封鎖未支援的檔案類型，或是否要啟用重新導向至受保護的檢視。</span><span class="sxs-lookup"><span data-stu-id="d06d9-182">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="d06d9-183">針對 Office 的應用程式防護中開啟的檔關閉相機和麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="d06d9-183">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="d06d9-184">啟用此原則將會移除 office 的應用程式防護內，對相機及麥克風的 Office 存取。</span><span class="sxs-lookup"><span data-stu-id="d06d9-184">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="d06d9-185">限制在 Office 的應用程式防護中開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="d06d9-185">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="d06d9-186">啟用此原則會限制使用者可以從 Office 的應用程式 Guard 中開啟的檔案列印的印表機。</span><span class="sxs-lookup"><span data-stu-id="d06d9-186">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="d06d9-187">例如，您可以使用這個原則來限制使用者只能列印為 PDF。</span><span class="sxs-lookup"><span data-stu-id="d06d9-187">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="d06d9-188">防止使用者移除 Office protection on files 上的應用程式防護</span><span class="sxs-lookup"><span data-stu-id="d06d9-188">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="d06d9-189">啟用此原則將會移除 Office 應用程式經驗) 中的選項 (，以停用 Office protection 的 Application Guard 或開啟檔案，以在應用程式的應用程式防護以外的 Office。</span><span class="sxs-lookup"><span data-stu-id="d06d9-189">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="d06d9-190">**附注：** 使用者仍可略過此原則，方法是手動移除檔案中的 web 標記，或是將檔移至信任位置。</span><span class="sxs-lookup"><span data-stu-id="d06d9-190">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="d06d9-191">下列原則將需要使用者登出並重新登入，才能生效：</span><span class="sxs-lookup"><span data-stu-id="d06d9-191">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="d06d9-192">停用 Office 應用程式防護中開啟檔的複製/貼上</span><span class="sxs-lookup"><span data-stu-id="d06d9-192">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="d06d9-193">限制在適用于 Office 的應用程式防護中開啟的檔列印</span><span class="sxs-lookup"><span data-stu-id="d06d9-193">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="d06d9-194">關閉以 Office 應用程式防護開啟的檔的相機和麥克風存取權</span><span class="sxs-lookup"><span data-stu-id="d06d9-194">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="d06d9-195">提交意見反應</span><span class="sxs-lookup"><span data-stu-id="d06d9-195">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="d06d9-196">透過意見反應中心提交意見反應</span><span class="sxs-lookup"><span data-stu-id="d06d9-196">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="d06d9-197">如果您在啟動 Office 的應用程式防護時遇到任何問題，建議您透過意見反應中心提交您的意見反應：</span><span class="sxs-lookup"><span data-stu-id="d06d9-197">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="d06d9-198">開啟「 **回饋中樞」應用程式** 並登入。</span><span class="sxs-lookup"><span data-stu-id="d06d9-198">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="d06d9-199">如果您在啟動應用程式防護時收到錯誤對話方塊，請在錯誤對話方塊中選取 [ **向 Microsoft 報告** ]，以啟動新的意見反應提交。</span><span class="sxs-lookup"><span data-stu-id="d06d9-199">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="d06d9-200">否則，請流覽至 <https://aka.ms/mdagoffice-fb> 以選取正確的應用程式防護類別類別，然後選取 [在右上方附近 **+ &nbsp; 新增新的意見** 反應]。</span><span class="sxs-lookup"><span data-stu-id="d06d9-200">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="d06d9-201">在 [摘要您的 **意見** 反應] 方塊中輸入摘要（如果尚未填入）。</span><span class="sxs-lookup"><span data-stu-id="d06d9-201">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="d06d9-202">在 [詳細 **資料** ] 方塊中，輸入您所遇到問題的詳細描述和您採取的步驟，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-202">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="d06d9-203">選取 [ **問題**] 旁邊的氣泡。</span><span class="sxs-lookup"><span data-stu-id="d06d9-203">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="d06d9-204">確定選取的類別為 **安全性和隱私權 \> Microsoft Defender 應用程式防護-Office**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-204">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="d06d9-205">選取 [ **新增** 反應]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-205">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="d06d9-206">收集有關問題的追蹤：</span><span class="sxs-lookup"><span data-stu-id="d06d9-206">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="d06d9-207">展開 [ **重新建立我的問題** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="d06d9-207">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="d06d9-208">如果您在執行應用程式防護時發生所遇到的問題，請開啟應用程式防護實例。</span><span class="sxs-lookup"><span data-stu-id="d06d9-208">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="d06d9-209">開啟實例允許從應用程式防護容器內收集其他追蹤。</span><span class="sxs-lookup"><span data-stu-id="d06d9-209">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="d06d9-210">選取 [ **開始錄製**]，等候拼貼停止旋轉，並說 *停止錄製*。</span><span class="sxs-lookup"><span data-stu-id="d06d9-210">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="d06d9-211">使用應用程式防護完全再現問題。</span><span class="sxs-lookup"><span data-stu-id="d06d9-211">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="d06d9-212">複製品可能包括嘗試啟動應用程式防護實例並等候失敗，或在執行中的應用程式防護實例中再現問題。</span><span class="sxs-lookup"><span data-stu-id="d06d9-212">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="d06d9-213">選取 [ **停止錄製** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="d06d9-213">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="d06d9-214">保留任何執行中的應用程式防護 (實例) 開啟，甚至在提交之後幾分鐘後，也可以收集容器診斷。</span><span class="sxs-lookup"><span data-stu-id="d06d9-214">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="d06d9-215">附加任何相關的螢幕擷取畫面或與問題相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="d06d9-215">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="d06d9-216">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="d06d9-216">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="d06d9-217">透過 Office 客戶語音提交意見反應</span><span class="sxs-lookup"><span data-stu-id="d06d9-217">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="d06d9-218">您也可以從 Office 提交意見，如果在應用程式防護中開啟 Office 檔時會發生問題。</span><span class="sxs-lookup"><span data-stu-id="d06d9-218">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="d06d9-219">請參閱 [Office 預覽人員手冊](https://insider.office.com/handbook) 以取得意見反應。</span><span class="sxs-lookup"><span data-stu-id="d06d9-219">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="d06d9-220">與 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 整合</span><span class="sxs-lookup"><span data-stu-id="d06d9-220">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="d06d9-221">適用于 Office 的應用程式防護會與 Microsoft Defender for Endpoint 整合，以針對隔離環境中發生的惡意活動提供監控和警示。</span><span class="sxs-lookup"><span data-stu-id="d06d9-221">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="d06d9-222">Microsoft Defender for Endpoint 是一種安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="d06d9-222">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="d06d9-223">如需此平臺的詳細資訊，請參閱 [Microsoft Defender For Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-223">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="d06d9-224">若要深入瞭解如何將裝置上架至此平臺，請參閱 [在 Microsoft Defender For Endpoint service 中的板載裝置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-224">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="d06d9-225">您也可以將 Microsoft Defender for Office 365 設定為搭配使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d06d9-225">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="d06d9-226">如需詳細資訊，請參閱 [整合 Defender For Office 365 搭配 Microsoft Defender For Endpoint](integrate-office-365-ti-with-wdatp.md)。</span><span class="sxs-lookup"><span data-stu-id="d06d9-226">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="d06d9-227">限制和考慮</span><span class="sxs-lookup"><span data-stu-id="d06d9-227">Limitations and considerations</span></span>

* <span data-ttu-id="d06d9-228">適用于 Office 的應用程式防護是一種限制模式，可隔離不可信的檔，使其無法存取電腦上信任的公司資源、內部網路、使用者的身分識別及任意檔案。</span><span class="sxs-lookup"><span data-stu-id="d06d9-228">Application Guard for Office is a restricted mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="d06d9-229">因此，如果使用者嘗試存取的功能具有對此存取的相依性（例如，從磁片上的本機檔案插入圖片），access 就會失敗，並產生如下列範例所示的提示。</span><span class="sxs-lookup"><span data-stu-id="d06d9-229">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="d06d9-230">若要讓不可信的檔能夠存取受信任的資源，使用者必須從檔中移除 Application Guard protection。</span><span class="sxs-lookup"><span data-stu-id="d06d9-230">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![對話方塊說可協助您保護安全，但無法使用此功能](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="d06d9-232">建議使用者只有在信任檔案及其來源或來源的位置時，才移除保護。</span><span class="sxs-lookup"><span data-stu-id="d06d9-232">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="d06d9-233">在 Office 的應用程式防護中，諸如宏和 ActiveX 控制項等檔中的作用中內容會停用。</span><span class="sxs-lookup"><span data-stu-id="d06d9-233">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="d06d9-234">使用者需要移除應用程式防護保護才能啟用 active 內容。</span><span class="sxs-lookup"><span data-stu-id="d06d9-234">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="d06d9-235">從 OneDrive、商務用 OneDrive 或從不同的組織 SharePoint 線上開啟的網路共用或檔案中的不受信任檔案，在 Application Guard 中開啟為唯讀。</span><span class="sxs-lookup"><span data-stu-id="d06d9-235">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="d06d9-236">使用者可以儲存這類檔案的本機副本，以繼續在容器中工作或移除保護，以直接使用原始檔案。</span><span class="sxs-lookup"><span data-stu-id="d06d9-236">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="d06d9-237">預設會封鎖受資訊版權管理 (IRM) 所保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="d06d9-237">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="d06d9-238">如果使用者想要在 [受保護的檢視] 中開啟這類檔案，系統管理員必須為組織設定不受支援的檔案類型的原則設定。</span><span class="sxs-lookup"><span data-stu-id="d06d9-238">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="d06d9-239">在使用者登出並重新登入後，或在裝置重新開機之後，對 office 應用程式中的 Office 應用程式進行的任何自訂功能都不會保留。</span><span class="sxs-lookup"><span data-stu-id="d06d9-239">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="d06d9-240">只有使用 UIA 架構的協助工具工具才能為 Office 的應用程式防護中開啟的檔案提供可存取的經驗。</span><span class="sxs-lookup"><span data-stu-id="d06d9-240">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="d06d9-241">安裝後第一次啟動應用程式防護時，必須具備網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="d06d9-241">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="d06d9-242">為了讓應用程式防護驗證授權，必須連線。</span><span class="sxs-lookup"><span data-stu-id="d06d9-242">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="d06d9-243">在檔的 [資訊] 區段中，[ *上次修改者* ] 屬性可能會以使用者的身分顯示 **WDAGUtilityAccount** 。</span><span class="sxs-lookup"><span data-stu-id="d06d9-243">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="d06d9-244">WDAGUtilityAccount 是在 Application Guard 中設定的匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="d06d9-244">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="d06d9-245">桌面使用者的身分識別不會在應用程式防護容器內共用。</span><span class="sxs-lookup"><span data-stu-id="d06d9-245">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="d06d9-246">適用于 Office 的應用程式防護效能優化</span><span class="sxs-lookup"><span data-stu-id="d06d9-246">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="d06d9-247">本節提供適用于 Office 的應用程式防護中所使用之效能優化的概述。</span><span class="sxs-lookup"><span data-stu-id="d06d9-247">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="d06d9-248">此資訊可協助系統管理員在啟用 Application Guard 時，向與 Office 效能或整體系統相關的使用者診斷報告。</span><span class="sxs-lookup"><span data-stu-id="d06d9-248">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="d06d9-249">Application Guard 會使用虛擬容器，將不受信任的檔與系統隔離。</span><span class="sxs-lookup"><span data-stu-id="d06d9-249">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="d06d9-250">建立容器及將應用程式防護容器設定為開啟 Office 檔的程式，在使用者開啟不受信任的檔時，可能會對使用者經驗造成負面影響的效能負荷。</span><span class="sxs-lookup"><span data-stu-id="d06d9-250">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="d06d9-251">若要為使用者提供預期的檔案開啟體驗，當系統符合下列啟發時，Application Guard 會使用邏輯來預先建立容器：使用者已于過去28天內，在受保護的 View 或 Application Guard 中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="d06d9-251">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="d06d9-252">當符合此啟發時，Office 會在使用者登入 Windows 後，預先為使用者建立應用程式防護容器。</span><span class="sxs-lookup"><span data-stu-id="d06d9-252">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="d06d9-253">在此預先建立作業進行中時，系統可能會遇到效能降低的情況，但在作業完成後，就會立即解決此影響。</span><span class="sxs-lookup"><span data-stu-id="d06d9-253">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="d06d9-254">用於預先建立容器的啟發方式所需的提示是由 Office 應用程式在使用者使用時產生。</span><span class="sxs-lookup"><span data-stu-id="d06d9-254">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="d06d9-255">若使用者在已啟用 Application Guard 的新系統上安裝 Office，除非使用者第一次在系統上開啟不受信任的檔，否則 Office 將不會預先建立容器。</span><span class="sxs-lookup"><span data-stu-id="d06d9-255">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="d06d9-256">使用者將會看到此第一個檔案在應用程式防護中所需的時間較長。</span><span class="sxs-lookup"><span data-stu-id="d06d9-256">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d06d9-257">已知問題</span><span class="sxs-lookup"><span data-stu-id="d06d9-257">Known issues</span></span>

* <span data-ttu-id="d06d9-258">選取 [網路連結] (`http` 或 `https`) 並不會開啟瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="d06d9-258">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="d06d9-259">目前不支援在使用應用程式防護開啟的 Office 檔中 (RTF) 內容或圖像貼上 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="d06d9-259">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="d06d9-260">更新 .NET 導致檔案無法在應用程式防護中開啟。</span><span class="sxs-lookup"><span data-stu-id="d06d9-260">Updates to .NET cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="d06d9-261">作為解決方法，使用者可以在發生這種失敗時，重新開機其裝置。</span><span class="sxs-lookup"><span data-stu-id="d06d9-261">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="d06d9-262">深入瞭解 [當嘗試開啟 Windows Defender 應用程式防護或 Windows 沙箱時，收到錯誤訊息時](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)，有關問題的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d06d9-262">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
