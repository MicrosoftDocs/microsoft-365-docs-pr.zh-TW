---
title: 依識別碼取得建議
description: 依識別碼取得安全性建議。
keywords: api，graph api，支援的 api，get，安全性建議，依識別碼的安全性建議，威脅與弱點管理，威脅與弱點管理 api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 66eb9c838e351a75ff68f40e9179cfeeb9bf9d4e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845183"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="2f7fb-104">根據識別碼取得建議</span><span class="sxs-lookup"><span data-stu-id="2f7fb-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f7fb-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2f7fb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2f7fb-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="2f7fb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f7fb-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2f7fb-108">依識別碼取得安全性建議。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="2f7fb-109">權限</span><span class="sxs-lookup"><span data-stu-id="2f7fb-109">Permissions</span></span>
<span data-ttu-id="2f7fb-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2f7fb-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2f7fb-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="2f7fb-112">Permission type</span></span> |   <span data-ttu-id="2f7fb-113">權限</span><span class="sxs-lookup"><span data-stu-id="2f7fb-113">Permission</span></span>  |   <span data-ttu-id="2f7fb-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="2f7fb-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2f7fb-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="2f7fb-115">Application</span></span> |   <span data-ttu-id="2f7fb-116">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="2f7fb-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="2f7fb-117">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="2f7fb-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="2f7fb-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="2f7fb-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2f7fb-119">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="2f7fb-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="2f7fb-120">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="2f7fb-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2f7fb-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2f7fb-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="2f7fb-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="2f7fb-122">Request headers</span></span>

<span data-ttu-id="2f7fb-123">名稱</span><span class="sxs-lookup"><span data-stu-id="2f7fb-123">Name</span></span> | <span data-ttu-id="2f7fb-124">類型</span><span class="sxs-lookup"><span data-stu-id="2f7fb-124">Type</span></span> | <span data-ttu-id="2f7fb-125">描述</span><span class="sxs-lookup"><span data-stu-id="2f7fb-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f7fb-126">授權</span><span class="sxs-lookup"><span data-stu-id="2f7fb-126">Authorization</span></span> | <span data-ttu-id="2f7fb-127">字串</span><span class="sxs-lookup"><span data-stu-id="2f7fb-127">String</span></span> | <span data-ttu-id="2f7fb-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-128">Bearer {token}.</span></span> <span data-ttu-id="2f7fb-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2f7fb-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="2f7fb-130">Request body</span></span>
<span data-ttu-id="2f7fb-131">空白</span><span class="sxs-lookup"><span data-stu-id="2f7fb-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2f7fb-132">回應</span><span class="sxs-lookup"><span data-stu-id="2f7fb-132">Response</span></span>
<span data-ttu-id="2f7fb-133">如果成功，這個方法會以本文中的安全性建議傳回 200 OK。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="2f7fb-134">範例</span><span class="sxs-lookup"><span data-stu-id="2f7fb-134">Example</span></span>

<span data-ttu-id="2f7fb-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="2f7fb-135">**Request**</span></span>

<span data-ttu-id="2f7fb-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="2f7fb-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="2f7fb-137">**Response**</span></span>

<span data-ttu-id="2f7fb-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="2f7fb-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="2f7fb-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f7fb-139">Related topics</span></span>
- [<span data-ttu-id="2f7fb-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="2f7fb-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2f7fb-141">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="2f7fb-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
