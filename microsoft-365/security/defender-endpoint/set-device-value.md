---
title: 設定裝置值 API
description: 瞭解如何使用 Microsoft Defender for Endpoint API 指定裝置的值。
keywords: api、graph api、支援的 api、標記、電腦標記
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498311"
---
# <a name="set-device-value-api"></a><span data-ttu-id="352be-104">設定裝置值 API</span><span class="sxs-lookup"><span data-stu-id="352be-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="352be-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="352be-105">**Applies to:**</span></span>
- [<span data-ttu-id="352be-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="352be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="352be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="352be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="352be-108">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="352be-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="352be-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="352be-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="352be-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="352be-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="352be-111">API 描述</span><span class="sxs-lookup"><span data-stu-id="352be-111">API description</span></span>

<span data-ttu-id="352be-112">設定特定 [電腦](machine.md)的裝置值。</span><span class="sxs-lookup"><span data-stu-id="352be-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="352be-113">請參閱 [指派裝置值](tvm-assign-device-value.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="352be-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="352be-114">限制</span><span class="sxs-lookup"><span data-stu-id="352be-114">Limitations</span></span>

1. <span data-ttu-id="352be-115">您可以根據您設定的保留期間，在上次看到的裝置上進行開機自檢。</span><span class="sxs-lookup"><span data-stu-id="352be-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="352be-116">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="352be-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="352be-117">權限</span><span class="sxs-lookup"><span data-stu-id="352be-117">Permissions</span></span>

<span data-ttu-id="352be-118">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="352be-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="352be-119">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="352be-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="352be-120">許可權類型</span><span class="sxs-lookup"><span data-stu-id="352be-120">Permission type</span></span> |    <span data-ttu-id="352be-121">權限</span><span class="sxs-lookup"><span data-stu-id="352be-121">Permission</span></span>    |    <span data-ttu-id="352be-122">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="352be-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="352be-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="352be-123">Application</span></span> |    <span data-ttu-id="352be-124">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="352be-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="352be-125">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="352be-125">'Read and write all machine information'</span></span>
<span data-ttu-id="352be-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="352be-126">Delegated (work or school account)</span></span> | <span data-ttu-id="352be-127">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="352be-127">Machine.ReadWrite</span></span> | <span data-ttu-id="352be-128">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="352be-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="352be-129">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="352be-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="352be-130">使用者至少必須具備下列角色許可權：「管理安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="352be-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="352be-131">如需詳細資訊，請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊 () </span><span class="sxs-lookup"><span data-stu-id="352be-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="352be-132">使用者必須能夠存取機器（根據電腦群組設定） (請參閱 [建立及管理電腦群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="352be-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="352be-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="352be-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="352be-134">要求標頭</span><span class="sxs-lookup"><span data-stu-id="352be-134">Request headers</span></span>

<span data-ttu-id="352be-135">名稱</span><span class="sxs-lookup"><span data-stu-id="352be-135">Name</span></span> | <span data-ttu-id="352be-136">類型</span><span class="sxs-lookup"><span data-stu-id="352be-136">Type</span></span> | <span data-ttu-id="352be-137">描述</span><span class="sxs-lookup"><span data-stu-id="352be-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="352be-138">授權</span><span class="sxs-lookup"><span data-stu-id="352be-138">Authorization</span></span> | <span data-ttu-id="352be-139">字串</span><span class="sxs-lookup"><span data-stu-id="352be-139">String</span></span> | <span data-ttu-id="352be-140">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="352be-140">Bearer {token}.</span></span> <span data-ttu-id="352be-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="352be-141">**Required**.</span></span>
<span data-ttu-id="352be-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="352be-142">Content-Type</span></span> | <span data-ttu-id="352be-143">string</span><span class="sxs-lookup"><span data-stu-id="352be-143">string</span></span> | <span data-ttu-id="352be-144">application/json。</span><span class="sxs-lookup"><span data-stu-id="352be-144">application/json.</span></span> <span data-ttu-id="352be-145">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="352be-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="352be-146">要求正文</span><span class="sxs-lookup"><span data-stu-id="352be-146">Request body</span></span>

<span data-ttu-id="352be-147">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="352be-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="352be-148">參數</span><span class="sxs-lookup"><span data-stu-id="352be-148">Parameter</span></span> |    <span data-ttu-id="352be-149">類型</span><span class="sxs-lookup"><span data-stu-id="352be-149">Type</span></span>    | <span data-ttu-id="352be-150">描述</span><span class="sxs-lookup"><span data-stu-id="352be-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="352be-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="352be-151">DeviceValue</span></span> |    <span data-ttu-id="352be-152">Enum</span><span class="sxs-lookup"><span data-stu-id="352be-152">Enum</span></span> |    <span data-ttu-id="352be-153">裝置值。</span><span class="sxs-lookup"><span data-stu-id="352be-153">Device value.</span></span> <span data-ttu-id="352be-154">允許的值為： ' Normal '、' Low ' 和 ' High '。</span><span class="sxs-lookup"><span data-stu-id="352be-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="352be-155">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="352be-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="352be-156">回應</span><span class="sxs-lookup"><span data-stu-id="352be-156">Response</span></span>

<span data-ttu-id="352be-157">如果成功，這個方法會傳回 200-Ok 回應碼和回應內文中的更新電腦。</span><span class="sxs-lookup"><span data-stu-id="352be-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="352be-158">範例</span><span class="sxs-lookup"><span data-stu-id="352be-158">Example</span></span>

<span data-ttu-id="352be-159">**請求**</span><span class="sxs-lookup"><span data-stu-id="352be-159">**Request**</span></span>

<span data-ttu-id="352be-160">以下是新增電腦標記之要求的範例。</span><span class="sxs-lookup"><span data-stu-id="352be-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```