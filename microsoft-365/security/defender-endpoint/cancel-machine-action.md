---
title: 取消電腦動作 API
description: 瞭解如何取消已啟動的機器動作
keywords: api、graph api、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879697"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="b6d58-104">取消電腦動作 API</span><span class="sxs-lookup"><span data-stu-id="b6d58-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6d58-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b6d58-105">**Applies to:**</span></span>
- [<span data-ttu-id="b6d58-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6d58-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="b6d58-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b6d58-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b6d58-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b6d58-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b6d58-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="b6d58-109">API description</span></span>

<span data-ttu-id="b6d58-110">取消已啟動的機器動作，該動作尚未處於最終狀態 (已完成、取消、失敗) 。</span><span class="sxs-lookup"><span data-stu-id="b6d58-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="b6d58-111">限制</span><span class="sxs-lookup"><span data-stu-id="b6d58-111">Limitations</span></span>

1.  <span data-ttu-id="b6d58-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="b6d58-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="b6d58-113">權限</span><span class="sxs-lookup"><span data-stu-id="b6d58-113">Permissions</span></span>

<span data-ttu-id="b6d58-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="b6d58-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b6d58-115">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d58-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="b6d58-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="b6d58-116">Permission    type</span></span>     |     <span data-ttu-id="b6d58-117">權限</span><span class="sxs-lookup"><span data-stu-id="b6d58-117">Permission</span></span>     |    <span data-ttu-id="b6d58-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="b6d58-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="b6d58-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="b6d58-119">Application</span></span>    |    <br><span data-ttu-id="b6d58-120">CollectForensic</span><span class="sxs-lookup"><span data-stu-id="b6d58-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="b6d58-121">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="b6d58-121">Machine.Isolate</span></span>   <br><span data-ttu-id="b6d58-122">RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b6d58-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="b6d58-123">電腦。掃描</span><span class="sxs-lookup"><span data-stu-id="b6d58-123">Machine.Scan</span></span><br>   <span data-ttu-id="b6d58-124">下架</span><span class="sxs-lookup"><span data-stu-id="b6d58-124">Machine.Offboard</span></span><br>   <span data-ttu-id="b6d58-125">StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="b6d58-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="b6d58-126">LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b6d58-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="b6d58-127">收集辯論</span><span class="sxs-lookup"><span data-stu-id="b6d58-127">Collect   forensics</span></span>   <br><span data-ttu-id="b6d58-128">隔離電腦</span><span class="sxs-lookup"><span data-stu-id="b6d58-128">Isolate   machine</span></span><br><span data-ttu-id="b6d58-129">限制程式碼執行</span><span class="sxs-lookup"><span data-stu-id="b6d58-129">Restrict   code execution</span></span><br>  <span data-ttu-id="b6d58-130">掃描電腦</span><span class="sxs-lookup"><span data-stu-id="b6d58-130">Scan   machine</span></span><br>  <span data-ttu-id="b6d58-131">下架機</span><span class="sxs-lookup"><span data-stu-id="b6d58-131">Offboard   machine</span></span><br>   <span data-ttu-id="b6d58-132">停止和隔離</span><span class="sxs-lookup"><span data-stu-id="b6d58-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="b6d58-133">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="b6d58-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="b6d58-134">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="b6d58-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="b6d58-135">CollectForensic</span><span class="sxs-lookup"><span data-stu-id="b6d58-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="b6d58-136">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="b6d58-136">Machine.Isolate</span></span>    <br><span data-ttu-id="b6d58-137">RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b6d58-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="b6d58-138">電腦。掃描</span><span class="sxs-lookup"><span data-stu-id="b6d58-138">Machine.Scan</span></span><br>   <span data-ttu-id="b6d58-139">下架</span><span class="sxs-lookup"><span data-stu-id="b6d58-139">Machine.Offboard</span></span><br>   <span data-ttu-id="b6d58-140">StopAndQuarantineMachine。 LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b6d58-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="b6d58-141">收集辯論</span><span class="sxs-lookup"><span data-stu-id="b6d58-141">Collect   forensics</span></span><br>   <span data-ttu-id="b6d58-142">隔離電腦</span><span class="sxs-lookup"><span data-stu-id="b6d58-142">Isolate   machine</span></span><br>  <span data-ttu-id="b6d58-143">限制程式碼執行</span><span class="sxs-lookup"><span data-stu-id="b6d58-143">Restrict   code execution</span></span><br> <span data-ttu-id="b6d58-144">掃描電腦</span><span class="sxs-lookup"><span data-stu-id="b6d58-144">Scan   machine</span></span><br><span data-ttu-id="b6d58-145">下架機</span><span class="sxs-lookup"><span data-stu-id="b6d58-145">Offboard   machine</span></span><br> <span data-ttu-id="b6d58-146">停止和隔離</span><span class="sxs-lookup"><span data-stu-id="b6d58-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="b6d58-147">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="b6d58-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="b6d58-148">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b6d58-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="b6d58-149">要求標頭</span><span class="sxs-lookup"><span data-stu-id="b6d58-149">Request headers</span></span>

| <span data-ttu-id="b6d58-150">名稱</span><span class="sxs-lookup"><span data-stu-id="b6d58-150">Name</span></span>      | <span data-ttu-id="b6d58-151">類型</span><span class="sxs-lookup"><span data-stu-id="b6d58-151">Type</span></span> | <span data-ttu-id="b6d58-152">描述</span><span class="sxs-lookup"><span data-stu-id="b6d58-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="b6d58-153">授權</span><span class="sxs-lookup"><span data-stu-id="b6d58-153">Authorization</span></span> | <span data-ttu-id="b6d58-154">字串</span><span class="sxs-lookup"><span data-stu-id="b6d58-154">String</span></span>   | <span data-ttu-id="b6d58-155">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="b6d58-155">Bearer {token}.</span></span> <span data-ttu-id="b6d58-156">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="b6d58-156">Required.</span></span>   |
| <span data-ttu-id="b6d58-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b6d58-157">Content-Type</span></span>  | <span data-ttu-id="b6d58-158">string</span><span class="sxs-lookup"><span data-stu-id="b6d58-158">string</span></span>   | <span data-ttu-id="b6d58-159">application/json。</span><span class="sxs-lookup"><span data-stu-id="b6d58-159">application/json.</span></span> <span data-ttu-id="b6d58-160">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="b6d58-160">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="b6d58-161">要求正文</span><span class="sxs-lookup"><span data-stu-id="b6d58-161">Request body</span></span>

| <span data-ttu-id="b6d58-162">參數</span><span class="sxs-lookup"><span data-stu-id="b6d58-162">Parameter</span></span> | <span data-ttu-id="b6d58-163">類型</span><span class="sxs-lookup"><span data-stu-id="b6d58-163">Type</span></span> | <span data-ttu-id="b6d58-164">描述</span><span class="sxs-lookup"><span data-stu-id="b6d58-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="b6d58-165">留言</span><span class="sxs-lookup"><span data-stu-id="b6d58-165">Comment</span></span>       | <span data-ttu-id="b6d58-166">字串</span><span class="sxs-lookup"><span data-stu-id="b6d58-166">String</span></span>   | <span data-ttu-id="b6d58-167">與取消動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="b6d58-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="b6d58-168">回應</span><span class="sxs-lookup"><span data-stu-id="b6d58-168">Response</span></span>

<span data-ttu-id="b6d58-169">若成功，這個方法會傳回200，具有機器動作實體的 Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="b6d58-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="b6d58-170">如果找不到具有指定識別碼的 machine action 實體-找不到404。</span><span class="sxs-lookup"><span data-stu-id="b6d58-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b6d58-171">範例</span><span class="sxs-lookup"><span data-stu-id="b6d58-171">Example</span></span>

<span data-ttu-id="b6d58-172">**請求**</span><span class="sxs-lookup"><span data-stu-id="b6d58-172">**Request**</span></span>

<span data-ttu-id="b6d58-173">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="b6d58-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="b6d58-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="b6d58-174">Related topic</span></span>

- [<span data-ttu-id="b6d58-175">取得機器動作 API</span><span class="sxs-lookup"><span data-stu-id="b6d58-175">Get machine action API</span></span>](get-machineaction-object.md)