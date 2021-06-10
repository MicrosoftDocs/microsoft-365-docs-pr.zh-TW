---
title: 使用 Puppet 在 Linux 上部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 說明如何使用 Puppet 在 Linux 上部署 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: d54732134e91b87b2639634c365556beda5312b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934570"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>使用 Puppet 在 Linux 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

本文說明如何使用 Puppet 在 Linux 上部署 Defender for Endpoint。 成功的部署需要完成下列所有工作：

- [下載上架套件](#download-the-onboarding-package)
- [建立 Puppet 資訊清單](#create-a-puppet-manifest)
- [部署](#deployment)
- [檢查上架狀態](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>必要條件和系統需求

 如需目前軟體版本之必要條件和系統需求的描述，請參閱 [Linux 的主要 Defender for The Endpoint on](microsoft-defender-endpoint-linux.md)。

此外，針對 Puppet 部署，您必須熟悉 Puppet 管理工作、Puppet 設定，以及瞭解如何部署套件。 Puppet 有許多方式可完成相同的工作。 這些指示假設支援的 Puppet 模組（如 *apt* 可協助部署套件）的可用性。 您的組織可能會使用不同的工作流程。 如需詳細資訊，請參閱 [Puppet 檔](https://puppet.com/docs) 。

## <a name="download-the-onboarding-package"></a>下載上架套件

從 Microsoft Defender 資訊安全中心下載上架套件：

1. 在 Microsoft Defender 資訊安全中心中，移至 **設定 > 裝置管理 > 上架**。
2. 在第一個下拉式功能表中，選取 [ **Linux 伺服器** ] 做為作業系統。 在第二個下拉式功能表中，選取 **您偏好的 Linux 設定管理工具** 做為部署方法。
3. 選取 [ **下載上架] 套件**。 將檔案儲存為 WindowsDefenderATPOnboardingPackage.zip。

    ![Microsoft Defender 資訊安全中心螢幕擷取畫面](images/atp-portal-onboarding-linux-2.png)

4. 在命令提示字元中，確認您有檔案。 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. 解壓縮封存的內容。
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>建立 Puppet 資訊清單

您必須建立 Puppet 資訊清單，以便在 Linux 上為端點部署 Defender，以 Puppet server 管理的裝置。 此範例會使用 puppetlabs 提供的 *apt* 和 *yumrepo* 模組，並假設您的 Puppet 伺服器上已安裝這些模組。

在 Puppet 安裝的 [模組] 資料夾下，建立 *install_mdatp/files* 及 *install_mdatp/manifests* 的資料夾。 此資料夾通常位於 Puppet 伺服器上的 */etc/puppetlabs/code/environments/production/modules* 中。 將上述 *install_mdatp/files* 資料夾上所建立的 mdatp_onboard.js。 建立 *init。 pp* 包含部署指示的檔案：

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>的內容 `install_mdatp/manifests/init.pp`

您可以從下列其中一個 (通道部署在 Linux 上的 Defender： *[通道]*) ：「內部人員 *-快*」、「 *預覽人員-緩慢*」或「 *生產*」。每個通道都會對應至 Linux 軟體存放庫。

通道選擇會決定提供給裝置的更新類型及頻率。 在內部版本中的裝置 *快* 用的第一種方法是接收更新及新功能，然後是上一個程式 *-速度慢* ，最後透過 *生產*。

為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用 *預覽人員-快* 或內部的 *速度緩慢*。

> [!WARNING]
> 初次安裝後切換通道需要重新安裝產品。 若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。

請記下您的發行及版本，並為其指定最接近的專案 `https://packages.microsoft.com/config/` 。

在下列命令中，將 *[distro]* 和 *[version]* 取代為您識別的資訊：

> [!NOTE]
> 在 RedHat、Oracle EL 和 CentOS 8 的情況下，以 ' rhel ' 取代 *[distro]* 。

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>部署

在您的 site 中包含上述資訊清單。 pp 檔：

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

已註冊的代理裝置會定期輪詢 Puppet 伺服器，並在偵測到新的設定設定檔和原則時立即加以安裝。

## <a name="monitor-puppet-deployment"></a>監視 Puppet 部署

在代理人裝置上，您也可以執行下列動作檢查上架狀態：

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- 已 **授權**：這會確認裝置是否與您的組織相關聯。

- **orgId**：這是您的 Defender for Endpoint 組織識別碼。

## <a name="check-onboarding-status"></a>檢查上架狀態

您可以透過建立腳本，檢查裝置是否已正確架。 例如，下列腳本會檢查已註冊的裝置是否有上架狀態：

```bash
mdatp health --field healthy
```

上述命令會在 `1` 產品架且如預期的運作時列印。

> [!IMPORTANT]
> 產品第一次啟動時，會下載最新的反惡意程式碼定義。 視您的網際網路連線而定，這可能需要幾分鐘的時間。 在這段時間內，上述命令會傳回值 `0` 。

如果產品不健康，可以透過) 檢查的退出程式碼 (`echo $?` 指出問題：

- 1如果尚未架裝置。
- 3如果無法建立與後臺連結的連線。

## <a name="log-installation-issues"></a>記錄安裝問題

 如需如何在發生錯誤時，尋找由安裝程式所建立之自動產生記錄的詳細資訊，請參閱 [記錄檔安裝的問題](linux-resources.md#log-installation-issues)。

## <a name="operating-system-upgrades"></a>作業系統升級

將作業系統升級為新的主要版本時，您必須先在 Linux 上卸載適用于 Endpoint 的 Defender，安裝升級，最後在裝置上重新設定 Linux 上的 Endpoint 的 Defender。

## <a name="uninstallation"></a>卸載

使用 *init* 中的下列內容建立模組 *remove_mdatp* 類似 *install_mdatp* 檔：

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
