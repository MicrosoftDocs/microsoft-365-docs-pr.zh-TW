---
title: 取得檔相關的警示 API
description: 瞭解如何使用 [取得檔案相關的警示] API，以取得與 Microsoft Defender for Endpoint 中的指定檔案雜湊相關的警示集合。
keywords: api、graph api、支援的 api、get、file、hash
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770292"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="5b058-104">取得檔相關的警示 API</span><span class="sxs-lookup"><span data-stu-id="5b058-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5b058-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5b058-105">**Applies to:**</span></span>
- [<span data-ttu-id="5b058-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5b058-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5b058-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b058-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5b058-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="5b058-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b058-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5b058-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5b058-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="5b058-110">API description</span></span>
<span data-ttu-id="5b058-111">會檢索與指定的檔案雜湊相關的警示集合。</span><span class="sxs-lookup"><span data-stu-id="5b058-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="5b058-112">限制</span><span class="sxs-lookup"><span data-stu-id="5b058-112">Limitations</span></span>
1. <span data-ttu-id="5b058-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="5b058-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5b058-114">權限</span><span class="sxs-lookup"><span data-stu-id="5b058-114">Permissions</span></span>
<span data-ttu-id="5b058-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="5b058-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5b058-116">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5b058-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5b058-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="5b058-117">Permission type</span></span> |   <span data-ttu-id="5b058-118">權限</span><span class="sxs-lookup"><span data-stu-id="5b058-118">Permission</span></span>  |   <span data-ttu-id="5b058-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="5b058-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5b058-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="5b058-120">Application</span></span> |   <span data-ttu-id="5b058-121">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="5b058-121">Alert.Read.All</span></span> |    <span data-ttu-id="5b058-122">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="5b058-122">'Read all alerts'</span></span>
<span data-ttu-id="5b058-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="5b058-123">Application</span></span> |   <span data-ttu-id="5b058-124">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="5b058-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="5b058-125">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="5b058-125">'Read and write all alerts'</span></span>
<span data-ttu-id="5b058-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="5b058-126">Delegated (work or school account)</span></span> | <span data-ttu-id="5b058-127">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="5b058-127">Alert.Read</span></span> | <span data-ttu-id="5b058-128">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="5b058-128">'Read alerts'</span></span>
<span data-ttu-id="5b058-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="5b058-129">Delegated (work or school account)</span></span> | <span data-ttu-id="5b058-130">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5b058-130">Alert.ReadWrite</span></span> | <span data-ttu-id="5b058-131">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="5b058-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="5b058-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="5b058-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5b058-133">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="5b058-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5b058-134">回應只會包含使用者有權存取之裝置的警示（取決於裝置群組設定） (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="5b058-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5b058-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="5b058-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="5b058-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="5b058-136">Request headers</span></span>

<span data-ttu-id="5b058-137">名稱</span><span class="sxs-lookup"><span data-stu-id="5b058-137">Name</span></span> | <span data-ttu-id="5b058-138">類型</span><span class="sxs-lookup"><span data-stu-id="5b058-138">Type</span></span> | <span data-ttu-id="5b058-139">描述</span><span class="sxs-lookup"><span data-stu-id="5b058-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="5b058-140">授權</span><span class="sxs-lookup"><span data-stu-id="5b058-140">Authorization</span></span> | <span data-ttu-id="5b058-141">字串</span><span class="sxs-lookup"><span data-stu-id="5b058-141">String</span></span> | <span data-ttu-id="5b058-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="5b058-142">Bearer {token}.</span></span> <span data-ttu-id="5b058-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="5b058-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5b058-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="5b058-144">Request body</span></span>
<span data-ttu-id="5b058-145">空白</span><span class="sxs-lookup"><span data-stu-id="5b058-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5b058-146">回應</span><span class="sxs-lookup"><span data-stu-id="5b058-146">Response</span></span>
<span data-ttu-id="5b058-147">如果成功和檔案存在-200 OK，含內文中的 [警示](alerts.md) 實體清單。</span><span class="sxs-lookup"><span data-stu-id="5b058-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="5b058-148">如果檔案不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="5b058-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5b058-149">範例</span><span class="sxs-lookup"><span data-stu-id="5b058-149">Example</span></span>

<span data-ttu-id="5b058-150">**請求**</span><span class="sxs-lookup"><span data-stu-id="5b058-150">**Request**</span></span>

<span data-ttu-id="5b058-151">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="5b058-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
