---
title: Microsoft 365 Defender 中的列出事件 API
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572150"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的列出事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。


## <a name="api-description"></a>API 描述

清單事件 API 可讓您排序事件，以建立已獲悉的 cybersecurity 回應。 它會針對您在環境保留原則中所指定的時間範圍內，公開網路上所標示的事件集合。 最近的事件會顯示在清單頂端。 每個事件都包含相關警示的陣列及其相關實體。

API 支援下列 **OData** 運算子：

- `$filter` 在 `lastUpdateTime` 、、 `createdTime` `status` 、和 `assignedTo` 屬性
- `$top`，最大值為 **100**
- `$skip`

## <a name="limitations"></a>限制

1. 頁面大小上限為 **100 事件**。
2. 要求的最大速率為 **每分鐘50個通話** ， **每小時1500個通話**。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱[Access Microsoft 365 Defender APIs](api-access.md)

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | Incident。已讀取。所有 | 讀取所有事件
應用程式 | Incident。 ReadWrite。 | 讀取和寫入所有事件
委派 (工作或學校帳戶)  | 事件。讀取 | 讀取事件
委派 (工作或學校帳戶)  | Incident。 ReadWrite | 讀取和寫入事件

> [!Note]
> 使用使用者認證取得權杖時：
>
> - 使用者必須要有入口網站中的事件的「查看」許可權。
> - 回應只會包含使用者所公開的事件。

## <a name="http-request"></a>HTTP 要求

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
-|-|-
授權 | 字串 | 載荷 {token}。 **Required**


## <a name="request-body"></a>要求正文

無。

## <a name="response"></a>回應

如果成功，此方法會傳回 `200 OK` ，以及回應內文中的 [事件](api-incident.md) 清單。

## <a name="schema-mapping"></a>架構對應

### <a name="incident-metadata"></a>事件中繼資料

欄位名稱 | 描述 | 範例值
-|-|-
incidentId | 代表事件的唯一識別碼 | 924565
redirectIncidentId | 只會填入事件處理邏輯的一部分，以案例事件與另一個事件群組在一起。 | 924569
incidentName | 每個事件可用的字串值。 | 勒索軟體活動
createdTime | 第一次建立事件的時間。 | 2020-09-06T14：46： 57.0733333 Z
lastUpdateTime | 最後在後端更新事件的時間。<br /><br /> 當您為已檢索事件的時間範圍設定要求參數時，可以使用此欄位。 | 2020-09-06T14：46： 57.29 Z
分配 | 事件的擁有者，如果未指派任何擁有者，則 *為 null* 。 | secop2@contoso.com
分類 | 事件的規格。 屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive* | Unknown
測定 | 指定事件的確定。 屬性值為： *NotAvailable*、 *Apt*、 *惡意* 代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *其他* | NotAvailable
地位 | 將事件分類 (*為使用* 中，或 *已解決*) 。 它可以協助您組織和管理事件的回應。 | 作用中
嚴重性 | 會指出對資產的可能影響。 嚴重程度越高，影響越大。 通常較高的嚴重性專案需要最直接的注意。<br /><br />下列其中一個值： *資訊*、 *低*、* 中和 *高*。 | 中
標籤 | 與事件關聯之自訂標記的陣列，例如，用來標示具有共同特性的事件群組。 | \[\]
註解 | Secops 在管理事件時所建立的批註陣列，例如有關分類選項的其他資訊。 | \[\]
警報 | 包含與該事件相關的所有警示的陣列，以及其他資訊，例如嚴重性、警示中所涉及的實體及警示來源。 | \[\] (查看以下警示欄位的詳細資料) 

### <a name="alerts-metadata"></a>警示中繼資料

欄位名稱 | 描述 | 範例值
-|-|-
為 alertid | 代表警示的唯一識別碼 | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | 代表此警示相關聯之事件的唯一識別碼 | 924565
serviceSource | 警示產生來源的服務，例如 microsoft defender for Endpoint、Microsoft Cloud App Security、microsoft defender 身分識別或 microsoft defender for Office 365。 | MicrosoftCloudAppSecurity
creationTime | 第一次建立警示的時間。 | 2020-09-06T14：46： 55.7182276 Z
lastUpdatedTime | 後端最後更新警示的時間。 | 2020-09-06T14：46： 57.2433333 Z
resolvedTime | 解決警示的時間。 | 2020-09-10T05：22：59Z
firstActivity | 警示第一次報告在後端更新活動的時間。| 2020-09-04T05：22：59Z
標題 | 可用於每個警示的簡短識別字串值。 | 勒索軟體活動
描述 | 描述每個警示的字串值。 | User Test 使用者 2 (testUser2@contoso.com) 會操縱使用多個副檔名（以不 *常見副檔名為* 結尾）的99檔案。 這是不尋常的檔案運算元目，也表示有潛在的勒索軟體攻擊。
類別 | 攻擊在終止鏈中的進展程度的視覺和數值視圖。 對應至 [MITRE ATT&CK™ framework](https://attack.mitre.org/)。 | 影響
地位 | 將警示分類 (為新 *、使用中或**已解決*) 。 它可以協助您組織和管理提醒的回應。 | 新增
嚴重性 | 會指出對資產的可能影響。 嚴重程度越高，影響越大。 通常較高的嚴重性專案需要最直接的注意。<br>下列其中一個值： *資訊*、 *低*、* 中和 *高*。 | 中
investigationId | 此警示所觸發的自動調查識別碼。 | 1234
investigationState | 調查目前狀態的資訊。 下列其中一個值： *Unknown*、*離職*、 *SuccessfullyRemediated*、*良性*、*失敗*、 *PartiallyRemediated*、執行 *、* *PendingApproval*、 *PendingResource*、 *PartiallyInvestigated*、 *TerminatedByUser*、 *TerminatedBySystem*、InnerFailure *、PreexistingAlert*、UnsupportedOs、UnsupportedAlertType、SuppressedAlert、 *、*、、、、、、、     | UnsupportedAlertType
分類 | 事件的規格。 屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive* 或 *null* | Unknown
測定 | 指定事件的確定。 屬性值為： *NotAvailable*、 *Apt*、 *惡意* 代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other* 或  *null* | 容易
分配 | 事件的擁有者，如果未指派任何擁有者，則 *為 null* 。 | secop2@contoso.com
actorName | 與此警示相關聯的活動群組（若有的話）。 | 硼
threatFamilyName | 與此警示相關聯的威脅系列。 | Null
mitreTechniques | 攻擊技巧，與 [MITRE ATT&](https://attack.mitre.org/)™ framework 對齊。 | \[\]
設備 | 傳送與該事件相關之提醒的所有裝置。 | \[\] (查看下列實體欄位的詳細資料) 

### <a name="device-format"></a>裝置格式

欄位名稱 | 描述 | 範例值
-|-|-
DeviceId | 在 Microsoft Defender for Endpoint 中指定的裝置識別碼。 | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)中指定的裝置識別碼。 僅適用于已加入網域的裝置。 | Null
deviceDnsName | 裝置的完整功能變數名稱。 | user5cx.middleeast.corp.contoso.com
osPlatform | 裝置正在執行的作業系統平臺。| WindowsServer2016
osBuild | 裝置執行的 OS 組建版本。 | 14393
rbacGroupName | 以 [角色為基礎的存取控制](/azure/role-based-access-control/overview) (與裝置相關聯的 RBAC) 群組。 | WDATP-Ring0
firstSeen | 第一次看到裝置的時間。 | 2020-02-06T14：16： 01.9330135 Z
healthStatus | 裝置的健康狀態。 | 作用中
riskScore | 裝置的風險分數。 | 高
實體 | 已識別為特定警示之一部分或與其相關的所有實體。 | \[\] (查看下列實體欄位的詳細資料) 

### <a name="entity-format"></a>實體格式

欄位名稱 | 描述 | 範例值
-|-|-
entityType | 識別為屬於指定警示或與其相關的實體。<br>屬性值包括： *User*， *Ip*， *Url*， *File*， *Process*， *MailBox*， *MailMessage*， *MailCluster*， *Registry* | 使用者
sha1 | 當 entityType 為 *File* 時可用。<br>與檔案或處理常式相關聯之警示的檔案雜湊。 | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | 當 entityType 為 *File* 時可用。<br>與檔案或處理常式相關聯之警示的檔案雜湊。 | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
檔案名 | 當 entityType 為 *File* 時可用。<br>與檔案或處理常式相關聯的警示檔案名 | Detector.UnitTests.dll
filePath | 當 entityType 為 *File* 時可用。<br>與檔案或處理常式相關聯之警示的檔路徑 | C： \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 Out
Id | 可用於 entityType 為 *處理* 程式。 | 24348
processCommandLine | 可用於 entityType 為 *處理* 程式。 | 「檔案可供下載1911150169.exe」 \_
processCreationTime | 可用於 entityType 為 *處理* 程式。 | 2020-18T03：25： 38.5269993 Z
parentProcessId | 可用於 entityType 為 *處理* 程式。 | 16840
parentProcessCreationTime | 可用於 entityType 為 *處理* 程式。 | 2020-07-18T02：12： 32.8616797 Z
址 | 可在 entityType 為 *Ip* 時使用。 <br>與網路事件相關聯之警示的 IP 位址，例如與 *惡意網路目標的通訊*。 | 62.216.203.204
URL | 可供 entityType 為 *Url*。 <br>與網路事件相關聯之警示的 Url，例如， *與惡意網路目標的通訊*。 | down.esales360.cn
名 | 當 entityType 為 *User* 時可用。 | testUser2
domainName | 當 entityType 為 *User* 時可用。 | 東歐公司 contoso
userSid | 當 entityType 為 *User* 時可用。 | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | 當 entityType 為 *User* 時可用。 | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | 當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。 | testUser2@contoso.com
mailboxDisplayName | 在 *MailBox* entityType 時可用。 | 測試使用者2
mailboxAddress | 當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。 | testUser2@contoso.com
clusterBy | 可用於  *MailCluster* 的 entityType。 | 話題P2SenderDomain;ContentType
sender | 當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。 | user.abc@mail.contoso.co.in
recipient | 在 *MailMessage* entityType 時可用。 | testUser2@contoso.com
主題 | 在 *MailMessage* entityType 時可用。 | \[外部 \] 注意
deliveryAction | 在 *MailMessage* entityType 時可用。 | 已傳遞
securityGroupId | 在  *SecurityGroup* entityType 時可用。 | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | 在  *SecurityGroup* entityType 時可用。 | 網路設定運算子
registryHive | 當 entityType 為  *Registry* 時可用。 | HKEY \_ 本機 \_ 電腦 |
registryKey | 當 entityType 為  *Registry* 時可用。 | SOFTWARE\Microsoft\ Windows NT \CurrentVersion\Winlogon
registryValueType | 當 entityType 為  *Registry* 時可用。 | 字串
registryValue | 當 entityType 為  *Registry* 時可用。 | 31-00-00-00
deviceId | 與實體相關之裝置的識別碼（如果有的話）。 | 986e5df8b73dacd43c8917d17e523e76b13c75cd

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

- [存取 Microsoft 365 Defender APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [事件概觀](incidents-overview.md)
- [事件 API](api-incident.md)
- [更新事件 API](api-update-incidents.md)
