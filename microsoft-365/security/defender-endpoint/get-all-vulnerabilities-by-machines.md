---
title: 依機器和軟體取得所有的隱患
description: 根據機器及軟體，檢索影響組織的所有安全性漏洞清單。
keywords: api、graph api、支援的 api、get、弱點資訊、Microsoft Defender for Endpoint tvm api
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
ms.technology: mde
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933406"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="67c9f-104">列出電腦和軟體的弱點</span><span class="sxs-lookup"><span data-stu-id="67c9f-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67c9f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="67c9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="67c9f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67c9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67c9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67c9f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67c9f-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="67c9f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67c9f-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="67c9f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="67c9f-110">會檢索影響每個 [機器](machine.md) 及 [軟體](software.md)之組織的所有安全性漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="67c9f-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="67c9f-111">如果此弱點已修復 KB，它就會出現在回應中。</span><span class="sxs-lookup"><span data-stu-id="67c9f-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="67c9f-112">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="67c9f-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="67c9f-113">```$filter```所有屬性都支援 OData。</span><span class="sxs-lookup"><span data-stu-id="67c9f-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="67c9f-114">這是 [POWER BI 整合](api-power-bi.md)的理想 API。</span><span class="sxs-lookup"><span data-stu-id="67c9f-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="67c9f-115">權限</span><span class="sxs-lookup"><span data-stu-id="67c9f-115">Permissions</span></span>
<span data-ttu-id="67c9f-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="67c9f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="67c9f-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="67c9f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="67c9f-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="67c9f-118">Permission type</span></span> |   <span data-ttu-id="67c9f-119">權限</span><span class="sxs-lookup"><span data-stu-id="67c9f-119">Permission</span></span>  |   <span data-ttu-id="67c9f-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="67c9f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="67c9f-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="67c9f-121">Application</span></span> |   <span data-ttu-id="67c9f-122">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="67c9f-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="67c9f-123">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="67c9f-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="67c9f-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="67c9f-124">Delegated (work or school account)</span></span> | <span data-ttu-id="67c9f-125">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="67c9f-125">Vulnerability.Read</span></span> |   <span data-ttu-id="67c9f-126">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="67c9f-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="67c9f-127">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="67c9f-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="67c9f-128">要求標頭</span><span class="sxs-lookup"><span data-stu-id="67c9f-128">Request headers</span></span>

<span data-ttu-id="67c9f-129">名稱</span><span class="sxs-lookup"><span data-stu-id="67c9f-129">Name</span></span> | <span data-ttu-id="67c9f-130">類型</span><span class="sxs-lookup"><span data-stu-id="67c9f-130">Type</span></span> | <span data-ttu-id="67c9f-131">描述</span><span class="sxs-lookup"><span data-stu-id="67c9f-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="67c9f-132">授權</span><span class="sxs-lookup"><span data-stu-id="67c9f-132">Authorization</span></span> | <span data-ttu-id="67c9f-133">字串</span><span class="sxs-lookup"><span data-stu-id="67c9f-133">String</span></span> | <span data-ttu-id="67c9f-134">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="67c9f-134">Bearer {token}.</span></span> <span data-ttu-id="67c9f-135">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="67c9f-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="67c9f-136">要求正文</span><span class="sxs-lookup"><span data-stu-id="67c9f-136">Request body</span></span>
<span data-ttu-id="67c9f-137">空白</span><span class="sxs-lookup"><span data-stu-id="67c9f-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="67c9f-138">回應</span><span class="sxs-lookup"><span data-stu-id="67c9f-138">Response</span></span>
<span data-ttu-id="67c9f-139">如果成功，這個方法會傳回200的 [確定] 清單中的漏洞。</span><span class="sxs-lookup"><span data-stu-id="67c9f-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="67c9f-140">範例</span><span class="sxs-lookup"><span data-stu-id="67c9f-140">Example</span></span>

<span data-ttu-id="67c9f-141">**請求**</span><span class="sxs-lookup"><span data-stu-id="67c9f-141">**Request**</span></span>

<span data-ttu-id="67c9f-142">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="67c9f-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="67c9f-143">**回應**</span><span class="sxs-lookup"><span data-stu-id="67c9f-143">**Response**</span></span>

<span data-ttu-id="67c9f-144">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="67c9f-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="67c9f-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="67c9f-145">See also</span></span>

- [<span data-ttu-id="67c9f-146">風險威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="67c9f-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="67c9f-147">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="67c9f-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
