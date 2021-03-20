---
title: SharePoint Online 容量規劃和負載測試
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 本文說明如何在不允許傳統負載測試的情況下，在不執行傳統負載測試的情況下，部署至 SharePoint Online。
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905221"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="a92ac-103">SharePoint Online 容量規劃和負載測試</span><span class="sxs-lookup"><span data-stu-id="a92ac-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="a92ac-104">本文說明如何在未使用傳統負載測試的情況下，部署至 SharePoint Online，因為 SharePoint 線上上不允許進行負載測試。</span><span class="sxs-lookup"><span data-stu-id="a92ac-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="a92ac-105">SharePoint 線上是雲端服務，且服務的負載、健康情況和整體平衡是由 Microsoft 所管理。</span><span class="sxs-lookup"><span data-stu-id="a92ac-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="a92ac-106">確保啟動網站成功的最佳方法，就是遵循 [您的入口網站啟動向外設計](planportallaunchroll-out.md)中所述的基本原則、作法和建議。</span><span class="sxs-lookup"><span data-stu-id="a92ac-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="a92ac-107">SharePoint 線上如何執行容量規劃的概述</span><span class="sxs-lookup"><span data-stu-id="a92ac-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="a92ac-108">在內部部署環境中 SharePoint 線上的主要好處之一是雲端的彈性，以及針對分散式區域中的使用者進行優化。</span><span class="sxs-lookup"><span data-stu-id="a92ac-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="a92ac-109">我們將大規模的環境設定為每天為數百萬的使用者提供服務，因此我們必須透過平衡和展開伺服器陣列，有效地處理容量。</span><span class="sxs-lookup"><span data-stu-id="a92ac-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="a92ac-110">在任何一個伺服器陣列中的任何一個租使用者的成長都不可預測的情況下，累積的要求總數可在一段時間後預測。</span><span class="sxs-lookup"><span data-stu-id="a92ac-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="a92ac-111">透過找出 SharePoint 線上中的成長趨勢，我們可以規劃未來的擴充。</span><span class="sxs-lookup"><span data-stu-id="a92ac-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="a92ac-112">為了有效地使用容量並處理未預期的成長，在任何伺服器陣列中，我們都有可讓您追蹤和監視服務各專案的自動化。</span><span class="sxs-lookup"><span data-stu-id="a92ac-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="a92ac-113">使用多個計量，其中一個主要是 CPU 負載，它是用來向上擴充前端伺服器的信號。</span><span class="sxs-lookup"><span data-stu-id="a92ac-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="a92ac-114">此外，我們也建議使用 [分階段/wave 的方法](planportallaunchroll-out.md)，因為 SQL 環境會隨著時間的負載和成長而縮放，而且遵循階段和波形可讓該負載和成長正確地散佈。</span><span class="sxs-lookup"><span data-stu-id="a92ac-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="a92ac-115">容量不僅僅是在連續新增更多硬體，也適用于管理和控制該容量，以確保其可提供有效的負載要求。</span><span class="sxs-lookup"><span data-stu-id="a92ac-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="a92ac-116">我們建議客戶遵循建議的指導方針，以確保獲得最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="a92ac-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="a92ac-117">這也表示我們有節流模式和控制措施，以確保我們不允許在服務中執行「濫用」行為。</span><span class="sxs-lookup"><span data-stu-id="a92ac-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="a92ac-118">雖然並非所有「不良」行為是特意的，但我們卻必須確定會限制該行為的影響。</span><span class="sxs-lookup"><span data-stu-id="a92ac-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="a92ac-119">如需節流的進一步資訊和避免，請參閱 how [to to the to to to to](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="a92ac-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="a92ac-120">為何無法將測試 SharePoint 線上載入</span><span class="sxs-lookup"><span data-stu-id="a92ac-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="a92ac-121">使用內部部署環境時，負載測試是用來驗證規模的設想，並最終找到伺服器陣列的中中斷點;透過負載飽和。</span><span class="sxs-lookup"><span data-stu-id="a92ac-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="a92ac-122">隨著 SharePoint 線上，我們需要以不同的方式執行，因為比例相對於特定的試探法而相對流動和調整、節流和控制負載。</span><span class="sxs-lookup"><span data-stu-id="a92ac-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="a92ac-123">如此大規模的多租使用者環境，我們必須保護相同伺服器陣列中的所有承租人，因此我們會自動節流任何負載測試。</span><span class="sxs-lookup"><span data-stu-id="a92ac-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="a92ac-124">不過，如果您在嘗試載入測試時，除了受到限制以外，您將會收到 disappointing 及可能誤導的結果，因為您現在所測試的伺服器陣列可能會在測試時段或在測試之後的時段內，隨著規模和伺服器陣列的平衡動作不斷執行。</span><span class="sxs-lookup"><span data-stu-id="a92ac-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="a92ac-125">不是嘗試將測試 SharePoint 當做服務，而是著重于遵循建議的做法，並遵循 [建立、啟動及維護健康的入口網站](/sharepoint/portal-health) 指導方針。</span><span class="sxs-lookup"><span data-stu-id="a92ac-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health) guidance.</span></span>