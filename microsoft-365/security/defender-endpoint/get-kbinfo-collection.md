---
title: 取得 KB 集合 API
description: 使用 Microsoft Defender for Endpoint，檢索知識文庫的集合 (KB 的) 和 KB 詳細資料。
keywords: api、graph api、支援的 api、get、kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166478"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="e47e8-104">取得 KB 集合 API</span><span class="sxs-lookup"><span data-stu-id="e47e8-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e47e8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e47e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="e47e8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e47e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e47e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e47e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e47e8-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e47e8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e47e8-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e47e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="e47e8-110">會檢索 KB 的和 KB 詳細資料的集合。</span><span class="sxs-lookup"><span data-stu-id="e47e8-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="e47e8-111">權限</span><span class="sxs-lookup"><span data-stu-id="e47e8-111">Permissions</span></span>
<span data-ttu-id="e47e8-112">使用者需要讀取權限。</span><span class="sxs-lookup"><span data-stu-id="e47e8-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="e47e8-113">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e47e8-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="e47e8-114">要求標頭</span><span class="sxs-lookup"><span data-stu-id="e47e8-114">Request headers</span></span>

<span data-ttu-id="e47e8-115">頁首</span><span class="sxs-lookup"><span data-stu-id="e47e8-115">Header</span></span> | <span data-ttu-id="e47e8-116">值</span><span class="sxs-lookup"><span data-stu-id="e47e8-116">Value</span></span> 
:---|:---
<span data-ttu-id="e47e8-117">授權</span><span class="sxs-lookup"><span data-stu-id="e47e8-117">Authorization</span></span> | <span data-ttu-id="e47e8-118">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="e47e8-118">Bearer {token}.</span></span> <span data-ttu-id="e47e8-119">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="e47e8-119">**Required**.</span></span>
<span data-ttu-id="e47e8-120">內容類型</span><span class="sxs-lookup"><span data-stu-id="e47e8-120">Content type</span></span> | <span data-ttu-id="e47e8-121">application/json</span><span class="sxs-lookup"><span data-stu-id="e47e8-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e47e8-122">要求正文</span><span class="sxs-lookup"><span data-stu-id="e47e8-122">Request body</span></span>
<span data-ttu-id="e47e8-123">空白</span><span class="sxs-lookup"><span data-stu-id="e47e8-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e47e8-124">回應</span><span class="sxs-lookup"><span data-stu-id="e47e8-124">Response</span></span>
<span data-ttu-id="e47e8-125">如果成功-200 確定。</span><span class="sxs-lookup"><span data-stu-id="e47e8-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="e47e8-126">範例</span><span class="sxs-lookup"><span data-stu-id="e47e8-126">Example</span></span>

<span data-ttu-id="e47e8-127">**請求**</span><span class="sxs-lookup"><span data-stu-id="e47e8-127">**Request**</span></span>

<span data-ttu-id="e47e8-128">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="e47e8-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="e47e8-129">**回應**</span><span class="sxs-lookup"><span data-stu-id="e47e8-129">**Response**</span></span>

<span data-ttu-id="e47e8-130">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="e47e8-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
