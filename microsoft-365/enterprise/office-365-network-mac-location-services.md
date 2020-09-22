---
title: 'Microsoft 365 Network Connectivity Location 服務 (預覽) '
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
description: 'Microsoft 365 Network Connectivity Location 服務 (預覽) '
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200778"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="b9ca6-103">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="b9ca6-104">Microsoft 365 系統管理中心現在會顯示 **網路洞察力和效能建議**，這些建議是從您的 Microsoft 365 租使用者收集到的即時效能度量，而且只能供您租使用者中的系統管理使用者查看。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="b9ca6-105">組織網路連線是透過網際網路的網路出局位置，為每個辦公室的位置所設計。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="b9ca6-106">Microsoft 365 用戶端連線會使用該路由，然後透過網際網路傳送至 Microsoft 服務的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="b9ca6-107">識別辦公室位置是可顯示這些網路洞察力的關鍵。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="b9ca6-108">網路度量的位置</span><span class="sxs-lookup"><span data-stu-id="b9ca6-108">Location in network measurements</span></span>

<span data-ttu-id="b9ca6-109">組織的管理員可以選擇是否要在此功能使用的網路度量中包含的位置。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="b9ca6-110">這可讓您在每個辦公室所在的城市自動探索。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="b9ca6-111">位置資訊不是精確的，而且會加以混淆以300m 及依城市分類。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="b9ca6-112">在 Windows 裝置上捕獲位置時，系統會顯示工具託盤中的 [ **位置內使用** ] 圖示，系統管理員可能會想要通知使用者這種情況。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="b9ca6-113">透過這項處理，該位置會被視為組織辦公室位置，而非人員或裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="b9ca6-114">網路洞察力可在這些已探索的 office 位置城市顯示。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="b9ca6-115">如果需要更精確的建議，系統管理員可以輸入特定的 office 位置位址，而網路洞察力也會匯總至這些位址。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="b9ca6-116">辦公室位置的合計不能超過300米。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b9ca6-117">Microsoft 365 系統管理中心的位置</span><span class="sxs-lookup"><span data-stu-id="b9ca6-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="b9ca6-118">在 Microsoft 365 系統管理中心中，Bing 地圖控制項是用來顯示組織辦公室位置所在的位置，以及顯示所選辦公室位置的網路周邊拓撲。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="b9ca6-119">當系統管理員新增 office 位置的特定位址詳細資料時，Bing 地圖也可以用來建議位址，讓資料輸入更容易。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="b9ca6-120">使用條款</span><span class="sxs-lookup"><span data-stu-id="b9ca6-120">Terms of Use</span></span>

<span data-ttu-id="b9ca6-121">透過 Bing 地圖提供的任何內容（包括 geocodes），只能在提供內容的產品內使用。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="b9ca6-122">客戶使用 Microsoft 365 Admin Center Location 服務功能（由 Bing 地圖供電）受 bing 地圖的制約，其 _使用於的 Bing 地圖使用者使用條款_ <https://go.microsoft.com/?linkid=9710837> 和 _Microsoft 隱私權聲明_ 可用於 <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="b9ca6-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="b9ca6-123">此功能（透過 Bing 地圖提供）也是由 **這裡的技術**支援。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="b9ca6-124">Bing 地圖如何利用這裡技術所提供的位置服務，受下列 _技術服務條款_ 的制約 <https://legal.here.com/en-gb/terms> 。</span><span class="sxs-lookup"><span data-stu-id="b9ca6-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9ca6-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="b9ca6-125">Related topics</span></span>

[<span data-ttu-id="b9ca6-126">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-126">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="b9ca6-127">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-127">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="b9ca6-128">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-128">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="b9ca6-129">Microsoft 365 connectivity test in M365 Admin Center (預覽) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-129">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
