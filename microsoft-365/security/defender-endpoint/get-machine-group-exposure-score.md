---
title: 依設備群組列出曝光排名
description: 依設備群組來檢索曝光分數的清單。
keywords: api、graph api、支援的 api、get、洩密分數、裝置群組、裝置群組暴露分數
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: a7f343db64174fe3c48eaf8b584b03b53921edcb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843611"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="ff419-104">依設備群組列出曝光排名</span><span class="sxs-lookup"><span data-stu-id="ff419-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff419-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ff419-105">**Applies to:**</span></span>
- [<span data-ttu-id="ff419-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ff419-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ff419-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff419-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ff419-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ff419-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ff419-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ff419-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ff419-110">會檢索與特定網域位址相關的警示集合。</span><span class="sxs-lookup"><span data-stu-id="ff419-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="ff419-111">權限</span><span class="sxs-lookup"><span data-stu-id="ff419-111">Permissions</span></span>

<span data-ttu-id="ff419-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="ff419-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ff419-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ff419-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ff419-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ff419-114">Permission type</span></span> |   <span data-ttu-id="ff419-115">權限</span><span class="sxs-lookup"><span data-stu-id="ff419-115">Permission</span></span>  |   <span data-ttu-id="ff419-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ff419-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ff419-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="ff419-117">Application</span></span> | <span data-ttu-id="ff419-118">Read。所有</span><span class="sxs-lookup"><span data-stu-id="ff419-118">Score.Read.All</span></span> | <span data-ttu-id="ff419-119">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="ff419-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="ff419-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ff419-120">Delegated (work or school account)</span></span> | <span data-ttu-id="ff419-121">讀取</span><span class="sxs-lookup"><span data-stu-id="ff419-121">Score.Read</span></span> | <span data-ttu-id="ff419-122">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="ff419-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="ff419-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ff419-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="ff419-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ff419-124">Request headers</span></span>

| <span data-ttu-id="ff419-125">名稱</span><span class="sxs-lookup"><span data-stu-id="ff419-125">Name</span></span>        | <span data-ttu-id="ff419-126">類型</span><span class="sxs-lookup"><span data-stu-id="ff419-126">Type</span></span> | <span data-ttu-id="ff419-127">描述</span><span class="sxs-lookup"><span data-stu-id="ff419-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="ff419-128">授權</span><span class="sxs-lookup"><span data-stu-id="ff419-128">Authorization</span></span> | <span data-ttu-id="ff419-129">字串</span><span class="sxs-lookup"><span data-stu-id="ff419-129">String</span></span> | <span data-ttu-id="ff419-130">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="ff419-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ff419-131">要求正文</span><span class="sxs-lookup"><span data-stu-id="ff419-131">Request body</span></span>

<span data-ttu-id="ff419-132">空白</span><span class="sxs-lookup"><span data-stu-id="ff419-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ff419-133">回應</span><span class="sxs-lookup"><span data-stu-id="ff419-133">Response</span></span>

<span data-ttu-id="ff419-134">如果成功，這個方法會傳回 200 OK，顯示回應內文中每個裝置群組資料的暴露分數清單。</span><span class="sxs-lookup"><span data-stu-id="ff419-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="ff419-135">範例</span><span class="sxs-lookup"><span data-stu-id="ff419-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="ff419-136">請求</span><span class="sxs-lookup"><span data-stu-id="ff419-136">Request</span></span>

<span data-ttu-id="ff419-137">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="ff419-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="ff419-138">回應</span><span class="sxs-lookup"><span data-stu-id="ff419-138">Response</span></span>

<span data-ttu-id="ff419-139">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="ff419-139">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="ff419-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="ff419-140">Related topics</span></span>

- [<span data-ttu-id="ff419-141">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="ff419-141">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ff419-142">威脅 & 漏洞洩密分數</span><span class="sxs-lookup"><span data-stu-id="ff419-142">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
