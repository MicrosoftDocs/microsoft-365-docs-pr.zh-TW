---
title: 可靠深入解析
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085665"
---
# <a name="reliability-insights"></a><span data-ttu-id="a2468-103">可靠深入解析</span><span class="sxs-lookup"><span data-stu-id="a2468-103">Reliability insights</span></span>

<span data-ttu-id="a2468-104">此檢視為您提供您受管理的裝置健全狀況摘要。</span><span class="sxs-lookup"><span data-stu-id="a2468-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="a2468-105">若要檢視可靠性資料，請選取 [**可靠性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a2468-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格： 上方的 [跨裝置透過時間圖表中右上，upper left、 可靠性問題資料表跨底部。](../../media/insights_reliability.png)

<span data-ttu-id="a2468-108">**跨裝置的可靠性**] 區段中會提供快速的健全狀況摘要。 您過去 14 天的部署所報告的裝置會被認為是 「 良好 」 並觀察到自上次報告失敗後平均時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a2468-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="a2468-109">**經過一段時間的可靠性**圖形右邊報告發生嚴重錯誤的裝置數目和觀察到的重大錯誤的總數，經過一段時間。</span><span class="sxs-lookup"><span data-stu-id="a2468-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="a2468-110">[**熱門問題**] 區段中詳細說明特定偵測到的問題會影響，至少有 5%的受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="a2468-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="a2468-111">報告的詳細資料包括：</span><span class="sxs-lookup"><span data-stu-id="a2468-111">Reported details include:</span></span>

- <span data-ttu-id="a2468-112">此類型的問題</span><span class="sxs-lookup"><span data-stu-id="a2468-112">The type of issue</span></span>
    - <span data-ttu-id="a2468-113">應用程式損毀，應用程式會停止運作或意外停止</span><span class="sxs-lookup"><span data-stu-id="a2468-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="a2468-114">應用程式停止回應，其中的應用程式停止回應輸入</span><span class="sxs-lookup"><span data-stu-id="a2468-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="a2468-115">嚴重錯誤，就會發生當發生此問題： 無法復原從 Windows。</span><span class="sxs-lookup"><span data-stu-id="a2468-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="a2468-116">受影響的同一個問題的裝置數目</span><span class="sxs-lookup"><span data-stu-id="a2468-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="a2468-117">數字代表的受管理裝置的百分比</span><span class="sxs-lookup"><span data-stu-id="a2468-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="a2468-118">特定問題數總計</span><span class="sxs-lookup"><span data-stu-id="a2468-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="a2468-119">問題的來源看起來軟體元件</span><span class="sxs-lookup"><span data-stu-id="a2468-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="a2468-120">偵測到問題的類別：</span><span class="sxs-lookup"><span data-stu-id="a2468-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="a2468-121">瀏覽器 (Edge、 Chrome IE)</span><span class="sxs-lookup"><span data-stu-id="a2468-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="a2468-122">未知 （非 Microsoft 元件）</span><span class="sxs-lookup"><span data-stu-id="a2468-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="a2468-123">驅動程式 （音訊、 圖形或其他驅動程式）</span><span class="sxs-lookup"><span data-stu-id="a2468-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="a2468-124">產能 （寬限時間，G Suite、 Microsoft Office 和其附加元件或擴充功能、 Teams）</span><span class="sxs-lookup"><span data-stu-id="a2468-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="a2468-125">媒體 （影像、 等候音樂或視訊的應用程式</span><span class="sxs-lookup"><span data-stu-id="a2468-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="a2468-126">安全性 （Windows 安全性元件）</span><span class="sxs-lookup"><span data-stu-id="a2468-126">Security (Windows security components)</span></span>
- <span data-ttu-id="a2468-127">為 Microsoft 受管理的桌上型電腦作業的目前狀態，進行調查和 remediates 問題</span><span class="sxs-lookup"><span data-stu-id="a2468-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

