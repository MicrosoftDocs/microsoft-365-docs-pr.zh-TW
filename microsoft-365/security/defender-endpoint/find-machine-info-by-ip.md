---
title: 依內部 IP API 尋找裝置資訊
description: 使用此 API 來建立與在內部 IP 中尋找特定時間戳記的裝置專案相關的呼叫。
keywords: ip，api，graph api，支援的 api，尋找裝置，裝置資訊
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166466"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="07159-104">依內部 IP API 尋找裝置資訊</span><span class="sxs-lookup"><span data-stu-id="07159-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="07159-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="07159-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="07159-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="07159-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07159-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="07159-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="07159-108">依內部 IP 尋找裝置。</span><span class="sxs-lookup"><span data-stu-id="07159-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="07159-109">時間戳記必須在過去30天內。</span><span class="sxs-lookup"><span data-stu-id="07159-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="07159-110">權限</span><span class="sxs-lookup"><span data-stu-id="07159-110">Permissions</span></span>
<span data-ttu-id="07159-111">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="07159-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="07159-112">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="07159-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="07159-113">許可權類型</span><span class="sxs-lookup"><span data-stu-id="07159-113">Permission type</span></span> | <span data-ttu-id="07159-114">權限</span><span class="sxs-lookup"><span data-stu-id="07159-114">Permission</span></span> | <span data-ttu-id="07159-115">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="07159-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="07159-116">應用程式</span><span class="sxs-lookup"><span data-stu-id="07159-116">Application</span></span> | <span data-ttu-id="07159-117">Read。所有</span><span class="sxs-lookup"><span data-stu-id="07159-117">Machine.Read.All</span></span> | <span data-ttu-id="07159-118">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="07159-118">'Read all machine profiles'</span></span>
<span data-ttu-id="07159-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="07159-119">Application</span></span> | <span data-ttu-id="07159-120">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="07159-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="07159-121">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="07159-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="07159-122">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="07159-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="07159-123">要求標頭</span><span class="sxs-lookup"><span data-stu-id="07159-123">Request headers</span></span>

<span data-ttu-id="07159-124">名稱</span><span class="sxs-lookup"><span data-stu-id="07159-124">Name</span></span> | <span data-ttu-id="07159-125">類型</span><span class="sxs-lookup"><span data-stu-id="07159-125">Type</span></span> | <span data-ttu-id="07159-126">描述</span><span class="sxs-lookup"><span data-stu-id="07159-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="07159-127">授權</span><span class="sxs-lookup"><span data-stu-id="07159-127">Authorization</span></span> | <span data-ttu-id="07159-128">字串</span><span class="sxs-lookup"><span data-stu-id="07159-128">String</span></span> | <span data-ttu-id="07159-129">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="07159-129">Bearer {token}.</span></span> <span data-ttu-id="07159-130">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="07159-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="07159-131">要求正文</span><span class="sxs-lookup"><span data-stu-id="07159-131">Request body</span></span>
<span data-ttu-id="07159-132">空白</span><span class="sxs-lookup"><span data-stu-id="07159-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="07159-133">回應</span><span class="sxs-lookup"><span data-stu-id="07159-133">Response</span></span>
<span data-ttu-id="07159-134">如果成功且機器存在-200 OK。</span><span class="sxs-lookup"><span data-stu-id="07159-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="07159-135">如果找不到任何機器-找不到404。</span><span class="sxs-lookup"><span data-stu-id="07159-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="07159-136">範例</span><span class="sxs-lookup"><span data-stu-id="07159-136">Example</span></span>

<span data-ttu-id="07159-137">**請求**</span><span class="sxs-lookup"><span data-stu-id="07159-137">**Request**</span></span>

<span data-ttu-id="07159-138">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="07159-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="07159-139">**回應**</span><span class="sxs-lookup"><span data-stu-id="07159-139">**Response**</span></span>

<span data-ttu-id="07159-140">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="07159-140">Here is an example of the response.</span></span>

<span data-ttu-id="07159-141">回應會傳回在時間戳記之前和之後16分鐘內，報告此 IP 位址的所有裝置清單。</span><span class="sxs-lookup"><span data-stu-id="07159-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
