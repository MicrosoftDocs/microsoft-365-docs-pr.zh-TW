---
title: 取得 CVE-KB 地圖 API
description: 瞭解如何使用 [取得 CVE-KB 對應 API]，以在 Microsoft Defender for Endpoint 中從 CVE 的摘要和 CVE 詳細資料中取得 CVE to KB 和 CVE 詳細資料的對應。
keywords: api，graph api，支援的 api，get，cve，kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166400"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="08a9b-104">取得 CVE-KB 地圖 API</span><span class="sxs-lookup"><span data-stu-id="08a9b-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08a9b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="08a9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="08a9b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08a9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08a9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08a9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="08a9b-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="08a9b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08a9b-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="08a9b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="08a9b-110">會檢索 CVE 的到 KB 和 CVE 詳細資料的對應。</span><span class="sxs-lookup"><span data-stu-id="08a9b-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="08a9b-111">權限</span><span class="sxs-lookup"><span data-stu-id="08a9b-111">Permissions</span></span>
<span data-ttu-id="08a9b-112">使用者需要讀取權限。</span><span class="sxs-lookup"><span data-stu-id="08a9b-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="08a9b-113">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="08a9b-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="08a9b-114">要求標頭</span><span class="sxs-lookup"><span data-stu-id="08a9b-114">Request headers</span></span>

<span data-ttu-id="08a9b-115">Header</span><span class="sxs-lookup"><span data-stu-id="08a9b-115">Header</span></span> | <span data-ttu-id="08a9b-116">值</span><span class="sxs-lookup"><span data-stu-id="08a9b-116">Value</span></span> 
:---|:---
<span data-ttu-id="08a9b-117">授權</span><span class="sxs-lookup"><span data-stu-id="08a9b-117">Authorization</span></span> | <span data-ttu-id="08a9b-118">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="08a9b-118">Bearer {token}.</span></span> <span data-ttu-id="08a9b-119">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="08a9b-119">**Required**.</span></span>
<span data-ttu-id="08a9b-120">內容類型</span><span class="sxs-lookup"><span data-stu-id="08a9b-120">Content type</span></span> | <span data-ttu-id="08a9b-121">application/json</span><span class="sxs-lookup"><span data-stu-id="08a9b-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="08a9b-122">要求正文</span><span class="sxs-lookup"><span data-stu-id="08a9b-122">Request body</span></span>
<span data-ttu-id="08a9b-123">空白</span><span class="sxs-lookup"><span data-stu-id="08a9b-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="08a9b-124">回應</span><span class="sxs-lookup"><span data-stu-id="08a9b-124">Response</span></span>
<span data-ttu-id="08a9b-125">如果成功和對應都存在-200 OK。</span><span class="sxs-lookup"><span data-stu-id="08a9b-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="08a9b-126">範例</span><span class="sxs-lookup"><span data-stu-id="08a9b-126">Example</span></span>

<span data-ttu-id="08a9b-127">**請求**</span><span class="sxs-lookup"><span data-stu-id="08a9b-127">**Request**</span></span>

<span data-ttu-id="08a9b-128">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="08a9b-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="08a9b-129">**回應**</span><span class="sxs-lookup"><span data-stu-id="08a9b-129">**Response**</span></span>

<span data-ttu-id="08a9b-130">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="08a9b-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
