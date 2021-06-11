---
title: 依建議列出裝置
description: 會檢索與安全性建議相關聯的裝置清單。
keywords: api、graph api、支援的 api、get、security 威脅與弱點管理 for a 威脅與弱點管理 api 的漏洞
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
ms.openlocfilehash: a321a3aec9bbd0e7e405b82b7cbd56cf214694ca
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845190"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="4938a-104">依建議列出裝置</span><span class="sxs-lookup"><span data-stu-id="4938a-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4938a-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4938a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="4938a-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4938a-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4938a-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4938a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4938a-108">會檢索與安全性建議相關聯的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="4938a-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="4938a-109">權限</span><span class="sxs-lookup"><span data-stu-id="4938a-109">Permissions</span></span>
<span data-ttu-id="4938a-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="4938a-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4938a-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4938a-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4938a-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="4938a-112">Permission type</span></span> |   <span data-ttu-id="4938a-113">權限</span><span class="sxs-lookup"><span data-stu-id="4938a-113">Permission</span></span>  |   <span data-ttu-id="4938a-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="4938a-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4938a-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="4938a-115">Application</span></span> |   <span data-ttu-id="4938a-116">SecurityRecommendation Read。 All</span><span class="sxs-lookup"><span data-stu-id="4938a-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="4938a-117">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="4938a-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="4938a-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="4938a-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4938a-119">SecurityRecommendation 讀取</span><span class="sxs-lookup"><span data-stu-id="4938a-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="4938a-120">「讀取威脅及弱點管理安全性建議資訊」</span><span class="sxs-lookup"><span data-stu-id="4938a-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4938a-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="4938a-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="4938a-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="4938a-122">Request headers</span></span>

<span data-ttu-id="4938a-123">名稱</span><span class="sxs-lookup"><span data-stu-id="4938a-123">Name</span></span> | <span data-ttu-id="4938a-124">類型</span><span class="sxs-lookup"><span data-stu-id="4938a-124">Type</span></span> | <span data-ttu-id="4938a-125">描述</span><span class="sxs-lookup"><span data-stu-id="4938a-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4938a-126">授權</span><span class="sxs-lookup"><span data-stu-id="4938a-126">Authorization</span></span> | <span data-ttu-id="4938a-127">字串</span><span class="sxs-lookup"><span data-stu-id="4938a-127">String</span></span> | <span data-ttu-id="4938a-128">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="4938a-128">Bearer {token}.</span></span> <span data-ttu-id="4938a-129">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="4938a-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4938a-130">要求正文</span><span class="sxs-lookup"><span data-stu-id="4938a-130">Request body</span></span>
<span data-ttu-id="4938a-131">空白</span><span class="sxs-lookup"><span data-stu-id="4938a-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4938a-132">回應</span><span class="sxs-lookup"><span data-stu-id="4938a-132">Response</span></span>
<span data-ttu-id="4938a-133">若成功，這個方法會傳回 200 OK 與安全性建議相關聯的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="4938a-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="4938a-134">範例</span><span class="sxs-lookup"><span data-stu-id="4938a-134">Example</span></span>

<span data-ttu-id="4938a-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="4938a-135">**Request**</span></span>

<span data-ttu-id="4938a-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="4938a-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="4938a-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="4938a-137">**Response**</span></span>

<span data-ttu-id="4938a-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="4938a-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="4938a-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="4938a-139">Related topics</span></span>
- [<span data-ttu-id="4938a-140">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="4938a-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4938a-141">威脅 & 漏洞安全性建議</span><span class="sxs-lookup"><span data-stu-id="4938a-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
