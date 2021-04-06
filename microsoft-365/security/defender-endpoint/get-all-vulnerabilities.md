---
title: 取得所有漏洞
description: 檢索影響組織的所有安全性漏洞清單
keywords: api、graph api、支援的 api、get、弱點資訊、mdatp tvm api
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
ms.openlocfilehash: c97b70b682351e5ad9d92435068b97622032f769
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166401"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="f395a-104">列出弱點</span><span class="sxs-lookup"><span data-stu-id="f395a-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f395a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f395a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f395a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f395a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f395a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f395a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f395a-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f395a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f395a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f395a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f395a-110">會檢索影響組織的所有安全性漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="f395a-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="f395a-111">權限</span><span class="sxs-lookup"><span data-stu-id="f395a-111">Permissions</span></span>
<span data-ttu-id="f395a-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="f395a-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f395a-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f395a-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f395a-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="f395a-114">Permission type</span></span> |   <span data-ttu-id="f395a-115">權限</span><span class="sxs-lookup"><span data-stu-id="f395a-115">Permission</span></span>  |   <span data-ttu-id="f395a-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f395a-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f395a-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="f395a-117">Application</span></span> |   <span data-ttu-id="f395a-118">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="f395a-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="f395a-119">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="f395a-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="f395a-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="f395a-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f395a-121">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="f395a-121">Vulnerability.Read</span></span> |   <span data-ttu-id="f395a-122">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="f395a-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f395a-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f395a-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f395a-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="f395a-124">Request headers</span></span>

<span data-ttu-id="f395a-125">名稱</span><span class="sxs-lookup"><span data-stu-id="f395a-125">Name</span></span> | <span data-ttu-id="f395a-126">類型</span><span class="sxs-lookup"><span data-stu-id="f395a-126">Type</span></span> | <span data-ttu-id="f395a-127">描述</span><span class="sxs-lookup"><span data-stu-id="f395a-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f395a-128">授權</span><span class="sxs-lookup"><span data-stu-id="f395a-128">Authorization</span></span> | <span data-ttu-id="f395a-129">字串</span><span class="sxs-lookup"><span data-stu-id="f395a-129">String</span></span> | <span data-ttu-id="f395a-130">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="f395a-130">Bearer {token}.</span></span> <span data-ttu-id="f395a-131">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="f395a-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f395a-132">要求正文</span><span class="sxs-lookup"><span data-stu-id="f395a-132">Request body</span></span>
<span data-ttu-id="f395a-133">空白</span><span class="sxs-lookup"><span data-stu-id="f395a-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f395a-134">回應</span><span class="sxs-lookup"><span data-stu-id="f395a-134">Response</span></span>
<span data-ttu-id="f395a-135">如果成功，這個方法會傳回200的 [確定] 清單中的漏洞。</span><span class="sxs-lookup"><span data-stu-id="f395a-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f395a-136">範例</span><span class="sxs-lookup"><span data-stu-id="f395a-136">Example</span></span>

<span data-ttu-id="f395a-137">**請求**</span><span class="sxs-lookup"><span data-stu-id="f395a-137">**Request**</span></span>

<span data-ttu-id="f395a-138">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="f395a-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="f395a-139">**回應**</span><span class="sxs-lookup"><span data-stu-id="f395a-139">**Response**</span></span>

<span data-ttu-id="f395a-140">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="f395a-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="f395a-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f395a-141">See also</span></span>
- [<span data-ttu-id="f395a-142">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="f395a-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f395a-143">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="f395a-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)