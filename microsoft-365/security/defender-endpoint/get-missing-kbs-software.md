---
title: 依軟體識別碼取得遺失的 Kb
description: 依軟體識別碼檢索遺失的安全性更新
keywords: api，graph api，支援的 api，get，list，file，information，軟體識別碼，威脅 & 弱點管理 api，Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9218ad447f926f0086801036277323e7c1efb4c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770556"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="4a577-104">依軟體識別碼取得遺失的 Kb</span><span class="sxs-lookup"><span data-stu-id="4a577-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a577-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4a577-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4a577-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="4a577-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a577-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4a577-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4a577-108">) 依軟體識別碼的安全性更新，檢索遺失的 Kb (</span><span class="sxs-lookup"><span data-stu-id="4a577-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="4a577-109">權限</span><span class="sxs-lookup"><span data-stu-id="4a577-109">Permissions</span></span>

<span data-ttu-id="4a577-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="4a577-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4a577-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4a577-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4a577-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="4a577-112">Permission type</span></span> |   <span data-ttu-id="4a577-113">權限</span><span class="sxs-lookup"><span data-stu-id="4a577-113">Permission</span></span>   |   <span data-ttu-id="4a577-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="4a577-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4a577-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="4a577-115">Application</span></span> |<span data-ttu-id="4a577-116">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="4a577-116">Software.Read.All</span></span> |   <span data-ttu-id="4a577-117">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="4a577-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="4a577-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="4a577-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4a577-119">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="4a577-119">Software.Read</span></span> |   <span data-ttu-id="4a577-120">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="4a577-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4a577-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="4a577-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="4a577-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="4a577-122">Request header</span></span>

<span data-ttu-id="4a577-123">名稱</span><span class="sxs-lookup"><span data-stu-id="4a577-123">Name</span></span> | <span data-ttu-id="4a577-124">類型</span><span class="sxs-lookup"><span data-stu-id="4a577-124">Type</span></span> | <span data-ttu-id="4a577-125">描述</span><span class="sxs-lookup"><span data-stu-id="4a577-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4a577-126">授權</span><span class="sxs-lookup"><span data-stu-id="4a577-126">Authorization</span></span> | <span data-ttu-id="4a577-127">字串</span><span class="sxs-lookup"><span data-stu-id="4a577-127">String</span></span> | <span data-ttu-id="4a577-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="4a577-128">Bearer {token}.</span></span> <span data-ttu-id="4a577-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="4a577-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4a577-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="4a577-130">Request body</span></span>

<span data-ttu-id="4a577-131">空白</span><span class="sxs-lookup"><span data-stu-id="4a577-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4a577-132">回應</span><span class="sxs-lookup"><span data-stu-id="4a577-132">Response</span></span>

<span data-ttu-id="4a577-133">如果成功，這個方法會傳回200，但主體中指定的軟體缺少 kb 資料。</span><span class="sxs-lookup"><span data-stu-id="4a577-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="4a577-134">範例</span><span class="sxs-lookup"><span data-stu-id="4a577-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="4a577-135">請求</span><span class="sxs-lookup"><span data-stu-id="4a577-135">Request</span></span>

<span data-ttu-id="4a577-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="4a577-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="4a577-137">回應</span><span class="sxs-lookup"><span data-stu-id="4a577-137">Response</span></span>

<span data-ttu-id="4a577-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="4a577-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="4a577-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="4a577-139">Related topics</span></span>

- [<span data-ttu-id="4a577-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="4a577-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4a577-141">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="4a577-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
