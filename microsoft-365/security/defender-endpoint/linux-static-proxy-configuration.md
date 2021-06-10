---
title: Linux 靜態 proxy 探索上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 說明如何針對靜態 proxy 探索，在 Linux 上設定 Microsoft Defender for Endpoint。
keywords: microsoft、defender、Microsoft Defender for Endpoint、linux、安裝、proxy
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
ms.openlocfilehash: c5dc14c71c344bf508cda8d39f892d740781ac87
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933118"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="8f545-104">針對靜態 proxy 探索，設定 Linux 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f545-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8f545-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8f545-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f545-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f545-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f545-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f545-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f545-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8f545-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f545-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8f545-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8f545-110">Microsoft Defender for Endpoint 可以使用環境變數探索 proxy 伺服器 ```HTTPS_PROXY``` 。</span><span class="sxs-lookup"><span data-stu-id="8f545-110">Microsoft Defender for Endpoint can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="8f545-111">此設定 **必須在安裝** 時和產品安裝之後設定。</span><span class="sxs-lookup"><span data-stu-id="8f545-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="8f545-112">安裝時間設定</span><span class="sxs-lookup"><span data-stu-id="8f545-112">Installation time configuration</span></span>

<span data-ttu-id="8f545-113">在安裝期間， ```HTTPS_PROXY``` 環境變數必須傳遞給套件管理員。</span><span class="sxs-lookup"><span data-stu-id="8f545-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="8f545-114">套件管理員可以採用下列任何一種方式讀取此變數：</span><span class="sxs-lookup"><span data-stu-id="8f545-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="8f545-115">```HTTPS_PROXY```變數是以 ```/etc/environment``` 下列行定義的：</span><span class="sxs-lookup"><span data-stu-id="8f545-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="8f545-116">`HTTPS_PROXY`變數是以 package 管理員全域設定定義。</span><span class="sxs-lookup"><span data-stu-id="8f545-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="8f545-117">例如，在 Ubuntu 18.04 中，您可以將下列行新增到 `/etc/apt/apt.conf.d/proxy.conf` ：</span><span class="sxs-lookup"><span data-stu-id="8f545-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="8f545-118">請注意，上述兩種方法可能會定義 proxy，以用於系統上的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="8f545-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="8f545-119">請謹慎使用此方法，或僅限這種方式是一般全域設定。</span><span class="sxs-lookup"><span data-stu-id="8f545-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="8f545-120">`HTTPS_PROXY`變數預先安裝或卸載命令。</span><span class="sxs-lookup"><span data-stu-id="8f545-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="8f545-121">例如，使用 APT 套件管理員時，會在安裝 Microsoft Defender for Endpoint 時，按下列方式前置變數：</span><span class="sxs-lookup"><span data-stu-id="8f545-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="8f545-122">請勿在環境變數定義和 apt 之間新增 sudo，否則將不會傳播此變數。</span><span class="sxs-lookup"><span data-stu-id="8f545-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="8f545-123">`HTTPS_PROXY`環境變數可能會在卸載期間定義。</span><span class="sxs-lookup"><span data-stu-id="8f545-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="8f545-124">請注意，如果需要 proxy 但未設定，則安裝和卸載不一定會失敗。</span><span class="sxs-lookup"><span data-stu-id="8f545-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="8f545-125">不過，遙測將不會送出，而且作業可能需要很長的時間，因為網路超時。</span><span class="sxs-lookup"><span data-stu-id="8f545-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="8f545-126">安裝後的設定</span><span class="sxs-lookup"><span data-stu-id="8f545-126">Post installation configuration</span></span>
  
<span data-ttu-id="8f545-127">安裝後， `HTTPS_PROXY` 環境變數必須在 Endpoint service 檔案中定義。</span><span class="sxs-lookup"><span data-stu-id="8f545-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="8f545-128">若要這麼做，請 `/lib/systemd/system/mdatp.service` 在文字編輯器中開啟以根使用者的模式。</span><span class="sxs-lookup"><span data-stu-id="8f545-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="8f545-129">然後，您可以採用下列其中一種方式將變數傳播至服務：</span><span class="sxs-lookup"><span data-stu-id="8f545-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="8f545-130">取消注釋該行 `#Environment="HTTPS_PROXY=http://address:port"` ，並指定您的靜態 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="8f545-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="8f545-131">新增一行 `EnvironmentFile=/path/to/env/file` 。</span><span class="sxs-lookup"><span data-stu-id="8f545-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="8f545-132">此路徑可以指向 `/etc/environment` 或自訂檔案，其中一個需要新增下列行：</span><span class="sxs-lookup"><span data-stu-id="8f545-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="8f545-133">修改檔案之後 `mdatp.service` ，儲存並關閉該檔案。</span><span class="sxs-lookup"><span data-stu-id="8f545-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="8f545-134">重新開機服務，以便可以套用變更。</span><span class="sxs-lookup"><span data-stu-id="8f545-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="8f545-135">在 Ubuntu 中，這包括兩個命令：</span><span class="sxs-lookup"><span data-stu-id="8f545-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
