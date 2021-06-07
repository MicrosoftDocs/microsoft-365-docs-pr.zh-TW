---
title: 列出所有建議
description: 會檢索影響組織之所有安全性建議的清單。
keywords: api、graph api、支援的 api、get、security 建議、Microsoft Defender for Endpoint tvm api 威脅與弱點管理威脅與弱點管理 api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768922"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="1102d-104">列出所有建議</span><span class="sxs-lookup"><span data-stu-id="1102d-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1102d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1102d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1102d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1102d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1102d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1102d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="1102d-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="1102d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1102d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1102d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1102d-110">會檢索影響組織之所有安全性建議的清單。</span><span class="sxs-lookup"><span data-stu-id="1102d-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="1102d-111">權限</span><span class="sxs-lookup"><span data-stu-id="1102d-111">Permissions</span></span>
<span data-ttu-id="1102d-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="1102d-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1102d-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1102d-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1102d-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="1102d-114">Permission type</span></span> |   <span data-ttu-id="1102d-115">權限</span><span class="sxs-lookup"><span data-stu-id="1102d-115">Permission</span></span>  |   <span data-ttu-id="1102d-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="1102d-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1102d-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="1102d-117">Application</span></span> |   <span data-ttu-id="1102d-118">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="1102d-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1102d-119">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1102d-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1102d-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="1102d-120">Delegated (work or school account)</span></span> | <span data-ttu-id="1102d-121">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="1102d-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1102d-122">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1102d-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1102d-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1102d-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="1102d-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1102d-124">Request headers</span></span>

<span data-ttu-id="1102d-125">名稱</span><span class="sxs-lookup"><span data-stu-id="1102d-125">Name</span></span> | <span data-ttu-id="1102d-126">類型</span><span class="sxs-lookup"><span data-stu-id="1102d-126">Type</span></span> | <span data-ttu-id="1102d-127">描述</span><span class="sxs-lookup"><span data-stu-id="1102d-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="1102d-128">授權</span><span class="sxs-lookup"><span data-stu-id="1102d-128">Authorization</span></span> | <span data-ttu-id="1102d-129">字串</span><span class="sxs-lookup"><span data-stu-id="1102d-129">String</span></span> | <span data-ttu-id="1102d-130">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="1102d-130">Bearer {token}.</span></span> <span data-ttu-id="1102d-131">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1102d-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1102d-132">要求正文</span><span class="sxs-lookup"><span data-stu-id="1102d-132">Request body</span></span>
<span data-ttu-id="1102d-133">空白</span><span class="sxs-lookup"><span data-stu-id="1102d-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1102d-134">回應</span><span class="sxs-lookup"><span data-stu-id="1102d-134">Response</span></span>
<span data-ttu-id="1102d-135">如果成功，這個方法會以本文中的安全性建議清單傳回 200 OK。</span><span class="sxs-lookup"><span data-stu-id="1102d-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1102d-136">範例</span><span class="sxs-lookup"><span data-stu-id="1102d-136">Example</span></span>

<span data-ttu-id="1102d-137">**請求**</span><span class="sxs-lookup"><span data-stu-id="1102d-137">**Request**</span></span>

<span data-ttu-id="1102d-138">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="1102d-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="1102d-139">**回應**</span><span class="sxs-lookup"><span data-stu-id="1102d-139">**Response**</span></span>

<span data-ttu-id="1102d-140">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="1102d-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="1102d-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="1102d-141">See also</span></span>
- [<span data-ttu-id="1102d-142">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="1102d-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1102d-143">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="1102d-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

