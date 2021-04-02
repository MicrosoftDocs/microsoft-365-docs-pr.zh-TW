---
title: 在 Microsoft Defender ATP 中回應 web 威脅
description: 回應與惡意網站和有害網站相關的提醒。 瞭解網頁威脅防護如何透過網頁瀏覽器和 Windows 通知通知使用者
keywords: web 保護，網頁威脅防護，網頁流覽，警示，回應，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器，通知，使用者，Windows 通知，封鎖頁面
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b0e6bb0d71c14bf7742f8d6508fbb95b76b10a34
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498361"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="93aba-105">回應 Web 威脅</span><span class="sxs-lookup"><span data-stu-id="93aba-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93aba-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="93aba-106">**Applies to:**</span></span>
- [<span data-ttu-id="93aba-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93aba-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93aba-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93aba-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="93aba-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="93aba-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93aba-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="93aba-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="93aba-111">Microsoft Defender for Endpoint 中的 Web 保護功能可讓您有效地調查與您自訂指示器清單中的惡意網站和網站相關的提醒。</span><span class="sxs-lookup"><span data-stu-id="93aba-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="93aba-112">查看網頁威脅警示</span><span class="sxs-lookup"><span data-stu-id="93aba-112">View web threat alerts</span></span>
<span data-ttu-id="93aba-113">Microsoft Defender for Endpoint 會針對惡意或可疑的 web 活動產生下列 [警示](manage-alerts.md) ：</span><span class="sxs-lookup"><span data-stu-id="93aba-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="93aba-114">**網路保護封鎖的可疑** 連線-當使用者嘗試存取您自訂指示器清單中的惡意網站或網站 *時，會* 產生此警示，以 *封鎖* 模式中的網路保護</span><span class="sxs-lookup"><span data-stu-id="93aba-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="93aba-115">**網路保護偵測到可疑** 的連線-當以「 *僅供審核* 」模式中的網路保護方式偵測到自訂指示器清單中的訪問惡意網站或網站時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="93aba-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="93aba-116">每個警示都提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="93aba-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="93aba-117">嘗試存取封鎖的網站的裝置</span><span class="sxs-lookup"><span data-stu-id="93aba-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="93aba-118">用來傳送 web 要求的應用程式或程式</span><span class="sxs-lookup"><span data-stu-id="93aba-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="93aba-119">自訂指示器清單中的惡意 URL 或 URL</span><span class="sxs-lookup"><span data-stu-id="93aba-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="93aba-120">回應回應程式的建議動作</span><span class="sxs-lookup"><span data-stu-id="93aba-120">Recommended actions for responders</span></span>

![與 web 威脅防護相關的提醒影像](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="93aba-122">為了降低警示數量，Microsoft Defender for Endpoint 會將相同裝置上相同網域的 web 威脅偵測，合併到單一警示。</span><span class="sxs-lookup"><span data-stu-id="93aba-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="93aba-123">只產生一個提醒並計算在 [web 保護報告](web-protection-monitoring.md)中。</span><span class="sxs-lookup"><span data-stu-id="93aba-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="93aba-124">檢查網站詳細資料</span><span class="sxs-lookup"><span data-stu-id="93aba-124">Inspect website details</span></span>
<span data-ttu-id="93aba-125">您可以在警示中，選取網站的 URL 或網域，以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="93aba-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="93aba-126">這會開啟有關該特定 URL 或網域的頁面，其中包含各種資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="93aba-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="93aba-127">嘗試存取網站的裝置</span><span class="sxs-lookup"><span data-stu-id="93aba-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="93aba-128">與網站相關的事件及警示</span><span class="sxs-lookup"><span data-stu-id="93aba-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="93aba-129">在組織中的事件看到網站的頻率</span><span class="sxs-lookup"><span data-stu-id="93aba-129">How frequent the website was seen in events in your organization</span></span>

    ![[網域] 或 [URL 實體詳細資料] 頁面的圖像](images/wtp-website-details.png)

[<span data-ttu-id="93aba-131">深入瞭解 URL 或網域實體頁面</span><span class="sxs-lookup"><span data-stu-id="93aba-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="93aba-132">檢查裝置</span><span class="sxs-lookup"><span data-stu-id="93aba-132">Inspect the device</span></span>
<span data-ttu-id="93aba-133">您也可以檢查嘗試存取封鎖 URL 的裝置。</span><span class="sxs-lookup"><span data-stu-id="93aba-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="93aba-134">在 [警示] 頁面上選取裝置的名稱，會開啟一個頁面，其中包含裝置的完整資訊。</span><span class="sxs-lookup"><span data-stu-id="93aba-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="93aba-135">深入瞭解裝置實體頁面</span><span class="sxs-lookup"><span data-stu-id="93aba-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="93aba-136">使用者的網頁瀏覽器和 Windows 通知</span><span class="sxs-lookup"><span data-stu-id="93aba-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="93aba-137">使用 Microsoft Defender for Endpoint 中的 web 保護，您的使用者將無法使用 Microsoft Edge 或其他瀏覽器來訪問惡意或有害的網站。</span><span class="sxs-lookup"><span data-stu-id="93aba-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="93aba-138">因為封鎖是透過 [網路保護](network-protection.md)來執行，所以他們會看到來自網頁瀏覽器的一般錯誤。</span><span class="sxs-lookup"><span data-stu-id="93aba-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="93aba-139">他們也會看到來自 Windows 的通知。</span><span class="sxs-lookup"><span data-stu-id="93aba-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="93aba-140">![Microsoft Edge 的影像，顯示403錯誤和 ](images/wtp-browser-blocking-page.png)
 *microsoft edge 封鎖* 的 Windows 通知網頁威脅</span><span class="sxs-lookup"><span data-stu-id="93aba-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="93aba-141">![Chrome 網頁瀏覽器的影像，顯示安全連線警告，以及 ](images/wtp-chrome-browser-blocking-page.png)
 *在 Chrome 上封鎖* 的 Windows 通知網頁威脅</span><span class="sxs-lookup"><span data-stu-id="93aba-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="93aba-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="93aba-142">Related topics</span></span>
- [<span data-ttu-id="93aba-143">Web 保護概觀</span><span class="sxs-lookup"><span data-stu-id="93aba-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="93aba-144">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="93aba-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="93aba-145">網頁威脅防護</span><span class="sxs-lookup"><span data-stu-id="93aba-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="93aba-146">監視 Web 安全性</span><span class="sxs-lookup"><span data-stu-id="93aba-146">Monitor web security</span></span>](web-protection-monitoring.md)
