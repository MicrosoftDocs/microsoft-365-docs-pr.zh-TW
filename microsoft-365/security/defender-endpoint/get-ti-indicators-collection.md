---
title: 清單指示器 API
description: 瞭解如何使用清單指標 API，在 Microsoft Defender for Endpoint 中取得所有作用中指示器的集合。
keywords: api，public api，支援的 api，標記集合
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198550"
---
# <a name="list-indicators-api"></a><span data-ttu-id="3ca24-104">清單指示器 API</span><span class="sxs-lookup"><span data-stu-id="3ca24-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ca24-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3ca24-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3ca24-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3ca24-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ca24-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3ca24-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3ca24-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="3ca24-108">API description</span></span>
<span data-ttu-id="3ca24-109">會檢索 [所有現用指標](ti-indicator.md)的集合。</span><span class="sxs-lookup"><span data-stu-id="3ca24-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="3ca24-110">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="3ca24-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="3ca24-111">支援 OData 的 ```$filter``` 查詢：、、、 ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` 和 ```severity``` 屬性。</span><span class="sxs-lookup"><span data-stu-id="3ca24-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="3ca24-112">請參閱[使用 Microsoft Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中的範例</span><span class="sxs-lookup"><span data-stu-id="3ca24-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="3ca24-113">限制</span><span class="sxs-lookup"><span data-stu-id="3ca24-113">Limitations</span></span>
1. <span data-ttu-id="3ca24-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3ca24-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3ca24-115">權限</span><span class="sxs-lookup"><span data-stu-id="3ca24-115">Permissions</span></span>
<span data-ttu-id="3ca24-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3ca24-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3ca24-117">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3ca24-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="3ca24-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3ca24-118">Permission type</span></span> |   <span data-ttu-id="3ca24-119">權限</span><span class="sxs-lookup"><span data-stu-id="3ca24-119">Permission</span></span>  |   <span data-ttu-id="3ca24-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3ca24-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3ca24-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="3ca24-121">Application</span></span> |   <span data-ttu-id="3ca24-122">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3ca24-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="3ca24-123">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="3ca24-123">'Read and write Indicators'</span></span>
<span data-ttu-id="3ca24-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="3ca24-124">Application</span></span> |   <span data-ttu-id="3ca24-125">Ti ReadWrite 所有</span><span class="sxs-lookup"><span data-stu-id="3ca24-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="3ca24-126">「讀取及寫入所有指示器」</span><span class="sxs-lookup"><span data-stu-id="3ca24-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="3ca24-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3ca24-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="3ca24-128">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3ca24-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="3ca24-129">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="3ca24-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="3ca24-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3ca24-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="3ca24-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3ca24-131">Request headers</span></span>

<span data-ttu-id="3ca24-132">名稱</span><span class="sxs-lookup"><span data-stu-id="3ca24-132">Name</span></span> | <span data-ttu-id="3ca24-133">類型</span><span class="sxs-lookup"><span data-stu-id="3ca24-133">Type</span></span> | <span data-ttu-id="3ca24-134">描述</span><span class="sxs-lookup"><span data-stu-id="3ca24-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3ca24-135">授權</span><span class="sxs-lookup"><span data-stu-id="3ca24-135">Authorization</span></span> | <span data-ttu-id="3ca24-136">字串</span><span class="sxs-lookup"><span data-stu-id="3ca24-136">String</span></span> | <span data-ttu-id="3ca24-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3ca24-137">Bearer {token}.</span></span> <span data-ttu-id="3ca24-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3ca24-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3ca24-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="3ca24-139">Request body</span></span>
<span data-ttu-id="3ca24-140">空白</span><span class="sxs-lookup"><span data-stu-id="3ca24-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3ca24-141">回應</span><span class="sxs-lookup"><span data-stu-id="3ca24-141">Response</span></span>
<span data-ttu-id="3ca24-142">如果成功，這個方法會以 [指示器](ti-indicator.md) 實體集合傳回200、Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="3ca24-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="3ca24-143">如果應用程式具有「Ti ReadWrite」許可權，它會公開給所有指示器。</span><span class="sxs-lookup"><span data-stu-id="3ca24-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="3ca24-144">否則，它只會公開給它所建立的指示器。</span><span class="sxs-lookup"><span data-stu-id="3ca24-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="3ca24-145">範例 1：</span><span class="sxs-lookup"><span data-stu-id="3ca24-145">Example 1:</span></span>

<span data-ttu-id="3ca24-146">**請求**</span><span class="sxs-lookup"><span data-stu-id="3ca24-146">**Request**</span></span>

<span data-ttu-id="3ca24-147">以下是取得所有標記的要求範例</span><span class="sxs-lookup"><span data-stu-id="3ca24-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="3ca24-148">**回應**</span><span class="sxs-lookup"><span data-stu-id="3ca24-148">**Response**</span></span>

<span data-ttu-id="3ca24-149">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3ca24-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="3ca24-150">範例 2：</span><span class="sxs-lookup"><span data-stu-id="3ca24-150">Example 2:</span></span>

<span data-ttu-id="3ca24-151">**請求**</span><span class="sxs-lookup"><span data-stu-id="3ca24-151">**Request**</span></span>

<span data-ttu-id="3ca24-152">以下是以 ' AlertAndBlock ' 動作取得所有標記的要求範例</span><span class="sxs-lookup"><span data-stu-id="3ca24-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="3ca24-153">**回應**</span><span class="sxs-lookup"><span data-stu-id="3ca24-153">**Response**</span></span>

<span data-ttu-id="3ca24-154">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3ca24-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
