---
title: 依軟體列出裝置
description: 檢索已安裝此軟體的裝置清單。
keywords: api，graph api，支援的 api，get，列出裝置，裝置清單，依軟體的清單裝置，mdatp tvm api
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
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200386"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="9c01f-104">依軟體列出裝置</span><span class="sxs-lookup"><span data-stu-id="9c01f-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c01f-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9c01f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9c01f-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9c01f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9c01f-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9c01f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9c01f-108">取得安裝了此軟體的裝置參考清單。</span><span class="sxs-lookup"><span data-stu-id="9c01f-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="9c01f-109">權限</span><span class="sxs-lookup"><span data-stu-id="9c01f-109">Permissions</span></span>
<span data-ttu-id="9c01f-110">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="9c01f-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9c01f-111">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9c01f-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="9c01f-112">許可權類型</span><span class="sxs-lookup"><span data-stu-id="9c01f-112">Permission type</span></span> |   <span data-ttu-id="9c01f-113">權限</span><span class="sxs-lookup"><span data-stu-id="9c01f-113">Permission</span></span>  |   <span data-ttu-id="9c01f-114">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="9c01f-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9c01f-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="9c01f-115">Application</span></span> | <span data-ttu-id="9c01f-116">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="9c01f-116">Software.Read.All</span></span> | <span data-ttu-id="9c01f-117">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="9c01f-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="9c01f-118">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="9c01f-118">Delegated (work or school account)</span></span> | <span data-ttu-id="9c01f-119">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="9c01f-119">Software.Read</span></span> | <span data-ttu-id="9c01f-120">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="9c01f-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="9c01f-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9c01f-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="9c01f-122">要求標頭</span><span class="sxs-lookup"><span data-stu-id="9c01f-122">Request headers</span></span>

| <span data-ttu-id="9c01f-123">名稱</span><span class="sxs-lookup"><span data-stu-id="9c01f-123">Name</span></span>        | <span data-ttu-id="9c01f-124">類型</span><span class="sxs-lookup"><span data-stu-id="9c01f-124">Type</span></span> | <span data-ttu-id="9c01f-125">描述</span><span class="sxs-lookup"><span data-stu-id="9c01f-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="9c01f-126">授權</span><span class="sxs-lookup"><span data-stu-id="9c01f-126">Authorization</span></span> | <span data-ttu-id="9c01f-127">字串</span><span class="sxs-lookup"><span data-stu-id="9c01f-127">String</span></span> | <span data-ttu-id="9c01f-128">載荷 {token}。**必要**。</span><span class="sxs-lookup"><span data-stu-id="9c01f-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9c01f-129">要求正文</span><span class="sxs-lookup"><span data-stu-id="9c01f-129">Request body</span></span>
<span data-ttu-id="9c01f-130">空白</span><span class="sxs-lookup"><span data-stu-id="9c01f-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9c01f-131">回應</span><span class="sxs-lookup"><span data-stu-id="9c01f-131">Response</span></span>
<span data-ttu-id="9c01f-132">如果成功，這個方法會傳回 200 OK 和裝置清單，其中的軟體是安裝在本文中。</span><span class="sxs-lookup"><span data-stu-id="9c01f-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="9c01f-133">範例</span><span class="sxs-lookup"><span data-stu-id="9c01f-133">Example</span></span>

<span data-ttu-id="9c01f-134">**請求**</span><span class="sxs-lookup"><span data-stu-id="9c01f-134">**Request**</span></span>

<span data-ttu-id="9c01f-135">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="9c01f-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="9c01f-136">**回應**</span><span class="sxs-lookup"><span data-stu-id="9c01f-136">**Response**</span></span>

<span data-ttu-id="9c01f-137">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="9c01f-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="9c01f-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="9c01f-138">Related topics</span></span>
- [<span data-ttu-id="9c01f-139">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="9c01f-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="9c01f-140">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="9c01f-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
