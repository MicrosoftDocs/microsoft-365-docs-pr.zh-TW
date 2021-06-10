---
title: 取得裝置安全分數
description: 會檢索組織裝置安全分數。
keywords: api、graph api、支援的 api、get、警示、最近
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
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772302"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="9d790-104">取得裝置安全分數</span><span class="sxs-lookup"><span data-stu-id="9d790-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d790-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9d790-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d790-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9d790-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d790-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d790-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9d790-108">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9d790-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9d790-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="9d790-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9d790-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9d790-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="9d790-111">會 [為裝置檢索您的 Microsoft 安全分數](tvm-microsoft-secure-score-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9d790-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="9d790-112">針對裝置的 Microsoft 安全分數較高表示您的端點對 cybersecurity 威脅攻擊的彈性程度較高。</span><span class="sxs-lookup"><span data-stu-id="9d790-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="9d790-113">權限</span><span class="sxs-lookup"><span data-stu-id="9d790-113">Permissions</span></span>

<span data-ttu-id="9d790-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="9d790-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9d790-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d790-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="9d790-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="9d790-116">Permission type</span></span> |   <span data-ttu-id="9d790-117">權限</span><span class="sxs-lookup"><span data-stu-id="9d790-117">Permission</span></span>  |   <span data-ttu-id="9d790-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="9d790-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9d790-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="9d790-119">Application</span></span> |   <span data-ttu-id="9d790-120">Alll</span><span class="sxs-lookup"><span data-stu-id="9d790-120">Score.Read.Alll</span></span> |   <span data-ttu-id="9d790-121">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="9d790-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="9d790-122">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="9d790-122">Delegated (work or school account)</span></span> | <span data-ttu-id="9d790-123">讀取</span><span class="sxs-lookup"><span data-stu-id="9d790-123">Score.Read</span></span> | <span data-ttu-id="9d790-124">「讀取威脅和弱點管理得分」</span><span class="sxs-lookup"><span data-stu-id="9d790-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="9d790-125">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9d790-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="9d790-126">要求標頭</span><span class="sxs-lookup"><span data-stu-id="9d790-126">Request headers</span></span>

<span data-ttu-id="9d790-127">名稱</span><span class="sxs-lookup"><span data-stu-id="9d790-127">Name</span></span> | <span data-ttu-id="9d790-128">類型</span><span class="sxs-lookup"><span data-stu-id="9d790-128">Type</span></span> | <span data-ttu-id="9d790-129">描述</span><span class="sxs-lookup"><span data-stu-id="9d790-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="9d790-130">授權</span><span class="sxs-lookup"><span data-stu-id="9d790-130">Authorization</span></span> | <span data-ttu-id="9d790-131">字串</span><span class="sxs-lookup"><span data-stu-id="9d790-131">String</span></span> | <span data-ttu-id="9d790-132">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="9d790-132">Bearer {token}.</span></span> <span data-ttu-id="9d790-133">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="9d790-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9d790-134">要求正文</span><span class="sxs-lookup"><span data-stu-id="9d790-134">Request body</span></span>

<span data-ttu-id="9d790-135">空白</span><span class="sxs-lookup"><span data-stu-id="9d790-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9d790-136">回應</span><span class="sxs-lookup"><span data-stu-id="9d790-136">Response</span></span>

<span data-ttu-id="9d790-137">如果成功，這個方法會傳回 200 OK，並提供回應內文中的裝置安全分數資料。</span><span class="sxs-lookup"><span data-stu-id="9d790-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="9d790-138">範例</span><span class="sxs-lookup"><span data-stu-id="9d790-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="9d790-139">請求</span><span class="sxs-lookup"><span data-stu-id="9d790-139">Request</span></span>

<span data-ttu-id="9d790-140">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="9d790-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="9d790-141">回應</span><span class="sxs-lookup"><span data-stu-id="9d790-141">Response</span></span>

<span data-ttu-id="9d790-142">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="9d790-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="9d790-143">在這裡顯示的回應清單可能會因簡潔而截斷。</span><span class="sxs-lookup"><span data-stu-id="9d790-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="9d790-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d790-144">See also</span></span>

- [<span data-ttu-id="9d790-145">使用 Microsoft Defender for Endpoint OData 查詢</span><span class="sxs-lookup"><span data-stu-id="9d790-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
