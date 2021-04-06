---
title: 取得安裝的軟體
description: 會檢索與指定裝置識別碼相關的已安裝軟體的集合。
keywords: api，graph api，支援的 api，get，list，file，information，軟體清查，每個裝置的已安裝軟體，威脅 & 漏洞管理 api，mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 6164020ef05561563fe0434bd2edac8c7b3e689a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166386"
---
# <a name="get-installed-software"></a><span data-ttu-id="3b951-104">取得安裝的軟體</span><span class="sxs-lookup"><span data-stu-id="3b951-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b951-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3b951-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b951-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b951-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b951-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b951-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b951-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3b951-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b951-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b951-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3b951-110">會檢索與指定裝置識別碼相關的已安裝軟體的集合。</span><span class="sxs-lookup"><span data-stu-id="3b951-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="3b951-111">權限</span><span class="sxs-lookup"><span data-stu-id="3b951-111">Permissions</span></span>
<span data-ttu-id="3b951-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3b951-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3b951-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3b951-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3b951-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3b951-114">Permission type</span></span> |   <span data-ttu-id="3b951-115">權限</span><span class="sxs-lookup"><span data-stu-id="3b951-115">Permission</span></span>  |   <span data-ttu-id="3b951-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3b951-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3b951-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="3b951-117">Application</span></span> |<span data-ttu-id="3b951-118">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="3b951-118">Software.Read.All</span></span> |    <span data-ttu-id="3b951-119">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="3b951-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="3b951-120">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3b951-120">Delegated (work or school account)</span></span> | <span data-ttu-id="3b951-121">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="3b951-121">Software.Read</span></span> |    <span data-ttu-id="3b951-122">「讀取威脅和弱點管理軟體資訊」</span><span class="sxs-lookup"><span data-stu-id="3b951-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3b951-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3b951-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="3b951-124">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3b951-124">Request headers</span></span>

<span data-ttu-id="3b951-125">名稱</span><span class="sxs-lookup"><span data-stu-id="3b951-125">Name</span></span> | <span data-ttu-id="3b951-126">類型</span><span class="sxs-lookup"><span data-stu-id="3b951-126">Type</span></span> | <span data-ttu-id="3b951-127">描述</span><span class="sxs-lookup"><span data-stu-id="3b951-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b951-128">授權</span><span class="sxs-lookup"><span data-stu-id="3b951-128">Authorization</span></span> | <span data-ttu-id="3b951-129">字串</span><span class="sxs-lookup"><span data-stu-id="3b951-129">String</span></span> | <span data-ttu-id="3b951-130">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3b951-130">Bearer {token}.</span></span> <span data-ttu-id="3b951-131">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3b951-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3b951-132">要求正文</span><span class="sxs-lookup"><span data-stu-id="3b951-132">Request body</span></span>
<span data-ttu-id="3b951-133">空白</span><span class="sxs-lookup"><span data-stu-id="3b951-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3b951-134">回應</span><span class="sxs-lookup"><span data-stu-id="3b951-134">Response</span></span>
<span data-ttu-id="3b951-135">若成功，這個方法會以主體中已安裝的軟體資訊傳回 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3b951-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="3b951-136">範例</span><span class="sxs-lookup"><span data-stu-id="3b951-136">Example</span></span>

<span data-ttu-id="3b951-137">**請求**</span><span class="sxs-lookup"><span data-stu-id="3b951-137">**Request**</span></span>

<span data-ttu-id="3b951-138">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3b951-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="3b951-139">**回應**</span><span class="sxs-lookup"><span data-stu-id="3b951-139">**Response**</span></span>

<span data-ttu-id="3b951-140">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3b951-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="3b951-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3b951-141">See also</span></span>

- [<span data-ttu-id="3b951-142">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="3b951-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3b951-143">威脅 & 弱點軟體清單</span><span class="sxs-lookup"><span data-stu-id="3b951-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)