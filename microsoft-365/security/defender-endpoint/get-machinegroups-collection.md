---
title: 取得 RBAC 機器群組集合 API
description: 瞭解如何使用「取得 KB 集合 API」，在 Microsoft Defender 高級威脅防護中取得 RBAC 裝置群組的集合。
keywords: api、graph api、支援的 api、get、RBAC、group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166426"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="792f4-104">取得 KB 集合 API</span><span class="sxs-lookup"><span data-stu-id="792f4-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="792f4-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="792f4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="792f4-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="792f4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="792f4-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="792f4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="792f4-108">會檢索 RBAC 裝置群組的集合。</span><span class="sxs-lookup"><span data-stu-id="792f4-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="792f4-109">權限</span><span class="sxs-lookup"><span data-stu-id="792f4-109">Permissions</span></span>
<span data-ttu-id="792f4-110">使用者需要讀取權限。</span><span class="sxs-lookup"><span data-stu-id="792f4-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="792f4-111">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="792f4-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="792f4-112">要求標頭</span><span class="sxs-lookup"><span data-stu-id="792f4-112">Request headers</span></span>

<span data-ttu-id="792f4-113">Header</span><span class="sxs-lookup"><span data-stu-id="792f4-113">Header</span></span> | <span data-ttu-id="792f4-114">值</span><span class="sxs-lookup"><span data-stu-id="792f4-114">Value</span></span> 
:---|:---
<span data-ttu-id="792f4-115">授權</span><span class="sxs-lookup"><span data-stu-id="792f4-115">Authorization</span></span> | <span data-ttu-id="792f4-116">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="792f4-116">Bearer {token}.</span></span> <span data-ttu-id="792f4-117">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="792f4-117">**Required**.</span></span>
<span data-ttu-id="792f4-118">內容類型</span><span class="sxs-lookup"><span data-stu-id="792f4-118">Content type</span></span> | <span data-ttu-id="792f4-119">application/json</span><span class="sxs-lookup"><span data-stu-id="792f4-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="792f4-120">要求正文</span><span class="sxs-lookup"><span data-stu-id="792f4-120">Request body</span></span>
<span data-ttu-id="792f4-121">空白</span><span class="sxs-lookup"><span data-stu-id="792f4-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="792f4-122">回應</span><span class="sxs-lookup"><span data-stu-id="792f4-122">Response</span></span>
<span data-ttu-id="792f4-123">如果成功-200 確定。</span><span class="sxs-lookup"><span data-stu-id="792f4-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="792f4-124">範例</span><span class="sxs-lookup"><span data-stu-id="792f4-124">Example</span></span>

<span data-ttu-id="792f4-125">**請求**</span><span class="sxs-lookup"><span data-stu-id="792f4-125">**Request**</span></span>

<span data-ttu-id="792f4-126">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="792f4-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="792f4-127">**回應**</span><span class="sxs-lookup"><span data-stu-id="792f4-127">**Response**</span></span>

<span data-ttu-id="792f4-128">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="792f4-128">Here is an example of the response.</span></span>
<span data-ttu-id="792f4-129">欄位識別碼包含裝置資訊中的裝置群組 **識別碼** 及等於欄位 **rbacGroupId** 。</span><span class="sxs-lookup"><span data-stu-id="792f4-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="792f4-130">[！注意] 只有一個群組適用于尚未指派給任何群組的所有裝置的欄位 **取消** 群組功能。</span><span class="sxs-lookup"><span data-stu-id="792f4-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="792f4-131">這個群組的一般名稱為 "UnassignedGroup"。</span><span class="sxs-lookup"><span data-stu-id="792f4-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
