---
title: 取得提醒 API
description: 深入瞭解 Microsoft Defender for Endpoint 中的警示資源類型的方法和屬性。
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
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769806"
---
# <a name="alert-resource-type"></a>警示資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>方法

方法	 |傳回類型 |描述
:---|:---|:---
[取得警示](get-alert-info-by-id.md) | [警示](alerts.md) | 取得單一 [警示](alerts.md) 物件。
[列出警示](get-alerts.md) | [警示](alerts.md) 集合 | 清單 [警示](alerts.md) 收集。
[更新警示](update-alert.md) | [警示](alerts.md) | 更新特定 [警示](alerts.md)。
[批次更新提醒](batch-update-alerts.md) | | 更新批次 [警示](alerts.md)。
[建立警示](create-alert-by-reference.md)|[警示](alerts.md)|根據從 [高級搜尋](run-advanced-query-api.md)取得的事件資料來建立警示。
[清單相關的網域](get-alert-related-domain-info.md)|網域集合| 與警示相關聯的清單 URLs。
[清單相關檔案](get-alert-related-files-info.md) | [檔](files.md) 集合 |  列出與[警示](alerts.md)相關[聯的檔案實體。](files.md)
[清單相關的 Ip](get-alert-related-ip-info.md) | IP 集合 | 列出與警示相關聯的 Ip。
[取得相關的電腦](get-alert-related-machine-info.md) | [機器](machine.md) | 與[警示](alerts.md)相關聯的[電腦](machine.md)。
[取得相關的使用者](get-alert-related-user-info.md) | [使用者](user.md) | 與[警示](alerts.md)相關聯的[使用者](user.md)。


## <a name="properties"></a>屬性

屬性	 |    類型    |    描述
:---|:---|:---
id | 字串 | 警示識別碼。
標題 | String | 警示標題。
描述 | 字串 | 警示描述。
alertCreationTime | 可為 null 的 DateTimeOffset | 在 UTC) 建立警示的日期和時間 (。
lastEventTime | 可為 null 的 DateTimeOffset | 在相同裝置上觸發警示的事件的最後一個出現。
firstEventTime | 可為 null 的 DateTimeOffset | 觸發該裝置上警示的事件第一次出現。
lastUpdateTime | 可為 null 的 DateTimeOffset | 上次更新警示) 日期和時間 (。
resolvedTime | 可為 null 的 DateTimeOffset | 警示狀態變更為「已解決」的日期和時間。
incidentId | 可為 null 的長 | 警示的 [事件](view-incidents-queue.md) 識別碼。
investigationId | 可為 null 的長 | 與提醒相關的 [調查](automated-investigations.md) 識別碼。
investigationState | 可為 null 的列舉 | [調查](automated-investigations.md)的目前狀態。 可能的值為： ' Unknown '、' 終止 '、' SuccessfullyRemediated '、' 良性 '、' Failed '、' PartiallyRemediated '、' PartiallyInvestigated '、' PendingApproval '、' PendingResource '、' TerminatedByUser '、' TerminatedBySystem '、' InnerFailure '、' PreexistingAlert '、' UnsupportedOs '、' UnsupportedAlertType '、' SuppressedAlert '、' '、' '。
分配 | 字串 | 警示的擁有者。
嚴重性 | Enum | 警示的嚴重性。 可能的值為：「未指定的 '、' 資訊」、「低 '、' 中」及 ' High」。
地位 | Enum | 指定警示的目前狀態。 可能的值為：「Unknown '、' New '、' InProgress ' 和 ' 已解析」。
分類 | 可為 null 的列舉 | 警示的規格。 可能的值為： ' Unknown '、' FalsePositive '、' TruePositive '。
測定 | 可為 null 的列舉 | 指定報警的決定。 可能的值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"。
類別| 字串 | 警示的類別。
detectionSource | 字串 | 偵測來源。
threatFamilyName | 字串 | 威脅系列。
threatName | 字串 | 威脅名稱。
machineId | 字串 | 與警示相關聯之 [電腦](machine.md) 實體的識別碼。
computerDnsName | 字串 | [電腦](machine.md) 完全限定名稱。
aadTenantId | 字串 | Azure Active Directory 識別碼。
detectorId | 字串 | 觸發警示的檢測器識別碼。
註解 | 警示批註清單 | 警示 Comment 物件包含： comment string、createdBy string 及 createTime date time。
證據 | 警示證據清單 | 與警示相關的證據。 請參閱下面範例。

### <a name="response-example-for-getting-single-alert"></a>取得單一警示的回應範例：

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
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
}
```
