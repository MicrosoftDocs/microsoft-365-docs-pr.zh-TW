---
title: 設定及驗證 Microsoft Defender 防毒軟體網路連線
description: 設定並測試您與 Microsoft Defender 防病毒雲端保護服務的連線。
keywords: 防病毒，Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6218bc32690ca42c06b5606d8a3922f6fc5c7307
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765152"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="a8815-104">設定及驗證 Microsoft Defender 防毒軟體網路連線</span><span class="sxs-lookup"><span data-stu-id="a8815-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a8815-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a8815-105">**Applies to:**</span></span>

- [<span data-ttu-id="a8815-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8815-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a8815-107">為了確保 Microsoft Defender 防病毒雲端提供的保護運作正常，您必須設定網路以允許端點和某些 Microsoft 伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="a8815-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="a8815-108">本文列出必須允許的連線，例如使用防火牆規則，並提供驗證連線的指示。</span><span class="sxs-lookup"><span data-stu-id="a8815-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="a8815-109">正確設定保護可協助確保您從雲端提供的保護服務中取得最佳價值。</span><span class="sxs-lookup"><span data-stu-id="a8815-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="a8815-110">如需網路連線的某些詳細資料，請參閱博客文章 [重要變更 Microsoft Active Protection Services 端點](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 。</span><span class="sxs-lookup"><span data-stu-id="a8815-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="a8815-111">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作：</span><span class="sxs-lookup"><span data-stu-id="a8815-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="a8815-112">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="a8815-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="a8815-113">Fast 教學 (包括第一次看到區塊) </span><span class="sxs-lookup"><span data-stu-id="a8815-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="a8815-114">可能有害的應用程式封鎖</span><span class="sxs-lookup"><span data-stu-id="a8815-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="a8815-115">允許連線至 Microsoft Defender 防病毒雲端服務</span><span class="sxs-lookup"><span data-stu-id="a8815-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="a8815-116">Microsoft Defender 防毒軟體雲端服務為您的端點提供快速、強大的保護。</span><span class="sxs-lookup"><span data-stu-id="a8815-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="a8815-117">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和整個網路提供重要的防護。</span><span class="sxs-lookup"><span data-stu-id="a8815-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="a8815-118">Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。</span><span class="sxs-lookup"><span data-stu-id="a8815-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="a8815-119">雖然它稱為雲端服務，但並不只是保護儲存在雲端中的檔案，而是使用分散式資源和機器學習功能，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="a8815-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="a8815-120">請參閱 [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) ，以取得使用 Intune、Microsoft 端點設定管理員、群組原則、PowerShell Cmdlet 或 Windows 安全性應用程式中個別用戶端上啟用服務的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a8815-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="a8815-121">在您啟用服務之後，您可能需要設定網路或防火牆，以允許其和您的端點之間的連線。</span><span class="sxs-lookup"><span data-stu-id="a8815-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="a8815-122">因為您的保護是雲端服務，所以電腦必須能夠存取網際網路，並且到達 Microsoft Defender for Office 365 機器教學服務。</span><span class="sxs-lookup"><span data-stu-id="a8815-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="a8815-123">請勿 `*.blob.core.windows.net` 從任何類型的網路檢查中排除 URL。</span><span class="sxs-lookup"><span data-stu-id="a8815-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="a8815-124">下表列出服務及其相關聯的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a8815-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="a8815-125">請確定沒有任何防火牆或網路篩選規則拒絕存取這些 URLs，否則您可能需要建立專用的 allow 規則 (排除 URL `*.blob.core.windows.net`) 。</span><span class="sxs-lookup"><span data-stu-id="a8815-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="a8815-126">以下提及 URLs 使用埠443進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a8815-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="a8815-127">**服務**</span><span class="sxs-lookup"><span data-stu-id="a8815-127">**Service**</span></span>| <span data-ttu-id="a8815-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="a8815-128">**Description**</span></span> |<span data-ttu-id="a8815-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="a8815-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="a8815-130">Microsoft Defender 防病毒雲端提供的保護服務，也稱為 Microsoft Active Protection Service (MAPS) </span><span class="sxs-lookup"><span data-stu-id="a8815-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="a8815-131">Microsoft Defender 防病毒用以提供雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="a8815-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="a8815-132">Microsoft Update Service (MU) </span><span class="sxs-lookup"><span data-stu-id="a8815-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="a8815-133">Windows Update Service (WU) </span><span class="sxs-lookup"><span data-stu-id="a8815-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="a8815-134">安全性智慧及產品更新</span><span class="sxs-lookup"><span data-stu-id="a8815-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="a8815-135">如需詳細資訊，請參閱 [Windows Update 的連接端點](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="a8815-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="a8815-136">安全性智慧更新替代下載位置 (ADL) </span><span class="sxs-lookup"><span data-stu-id="a8815-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="a8815-137">Microsoft Defender 防病毒安全性情報更新的替代位置（如果已安裝的安全性情報已過期 (7 天以上或以上版本）) </span><span class="sxs-lookup"><span data-stu-id="a8815-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="a8815-138">惡意程式碼提交存放區</span><span class="sxs-lookup"><span data-stu-id="a8815-138">Malware submission storage</span></span>|<span data-ttu-id="a8815-139">透過提交表單或自動範例提交提交給 Microsoft 的檔案上傳位置</span><span class="sxs-lookup"><span data-stu-id="a8815-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="a8815-140"> (CRL) 的憑證吊銷清單</span><span class="sxs-lookup"><span data-stu-id="a8815-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="a8815-141">當您建立連結至地圖的 SSL 連線以更新 CRL 時，由 Windows 使用</span><span class="sxs-lookup"><span data-stu-id="a8815-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="a8815-142">符號儲存區</span><span class="sxs-lookup"><span data-stu-id="a8815-142">Symbol Store</span></span>|<span data-ttu-id="a8815-143">Microsoft Defender 防毒程式用來在修正流程期間還原某些重要檔案</span><span class="sxs-lookup"><span data-stu-id="a8815-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="a8815-144">通用遙測用戶端</span><span class="sxs-lookup"><span data-stu-id="a8815-144">Universal Telemetry Client</span></span>| <span data-ttu-id="a8815-145">由 Windows 用來傳送用戶端診斷資料;Microsoft Defender 防病毒使用遙測進行產品品質監控的目的</span><span class="sxs-lookup"><span data-stu-id="a8815-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="a8815-146">更新使用 SSL (TCP 埠 443) 下載資訊清單，並將使用下列 DNS 端點的診斷資料上傳至 Microsoft：   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a8815-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="a8815-147">驗證網路與雲端之間的連線</span><span class="sxs-lookup"><span data-stu-id="a8815-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="a8815-148">在允許上述 URLs 之後，您可以測試是否已連線至 Microsoft Defender 防毒軟體雲端服務，以及是否正確報告和接收資訊，以確保您受到完全保護。</span><span class="sxs-lookup"><span data-stu-id="a8815-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="a8815-149">**使用 cmdline 工具來驗證雲端提供的保護：**</span><span class="sxs-lookup"><span data-stu-id="a8815-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="a8815-150">使用下列引數搭配 Microsoft Defender 防病毒命令列實用程式 (`mpcmdrun.exe`) ，以確認您的網路可以與 Microsoft Defender 防病毒雲端服務通訊：</span><span class="sxs-lookup"><span data-stu-id="a8815-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="a8815-151">您必須開啟命令提示字元的系統管理員層級版本。</span><span class="sxs-lookup"><span data-stu-id="a8815-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="a8815-152">在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行** ]，然後在許可權提示中按一下 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="a8815-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="a8815-153">這個命令只會在 Windows 10、版本1703或更高版本上運作。</span><span class="sxs-lookup"><span data-stu-id="a8815-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="a8815-154">如需詳細資訊，請參閱 [使用 mpcmdrun.exe 命令命令列工具管理 Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a8815-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a8815-155">**嘗試從 Microsoft 下載虛假惡意程式碼檔：**</span><span class="sxs-lookup"><span data-stu-id="a8815-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="a8815-156">您可以下載一個範例檔案，當您已正確連接至雲端時，Microsoft Defender 防毒軟體會偵測並封鎖這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a8815-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="a8815-157">透過訪問下載檔案 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。</span><span class="sxs-lookup"><span data-stu-id="a8815-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="a8815-158">此檔案不是惡意程式碼的實際部分。</span><span class="sxs-lookup"><span data-stu-id="a8815-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="a8815-159">這是一個偽檔案，其設計目的是為了測試您是否已正確連接至雲端。</span><span class="sxs-lookup"><span data-stu-id="a8815-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="a8815-160">如果您已正確連線，您會看到 Microsoft Defender 防病毒通知的警告。</span><span class="sxs-lookup"><span data-stu-id="a8815-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="a8815-161">如果您使用的是 Microsoft Edge，您也會看到一則通知訊息：</span><span class="sxs-lookup"><span data-stu-id="a8815-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge 告知使用者發現惡意程式碼](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="a8815-163">當您使用 Internet Explorer 時，會發生類似的訊息：</span><span class="sxs-lookup"><span data-stu-id="a8815-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender 防病毒通知會通知使用者發現惡意程式碼](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="a8815-165">您也可以在 Windows 安全性應用程式的 [**掃描記錄**] 區段中看到 [**隔離威脅**] 下的偵測：</span><span class="sxs-lookup"><span data-stu-id="a8815-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="a8815-166">按一下工作列上的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8815-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="a8815-167">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後按一下 [ **掃描歷程記錄** ] 標籤：</span><span class="sxs-lookup"><span data-stu-id="a8815-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Windows 安全性應用程式中 [掃描史] 標籤的螢幕擷取畫面](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="a8815-169">在 [ **隔離威脅** ] 區段中，選取 [ **查看完整的史** ]，以查看偵測到的虛假惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="a8815-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8815-170">版本1703之前的 Windows 10 版本具有不同的使用者介面。</span><span class="sxs-lookup"><span data-stu-id="a8815-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="a8815-171">請參閱 [Windows 安全性應用程式中的 Microsoft Defender 防病毒](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a8815-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="a8815-172">Windows 事件記錄也會顯示 [Windows Defender 用戶端事件識別碼 1116](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a8815-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a8815-173">相關文章</span><span class="sxs-lookup"><span data-stu-id="a8815-173">Related articles</span></span>

- [<span data-ttu-id="a8815-174">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="a8815-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="a8815-175">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="a8815-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a8815-176">命令列引數</span><span class="sxs-lookup"><span data-stu-id="a8815-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a8815-177">Microsoft Active Protection Services 端點的重要變更</span><span class="sxs-lookup"><span data-stu-id="a8815-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)