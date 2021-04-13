---
title: 為 Linux 部署 Microsoft Defender ATP 更新
ms.reviewer: ''
description: 說明如何在企業環境中部署 Microsoft Defender ATP for Linux 的更新。
keywords: microsoft，defender，atp，linux，更新，部署
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
ms.openlocfilehash: 2e4ea4942446317aef90288da9fb181935503fa9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687463"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上部署 Microsoft Defender for Endpoint 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。

> [!WARNING]
> 每個用於 Linux 的 Endpoint 的 Defender 版本都有到期日，此後將不再繼續保護您的裝置。 您必須更新此日期之前的產品。 若要檢查到期日，請執行下列命令：
> ```bash
> mdatp health --field product_expiration
> ```

若要手動更新適用于 Linux 之端點的 Defender，請執行下列其中一個命令：

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL 和變種 (CentOS 和 Oracle Linux) 

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES 和變種

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu 和 Debian 系統

```bash
sudo apt-get install --only-upgrade mdatp
```
