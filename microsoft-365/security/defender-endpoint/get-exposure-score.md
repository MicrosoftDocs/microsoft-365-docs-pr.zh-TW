---
title: 取得暴險分數
description: 會檢索組織公開分數。
keywords: api、graph api、支援的 api、get、洩密分數、組織公開分數
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
ms.openlocfilehash: 9da87dcb64f8c62966382e3a2888f03c49149a09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770423"
---
# <a name="get-exposure-score"></a><span data-ttu-id="66793-104">取得暴險分數</span><span class="sxs-lookup"><span data-stu-id="66793-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66793-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="66793-105">**Applies to:**</span></span>
- [<span data-ttu-id="66793-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="66793-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="66793-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66793-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="66793-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="66793-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="66793-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="66793-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="66793-110">會檢索組織公開分數。</span><span class="sxs-lookup"><span data-stu-id="66793-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="66793-111">權限</span><span class="sxs-lookup"><span data-stu-id="66793-111">Permissions</span></span>

<span data-ttu-id="66793-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="66793-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="66793-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="66793-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="66793-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="66793-114">Permission type</span></span> | <span data-ttu-id="66793-115">權限</span><span class="sxs-lookup"><span data-stu-id="66793-115">Permission</span></span> | <span data-ttu-id="66793-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="66793-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="66793-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="66793-117">Application</span></span> | <span data-ttu-id="66793-118">Read。所有</span><span class="sxs-lookup"><span data-stu-id="66793-118">Score.Read.All</span></span> | <span data-ttu-id="66793-119">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="66793-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="66793-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="66793-120">Delegated (work or school account)</span></span> | <span data-ttu-id="66793-121">讀取</span><span class="sxs-lookup"><span data-stu-id="66793-121">Score.Read</span></span> | <span data-ttu-id="66793-122">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="66793-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="66793-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="66793-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="66793-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="66793-124">Request headers</span></span>

<span data-ttu-id="66793-125">名稱</span><span class="sxs-lookup"><span data-stu-id="66793-125">Name</span></span> | <span data-ttu-id="66793-126">類型</span><span class="sxs-lookup"><span data-stu-id="66793-126">Type</span></span> | <span data-ttu-id="66793-127">描述</span><span class="sxs-lookup"><span data-stu-id="66793-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="66793-128">授權</span><span class="sxs-lookup"><span data-stu-id="66793-128">Authorization</span></span> | <span data-ttu-id="66793-129">字串</span><span class="sxs-lookup"><span data-stu-id="66793-129">String</span></span> | <span data-ttu-id="66793-130">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="66793-130">Bearer {token}.</span></span> <span data-ttu-id="66793-131">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="66793-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="66793-132">要求正文</span><span class="sxs-lookup"><span data-stu-id="66793-132">Request body</span></span>

<span data-ttu-id="66793-133">空白</span><span class="sxs-lookup"><span data-stu-id="66793-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="66793-134">回應</span><span class="sxs-lookup"><span data-stu-id="66793-134">Response</span></span>

<span data-ttu-id="66793-135">如果成功，這個方法會傳回 200 OK，並在回應內文中包含曝光資料。</span><span class="sxs-lookup"><span data-stu-id="66793-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="66793-136">範例</span><span class="sxs-lookup"><span data-stu-id="66793-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="66793-137">請求</span><span class="sxs-lookup"><span data-stu-id="66793-137">Request</span></span>

<span data-ttu-id="66793-138">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="66793-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="66793-139">回應</span><span class="sxs-lookup"><span data-stu-id="66793-139">Response</span></span>

<span data-ttu-id="66793-140">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="66793-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="66793-141">在這裡顯示的回應清單可能會因簡潔而截斷。</span><span class="sxs-lookup"><span data-stu-id="66793-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="66793-142">請參閱</span><span class="sxs-lookup"><span data-stu-id="66793-142">See also</span></span>

- [<span data-ttu-id="66793-143">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="66793-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="66793-144">威脅 & 漏洞洩密分數</span><span class="sxs-lookup"><span data-stu-id="66793-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
