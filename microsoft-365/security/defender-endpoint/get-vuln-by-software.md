---
title: 列出軟體的弱點
description: 在已安裝的軟體中取得漏洞清單。
keywords: api、graph api、支援的 api、get、弱點清單、Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769914"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="eae4d-104">列出軟體的弱點</span><span class="sxs-lookup"><span data-stu-id="eae4d-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eae4d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="eae4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="eae4d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eae4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eae4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eae4d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eae4d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="eae4d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eae4d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="eae4d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="eae4d-110">在已安裝的軟體中取得漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="eae4d-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="eae4d-111">權限</span><span class="sxs-lookup"><span data-stu-id="eae4d-111">Permissions</span></span>
<span data-ttu-id="eae4d-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="eae4d-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eae4d-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eae4d-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="eae4d-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="eae4d-114">Permission type</span></span> |   <span data-ttu-id="eae4d-115">權限</span><span class="sxs-lookup"><span data-stu-id="eae4d-115">Permission</span></span>  |   <span data-ttu-id="eae4d-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="eae4d-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eae4d-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="eae4d-117">Application</span></span> | <span data-ttu-id="eae4d-118">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="eae4d-118">Software.Read.All</span></span> | <span data-ttu-id="eae4d-119">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="eae4d-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="eae4d-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="eae4d-120">Delegated (work or school account)</span></span> | <span data-ttu-id="eae4d-121">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="eae4d-121">Software.Read</span></span> | <span data-ttu-id="eae4d-122">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="eae4d-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="eae4d-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="eae4d-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="eae4d-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="eae4d-124">Request headers</span></span>

| <span data-ttu-id="eae4d-125">名稱</span><span class="sxs-lookup"><span data-stu-id="eae4d-125">Name</span></span>        | <span data-ttu-id="eae4d-126">類型</span><span class="sxs-lookup"><span data-stu-id="eae4d-126">Type</span></span> | <span data-ttu-id="eae4d-127">描述</span><span class="sxs-lookup"><span data-stu-id="eae4d-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="eae4d-128">授權</span><span class="sxs-lookup"><span data-stu-id="eae4d-128">Authorization</span></span> | <span data-ttu-id="eae4d-129">字串</span><span class="sxs-lookup"><span data-stu-id="eae4d-129">String</span></span> | <span data-ttu-id="eae4d-130">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="eae4d-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="eae4d-131">要求正文</span><span class="sxs-lookup"><span data-stu-id="eae4d-131">Request body</span></span>
<span data-ttu-id="eae4d-132">空白</span><span class="sxs-lookup"><span data-stu-id="eae4d-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eae4d-133">回應</span><span class="sxs-lookup"><span data-stu-id="eae4d-133">Response</span></span>
<span data-ttu-id="eae4d-134">若成功，這個方法會傳回 200 OK，包含指定軟體所公開的漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="eae4d-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="eae4d-135">範例</span><span class="sxs-lookup"><span data-stu-id="eae4d-135">Example</span></span>

<span data-ttu-id="eae4d-136">**請求**</span><span class="sxs-lookup"><span data-stu-id="eae4d-136">**Request**</span></span>

<span data-ttu-id="eae4d-137">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="eae4d-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="eae4d-138">**回應**</span><span class="sxs-lookup"><span data-stu-id="eae4d-138">**Response**</span></span>

<span data-ttu-id="eae4d-139">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="eae4d-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

