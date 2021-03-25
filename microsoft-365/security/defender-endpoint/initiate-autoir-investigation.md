---
title: 開始調查 API
description: 使用此 API 在裝置上開始調查。
keywords: api，graph api，支援的 api，調查
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
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187115"
---
# <a name="start-investigation-api"></a><span data-ttu-id="f62d8-104">開始調查 API</span><span class="sxs-lookup"><span data-stu-id="f62d8-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f62d8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f62d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="f62d8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f62d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f62d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f62d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f62d8-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f62d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f62d8-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f62d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f62d8-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="f62d8-110">API description</span></span>
<span data-ttu-id="f62d8-111">在裝置上開始自動調查。</span><span class="sxs-lookup"><span data-stu-id="f62d8-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="f62d8-112">如需詳細資訊，請參閱 [自動調查一覽](automated-investigations.md) 。</span><span class="sxs-lookup"><span data-stu-id="f62d8-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="f62d8-113">限制</span><span class="sxs-lookup"><span data-stu-id="f62d8-113">Limitations</span></span>
1. <span data-ttu-id="f62d8-114">此 API 的速率限制為每小時50個通話。</span><span class="sxs-lookup"><span data-stu-id="f62d8-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f62d8-115">權限</span><span class="sxs-lookup"><span data-stu-id="f62d8-115">Permissions</span></span>
<span data-ttu-id="f62d8-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="f62d8-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f62d8-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f62d8-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f62d8-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="f62d8-118">Permission type</span></span> |   <span data-ttu-id="f62d8-119">權限</span><span class="sxs-lookup"><span data-stu-id="f62d8-119">Permission</span></span>  |   <span data-ttu-id="f62d8-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f62d8-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f62d8-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="f62d8-121">Application</span></span> |   <span data-ttu-id="f62d8-122">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="f62d8-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="f62d8-123">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="f62d8-123">'Read and write all alerts'</span></span>
<span data-ttu-id="f62d8-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="f62d8-124">Delegated (work or school account)</span></span> | <span data-ttu-id="f62d8-125">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f62d8-125">Alert.ReadWrite</span></span> | <span data-ttu-id="f62d8-126">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="f62d8-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="f62d8-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="f62d8-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f62d8-128">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="f62d8-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f62d8-129">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="f62d8-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="f62d8-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f62d8-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="f62d8-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="f62d8-131">Request headers</span></span>

<span data-ttu-id="f62d8-132">名稱</span><span class="sxs-lookup"><span data-stu-id="f62d8-132">Name</span></span> | <span data-ttu-id="f62d8-133">類型</span><span class="sxs-lookup"><span data-stu-id="f62d8-133">Type</span></span> | <span data-ttu-id="f62d8-134">描述</span><span class="sxs-lookup"><span data-stu-id="f62d8-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f62d8-135">授權</span><span class="sxs-lookup"><span data-stu-id="f62d8-135">Authorization</span></span> | <span data-ttu-id="f62d8-136">字串</span><span class="sxs-lookup"><span data-stu-id="f62d8-136">String</span></span> | <span data-ttu-id="f62d8-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="f62d8-137">Bearer {token}.</span></span> <span data-ttu-id="f62d8-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="f62d8-138">**Required**.</span></span>
<span data-ttu-id="f62d8-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f62d8-139">Content-Type</span></span> | <span data-ttu-id="f62d8-140">string</span><span class="sxs-lookup"><span data-stu-id="f62d8-140">string</span></span> | <span data-ttu-id="f62d8-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="f62d8-141">application/json.</span></span> <span data-ttu-id="f62d8-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="f62d8-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f62d8-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="f62d8-143">Request body</span></span>
<span data-ttu-id="f62d8-144">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="f62d8-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f62d8-145">參數</span><span class="sxs-lookup"><span data-stu-id="f62d8-145">Parameter</span></span> | <span data-ttu-id="f62d8-146">類型</span><span class="sxs-lookup"><span data-stu-id="f62d8-146">Type</span></span>    | <span data-ttu-id="f62d8-147">描述</span><span class="sxs-lookup"><span data-stu-id="f62d8-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="f62d8-148">留言</span><span class="sxs-lookup"><span data-stu-id="f62d8-148">Comment</span></span> |   <span data-ttu-id="f62d8-149">字串</span><span class="sxs-lookup"><span data-stu-id="f62d8-149">String</span></span> |    <span data-ttu-id="f62d8-150">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="f62d8-150">Comment to associate with the action.</span></span> <span data-ttu-id="f62d8-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="f62d8-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="f62d8-152">回應</span><span class="sxs-lookup"><span data-stu-id="f62d8-152">Response</span></span>
<span data-ttu-id="f62d8-153">如果成功，此方法會傳回201在回應內文中建立的回應碼和 [調查](investigation.md) 。</span><span class="sxs-lookup"><span data-stu-id="f62d8-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f62d8-154">範例</span><span class="sxs-lookup"><span data-stu-id="f62d8-154">Example</span></span>

<span data-ttu-id="f62d8-155">**請求**</span><span class="sxs-lookup"><span data-stu-id="f62d8-155">**Request**</span></span>

<span data-ttu-id="f62d8-156">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="f62d8-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
