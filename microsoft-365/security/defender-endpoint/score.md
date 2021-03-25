---
title: 計分方法和屬性
description: 依設備群組，檢索組織的公開分數、裝置安全分數和披露分數
keywords: api，graph api，支援的 api，分數，暴露分數，裝置安全分數，依設備群組的暴露分數
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200158"
---
# <a name="score-resource-type"></a><span data-ttu-id="d6a26-104">評分資源類型</span><span class="sxs-lookup"><span data-stu-id="d6a26-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d6a26-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d6a26-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6a26-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6a26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d6a26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6a26-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d6a26-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d6a26-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d6a26-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d6a26-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="d6a26-110">方法</span><span class="sxs-lookup"><span data-stu-id="d6a26-110">Methods</span></span>

<span data-ttu-id="d6a26-111">方法	</span><span class="sxs-lookup"><span data-stu-id="d6a26-111">Method</span></span> |<span data-ttu-id="d6a26-112">傳回類型</span><span class="sxs-lookup"><span data-stu-id="d6a26-112">Return Type</span></span> |<span data-ttu-id="d6a26-113">描述</span><span class="sxs-lookup"><span data-stu-id="d6a26-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d6a26-114">取得披露分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="d6a26-115">分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-115">Score</span></span>](score.md) | <span data-ttu-id="d6a26-116">取得組織公開分數。</span><span class="sxs-lookup"><span data-stu-id="d6a26-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="d6a26-117">取得裝置安全分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="d6a26-118">分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-118">Score</span></span>](score.md) | <span data-ttu-id="d6a26-119">取得組織裝置安全分數。</span><span class="sxs-lookup"><span data-stu-id="d6a26-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="d6a26-120">依設備群組列出曝光排名</span><span class="sxs-lookup"><span data-stu-id="d6a26-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="d6a26-121">分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-121">Score</span></span>](score.md) | <span data-ttu-id="d6a26-122">依設備群組列出分數。</span><span class="sxs-lookup"><span data-stu-id="d6a26-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="d6a26-123">屬性</span><span class="sxs-lookup"><span data-stu-id="d6a26-123">Properties</span></span>

<span data-ttu-id="d6a26-124">屬性	</span><span class="sxs-lookup"><span data-stu-id="d6a26-124">Property</span></span> |  <span data-ttu-id="d6a26-125">類型</span><span class="sxs-lookup"><span data-stu-id="d6a26-125">Type</span></span>    |   <span data-ttu-id="d6a26-126">描述</span><span class="sxs-lookup"><span data-stu-id="d6a26-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="d6a26-127">分數</span><span class="sxs-lookup"><span data-stu-id="d6a26-127">Score</span></span> | <span data-ttu-id="d6a26-128">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="d6a26-128">Double</span></span> | <span data-ttu-id="d6a26-129">目前的分數。</span><span class="sxs-lookup"><span data-stu-id="d6a26-129">The current score.</span></span>
<span data-ttu-id="d6a26-130">時間</span><span class="sxs-lookup"><span data-stu-id="d6a26-130">Time</span></span> | <span data-ttu-id="d6a26-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="d6a26-131">DateTime</span></span> | <span data-ttu-id="d6a26-132">此 API 通話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d6a26-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="d6a26-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d6a26-133">RbacGroupName</span></span> | <span data-ttu-id="d6a26-134">字串</span><span class="sxs-lookup"><span data-stu-id="d6a26-134">String</span></span> | <span data-ttu-id="d6a26-135">裝置群組名稱。</span><span class="sxs-lookup"><span data-stu-id="d6a26-135">The device group name.</span></span>
