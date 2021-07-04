---
title: 刪除指示器 API。
description: 瞭解如何使用刪除指示器 API，在 Microsoft Defender for Endpoint 中刪除識別碼實體。
keywords: api、public api、支援的 api、delete、ti 指標、實體、識別碼
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289916"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="ec576-104">刪除指示器 API</span><span class="sxs-lookup"><span data-stu-id="ec576-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec576-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ec576-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec576-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ec576-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec576-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec576-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec576-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ec576-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ec576-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ec576-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ec576-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="ec576-110">API description</span></span>

<span data-ttu-id="ec576-111">依識別碼刪除 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="ec576-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="ec576-112">限制</span><span class="sxs-lookup"><span data-stu-id="ec576-112">Limitations</span></span>

<span data-ttu-id="ec576-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="ec576-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="ec576-114">權限</span><span class="sxs-lookup"><span data-stu-id="ec576-114">Permissions</span></span>

<span data-ttu-id="ec576-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="ec576-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ec576-116">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ec576-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="ec576-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ec576-117">Permission type</span></span> | <span data-ttu-id="ec576-118">權限</span><span class="sxs-lookup"><span data-stu-id="ec576-118">Permission</span></span> | <span data-ttu-id="ec576-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ec576-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ec576-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="ec576-120">Application</span></span> | <span data-ttu-id="ec576-121">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ec576-121">Ti.ReadWrite</span></span> | <span data-ttu-id="ec576-122">「讀取及寫入 TI 指標 '</span><span class="sxs-lookup"><span data-stu-id="ec576-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="ec576-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="ec576-123">Application</span></span> | <span data-ttu-id="ec576-124">Ti ReadWrite 所有</span><span class="sxs-lookup"><span data-stu-id="ec576-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="ec576-125">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="ec576-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="ec576-126">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ec576-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="ec576-127">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ec576-127">Request headers</span></span>

<span data-ttu-id="ec576-128">名稱</span><span class="sxs-lookup"><span data-stu-id="ec576-128">Name</span></span> | <span data-ttu-id="ec576-129">類型</span><span class="sxs-lookup"><span data-stu-id="ec576-129">Type</span></span> | <span data-ttu-id="ec576-130">說明</span><span class="sxs-lookup"><span data-stu-id="ec576-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="ec576-131">授權</span><span class="sxs-lookup"><span data-stu-id="ec576-131">Authorization</span></span> | <span data-ttu-id="ec576-132">字串</span><span class="sxs-lookup"><span data-stu-id="ec576-132">String</span></span> | <span data-ttu-id="ec576-133">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="ec576-133">Bearer {token}.</span></span> <span data-ttu-id="ec576-134">**必要**。</span><span class="sxs-lookup"><span data-stu-id="ec576-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ec576-135">要求內文</span><span class="sxs-lookup"><span data-stu-id="ec576-135">Request body</span></span>

<span data-ttu-id="ec576-136">空白</span><span class="sxs-lookup"><span data-stu-id="ec576-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ec576-137">回應</span><span class="sxs-lookup"><span data-stu-id="ec576-137">Response</span></span>

<span data-ttu-id="ec576-138">如果指示器存在並成功刪除-204 OK （沒有內容）。</span><span class="sxs-lookup"><span data-stu-id="ec576-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="ec576-139">如果找不到具有指定識別碼的指示器-找不到404。</span><span class="sxs-lookup"><span data-stu-id="ec576-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="ec576-140">範例</span><span class="sxs-lookup"><span data-stu-id="ec576-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="ec576-141">請求</span><span class="sxs-lookup"><span data-stu-id="ec576-141">Request</span></span>

<span data-ttu-id="ec576-142">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="ec576-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
