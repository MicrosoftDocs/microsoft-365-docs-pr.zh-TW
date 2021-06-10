---
title: 分數方法和屬性
description: 依設備群組，檢索組織的公開分數、裝置安全分數和披露分數
keywords: api，graph api，支援的 api，分數，暴露分數，裝置安全分數，依設備群組的暴露分數
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771426"
---
# <a name="score-resource-type"></a><span data-ttu-id="848f1-104">評分資源類型</span><span class="sxs-lookup"><span data-stu-id="848f1-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="848f1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="848f1-105">**Applies to:**</span></span>
- [<span data-ttu-id="848f1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="848f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="848f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="848f1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="848f1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="848f1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="848f1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="848f1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="848f1-110">方法</span><span class="sxs-lookup"><span data-stu-id="848f1-110">Methods</span></span>

<span data-ttu-id="848f1-111">方法	</span><span class="sxs-lookup"><span data-stu-id="848f1-111">Method</span></span> |<span data-ttu-id="848f1-112">傳回類型</span><span class="sxs-lookup"><span data-stu-id="848f1-112">Return Type</span></span> |<span data-ttu-id="848f1-113">描述</span><span class="sxs-lookup"><span data-stu-id="848f1-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="848f1-114">取得暴險分數</span><span class="sxs-lookup"><span data-stu-id="848f1-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="848f1-115">分數</span><span class="sxs-lookup"><span data-stu-id="848f1-115">Score</span></span>](score.md) | <span data-ttu-id="848f1-116">取得組織公開分數。</span><span class="sxs-lookup"><span data-stu-id="848f1-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="848f1-117">取得裝置安全分數</span><span class="sxs-lookup"><span data-stu-id="848f1-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="848f1-118">分數</span><span class="sxs-lookup"><span data-stu-id="848f1-118">Score</span></span>](score.md) | <span data-ttu-id="848f1-119">取得組織裝置安全分數。</span><span class="sxs-lookup"><span data-stu-id="848f1-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="848f1-120">依設備群組列出曝光排名</span><span class="sxs-lookup"><span data-stu-id="848f1-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="848f1-121">分數</span><span class="sxs-lookup"><span data-stu-id="848f1-121">Score</span></span>](score.md) | <span data-ttu-id="848f1-122">依設備群組列出分數。</span><span class="sxs-lookup"><span data-stu-id="848f1-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="848f1-123">屬性</span><span class="sxs-lookup"><span data-stu-id="848f1-123">Properties</span></span>

<span data-ttu-id="848f1-124">屬性	</span><span class="sxs-lookup"><span data-stu-id="848f1-124">Property</span></span> |  <span data-ttu-id="848f1-125">類型</span><span class="sxs-lookup"><span data-stu-id="848f1-125">Type</span></span>    |   <span data-ttu-id="848f1-126">描述</span><span class="sxs-lookup"><span data-stu-id="848f1-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="848f1-127">分數</span><span class="sxs-lookup"><span data-stu-id="848f1-127">Score</span></span> | <span data-ttu-id="848f1-128">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="848f1-128">Double</span></span> | <span data-ttu-id="848f1-129">目前的分數。</span><span class="sxs-lookup"><span data-stu-id="848f1-129">The current score.</span></span>
<span data-ttu-id="848f1-130">時間</span><span class="sxs-lookup"><span data-stu-id="848f1-130">Time</span></span> | <span data-ttu-id="848f1-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="848f1-131">DateTime</span></span> | <span data-ttu-id="848f1-132">此 API 通話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="848f1-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="848f1-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="848f1-133">RbacGroupName</span></span> | <span data-ttu-id="848f1-134">字串</span><span class="sxs-lookup"><span data-stu-id="848f1-134">String</span></span> | <span data-ttu-id="848f1-135">裝置群組名稱。</span><span class="sxs-lookup"><span data-stu-id="848f1-135">The device group name.</span></span>
