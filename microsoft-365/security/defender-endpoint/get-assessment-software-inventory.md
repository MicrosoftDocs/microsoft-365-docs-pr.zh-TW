---
title: 每個裝置匯出軟體清查評估
description: 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。
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
ms.openlocfilehash: 4f2e16acf474d6da8867a6bd392f9e90e0cf166e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984841"
---
# <a name="export-software-inventory-assessment-per-device"></a>每個裝置匯出軟體清查評估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
有不同的 API 呼叫可取得不同的資料類型。 因為資料量可能很大，所以可供檢索的方式有兩種：

- [匯出軟體清查評估 **OData**](#1-export-software-inventory-assessment-odata) API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。 這種方法最適合 _小型組織，且少於 100 K 裝置_。 回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。

- 透過[檔案匯出軟體清查評估](#2-export-software-inventory-assessment-via-files) 此 API 解決方案可讓大量的資料更快速且可靠地進行。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：

  - 呼叫 API 以取得所有組織資料的下載 URLs 清單。

  - 使用下載 URLs 下載所有檔案，並視需要處理資料。

使用 _OData_ _或透過_ 檔案收集 (所收集的資料，) 目前狀態的目前快照，且不包含歷史資料。 為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。

> [!Note]
>
> 除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。

## <a name="1-export-software-inventory-assessment-odata"></a>1. 匯出軟體清查評估 (OData) 

### <a name="11-api-method-description"></a>1.1 API 方法描述

此 API 回應包含每個裝置已安裝軟體的所有資料。 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。

#### <a name="limitations"></a>限制

- 頁面大小上限為200000。

- 此 API 的速率限制為每分鐘30個通話，每小時1000個通話。

### <a name="12-permissions"></a>1.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 已讀取軟體。所有 | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | 軟體. 讀取 | \'讀取威脅及弱點管理弱點資訊\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 參數

- pageSize (預設值 = 50000) –回應的結果數目。

- $top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) 

### <a name="15-properties"></a>1.5 屬性

>[!NOTE]
>
>-每筆記錄大約 0.5 KB 的資料。 為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。

>-在下表中定義的屬性依屬性識別碼列出字母順序。 執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。
>
>-回應中可能傳回其他一些欄。 這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
DeviceId | string | 服務中裝置的唯一識別碼。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。 | johnlaptop.europe.contoso.com
DiskPaths | 陣列 [字串]  | 在裝置上安裝產品的磁片證據。 | [C： \\ (x86) \\ Microsoft \\ Silverlight \\ 應用程式 \\silverlight.exe "] 的程式檔案
EndOfSupportDate | string | 此軟體支援或會結束的日期。 | 2020-12-30
EndOfSupportStatus | string | 支援狀態的結束。 可以包含這些可能的值：無、EOS 版本、即將發生的 EOS 版本、EOS 軟體（即將進行的 EOS 軟體）。 | 即將進行的 EOS
識別碼 | string | 記錄的唯一識別碼。 | 123ABG55_573AG&mnp！
NumberOfWeaknesses | int | 此裝置上的此軟體弱點數目 | 個
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。 | Windows10
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。 | 伺服器
RegistryPaths | 陣列 [字串] | 產品已安裝在裝置中的登錄證據。 | ["HKEY_LOCAL_MACHINE \\軟體 \\ WOW6432Node \\ microsoft \\ Windows \\ CurrentVersion \\ 卸載 \\ microsoft Silverlight "]
SoftwareFirstSeenTimestamp | string | 此軟體第一次出現于此裝置上。 | 2019-04-07 02:06:47
SoftwareName | string | 軟體產品的名稱。 | Silverlight
SoftwareVendor | string | 軟體廠商的名稱。 | 微軟
SoftwareVersion | string | 軟體產品的版本號碼。 | 81.0.4044.138

### <a name="16-examples"></a>1.6 範例

#### <a name="161-request-example"></a>1.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 回應範例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. 透過檔案匯出軟體清查評估 () 

### <a name="21-api-method-description"></a>2.1 API 方法描述

此 API 回應包含每個裝置已安裝軟體的所有資料。 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。

#### <a name="211-limitations"></a>2.1.1 限制

此 API 的速率限制是每分鐘5個通話，每小時20個通話。

### <a name="22-permissions"></a>2.2 許可權

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
---|---|---
應用程式 | 已讀取軟體。所有 | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | 軟體. 讀取 | \'讀取威脅及弱點管理弱點資訊\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>參數

- sasValidHours –下載 URLs (最長24小時內的有效時數) 

### <a name="25-properties"></a>2.5 屬性

>[!Note]
>
>- 這些檔案是以多行 Json 格式的 gzip 壓縮 &。
>
>- 下載 URLs 只會在3小時內有效。 否則您可以使用參數。
>
>_ 若要下載最大的資料下載速度，您可以確定從資料所在的相同 Azure 地區下載。
>
屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
匯出檔案 | 陣列 \[ 字串\] | 用於存放組織目前快照之檔案的下載 URLs 清單 | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | string | 產生匯出的時間。 | 2021-05-20T08：00： 00Z]

### <a name="26-examples"></a>2.6 範例

#### <a name="261-request-example"></a>2.6.1 要求範例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 回應範例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>另請參閱

- [匯出每台裝置的評估方法和屬性](get-assessment-methods-properties.md)

- [匯出每個裝置的安全設定評估](get-assessment-secure-config.md)

- [每個裝置的匯出軟體漏洞評估](get-assessment-software-vulnerabilities.md)

其他相關

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
