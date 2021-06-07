---
title: 列出軟體版本發佈
description: 檢索您組織的軟體發行版本本清單
keywords: api，graph api，支援的 api，get，軟體版本發佈，Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772119"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="fd2cb-104">列出軟體版本發佈</span><span class="sxs-lookup"><span data-stu-id="fd2cb-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd2cb-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="fd2cb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="fd2cb-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="fd2cb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fd2cb-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="fd2cb-108">會檢索您組織的軟體發行版本本清單。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="fd2cb-109">權限</span><span class="sxs-lookup"><span data-stu-id="fd2cb-109">Permissions</span></span>
<span data-ttu-id="fd2cb-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fd2cb-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="fd2cb-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="fd2cb-112">Permission type</span></span> |   <span data-ttu-id="fd2cb-113">權限</span><span class="sxs-lookup"><span data-stu-id="fd2cb-113">Permission</span></span>  |   <span data-ttu-id="fd2cb-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="fd2cb-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fd2cb-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="fd2cb-115">Application</span></span> | <span data-ttu-id="fd2cb-116">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="fd2cb-116">Software.Read.All</span></span> | <span data-ttu-id="fd2cb-117">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="fd2cb-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="fd2cb-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="fd2cb-118">Delegated (work or school account)</span></span> | <span data-ttu-id="fd2cb-119">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="fd2cb-119">Software.Read</span></span> | <span data-ttu-id="fd2cb-120">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="fd2cb-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="fd2cb-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="fd2cb-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="fd2cb-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="fd2cb-122">Request headers</span></span>

| <span data-ttu-id="fd2cb-123">名稱</span><span class="sxs-lookup"><span data-stu-id="fd2cb-123">Name</span></span>        | <span data-ttu-id="fd2cb-124">類型</span><span class="sxs-lookup"><span data-stu-id="fd2cb-124">Type</span></span> | <span data-ttu-id="fd2cb-125">描述</span><span class="sxs-lookup"><span data-stu-id="fd2cb-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="fd2cb-126">授權</span><span class="sxs-lookup"><span data-stu-id="fd2cb-126">Authorization</span></span> | <span data-ttu-id="fd2cb-127">字串</span><span class="sxs-lookup"><span data-stu-id="fd2cb-127">String</span></span> | <span data-ttu-id="fd2cb-128">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fd2cb-129">要求正文</span><span class="sxs-lookup"><span data-stu-id="fd2cb-129">Request body</span></span>
<span data-ttu-id="fd2cb-130">空白</span><span class="sxs-lookup"><span data-stu-id="fd2cb-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fd2cb-131">回應</span><span class="sxs-lookup"><span data-stu-id="fd2cb-131">Response</span></span>
<span data-ttu-id="fd2cb-132">如果成功，這個方法會傳回 200 OK，包含本文中的軟體發行資料清單。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="fd2cb-133">範例</span><span class="sxs-lookup"><span data-stu-id="fd2cb-133">Example</span></span>

<span data-ttu-id="fd2cb-134">**請求**</span><span class="sxs-lookup"><span data-stu-id="fd2cb-134">**Request**</span></span>

<span data-ttu-id="fd2cb-135">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="fd2cb-136">**回應**</span><span class="sxs-lookup"><span data-stu-id="fd2cb-136">**Response**</span></span>

<span data-ttu-id="fd2cb-137">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="fd2cb-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="fd2cb-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="fd2cb-138">Related topics</span></span>
- [<span data-ttu-id="fd2cb-139">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="fd2cb-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="fd2cb-140">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="fd2cb-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
