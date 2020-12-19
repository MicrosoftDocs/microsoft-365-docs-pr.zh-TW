---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: MTP、APIs、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719319"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="cc2cf-104">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="cc2cf-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cc2cf-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="cc2cf-105">**Applies to:**</span></span>
- <span data-ttu-id="cc2cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc2cf-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc2cf-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cc2cf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="cc2cf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="cc2cf-109">可用 APIs 的清單</span><span class="sxs-lookup"><span data-stu-id="cc2cf-109">List of available APIs</span></span>

<span data-ttu-id="cc2cf-110">文章</span><span class="sxs-lookup"><span data-stu-id="cc2cf-110">Article</span></span> | <span data-ttu-id="cc2cf-111">描述</span><span class="sxs-lookup"><span data-stu-id="cc2cf-111">Description</span></span>
-|-
[<span data-ttu-id="cc2cf-112">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="cc2cf-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="cc2cf-113">執行高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="cc2cf-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="cc2cf-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="cc2cf-115">列出和更新事件，以及其他實用工作。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="cc2cf-116">端點 URIs</span><span class="sxs-lookup"><span data-stu-id="cc2cf-116">Endpoint URIs</span></span>

<span data-ttu-id="cc2cf-117">主要 APIs 的基底 URI 是： https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="cc2cf-118">為了獲得較佳的效能，請使用與您的地理位置更接近的伺服器：</span><span class="sxs-lookup"><span data-stu-id="cc2cf-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="cc2cf-119">美國： api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc2cf-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="cc2cf-120">歐洲： api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc2cf-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="cc2cf-121">英國： api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc2cf-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="cc2cf-122">您可以透過存取來取得權杖 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="cc2cf-123">所有沿路徑的 APIs 都 `/api` 使用 [OData](https://docs.microsoft.com/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="cc2cf-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cc2cf-124">相關文章</span><span class="sxs-lookup"><span data-stu-id="cc2cf-124">Related articles</span></span>

- [<span data-ttu-id="cc2cf-125">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="cc2cf-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cc2cf-126">存取 Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="cc2cf-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="cc2cf-127">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="cc2cf-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cc2cf-128">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="cc2cf-128">Understand error codes</span></span>](api-error-codes.md)
