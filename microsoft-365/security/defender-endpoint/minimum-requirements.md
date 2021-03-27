---
title: Microsoft Defender for Endpoint 的基本需求
description: 瞭解上架裝置對服務的授權需求和需求
keywords: 最低需求、授權、比較表
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6a8e1091490cb9f3fe1eedadec0b76a56ada936e
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379487"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="5fa97-104">Microsoft Defender for Endpoint 的基本需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fa97-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5fa97-105">**Applies to:**</span></span>
- [<span data-ttu-id="5fa97-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5fa97-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5fa97-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fa97-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5fa97-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5fa97-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5fa97-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5fa97-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="5fa97-110">對服務上架裝置的一些基本需求。</span><span class="sxs-lookup"><span data-stu-id="5fa97-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="5fa97-111">深入瞭解授權、硬體和軟體需求，以及對服務的板載裝置的其他設定。</span><span class="sxs-lookup"><span data-stu-id="5fa97-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="5fa97-112">深入瞭解 endpoint for endpoint the defender 的最新增強功能： [defender For Endpoint 社區](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="5fa97-113">在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。</span><span class="sxs-lookup"><span data-stu-id="5fa97-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="5fa97-114">Read： [來自 MITRE ATT 的 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5fa97-115">授權需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-115">Licensing requirements</span></span>
<span data-ttu-id="5fa97-116">Microsoft Defender for Endpoint 需要下列其中一個 Microsoft 大量授權服務：</span><span class="sxs-lookup"><span data-stu-id="5fa97-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="5fa97-117">Windows 10 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="5fa97-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5fa97-118">Windows 10 教育版 A5</span><span class="sxs-lookup"><span data-stu-id="5fa97-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="5fa97-119">Microsoft 365 E5 (M365 E5) 包含 Windows 10 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="5fa97-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5fa97-120">Microsoft 365 A5 (M365 A5) </span><span class="sxs-lookup"><span data-stu-id="5fa97-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="5fa97-121">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="5fa97-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="5fa97-122">Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="5fa97-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="5fa97-123">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5fa97-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-124">合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。</span><span class="sxs-lookup"><span data-stu-id="5fa97-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="5fa97-125">Microsoft Defender for Endpoint 也可從雲端解決方案供應商購買 (CSP) 。</span><span class="sxs-lookup"><span data-stu-id="5fa97-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="5fa97-126">伺服器的 Microsoft Defender 端點需要下列其中一個授權選項：</span><span class="sxs-lookup"><span data-stu-id="5fa97-126">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="5fa97-127">啟用 Azure Defender 的 azure Security Center</span><span class="sxs-lookup"><span data-stu-id="5fa97-127">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="5fa97-128">Microsoft Defender for Server (每個伺服器) 一個伺服器的端點</span><span class="sxs-lookup"><span data-stu-id="5fa97-128">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-129">如果伺服器具有至少一或多個下列使用者授權的最低50授權，則每個伺服器的伺服器作業系統環境都可取得伺服器授權 ( (OSE) ) 的 Microsoft Defender for server。</span><span class="sxs-lookup"><span data-stu-id="5fa97-129">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="5fa97-130">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5fa97-130">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="5fa97-131">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="5fa97-131">Windows E5/A5</span></span>
> * <span data-ttu-id="5fa97-132">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="5fa97-132">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="5fa97-133">Microsoft 365 E5/A5 安全性</span><span class="sxs-lookup"><span data-stu-id="5fa97-133">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="5fa97-134">如需詳細的授權資訊，請參閱 [產品條款網站](https://www.microsoft.com/licensing/terms/) ，與您的帳戶小組合作以深入瞭解條款與條件。</span><span class="sxs-lookup"><span data-stu-id="5fa97-134">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="5fa97-135">如需 Windows 10 版中功能陣列的詳細資訊，請參閱 [比較 Windows 10 edition](https://www.microsoft.com/windowsforbusiness/compare)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-135">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="5fa97-136">如需 Windows 10 商業版比較的詳細比較表，請參閱 [比較 PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-136">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="5fa97-137">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-137">Browser requirements</span></span>
<span data-ttu-id="5fa97-138">您可以透過瀏覽器來存取端點，以支援下列瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="5fa97-138">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="5fa97-139">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5fa97-139">Microsoft Edge</span></span>
- <span data-ttu-id="5fa97-140">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5fa97-140">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-141">雖然其他瀏覽器可能會運作，但上述瀏覽器也是支援的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="5fa97-141">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="5fa97-142">硬體及軟體需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-142">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="5fa97-143">支援的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="5fa97-143">Supported Windows versions</span></span>
- <span data-ttu-id="5fa97-144">Windows 7 SP1 Enterprise ([需要 ESU 以取得支援服務](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。 ) </span><span class="sxs-lookup"><span data-stu-id="5fa97-144">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5fa97-145">Windows 7 SP1 Pro ([需要 ESU 以取得支援服務](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。 ) </span><span class="sxs-lookup"><span data-stu-id="5fa97-145">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5fa97-146">Windows 8.1 企業版</span><span class="sxs-lookup"><span data-stu-id="5fa97-146">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="5fa97-147">Windows 8.1 專業版</span><span class="sxs-lookup"><span data-stu-id="5fa97-147">Windows 8.1 Pro</span></span>
- <span data-ttu-id="5fa97-148">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="5fa97-148">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="5fa97-149">Windows 10 企業版 LTSC</span><span class="sxs-lookup"><span data-stu-id="5fa97-149">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="5fa97-150">Windows 10 教育版</span><span class="sxs-lookup"><span data-stu-id="5fa97-150">Windows 10 Education</span></span>
- <span data-ttu-id="5fa97-151">Windows 10 專業版</span><span class="sxs-lookup"><span data-stu-id="5fa97-151">Windows 10 Pro</span></span>
- <span data-ttu-id="5fa97-152">Windows 10 專業教育版</span><span class="sxs-lookup"><span data-stu-id="5fa97-152">Windows 10 Pro Education</span></span>
- <span data-ttu-id="5fa97-153">Windows server</span><span class="sxs-lookup"><span data-stu-id="5fa97-153">Windows server</span></span>
  - <span data-ttu-id="5fa97-154">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="5fa97-154">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="5fa97-155">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5fa97-155">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="5fa97-156">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5fa97-156">Windows Server 2016</span></span>
  - <span data-ttu-id="5fa97-157">Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="5fa97-157">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="5fa97-158">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5fa97-158">Windows Server 2019</span></span>
- <span data-ttu-id="5fa97-159">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="5fa97-159">Windows Virtual Desktop</span></span>

<span data-ttu-id="5fa97-160">您的網路上的裝置必須執行下列其中一個版本。</span><span class="sxs-lookup"><span data-stu-id="5fa97-160">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="5fa97-161">針對支援的版本，裝置上之 Endpoint 的 Defender 的硬體需求是相同的。</span><span class="sxs-lookup"><span data-stu-id="5fa97-161">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-162">不支援執行行動 Windows mobile 版本 Windows 的機器 (例如 Windows CE 和 Windows 10 行動) 。</span><span class="sxs-lookup"><span data-stu-id="5fa97-162">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="5fa97-163">執行 Windows 10 企業版 2016 LTSB 的虛擬機器在非 Microsoft 虛擬化平臺上執行時，可能會遇到效能問題。</span><span class="sxs-lookup"><span data-stu-id="5fa97-163">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="5fa97-164">在虛擬環境中，我們建議使用 Windows 10 Enterprise LTSC 2019 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="5fa97-164">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="5fa97-165">其他支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="5fa97-165">Other supported operating systems</span></span>
- <span data-ttu-id="5fa97-166">Android</span><span class="sxs-lookup"><span data-stu-id="5fa97-166">Android</span></span>
- <span data-ttu-id="5fa97-167">iOS</span><span class="sxs-lookup"><span data-stu-id="5fa97-167">iOS</span></span>
- <span data-ttu-id="5fa97-168">Linux</span><span class="sxs-lookup"><span data-stu-id="5fa97-168">Linux</span></span>
- <span data-ttu-id="5fa97-169">macOS</span><span class="sxs-lookup"><span data-stu-id="5fa97-169">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-170">您必須確認 Linux 的發行和版本的 Android、iOS 和 macOS 與您的電腦上的 Defender for Endpoint 相容，以供整合運作。</span><span class="sxs-lookup"><span data-stu-id="5fa97-170">You'll need to confirm the Linux distributions and versions of Android, iOS and macOS you've are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="5fa97-171">網路和資料儲存區及設定需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-171">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="5fa97-172">當您第一次執行 [上架] 嚮導時，必須選擇 Microsoft Defender 用於端點相關資訊的儲存位置：在歐盟、英國或美國資料中心。</span><span class="sxs-lookup"><span data-stu-id="5fa97-172">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="5fa97-173">您無法在第一次設定之後變更資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="5fa97-173">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="5fa97-174">請參閱 [Microsoft Defender For Endpoint data storage and 隱私權](data-storage-privacy.md) ，以取得 microsoft 儲存資料的地點和方式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fa97-174">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="5fa97-175">診斷資料設定</span><span class="sxs-lookup"><span data-stu-id="5fa97-175">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-176">只要啟用，則 Microsoft Defender for Endpoint 不需要任何特定的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="5fa97-176">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="5fa97-177">確定您組織中的所有裝置都已啟用診斷資料服務。</span><span class="sxs-lookup"><span data-stu-id="5fa97-177">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="5fa97-178">依預設，會啟用此服務。</span><span class="sxs-lookup"><span data-stu-id="5fa97-178">By default, this service is enabled.</span></span> <span data-ttu-id="5fa97-179">請務必確認您會從這些位置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="5fa97-179">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="5fa97-180">**使用命令列來檢查 Windows 10 診斷資料服務啟動類型**：</span><span class="sxs-lookup"><span data-stu-id="5fa97-180">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="5fa97-181">在裝置上開啟已提升許可權的命令列提示：</span><span class="sxs-lookup"><span data-stu-id="5fa97-181">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="5fa97-182">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="5fa97-182">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="5fa97-183">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="5fa97-183">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="5fa97-184">輸入下列命令，然後按 **enter**：</span><span class="sxs-lookup"><span data-stu-id="5fa97-184">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="5fa97-185">如果已啟用服務，結果應該如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="5fa97-185">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Diagtrack 的 sc 查詢命令的結果](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="5fa97-187">如果 **START_TYPE** 未設定為 **AUTO_START**，您必須將服務設定為自動啟動。</span><span class="sxs-lookup"><span data-stu-id="5fa97-187">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="5fa97-188">**使用命令列將 Windows 10 診斷資料服務設定為自動啟動：**</span><span class="sxs-lookup"><span data-stu-id="5fa97-188">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="5fa97-189">在端點上開啟已提升許可權的命令列提示：</span><span class="sxs-lookup"><span data-stu-id="5fa97-189">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="5fa97-190">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="5fa97-190">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="5fa97-191">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="5fa97-191">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="5fa97-192">輸入下列命令，然後按 **enter**：</span><span class="sxs-lookup"><span data-stu-id="5fa97-192">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="5fa97-193">隨即顯示一則成功訊息。</span><span class="sxs-lookup"><span data-stu-id="5fa97-193">A success message is displayed.</span></span> <span data-ttu-id="5fa97-194">輸入下列命令，然後按 **enter**，以確認變更：</span><span class="sxs-lookup"><span data-stu-id="5fa97-194">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="5fa97-195">網際網路連線能力</span><span class="sxs-lookup"><span data-stu-id="5fa97-195">Internet connectivity</span></span>
<span data-ttu-id="5fa97-196">必須直接或透過 proxy，在裝置上的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="5fa97-196">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="5fa97-197">「！使用條款」的 Defender for Endpoint 感應器可以使用每日平均頻寬為 5 MB，以與 Endpoint 雲端服務和報告網路資料的 Defender 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="5fa97-197">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="5fa97-198">在此每日平均頻寬中不會包含一項一次性活動，例如檔案上傳和調查套件集合。</span><span class="sxs-lookup"><span data-stu-id="5fa97-198">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="5fa97-199">如需其他 proxy 設定設定的詳細資訊，請參閱 [Configure device proxy And Internet connectivity settings](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-199">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="5fa97-200">在您的板載裝置之前，必須先啟用診斷資料服務。</span><span class="sxs-lookup"><span data-stu-id="5fa97-200">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="5fa97-201">Windows 10 中預設會啟用此服務。</span><span class="sxs-lookup"><span data-stu-id="5fa97-201">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="5fa97-202">Microsoft Defender 防病毒設定需求</span><span class="sxs-lookup"><span data-stu-id="5fa97-202">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="5fa97-203">端點代理程式的 Defender 取決於 Microsoft Defender 防病毒掃描檔案的能力，並提供這些檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5fa97-203">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="5fa97-204">在 Defender for Endpoint 裝置上設定安全性智慧更新，是否 Microsoft Defender 防病毒是使用中的反惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="5fa97-204">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="5fa97-205">如需詳細資訊，請參閱 [管理 Microsoft Defender 防病毒更新及套用基準](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-205">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="5fa97-206">當 Microsoft Defender 防毒程式不是您組織中使用的反惡意程式碼，且您使用 Defender for Endpoint service 時，Microsoft Defender 防毒程式會進入被動模式。</span><span class="sxs-lookup"><span data-stu-id="5fa97-206">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="5fa97-207">如果您的組織已透過群組原則或其他方法關閉 Microsoft Defender 防病毒，則必須從此群組原則排除架裝置。</span><span class="sxs-lookup"><span data-stu-id="5fa97-207">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="5fa97-208">如果您是上架伺服器，而 Microsoft Defender 防毒軟體不是伺服器上使用中的反惡意程式碼，則 Microsoft Defender 防毒軟體必須設定為進入被動模式或已卸載。</span><span class="sxs-lookup"><span data-stu-id="5fa97-208">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="5fa97-209">設定取決於伺服器版本。</span><span class="sxs-lookup"><span data-stu-id="5fa97-209">The configuration is dependent on the server version.</span></span> <span data-ttu-id="5fa97-210">如需詳細資訊，請參閱 [Microsoft Defender 防毒程式相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-210">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5fa97-211">您的一般群組原則不會套用到防篡改保護，當防篡改保護開啟時，將會忽略對 Microsoft Defender 防病毒設定所做的變更。</span><span class="sxs-lookup"><span data-stu-id="5fa97-211">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="5fa97-212">Microsoft Defender 防病毒及早啟動反惡意程式碼 (ELAM) 驅動程式已啟用</span><span class="sxs-lookup"><span data-stu-id="5fa97-212">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="5fa97-213">如果您是在裝置上執行 Microsoft Defender 防毒軟體做為主要的反惡意軟體產品，端點代理程式的 Defender 代理程式就會順利地板載。</span><span class="sxs-lookup"><span data-stu-id="5fa97-213">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="5fa97-214">如果您正在執行協力廠商反惡意程式碼用戶端，並使用行動裝置管理解決方案或 Microsoft 端點管理員 (目前的分支) ，您必須確定已啟用 Microsoft Defender 防病毒 ELAM 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="5fa97-214">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="5fa97-215">如需詳細資訊，請參閱 [確定原則未停用 Microsoft Defender 防病毒](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="5fa97-215">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5fa97-216">相關主題</span><span class="sxs-lookup"><span data-stu-id="5fa97-216">Related topics</span></span>
- [<span data-ttu-id="5fa97-217">設定 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="5fa97-217">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="5fa97-218">板載裝置</span><span class="sxs-lookup"><span data-stu-id="5fa97-218">Onboard devices</span></span>](onboard-configure.md)
