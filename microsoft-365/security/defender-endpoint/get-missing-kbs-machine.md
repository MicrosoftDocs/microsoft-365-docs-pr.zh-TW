---
title: 依設備識別碼取得遺失的 Kb
description: 依設備識別碼檢索遺失的安全性更新
keywords: api，graph api，支援的 api，get，list，file，information，device id，威脅 & 弱點管理 api，Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845231"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="aa3ce-104">依設備識別碼取得遺失的 Kb</span><span class="sxs-lookup"><span data-stu-id="aa3ce-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa3ce-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="aa3ce-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="aa3ce-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="aa3ce-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa3ce-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="aa3ce-108">) 依設備識別碼的安全性更新，檢索遺失的 Kb (</span><span class="sxs-lookup"><span data-stu-id="aa3ce-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="aa3ce-109">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="aa3ce-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="aa3ce-110">要求標頭</span><span class="sxs-lookup"><span data-stu-id="aa3ce-110">Request header</span></span>

<span data-ttu-id="aa3ce-111">名稱</span><span class="sxs-lookup"><span data-stu-id="aa3ce-111">Name</span></span> | <span data-ttu-id="aa3ce-112">類型</span><span class="sxs-lookup"><span data-stu-id="aa3ce-112">Type</span></span> | <span data-ttu-id="aa3ce-113">描述</span><span class="sxs-lookup"><span data-stu-id="aa3ce-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="aa3ce-114">授權</span><span class="sxs-lookup"><span data-stu-id="aa3ce-114">Authorization</span></span> | <span data-ttu-id="aa3ce-115">字串</span><span class="sxs-lookup"><span data-stu-id="aa3ce-115">String</span></span> | <span data-ttu-id="aa3ce-116">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-116">Bearer {token}.</span></span> <span data-ttu-id="aa3ce-117">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="aa3ce-118">要求正文</span><span class="sxs-lookup"><span data-stu-id="aa3ce-118">Request body</span></span>

<span data-ttu-id="aa3ce-119">空白</span><span class="sxs-lookup"><span data-stu-id="aa3ce-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aa3ce-120">回應</span><span class="sxs-lookup"><span data-stu-id="aa3ce-120">Response</span></span>

<span data-ttu-id="aa3ce-121">如果成功，這個方法會傳回 200 OK，並指定的裝置中的主體中遺失 kb 資料。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="aa3ce-122">範例</span><span class="sxs-lookup"><span data-stu-id="aa3ce-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="aa3ce-123">請求</span><span class="sxs-lookup"><span data-stu-id="aa3ce-123">Request</span></span>

<span data-ttu-id="aa3ce-124">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="aa3ce-125">回應</span><span class="sxs-lookup"><span data-stu-id="aa3ce-125">Response</span></span>

<span data-ttu-id="aa3ce-126">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="aa3ce-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="aa3ce-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa3ce-127">Related topics</span></span>

- [<span data-ttu-id="aa3ce-128">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="aa3ce-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="aa3ce-129">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="aa3ce-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
