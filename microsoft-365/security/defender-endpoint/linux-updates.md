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
ms.openlocfilehash: 9cb0c7375b538f502cf6165f13c68fd4b2fdcc64
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934750"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="428b7-104">在 Linux 上部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="428b7-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="428b7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="428b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="428b7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="428b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="428b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="428b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="428b7-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="428b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="428b7-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="428b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="428b7-110">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="428b7-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="428b7-111">在 Linux 上每個端點的版本都有到期日，此後將不再繼續保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="428b7-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="428b7-112">您必須更新此日期之前的產品。</span><span class="sxs-lookup"><span data-stu-id="428b7-112">You must update the product prior to this date.</span></span> <span data-ttu-id="428b7-113">若要檢查到期日，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="428b7-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="428b7-114">若要手動更新 Linux 上的 Defender for Endpoint，請執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="428b7-114">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="428b7-115">RHEL 和變種 (CentOS 和 Oracle Linux) </span><span class="sxs-lookup"><span data-stu-id="428b7-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="428b7-116">SLES 和變種</span><span class="sxs-lookup"><span data-stu-id="428b7-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="428b7-117">Ubuntu 和 Debian 系統</span><span class="sxs-lookup"><span data-stu-id="428b7-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
