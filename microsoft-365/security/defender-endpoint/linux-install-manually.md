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
ms.openlocfilehash: c50efb11ee7f884be6788b90c14e7fc639d9b8ca
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281002"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>手動在 Linux 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

本文說明如何手動在 Linux 上部署 Microsoft Defender for Endpoint。 成功的部署需要完成下列所有工作：

- [手動在 Linux 上部署 Microsoft Defender for Endpoint](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [必要條件和系統需求](#prerequisites-and-system-requirements)
  - [設定 Linux 軟體存放庫](#configure-the-linux-software-repository)
    - [RHEL 和變種 (CentOS 和 Oracle Linux) ](#rhel-and-variants-centos-and-oracle-linux)
    - [SLES 和變種](#sles-and-variants)
    - [Ubuntu 和 Debian 系統](#ubuntu-and-debian-systems)
  - [應用程式安裝](#application-installation)
  - [下載上架套件](#download-the-onboarding-package)
  - [用戶端設定](#client-configuration)
  - [Installer 腳本](#installer-script)
  - [記錄安裝問題](#log-installation-issues)
  - [作業系統升級](#operating-system-upgrades)
  - [卸載](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a>必要條件和系統需求

開始之前，請參閱 [Linux 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-linux.md) ，以取得目前軟體版本的必要條件和系統需求的描述。

## <a name="configure-the-linux-software-repository"></a>設定 Linux 軟體存放庫

您可以從下列其中一個 (通道部署在 Linux 上的 Defender： *[通道]*) ：「內部人員 *-快*」、「 *預覽人員-緩慢*」或「 *生產*」。每個通道都會對應至 Linux 軟體存放庫。 以下提供設定裝置使用其中一種存放庫的指示。

通道選擇會決定提供給裝置的更新類型及頻率。 在內部版本中的裝置 *快* 用的第一種方法是接收更新及新功能，然後是上一個程式 *-速度慢* ，最後透過 *生產*。

為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用 *預覽人員-快* 或內部的 *速度緩慢*。

> [!WARNING]
> 初次安裝後切換通道需要重新安裝產品。 若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。

### <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL 和變種 (CentOS 和 Oracle Linux) 

- `yum-utils`若尚未安裝，請安裝：

    ```bash
    sudo yum install yum-utils
    ```

- 請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config/` 。 例如，RHEL 7.9 比對7.4 更近。

    在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：

    > [!NOTE]
    > 如果是 Oracle Linux，請將 *[distro]* 取代為 "rhel"。

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    例如，如果您正在執行 CentOS 7，且想要從 *生產* 通道在 Linux 上部署 Defender for Endpoint：

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    或者，如果您想要在選取的裝置上探索新的功能，您可能想要將 MDE Linux 部署至 *內部使用者-fast* 通道：

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- 安裝 Microsoft GPG 公用機碼：

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- 下載並使所有的中繼資料都可供目前啟用的 yum 存放庫使用：

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a>SLES 和變種

- 請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config/` 。

    在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    例如，如果您正在執行 SLES 12，且想要從 *生產* 通道部署 MDE for Linux：

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- 安裝 Microsoft GPG 公用機碼：

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Ubuntu 和 Debian 系統

- `curl`若尚未安裝，請安裝：

    ```bash
    sudo apt-get install curl
    ```

- `libplist-utils`若尚未安裝，請安裝：

    ```bash
    sudo apt-get install libplist-utils
    ```

- 請記下您的發行和版本，並找出最接近的專案 (依主要、次要) `https://packages.microsoft.com/config` 。

    在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    例如，如果您正在執行 Ubuntu 18.04，並希望從 *生產* 通道部署 MDE for Linux：

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- 安裝存放庫設定：

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    例如，如果您選擇 [ *生產* ] 通道：

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- `gpg`若尚未安裝套件，請安裝：

    ```bash
    sudo apt-get install gpg
    ```

  若 `gpg` 無法使用，請安裝 `gnupg` 。

- 安裝 Microsoft GPG 公用機碼：

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- 若尚未出現 HTTPs 驅動程式，請加以安裝：

    ```bash
    sudo apt-get install apt-transport-https
    ```

- 更新存放庫中繼資料：

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>應用程式安裝

- RHEL 和 variant (CentOS 和 Oracle Linux) ：

    ```bash
    sudo yum install mdatp
    ```

    如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。 下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。 當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。 根據發佈和伺服器的版本而定，存放庫別名可能與下列範例中的不同。

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

- SLES 和變種：

    ```bash
    sudo zypper install mdatp
    ```

    如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。 下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。 當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。

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

- Ubuntu 和 Debian 系統：

    ```bash
    sudo apt-get install mdatp
    ```

    如果您已在裝置上設定多個 Microsoft 存放庫，您可以專門瞭解要從其中安裝套件的存放庫。 下列範例會顯示如何在 `production` `insiders-fast` 此裝置上設定了存放庫通道時，從通道安裝套件。 當您在裝置上使用多個 Microsoft 產品時，可能會發生這種情況。

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

## <a name="download-the-onboarding-package"></a>下載上架套件

從 Microsoft Defender 資訊安全中心下載上架套件：

1. 在 Microsoft Defender 資訊安全中心中，移至 **設定 > 裝置管理 > 上架**。
2. 在第一個下拉式功能表中，選取 [ **Linux 伺服器** ] 做為作業系統。 在第二個下拉式功能表中，選取 [ **本機腳本 (，最多10個裝置)** 做為部署方法。
3. 選取 [ **下載上架] 套件**。 將檔案儲存為 WindowsDefenderATPOnboardingPackage.zip。

    ![Microsoft Defender 資訊安全中心螢幕擷取畫面](images/atp-portal-onboarding-linux.png)

4. 在命令提示字元中，確認您有檔案。
    解壓縮封存的內容：

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


## <a name="client-configuration"></a>用戶端設定

1. 將 MicrosoftDefenderATPOnboardingLinuxServer.py 複製到目標裝置。

    最初，用戶端裝置不會與組織產生關聯。 請注意， *orgId* 屬性是空白的：

    ```bash
    mdatp health --field org_id
    ```

2. 執行 MicrosoftDefenderATPOnboardingLinuxServer.py，請注意，為了執行此命令，您必須 `python` 安裝在裝置上：

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. 請確認裝置現在與您的組織有關聯，並報告有效的組織識別碼：

    ```bash
    mdatp health --field org_id
    ```

4. 完成安裝後幾分鐘之後，您可以執行下列命令來查看狀態。 傳回值 `1` 表示產品如預期般運作：

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > 產品第一次啟動時，會下載最新的反惡意程式碼定義。 視您的網際網路連線而定，這可能需要幾分鐘的時間。 在這段時間內，上述命令會傳回值 `false` 。 您可以使用下列命令來檢查定義更新的狀態：
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > 請注意，在完成初始安裝之後，您可能還需要設定 proxy。 請參閱 [在 Linux 上設定用於靜態 proxy 探索的 Defender For Endpoint：安裝後設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)。

5. 執行偵測測試，確認裝置已正確架及報表服務。 在新的架裝置上執行下列步驟：

    - 確定即時保護已啟用 (由執行下列命令的結果所表示 `1`) ：

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - 開啟終端視窗。 複製並執行下列命令：

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - 檔案應該已被 Linux 上的 Defender for Endpoint 隔離。 使用下列命令列出所有偵測到的威脅：

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a>Installer 腳本

或者，您也可以使用我們[公開 GitHub 存放庫](https://github.com/microsoft/mdatp-xplat/)中提供的自動[安裝程式 bash 腳本](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh)。
腳本會識別發行及版本，並設定裝置以拉入最新的套件並加以安裝。
您也可以使用所提供的腳本進行上架。

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

若要 [深入閱讀](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)，請參閱。

## <a name="log-installation-issues"></a>記錄安裝問題

如需如何找到錯誤發生時所建立的自動產生記錄，請參閱 [記錄安裝的問題](linux-resources.md#log-installation-issues) 。

## <a name="operating-system-upgrades"></a>作業系統升級

將作業系統升級為新的主要版本時，您必須先在 Linux 上卸載適用于 Endpoint 的 Defender，安裝升級，最後在裝置上重新設定 Linux 上的 Endpoint 的 Defender。

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>如何從 Insiders-Fast 遷移至實際執行通道

1. 為 Linux 卸載「預覽人員-Fast 通道」版本的 MDE。

    ``
    sudo yum remove mdatp
    ``

1. 停用 Linux Insiders-Fast 的 MDE  ``
    sudo yum repolist
    ``

    > [!NOTE]
    > 輸出應該會顯示「套件-microsoft-com-快-生產」。

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. 使用 "實際執行通道" 重新部署的 .MDE 為 Linux。


## <a name="uninstallation"></a>卸載

如需如何從用戶端裝置移除 Linux 上的 Endpoint Endpoint 的詳細資訊，請參閱 [Uninstall](linux-resources.md#uninstall) 。

## <a name="see-also"></a>另請參閱
- [調查代理程式健康情況問題](health-status.md)
