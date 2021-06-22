---
title: 每個裝置的匯出軟體漏洞評估
description: API 回應是每個裝置，並包含您已公開裝置上安裝的易受攻擊軟體，以及這些軟體產品中的任何已知弱點。 本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。
keywords: api、api、export 評估、每個裝置評估、弱點評定報告、裝置弱點評估、裝置弱點報告、安全設定評估、安全設定報告、軟體漏洞評估、軟體弱點報告、依機器的弱點報告
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052960"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>每個裝置的匯出軟體漏洞評估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
以每個裝置為基礎，傳回所有裝置的所有已知軟體弱點及其詳細資料。

有不同的 API 呼叫可取得不同的資料類型。 因為資料量可能非常大，所以可供檢索的方式有兩種：

1. [匯出軟體漏洞評估 **JSON 回應**](#1-export-software-vulnerabilities-assessment-json-response)  API 將組織中的所有資料都提取為 Json 回應。 這種方法適用于 _低於 100 K 裝置的小型組織_。 回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。

2. 透過檔案[匯出軟體漏洞評估](#2-export-software-vulnerabilities-assessment-via-files)此 API 解決方案可讓大量的資料更快速且可靠地進行。 針對大型組織，建議使用透過檔案，且包含超過 100 K 個裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：

   - 呼叫 API 以取得所有組織資料的下載 URLs 清單。

   - 使用下載 URLs 下載所有檔案，並視需要處理資料。

3. [Delta export 軟體漏洞評估 **JSON 回應**](#3-delta-export-software-vulnerabilities-assessment-json-response)  會傳回表格，其中每個唯一的組合： DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 及 EventTimestamp。
API 將組織中的資料提取為 Json 回應。 回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。 <br><br> 與完整的「軟體弱點評估 (JSON 回應) 」（用來取得組織之軟體漏洞評估的整個快照）不同，「增量匯出 API 呼叫」是用來只提取選取日期和目前日期之間所發生的變更， ("delta" API 呼叫) 。 您不需要每次獲得大量資料的完整匯出，只會取得新的、已修復和更新之弱點的特定資訊。 Delta export JSON 回應 API 通話也可以用來計算不同的 KPIs 例如「修復多少個漏洞？」。 或「我的組織新增了多少個新的漏洞？」 <br><br> 因為軟體弱點的 Delta export JSON 回應 API 呼叫只會傳回目標日期範圍的資料，所以不會被視為 _完整匯出_。

使用 _Json 回應__或透過_ 檔案 (收集的資料) 目前狀態的目前快照，而且不包含歷史資料。 為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。

> [!Note]
>
> 除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. 匯出軟體漏洞評估 (JSON 回應) 

### <a name="11-api-method-description"></a>1.1 API 方法描述

此 API 回應包含每個裝置已安裝軟體的所有資料。 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。

#### <a name="111-limitations"></a>1.1.1 限制

- 頁面大小上限為200000。

- 此 API 的速率限制為每分鐘30個通話，每小時1000個通話。

### <a name="12-permissions"></a>1.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 弱點。 Read。 All | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | 弱點。讀取 | \'讀取威脅及弱點管理弱點資訊\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 參數

- pageSize (預設值 = 50000) –回應的結果數目
- $top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) 

### <a name="15-properties"></a>1.5 屬性

>[!Note]
>
>- 每筆記錄大約是 1 KB 的資料。 為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。
>
>- 其他一些欄可能會在回應中傳回。 這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。
>
>- 下表中所定義的屬性依字母順序依屬性識別碼列出。  執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。

<br/>

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
CveId | string | 指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。 | CVE-2020-15992
CvssScore | string | CVE 的 CVSS 分數。 | 6.2
DeviceId | string | 服務中裝置的唯一識別碼。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。 | johnlaptop.europe.contoso.com
DiskPaths  | 陣列 \[ 字串\] | 在裝置上安裝產品的磁片證據。 | ["C:\Program (x86) \Microsoft\Silverlight\Application\silverlight.exe 的檔案]]
ExploitabilityLevel | string | 此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)  | ExploitIsInKit
FirstSeenTimestamp | string | 第一次在裝置上看到此項產品的 CVE。 | 2020-11-03 10：13：34.8476880
識別碼 | string | 記錄的唯一識別碼。 | 123ABG55_573AG&mnp！
LastSeenTimestamp | string | 最後一次在裝置上看到 CVE。 | 2020-11-03 10：13：34.8476880
OSPlatform | string | 裝置上所執行作業系統的平臺。 此屬性會指出特定的作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。 | Windows10
RbacGroupName  | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。 | 伺服器
RecommendationReference | string | 與此軟體相關的建議識別碼參照。 | va-_-_ silverlight
RecommendedSecurityUpdate (選用)  | string | 軟體廠商提供的安全性更新名稱或描述，以解決此弱點。 | 2020年4月安全性更新
RecommendedSecurityUpdateId (選用)  | string | 對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼 | 4550961
RegistryPaths  | 陣列 \[ 字串\] | 產品已安裝在裝置中的登錄證據。 | ["HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"]
SoftwareName | string | 軟體產品的名稱。 | 鉻
SoftwareVendor | string | 軟體廠商的名稱。 | 谷歌
SoftwareVersion | string | 軟體產品的版本號碼。 | 81.0.4044.138
VulnerabilitySeverityLevel  | string | 依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。 | 中

### <a name="16-examples"></a>1.6 範例

#### <a name="161-request-example"></a>1.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 回應範例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. 透過檔案匯出軟體漏洞評估 () 

### <a name="21-api-method-description"></a>2.1 API 方法描述

此 API 回應包含每個裝置已安裝軟體的所有資料。 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。

#### <a name="212-limitations"></a>2.1.2 限制

此 API 的速率限制是每分鐘5個通話，每小時20個通話。

### <a name="22-permissions"></a>2.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊](apis-intro.md)。

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 弱點。 Read。 All | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | 弱點。讀取 | \'讀取威脅及弱點管理弱點資訊\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 參數

- sasValidHours –下載 URLs (最長24小時內的有效時數) 

### <a name="25-properties"></a>2.5 屬性

>[!Note]
>
>- 這些檔案是以多行 Json 格式的 gzip 壓縮 &。
>
>- 下載 URLs 只會在3小時內有效;否則您可以使用參數。
>
>- 為了獲得最大的下載速度，您可以確保從您的資料所在的相同 Azure 地區下載。
>

>[!Note]
>
>- 每筆記錄大約是1KB 的資料。 為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。
>
>- 其他一些欄可能會在回應中傳回。 這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。
>

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
匯出檔案 | 陣列 \[ 字串\]  | 用於存放組織目前快照之檔案的下載 URLs 清單。 | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | 產生匯出的時間。 | 2021-05-20T08：00：00Z

### <a name="26-examples"></a>2.6 範例

#### <a name="261-request-example"></a>2.6.1 要求範例

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 回應範例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. 增量匯出軟體漏洞評估 (JSON 回應) 

### <a name="31-api-method-description"></a>3.1 API 方法描述

會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 的每個唯一組合的專案。 API 將組織中的資料提取為 Json 回應。 回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。 與完整的軟體漏洞評估 (JSON 回應) （用來取得組織的軟體漏洞評估整個快照）不同時，會使用 delta export JSON 回應 API 呼叫，只提取選取日期和目前日期之間所發生的變更， ("delta" API 呼叫) 。 您不需要每次獲得大量資料的完整匯出，只會取得新的、已修復和更新之弱點的特定資訊。 Delta export JSON 回應 API 通話也可以用來計算不同的 KPIs 例如「修復多少個漏洞？」。 或「我的組織新增了多少個新的漏洞？」

>[!NOTE]
>
>強烈建議您在一周內至少使用一次裝置 API 呼叫的完整匯出軟體漏洞評估，而裝置 (delta) API 將此額外的匯出軟體弱點變更為一周的所有其他日子。  與其他評估 JSON 回應 APIs 不同的是，「delta export」不是完整匯出。 Delta export 只會包含選取日期和目前日期之間所發生的變更 (「delta」 API 呼叫) 。

#### <a name="311-limitations"></a>3.1.1 限制

- 頁面大小上限為200000。

- SinceTime 參數的最大值為14天。

- 此 API 的速率限制為每分鐘30個通話，每小時1000個通話。

### <a name="32-permissions"></a>3.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 弱點。 Read。 All | 「讀取威脅及弱點管理弱點資訊」
委派 (工作或學校帳戶)  | 弱點。讀取 | 「讀取威脅及弱點管理弱點資訊」

### <a name="33-url"></a>3.3 URL

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a>3.4 參數

- sinceTime (必要) –所選時間與今天之間的資料。
- pageSize (預設值 = 50000) –回應的結果數目
- $top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) 

### <a name="35-properties"></a>3.5 屬性

每個傳回的記錄包含由裝置 API 完整匯出軟體漏洞評估中的所有資料，另外還有兩個額外的欄位：  _**EventTimestamp**_ 和 _**Status**_。

>[!NOTE]
>- 其他一些欄可能會在回應中傳回。 這些欄是暫存檔的，而且可能會被移除，所以請只使用記錄的資料行。
>
>- 下表中所定義的屬性依字母順序依屬性識別碼列出。  執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。
<br><br/>

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
CveId | string | 指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。 | CVE-2020-15992  
CvssScore | string | CVE 的 CVSS 分數。 | 6.2  
DeviceId | string | 服務中裝置的唯一識別碼。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。 | johnlaptop.europe.contoso.com  
DiskPaths | 陣列 [字串] | 在裝置上安裝產品的磁片證據。 | ["C:\Program (x86) \Microsoft\Silverlight\Application\silverlight.exe 的檔案]]  
EventTimestamp | 字串 | 找到此 delta 事件的時間。 | 2021-01-11T11：06： 08.291 Z
ExploitabilityLevel | string | 此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)  | ExploitIsInKit  
FirstSeenTimestamp | string | 第一次在裝置上看到此項產品的 CVE。 | 2020-11-03 10：13：34.8476880  
識別碼 | string | 記錄的唯一識別碼。 | 123ABG55_573AG&mnp！  
LastSeenTimestamp | string | 最後一次在裝置上看到 CVE。 | 2020-11-03 10：13：34.8476880  
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。 | Windows10  
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。 | 伺服器  
RecommendationReference | string | 與此軟體相關的建議識別碼參照。 | va--silverlight  
RecommendedSecurityUpdate  | string | 軟體廠商提供的安全性更新名稱或描述，以解決此弱點。 | 2020年4月安全性更新  
RecommendedSecurityUpdateId  | string | 對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼 | 4550961  
RegistryPaths  | 陣列 [字串] | 產品已安裝在裝置中的登錄證據。 | ["HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome"]  
SoftwareName | string | 軟體產品的名稱。 | 鉻  
SoftwareVendor | string | 軟體廠商的名稱。 | 谷歌  
SoftwareVersion | string | 軟體產品的版本號碼。 | 81.0.4044.138  
狀態 | 字串 | **新**  針對裝置上引進的新弱點 ()  (1) **固定**   (如果此弱點不再存在於裝置上，表示它已修正) 。  (2)  **更新**，   (如果裝置上的某個弱點已變更。 可能的變更如下： CVSS 評分、exploitability 層級、嚴重性層級、DiskPaths、RegistryPaths、RecommendedSecurityUpdate) 。 | Fixed
VulnerabilitySeverityLevel | string | 依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。 | 中  

#### <a name="clarifications"></a>澄清

- 若軟體從版本1.0 更新為版本2.0，而且這兩個版本都會公開至 CVE-A，您會收到2個不同的事件：  
   1. 固定– CVE-已修正版本1。0  
   1. 新增– CVE-已新增版本2。0

- 例如，如果特定弱點 (例如，在特定時間內第一 (次看到) （例如，1.0 年1月10日) ），而軟體更新至版本2.0 （也是對相同的 CVE-A 所公開），您將會收到這兩個分隔的事件：  
   1. Fixed – CVE-X，FirstSeenTimestamp 年1月10日，第1版，0。  
   1. 新增– CVE-X，FirstSeenTimestamp 年1月10日，版本2.0。

### <a name="36-examples"></a>3.6 範例

#### <a name="361-request-example"></a>3.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 回應範例

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a>另請參閱

- [匯出每台裝置的評估方法和屬性](get-assessment-methods-properties.md)

- [匯出每個裝置的安全設定評估](get-assessment-secure-config.md)

- [每個裝置匯出軟體清查評估](get-assessment-software-inventory.md)

其他相關

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
