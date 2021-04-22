---
title: Linux 上適用於端點的 Microsoft Defender
ms.reviewer: ''
description: 說明如何在 Linux 上安裝及使用 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.openlocfilehash: 34274e260da2e8acc8088fcff6d324b6b31fc2ef
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935938"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="acaeb-104">Linux 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="acaeb-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="acaeb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="acaeb-105">**Applies to:**</span></span>
- [<span data-ttu-id="acaeb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="acaeb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="acaeb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acaeb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="acaeb-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="acaeb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="acaeb-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="acaeb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="acaeb-110">本主題說明如何在 Linux 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="acaeb-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="acaeb-111">在 Linux 上執行其他協力廠商端點保護產品及 Microsoft Defender for Endpoint 時，可能會造成效能問題和不可預測的副作用。</span><span class="sxs-lookup"><span data-stu-id="acaeb-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="acaeb-112">若非 Microsoft endpoint protection 是您環境中的絕對需求，則在將防病毒功能設定為以 [被動式模式](linux-preferences.md#enable--disable-passive-mode)執行之前，您仍然可以安全地利用適用于 Linux EDR 功能的 Defender for endpoint。</span><span class="sxs-lookup"><span data-stu-id="acaeb-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="acaeb-113">如何在 Linux 上安裝 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="acaeb-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="acaeb-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="acaeb-114">Prerequisites</span></span>

- <span data-ttu-id="acaeb-115">存取 Microsoft Defender 安全中心入口網站</span><span class="sxs-lookup"><span data-stu-id="acaeb-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="acaeb-116">使用 [systemd](https://systemd.io/) 系統管理員的 Linux 發行</span><span class="sxs-lookup"><span data-stu-id="acaeb-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="acaeb-117">在 Linux 和 BASH 腳本中的初級層級體驗</span><span class="sxs-lookup"><span data-stu-id="acaeb-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="acaeb-118">當手動部署時，裝置上的系統管理許可權 () </span><span class="sxs-lookup"><span data-stu-id="acaeb-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="acaeb-119">安裝指示</span><span class="sxs-lookup"><span data-stu-id="acaeb-119">Installation instructions</span></span>

<span data-ttu-id="acaeb-120">您可以使用數種方法和部署工具，在 Linux 上安裝及設定 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="acaeb-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="acaeb-121">一般說來，您必須採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="acaeb-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="acaeb-122">確定您有 Microsoft Defender for Endpoint 訂閱，且您可以存取 [Microsoft defender For endpoint 入口網站](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="acaeb-123">使用下列其中一個部署方法，在 Linux 上部署 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="acaeb-123">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="acaeb-124">命令列工具：</span><span class="sxs-lookup"><span data-stu-id="acaeb-124">The command-line tool:</span></span>
    - [<span data-ttu-id="acaeb-125">手動部署</span><span class="sxs-lookup"><span data-stu-id="acaeb-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="acaeb-126">協力廠商管理工具：</span><span class="sxs-lookup"><span data-stu-id="acaeb-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="acaeb-127">使用 Puppet 建構管理工具進行部署</span><span class="sxs-lookup"><span data-stu-id="acaeb-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="acaeb-128">使用 Ansible 建構管理工具進行部署</span><span class="sxs-lookup"><span data-stu-id="acaeb-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="acaeb-129">如果您遇到任何安裝失敗問題，請參閱在 [Linux 上的 Microsoft Defender For Endpoint 中的安裝失敗疑難排解](linux-support-install.md)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="acaeb-130">系統需求</span><span class="sxs-lookup"><span data-stu-id="acaeb-130">System requirements</span></span>

- <span data-ttu-id="acaeb-131">支援的 Linux 伺服器發行及版本：</span><span class="sxs-lookup"><span data-stu-id="acaeb-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="acaeb-132">Red Hat Enterprise Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="acaeb-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="acaeb-133">CentOS 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="acaeb-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="acaeb-134">Ubuntu 16.04 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="acaeb-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="acaeb-135">Debian 9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="acaeb-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="acaeb-136">SUSE Linux Enterprise Server 12 或更高版本</span><span class="sxs-lookup"><span data-stu-id="acaeb-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="acaeb-137">Oracle Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="acaeb-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="acaeb-138">最小內核版本 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="acaeb-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="acaeb-139">`fanotify`必須啟用內核選項</span><span class="sxs-lookup"><span data-stu-id="acaeb-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="acaeb-140">不支援以其他方式的安全性解決方案，並排在 Linux 上執行 Defender for Endpoint `fanotify` 。</span><span class="sxs-lookup"><span data-stu-id="acaeb-140">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="acaeb-141">這可能會造成無法預期的結果，包括懸掛作業系統。</span><span class="sxs-lookup"><span data-stu-id="acaeb-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="acaeb-142">磁碟空間：1GB</span><span class="sxs-lookup"><span data-stu-id="acaeb-142">Disk space: 1GB</span></span>
- <span data-ttu-id="acaeb-143">/opt/microsoft/mdatp/sbin/wdavdaemon 需要可執行檔許可權。</span><span class="sxs-lookup"><span data-stu-id="acaeb-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="acaeb-144">如需詳細資訊，請參閱 [疑難排解 Microsoft Defender for The Linux 上的 Microsoft Defender For Endpoint 的安裝問題](/microsoft-365/security/defender-endpoint/linux-support-install)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="acaeb-145">記憶體：1GB</span><span class="sxs-lookup"><span data-stu-id="acaeb-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="acaeb-146">請確認您在/var. 中有可用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="acaeb-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="acaeb-147">目前的解決方案為下列檔案系統類型提供即時保護：</span><span class="sxs-lookup"><span data-stu-id="acaeb-147">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="acaeb-148">在您啟用服務之後，您可能需要設定網路或防火牆，以允許它和您的端點之間的輸出連線。</span><span class="sxs-lookup"><span data-stu-id="acaeb-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="acaeb-149">必須啟用審核架構 (`auditd`) 。</span><span class="sxs-lookup"><span data-stu-id="acaeb-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="acaeb-150">新增至的規則所捕獲的系統事件 `/etc/audit/rules.d/` 會新增至 `audit.log` (s) ，而且可能會影響主機審核和上游集合。</span><span class="sxs-lookup"><span data-stu-id="acaeb-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="acaeb-151">在 Linux 上由 Microsoft Defender for Endpoint 新增的事件將會以 `mdatp` 金鑰標示。</span><span class="sxs-lookup"><span data-stu-id="acaeb-151">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="acaeb-152">網路連線</span><span class="sxs-lookup"><span data-stu-id="acaeb-152">Network connections</span></span>

<span data-ttu-id="acaeb-153">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="acaeb-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="acaeb-154">您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權。</span><span class="sxs-lookup"><span data-stu-id="acaeb-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="acaeb-155">如果有，您可能需要專門為其建立一個 *allow* 規則。</span><span class="sxs-lookup"><span data-stu-id="acaeb-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="acaeb-156">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="acaeb-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="acaeb-157">**描述**</span><span class="sxs-lookup"><span data-stu-id="acaeb-157">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="acaeb-159">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="acaeb-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="acaeb-160">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="acaeb-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="acaeb-161">如需詳細的 URL 清單，請參閱 [設定 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="acaeb-162">「！的 Defender」可以使用下列探索方法探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="acaeb-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="acaeb-163">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="acaeb-163">Transparent proxy</span></span>
- <span data-ttu-id="acaeb-164">手動靜態 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="acaeb-164">Manual static proxy configuration</span></span>

<span data-ttu-id="acaeb-165">如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="acaeb-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="acaeb-166">針對透明 proxy，不需要其他設定供 Defender 用於端點。</span><span class="sxs-lookup"><span data-stu-id="acaeb-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="acaeb-167">針對靜態 proxy，依照 [手動靜態 proxy](linux-static-proxy-configuration.md)設定中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="acaeb-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="acaeb-168">不支援 PAC、WPAD 及已驗證的 proxy。</span><span class="sxs-lookup"><span data-stu-id="acaeb-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="acaeb-169">確定只使用靜態 proxy 或透明 proxy。</span><span class="sxs-lookup"><span data-stu-id="acaeb-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="acaeb-170">出於安全性原因，也不支援 SSL 檢查和截取 proxy。</span><span class="sxs-lookup"><span data-stu-id="acaeb-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="acaeb-171">設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接將來自 Linux 之 Defender 的資料傳遞至相關的 URLs，而不需截獲。</span><span class="sxs-lookup"><span data-stu-id="acaeb-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="acaeb-172">將您的截取憑證新增至全域存放區將不允許截取。</span><span class="sxs-lookup"><span data-stu-id="acaeb-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="acaeb-173">如需疑難排解步驟，請參閱 [疑難排解 Microsoft Defender for a For Endpoint On Linux 上的 cloud connectivity connectivity 問題](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="acaeb-174">如何在 Linux 上更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="acaeb-174">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="acaeb-175">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="acaeb-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="acaeb-176">若要在 Linux 上更新 Microsoft Defender for Endpoint，請參閱 [在 linux 上為 Microsoft defender For Endpoint 部署更新](linux-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-176">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="acaeb-177">如何在 Linux 上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="acaeb-177">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="acaeb-178">有關如何在企業環境中設定產品的指引，可在 [Linux 上的 Microsoft Defender For Endpoint 的 [設定偏好設定](linux-preferences.md)] 中取得。</span><span class="sxs-lookup"><span data-stu-id="acaeb-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="acaeb-179">資源</span><span class="sxs-lookup"><span data-stu-id="acaeb-179">Resources</span></span>

- <span data-ttu-id="acaeb-180">如需有關記錄、卸載或其他主題的詳細資訊，請參閱 [Resources](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="acaeb-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
