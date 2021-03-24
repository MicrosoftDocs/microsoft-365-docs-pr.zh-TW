---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: MTP、APIs、api
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
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054606"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="c3dee-104">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="c3dee-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c3dee-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c3dee-105">**Applies to:**</span></span>
- <span data-ttu-id="c3dee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3dee-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3dee-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="c3dee-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c3dee-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="c3dee-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="c3dee-109">可用 APIs 的清單</span><span class="sxs-lookup"><span data-stu-id="c3dee-109">List of available APIs</span></span>

<span data-ttu-id="c3dee-110">文章</span><span class="sxs-lookup"><span data-stu-id="c3dee-110">Article</span></span> | <span data-ttu-id="c3dee-111">描述</span><span class="sxs-lookup"><span data-stu-id="c3dee-111">Description</span></span>
-|-
[<span data-ttu-id="c3dee-112">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="c3dee-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="c3dee-113">執行高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c3dee-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="c3dee-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="c3dee-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="c3dee-115">列出和更新事件，以及其他實用工作。</span><span class="sxs-lookup"><span data-stu-id="c3dee-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="c3dee-116">端點 URIs</span><span class="sxs-lookup"><span data-stu-id="c3dee-116">Endpoint URIs</span></span>

<span data-ttu-id="c3dee-117">主要 APIs 的基底 URI 是： https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="c3dee-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="c3dee-118">為了獲得較佳的效能，請使用與您的地理位置更接近的伺服器：</span><span class="sxs-lookup"><span data-stu-id="c3dee-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="c3dee-119">美國： api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c3dee-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="c3dee-120">歐洲： api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c3dee-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="c3dee-121">英國： api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c3dee-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="c3dee-122">您可以透過存取來取得權杖 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="c3dee-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="c3dee-123">所有沿路徑的 APIs 都 `/api` 使用 [OData](/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="c3dee-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c3dee-124">相關文章</span><span class="sxs-lookup"><span data-stu-id="c3dee-124">Related articles</span></span>

- [<span data-ttu-id="c3dee-125">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="c3dee-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c3dee-126">存取 Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="c3dee-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="c3dee-127">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="c3dee-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c3dee-128">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="c3dee-128">Understand error codes</span></span>](api-error-codes.md)