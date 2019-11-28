---
title: 可靠深入解析
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634030"
---
# <a name="reliability-insights"></a><span data-ttu-id="115a1-103">可靠深入解析</span><span class="sxs-lookup"><span data-stu-id="115a1-103">Reliability insights</span></span>

<span data-ttu-id="115a1-104">此檢視為您提供您受管理的裝置健全狀況摘要。</span><span class="sxs-lookup"><span data-stu-id="115a1-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="115a1-105">若要檢視可靠性資料，請選取 [**可靠性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="115a1-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格](images/insights_reliability.png)

<span data-ttu-id="115a1-107">**跨裝置的可靠性**] 區段中會提供快速的健全狀況摘要。 您過去 14 天的部署所報告的裝置會被認為是 「 良好 」 並觀察到自上次報告失敗後平均時間百分比。</span><span class="sxs-lookup"><span data-stu-id="115a1-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="115a1-108">**經過一段時間的可靠性**圖形右邊報告發生嚴重錯誤的裝置數目和觀察到的重大錯誤的總數，經過一段時間。</span><span class="sxs-lookup"><span data-stu-id="115a1-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="115a1-109">[**熱門問題**] 區段中詳細說明特定偵測到的問題會影響，至少有 5%的受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="115a1-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="115a1-110">報告的詳細資料包括：</span><span class="sxs-lookup"><span data-stu-id="115a1-110">Reported details include:</span></span>

- <span data-ttu-id="115a1-111">此類型的問題</span><span class="sxs-lookup"><span data-stu-id="115a1-111">The type of issue</span></span>
    - <span data-ttu-id="115a1-112">應用程式損毀，應用程式會停止運作或意外停止</span><span class="sxs-lookup"><span data-stu-id="115a1-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="115a1-113">應用程式停止回應，其中的應用程式停止回應輸入</span><span class="sxs-lookup"><span data-stu-id="115a1-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="115a1-114">嚴重錯誤，就會發生當發生此問題： 無法復原從 Windows。</span><span class="sxs-lookup"><span data-stu-id="115a1-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="115a1-115">受影響的同一個問題的裝置數目</span><span class="sxs-lookup"><span data-stu-id="115a1-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="115a1-116">數字代表的受管理裝置的百分比</span><span class="sxs-lookup"><span data-stu-id="115a1-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="115a1-117">特定問題數總計</span><span class="sxs-lookup"><span data-stu-id="115a1-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="115a1-118">問題的來源看起來軟體元件</span><span class="sxs-lookup"><span data-stu-id="115a1-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="115a1-119">偵測到問題的類別：</span><span class="sxs-lookup"><span data-stu-id="115a1-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="115a1-120">瀏覽器 (Edge、 Chrome IE)</span><span class="sxs-lookup"><span data-stu-id="115a1-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="115a1-121">未知 （非 Microsoft 元件）</span><span class="sxs-lookup"><span data-stu-id="115a1-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="115a1-122">驅動程式 （音訊、 圖形或其他驅動程式）</span><span class="sxs-lookup"><span data-stu-id="115a1-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="115a1-123">產能 （寬限時間，G Suite、 Microsoft Office 和其附加元件或擴充功能、 Teams）</span><span class="sxs-lookup"><span data-stu-id="115a1-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="115a1-124">媒體 （影像、 等候音樂或視訊的應用程式</span><span class="sxs-lookup"><span data-stu-id="115a1-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="115a1-125">安全性 （Windows 安全性元件）</span><span class="sxs-lookup"><span data-stu-id="115a1-125">Security (Windows security components)</span></span>
- <span data-ttu-id="115a1-126">為 Microsoft 受管理的桌上型電腦作業的目前狀態，進行調查和 remediates 問題</span><span class="sxs-lookup"><span data-stu-id="115a1-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

