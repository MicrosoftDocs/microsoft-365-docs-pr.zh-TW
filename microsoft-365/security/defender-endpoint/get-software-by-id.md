---
title: 依識別碼取得軟體
description: 依設備群組來檢索曝光分數的清單。
keywords: api，graph api，支援的 api，get，software，mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198586"
---
# <a name="get-software-by-id"></a><span data-ttu-id="3afe0-104">依識別碼取得軟體</span><span class="sxs-lookup"><span data-stu-id="3afe0-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3afe0-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3afe0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3afe0-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3afe0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3afe0-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3afe0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3afe0-108">依識別碼檢索軟體詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3afe0-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="3afe0-109">權限</span><span class="sxs-lookup"><span data-stu-id="3afe0-109">Permissions</span></span>
<span data-ttu-id="3afe0-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3afe0-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3afe0-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3afe0-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="3afe0-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3afe0-112">Permission type</span></span> |   <span data-ttu-id="3afe0-113">權限</span><span class="sxs-lookup"><span data-stu-id="3afe0-113">Permission</span></span>  |   <span data-ttu-id="3afe0-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3afe0-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3afe0-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="3afe0-115">Application</span></span> | <span data-ttu-id="3afe0-116">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="3afe0-116">Software.Read.All</span></span> | <span data-ttu-id="3afe0-117">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="3afe0-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="3afe0-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3afe0-118">Delegated (work or school account)</span></span> | <span data-ttu-id="3afe0-119">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="3afe0-119">Software.Read</span></span> | <span data-ttu-id="3afe0-120">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="3afe0-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3afe0-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3afe0-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="3afe0-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3afe0-122">Request headers</span></span>

| <span data-ttu-id="3afe0-123">名稱</span><span class="sxs-lookup"><span data-stu-id="3afe0-123">Name</span></span>        | <span data-ttu-id="3afe0-124">類型</span><span class="sxs-lookup"><span data-stu-id="3afe0-124">Type</span></span> | <span data-ttu-id="3afe0-125">描述</span><span class="sxs-lookup"><span data-stu-id="3afe0-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="3afe0-126">授權</span><span class="sxs-lookup"><span data-stu-id="3afe0-126">Authorization</span></span> | <span data-ttu-id="3afe0-127">字串</span><span class="sxs-lookup"><span data-stu-id="3afe0-127">String</span></span> | <span data-ttu-id="3afe0-128">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="3afe0-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3afe0-129">要求正文</span><span class="sxs-lookup"><span data-stu-id="3afe0-129">Request body</span></span>
<span data-ttu-id="3afe0-130">空白</span><span class="sxs-lookup"><span data-stu-id="3afe0-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3afe0-131">回應</span><span class="sxs-lookup"><span data-stu-id="3afe0-131">Response</span></span>
<span data-ttu-id="3afe0-132">如果成功，這個方法會以本文中指定的軟體資料傳回 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3afe0-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="3afe0-133">範例</span><span class="sxs-lookup"><span data-stu-id="3afe0-133">Example</span></span>

<span data-ttu-id="3afe0-134">**請求**</span><span class="sxs-lookup"><span data-stu-id="3afe0-134">**Request**</span></span>

<span data-ttu-id="3afe0-135">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3afe0-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="3afe0-136">**回應**</span><span class="sxs-lookup"><span data-stu-id="3afe0-136">**Response**</span></span>

<span data-ttu-id="3afe0-137">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3afe0-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="3afe0-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="3afe0-138">Related topics</span></span>
- [<span data-ttu-id="3afe0-139">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="3afe0-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3afe0-140">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="3afe0-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
