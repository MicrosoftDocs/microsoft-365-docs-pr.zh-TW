---
title: Microsoft Defender for Endpoint 裝置的時間表事件旗標
description: 使用 Microsoft Defender for Endpoint device 時序表事件旗標
keywords: 用於端點裝置時程表的 Defender，事件旗標
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165150"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="2ee18-104">Microsoft Defender for Endpoint 裝置的時間表事件旗標</span><span class="sxs-lookup"><span data-stu-id="2ee18-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ee18-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2ee18-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ee18-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ee18-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ee18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ee18-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2ee18-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2ee18-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ee18-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2ee18-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2ee18-110">Defender for Endpoint 裝置時程表中的事件旗標可協助您在調查可能的攻擊時，篩選和組織特定事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="2ee18-111">[Defender for Endpoint 裝置時程表] 提供在裝置上觀察到的事件及相關警示的按時間排序的視圖。</span><span class="sxs-lookup"><span data-stu-id="2ee18-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="2ee18-112">此事件清單可讓您在裝置上看到任何事件、檔案及 IP 位址的完整可視性。</span><span class="sxs-lookup"><span data-stu-id="2ee18-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="2ee18-113">清單有時候會很長。</span><span class="sxs-lookup"><span data-stu-id="2ee18-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="2ee18-114">裝置時程表事件旗標可協助您追蹤可能相關的事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="2ee18-115">在您完成裝置時程表之後，您可以排序、篩選和匯出您已標記的特定事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="2ee18-116">流覽裝置時程表時，您可以搜尋並篩選特定的事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="2ee18-117">您可以使用下列方式設定事件旗標：</span><span class="sxs-lookup"><span data-stu-id="2ee18-117">You can set event flags by:</span></span> 

- <span data-ttu-id="2ee18-118">高亮顯示最重要的事件</span><span class="sxs-lookup"><span data-stu-id="2ee18-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="2ee18-119">標示需要深入深入的事件</span><span class="sxs-lookup"><span data-stu-id="2ee18-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="2ee18-120">建立清晰的破壞時程表</span><span class="sxs-lookup"><span data-stu-id="2ee18-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="2ee18-121">旗標事件</span><span class="sxs-lookup"><span data-stu-id="2ee18-121">Flag an event</span></span>
1. <span data-ttu-id="2ee18-122">尋找您要標示的事件</span><span class="sxs-lookup"><span data-stu-id="2ee18-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="2ee18-123">按一下 [旗標] 欄中的旗標圖示。</span><span class="sxs-lookup"><span data-stu-id="2ee18-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="2ee18-124">![裝置時程表旗標的影像](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="2ee18-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="2ee18-125">查看已標記的事件</span><span class="sxs-lookup"><span data-stu-id="2ee18-125">View flagged events</span></span>  
1. <span data-ttu-id="2ee18-126">在 [時程表 **篩選** ] 區段中，啟用已 **標記的事件**。</span><span class="sxs-lookup"><span data-stu-id="2ee18-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="2ee18-127">按一下 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="2ee18-127">Click **Apply**.</span></span> <span data-ttu-id="2ee18-128">只會顯示已標示的事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="2ee18-129">您可以按一下時間列來套用其他篩選器。</span><span class="sxs-lookup"><span data-stu-id="2ee18-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="2ee18-130">這只會顯示已標示事件之前的事件。</span><span class="sxs-lookup"><span data-stu-id="2ee18-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="2ee18-131">![具有篩選器之裝置時程表旗標的影像](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="2ee18-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
