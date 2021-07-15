---
title: 手動在 Linux 上部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 說明如何從命令列手動在 Linux 上部署 Microsoft Defender for Endpoint。
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3579e9dab975d8776a53d400121d98fe119fe6cc
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438069"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="64093-104">手動在 Linux 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64093-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="64093-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="64093-105">**Applies to:**</span></span>
- [<span data-ttu-id="64093-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="64093-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64093-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64093-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64093-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="64093-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64093-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="64093-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="64093-110">本文說明如何手動在 Linux 上部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="64093-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="64093-111">成功的部署需要完成下列所有工作：</span><span class="sxs-lookup"><span data-stu-id="64093-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="64093-112">手動在 Linux 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64093-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="64093-113">必要條件和系統需求</span><span class="sxs-lookup"><span data-stu-id="64093-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="64093-114">設定 Linux 軟體存放庫</span><span class="sxs-lookup"><span data-stu-id="64093-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="64093-115">RHEL 和變種 (CentOS 和 Oracle Linux) </span><span class="sxs-lookup"><span data-stu-id="64093-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="64093-116">SLES 和變種</span><span class="sxs-lookup"><span data-stu-id="64093-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="64093-117">Ubuntu 和 Debian 系統</span><span class="sxs-lookup"><span data-stu-id="64093-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="64093-118">應用程式安裝</span><span class="sxs-lookup"><span data-stu-id="64093-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="64093-119">下載上架套件</span><span class="sxs-lookup"><span data-stu-id="64093-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="64093-120">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="64093-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="64093-121">Installer 腳本</span><span class="sxs-lookup"><span data-stu-id="64093-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="64093-122">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="64093-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="64093-123">作業系統升級</span><span class="sxs-lookup"><span data-stu-id="64093-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="64093-124">卸載</span><span class="sxs-lookup"><span data-stu-id="64093-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="64093-125">必要條件和系統需求</span><span class="sxs-lookup"><span data-stu-id="64093-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="64093-126">開始之前，請參閱 [Linux 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-linux.md) ，以取得目前軟體版本的必要條件和系統需求的描述。</span><span class="sxs-lookup"><span data-stu-id="64093-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="64093-127">設定 Linux 軟體存放庫</span><span class="sxs-lookup"><span data-stu-id="64093-127">Configure the Linux software repository</span></span>

<span data-ttu-id="64093-128">您可以從下列其中一個 (通道部署在 Linux 上的 Defender： *[通道]*) ：「內部人員 *-快*」、「 *預覽人員-緩慢*」或「 *生產*」。每個通道都會對應至 Linux 軟體存放庫。</span><span class="sxs-lookup"><span data-stu-id="64093-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="64093-129">以下提供設定裝置使用其中一種存放庫的指示。</span><span class="sxs-lookup"><span data-stu-id="64093-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="64093-130">通道選擇會決定提供給裝置的更新類型及頻率。</span><span class="sxs-lookup"><span data-stu-id="64093-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="64093-131">在內部版本中的裝置 *快* 用的第一種方法是接收更新及新功能，然後是上一個程式 *-速度慢* ，最後透過 *生產*。</span><span class="sxs-lookup"><span data-stu-id="64093-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="64093-132">為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用 *預覽人員-快* 或內部的 *速度緩慢*。</span><span class="sxs-lookup"><span data-stu-id="64093-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="64093-133">初次安裝後切換通道需要重新安裝產品。</span><span class="sxs-lookup"><span data-stu-id="64093-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="64093-134">若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。</span><span class="sxs-lookup"><span data-stu-id="64093-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="64093-135">RHEL 和變種 (CentOS 和 Oracle Linux) </span><span class="sxs-lookup"><span data-stu-id="64093-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="64093-136">`yum-utils`若尚未安裝，請安裝：</span><span class="sxs-lookup"><span data-stu-id="64093-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="64093-137">請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="64093-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="64093-138">例如，RHEL 7.9 比對7.4 更近。</span><span class="sxs-lookup"><span data-stu-id="64093-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="64093-139">在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：</span><span class="sxs-lookup"><span data-stu-id="64093-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="64093-140">如果是 Oracle Linux，請將 *[distro]* 取代為 "rhel"。</span><span class="sxs-lookup"><span data-stu-id="64093-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="64093-141">例如，如果您正在執行 CentOS 7，且想要從 *生產* 通道在 Linux 上部署 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="64093-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="64093-142">或者，如果您想要在選取的裝置上探索新功能，您可能想要在 Linux 上將 Microsoft Defender for Endpoint 部署為 *內部版-快速* 通道：</span><span class="sxs-lookup"><span data-stu-id="64093-142">Or if you wish to explore new features on selected devices, you might want to deploy Microsoft Defender for Endpoint on Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="64093-143">安裝 Microsoft GPG 公用機碼：</span><span class="sxs-lookup"><span data-stu-id="64093-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="64093-144">下載並使所有的中繼資料都可供目前啟用的 yum 存放庫使用：</span><span class="sxs-lookup"><span data-stu-id="64093-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="64093-145">SLES 和變種</span><span class="sxs-lookup"><span data-stu-id="64093-145">SLES and variants</span></span>

- <span data-ttu-id="64093-146">請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="64093-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="64093-147">在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：</span><span class="sxs-lookup"><span data-stu-id="64093-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="64093-148">例如，如果您正在執行 SLES 12，且想要從 *生產* 通道在 Linux 上部署 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="64093-148">For example, if you are running SLES 12 and wish to deploy Microsoft Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="64093-149">安裝 Microsoft GPG 公用機碼：</span><span class="sxs-lookup"><span data-stu-id="64093-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="64093-150">Ubuntu 和 Debian 系統</span><span class="sxs-lookup"><span data-stu-id="64093-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="64093-151">`curl`若尚未安裝，請安裝：</span><span class="sxs-lookup"><span data-stu-id="64093-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="64093-152">`libplist-utils`若尚未安裝，請安裝：</span><span class="sxs-lookup"><span data-stu-id="64093-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="64093-153">請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config` 。</span><span class="sxs-lookup"><span data-stu-id="64093-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="64093-154">在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：</span><span class="sxs-lookup"><span data-stu-id="64093-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="64093-155">例如，如果您正在執行 Ubuntu 18.04，並希望從 *生產* 通道部署 MDE for Linux：</span><span class="sxs-lookup"><span data-stu-id="64093-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="64093-156">安裝存放庫設定：</span><span class="sxs-lookup"><span data-stu-id="64093-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="64093-157">例如，如果您選擇 [ *生產* ] 通道：</span><span class="sxs-lookup"><span data-stu-id="64093-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="64093-158">`gpg`若尚未安裝套件，請安裝：</span><span class="sxs-lookup"><span data-stu-id="64093-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="64093-159">若 `gpg` 無法使用，請安裝 `gnupg` 。</span><span class="sxs-lookup"><span data-stu-id="64093-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="64093-160">安裝 Microsoft GPG 公用機碼：</span><span class="sxs-lookup"><span data-stu-id="64093-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="64093-161">若尚未出現 HTTPs 驅動程式，請加以安裝：</span><span class="sxs-lookup"><span data-stu-id="64093-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="64093-162">更新存放庫中繼資料：</span><span class="sxs-lookup"><span data-stu-id="64093-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="64093-163">應用程式安裝</span><span class="sxs-lookup"><span data-stu-id="64093-163">Application installation</span></span>

- <span data-ttu-id="64093-164">RHEL 和 variant (CentOS 和 Oracle Linux) ：</span><span class="sxs-lookup"><span data-stu-id="64093-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="64093-165">如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。</span><span class="sxs-lookup"><span data-stu-id="64093-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="64093-166">下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。</span><span class="sxs-lookup"><span data-stu-id="64093-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="64093-167">當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="64093-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="64093-168">根據發佈和伺服器的版本而定，存放庫別名可能與下列範例中的不同。</span><span class="sxs-lookup"><span data-stu-id="64093-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="64093-169">SLES 和變種：</span><span class="sxs-lookup"><span data-stu-id="64093-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="64093-170">如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。</span><span class="sxs-lookup"><span data-stu-id="64093-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="64093-171">下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。</span><span class="sxs-lookup"><span data-stu-id="64093-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="64093-172">當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="64093-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="64093-173">Ubuntu 和 Debian 系統：</span><span class="sxs-lookup"><span data-stu-id="64093-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="64093-174">如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。</span><span class="sxs-lookup"><span data-stu-id="64093-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="64093-175">下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。</span><span class="sxs-lookup"><span data-stu-id="64093-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="64093-176">當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="64093-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="64093-177">下載上架套件</span><span class="sxs-lookup"><span data-stu-id="64093-177">Download the onboarding package</span></span>

<span data-ttu-id="64093-178">從 Microsoft Defender 資訊安全中心下載上架套件：</span><span class="sxs-lookup"><span data-stu-id="64093-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="64093-179">在 Microsoft Defender 資訊安全中心中，移至 **設定 > 裝置管理 > 上架**。</span><span class="sxs-lookup"><span data-stu-id="64093-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="64093-180">在第一個下拉式功能表中，選取 [ **Linux 伺服器** ] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="64093-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="64093-181">在第二個下拉式功能表中，選取 [ **本機腳本 (，最多10個裝置)** 做為部署方法。</span><span class="sxs-lookup"><span data-stu-id="64093-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="64093-182">選取 [ **下載上架] 套件**。</span><span class="sxs-lookup"><span data-stu-id="64093-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="64093-183">將檔案儲存為 WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="64093-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 資訊安全中心螢幕擷取畫面](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="64093-185">在命令提示字元中，確認您有檔案。</span><span class="sxs-lookup"><span data-stu-id="64093-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="64093-186">解壓縮封存的內容：</span><span class="sxs-lookup"><span data-stu-id="64093-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="64093-187">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="64093-187">Client configuration</span></span>

1. <span data-ttu-id="64093-188">將 MicrosoftDefenderATPOnboardingLinuxServer.py 複製到目標裝置。</span><span class="sxs-lookup"><span data-stu-id="64093-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="64093-189">最初，用戶端裝置不會與組織產生關聯。</span><span class="sxs-lookup"><span data-stu-id="64093-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="64093-190">請注意， *orgId* 屬性是空白的：</span><span class="sxs-lookup"><span data-stu-id="64093-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="64093-191">執行 MicrosoftDefenderATPOnboardingLinuxServer.py。</span><span class="sxs-lookup"><span data-stu-id="64093-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py.</span></span> 
   
    >[!NOTE]
    ><span data-ttu-id="64093-192">若要執行此命令，您必須已 `python` 安裝在裝置上。</span><span class="sxs-lookup"><span data-stu-id="64093-192">To run this command, you must have `python` installed on the device.</span></span> <span data-ttu-id="64093-193">如果您正在執行 RHEL ∞或 Ubuntu 20.04 或更新版本，則您必須使用 Python 3，而不是 Python。</span><span class="sxs-lookup"><span data-stu-id="64093-193">If you're running RHEL 8.x or Ubuntu 20.04 or higher, then you will need to use Python 3 instead of Python.</span></span>



    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="64093-194">請確認裝置現在與您的組織有關聯，並報告有效的組織識別碼：</span><span class="sxs-lookup"><span data-stu-id="64093-194">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="64093-195">完成安裝後幾分鐘之後，您可以執行下列命令來查看狀態。</span><span class="sxs-lookup"><span data-stu-id="64093-195">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="64093-196">傳回值 `1` 表示產品如預期般運作：</span><span class="sxs-lookup"><span data-stu-id="64093-196">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="64093-197">產品第一次啟動時，會下載最新的反惡意程式碼定義。</span><span class="sxs-lookup"><span data-stu-id="64093-197">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="64093-198">視您的網際網路連線而定，這可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="64093-198">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="64093-199">在這段時間內，上述命令會傳回值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="64093-199">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="64093-200">您可以使用下列命令來檢查定義更新的狀態：</span><span class="sxs-lookup"><span data-stu-id="64093-200">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="64093-201">請注意，在完成初始安裝之後，您可能還需要設定 proxy。</span><span class="sxs-lookup"><span data-stu-id="64093-201">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="64093-202">請參閱 [在 Linux 上設定用於靜態 proxy 探索的 Defender For Endpoint：安裝後設定](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)。</span><span class="sxs-lookup"><span data-stu-id="64093-202">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="64093-203">執行偵測測試，確認裝置已正確架及報表服務。</span><span class="sxs-lookup"><span data-stu-id="64093-203">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="64093-204">在新的架裝置上執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="64093-204">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="64093-205">確定即時保護已啟用 (由執行下列命令的結果所表示 `1`) ：</span><span class="sxs-lookup"><span data-stu-id="64093-205">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="64093-206">開啟終端視窗。</span><span class="sxs-lookup"><span data-stu-id="64093-206">Open a Terminal window.</span></span> <span data-ttu-id="64093-207">複製並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="64093-207">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="64093-208">檔案應該已被 Linux 上的 Defender for Endpoint 隔離。</span><span class="sxs-lookup"><span data-stu-id="64093-208">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="64093-209">使用下列命令列出所有偵測到的威脅：</span><span class="sxs-lookup"><span data-stu-id="64093-209">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="64093-210">體驗具有模擬攻擊的 Linux 端點偵測和回應 (EDR) 功能</span><span class="sxs-lookup"><span data-stu-id="64093-210">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="64093-211">若要測試 linux EDR 的功能，請遵循下列步驟，在 linux 伺服器上模擬偵測，並調查案例。</span><span class="sxs-lookup"><span data-stu-id="64093-211">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="64093-212">確認架 Linux 伺服器出現在 Microsoft Defender 資訊安全中心中。</span><span class="sxs-lookup"><span data-stu-id="64093-212">Verify that the onboarded Linux server appears in Microsoft Defender Security Center.</span></span> <span data-ttu-id="64093-213">如果這是電腦的第一個上架，可能需要長達20分鐘，直到出現為止。</span><span class="sxs-lookup"><span data-stu-id="64093-213">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="64093-214">下載 [腳本](https://aka.ms/LinuxDIY) 檔案並將其解壓縮至架 Linux 伺服器，並執行下列命令： `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="64093-214">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="64093-215">幾分鐘後，就會在 Microsoft Defender 資訊安全中心中引發偵測。</span><span class="sxs-lookup"><span data-stu-id="64093-215">After a few minutes, a detection should be raised in Microsoft Defender Security Center.</span></span>

4.  <span data-ttu-id="64093-216">查看警示詳細資料、電腦時程表，並執行您的一般調查步驟。</span><span class="sxs-lookup"><span data-stu-id="64093-216">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="64093-217">Installer 腳本</span><span class="sxs-lookup"><span data-stu-id="64093-217">Installer script</span></span>

<span data-ttu-id="64093-218">或者，您也可以使用我們[公開 GitHub 存放庫](https://github.com/microsoft/mdatp-xplat/)中提供的自動[安裝程式 bash 腳本](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh)。</span><span class="sxs-lookup"><span data-stu-id="64093-218">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="64093-219">腳本會識別發行及版本，並設定裝置以拉入最新的套件並加以安裝。</span><span class="sxs-lookup"><span data-stu-id="64093-219">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="64093-220">您也可以使用所提供的腳本進行上架。</span><span class="sxs-lookup"><span data-stu-id="64093-220">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="64093-221">若要 [深入閱讀](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="64093-221">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="64093-222">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="64093-222">Log installation issues</span></span>

<span data-ttu-id="64093-223">如需如何找到錯誤發生時所建立的自動產生記錄，請參閱 [記錄安裝的問題](linux-resources.md#log-installation-issues) 。</span><span class="sxs-lookup"><span data-stu-id="64093-223">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="64093-224">作業系統升級</span><span class="sxs-lookup"><span data-stu-id="64093-224">Operating system upgrades</span></span>

<span data-ttu-id="64093-225">將作業系統升級為新的主要版本時，您必須先在 Linux 上卸載適用于 Endpoint 的 Defender，安裝升級，最後在裝置上重新設定 Linux 上的 Endpoint 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="64093-225">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="64093-226">如何從 Insiders-Fast 遷移至實際執行通道</span><span class="sxs-lookup"><span data-stu-id="64093-226">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="64093-227">在 Linux 上卸載「預覽人員-Fast 通道」版本的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="64093-227">Uninstall the “Insiders-Fast channel” version of Defender for Endpoint on Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="64093-228">停用 Linux Insiders-Fast 儲存機制的 Defender for Endpoint  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="64093-228">Disable the Defender for Endpoint on Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="64093-229">輸出應該會顯示「套件-microsoft-com-快-生產」。</span><span class="sxs-lookup"><span data-stu-id="64093-229">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="64093-230">使用 "實際執行通道" 重新部署的 .MDE 為 Linux。</span><span class="sxs-lookup"><span data-stu-id="64093-230">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="64093-231">卸載</span><span class="sxs-lookup"><span data-stu-id="64093-231">Uninstallation</span></span>

<span data-ttu-id="64093-232">如需如何從用戶端裝置移除 Linux 上的 Endpoint Endpoint 的詳細資訊，請參閱 [Uninstall](linux-resources.md#uninstall) 。</span><span class="sxs-lookup"><span data-stu-id="64093-232">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="64093-233">請參閱</span><span class="sxs-lookup"><span data-stu-id="64093-233">See also</span></span>
- [<span data-ttu-id="64093-234">調查代理程式健康狀況問題</span><span class="sxs-lookup"><span data-stu-id="64093-234">Investigate agent health issues</span></span>](health-status.md)
