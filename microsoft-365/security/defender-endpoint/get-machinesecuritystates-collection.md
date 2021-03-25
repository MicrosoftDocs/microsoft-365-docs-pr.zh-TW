---
title: 取得電腦安全性性狀態集合 API
description: 使用 Microsoft Defender for Endpoint 來檢索裝置安全性狀態的集合。
keywords: api、graph api、支援的 api、get、device、security、state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200362"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="d11e8-104">取得電腦安全性性狀態集合 API</span><span class="sxs-lookup"><span data-stu-id="d11e8-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d11e8-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d11e8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d11e8-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d11e8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d11e8-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d11e8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="d11e8-108">會檢索裝置安全性狀態的集合。</span><span class="sxs-lookup"><span data-stu-id="d11e8-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="d11e8-109">權限</span><span class="sxs-lookup"><span data-stu-id="d11e8-109">Permissions</span></span>
<span data-ttu-id="d11e8-110">使用者需要讀取權限。</span><span class="sxs-lookup"><span data-stu-id="d11e8-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="d11e8-111">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d11e8-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="d11e8-112">要求標頭</span><span class="sxs-lookup"><span data-stu-id="d11e8-112">Request headers</span></span>

<span data-ttu-id="d11e8-113">Header</span><span class="sxs-lookup"><span data-stu-id="d11e8-113">Header</span></span> | <span data-ttu-id="d11e8-114">值</span><span class="sxs-lookup"><span data-stu-id="d11e8-114">Value</span></span> 
:---|:---
<span data-ttu-id="d11e8-115">授權</span><span class="sxs-lookup"><span data-stu-id="d11e8-115">Authorization</span></span> | <span data-ttu-id="d11e8-116">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="d11e8-116">Bearer {token}.</span></span> <span data-ttu-id="d11e8-117">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="d11e8-117">**Required**.</span></span>
<span data-ttu-id="d11e8-118">內容類型</span><span class="sxs-lookup"><span data-stu-id="d11e8-118">Content type</span></span> | <span data-ttu-id="d11e8-119">application/json</span><span class="sxs-lookup"><span data-stu-id="d11e8-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="d11e8-120">要求正文</span><span class="sxs-lookup"><span data-stu-id="d11e8-120">Request body</span></span>
<span data-ttu-id="d11e8-121">空白</span><span class="sxs-lookup"><span data-stu-id="d11e8-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d11e8-122">回應</span><span class="sxs-lookup"><span data-stu-id="d11e8-122">Response</span></span>
<span data-ttu-id="d11e8-123">如果成功-200 確定。</span><span class="sxs-lookup"><span data-stu-id="d11e8-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="d11e8-124">範例</span><span class="sxs-lookup"><span data-stu-id="d11e8-124">Example</span></span>

<span data-ttu-id="d11e8-125">**請求**</span><span class="sxs-lookup"><span data-stu-id="d11e8-125">**Request**</span></span>

<span data-ttu-id="d11e8-126">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="d11e8-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="d11e8-127">**回應**</span><span class="sxs-lookup"><span data-stu-id="d11e8-127">**Response**</span></span>

<span data-ttu-id="d11e8-128">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="d11e8-128">Here is an example of the response.</span></span>
<span data-ttu-id="d11e8-129">欄位 *識別碼* 包含裝置識別碼，且等於裝置資訊中的欄位 \*識別碼\*\*。</span><span class="sxs-lookup"><span data-stu-id="d11e8-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
