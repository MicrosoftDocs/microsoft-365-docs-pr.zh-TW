---
title: 依設備群組列出曝光排名
description: 依設備群組來檢索曝光分數的清單。
keywords: api、graph api、支援的 api、get、洩密分數、裝置群組、裝置群組暴露分數
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fe4c2d4a4f18a1057472007f21936b4111673849
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166378"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="e7c36-104">依設備群組列出曝光排名</span><span class="sxs-lookup"><span data-stu-id="e7c36-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7c36-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e7c36-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7c36-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7c36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7c36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7c36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7c36-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e7c36-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7c36-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e7c36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e7c36-110">會檢索與特定網域位址相關的警示集合。</span><span class="sxs-lookup"><span data-stu-id="e7c36-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="e7c36-111">權限</span><span class="sxs-lookup"><span data-stu-id="e7c36-111">Permissions</span></span>

<span data-ttu-id="e7c36-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="e7c36-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e7c36-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e7c36-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e7c36-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="e7c36-114">Permission type</span></span> |   <span data-ttu-id="e7c36-115">權限</span><span class="sxs-lookup"><span data-stu-id="e7c36-115">Permission</span></span>  |   <span data-ttu-id="e7c36-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e7c36-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e7c36-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="e7c36-117">Application</span></span> | <span data-ttu-id="e7c36-118">Read。所有</span><span class="sxs-lookup"><span data-stu-id="e7c36-118">Score.Read.All</span></span> | <span data-ttu-id="e7c36-119">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="e7c36-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="e7c36-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="e7c36-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e7c36-121">讀取</span><span class="sxs-lookup"><span data-stu-id="e7c36-121">Score.Read</span></span> | <span data-ttu-id="e7c36-122">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="e7c36-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="e7c36-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e7c36-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="e7c36-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="e7c36-124">Request headers</span></span>

| <span data-ttu-id="e7c36-125">名稱</span><span class="sxs-lookup"><span data-stu-id="e7c36-125">Name</span></span>        | <span data-ttu-id="e7c36-126">類型</span><span class="sxs-lookup"><span data-stu-id="e7c36-126">Type</span></span> | <span data-ttu-id="e7c36-127">描述</span><span class="sxs-lookup"><span data-stu-id="e7c36-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="e7c36-128">授權</span><span class="sxs-lookup"><span data-stu-id="e7c36-128">Authorization</span></span> | <span data-ttu-id="e7c36-129">字串</span><span class="sxs-lookup"><span data-stu-id="e7c36-129">String</span></span> | <span data-ttu-id="e7c36-130">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="e7c36-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e7c36-131">要求正文</span><span class="sxs-lookup"><span data-stu-id="e7c36-131">Request body</span></span>

<span data-ttu-id="e7c36-132">空白</span><span class="sxs-lookup"><span data-stu-id="e7c36-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e7c36-133">回應</span><span class="sxs-lookup"><span data-stu-id="e7c36-133">Response</span></span>

<span data-ttu-id="e7c36-134">如果成功，這個方法會傳回 200 OK，顯示回應內文中每個裝置群組資料的暴露分數清單。</span><span class="sxs-lookup"><span data-stu-id="e7c36-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="e7c36-135">範例</span><span class="sxs-lookup"><span data-stu-id="e7c36-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="e7c36-136">請求</span><span class="sxs-lookup"><span data-stu-id="e7c36-136">Request</span></span>

<span data-ttu-id="e7c36-137">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="e7c36-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="e7c36-138">回應</span><span class="sxs-lookup"><span data-stu-id="e7c36-138">Response</span></span>

<span data-ttu-id="e7c36-139">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="e7c36-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="e7c36-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7c36-140">Related topics</span></span>

- [<span data-ttu-id="e7c36-141">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="e7c36-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e7c36-142">威脅 & 漏洞洩密分數</span><span class="sxs-lookup"><span data-stu-id="e7c36-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
