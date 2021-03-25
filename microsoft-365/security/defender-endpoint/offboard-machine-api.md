---
title: 下架 machine API
description: 瞭解如何使用 API，從 Windows Defender 高級威脅防護 (WDATP) 中，下架裝置。
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
ms.technology: mde
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187123"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="19396-104">下架 machine API</span><span class="sxs-lookup"><span data-stu-id="19396-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19396-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="19396-105">**Applies to:**</span></span>
- [<span data-ttu-id="19396-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19396-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19396-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19396-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19396-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="19396-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="19396-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="19396-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="19396-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="19396-110">API description</span></span>
<span data-ttu-id="19396-111">下架裝置從 Defender 取得端點。</span><span class="sxs-lookup"><span data-stu-id="19396-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="19396-112">限制</span><span class="sxs-lookup"><span data-stu-id="19396-112">Limitations</span></span>
 - <span data-ttu-id="19396-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="19396-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="19396-114">Windows 10、版本1703和更新版本或 Windows Server 2019 及更新版本都支援此 API。</span><span class="sxs-lookup"><span data-stu-id="19396-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="19396-115">MacOS 或 Linux 裝置不支援此 API。</span><span class="sxs-lookup"><span data-stu-id="19396-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="19396-116">權限</span><span class="sxs-lookup"><span data-stu-id="19396-116">Permissions</span></span>
<span data-ttu-id="19396-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="19396-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19396-118">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="19396-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="19396-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="19396-119">Permission type</span></span> |   <span data-ttu-id="19396-120">權限</span><span class="sxs-lookup"><span data-stu-id="19396-120">Permission</span></span>  |   <span data-ttu-id="19396-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="19396-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="19396-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="19396-122">Application</span></span> |   <span data-ttu-id="19396-123">下架</span><span class="sxs-lookup"><span data-stu-id="19396-123">Machine.Offboard</span></span> |  <span data-ttu-id="19396-124">' 下架電腦 '</span><span class="sxs-lookup"><span data-stu-id="19396-124">'Offboard machine'</span></span>
<span data-ttu-id="19396-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="19396-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="19396-126">下架</span><span class="sxs-lookup"><span data-stu-id="19396-126">Machine.Offboard</span></span> |  <span data-ttu-id="19396-127">' 下架電腦 '</span><span class="sxs-lookup"><span data-stu-id="19396-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="19396-128">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="19396-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="19396-129">使用者需要「全域 Admin」 AD 角色</span><span class="sxs-lookup"><span data-stu-id="19396-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="19396-130">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="19396-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="19396-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="19396-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="19396-132">要求標頭</span><span class="sxs-lookup"><span data-stu-id="19396-132">Request headers</span></span>

<span data-ttu-id="19396-133">名稱</span><span class="sxs-lookup"><span data-stu-id="19396-133">Name</span></span> | <span data-ttu-id="19396-134">類型</span><span class="sxs-lookup"><span data-stu-id="19396-134">Type</span></span> | <span data-ttu-id="19396-135">描述</span><span class="sxs-lookup"><span data-stu-id="19396-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="19396-136">授權</span><span class="sxs-lookup"><span data-stu-id="19396-136">Authorization</span></span> | <span data-ttu-id="19396-137">字串</span><span class="sxs-lookup"><span data-stu-id="19396-137">String</span></span> | <span data-ttu-id="19396-138">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="19396-138">Bearer {token}.</span></span> <span data-ttu-id="19396-139">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="19396-139">**Required**.</span></span>
<span data-ttu-id="19396-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="19396-140">Content-Type</span></span> | <span data-ttu-id="19396-141">string</span><span class="sxs-lookup"><span data-stu-id="19396-141">string</span></span> | <span data-ttu-id="19396-142">application/json。</span><span class="sxs-lookup"><span data-stu-id="19396-142">application/json.</span></span> <span data-ttu-id="19396-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="19396-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="19396-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="19396-144">Request body</span></span>
<span data-ttu-id="19396-145">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="19396-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="19396-146">參數</span><span class="sxs-lookup"><span data-stu-id="19396-146">Parameter</span></span> | <span data-ttu-id="19396-147">類型</span><span class="sxs-lookup"><span data-stu-id="19396-147">Type</span></span>    | <span data-ttu-id="19396-148">描述</span><span class="sxs-lookup"><span data-stu-id="19396-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="19396-149">留言</span><span class="sxs-lookup"><span data-stu-id="19396-149">Comment</span></span> |   <span data-ttu-id="19396-150">字串</span><span class="sxs-lookup"><span data-stu-id="19396-150">String</span></span> |    <span data-ttu-id="19396-151">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="19396-151">Comment to associate with the action.</span></span> <span data-ttu-id="19396-152">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="19396-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="19396-153">回應</span><span class="sxs-lookup"><span data-stu-id="19396-153">Response</span></span>
<span data-ttu-id="19396-154">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="19396-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="19396-155">範例</span><span class="sxs-lookup"><span data-stu-id="19396-155">Example</span></span>

<span data-ttu-id="19396-156">**請求**</span><span class="sxs-lookup"><span data-stu-id="19396-156">**Request**</span></span>

<span data-ttu-id="19396-157">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="19396-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
