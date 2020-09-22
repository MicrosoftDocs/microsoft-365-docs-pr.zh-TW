---
title: 受支援的 Microsoft 威脅防護 API
description: 受支援的 Microsoft 威脅防護 API
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203692"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="652e8-104">受支援的 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="652e8-104">Supported Microsoft Threat Protection APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="652e8-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="652e8-105">**Applies to:**</span></span>
- <span data-ttu-id="652e8-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="652e8-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="652e8-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="652e8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="652e8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="652e8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="652e8-109">結束點 URIs：</span><span class="sxs-lookup"><span data-stu-id="652e8-109">End Point URIs:</span></span>

- <span data-ttu-id="652e8-110">服務基底 URI 是： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="652e8-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="652e8-111">為了提高效能，您可以使用伺服器以接近地理位置：</span><span class="sxs-lookup"><span data-stu-id="652e8-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="652e8-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="652e8-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="652e8-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="652e8-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="652e8-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="652e8-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="652e8-115">權杖購置的資源應該是： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="652e8-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="652e8-116">Path 下的所有 APIs ```/api``` 都是 OData APIs。</span><span class="sxs-lookup"><span data-stu-id="652e8-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="652e8-117">舉例來說. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="652e8-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="652e8-118">可用 APIs 清單：</span><span class="sxs-lookup"><span data-stu-id="652e8-118">List of available APIs:</span></span>

<span data-ttu-id="652e8-119">主題</span><span class="sxs-lookup"><span data-stu-id="652e8-119">Topic</span></span> | <span data-ttu-id="652e8-120">描述</span><span class="sxs-lookup"><span data-stu-id="652e8-120">Description</span></span>
:---|:---
[<span data-ttu-id="652e8-121">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="652e8-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="652e8-122">從 API 執行高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="652e8-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="652e8-123">事件 API</span><span class="sxs-lookup"><span data-stu-id="652e8-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="652e8-124">執行與事件相關的 API 通話，例如：列出事件、更新事件等等。</span><span class="sxs-lookup"><span data-stu-id="652e8-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
