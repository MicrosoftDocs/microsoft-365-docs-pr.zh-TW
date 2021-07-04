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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289460"
---
# <a name="create-alert-api"></a><span data-ttu-id="507d8-104">建立警示 API</span><span class="sxs-lookup"><span data-stu-id="507d8-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="507d8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="507d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="507d8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="507d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="507d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="507d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="507d8-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="507d8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="507d8-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="507d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="507d8-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="507d8-110">API description</span></span>

<span data-ttu-id="507d8-111">在 **事件** 上建立新的 [警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="507d8-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>

- <span data-ttu-id="507d8-112">需要有 **Microsoft Defender For Endpoint 事件** 才能建立警示。</span><span class="sxs-lookup"><span data-stu-id="507d8-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
- <span data-ttu-id="507d8-113">您必須從要求中的事件提供3個參數： **事件時間**、 **電腦識別碼** 及 **報表識別碼**。</span><span class="sxs-lookup"><span data-stu-id="507d8-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="507d8-114">請參閱下面範例。</span><span class="sxs-lookup"><span data-stu-id="507d8-114">See example below.</span></span>
- <span data-ttu-id="507d8-115">您可以使用在高級搜尋 API 或入口網站中找到的事件。</span><span class="sxs-lookup"><span data-stu-id="507d8-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
- <span data-ttu-id="507d8-116">如果在相同的裝置上有相同標題的開啟警示，新建立的警示會與其合併。</span><span class="sxs-lookup"><span data-stu-id="507d8-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
- <span data-ttu-id="507d8-117">自動調查會在透過 API 建立的提醒上自動啟動。</span><span class="sxs-lookup"><span data-stu-id="507d8-117">An automatic investigation starts automatically on alerts created via the API.</span></span>

## <a name="limitations"></a><span data-ttu-id="507d8-118">限制</span><span class="sxs-lookup"><span data-stu-id="507d8-118">Limitations</span></span>

1. <span data-ttu-id="507d8-119">此 API 的速率限制為每分鐘15次通話。</span><span class="sxs-lookup"><span data-stu-id="507d8-119">Rate limitations for this API are 15 calls per minute.</span></span>

## <a name="permissions"></a><span data-ttu-id="507d8-120">權限</span><span class="sxs-lookup"><span data-stu-id="507d8-120">Permissions</span></span>

<span data-ttu-id="507d8-121">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="507d8-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="507d8-122">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="507d8-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="507d8-123">許可權類型</span><span class="sxs-lookup"><span data-stu-id="507d8-123">Permission type</span></span> | <span data-ttu-id="507d8-124">權限</span><span class="sxs-lookup"><span data-stu-id="507d8-124">Permission</span></span> | <span data-ttu-id="507d8-125">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="507d8-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="507d8-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="507d8-126">Application</span></span> | <span data-ttu-id="507d8-127">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="507d8-127">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="507d8-128">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="507d8-128">'Read and write all alerts'</span></span>
<span data-ttu-id="507d8-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="507d8-129">Delegated (work or school account)</span></span> | <span data-ttu-id="507d8-130">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="507d8-130">Alert.ReadWrite</span></span> | <span data-ttu-id="507d8-131">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="507d8-131">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="507d8-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="507d8-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="507d8-133">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="507d8-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="507d8-134">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="507d8-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="507d8-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="507d8-135">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="507d8-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="507d8-136">Request headers</span></span>

<span data-ttu-id="507d8-137">名稱</span><span class="sxs-lookup"><span data-stu-id="507d8-137">Name</span></span> | <span data-ttu-id="507d8-138">類型</span><span class="sxs-lookup"><span data-stu-id="507d8-138">Type</span></span> | <span data-ttu-id="507d8-139">說明</span><span class="sxs-lookup"><span data-stu-id="507d8-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="507d8-140">授權</span><span class="sxs-lookup"><span data-stu-id="507d8-140">Authorization</span></span> | <span data-ttu-id="507d8-141">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-141">String</span></span> | <span data-ttu-id="507d8-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="507d8-142">Bearer {token}.</span></span> <span data-ttu-id="507d8-143">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-143">**Required**.</span></span>
<span data-ttu-id="507d8-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="507d8-144">Content-Type</span></span> | <span data-ttu-id="507d8-145">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-145">String</span></span> | <span data-ttu-id="507d8-146">application/json。</span><span class="sxs-lookup"><span data-stu-id="507d8-146">application/json.</span></span> <span data-ttu-id="507d8-147">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="507d8-148">要求內文</span><span class="sxs-lookup"><span data-stu-id="507d8-148">Request body</span></span>

<span data-ttu-id="507d8-149">在要求內，請提供下列值 (所有必要) ：</span><span class="sxs-lookup"><span data-stu-id="507d8-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="507d8-150">屬性	</span><span class="sxs-lookup"><span data-stu-id="507d8-150">Property</span></span> | <span data-ttu-id="507d8-151">類型</span><span class="sxs-lookup"><span data-stu-id="507d8-151">Type</span></span> | <span data-ttu-id="507d8-152">說明</span><span class="sxs-lookup"><span data-stu-id="507d8-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="507d8-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="507d8-153">eventTime</span></span> | <span data-ttu-id="507d8-154">DateTime (UTC) </span><span class="sxs-lookup"><span data-stu-id="507d8-154">DateTime(UTC)</span></span> | <span data-ttu-id="507d8-155">從高級搜尋取得之事件的確切時間（字串）。</span><span class="sxs-lookup"><span data-stu-id="507d8-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="507d8-156">例如， ```2018-08-03T16:45:21.7115183Z``` **必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="507d8-157">reportId</span><span class="sxs-lookup"><span data-stu-id="507d8-157">reportId</span></span> | <span data-ttu-id="507d8-158">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-158">String</span></span> | <span data-ttu-id="507d8-159">從高級搜尋取得的事件 reportId。</span><span class="sxs-lookup"><span data-stu-id="507d8-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="507d8-160">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-160">**Required**.</span></span>
<span data-ttu-id="507d8-161">machineId</span><span class="sxs-lookup"><span data-stu-id="507d8-161">machineId</span></span> | <span data-ttu-id="507d8-162">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-162">String</span></span> | <span data-ttu-id="507d8-163">識別事件之裝置的識別碼。</span><span class="sxs-lookup"><span data-stu-id="507d8-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="507d8-164">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-164">**Required**.</span></span>
<span data-ttu-id="507d8-165">嚴重性</span><span class="sxs-lookup"><span data-stu-id="507d8-165">severity</span></span> | <span data-ttu-id="507d8-166">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-166">String</span></span> | <span data-ttu-id="507d8-167">警示的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="507d8-167">Severity of the alert.</span></span> <span data-ttu-id="507d8-168">屬性值為：「低 '、' 中」及 ' 高」。</span><span class="sxs-lookup"><span data-stu-id="507d8-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="507d8-169">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-169">**Required**.</span></span>
<span data-ttu-id="507d8-170">標題</span><span class="sxs-lookup"><span data-stu-id="507d8-170">title</span></span> | <span data-ttu-id="507d8-171">String</span><span class="sxs-lookup"><span data-stu-id="507d8-171">String</span></span> | <span data-ttu-id="507d8-172">提醒的標題。</span><span class="sxs-lookup"><span data-stu-id="507d8-172">Title for the alert.</span></span> <span data-ttu-id="507d8-173">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-173">**Required**.</span></span>
<span data-ttu-id="507d8-174">描述</span><span class="sxs-lookup"><span data-stu-id="507d8-174">description</span></span> | <span data-ttu-id="507d8-175">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-175">String</span></span> | <span data-ttu-id="507d8-176">警示的描述。</span><span class="sxs-lookup"><span data-stu-id="507d8-176">Description of the alert.</span></span> <span data-ttu-id="507d8-177">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-177">**Required**.</span></span>
<span data-ttu-id="507d8-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="507d8-178">recommendedAction</span></span>| <span data-ttu-id="507d8-179">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-179">String</span></span> | <span data-ttu-id="507d8-180">在分析警示時，安全性監察官建議採取的動作。</span><span class="sxs-lookup"><span data-stu-id="507d8-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="507d8-181">**必要**。</span><span class="sxs-lookup"><span data-stu-id="507d8-181">**Required**.</span></span>
<span data-ttu-id="507d8-182">類別</span><span class="sxs-lookup"><span data-stu-id="507d8-182">category</span></span>| <span data-ttu-id="507d8-183">字串</span><span class="sxs-lookup"><span data-stu-id="507d8-183">String</span></span> | <span data-ttu-id="507d8-184">警示的類別。</span><span class="sxs-lookup"><span data-stu-id="507d8-184">Category of the alert.</span></span> <span data-ttu-id="507d8-185">屬性值包括： "General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"InitialAccess"、"LateralMovement"、""、"PrivilegeEscalation"、"SuspiciousActivity"、"持久性"、""、"勒索軟體"、"" （ **必要**）。</span><span class="sxs-lookup"><span data-stu-id="507d8-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="507d8-186">回應</span><span class="sxs-lookup"><span data-stu-id="507d8-186">Response</span></span>

<span data-ttu-id="507d8-187">如果成功，這個方法會傳回 200 OK 及回應內文中的新 [警示](alerts.md) 物件。</span><span class="sxs-lookup"><span data-stu-id="507d8-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="507d8-188">如果找不到具有指定屬性的事件 (_reportId_、 _eventTime_ 及 _MachineId_) -找不到404。</span><span class="sxs-lookup"><span data-stu-id="507d8-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="507d8-189">範例</span><span class="sxs-lookup"><span data-stu-id="507d8-189">Example</span></span>

### <a name="request"></a><span data-ttu-id="507d8-190">請求</span><span class="sxs-lookup"><span data-stu-id="507d8-190">Request</span></span>

<span data-ttu-id="507d8-191">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="507d8-191">Here is an example of the request.</span></span>

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
