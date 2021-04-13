---
title: 檢查 Microsoft Defender for Endpoint service health
description: 檢查 Microsoft Defender for Endpoint service health，查看服務是否發生問題，並檢查先前已解決的問題。
keywords: 儀表板、服務、問題、服務健康情況、目前狀態、狀態史、影響摘要、初始根本原因、解析度、解決時間、預期的解決時間
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687622"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="3afbf-104">檢查 Microsoft Defender for Endpoint service health</span><span class="sxs-lookup"><span data-stu-id="3afbf-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3afbf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3afbf-105">**Applies to:**</span></span>
- [<span data-ttu-id="3afbf-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3afbf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="3afbf-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3afbf-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3afbf-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3afbf-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="3afbf-109">**服務健康** 情況提供有關 Endpoint Service 之 Defender 的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="3afbf-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="3afbf-110">您可以驗證服務健康情況是否良好，或是否有目前的問題。</span><span class="sxs-lookup"><span data-stu-id="3afbf-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="3afbf-111">如果發生問題，您會看到資訊，例如偵測到問題的時間、初級的根本原因以及預期的解決時間。</span><span class="sxs-lookup"><span data-stu-id="3afbf-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="3afbf-112">您也會看到已解決之歷史問題的資訊，以及解決問題的日期和時間等詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3afbf-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="3afbf-113">當服務沒有問題時，您會看到 [狀況良好] 狀態。</span><span class="sxs-lookup"><span data-stu-id="3afbf-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="3afbf-114">您可以從 [ **安全性作業] 儀表板** 上按一下 [磚]，或從功能窗格中選取 [ **服務健康** 情況] 功能表，以查看服務健康情況的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3afbf-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="3afbf-115">[ **服務狀況** 詳細資料] 頁面包含下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="3afbf-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="3afbf-116">**目前狀態**</span><span class="sxs-lookup"><span data-stu-id="3afbf-116">**Current status**</span></span>
- <span data-ttu-id="3afbf-117">**狀態歷程記錄**</span><span class="sxs-lookup"><span data-stu-id="3afbf-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="3afbf-118">目前狀態</span><span class="sxs-lookup"><span data-stu-id="3afbf-118">Current status</span></span>
<span data-ttu-id="3afbf-119">[ **目前狀態** ] 索引標籤會顯示端點服務之 Defender 的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="3afbf-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="3afbf-120">當服務執行順利時，就會顯示 [狀況良好的服務健康情況]。</span><span class="sxs-lookup"><span data-stu-id="3afbf-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="3afbf-121">如果出現問題，將會顯示下列服務詳細資料，以協助您深入瞭解問題：</span><span class="sxs-lookup"><span data-stu-id="3afbf-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="3afbf-122">偵測到問題的日期和時間</span><span class="sxs-lookup"><span data-stu-id="3afbf-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="3afbf-123">問題的簡短描述</span><span class="sxs-lookup"><span data-stu-id="3afbf-123">A short description of the issue</span></span>
- <span data-ttu-id="3afbf-124">更新時間</span><span class="sxs-lookup"><span data-stu-id="3afbf-124">Update time</span></span>
- <span data-ttu-id="3afbf-125">影響摘要</span><span class="sxs-lookup"><span data-stu-id="3afbf-125">Summary of impact</span></span>
- <span data-ttu-id="3afbf-126">初步的根本原因</span><span class="sxs-lookup"><span data-stu-id="3afbf-126">Preliminary root cause</span></span>
- <span data-ttu-id="3afbf-127">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3afbf-127">Next steps</span></span>
- <span data-ttu-id="3afbf-128">預期的解決時間</span><span class="sxs-lookup"><span data-stu-id="3afbf-128">Expected resolution time</span></span>

<span data-ttu-id="3afbf-129">當問題解決時，在問題的進度上的更新會在頁面上反映出來。</span><span class="sxs-lookup"><span data-stu-id="3afbf-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="3afbf-130">您會看到更新的資訊，例如更新的估算解析度時間或後續步驟。</span><span class="sxs-lookup"><span data-stu-id="3afbf-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="3afbf-131">當問題解決時，它會記錄在 [ **狀態史** ] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="3afbf-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="3afbf-132">狀態歷程記錄</span><span class="sxs-lookup"><span data-stu-id="3afbf-132">Status history</span></span>
<span data-ttu-id="3afbf-133">[ **狀態記錄** ] 索引標籤會反映已出現及已解決的所有歷史問題。</span><span class="sxs-lookup"><span data-stu-id="3afbf-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="3afbf-134">您會看到已解決問題的詳細資料，以及解決問題時所包含的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="3afbf-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="3afbf-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="3afbf-135">Related topic</span></span>
- [<span data-ttu-id="3afbf-136">View the Security operations 儀表板</span><span class="sxs-lookup"><span data-stu-id="3afbf-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
