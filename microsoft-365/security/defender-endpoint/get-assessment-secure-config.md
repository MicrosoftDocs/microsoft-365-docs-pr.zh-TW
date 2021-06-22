---
title: 匯出每個裝置的安全設定評估
description: 傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。
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
ms.openlocfilehash: 7d39dddf4928b3bcb28fb008bcccd83c67f60177
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053176"
---
# <a name="export-secure-configuration-assessment-per-device"></a>匯出每個裝置的安全設定評估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
以每個裝置為基礎，傳回所有設定及其狀態。

有不同的 API 呼叫可取得不同的資料類型。 因為資料量可能很大，所以可供檢索的方式有兩種：

- [匯出安全設定評估 **JSON 回應**](#1-export-secure-configuration-assessment-json-response)： API 將組織中的所有資料都提取為 JSON 回應。 這種方法最適合 _小型組織，且少於 100 K 裝置_。 回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。

- [匯出安全設定評估](#2-export-secure-configuration-assessment-via-files)：透過檔案：此 API 解決方案可讓更快更可靠的資料量增加。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：

  - 呼叫 API 以取得所有組織資料的下載 URLs 清單。

  - 使用下載 URLs 下載所有檔案，並視需要處理資料。

使用 _JSON 回應__或透過_ 檔案 (收集的資料) 目前狀態的目前快照，而且不包含歷史資料。 為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。

> [!Note]
>
> 除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。

## <a name="1-export-secure-configuration-assessment-json-response"></a>1. 匯出 secure configuration 評估 (JSON 回應) 

### <a name="11-api-method-description"></a>1.1 API 方法描述

此 API 回應包含您已公開裝置上的安全設定評估，並傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。

#### <a name="111-limitations"></a>1.1.1 限制

- 頁面大小上限為200000。

- 此 API 的速率限制為每分鐘30個通話，每小時1000個通話。

### <a name="12-permissions"></a>1.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 弱點。 Read。 All | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | 弱點。讀取 | \'讀取威脅及弱點管理弱點資訊\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 參數

- pageSize \( 預設值 = 50000 \) –回應的結果數目

- \$top –傳回的結果數 \( 不會傳回 \@ Odata。 nextLink，因此不會拉入所有資料\)

### <a name="15-properties"></a>1.5 屬性

>[!Note]
>
>- 下表中所定義的屬性依字母順序依屬性識別碼列出。  執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。
>
>- 其他一些欄可能會在回應中傳回。 這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。
>

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
ConfigurationCategory | string | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制 | 安全性控制
ConfigurationId | string | 特定設定的唯一識別碼 | scid-10000
ConfigurationImpact | string | 設定對整個設定分數 (1-10) 的評分影響 | 9 
ConfigurationName | 字串 | 組態的顯示名稱 | 將裝置上線至適用於端點的 Microsoft Defender
ConfigurationSubcategory | string | 設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 | 板載裝置
DeviceId | string | 服務中裝置的唯一識別碼。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。 | johnlaptop.europe.contoso.com
IsApplicable | bool | 指出設定或原則是否適用 | 真
IsCompliant | bool | 指出設定或原則是否已正確設定 | 假
IsExpectedUserImpact | bool | 會指出若要套用設定，是否會影響使用者 | 真
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。 | Windows10
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。 | 伺服器
RecommendationReference | string | 與此軟體相關的建議識別碼參照。 | sca-_-scid-20000
時間 戳 | string | 最近一次在裝置上看到的設定 | 2020-11-03 10：13：34.8476880

### <a name="16-examples"></a>1.6 範例

#### <a name="161-request-example"></a>1.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 回應範例

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. 透過檔案匯出 secure configuration 評估 () 

### <a name="21-api-method-description"></a>2.1 API 方法描述

此 API 回應包含您已公開裝置上的安全設定評估，並傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。

#### <a name="212-limitations"></a>2.1.2 限制

此 API 的速率限制是每分鐘5個通話，每小時20個通話。

### <a name="22-permissions"></a>2.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 弱點。 Read。 All | \'讀取「威脅與弱點管理」弱點資訊\'
委派 (工作或學校帳戶)  | 弱點。讀取 | \'讀取「威脅與弱點管理」弱點資訊\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>參數

- sasValidHours –下載 URLs (最長24小時) 時可有效的小時數。

### <a name="25-properties"></a>2.5 屬性

>[!Note]
>
>- 這些檔案是以多行 Json 格式的 gzip 壓縮 &。
>
>- 下載 URLs 只會在3小時內有效;否則您可以使用參數。
>
>- 為了獲得最大的下載速度，您可以確保從您的資料所在的相同 Azure 地區下載。
>
屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
匯出檔案 | 陣列 \[ 字串\] | 用於存放組織目前快照之檔案的下載 URLs 清單 | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | string | 產生匯出的時間。 | 2021-05-20T08：00： 00Z]

### <a name="26-examples"></a>2.6 範例

#### <a name="261-request-example"></a>2.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 回應範例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>另請參閱

- [匯出每台裝置的評估方法和屬性](get-assessment-methods-properties.md)

- [每個裝置匯出軟體清查評估](get-assessment-software-inventory.md)

- [每個裝置的匯出軟體漏洞評估](get-assessment-software-vulnerabilities.md)

其他相關

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
