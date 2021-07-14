---
title: 取得發現的弱點
description: 會檢索與指定裝置識別碼相關的已探索弱點的集合。
keywords: api，graph api，支援的 api，get，list，file，information，發現的弱點，威脅 & 弱點管理 api，Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: cd3b1343711a5bed9ad606a6b8dc754f223ed279
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430777"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="663ba-104">取得發現的弱點</span><span class="sxs-lookup"><span data-stu-id="663ba-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="663ba-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="663ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="663ba-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="663ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="663ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="663ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="663ba-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="663ba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="663ba-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="663ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="663ba-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="663ba-110">API description</span></span>
<span data-ttu-id="663ba-111">會檢索與指定裝置識別碼相關的已探索弱點的集合。</span><span class="sxs-lookup"><span data-stu-id="663ba-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="663ba-112">限制</span><span class="sxs-lookup"><span data-stu-id="663ba-112">Limitations</span></span>
1. <span data-ttu-id="663ba-113">此 API 的速率限制為每分鐘50個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="663ba-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="663ba-114">權限</span><span class="sxs-lookup"><span data-stu-id="663ba-114">Permissions</span></span>

<span data-ttu-id="663ba-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="663ba-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="663ba-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="663ba-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="663ba-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="663ba-117">Permission type</span></span> | <span data-ttu-id="663ba-118">權限</span><span class="sxs-lookup"><span data-stu-id="663ba-118">Permission</span></span> | <span data-ttu-id="663ba-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="663ba-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="663ba-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="663ba-120">Application</span></span> |<span data-ttu-id="663ba-121">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="663ba-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="663ba-122">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="663ba-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="663ba-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="663ba-123">Delegated (work or school account)</span></span> | <span data-ttu-id="663ba-124">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="663ba-124">Vulnerability.Read</span></span> | <span data-ttu-id="663ba-125">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="663ba-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="663ba-126">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="663ba-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="663ba-127">要求標頭</span><span class="sxs-lookup"><span data-stu-id="663ba-127">Request headers</span></span>

<span data-ttu-id="663ba-128">名稱</span><span class="sxs-lookup"><span data-stu-id="663ba-128">Name</span></span> | <span data-ttu-id="663ba-129">類型</span><span class="sxs-lookup"><span data-stu-id="663ba-129">Type</span></span> | <span data-ttu-id="663ba-130">說明</span><span class="sxs-lookup"><span data-stu-id="663ba-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="663ba-131">授權</span><span class="sxs-lookup"><span data-stu-id="663ba-131">Authorization</span></span> | <span data-ttu-id="663ba-132">字串</span><span class="sxs-lookup"><span data-stu-id="663ba-132">String</span></span> | <span data-ttu-id="663ba-133">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="663ba-133">Bearer {token}.</span></span> <span data-ttu-id="663ba-134">**必要**。</span><span class="sxs-lookup"><span data-stu-id="663ba-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="663ba-135">要求內文</span><span class="sxs-lookup"><span data-stu-id="663ba-135">Request body</span></span>

<span data-ttu-id="663ba-136">空白</span><span class="sxs-lookup"><span data-stu-id="663ba-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="663ba-137">回應</span><span class="sxs-lookup"><span data-stu-id="663ba-137">Response</span></span>

<span data-ttu-id="663ba-138">如果成功，這個方法會傳回200，並顯示本文中所發現的弱點資訊。</span><span class="sxs-lookup"><span data-stu-id="663ba-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="663ba-139">範例</span><span class="sxs-lookup"><span data-stu-id="663ba-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="663ba-140">請求</span><span class="sxs-lookup"><span data-stu-id="663ba-140">Request</span></span>

<span data-ttu-id="663ba-141">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="663ba-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="663ba-142">回應</span><span class="sxs-lookup"><span data-stu-id="663ba-142">Response</span></span>

<span data-ttu-id="663ba-143">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="663ba-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="663ba-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="663ba-144">See also</span></span>

- [<span data-ttu-id="663ba-145">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="663ba-145">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="663ba-146">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="663ba-146">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
