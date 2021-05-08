---
title: 在 Linux 上部署 Microsoft Defender for Endpoint 的更新
ms.reviewer: ''
description: 說明如何在企業環境中為 Linux 上的端點部署 Microsoft Defender 的更新。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，update，deploy
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274721"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上部署 Microsoft Defender for Endpoint 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。

> [!WARNING]
> 在 Linux 上每個端點的版本都有到期日，此後將不再繼續保護您的裝置。 您必須更新此日期之前的產品。 若要檢查到期日，請執行下列命令：
> ```bash
> mdatp health --field product_expiration
> ```


一般可用的 Microsoft Defender for Endpoint 功能是相同的，不論用於部署的更新通道 (Beta (有問必答) 、預覽 (外部) 、目前 (的實際執行) ) 。


若要手動更新 Linux 上的 Defender for Endpoint，請執行下列其中一個命令：

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
