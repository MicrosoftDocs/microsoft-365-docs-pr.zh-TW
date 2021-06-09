---
title: Microsoft 365網路連接位置服務
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365網路連接位置服務
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470445"
---
# <a name="microsoft-365-network-connectivity-location-services"></a><span data-ttu-id="d9f1e-103">Microsoft 365網路連接位置服務</span><span class="sxs-lookup"><span data-stu-id="d9f1e-103">Microsoft 365 Network Connectivity Location Services</span></span>

<span data-ttu-id="d9f1e-104">Microsoft 365 系統管理中心現在會顯示 **網路洞察力和效能建議**，也就是從您的 Microsoft 365 租使用者收集到的即時效能度量。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics that are collected from your Microsoft 365 tenant.</span></span> <span data-ttu-id="d9f1e-105">只有租使用者中的系統管理使用者可以查看這些計量。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-105">These metrics can be viewed only by administrative users in your tenant.</span></span> <span data-ttu-id="d9f1e-106">組織網路連線是透過網際網路的網路出局位置，為每個辦公室的位置所設計。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-106">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="d9f1e-107">Microsoft 365 用戶端連線會使用該路由，然後透過網際網路到 Microsoft 服務的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-107">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="d9f1e-108">識別辦公室位置是可顯示這些網路洞察力的關鍵。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-108">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="d9f1e-109">網路度量的位置</span><span class="sxs-lookup"><span data-stu-id="d9f1e-109">Location in network measurements</span></span>

<span data-ttu-id="d9f1e-110">組織的管理員可以選擇是否要在此功能使用的網路度量中包含的位置。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-110">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="d9f1e-111">這可讓您在每個辦公室所在的城市自動探索。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-111">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="d9f1e-112">位置資訊不是精確的，而且會加以混淆以300m 及依城市分類。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-112">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="d9f1e-113">在 Windows 裝置上捕獲位置時，裝置會在工具託盤中顯示 **位置使用中** 圖示。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-113">At the time when location is captured on a Windows device, the device will show a **Location In-Use** icon in the tool tray.</span></span> <span data-ttu-id="d9f1e-114">管理員可能會想要通知使用者此圖示的外觀。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-114">Administrators may want to notify users of the appearance of this icon.</span></span> <span data-ttu-id="d9f1e-115">透過這項處理，該位置會被視為組織辦公室位置，而非人員或裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-115">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="d9f1e-116">網路洞察力可在這些已探索的 office 位置城市顯示。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-116">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="d9f1e-117">如果您想要在建議中獲得更高的精確度，您可以輸入特定的 office 位置位址。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-117">If you want higher accuracy in the recommendations, you can enter specific office location addresses.</span></span> <span data-ttu-id="d9f1e-118">而是會將網路洞察力匯總到這些位置。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-118">The network insights will be aggregated to those locations instead.</span></span> <span data-ttu-id="d9f1e-119">Office 位置的匯總不能大於300米。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-119">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d9f1e-120">Microsoft 365 系統管理中心的位置</span><span class="sxs-lookup"><span data-stu-id="d9f1e-120">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="d9f1e-121">在 Microsoft 365 系統管理中心中，Bing map 控制項是用來顯示組織辦公室位置的位置。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-121">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are.</span></span> <span data-ttu-id="d9f1e-122">控制項也會顯示所選辦公室位置的網路周邊拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-122">The controls also show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="d9f1e-123">當系統管理員新增 office 位置的特定位址詳細資料時，Bing 地圖服務也會用來建議位址，讓資料輸入更容易。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-123">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="d9f1e-124">使用條款</span><span class="sxs-lookup"><span data-stu-id="d9f1e-124">Terms of Use</span></span>

<span data-ttu-id="d9f1e-125">透過 Bing 地圖服務提供的任何內容（包括 geocodes），只能在提供內容的產品內使用。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-125">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="d9f1e-126">客戶使用由 Bing 地圖服務所提供的 Microsoft 365 系統管理中心位置服務功能，受 _Bing 地圖服務 End-User 使用條款_ 的制約， <https://go.microsoft.com/?linkid=9710837> 並由 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?LinkID=248686)使用。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-126">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End-User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=248686).</span></span>

<span data-ttu-id="d9f1e-127">**TomTom** 也支援此功能（透過 Bing 地圖服務提供）。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-127">This feature, provided through Bing Maps, is also supported by **TomTom**.</span></span> <span data-ttu-id="d9f1e-128">您可以在 TomTom 的產品和服務上找到相關資訊 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-128">More information about TomTom's products and services may be found at [https://www.tomtom.com/legal](https://www.tomtom.com/legal).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9f1e-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9f1e-129">Related topics</span></span>

[<span data-ttu-id="d9f1e-130">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="d9f1e-130">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="d9f1e-131">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="d9f1e-131">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="d9f1e-132"> (預覽 Microsoft 365 網路評估) </span><span class="sxs-lookup"><span data-stu-id="d9f1e-132">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="d9f1e-133">Microsoft 365 系統管理中心的 Microsoft 365 連線測試 (預覽) </span><span class="sxs-lookup"><span data-stu-id="d9f1e-133">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
