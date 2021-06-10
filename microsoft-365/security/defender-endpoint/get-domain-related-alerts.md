---
title: 取得與網域相關的警示 API
description: 瞭解如何使用「取得網域相關的警示」 API，以在 Microsoft Defender for Endpoint 中檢索與特定網域位址相關的提醒。
keywords: api、graph api、支援的 api、get、domain、相關、警示
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772254"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="822b0-104">取得與網域相關的警示 API</span><span class="sxs-lookup"><span data-stu-id="822b0-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="822b0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="822b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="822b0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="822b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="822b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="822b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="822b0-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="822b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="822b0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="822b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="822b0-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="822b0-110">API description</span></span>
<span data-ttu-id="822b0-111">會檢索與特定網域位址相關的 [警示](alerts.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="822b0-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="822b0-112">限制</span><span class="sxs-lookup"><span data-stu-id="822b0-112">Limitations</span></span>
1. <span data-ttu-id="822b0-113">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="822b0-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="822b0-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="822b0-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="822b0-115">權限</span><span class="sxs-lookup"><span data-stu-id="822b0-115">Permissions</span></span>
<span data-ttu-id="822b0-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="822b0-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="822b0-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="822b0-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="822b0-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="822b0-118">Permission type</span></span> |   <span data-ttu-id="822b0-119">權限</span><span class="sxs-lookup"><span data-stu-id="822b0-119">Permission</span></span>  |   <span data-ttu-id="822b0-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="822b0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="822b0-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="822b0-121">Application</span></span> |   <span data-ttu-id="822b0-122">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="822b0-122">Alert.Read.All</span></span> |    <span data-ttu-id="822b0-123">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="822b0-123">'Read all alerts'</span></span>
<span data-ttu-id="822b0-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="822b0-124">Application</span></span> |   <span data-ttu-id="822b0-125">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="822b0-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="822b0-126">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="822b0-126">'Read and write all alerts'</span></span>
<span data-ttu-id="822b0-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="822b0-127">Delegated (work or school account)</span></span> | <span data-ttu-id="822b0-128">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="822b0-128">Alert.Read</span></span> | <span data-ttu-id="822b0-129">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="822b0-129">'Read alerts'</span></span>
<span data-ttu-id="822b0-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="822b0-130">Delegated (work or school account)</span></span> | <span data-ttu-id="822b0-131">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="822b0-131">Alert.ReadWrite</span></span> | <span data-ttu-id="822b0-132">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="822b0-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="822b0-133">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="822b0-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="822b0-134">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="822b0-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="822b0-135">回應只會包含使用者有權存取之裝置的警示（取決於裝置群組設定） (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="822b0-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="822b0-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="822b0-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="822b0-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="822b0-137">Request headers</span></span>

| <span data-ttu-id="822b0-138">頁首</span><span class="sxs-lookup"><span data-stu-id="822b0-138">Header</span></span>        | <span data-ttu-id="822b0-139">值</span><span class="sxs-lookup"><span data-stu-id="822b0-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="822b0-140">授權</span><span class="sxs-lookup"><span data-stu-id="822b0-140">Authorization</span></span> | <span data-ttu-id="822b0-141">字串</span><span class="sxs-lookup"><span data-stu-id="822b0-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="822b0-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="822b0-142">Request body</span></span>
<span data-ttu-id="822b0-143">空白</span><span class="sxs-lookup"><span data-stu-id="822b0-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="822b0-144">回應</span><span class="sxs-lookup"><span data-stu-id="822b0-144">Response</span></span>
<span data-ttu-id="822b0-145">如果成功且網域存在-200 OK （含 [警示](alerts.md) 實體的清單）。</span><span class="sxs-lookup"><span data-stu-id="822b0-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="822b0-146">如果網域不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="822b0-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="822b0-147">範例</span><span class="sxs-lookup"><span data-stu-id="822b0-147">Example</span></span>

<span data-ttu-id="822b0-148">**請求**</span><span class="sxs-lookup"><span data-stu-id="822b0-148">**Request**</span></span>

<span data-ttu-id="822b0-149">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="822b0-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
