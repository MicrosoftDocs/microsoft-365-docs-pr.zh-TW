---
title: 根據建議列出弱點
description: 會檢索與安全性建議相關的漏洞清單。
keywords: api、graph api、支援的 api、get、隱患清單、安全性建議、弱點的安全性建議、威脅與弱點管理威脅與弱點管理 api
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845147"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="ffc62-104">根據建議列出弱點</span><span class="sxs-lookup"><span data-stu-id="ffc62-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffc62-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ffc62-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="ffc62-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ffc62-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ffc62-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ffc62-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ffc62-108">會檢索與安全性建議相關的漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="ffc62-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="ffc62-109">權限</span><span class="sxs-lookup"><span data-stu-id="ffc62-109">Permissions</span></span>
<span data-ttu-id="ffc62-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="ffc62-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ffc62-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ffc62-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ffc62-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ffc62-112">Permission type</span></span> |   <span data-ttu-id="ffc62-113">權限</span><span class="sxs-lookup"><span data-stu-id="ffc62-113">Permission</span></span>  |   <span data-ttu-id="ffc62-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ffc62-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ffc62-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="ffc62-115">Application</span></span> |   <span data-ttu-id="ffc62-116">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="ffc62-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="ffc62-117">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="ffc62-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="ffc62-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ffc62-118">Delegated (work or school account)</span></span> | <span data-ttu-id="ffc62-119">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="ffc62-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="ffc62-120">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="ffc62-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ffc62-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ffc62-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="ffc62-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ffc62-122">Request headers</span></span>

<span data-ttu-id="ffc62-123">名稱</span><span class="sxs-lookup"><span data-stu-id="ffc62-123">Name</span></span> | <span data-ttu-id="ffc62-124">類型</span><span class="sxs-lookup"><span data-stu-id="ffc62-124">Type</span></span> | <span data-ttu-id="ffc62-125">描述</span><span class="sxs-lookup"><span data-stu-id="ffc62-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="ffc62-126">授權</span><span class="sxs-lookup"><span data-stu-id="ffc62-126">Authorization</span></span> | <span data-ttu-id="ffc62-127">字串</span><span class="sxs-lookup"><span data-stu-id="ffc62-127">String</span></span> | <span data-ttu-id="ffc62-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="ffc62-128">Bearer {token}.</span></span> <span data-ttu-id="ffc62-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="ffc62-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ffc62-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="ffc62-130">Request body</span></span>
<span data-ttu-id="ffc62-131">空白</span><span class="sxs-lookup"><span data-stu-id="ffc62-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ffc62-132">回應</span><span class="sxs-lookup"><span data-stu-id="ffc62-132">Response</span></span>
<span data-ttu-id="ffc62-133">若成功，這個方法會傳回 200 OK，並顯示與安全性建議相關的安全性漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="ffc62-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="ffc62-134">範例</span><span class="sxs-lookup"><span data-stu-id="ffc62-134">Example</span></span>

<span data-ttu-id="ffc62-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="ffc62-135">**Request**</span></span>

<span data-ttu-id="ffc62-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="ffc62-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="ffc62-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="ffc62-137">**Response**</span></span>

<span data-ttu-id="ffc62-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="ffc62-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="ffc62-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="ffc62-139">Related topics</span></span>
- [<span data-ttu-id="ffc62-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="ffc62-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ffc62-141">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="ffc62-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
