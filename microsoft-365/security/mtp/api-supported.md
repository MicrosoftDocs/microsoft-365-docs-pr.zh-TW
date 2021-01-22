---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: MTP、API、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926195"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="66037-104">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="66037-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="66037-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="66037-105">**Applies to:**</span></span>
- <span data-ttu-id="66037-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66037-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66037-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="66037-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="66037-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="66037-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="66037-109">可用的 API 清單</span><span class="sxs-lookup"><span data-stu-id="66037-109">List of available APIs</span></span>

<span data-ttu-id="66037-110">文章</span><span class="sxs-lookup"><span data-stu-id="66037-110">Article</span></span> | <span data-ttu-id="66037-111">描述</span><span class="sxs-lookup"><span data-stu-id="66037-111">Description</span></span>
-|-
[<span data-ttu-id="66037-112">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="66037-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="66037-113">執行進位搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="66037-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="66037-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="66037-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="66037-115">列出及更新事件，以及其他實際工作。</span><span class="sxs-lookup"><span data-stu-id="66037-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="66037-116">端點 URI</span><span class="sxs-lookup"><span data-stu-id="66037-116">Endpoint URIs</span></span>

<span data-ttu-id="66037-117">兩個主要 API 的基本 URI 為： https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="66037-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="66037-118">若要獲得更佳的績效，請使用較靠近您地理位置的伺服器：</span><span class="sxs-lookup"><span data-stu-id="66037-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="66037-119">美國：api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66037-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="66037-120">歐洲：api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66037-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="66037-121">英國：api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66037-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="66037-122">權杖可以存取來取得 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="66037-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="66037-123">路徑上的所有 API `/api` 都使用 [OData](https://docs.microsoft.com/odata/overview) Protocol;例如 https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="66037-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="66037-124">相關文章</span><span class="sxs-lookup"><span data-stu-id="66037-124">Related articles</span></span>

- [<span data-ttu-id="66037-125">Microsoft 365 Defender API 概觀</span><span class="sxs-lookup"><span data-stu-id="66037-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="66037-126">存取 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="66037-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="66037-127">瞭解 API 限制與授權</span><span class="sxs-lookup"><span data-stu-id="66037-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="66037-128">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="66037-128">Understand error codes</span></span>](api-error-codes.md)
