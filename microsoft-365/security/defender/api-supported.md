---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: Microsoft 365 Defender、APIs、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935722"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="beb88-104">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="beb88-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="beb88-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="beb88-105">**Applies to:**</span></span>
- <span data-ttu-id="beb88-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beb88-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beb88-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="beb88-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="beb88-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="beb88-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="beb88-109">可用 APIs 的清單</span><span class="sxs-lookup"><span data-stu-id="beb88-109">List of available APIs</span></span>

<span data-ttu-id="beb88-110">文章</span><span class="sxs-lookup"><span data-stu-id="beb88-110">Article</span></span> | <span data-ttu-id="beb88-111">描述</span><span class="sxs-lookup"><span data-stu-id="beb88-111">Description</span></span>
-|-
[<span data-ttu-id="beb88-112">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="beb88-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="beb88-113">執行高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="beb88-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="beb88-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="beb88-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="beb88-115">列出和更新事件，以及其他實用工作。</span><span class="sxs-lookup"><span data-stu-id="beb88-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="beb88-116">端點 URIs</span><span class="sxs-lookup"><span data-stu-id="beb88-116">Endpoint URIs</span></span>

<span data-ttu-id="beb88-117">主要 APIs 的基底 URI 是： https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="beb88-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="beb88-118">為了獲得較佳的效能，請使用與您的地理位置更接近的伺服器：</span><span class="sxs-lookup"><span data-stu-id="beb88-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="beb88-119">美國： api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="beb88-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="beb88-120">歐洲： api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="beb88-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="beb88-121">英國： api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="beb88-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="beb88-122">您可以透過存取來取得權杖 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="beb88-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="beb88-123">所有沿路徑的 APIs 都 `/api` 使用 [OData](/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="beb88-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="beb88-124">相關文章</span><span class="sxs-lookup"><span data-stu-id="beb88-124">Related articles</span></span>

- [<span data-ttu-id="beb88-125">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="beb88-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="beb88-126">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="beb88-126">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="beb88-127">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="beb88-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="beb88-128">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="beb88-128">Understand error codes</span></span>](api-error-codes.md)