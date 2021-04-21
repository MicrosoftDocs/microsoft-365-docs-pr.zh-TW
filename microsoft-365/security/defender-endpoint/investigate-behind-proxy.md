---
title: 調查正向 Proxy 背後發生的連線事件。
description: 瞭解如何在 Microsoft Defender for Endpoint 中透過網路保護使用高級 HTTP 層級監視，以呈現真實目標，而非 proxy。
keywords: proxy，網路保護，轉寄 proxy，網路事件，審核，封鎖，功能變數名稱，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47be07759a72a080a3687ed3bb50cef9d0a959b7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904043"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="667b9-104">調查正向 Proxy 背後發生的連線事件。</span><span class="sxs-lookup"><span data-stu-id="667b9-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="667b9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="667b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="667b9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="667b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="667b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="667b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="667b9-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="667b9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="667b9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="667b9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="667b9-110">Defender for Endpoint 支援來自不同網路堆疊層級的網路連線監視。</span><span class="sxs-lookup"><span data-stu-id="667b9-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="667b9-111">一個挑戰性的案例是，網路使用轉寄 proxy 做為網際網路的閘道。</span><span class="sxs-lookup"><span data-stu-id="667b9-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="667b9-112">Proxy 的運作方式就如同目標端點。</span><span class="sxs-lookup"><span data-stu-id="667b9-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="667b9-113">在這些情況下，「簡易網路連線監視器」會審核與正確但是具有較低調查值之 proxy 的連線。</span><span class="sxs-lookup"><span data-stu-id="667b9-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="667b9-114">Endpoint for Endpoint 支援透過網路保護進行的高級 HTTP 層級監視。</span><span class="sxs-lookup"><span data-stu-id="667b9-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="667b9-115">開啟時，會呈現出公開實際目標功能變數名稱的新事件種類。</span><span class="sxs-lookup"><span data-stu-id="667b9-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="667b9-116">使用網路防護來監視防火牆後的網路連線</span><span class="sxs-lookup"><span data-stu-id="667b9-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="667b9-117">因為來自網路保護的其他網路事件，所以可以監視正向 proxy 背後的網路連線。</span><span class="sxs-lookup"><span data-stu-id="667b9-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="667b9-118">若要在裝置時程表上查看它們，請在 (中至少以「審計模式」) 中開啟 [網路保護]。</span><span class="sxs-lookup"><span data-stu-id="667b9-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="667b9-119">您可以使用下列模式來控制網路保護：</span><span class="sxs-lookup"><span data-stu-id="667b9-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="667b9-120">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="667b9-120">**Block**</span></span> <br> <span data-ttu-id="667b9-121">使用者或應用程式將被封鎖，無法連線到危險網域。</span><span class="sxs-lookup"><span data-stu-id="667b9-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="667b9-122">您可以在 Microsoft Defender Security Center 中看到這項活動。</span><span class="sxs-lookup"><span data-stu-id="667b9-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="667b9-123">**稽核**</span><span class="sxs-lookup"><span data-stu-id="667b9-123">**Audit**</span></span> <br> <span data-ttu-id="667b9-124">不會封鎖使用者或應用程式連線到危險網域。</span><span class="sxs-lookup"><span data-stu-id="667b9-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="667b9-125">不過，您仍會在 Microsoft Defender 安全中心看到這項活動。</span><span class="sxs-lookup"><span data-stu-id="667b9-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="667b9-126">如果關閉網路保護，將不會封鎖使用者或應用程式連線到危險網域。</span><span class="sxs-lookup"><span data-stu-id="667b9-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="667b9-127">在 Microsoft Defender Security Center 中，您不會看到任何網路活動。</span><span class="sxs-lookup"><span data-stu-id="667b9-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="667b9-128">如果您未設定它，預設會關閉網路封鎖功能。</span><span class="sxs-lookup"><span data-stu-id="667b9-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="667b9-129">如需詳細資訊，請參閱 [Enable network protection](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="667b9-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="667b9-130">調查影響</span><span class="sxs-lookup"><span data-stu-id="667b9-130">Investigation impact</span></span>
<span data-ttu-id="667b9-131">當網路保護開啟時，您會在裝置的時程表上看到 IP 位址會保留 proxy，而實際的目標位址會顯示。</span><span class="sxs-lookup"><span data-stu-id="667b9-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![裝置時程表上之網路事件的影像](images/atp-proxy-investigation.png)

<span data-ttu-id="667b9-133">網路保護層所觸發的其他事件現在可用於呈現真實的功能變數名稱，甚至是在 proxy 之後。</span><span class="sxs-lookup"><span data-stu-id="667b9-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="667b9-134">事件資訊：</span><span class="sxs-lookup"><span data-stu-id="667b9-134">Event's information:</span></span>

![單一網路事件的影像](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="667b9-136">使用高級搜尋來尋找連接事件</span><span class="sxs-lookup"><span data-stu-id="667b9-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="667b9-137">您也可以透過高級搜尋來尋找所有新的線上活動。</span><span class="sxs-lookup"><span data-stu-id="667b9-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="667b9-138">因為這些事件是線上活動，所以您可以在 [動作類型] 底下的 [DeviceNetworkEvents] 表格底下找到這些事件 `ConnecionSuccess` 。</span><span class="sxs-lookup"><span data-stu-id="667b9-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="667b9-139">使用此簡單查詢會顯示所有相關的事件：</span><span class="sxs-lookup"><span data-stu-id="667b9-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![高級搜尋查詢的影像](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="667b9-141">您也可以篩選出與 proxy 本身連線相關的事件。</span><span class="sxs-lookup"><span data-stu-id="667b9-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="667b9-142">使用下列查詢篩選出 proxy 的連線：</span><span class="sxs-lookup"><span data-stu-id="667b9-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="667b9-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="667b9-143">Related topics</span></span>
- [<span data-ttu-id="667b9-144">使用 GP-原則 CSP 應用網路保護</span><span class="sxs-lookup"><span data-stu-id="667b9-144">Applying network protection with GP - policy CSP</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
