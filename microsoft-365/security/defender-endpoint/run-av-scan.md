---
title: 執行防病毒掃描 API
description: 使用此 API 來建立與在裝置上執行防病毒掃描有關的呼叫。
keywords: api，graph api，支援的 api，從隔離中移除裝置
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
ms.openlocfilehash: 3df703fd84c87a2bd34bb2a81f8c83063e468b17
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771444"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="98c17-104">執行防病毒掃描 API</span><span class="sxs-lookup"><span data-stu-id="98c17-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98c17-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="98c17-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="98c17-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="98c17-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="98c17-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="98c17-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="98c17-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="98c17-108">API description</span></span>
<span data-ttu-id="98c17-109">在裝置上開始 Microsoft Defender 防毒軟體掃描。</span><span class="sxs-lookup"><span data-stu-id="98c17-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="98c17-110">限制</span><span class="sxs-lookup"><span data-stu-id="98c17-110">Limitations</span></span>
1. <span data-ttu-id="98c17-111">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="98c17-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="98c17-112">權限</span><span class="sxs-lookup"><span data-stu-id="98c17-112">Permissions</span></span>
<span data-ttu-id="98c17-113">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="98c17-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="98c17-114">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="98c17-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="98c17-115">許可權類型</span><span class="sxs-lookup"><span data-stu-id="98c17-115">Permission type</span></span> |   <span data-ttu-id="98c17-116">權限</span><span class="sxs-lookup"><span data-stu-id="98c17-116">Permission</span></span>  |   <span data-ttu-id="98c17-117">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="98c17-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="98c17-118">應用程式</span><span class="sxs-lookup"><span data-stu-id="98c17-118">Application</span></span> |   <span data-ttu-id="98c17-119">電腦。掃描</span><span class="sxs-lookup"><span data-stu-id="98c17-119">Machine.Scan</span></span> |  <span data-ttu-id="98c17-120">「掃描電腦」</span><span class="sxs-lookup"><span data-stu-id="98c17-120">'Scan machine'</span></span>
<span data-ttu-id="98c17-121">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="98c17-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="98c17-122">電腦。掃描</span><span class="sxs-lookup"><span data-stu-id="98c17-122">Machine.Scan</span></span> |  <span data-ttu-id="98c17-123">「掃描電腦」</span><span class="sxs-lookup"><span data-stu-id="98c17-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="98c17-124">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="98c17-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="98c17-125">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="98c17-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="98c17-126">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="98c17-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="98c17-127">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="98c17-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="98c17-128">要求標頭</span><span class="sxs-lookup"><span data-stu-id="98c17-128">Request headers</span></span>

<span data-ttu-id="98c17-129">名稱</span><span class="sxs-lookup"><span data-stu-id="98c17-129">Name</span></span> | <span data-ttu-id="98c17-130">類型</span><span class="sxs-lookup"><span data-stu-id="98c17-130">Type</span></span> | <span data-ttu-id="98c17-131">描述</span><span class="sxs-lookup"><span data-stu-id="98c17-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="98c17-132">授權</span><span class="sxs-lookup"><span data-stu-id="98c17-132">Authorization</span></span> | <span data-ttu-id="98c17-133">字串</span><span class="sxs-lookup"><span data-stu-id="98c17-133">String</span></span> | <span data-ttu-id="98c17-134">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="98c17-134">Bearer {token}.</span></span> <span data-ttu-id="98c17-135">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="98c17-135">**Required**.</span></span>
<span data-ttu-id="98c17-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="98c17-136">Content-Type</span></span> | <span data-ttu-id="98c17-137">string</span><span class="sxs-lookup"><span data-stu-id="98c17-137">string</span></span> | <span data-ttu-id="98c17-138">application/json</span><span class="sxs-lookup"><span data-stu-id="98c17-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="98c17-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="98c17-139">Request body</span></span>
<span data-ttu-id="98c17-140">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="98c17-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="98c17-141">參數</span><span class="sxs-lookup"><span data-stu-id="98c17-141">Parameter</span></span> | <span data-ttu-id="98c17-142">類型</span><span class="sxs-lookup"><span data-stu-id="98c17-142">Type</span></span>    | <span data-ttu-id="98c17-143">描述</span><span class="sxs-lookup"><span data-stu-id="98c17-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="98c17-144">留言</span><span class="sxs-lookup"><span data-stu-id="98c17-144">Comment</span></span> |   <span data-ttu-id="98c17-145">字串</span><span class="sxs-lookup"><span data-stu-id="98c17-145">String</span></span> | <span data-ttu-id="98c17-146">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="98c17-146">Comment to associate with the action.</span></span> <span data-ttu-id="98c17-147">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="98c17-147">**Required**.</span></span>
<span data-ttu-id="98c17-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="98c17-148">ScanType</span></span>|   <span data-ttu-id="98c17-149">字串</span><span class="sxs-lookup"><span data-stu-id="98c17-149">String</span></span>  | <span data-ttu-id="98c17-150">定義掃描類型。</span><span class="sxs-lookup"><span data-stu-id="98c17-150">Defines the type of the Scan.</span></span> <span data-ttu-id="98c17-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="98c17-151">**Required**.</span></span>

<span data-ttu-id="98c17-152">**ScanType** 控制要執行的掃描類型，可為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="98c17-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="98c17-153">**Quick** –在裝置上執行快速掃描</span><span class="sxs-lookup"><span data-stu-id="98c17-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="98c17-154">**Full** –在裝置上執行完整掃描</span><span class="sxs-lookup"><span data-stu-id="98c17-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="98c17-155">回應</span><span class="sxs-lookup"><span data-stu-id="98c17-155">Response</span></span>
<span data-ttu-id="98c17-156">如果成功，這個方法會傳回201、在回應內文中建立的回應碼和 _MachineAction_ 物件。</span><span class="sxs-lookup"><span data-stu-id="98c17-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="98c17-157">範例</span><span class="sxs-lookup"><span data-stu-id="98c17-157">Example</span></span>

<span data-ttu-id="98c17-158">**請求**</span><span class="sxs-lookup"><span data-stu-id="98c17-158">**Request**</span></span>

<span data-ttu-id="98c17-159">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="98c17-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

