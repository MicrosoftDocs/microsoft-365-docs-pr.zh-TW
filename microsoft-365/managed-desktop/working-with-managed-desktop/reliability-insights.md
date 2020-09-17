---
title: 可靠深入解析
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950339"
---
# <a name="reliability-insights"></a><span data-ttu-id="ba41f-103">可靠深入解析</span><span class="sxs-lookup"><span data-stu-id="ba41f-103">Reliability insights</span></span>

<span data-ttu-id="ba41f-104">此視圖提供受管理裝置的健康情況摘要。</span><span class="sxs-lookup"><span data-stu-id="ba41f-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="ba41f-105">若要查看可靠性資料，請選取 [ **可靠性** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ba41f-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格：左上方各裝置的可靠性、右上方的可靠性，右上方的 [最大問題] 表格。](../../media/insights_reliability.png)

<span data-ttu-id="ba41f-108">[ **各裝置的可靠性** ] 區段透過報告視為「狀況良好」的裝置百分比，以及自上次報告失敗後所觀測的平均時間，提供您部署在過去14天內的快速狀況摘要。</span><span class="sxs-lookup"><span data-stu-id="ba41f-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="ba41f-109">右側的 **可靠性隨時間** 圖表會報告發生嚴重錯誤的裝置數量，以及觀測的嚴重錯誤總數。</span><span class="sxs-lookup"><span data-stu-id="ba41f-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="ba41f-110">**最上層的問題**一節將詳細說明會影響至少5% 受管理裝置之特定偵測到的問題。</span><span class="sxs-lookup"><span data-stu-id="ba41f-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="ba41f-111">報告的詳細資料包括：</span><span class="sxs-lookup"><span data-stu-id="ba41f-111">Reported details include:</span></span>

- <span data-ttu-id="ba41f-112">問題類型</span><span class="sxs-lookup"><span data-stu-id="ba41f-112">The type of issue</span></span>
    - <span data-ttu-id="ba41f-113">應用程式崩潰，應用程式停止運作或意外停止</span><span class="sxs-lookup"><span data-stu-id="ba41f-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="ba41f-114">應用程式懸掛，應用程式停止回應輸入</span><span class="sxs-lookup"><span data-stu-id="ba41f-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="ba41f-115">發生嚴重錯誤，當 Windows 發生問題而無法復原時，便會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="ba41f-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="ba41f-116">受相同問題影響的裝置數目</span><span class="sxs-lookup"><span data-stu-id="ba41f-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="ba41f-117">代表數目的受管理裝置百分比</span><span class="sxs-lookup"><span data-stu-id="ba41f-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="ba41f-118">特定問題發生的總次數</span><span class="sxs-lookup"><span data-stu-id="ba41f-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="ba41f-119">似乎是問題來源的軟體元件</span><span class="sxs-lookup"><span data-stu-id="ba41f-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="ba41f-120">偵測到之問題的類別：</span><span class="sxs-lookup"><span data-stu-id="ba41f-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="ba41f-121">瀏覽器 (Edge、Chrome、IE) </span><span class="sxs-lookup"><span data-stu-id="ba41f-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="ba41f-122">未知的 (非 Microsoft 元件) </span><span class="sxs-lookup"><span data-stu-id="ba41f-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="ba41f-123">驅動程式 (音訊、圖形或其他驅動程式) </span><span class="sxs-lookup"><span data-stu-id="ba41f-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="ba41f-124">生產力 (寬限時間、G-套件、Microsoft Office 及其附加元件或分機，小組) </span><span class="sxs-lookup"><span data-stu-id="ba41f-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="ba41f-125">媒體 (影像、音樂或影片應用程式</span><span class="sxs-lookup"><span data-stu-id="ba41f-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="ba41f-126">安全性 (Windows 安全性元件) </span><span class="sxs-lookup"><span data-stu-id="ba41f-126">Security (Windows security components)</span></span>
- <span data-ttu-id="ba41f-127">目前的狀態為 Microsoft 受管理的桌面作業調查並 remediates 問題</span><span class="sxs-lookup"><span data-stu-id="ba41f-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

