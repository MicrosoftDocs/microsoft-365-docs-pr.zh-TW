---
title: 依軟體識別碼取得遺失的 Kb
description: 依軟體識別碼檢索遺失的安全性更新
keywords: api，graph api，支援的 api，get，list，file，information，軟體識別碼，威脅 & 漏洞管理 api，mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499385"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="54ac8-104">依軟體識別碼取得遺失的 Kb</span><span class="sxs-lookup"><span data-stu-id="54ac8-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54ac8-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="54ac8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="54ac8-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="54ac8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54ac8-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="54ac8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="54ac8-108">) 依軟體識別碼的安全性更新，檢索遺失的 Kb (</span><span class="sxs-lookup"><span data-stu-id="54ac8-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="54ac8-109">權限</span><span class="sxs-lookup"><span data-stu-id="54ac8-109">Permissions</span></span>

<span data-ttu-id="54ac8-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="54ac8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="54ac8-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="54ac8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="54ac8-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="54ac8-112">Permission type</span></span> |   <span data-ttu-id="54ac8-113">權限</span><span class="sxs-lookup"><span data-stu-id="54ac8-113">Permission</span></span>   |   <span data-ttu-id="54ac8-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="54ac8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="54ac8-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="54ac8-115">Application</span></span> |<span data-ttu-id="54ac8-116">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="54ac8-116">Software.Read.All</span></span> |   <span data-ttu-id="54ac8-117">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="54ac8-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="54ac8-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="54ac8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="54ac8-119">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="54ac8-119">Software.Read</span></span> |   <span data-ttu-id="54ac8-120">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="54ac8-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="54ac8-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="54ac8-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="54ac8-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="54ac8-122">Request header</span></span>

<span data-ttu-id="54ac8-123">名稱</span><span class="sxs-lookup"><span data-stu-id="54ac8-123">Name</span></span> | <span data-ttu-id="54ac8-124">類型</span><span class="sxs-lookup"><span data-stu-id="54ac8-124">Type</span></span> | <span data-ttu-id="54ac8-125">描述</span><span class="sxs-lookup"><span data-stu-id="54ac8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="54ac8-126">授權</span><span class="sxs-lookup"><span data-stu-id="54ac8-126">Authorization</span></span> | <span data-ttu-id="54ac8-127">字串</span><span class="sxs-lookup"><span data-stu-id="54ac8-127">String</span></span> | <span data-ttu-id="54ac8-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="54ac8-128">Bearer {token}.</span></span> <span data-ttu-id="54ac8-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="54ac8-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="54ac8-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="54ac8-130">Request body</span></span>

<span data-ttu-id="54ac8-131">空白</span><span class="sxs-lookup"><span data-stu-id="54ac8-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="54ac8-132">回應</span><span class="sxs-lookup"><span data-stu-id="54ac8-132">Response</span></span>

<span data-ttu-id="54ac8-133">如果成功，這個方法會傳回200，但主體中指定的軟體缺少 kb 資料。</span><span class="sxs-lookup"><span data-stu-id="54ac8-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="54ac8-134">範例</span><span class="sxs-lookup"><span data-stu-id="54ac8-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="54ac8-135">請求</span><span class="sxs-lookup"><span data-stu-id="54ac8-135">Request</span></span>

<span data-ttu-id="54ac8-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="54ac8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="54ac8-137">回應</span><span class="sxs-lookup"><span data-stu-id="54ac8-137">Response</span></span>

<span data-ttu-id="54ac8-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="54ac8-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="54ac8-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="54ac8-139">Related topics</span></span>

- [<span data-ttu-id="54ac8-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="54ac8-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="54ac8-141">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="54ac8-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
