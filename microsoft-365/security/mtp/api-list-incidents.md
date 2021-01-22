---
title: Microsoft 365 Defender 中的清單事件 API
description: 瞭解如何在 Microsoft 365 Defender 中列出事件 API
keywords: 清單、事件、事件、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932067"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的清單事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 描述

清單事件 API 可讓您針對事件進行排序，以建立明智的網路安全性回應。 它會公開在環境保留政策所指定的時間範圍內，已標出您網路中已標出之事件的集合。 最新的事件會顯示在清單頂端。 每個事件都包含相關警示陣列及其相關實體。

API 支援下列 **OData** 運算子：

- `$filter``lastUpdateTime`、 `createdTime` `status` 和 `assignedTo` 屬性
- `$top`，最大值為 **100**
- `$skip`

## <a name="limitations"></a>限制

1. 頁面大小上限為 **100 個事件**。
2. 要求最高速率為每分鐘 **50 個通話，****以及每小時 1500 個通話**。

## <a name="permissions"></a>權限

呼叫此 API 需要下列其中一種許可權。 若要深入瞭解，包括如何選擇許可權，請參閱 Access [Microsoft 365 Defender API](api-access.md)

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | Incident.Read.all | 讀取所有事件
應用程式 | Incident.ReadWrite.All | 讀取及寫入所有事件
已委派 (公司或學校帳戶)  | Incident.Read | 讀取事件
已委派 (公司或學校帳戶)  | Incident.ReadWrite | 讀取和寫入事件

> [!Note]
> 使用使用者認證取得權杖時：
>
> - 使用者必須擁有入口網站中事件的查看許可權。
> - 回應只會包括使用者受到公開的事件。

## <a name="http-request"></a>HTTP 要求

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
-|-|-
授權 | 字串 | Bearer {token}. **Required**


## <a name="request-body"></a>要求內體

無。

## <a name="response"></a>回應

如果成功，此方法會返回 `200 OK` 回應 [本文中的](api-incident.md) 事件清單。

## <a name="schema-mapping"></a>架構地圖

### <a name="incident-metadata"></a>事件中繼資料

欄位名稱 | 說明 | 範例值
-|-|-
incidentId | 代表事件的唯一識別碼 | 924565
redirectIncidentId | 只有在事件與另一個事件分組時，才填上專案，做為事件處理邏輯的一部分。 | 924569
incidentName | 每個事件都可用的字串值。 | 勒索軟體活動
createdTime | 第一次建立事件的時間。 | 2020-09-06T14：46：57.073333Z
lastUpdateTime | 上次在後端更新事件的時間。<br /><br /> 當您針對事件取回的時間範圍設定要求參數時，可以使用此欄位。 | 2020-09-06T14：46：57.29Z
assignedTo | 事件的擁有者;如果沒有指派擁有者，則為 *Null。* | secop2@contoso.com
分類 | 事件的規格。 屬性值為：*未知**、FalsePositive、TruePositive*  | Unknown
測定 | 指定事件判定。 屬性值為 *：NotAvailable，* *Apt， Malware，* *SecurityPerson您*， *SecurityTesting，* *UnwantedSoftware，* *Other*  | NotAvailable
地位 | 將事件分類 (*為使用中* 或 *已解決) 。* 它可協助組織及管理對事件的回應。 | 作用中
嚴重性 | 表示可能會影響資產。 嚴重性越高，影響越大。 一般來說，高嚴重性的專案需要立即引起注意。<br /><br />下列其中一個值：*資訊、**低*、*中、*高*。 | 中
標籤 | 與事件相關聯的自訂標記陣列，例如，以共同特性為事件群組標標。 | \[\]
警報 | 包含與事件有關之所有警示的陣列，以及其他資訊，例如嚴重性、參與警示的實體，以及警示的來源。 | \[\] (下方查看警示欄位) 

### <a name="alerts-metadata"></a>提醒中繼資料

欄位名稱 | 說明 | 範例值
-|-|-
alertId | 代表警示的唯一識別碼 | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | 代表與此警示相關聯之事件的唯一識別碼 | 924565
serviceSource | 警示的來源服務，例如端點的 Microsoft Defender、Microsoft Cloud App 安全性、身分識別的 Microsoft Defender 或 Office 365 的 Microsoft Defender。 | MicrosoftCloudAppSecurity
creationTime | 第一次建立警示的時間。 | 2020-09-06T14：46：55.7182276Z
lastUpdatedTime | 上次在後端更新警示的時間。 | 2020-09-06T14：46：57.2433333Z
resolvedTime | 警示已解決的時間。 | 2020-09-10T05：22：59Z
firstActivity | 第一次報告後端活動已更新的時間。| 2020-09-04T05：22：59Z
標題 | 每個警示的簡短識別字串值。 | 勒索軟體活動
描述 | 描述每個警示的字串值。 | 使用者測試使用者2 (testUser2@contoso.com) 處理 99 個副檔名結尾為不常副檔名 *的檔案*。 這是一些異常數目的檔案操控，且有潛在的勒索軟體攻擊。
類別 | 以視覺和數值方式查看攻擊在攻擊鏈中的進度。 與 [MITRE ATT&CK™對齊](https://attack.mitre.org/)。 | 影響
地位 | 將警示分類 (*新增、**使用中* 或 *已解決) 。* 它可協助您將通知整理及管理。 | 新增
嚴重性 | 表示可能會影響資產。 嚴重性越高，影響越大。 一般來說，高嚴重性的專案需要立即引起注意。<br>下列其中一個值：*資訊、**低*、*中、*高*。 | 中
investigationId | 此警示所觸發的自動化調查識別碼。 | 1234
investigationState | 調查目前狀態的資訊。 下列其中一個值：Unknown，*已* 終止 *，SuccessfullyRemediaed，* *Queue，* *Failed，* *PartiallyRemediaed，* *running，* *PendingApproval，* *PendingResource，* *PartiallyInvesed，*  *TerminatedByUser，* *TerminatedBySystem， Queued，* *InnerFailure，* *PreexingAlert，* *UnsupportedOs，* *UnsupportedAlertType，* *SuppressedAlert.*  | 不支援的AlertType
分類 | 事件的規格。 屬性值為：*未知**、FalsePositive、TruePositive* 或 *Null*  | Unknown
測定 | 指定事件判定。 屬性值為 *：NotAvailable，* *Apt， Malware，* *SecurityPerson您*， *SecurityTesting，* *UnwantedSoftware，* *Other* or *null*  | 容易
assignedTo | 事件的擁有者;如果沒有指派擁有者，則為 *Null。* | secop2@contoso.com
actorName | 活動群組 ，如果有，則與此警示相關聯。 | 硼
threatFamilyName | 與此警示相關聯的威脅系列。 | Null
mitreTechniques | 符合MITRE ATT 和 [CK&架構™](https://attack.mitre.org/)技術。 | \[\]
設備 | 所有已送出事件相關警示的裝置。 | \[\] (下方查看實體欄位的詳細資訊) 

### <a name="device-format"></a>裝置格式

欄位名稱 | 說明 | 範例值
-|-|-
DeviceId | Microsoft Defender ATP 中指定的裝置識別碼。 | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)中指定的裝置識別碼。 僅適用于加入網域的裝置。 | Null
deviceDnsName | 裝置完整功能變數名稱。 | user5cx.middleeast.corp.contoso.com
osPlatform | 裝置正在作業系統平臺中運作。| WindowsServer2016
os在 | 裝置所作業系統的建立版本。 | 14393
rbacGroupName | 角色 [型存取控制是](https://docs.microsoft.com/azure/role-based-access-control/overview) (裝置) 的 RBAC 群組。 | WDATP-Ring0
firstSeen | 裝置第一次出現的時間。 | 2020-02-06T14：16：01.9330135Z
healthStatus | 裝置的健康狀態。 | 作用中
riskScore | 裝置的風險分數。 | 高
實體 | 所有已識別為所警示一部分或與它相關的實體。 | \[\] (下方查看實體欄位的詳細資訊) 

### <a name="entity-format"></a>實體格式

欄位名稱 | 說明 | 範例值
-|-|-
entityType | 識別為屬於所提供警示之一部分或與它相關之實體。<br>屬性值為 *：User，* *Ip，* *Url，* *File，* *Process，* *MailBox，* *MailMessage，* *MailCluster，* *Registry* | User
sha1 | 如果 entityType 為 *File，則可供使用*。<br>與檔案或程式相關的警示之檔案雜湊。 | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | 如果 entityType 為 *File，則可供使用*。<br>與檔案或程式相關的警示之檔案雜湊。 | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
檔案名 | 如果 entityType 為 *File，則可供使用*。<br>與檔案或程式相關聯的通知的檔案名 | Detector.UnitTests.dll
filePath | 如果 entityType 為 *File，則可供使用*。<br>與檔案或程式相關聯的警示之檔案路徑 | \\C：\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | 如果 entityType 為 *Process，則可用*。 | 24348
processCommandLine | 如果 entityType 為 *Process，則可用*。 | 「您的檔案已經準備好下載檔案 \_1911150169.exe」
processCreationTime | 如果 entityType 為 *Process，則可用*。 | 2020-07-18T03：25：38.5269993Z
parentProcessId | 如果 entityType 為 *Process，則可用*。 | 16840
parentProcessCreationTime | 如果 entityType 為 *Process，則可用*。 | 2020-07-18T02：12：32.8616797Z
ipAddress | 如果 entityType 是 *Ip，則可供使用*。 <br>與網路事件相關聯的警示之 IP 位址，例如與惡意網路目的地 *通訊。* | 62.216.203.204
URL | 如果 entityType 為 *URL，則可供使用*。 <br>與網路事件相關聯的警示 URL，例如，與惡意 *網路* 目的地通訊。 | down.esales360.cn
accountName | 如果 entityType 為 *User，則可供使用*。 | testUser2
domainName | 如果 entityType 為 *User，則可供使用*。 | europe.corp.contoso
userSid | 如果 entityType 為 *User，則可供使用*。 | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | 如果 entityType 為 *User，則可供使用*。 | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | 如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。 | testUser2@contoso.com
mailboxDisplayName | 如果 entityType 為 *MailBox，則可供使用*。 | 測試 User2
mailboxAddress | 如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。 | testUser2@contoso.com
clusterBy | 如果 entityType 是  *MailCluster，則可用*。 | Subject;P2SenderDomain;ContentType
sender | 如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。 | user.abc@mail.contoso.co.in
recipient | 如果 entityType 為 *MailMessage，則可用*。 | testUser2@contoso.com
主題 | 如果 entityType 為 *MailMessage，則可用*。 | \[外部 \] 注意
deliveryAction | 如果 entityType 為 *MailMessage，則可用*。 | 已傳遞
securityGroupId | 如果 entityType 為  *SecurityGroup，則可供使用*。 | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | 如果 entityType 為  *SecurityGroup，則可供使用*。 | 網路組組運算子
registryHive | 如果 entityType 為  *Registry，則可供使用*。 | HKEY \_ LOCAL \_ MACHINE |
registryKey | 如果 entityType 為  *Registry，則可供使用*。 | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | 如果 entityType 為  *Registry，則可供使用*。 | 字串
registryValue | 如果 entityType 為  *Registry，則可供使用*。 | 31-00-00-00
deviceId | 與實體相關的裝置識別碼 ，如果有的話。 | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>範例

**請求**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**回應**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>相關文章

- [存取 Microsoft 365 Defender API](api-access.md)
- [瞭解 API 限制與授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [事件概觀](incidents-overview.md)
- [事件 API](api-incident.md)
- [更新事件 API](api-update-incidents.md)
