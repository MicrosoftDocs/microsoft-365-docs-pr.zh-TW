---
title: 下架 machine API
description: 瞭解如何使用 API 從 Microsoft Defender for Endpoint 下架裝置。
keywords: api、graph api、支援的 api、收集調查套件
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
ms.openlocfilehash: e2b1114cd091c9cd42aa8e4525416f9d73358a65
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771990"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="c6225-104">下架 machine API</span><span class="sxs-lookup"><span data-stu-id="c6225-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6225-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c6225-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6225-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c6225-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6225-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6225-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6225-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c6225-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6225-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c6225-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c6225-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="c6225-110">API description</span></span>
<span data-ttu-id="c6225-111">下架裝置從 Defender 取得端點。</span><span class="sxs-lookup"><span data-stu-id="c6225-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="c6225-112">限制</span><span class="sxs-lookup"><span data-stu-id="c6225-112">Limitations</span></span>
 - <span data-ttu-id="c6225-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="c6225-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="c6225-114">Windows 10、版本1703和更新版本，或是 Windows Server 2019 及更新版本，都支援此 API。</span><span class="sxs-lookup"><span data-stu-id="c6225-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="c6225-115">MacOS 或 Linux 裝置不支援此 API。</span><span class="sxs-lookup"><span data-stu-id="c6225-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="c6225-116">權限</span><span class="sxs-lookup"><span data-stu-id="c6225-116">Permissions</span></span>
<span data-ttu-id="c6225-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="c6225-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c6225-118">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c6225-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c6225-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="c6225-119">Permission type</span></span> |   <span data-ttu-id="c6225-120">權限</span><span class="sxs-lookup"><span data-stu-id="c6225-120">Permission</span></span>  |   <span data-ttu-id="c6225-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c6225-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c6225-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="c6225-122">Application</span></span> |   <span data-ttu-id="c6225-123">下架</span><span class="sxs-lookup"><span data-stu-id="c6225-123">Machine.Offboard</span></span> |  <span data-ttu-id="c6225-124">' 下架電腦 '</span><span class="sxs-lookup"><span data-stu-id="c6225-124">'Offboard machine'</span></span>
<span data-ttu-id="c6225-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="c6225-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="c6225-126">下架</span><span class="sxs-lookup"><span data-stu-id="c6225-126">Machine.Offboard</span></span> |  <span data-ttu-id="c6225-127">' 下架電腦 '</span><span class="sxs-lookup"><span data-stu-id="c6225-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="c6225-128">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="c6225-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c6225-129">使用者需要「全域 Admin」 AD 角色</span><span class="sxs-lookup"><span data-stu-id="c6225-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="c6225-130">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="c6225-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c6225-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c6225-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="c6225-132">要求標頭</span><span class="sxs-lookup"><span data-stu-id="c6225-132">Request headers</span></span>

<span data-ttu-id="c6225-133">名稱</span><span class="sxs-lookup"><span data-stu-id="c6225-133">Name</span></span> | <span data-ttu-id="c6225-134">類型</span><span class="sxs-lookup"><span data-stu-id="c6225-134">Type</span></span> | <span data-ttu-id="c6225-135">描述</span><span class="sxs-lookup"><span data-stu-id="c6225-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="c6225-136">授權</span><span class="sxs-lookup"><span data-stu-id="c6225-136">Authorization</span></span> | <span data-ttu-id="c6225-137">字串</span><span class="sxs-lookup"><span data-stu-id="c6225-137">String</span></span> | <span data-ttu-id="c6225-138">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="c6225-138">Bearer {token}.</span></span> <span data-ttu-id="c6225-139">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="c6225-139">**Required**.</span></span>
<span data-ttu-id="c6225-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c6225-140">Content-Type</span></span> | <span data-ttu-id="c6225-141">string</span><span class="sxs-lookup"><span data-stu-id="c6225-141">string</span></span> | <span data-ttu-id="c6225-142">application/json。</span><span class="sxs-lookup"><span data-stu-id="c6225-142">application/json.</span></span> <span data-ttu-id="c6225-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="c6225-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c6225-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="c6225-144">Request body</span></span>
<span data-ttu-id="c6225-145">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="c6225-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c6225-146">參數</span><span class="sxs-lookup"><span data-stu-id="c6225-146">Parameter</span></span> | <span data-ttu-id="c6225-147">類型</span><span class="sxs-lookup"><span data-stu-id="c6225-147">Type</span></span>    | <span data-ttu-id="c6225-148">描述</span><span class="sxs-lookup"><span data-stu-id="c6225-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="c6225-149">留言</span><span class="sxs-lookup"><span data-stu-id="c6225-149">Comment</span></span> |   <span data-ttu-id="c6225-150">字串</span><span class="sxs-lookup"><span data-stu-id="c6225-150">String</span></span> |    <span data-ttu-id="c6225-151">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="c6225-151">Comment to associate with the action.</span></span> <span data-ttu-id="c6225-152">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="c6225-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c6225-153">回應</span><span class="sxs-lookup"><span data-stu-id="c6225-153">Response</span></span>
<span data-ttu-id="c6225-154">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="c6225-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c6225-155">範例</span><span class="sxs-lookup"><span data-stu-id="c6225-155">Example</span></span>

<span data-ttu-id="c6225-156">**請求**</span><span class="sxs-lookup"><span data-stu-id="c6225-156">**Request**</span></span>

<span data-ttu-id="c6225-157">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="c6225-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
