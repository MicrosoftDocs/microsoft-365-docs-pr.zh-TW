---
title: 設定及驗證 Microsoft Defender 防毒軟體網路連線
description: 設定和測試您與 Microsoft Defender 防毒軟體 cloud protection service 的連接。
keywords: 防病毒，Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 5b6ed22b38d0795073fc72f380bcad89683ada9c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286810"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="ead73-104">設定及驗證 Microsoft Defender 防毒軟體網路連線</span><span class="sxs-lookup"><span data-stu-id="ead73-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="ead73-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ead73-105">**Applies to:**</span></span>

- [<span data-ttu-id="ead73-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ead73-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ead73-107">為了確保已 Microsoft Defender 防毒軟體雲端傳送保護運作正常，您的安全小組必須設定您的網路，以允許端點和某些 Microsoft 伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="ead73-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, your security team must configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="ead73-108">本文列出必須允許的連線，例如使用防火牆規則，並提供驗證連線的指示。</span><span class="sxs-lookup"><span data-stu-id="ead73-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="ead73-109">正確設定保護可協助確保您從雲端提供的保護服務中取得最佳價值。</span><span class="sxs-lookup"><span data-stu-id="ead73-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="ead73-110">如需網路連線的某些詳細資料，請參閱博客文章 [重要變更 Microsoft Active Protection Services 端點](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 。</span><span class="sxs-lookup"><span data-stu-id="ead73-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="ead73-111">在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，確認下列功能正在運作：</span><span class="sxs-lookup"><span data-stu-id="ead73-111">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="ead73-112">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="ead73-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="ead73-113">Fast 教學 (包括第一次看到區塊) </span><span class="sxs-lookup"><span data-stu-id="ead73-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="ead73-114">可能有害的應用程式封鎖</span><span class="sxs-lookup"><span data-stu-id="ead73-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="ead73-115">允許連線至 Microsoft Defender 防毒軟體雲端服務</span><span class="sxs-lookup"><span data-stu-id="ead73-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="ead73-116">Microsoft Defender 防毒軟體 cloud service 為您的端點提供快速、強大的保護。</span><span class="sxs-lookup"><span data-stu-id="ead73-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="ead73-117">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和整個網路提供重要的防護。</span><span class="sxs-lookup"><span data-stu-id="ead73-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span> <span data-ttu-id="ead73-118">請參閱[啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)，以取得使用 Intune、Microsoft Endpoint Configuration Manager、群組原則、PowerShell 指令程式或 Windows 安全性應用程式中個別用戶端上啟用服務的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ead73-118">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="ead73-119">在您啟用服務之後，您可能需要設定網路或防火牆，以允許其和您的端點之間的連線。</span><span class="sxs-lookup"><span data-stu-id="ead73-119">After you've enabled the service, you might need to configure your network or firewall to allow connections between it and your endpoints.</span></span> <span data-ttu-id="ead73-120">因為您的保護是雲端服務，所以電腦必須能夠存取網際網路，並接觸 Microsoft Defender for a machine 教學 services Office 365。</span><span class="sxs-lookup"><span data-stu-id="ead73-120">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="ead73-121">請勿 `*.blob.core.windows.net` 從任何類型的網路檢查中排除 URL。</span><span class="sxs-lookup"><span data-stu-id="ead73-121">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span>

> [!NOTE]
> <span data-ttu-id="ead73-122">Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。</span><span class="sxs-lookup"><span data-stu-id="ead73-122">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="ead73-123">雖然它稱為雲端服務，但並不只是保護儲存在雲端中的檔案，而是使用分散式資源和機器學習功能，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="ead73-123">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

## <a name="services-and-urls"></a><span data-ttu-id="ead73-124">服務和 URLs</span><span class="sxs-lookup"><span data-stu-id="ead73-124">Services and URLs</span></span>

<span data-ttu-id="ead73-125">本節中的表格列出 (URLs) 的服務及其相關聯的網站位址。</span><span class="sxs-lookup"><span data-stu-id="ead73-125">The table in this section lists the services and their associated website addresses (URLs).</span></span> 

<span data-ttu-id="ead73-126">請確定沒有防火牆或網路篩選規則拒絕存取這些 URLs。</span><span class="sxs-lookup"><span data-stu-id="ead73-126">Make sure that there are no firewall or network filtering rules denying access to these URLs.</span></span> <span data-ttu-id="ead73-127">否則，您可能需要為 (排除 URL) 以外的使用者建立允許規則 `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="ead73-127">Otherwise, you might need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="ead73-128">下表中的 URLs 使用埠443進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ead73-128">The URLs in the following table use port 443 for communication.</span></span>

| <span data-ttu-id="ead73-129">服務和描述</span><span class="sxs-lookup"><span data-stu-id="ead73-129">Service and description</span></span> | <span data-ttu-id="ead73-130">URL</span><span class="sxs-lookup"><span data-stu-id="ead73-130">URL</span></span> |
|----|---- |
| <span data-ttu-id="ead73-131">Microsoft Defender 防毒軟體雲端提供的保護服務，也稱為 Microsoft Active Protection Service (對應) </span><span class="sxs-lookup"><span data-stu-id="ead73-131">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span><p><span data-ttu-id="ead73-132">Microsoft Defender 防毒軟體使用此服務提供雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="ead73-132">This service is used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| <span data-ttu-id="ead73-133">Microsoft Update service (MU) 和 Windows Update service (WU) </span><span class="sxs-lookup"><span data-stu-id="ead73-133">Microsoft Update Service (MU) and Windows Update Service (WU)</span></span> <p><span data-ttu-id="ead73-134">這些服務可讓安全性情報和產品更新</span><span class="sxs-lookup"><span data-stu-id="ead73-134">These services allow for security intelligence and product updates</span></span> |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> <span data-ttu-id="ead73-135">如需詳細資訊，請參閱[Windows 更新的連接端點](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="ead73-135">For more details, see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="ead73-136">安全性智慧更新替代下載位置 (ADL) </span><span class="sxs-lookup"><span data-stu-id="ead73-136">Security intelligence updates Alternate Download Location (ADL)</span></span><p><span data-ttu-id="ead73-137">如果已安裝的安全性情報已過時 (7 天以上，則為 Microsoft Defender 防毒軟體安全性智慧更新的替代位置) </span><span class="sxs-lookup"><span data-stu-id="ead73-137">This is an alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>| `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="ead73-138">惡意程式碼提交存放區</span><span class="sxs-lookup"><span data-stu-id="ead73-138">Malware submission storage</span></span> <p><span data-ttu-id="ead73-139">這是透過提交表單或自動範例提交提交給 Microsoft 的檔案上傳位置。</span><span class="sxs-lookup"><span data-stu-id="ead73-139">This is the upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span> | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="ead73-140"> (CRL) 的憑證吊銷清單</span><span class="sxs-lookup"><span data-stu-id="ead73-140">Certificate Revocation List (CRL)</span></span> <p><span data-ttu-id="ead73-141">當您建立連結至地圖的 SSL 連線以更新 CRL 時，就會使用此清單 Windows</span><span class="sxs-lookup"><span data-stu-id="ead73-141">This list is used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span> | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="ead73-142">符號儲存區</span><span class="sxs-lookup"><span data-stu-id="ead73-142">Symbol Store</span></span> <p><span data-ttu-id="ead73-143">符號存放區是由 Microsoft Defender 防毒軟體用來在修正流程中還原某些重要的檔案</span><span class="sxs-lookup"><span data-stu-id="ead73-143">The symbol store is used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span> | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="ead73-144">通用遙測用戶端</span><span class="sxs-lookup"><span data-stu-id="ead73-144">Universal Telemetry Client</span></span> <p><span data-ttu-id="ead73-145">Windows 使用此用戶端傳送用戶端診斷資料</span><span class="sxs-lookup"><span data-stu-id="ead73-145">This client is used by Windows to send client diagnostic data</span></span><p> <span data-ttu-id="ead73-146">Microsoft Defender 防毒軟體使用遙測進行產品品質監控的目的</span><span class="sxs-lookup"><span data-stu-id="ead73-146">Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span> | <span data-ttu-id="ead73-147">更新使用 SSL (TCP 埠 443) 下載資訊清單，並將使用下列 DNS 端點的診斷資料上傳至 Microsoft：</span><span class="sxs-lookup"><span data-stu-id="ead73-147">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:</span></span> <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="ead73-148">驗證網路與雲端之間的連線</span><span class="sxs-lookup"><span data-stu-id="ead73-148">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="ead73-149">允許上述 URLs 之後，您可以測試是否已連線到 Microsoft Defender 防毒軟體雲端服務，並正確報告和接收資訊，以確保您受到完全保護。</span><span class="sxs-lookup"><span data-stu-id="ead73-149">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a><span data-ttu-id="ead73-150">使用 cmdline 工具來驗證雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="ead73-150">Use the cmdline tool to validate cloud-delivered protection</span></span>

<span data-ttu-id="ead73-151">在 Microsoft Defender 防毒軟體命令列公用程式 () 使用下列引數， `mpcmdrun.exe` 以確認您的網路能夠與 Microsoft Defender 防毒軟體雲端服務通訊：</span><span class="sxs-lookup"><span data-stu-id="ead73-151">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="ead73-152">您必須開啟命令提示字元的系統管理員層級版本。</span><span class="sxs-lookup"><span data-stu-id="ead73-152">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="ead73-153">在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行**]，然後在 [許可權] 提示中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="ead73-153">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="ead73-154">這個命令只會在 Windows 10 版本1703或更高版本上運作。</span><span class="sxs-lookup"><span data-stu-id="ead73-154">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="ead73-155">如需詳細資訊，請參閱[使用 mpcmdrun.exe 命令列工具管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ead73-155">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a><span data-ttu-id="ead73-156">嘗試從 Microsoft 下載虛假惡意程式碼檔</span><span class="sxs-lookup"><span data-stu-id="ead73-156">Attempt to download a fake malware file from Microsoft</span></span>

<span data-ttu-id="ead73-157">您可以下載範例檔案，當您已正確連接至雲端時，Microsoft Defender 防毒軟體會偵測並封鎖。</span><span class="sxs-lookup"><span data-stu-id="ead73-157">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="ead73-158">透過訪問下載檔案 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。</span><span class="sxs-lookup"><span data-stu-id="ead73-158">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="ead73-159">此檔案不是惡意程式碼的實際部分。</span><span class="sxs-lookup"><span data-stu-id="ead73-159">This file is not an actual piece of malware.</span></span> <span data-ttu-id="ead73-160">這是一個偽檔案，其設計目的是為了測試您是否已正確連接至雲端。</span><span class="sxs-lookup"><span data-stu-id="ead73-160">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="ead73-161">正確連接後，您會看到警告 Microsoft Defender 防毒軟體通知。</span><span class="sxs-lookup"><span data-stu-id="ead73-161">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="ead73-162">如果您正在使用 Microsoft Edge，您也會看到通知訊息：</span><span class="sxs-lookup"><span data-stu-id="ead73-162">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="在 Edge 中找到惡意程式碼之通知的螢幕擷取畫面":::

<span data-ttu-id="ead73-164">當您使用 Internet Explorer 時，會發生類似的訊息：</span><span class="sxs-lookup"><span data-stu-id="ead73-164">A similar message occurs if you're using Internet Explorer:</span></span>

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="找到惡意程式碼的 Microsoft Defender AV 通知":::

<span data-ttu-id="ead73-166">您也會在 Windows 安全性應用程式的 [掃描歷程 **記錄**] 區段中看到 [**隔離威脅**] 下的偵測：</span><span class="sxs-lookup"><span data-stu-id="ead73-166">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="ead73-167">按一下工作列中的盾牌圖示，或搜尋 [**安全性**] 的 [開始] 功能表，開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="ead73-167">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="ead73-168">選取 [ **病毒 & 威脅防護**]，然後選取 [ **保護歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ead73-168">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="ead73-169">在 [ **隔離威脅** ] 區段中，選取 [ **查看完整的史** ]，以查看偵測到的虛假惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="ead73-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ead73-170">版本1703之前的 Windows 10 版本都具有不同的使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ead73-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="ead73-171">請參閱[Windows 安全性應用程式中的 Microsoft Defender 防毒軟體](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ead73-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="ead73-172">Windows 事件記錄也會顯示[Windows Defender 用戶端事件識別碼 1116](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ead73-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>
