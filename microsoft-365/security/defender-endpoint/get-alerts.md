---
title: 清單提醒 API
description: 瞭解如何使用清單警示 API，在 Microsoft Defender for Endpoint 中檢索警示的集合。
keywords: api、graph api、支援的 api、get、警示、最近
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
ms.openlocfilehash: 4da646a52392871cde99271a17ed6eb9111f51ab
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769238"
---
# <a name="list-alerts-api"></a><span data-ttu-id="3f99f-104">清單提醒 API</span><span class="sxs-lookup"><span data-stu-id="3f99f-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f99f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3f99f-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f99f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3f99f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3f99f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f99f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3f99f-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="3f99f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f99f-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3f99f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3f99f-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="3f99f-110">API description</span></span>
<span data-ttu-id="3f99f-111">會檢索警示的集合。</span><span class="sxs-lookup"><span data-stu-id="3f99f-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="3f99f-112">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="3f99f-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="3f99f-113">OData 支援的運算子：</span><span class="sxs-lookup"><span data-stu-id="3f99f-113">OData supported operators:</span></span>
<br><span data-ttu-id="3f99f-114">```$filter``` 于：、、、、 ```alertCreationTime``` ```lastUpdateTime``` ```incidentId``` ```InvestigationId``` ```status``` ```severity``` 和 ```category``` 屬性。</span><span class="sxs-lookup"><span data-stu-id="3f99f-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="3f99f-115">```$top``` 10000的最大值為</span><span class="sxs-lookup"><span data-stu-id="3f99f-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="3f99f-116">```$expand``` 背面 ```evidence```</span><span class="sxs-lookup"><span data-stu-id="3f99f-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="3f99f-117">請參閱[使用 Microsoft Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中的範例</span><span class="sxs-lookup"><span data-stu-id="3f99f-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="3f99f-118">限制</span><span class="sxs-lookup"><span data-stu-id="3f99f-118">Limitations</span></span>
1. <span data-ttu-id="3f99f-119">您可以根據您設定的保留期間，取得最後更新的警示。</span><span class="sxs-lookup"><span data-stu-id="3f99f-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3f99f-120">頁面大小上限為10000。</span><span class="sxs-lookup"><span data-stu-id="3f99f-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="3f99f-121">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3f99f-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3f99f-122">權限</span><span class="sxs-lookup"><span data-stu-id="3f99f-122">Permissions</span></span>
<span data-ttu-id="3f99f-123">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3f99f-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3f99f-124">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3f99f-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3f99f-125">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3f99f-125">Permission type</span></span> |   <span data-ttu-id="3f99f-126">權限</span><span class="sxs-lookup"><span data-stu-id="3f99f-126">Permission</span></span>  |   <span data-ttu-id="3f99f-127">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3f99f-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3f99f-128">應用程式</span><span class="sxs-lookup"><span data-stu-id="3f99f-128">Application</span></span> |   <span data-ttu-id="3f99f-129">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="3f99f-129">Alert.Read.All</span></span> |    <span data-ttu-id="3f99f-130">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="3f99f-130">'Read all alerts'</span></span>
<span data-ttu-id="3f99f-131">應用程式</span><span class="sxs-lookup"><span data-stu-id="3f99f-131">Application</span></span> |   <span data-ttu-id="3f99f-132">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="3f99f-132">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="3f99f-133">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="3f99f-133">'Read and write all alerts'</span></span>
<span data-ttu-id="3f99f-134">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3f99f-134">Delegated (work or school account)</span></span> | <span data-ttu-id="3f99f-135">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="3f99f-135">Alert.Read</span></span> | <span data-ttu-id="3f99f-136">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="3f99f-136">'Read alerts'</span></span>
<span data-ttu-id="3f99f-137">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3f99f-137">Delegated (work or school account)</span></span> | <span data-ttu-id="3f99f-138">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3f99f-138">Alert.ReadWrite</span></span> | <span data-ttu-id="3f99f-139">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="3f99f-139">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="3f99f-140">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="3f99f-140">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3f99f-141">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3f99f-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3f99f-142">回應只會包含與使用者可以存取之裝置相關聯的警示，取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3f99f-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3f99f-143">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3f99f-143">HTTP request</span></span>
```
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="3f99f-144">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3f99f-144">Request headers</span></span>

<span data-ttu-id="3f99f-145">名稱</span><span class="sxs-lookup"><span data-stu-id="3f99f-145">Name</span></span> | <span data-ttu-id="3f99f-146">類型</span><span class="sxs-lookup"><span data-stu-id="3f99f-146">Type</span></span> | <span data-ttu-id="3f99f-147">描述</span><span class="sxs-lookup"><span data-stu-id="3f99f-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f99f-148">授權</span><span class="sxs-lookup"><span data-stu-id="3f99f-148">Authorization</span></span> | <span data-ttu-id="3f99f-149">字串</span><span class="sxs-lookup"><span data-stu-id="3f99f-149">String</span></span> | <span data-ttu-id="3f99f-150">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3f99f-150">Bearer {token}.</span></span> <span data-ttu-id="3f99f-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3f99f-151">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3f99f-152">要求正文</span><span class="sxs-lookup"><span data-stu-id="3f99f-152">Request body</span></span>
<span data-ttu-id="3f99f-153">空白</span><span class="sxs-lookup"><span data-stu-id="3f99f-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3f99f-154">回應</span><span class="sxs-lookup"><span data-stu-id="3f99f-154">Response</span></span>
<span data-ttu-id="3f99f-155">如果成功，這個方法會傳回 200 OK，以及回應內文中的 [警示](alerts.md) 物件清單。</span><span class="sxs-lookup"><span data-stu-id="3f99f-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>


## <a name="example-1---default"></a><span data-ttu-id="3f99f-156">範例 1-預設值</span><span class="sxs-lookup"><span data-stu-id="3f99f-156">Example 1 - Default</span></span>

<span data-ttu-id="3f99f-157">**請求**</span><span class="sxs-lookup"><span data-stu-id="3f99f-157">**Request**</span></span>

<span data-ttu-id="3f99f-158">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3f99f-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

<span data-ttu-id="3f99f-159">**回應**</span><span class="sxs-lookup"><span data-stu-id="3f99f-159">**Response**</span></span>

<span data-ttu-id="3f99f-160">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3f99f-160">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="3f99f-161">在這裡顯示的回應清單可能會因簡潔而截斷。</span><span class="sxs-lookup"><span data-stu-id="3f99f-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="3f99f-162">所有警示都會透過實際通話傳回。</span><span class="sxs-lookup"><span data-stu-id="3f99f-162">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="3f99f-163">範例 2-取得相關證據的10個最新警示</span><span class="sxs-lookup"><span data-stu-id="3f99f-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

<span data-ttu-id="3f99f-164">**請求**</span><span class="sxs-lookup"><span data-stu-id="3f99f-164">**Request**</span></span>

<span data-ttu-id="3f99f-165">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3f99f-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```


<span data-ttu-id="3f99f-166">**回應**</span><span class="sxs-lookup"><span data-stu-id="3f99f-166">**Response**</span></span>

<span data-ttu-id="3f99f-167">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3f99f-167">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="3f99f-168">在這裡顯示的回應清單可能會因簡潔而截斷。</span><span class="sxs-lookup"><span data-stu-id="3f99f-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="3f99f-169">所有警示都會透過實際通話傳回。</span><span class="sxs-lookup"><span data-stu-id="3f99f-169">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```


## <a name="see-also"></a><span data-ttu-id="3f99f-170">請參閱</span><span class="sxs-lookup"><span data-stu-id="3f99f-170">See also</span></span>
- [<span data-ttu-id="3f99f-171">使用 Microsoft Defender for Endpoint OData 查詢</span><span class="sxs-lookup"><span data-stu-id="3f99f-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
