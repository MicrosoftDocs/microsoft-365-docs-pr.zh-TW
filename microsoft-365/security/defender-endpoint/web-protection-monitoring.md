---
title: 監視 Microsoft Defender for Endpoint 中的 web 流覽安全性
description: 在 Microsoft Defender for Endpoint 中使用 web 保護以監視網頁流覽安全性
keywords: web 保護，網頁威脅防護，網頁流覽，監控，報表，卡片，網域清單，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器
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
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687420"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="b2302-104">監視網頁流覽安全性</span><span class="sxs-lookup"><span data-stu-id="b2302-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2302-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b2302-105">**Applies to:**</span></span>
- [<span data-ttu-id="b2302-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2302-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b2302-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2302-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b2302-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b2302-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2302-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b2302-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="b2302-110">web 保護可讓您透過 Microsoft Defender 資訊安全中心中 **報告 > web 保護**，來監視組織的 web 流覽安全性。</span><span class="sxs-lookup"><span data-stu-id="b2302-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b2302-111">報告包含的卡片可提供 web 威脅偵測統計資料。</span><span class="sxs-lookup"><span data-stu-id="b2302-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="b2302-112">**隨時間變化的 web 威脅防護** 偵測-此趨勢卡會在過去30天、過去3個月、過去6個月的 (，顯示在選取的時段內，由類型偵測到的 web 威脅數目) </span><span class="sxs-lookup"><span data-stu-id="b2302-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![顯示網路威脅防護偵測一段時間的卡片影像](images/wtp-blocks-over-time.png)

- <span data-ttu-id="b2302-114">**Web 威脅防護摘要** -此卡片會顯示過去30天內的 web 威脅偵測總數，顯示不同網路威脅類型的散佈。</span><span class="sxs-lookup"><span data-stu-id="b2302-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="b2302-115">選取切片時，會開啟包含惡意網站或有害網站的網域清單。</span><span class="sxs-lookup"><span data-stu-id="b2302-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![顯示網路威脅保護摘要的卡片影像](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="b2302-117">在 [卡片] 或 [網域] 清單中的區塊反映之前，可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="b2302-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="b2302-118">Web 威脅類型</span><span class="sxs-lookup"><span data-stu-id="b2302-118">Types of web threats</span></span>

<span data-ttu-id="b2302-119">Web 保護會將惡意及有害的網站分類，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2302-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="b2302-120">**網路釣魚** -包含冒牌網頁表單和其他網路釣魚詐騙機制的網站，其設計目的是欺騙使用者 divulging 認證及其他敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="b2302-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="b2302-121">**惡意** 網站，主控惡意程式碼和利用程式碼</span><span class="sxs-lookup"><span data-stu-id="b2302-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="b2302-122">**自訂指示器** -已新增至您 [自訂指示器清單](manage-indicators.md) 進行封鎖的 URLs 或網域的網站</span><span class="sxs-lookup"><span data-stu-id="b2302-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="b2302-123">查看網域清單</span><span class="sxs-lookup"><span data-stu-id="b2302-123">View the domain list</span></span>

<span data-ttu-id="b2302-124">在 [ **網頁威脅防護] 摘要** 卡中，選取特定的 web 威脅類別，以開啟 [ **網域** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b2302-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="b2302-125">此頁面會顯示 [威脅] 類別底下的網域清單。</span><span class="sxs-lookup"><span data-stu-id="b2302-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="b2302-126">此頁面提供每個網域的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b2302-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="b2302-127">**存取計數** -網域中 URLs 的要求數目</span><span class="sxs-lookup"><span data-stu-id="b2302-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="b2302-128">**區塊** -封鎖要求的次數</span><span class="sxs-lookup"><span data-stu-id="b2302-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="b2302-129">**存取趨勢** -在存取嘗試數目上的變更</span><span class="sxs-lookup"><span data-stu-id="b2302-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="b2302-130">**威脅類別** -web 威脅類型</span><span class="sxs-lookup"><span data-stu-id="b2302-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="b2302-131">**裝置** -具有存取嘗試的裝置數目</span><span class="sxs-lookup"><span data-stu-id="b2302-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="b2302-132">選取一個網域，以查看已嘗試存取該網域中 URLs 的裝置清單及 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="b2302-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2302-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2302-133">Related topics</span></span>

- [<span data-ttu-id="b2302-134">Web 保護概觀</span><span class="sxs-lookup"><span data-stu-id="b2302-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="b2302-135">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="b2302-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="b2302-136">網頁威脅防護</span><span class="sxs-lookup"><span data-stu-id="b2302-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="b2302-137">回應 Web 威脅</span><span class="sxs-lookup"><span data-stu-id="b2302-137">Respond to web threats</span></span>](web-protection-response.md)
