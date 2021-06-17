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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985081"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="35b25-104">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="35b25-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="35b25-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="35b25-105">**Applies to:**</span></span>
- <span data-ttu-id="35b25-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35b25-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35b25-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="35b25-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="35b25-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="35b25-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="35b25-109">可用 APIs 的清單</span><span class="sxs-lookup"><span data-stu-id="35b25-109">List of available APIs</span></span>

<span data-ttu-id="35b25-110">文章</span><span class="sxs-lookup"><span data-stu-id="35b25-110">Article</span></span> | <span data-ttu-id="35b25-111">描述</span><span class="sxs-lookup"><span data-stu-id="35b25-111">Description</span></span>
-|-
[<span data-ttu-id="35b25-112">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="35b25-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="35b25-113">執行高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="35b25-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="35b25-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="35b25-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="35b25-115">列出和更新事件，以及其他實用工作。</span><span class="sxs-lookup"><span data-stu-id="35b25-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="35b25-116">[流式 API](streaming-api.md) (預覽) </span><span class="sxs-lookup"><span data-stu-id="35b25-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="35b25-117">在單一資料流程中發生即時事件及警示。</span><span class="sxs-lookup"><span data-stu-id="35b25-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="35b25-118">端點 URIs</span><span class="sxs-lookup"><span data-stu-id="35b25-118">Endpoint URIs</span></span>

<span data-ttu-id="35b25-119">主要 APIs 的基底 URI 是： https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="35b25-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="35b25-120">為了獲得較佳的效能，請使用與您的地理位置更接近的伺服器：</span><span class="sxs-lookup"><span data-stu-id="35b25-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="35b25-121">美國： api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35b25-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="35b25-122">歐洲： api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35b25-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="35b25-123">英國： api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35b25-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="35b25-124">您可以透過存取來取得權杖 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="35b25-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="35b25-125">所有沿路徑的 APIs 都 `/api` 使用 [OData](/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="35b25-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="35b25-126">相關文章</span><span class="sxs-lookup"><span data-stu-id="35b25-126">Related articles</span></span>

- [<span data-ttu-id="35b25-127">Microsoft 365 DefenderAPIs 概述</span><span class="sxs-lookup"><span data-stu-id="35b25-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="35b25-128">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="35b25-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="35b25-129">串流 API</span><span class="sxs-lookup"><span data-stu-id="35b25-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="35b25-130">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="35b25-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="35b25-131">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="35b25-131">Understand error codes</span></span>](api-error-codes.md)
