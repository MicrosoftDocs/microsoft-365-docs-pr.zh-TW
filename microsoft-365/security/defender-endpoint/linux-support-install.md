---
title: 疑難排解 Linux 上 Microsoft Defender for Endpoint 的安裝問題
ms.reviewer: ''
description: 疑難排解 Linux 上 Microsoft Defender for Endpoint 的安裝問題
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝
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
ms.openlocfilehash: dc1e8707dc0810c0986698674a64e969792b5fb8
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311229"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="f7792-104">疑難排解 Linux 上 Microsoft Defender for Endpoint 的安裝問題</span><span class="sxs-lookup"><span data-stu-id="f7792-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7792-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f7792-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7792-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f7792-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7792-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7792-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7792-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f7792-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7792-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f7792-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="f7792-110">確認安裝是否成功</span><span class="sxs-lookup"><span data-stu-id="f7792-110">Verify if installation succeeded</span></span>

<span data-ttu-id="f7792-111">「安裝」中的錯誤可能會或不會由封裝管理員產生有意義的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f7792-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="f7792-112">若要確認安裝是否成功，請使用下列步驟取得並檢查安裝記錄檔：</span><span class="sxs-lookup"><span data-stu-id="f7792-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

```bash
 sudo journalctl --no-pager | grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

<span data-ttu-id="f7792-113">先前命令的輸出和安裝的正確日期和時間會指出成功。</span><span class="sxs-lookup"><span data-stu-id="f7792-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="f7792-114">此外，請檢查 [用戶端](linux-install-manually.md#client-configuration) 設定，以確認產品的健康情況，並偵測 eicar.txt 文字檔。</span><span class="sxs-lookup"><span data-stu-id="f7792-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="f7792-115">請確定您有正確的套件</span><span class="sxs-lookup"><span data-stu-id="f7792-115">Make sure you have the correct package</span></span>

<span data-ttu-id="f7792-116">請注意，您要安裝的套件符合主機發佈和版本。</span><span class="sxs-lookup"><span data-stu-id="f7792-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="f7792-117">包</span><span class="sxs-lookup"><span data-stu-id="f7792-117">package</span></span>                       | <span data-ttu-id="f7792-118">分佈</span><span class="sxs-lookup"><span data-stu-id="f7792-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="f7792-119">mdatp-rhel8.Linux.x86_64 rpm</span><span class="sxs-lookup"><span data-stu-id="f7792-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="f7792-120">Oracle、RHEL 和 CentOS ∞</span><span class="sxs-lookup"><span data-stu-id="f7792-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="f7792-121">mdatp-sles12.Linux.x86_64 rpm</span><span class="sxs-lookup"><span data-stu-id="f7792-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="f7792-122">SuSE Linux Enterprise Server 12. x</span><span class="sxs-lookup"><span data-stu-id="f7792-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="f7792-123">mdatp-sles15.Linux.x86_64 rpm</span><span class="sxs-lookup"><span data-stu-id="f7792-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="f7792-124">SuSE Linux Enterprise 伺服器15。</span><span class="sxs-lookup"><span data-stu-id="f7792-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="f7792-125">mdatp.Linux.x86_64 rpm</span><span class="sxs-lookup"><span data-stu-id="f7792-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="f7792-126">Oracle、RHEL 和 CentOS 7. x</span><span class="sxs-lookup"><span data-stu-id="f7792-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="f7792-127">mdatp.Linux.x86_64。 deb</span><span class="sxs-lookup"><span data-stu-id="f7792-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="f7792-128">Debian 和 Ubuntu 16.04、18.04 及20.04</span><span class="sxs-lookup"><span data-stu-id="f7792-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="f7792-129">若要進行 [手動部署](linux-install-manually.md)，請確定已選取正確的 distro 和版本。</span><span class="sxs-lookup"><span data-stu-id="f7792-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="f7792-130">安裝失敗</span><span class="sxs-lookup"><span data-stu-id="f7792-130">Installation failed</span></span>

<span data-ttu-id="f7792-131">檢查 mdatp 服務是否正在執行：</span><span class="sxs-lookup"><span data-stu-id="f7792-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="f7792-132">Mdatp 服務未執行時的疑難排解步驟</span><span class="sxs-lookup"><span data-stu-id="f7792-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="f7792-133">檢查是否存在 "mdatp" 使用者：</span><span class="sxs-lookup"><span data-stu-id="f7792-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="f7792-134">如果沒有輸出，請執行</span><span class="sxs-lookup"><span data-stu-id="f7792-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="f7792-135">嘗試啟用並重啟服務，請使用：</span><span class="sxs-lookup"><span data-stu-id="f7792-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="f7792-136">若執行先前命令時未找到 mdatp，請執行：</span><span class="sxs-lookup"><span data-stu-id="f7792-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="f7792-137">`<systemd_path>`位於 `/lib/systemd/system` Ubuntu 和 Debian 發行的位置， `/usr/lib/systemd/system` 以及 Rhel、CentOS、Oracle 和 SLES 的位置。</span><span class="sxs-lookup"><span data-stu-id="f7792-137">where `<systemd_path>` is `/lib/systemd/system` for Ubuntu and Debian distributions and `/usr/lib/systemd/system` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="f7792-138">然後重新執行步驟2。</span><span class="sxs-lookup"><span data-stu-id="f7792-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="f7792-139">如果上述步驟無法運作，請檢查是否已安裝 SELinux，並檢查強制模式。</span><span class="sxs-lookup"><span data-stu-id="f7792-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="f7792-140">如果是的話，請嘗試將其設為「許可」 (首選) 或已停用的模式。</span><span class="sxs-lookup"><span data-stu-id="f7792-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="f7792-141">您可以在檔案中將參數設 `SELINUX` 為「容許」或「停用」 `/etc/selinux/config` ，接著再重新開機。</span><span class="sxs-lookup"><span data-stu-id="f7792-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="f7792-142">如需詳細資訊，請參閱 selinux 的手冊頁面。</span><span class="sxs-lookup"><span data-stu-id="f7792-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="f7792-143">現在請嘗試使用步驟2重新開機 mdatp 服務。</span><span class="sxs-lookup"><span data-stu-id="f7792-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="f7792-144">請立即還原設定變更，但出於安全性原因，請試一試並重啟。</span><span class="sxs-lookup"><span data-stu-id="f7792-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="f7792-145">如果 `/opt` 目錄是符號連結，請建立 bind 裝載 `/opt/microsoft` 。</span><span class="sxs-lookup"><span data-stu-id="f7792-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="f7792-146">確定守護程式具有可執行檔許可權。</span><span class="sxs-lookup"><span data-stu-id="f7792-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="f7792-147">如果此守護程式沒有可執行檔許可權，請使用下列方式進行：</span><span class="sxs-lookup"><span data-stu-id="f7792-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="f7792-148">並重試執行步驟2。</span><span class="sxs-lookup"><span data-stu-id="f7792-148">and retry running step 2.</span></span>

7. <span data-ttu-id="f7792-149">確定包含 wdavdaemon 的檔案系統未裝載為 "noexec"。</span><span class="sxs-lookup"><span data-stu-id="f7792-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="f7792-150">如果 mdatp 服務正在執行，但 EICAR.TXT 文字檔偵測無法運作</span><span class="sxs-lookup"><span data-stu-id="f7792-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="f7792-151">使用下列專案檢查檔案系統類型：</span><span class="sxs-lookup"><span data-stu-id="f7792-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="f7792-152">目前支援的內部存取使用中的檔案[系統如下所列。](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="f7792-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="f7792-153">不會掃描這些檔案系統以外的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="f7792-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="f7792-154">命令列工具 "mdatp" 無法運作</span><span class="sxs-lookup"><span data-stu-id="f7792-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="f7792-155">如果執行命令列工具 `mdatp` 時發生錯誤 `command not found` ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f7792-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="f7792-156">然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="f7792-156">and try again.</span></span>

    <span data-ttu-id="f7792-157">如果上述步驟都沒有説明，請收集診斷記錄：</span><span class="sxs-lookup"><span data-stu-id="f7792-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="f7792-158">包含記錄檔的 zip 檔案路徑會顯示為輸出。</span><span class="sxs-lookup"><span data-stu-id="f7792-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="f7792-159">使用這些記錄與我們的客戶支援部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="f7792-159">Reach out to our customer support with these logs.</span></span>
