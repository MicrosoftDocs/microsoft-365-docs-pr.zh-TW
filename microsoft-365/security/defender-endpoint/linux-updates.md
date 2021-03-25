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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187718"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="b0be6-104">為 Linux 部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="b0be6-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b0be6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b0be6-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0be6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0be6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0be6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0be6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0be6-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b0be6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0be6-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b0be6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b0be6-110">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="b0be6-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="b0be6-111">每個用於 Linux 的 Endpoint 的 Defender 版本都有到期日，此後將不再繼續保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="b0be6-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="b0be6-112">您必須更新此日期之前的產品。</span><span class="sxs-lookup"><span data-stu-id="b0be6-112">You must update the product prior to this date.</span></span> <span data-ttu-id="b0be6-113">若要檢查到期日，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b0be6-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="b0be6-114">若要手動更新適用于 Linux 之端點的 Defender，請執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="b0be6-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="b0be6-115">RHEL 和變種 (CentOS 和 Oracle Linux) </span><span class="sxs-lookup"><span data-stu-id="b0be6-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="b0be6-116">SLES 和變種</span><span class="sxs-lookup"><span data-stu-id="b0be6-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="b0be6-117">Ubuntu 和 Debian 系統</span><span class="sxs-lookup"><span data-stu-id="b0be6-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
