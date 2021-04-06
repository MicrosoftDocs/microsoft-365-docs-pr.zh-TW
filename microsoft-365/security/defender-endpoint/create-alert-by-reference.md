---
title: 從事件 API 建立警示
description: 瞭解如何使用 [建立警示 API]，在 Microsoft Defender for Endpoint 中的事件上建立新的警示。
keywords: api、graph api、支援的 api、get、警示、資訊、識別碼
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166442"
---
# <a name="create-alert-api"></a><span data-ttu-id="72c57-104">建立警示 API</span><span class="sxs-lookup"><span data-stu-id="72c57-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72c57-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="72c57-105">**Applies to:**</span></span>
- [<span data-ttu-id="72c57-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="72c57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72c57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72c57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="72c57-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="72c57-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72c57-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="72c57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="72c57-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="72c57-110">API description</span></span>
<span data-ttu-id="72c57-111">在 **事件** 上建立新的 [警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="72c57-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="72c57-112">需要有 **Microsoft Defender For Endpoint 事件** 才能建立警示。</span><span class="sxs-lookup"><span data-stu-id="72c57-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="72c57-113">您必須從要求中的事件提供3個參數： **事件時間**、 **電腦識別碼** 及 **報表識別碼**。</span><span class="sxs-lookup"><span data-stu-id="72c57-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="72c57-114">請參閱下面範例。</span><span class="sxs-lookup"><span data-stu-id="72c57-114">See example below.</span></span>
<br><span data-ttu-id="72c57-115">您可以使用在高級搜尋 API 或入口網站中找到的事件。</span><span class="sxs-lookup"><span data-stu-id="72c57-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="72c57-116">如果在相同的裝置上有相同標題的開啟警示，新建立的警示會與其合併。</span><span class="sxs-lookup"><span data-stu-id="72c57-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="72c57-117">自動調查會在透過 API 建立的提醒上自動啟動。</span><span class="sxs-lookup"><span data-stu-id="72c57-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="72c57-118">限制</span><span class="sxs-lookup"><span data-stu-id="72c57-118">Limitations</span></span>
1. <span data-ttu-id="72c57-119">此 API 的速率限制為每分鐘15次通話。</span><span class="sxs-lookup"><span data-stu-id="72c57-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="72c57-120">權限</span><span class="sxs-lookup"><span data-stu-id="72c57-120">Permissions</span></span>

<span data-ttu-id="72c57-121">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="72c57-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72c57-122">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72c57-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="72c57-123">許可權類型</span><span class="sxs-lookup"><span data-stu-id="72c57-123">Permission type</span></span> |   <span data-ttu-id="72c57-124">權限</span><span class="sxs-lookup"><span data-stu-id="72c57-124">Permission</span></span>  |   <span data-ttu-id="72c57-125">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="72c57-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="72c57-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="72c57-126">Application</span></span> |   <span data-ttu-id="72c57-127">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="72c57-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="72c57-128">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="72c57-128">'Read and write all alerts'</span></span>
<span data-ttu-id="72c57-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="72c57-129">Delegated (work or school account)</span></span> | <span data-ttu-id="72c57-130">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="72c57-130">Alert.ReadWrite</span></span> | <span data-ttu-id="72c57-131">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="72c57-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="72c57-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="72c57-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="72c57-133">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="72c57-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="72c57-134">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="72c57-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="72c57-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="72c57-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="72c57-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="72c57-136">Request headers</span></span>

<span data-ttu-id="72c57-137">名稱</span><span class="sxs-lookup"><span data-stu-id="72c57-137">Name</span></span> | <span data-ttu-id="72c57-138">類型</span><span class="sxs-lookup"><span data-stu-id="72c57-138">Type</span></span> | <span data-ttu-id="72c57-139">描述</span><span class="sxs-lookup"><span data-stu-id="72c57-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="72c57-140">授權</span><span class="sxs-lookup"><span data-stu-id="72c57-140">Authorization</span></span> | <span data-ttu-id="72c57-141">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-141">String</span></span> | <span data-ttu-id="72c57-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="72c57-142">Bearer {token}.</span></span> <span data-ttu-id="72c57-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-143">**Required**.</span></span>
<span data-ttu-id="72c57-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="72c57-144">Content-Type</span></span> | <span data-ttu-id="72c57-145">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-145">String</span></span> | <span data-ttu-id="72c57-146">application/json。</span><span class="sxs-lookup"><span data-stu-id="72c57-146">application/json.</span></span> <span data-ttu-id="72c57-147">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="72c57-148">要求正文</span><span class="sxs-lookup"><span data-stu-id="72c57-148">Request body</span></span>

<span data-ttu-id="72c57-149">在要求內，請提供下列值 (所有必要) ：</span><span class="sxs-lookup"><span data-stu-id="72c57-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="72c57-150">屬性	</span><span class="sxs-lookup"><span data-stu-id="72c57-150">Property</span></span> | <span data-ttu-id="72c57-151">類型</span><span class="sxs-lookup"><span data-stu-id="72c57-151">Type</span></span> | <span data-ttu-id="72c57-152">描述</span><span class="sxs-lookup"><span data-stu-id="72c57-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="72c57-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="72c57-153">eventTime</span></span> | <span data-ttu-id="72c57-154">DateTime (UTC) </span><span class="sxs-lookup"><span data-stu-id="72c57-154">DateTime(UTC)</span></span> | <span data-ttu-id="72c57-155">從高級搜尋取得之事件的確切時間（字串）。</span><span class="sxs-lookup"><span data-stu-id="72c57-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="72c57-156">例如， ```2018-08-03T16:45:21.7115183Z``` **必要**。</span><span class="sxs-lookup"><span data-stu-id="72c57-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="72c57-157">reportId</span><span class="sxs-lookup"><span data-stu-id="72c57-157">reportId</span></span> | <span data-ttu-id="72c57-158">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-158">String</span></span> | <span data-ttu-id="72c57-159">從高級搜尋取得的事件 reportId。</span><span class="sxs-lookup"><span data-stu-id="72c57-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="72c57-160">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-160">**Required**.</span></span>
<span data-ttu-id="72c57-161">machineId</span><span class="sxs-lookup"><span data-stu-id="72c57-161">machineId</span></span> | <span data-ttu-id="72c57-162">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-162">String</span></span> | <span data-ttu-id="72c57-163">識別事件之裝置的識別碼。</span><span class="sxs-lookup"><span data-stu-id="72c57-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="72c57-164">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-164">**Required**.</span></span>
<span data-ttu-id="72c57-165">嚴重性</span><span class="sxs-lookup"><span data-stu-id="72c57-165">severity</span></span> | <span data-ttu-id="72c57-166">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-166">String</span></span> | <span data-ttu-id="72c57-167">警示的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="72c57-167">Severity of the alert.</span></span> <span data-ttu-id="72c57-168">屬性值為：「低 '、' 中」及 ' 高」。</span><span class="sxs-lookup"><span data-stu-id="72c57-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="72c57-169">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-169">**Required**.</span></span>
<span data-ttu-id="72c57-170">標題</span><span class="sxs-lookup"><span data-stu-id="72c57-170">title</span></span> | <span data-ttu-id="72c57-171">String</span><span class="sxs-lookup"><span data-stu-id="72c57-171">String</span></span> | <span data-ttu-id="72c57-172">提醒的標題。</span><span class="sxs-lookup"><span data-stu-id="72c57-172">Title for the alert.</span></span> <span data-ttu-id="72c57-173">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-173">**Required**.</span></span>
<span data-ttu-id="72c57-174">描述</span><span class="sxs-lookup"><span data-stu-id="72c57-174">description</span></span> | <span data-ttu-id="72c57-175">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-175">String</span></span> | <span data-ttu-id="72c57-176">警示的描述。</span><span class="sxs-lookup"><span data-stu-id="72c57-176">Description of the alert.</span></span> <span data-ttu-id="72c57-177">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-177">**Required**.</span></span>
<span data-ttu-id="72c57-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="72c57-178">recommendedAction</span></span>| <span data-ttu-id="72c57-179">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-179">String</span></span> | <span data-ttu-id="72c57-180">在分析警示時，安全性監察官建議採取的動作。</span><span class="sxs-lookup"><span data-stu-id="72c57-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="72c57-181">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="72c57-181">**Required**.</span></span>
<span data-ttu-id="72c57-182">類別</span><span class="sxs-lookup"><span data-stu-id="72c57-182">category</span></span>| <span data-ttu-id="72c57-183">字串</span><span class="sxs-lookup"><span data-stu-id="72c57-183">String</span></span> | <span data-ttu-id="72c57-184">警示的類別。</span><span class="sxs-lookup"><span data-stu-id="72c57-184">Category of the alert.</span></span> <span data-ttu-id="72c57-185">屬性值包括： "General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"InitialAccess"、"LateralMovement"、""、"PrivilegeEscalation"、"SuspiciousActivity"、"持久性"、""、"勒索軟體"、"" （ **必要**）。</span><span class="sxs-lookup"><span data-stu-id="72c57-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="72c57-186">回應</span><span class="sxs-lookup"><span data-stu-id="72c57-186">Response</span></span>

<span data-ttu-id="72c57-187">如果成功，這個方法會傳回 200 OK 及回應內文中的新 [警示](alerts.md) 物件。</span><span class="sxs-lookup"><span data-stu-id="72c57-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="72c57-188">如果找不到具有指定屬性的事件 (_reportId_、 _eventTime_ 及 _MachineId_) -找不到404。</span><span class="sxs-lookup"><span data-stu-id="72c57-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="72c57-189">範例</span><span class="sxs-lookup"><span data-stu-id="72c57-189">Example</span></span>

<span data-ttu-id="72c57-190">**請求**</span><span class="sxs-lookup"><span data-stu-id="72c57-190">**Request**</span></span>

<span data-ttu-id="72c57-191">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="72c57-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```