---
title: 依軟體取得建議
description: 會檢索與特定軟體相關的安全性建議。
keywords: api，graph api，支援的 api，get，安全性建議，軟體的安全性建議，威脅和弱點管理，威脅和弱點管理 api
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199498"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="1bb1b-104">依軟體取得建議</span><span class="sxs-lookup"><span data-stu-id="1bb1b-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1bb1b-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1bb1b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1bb1b-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1bb1b-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1bb1b-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1bb1b-108">會檢索與特定軟體相關的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="1bb1b-109">權限</span><span class="sxs-lookup"><span data-stu-id="1bb1b-109">Permissions</span></span>
<span data-ttu-id="1bb1b-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1bb1b-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1bb1b-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="1bb1b-112">Permission type</span></span> |   <span data-ttu-id="1bb1b-113">權限</span><span class="sxs-lookup"><span data-stu-id="1bb1b-113">Permission</span></span>  |   <span data-ttu-id="1bb1b-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="1bb1b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1bb1b-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb1b-115">Application</span></span> |   <span data-ttu-id="1bb1b-116">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="1bb1b-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1bb1b-117">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1bb1b-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1bb1b-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="1bb1b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1bb1b-119">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="1bb1b-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1bb1b-120">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="1bb1b-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1bb1b-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1bb1b-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="1bb1b-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1bb1b-122">Request headers</span></span>

<span data-ttu-id="1bb1b-123">名稱</span><span class="sxs-lookup"><span data-stu-id="1bb1b-123">Name</span></span> | <span data-ttu-id="1bb1b-124">類型</span><span class="sxs-lookup"><span data-stu-id="1bb1b-124">Type</span></span> | <span data-ttu-id="1bb1b-125">描述</span><span class="sxs-lookup"><span data-stu-id="1bb1b-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1bb1b-126">授權</span><span class="sxs-lookup"><span data-stu-id="1bb1b-126">Authorization</span></span> | <span data-ttu-id="1bb1b-127">字串</span><span class="sxs-lookup"><span data-stu-id="1bb1b-127">String</span></span> | <span data-ttu-id="1bb1b-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-128">Bearer {token}.</span></span> <span data-ttu-id="1bb1b-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1bb1b-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="1bb1b-130">Request body</span></span>
<span data-ttu-id="1bb1b-131">空白</span><span class="sxs-lookup"><span data-stu-id="1bb1b-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1bb1b-132">回應</span><span class="sxs-lookup"><span data-stu-id="1bb1b-132">Response</span></span>
<span data-ttu-id="1bb1b-133">若成功，這個方法會傳回 200 OK，與本文中的安全性建議相關聯的軟體。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1bb1b-134">範例</span><span class="sxs-lookup"><span data-stu-id="1bb1b-134">Example</span></span>

<span data-ttu-id="1bb1b-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="1bb1b-135">**Request**</span></span>

<span data-ttu-id="1bb1b-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="1bb1b-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="1bb1b-137">**Response**</span></span>

<span data-ttu-id="1bb1b-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="1bb1b-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="1bb1b-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="1bb1b-139">Related topics</span></span>
- [<span data-ttu-id="1bb1b-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="1bb1b-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1bb1b-141">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="1bb1b-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)