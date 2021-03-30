---
title: Microsoft Defender ATP （適用于 Linux）
ms.reviewer: ''
description: 說明如何安裝及使用 Microsoft Defender ATP for Linux。
keywords: microsoft，defender，atp，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 08bb4c73cb9df429c4b07194f1c7615f44d745d8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408334"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="edac1-104">Linux 版適用於端點的 Microsoft Defende</span><span class="sxs-lookup"><span data-stu-id="edac1-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="edac1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="edac1-105">**Applies to:**</span></span>
- [<span data-ttu-id="edac1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="edac1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="edac1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edac1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="edac1-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="edac1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="edac1-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="edac1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="edac1-110">本主題說明如何針對 Linux 安裝、設定、更新及使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="edac1-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="edac1-111">針對 Linux 執行其他協力廠商端點保護產品及 Microsoft Defender for Linux，都可能會造成效能問題和不可預期的系統錯誤。</span><span class="sxs-lookup"><span data-stu-id="edac1-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="edac1-112">如何為 Linux 安裝 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edac1-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="edac1-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="edac1-113">Prerequisites</span></span>

- <span data-ttu-id="edac1-114">存取 Microsoft Defender 安全中心入口網站</span><span class="sxs-lookup"><span data-stu-id="edac1-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="edac1-115">使用 [systemd](https://systemd.io/) 系統管理員的 Linux 發行</span><span class="sxs-lookup"><span data-stu-id="edac1-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="edac1-116">在 Linux 和 BASH 腳本中的初級層級體驗</span><span class="sxs-lookup"><span data-stu-id="edac1-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="edac1-117">當手動部署時，裝置上的系統管理許可權 () </span><span class="sxs-lookup"><span data-stu-id="edac1-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="edac1-118">安裝指示</span><span class="sxs-lookup"><span data-stu-id="edac1-118">Installation instructions</span></span>

<span data-ttu-id="edac1-119">您可以使用數種方法和部署工具，為 Linux 安裝和設定 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="edac1-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="edac1-120">一般說來，您必須採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="edac1-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="edac1-121">確定您有 Microsoft Defender for Endpoint 訂閱，且您可以存取 [Microsoft defender For endpoint 入口網站](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="edac1-122">使用下列其中一個部署方法，為 Linux 部署 Microsoft Defender for Linux：</span><span class="sxs-lookup"><span data-stu-id="edac1-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="edac1-123">命令列工具：</span><span class="sxs-lookup"><span data-stu-id="edac1-123">The command-line tool:</span></span>
    - [<span data-ttu-id="edac1-124">手動部署</span><span class="sxs-lookup"><span data-stu-id="edac1-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="edac1-125">協力廠商管理工具：</span><span class="sxs-lookup"><span data-stu-id="edac1-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="edac1-126">使用 Puppet 建構管理工具進行部署</span><span class="sxs-lookup"><span data-stu-id="edac1-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="edac1-127">使用 Ansible 建構管理工具進行部署</span><span class="sxs-lookup"><span data-stu-id="edac1-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="edac1-128">如果您遇到任何安裝失敗，請參閱 [Microsoft Defender For Linux 中的疑難排解安裝失敗](linux-support-install.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="edac1-129">系統需求</span><span class="sxs-lookup"><span data-stu-id="edac1-129">System requirements</span></span>

- <span data-ttu-id="edac1-130">支援的 Linux 伺服器發行及版本：</span><span class="sxs-lookup"><span data-stu-id="edac1-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="edac1-131">Red Hat Enterprise Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="edac1-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="edac1-132">CentOS 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="edac1-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="edac1-133">Ubuntu 16.04 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="edac1-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="edac1-134">Debian 9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="edac1-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="edac1-135">SUSE Linux Enterprise Server 12 或更高版本</span><span class="sxs-lookup"><span data-stu-id="edac1-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="edac1-136">Oracle Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="edac1-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="edac1-137">最小內核版本 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="edac1-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="edac1-138">`fanotify`必須啟用內核選項</span><span class="sxs-lookup"><span data-stu-id="edac1-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="edac1-139">不支援以其他方式的安全性解決方案為基礎，針對 Linux 的端點執行 Defender `fanotify` 。</span><span class="sxs-lookup"><span data-stu-id="edac1-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="edac1-140">這可能會造成無法預期的結果，包括懸掛作業系統。</span><span class="sxs-lookup"><span data-stu-id="edac1-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="edac1-141">磁碟空間：1GB</span><span class="sxs-lookup"><span data-stu-id="edac1-141">Disk space: 1GB</span></span>
- <span data-ttu-id="edac1-142">/opt/microsoft/mdatp/sbin/wdavdaemon 需要可執行檔許可權。</span><span class="sxs-lookup"><span data-stu-id="edac1-142">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="edac1-143">如需詳細資訊，請參閱 [Microsoft DEFENDER ATP For Linux 的安裝問題疑難排解](/microsoft-365/security/defender-endpoint/linux-support-install)中的「確定守護程式具有可執行檔許可權」。</span><span class="sxs-lookup"><span data-stu-id="edac1-143">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="edac1-144">記憶體：1GB</span><span class="sxs-lookup"><span data-stu-id="edac1-144">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="edac1-145">請確認您在/var. 中有可用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="edac1-145">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="edac1-146">目前的解決方案為下列檔案系統類型提供即時保護：</span><span class="sxs-lookup"><span data-stu-id="edac1-146">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="edac1-147">在您啟用服務之後，您可能需要設定網路或防火牆，以允許它和您的端點之間的輸出連線。</span><span class="sxs-lookup"><span data-stu-id="edac1-147">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="edac1-148">必須啟用審核架構 (`auditd`) 。</span><span class="sxs-lookup"><span data-stu-id="edac1-148">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="edac1-149">新增至審核記錄的規則所捕獲的系統事件 `audit.logs` 會將其新增至審核記錄，而且可能會影響主機審核和上游集合。</span><span class="sxs-lookup"><span data-stu-id="edac1-149">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="edac1-150">Microsoft Defender for Endopoint for Linux 新增的事件將會以 `mdatp` 金鑰標示。</span><span class="sxs-lookup"><span data-stu-id="edac1-150">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="edac1-151">網路連線</span><span class="sxs-lookup"><span data-stu-id="edac1-151">Network connections</span></span>

<span data-ttu-id="edac1-152">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="edac1-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="edac1-153">您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權。</span><span class="sxs-lookup"><span data-stu-id="edac1-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="edac1-154">如果有，您可能需要專門為其建立一個 *allow* 規則。</span><span class="sxs-lookup"><span data-stu-id="edac1-154">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="edac1-155">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="edac1-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="edac1-156">**描述**</span><span class="sxs-lookup"><span data-stu-id="edac1-156">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="edac1-158">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="edac1-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="edac1-159">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="edac1-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="edac1-160">如需詳細的 URL 清單，請參閱 [設定 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="edac1-160">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="edac1-161">「！的 Defender」可以使用下列探索方法探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="edac1-161">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="edac1-162">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="edac1-162">Transparent proxy</span></span>
- <span data-ttu-id="edac1-163">手動靜態 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="edac1-163">Manual static proxy configuration</span></span>

<span data-ttu-id="edac1-164">如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="edac1-164">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="edac1-165">針對透明 proxy，不需要其他設定供 Defender 用於端點。</span><span class="sxs-lookup"><span data-stu-id="edac1-165">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="edac1-166">針對靜態 proxy，依照 [手動靜態 proxy](linux-static-proxy-configuration.md)設定中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="edac1-166">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="edac1-167">不支援 PAC、WPAD 及已驗證的 proxy。</span><span class="sxs-lookup"><span data-stu-id="edac1-167">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="edac1-168">確定只使用靜態 proxy 或透明 proxy。</span><span class="sxs-lookup"><span data-stu-id="edac1-168">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="edac1-169">出於安全性原因，也不支援 SSL 檢查和截取 proxy。</span><span class="sxs-lookup"><span data-stu-id="edac1-169">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="edac1-170">設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接透過來自 Linux 的 Defender 的資料傳遞至相關的 URLs，而不需截獲。</span><span class="sxs-lookup"><span data-stu-id="edac1-170">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="edac1-171">將您的截取憑證新增至全域存放區將不允許截取。</span><span class="sxs-lookup"><span data-stu-id="edac1-171">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="edac1-172">如需疑難排解步驟，請參閱 [疑難排解 Microsoft Defender for a For Linux 之 cloud connectivity connectivity 的問題](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-172">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="edac1-173">如何為 Linux 更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edac1-173">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="edac1-174">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="edac1-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="edac1-175">若要更新 Microsoft Defender for Linux，請參閱為 [Linux 部署 Microsoft defender For endpoint 的更新](linux-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-175">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="edac1-176">如何為 Linux 設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edac1-176">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="edac1-177">有關如何在企業環境中設定產品的指引，可在 [設定 Microsoft Defender For Linux 的首選項中取得](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="edac1-178">資源</span><span class="sxs-lookup"><span data-stu-id="edac1-178">Resources</span></span>

- <span data-ttu-id="edac1-179">如需有關記錄、卸載或其他主題的詳細資訊，請參閱 [Resources](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="edac1-179">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
