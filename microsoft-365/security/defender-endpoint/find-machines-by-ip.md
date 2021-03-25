---
title: 依內部 IP API 尋找裝置
description: 在指定的時間戳記之前和之後，在15分鐘的時間範圍內尋找所要求的內部 IP 裝置。
keywords: api，graph api，支援的 api，get，裝置，IP，尋找，尋找裝置，依 ip，ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200434"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="2d606-104">依內部 IP API 尋找裝置</span><span class="sxs-lookup"><span data-stu-id="2d606-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2d606-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2d606-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="2d606-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2d606-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d606-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2d606-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2d606-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="2d606-108">API description</span></span>
<span data-ttu-id="2d606-109">在指定的時間戳記之前和之後的時間範圍內，尋找所要求內部 IP 的 [機器](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="2d606-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="2d606-110">限制</span><span class="sxs-lookup"><span data-stu-id="2d606-110">Limitations</span></span>
1. <span data-ttu-id="2d606-111">指定的時間戳記必須在過去30天內。</span><span class="sxs-lookup"><span data-stu-id="2d606-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="2d606-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="2d606-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2d606-113">權限</span><span class="sxs-lookup"><span data-stu-id="2d606-113">Permissions</span></span>
<span data-ttu-id="2d606-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="2d606-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d606-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2d606-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2d606-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="2d606-116">Permission type</span></span> |   <span data-ttu-id="2d606-117">權限</span><span class="sxs-lookup"><span data-stu-id="2d606-117">Permission</span></span>  |   <span data-ttu-id="2d606-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="2d606-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d606-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="2d606-119">Application</span></span> |   <span data-ttu-id="2d606-120">Read。所有</span><span class="sxs-lookup"><span data-stu-id="2d606-120">Machine.Read.All</span></span> |  <span data-ttu-id="2d606-121">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="2d606-121">'Read all machine profiles'</span></span>
<span data-ttu-id="2d606-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="2d606-122">Application</span></span> |   <span data-ttu-id="2d606-123">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="2d606-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="2d606-124">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="2d606-124">'Read and write all machine information'</span></span>
<span data-ttu-id="2d606-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="2d606-125">Delegated (work or school account)</span></span> | <span data-ttu-id="2d606-126">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="2d606-126">Machine.Read</span></span> | <span data-ttu-id="2d606-127">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="2d606-127">'Read machine information'</span></span>
<span data-ttu-id="2d606-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="2d606-128">Delegated (work or school account)</span></span> | <span data-ttu-id="2d606-129">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2d606-129">Machine.ReadWrite</span></span> | <span data-ttu-id="2d606-130">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="2d606-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="2d606-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="2d606-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="2d606-132">回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2d606-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="2d606-133">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2d606-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="2d606-134">回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2d606-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2d606-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2d606-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="2d606-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="2d606-136">Request headers</span></span>

<span data-ttu-id="2d606-137">名稱</span><span class="sxs-lookup"><span data-stu-id="2d606-137">Name</span></span> | <span data-ttu-id="2d606-138">類型</span><span class="sxs-lookup"><span data-stu-id="2d606-138">Type</span></span> | <span data-ttu-id="2d606-139">描述</span><span class="sxs-lookup"><span data-stu-id="2d606-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d606-140">授權</span><span class="sxs-lookup"><span data-stu-id="2d606-140">Authorization</span></span> | <span data-ttu-id="2d606-141">字串</span><span class="sxs-lookup"><span data-stu-id="2d606-141">String</span></span> | <span data-ttu-id="2d606-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="2d606-142">Bearer {token}.</span></span> <span data-ttu-id="2d606-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2d606-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2d606-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="2d606-144">Request body</span></span>
<span data-ttu-id="2d606-145">空白</span><span class="sxs-lookup"><span data-stu-id="2d606-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2d606-146">回應</span><span class="sxs-lookup"><span data-stu-id="2d606-146">Response</span></span>
<span data-ttu-id="2d606-147">如果成功-200 OK （含回應內的機器清單）。</span><span class="sxs-lookup"><span data-stu-id="2d606-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="2d606-148">如果 timestamp 不在過去30天-400 錯誤的要求中。</span><span class="sxs-lookup"><span data-stu-id="2d606-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="2d606-149">範例</span><span class="sxs-lookup"><span data-stu-id="2d606-149">Example</span></span>

<span data-ttu-id="2d606-150">**請求**</span><span class="sxs-lookup"><span data-stu-id="2d606-150">**Request**</span></span>

<span data-ttu-id="2d606-151">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="2d606-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
