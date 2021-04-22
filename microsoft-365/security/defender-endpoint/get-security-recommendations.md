---
title: 取得安全性建議
description: 會檢索與指定裝置識別碼相關的安全性建議集合。
keywords: api，graph api，支援的 api，get，list，file，information，per device 的安全性建議，威脅 & 漏洞管理 api，Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935302"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="1d726-104">取得安全性建議</span><span class="sxs-lookup"><span data-stu-id="1d726-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d726-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1d726-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1d726-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1d726-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1d726-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1d726-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1d726-108">會檢索與指定裝置識別碼相關的安全性建議集合。</span><span class="sxs-lookup"><span data-stu-id="1d726-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="1d726-109">權限</span><span class="sxs-lookup"><span data-stu-id="1d726-109">Permissions</span></span>
<span data-ttu-id="1d726-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="1d726-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d726-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d726-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1d726-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="1d726-112">Permission type</span></span> |   <span data-ttu-id="1d726-113">權限</span><span class="sxs-lookup"><span data-stu-id="1d726-113">Permission</span></span>  |   <span data-ttu-id="1d726-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="1d726-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d726-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="1d726-115">Application</span></span> | <span data-ttu-id="1d726-116">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="1d726-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="1d726-117">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1d726-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1d726-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="1d726-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1d726-119">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="1d726-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1d726-120">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1d726-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1d726-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1d726-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="1d726-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1d726-122">Request headers</span></span>

<span data-ttu-id="1d726-123">名稱</span><span class="sxs-lookup"><span data-stu-id="1d726-123">Name</span></span> | <span data-ttu-id="1d726-124">類型</span><span class="sxs-lookup"><span data-stu-id="1d726-124">Type</span></span> | <span data-ttu-id="1d726-125">描述</span><span class="sxs-lookup"><span data-stu-id="1d726-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d726-126">授權</span><span class="sxs-lookup"><span data-stu-id="1d726-126">Authorization</span></span> | <span data-ttu-id="1d726-127">字串</span><span class="sxs-lookup"><span data-stu-id="1d726-127">String</span></span> | <span data-ttu-id="1d726-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="1d726-128">Bearer {token}.</span></span> <span data-ttu-id="1d726-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1d726-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1d726-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="1d726-130">Request body</span></span>
<span data-ttu-id="1d726-131">空白</span><span class="sxs-lookup"><span data-stu-id="1d726-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d726-132">回應</span><span class="sxs-lookup"><span data-stu-id="1d726-132">Response</span></span>
<span data-ttu-id="1d726-133">如果成功，這個方法會以本文中的安全性建議傳回 200 OK。</span><span class="sxs-lookup"><span data-stu-id="1d726-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1d726-134">範例</span><span class="sxs-lookup"><span data-stu-id="1d726-134">Example</span></span>

<span data-ttu-id="1d726-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="1d726-135">**Request**</span></span>

<span data-ttu-id="1d726-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="1d726-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="1d726-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="1d726-137">**Response**</span></span>

<span data-ttu-id="1d726-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="1d726-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="1d726-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="1d726-139">Related topics</span></span>
- [<span data-ttu-id="1d726-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="1d726-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1d726-141">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="1d726-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
