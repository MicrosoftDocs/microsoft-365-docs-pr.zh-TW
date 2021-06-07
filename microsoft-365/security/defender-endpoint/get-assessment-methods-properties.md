---
title: 匯出每台裝置的評估方法和屬性
description: 提供用於提取 "威脅與弱點管理" 資料的 APIs 資訊。 有不同的 API 呼叫可取得不同的資料類型。 一般而言，每個 API 通話包含組織中裝置的必要資料。 因為資料量可能很大，所以有兩種方法可供檢索
keywords: api，api，export 評估，每個裝置評估，每個機器評估、弱點評估報告、裝置弱點評估、裝置弱點報告、安全設定評估、安全設定報告、軟體漏洞評估、軟體弱點報告、電腦的弱點報告、
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
ms.openlocfilehash: 63f8490984886b8b95e5c090865b5384a0ba04fb
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789337"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>匯出每台裝置的評估方法和屬性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API 描述

提供以每個裝置為基礎拉威脅與弱點管理資料之 APIs 的方法和屬性詳細資料。 有不同的 API 呼叫可取得不同的資料類型。 一般而言，每個 API 通話包含組織中裝置的必要資料。

> [!Note]
>
> 除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。

您可以使用三個 API 方法來找回 (匯出) 不同類型的資訊：

1. 匯出安全設定評估

2. 匯出軟體清查評估

3. 匯出軟體弱點評估

針對每個方法，有不同的 API 呼叫可取得不同的資料類型。 因為資料量可能很大，所以可供檢索的方式有兩種：

- **OData**  API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。 這種方法最適合 _小型組織，且少於 100 K 裝置_。 回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。

- 透過檔案此 API 解決方案可讓大量的資料更快速且可靠地進行。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：

  - 呼叫 API 以取得所有組織資料的下載 URLs 清單。

  - 使用下載 URLs 下載所有檔案，並視需要處理資料。

使用 _OData_ _或透過_ 檔案收集 (所收集的資料，) 目前狀態的目前快照，且不包含歷史資料。 為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。

## <a name="1-export-secure-configurations-assessment"></a>1. 匯出安全設定評估

以每個裝置為基礎，傳回所有設定及其狀態。

### <a name="11-methods"></a>1.1 方法

方法 | 資料類型 | 描述
:---|:---|:---
匯出 secure configuration 評估 **(OData)** | 依裝置集合的安全設定。 請參閱： [1.2 屬性 (OData) ](#12-properties-odata) | 會傳回資料表，其中包含對應之 DeviceId，ConfigurationId 的每個唯一組合的專案。 API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。 這種方法最適合小型組織，且少於 100 K 裝置。 回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。
透過檔案匯出 secure configuration 評估 **()** | 依裝置集合的安全設定。 請參閱： [1.2 屬性 (OData) ](#12-properties-odata) | 會傳回資料表，其中包含對應之 DeviceId，ConfigurationId 的每個唯一組合的專案。 此 API 解決方案可讓大量的資料更快速且可靠地進行。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：1。  呼叫 API 以取得所有組織資料的下載 URLs 清單。 2.  使用下載 URLs 下載所有檔案，並視需要處理資料。

### <a name="12-properties-odata"></a>1.2 屬性 (OData) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
ConfigurationCategory | string | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制
ConfigurationId | string | 特定設定的唯一識別碼
ConfigurationImpact | string | 設定對整個設定分數 (1-10) 的評分影響
ConfigurationName | 字串 | 組態的顯示名稱
ConfigurationSubcategory | string | 設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。
DeviceId | string | 服務中裝置的唯一識別碼。
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。
IsApplicable | bool | 指出設定或原則是否適用
IsCompliant | bool | 指出設定或原則是否已正確設定
IsExpectedUserImpact | bool | 會指出若要套用設定，是否會影響使用者
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。
RecommendationReference | string | 與此軟體相關的建議識別碼參照。
時間 戳 | string | 最近一次在裝置上看到的設定

### <a name="13-properties-via-files"></a>1.3 透過檔案 (的屬性) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
匯出檔案 | 陣列 \[ 字串\] | 用於存放組織目前快照之檔案的下載 URLs 清單。
GeneratedTime | string | 產生匯出的時間。

## <a name="2-export-software-inventory-assessment"></a>2. 匯出軟體清查評估

傳回所有已安裝的軟體及其所有設備的詳細資料。

### <a name="21-methods"></a>2.1 方法

方法 | 資料類型 | 描述
:---|:---|:---
匯出軟體清查評估 **(OData)** | 依裝置集合的軟體清查。 請參閱： [2.2 屬性 (OData) ](#22-properties-odata) | 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。 API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。 這種方法最適合小型組織，且少於 100 K 裝置。 回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。
透過檔案匯出軟體清查評估 **()** | 依裝置檔案清點軟體。 請參閱：2.3 透過檔案 [ (的屬性) ](#23-properties-via-files) | 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。 此 API 解決方案可讓大量的資料更快速且可靠地進行。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：1。  呼叫 API 以取得所有組織資料的下載 URLs 清單。 2.  使用下載 URLs 下載所有檔案，並視需要處理資料。

### <a name="22-properties-odata"></a>2.2 屬性 (OData) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
DeviceId | string | 服務中裝置的唯一識別碼。
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。
DiskPaths | 陣列 [字串]  | 在裝置上安裝產品的磁片證據。
EndOfSupportDate | string | 此軟體支援或會結束的日期。
EndOfSupportStatus | string | 支援狀態的結束。 可以包含這些可能的值：無、EOS 版本、即將發生的 EOS 版本、EOS 軟體（即將進行的 EOS 軟體）。
識別碼 | string | 記錄的唯一識別碼。
NumberOfWeaknesses | int|此裝置上的此軟體弱點數目
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。
RegistryPaths | 陣列 [字串] | 產品已安裝在裝置中的登錄證據。
SoftwareFirstSeenTimestamp | string | 此軟體第一次出現于此裝置上。
SoftwareName | string | 軟體產品的名稱。
SoftwareVendor | string | 軟體廠商的名稱。
SoftwareVersion | string | 軟體產品的版本號碼。

### <a name="23-properties-via-files"></a>2.3 透過檔案 (的屬性) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
匯出檔案 | 陣列 \[ 字串\] | 用於存放組織目前快照之檔案的下載 URLs 清單。
GeneratedTime | string | 產生匯出的時間。

## <a name="3-export-software-vulnerabilities-assessment"></a>3. 匯出軟體漏洞評估

傳回所有裝置的裝置及其詳細資料中的所有已知的安全性漏洞。

### <a name="31-methods"></a>3.1 方法

方法 | 資料類型 | 描述
:---|:---|:---
匯出軟體漏洞評估 **(OData)** | 調查集合請參閱： [3.2 屬性 (OData) ](#32-properties-odata) | 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 的每個唯一組合的專案。 API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。 這種方法最適合小型組織，且少於 100 K 裝置。 回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。
透過檔案匯出軟體漏洞評估 **()** | 調查實體請參閱：3.3 透過檔案 [ (的屬性) ](#33-properties-via-files) | 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 的每個唯一組合的專案。 此 API 解決方案可讓大量的資料更快速且可靠地進行。 因此，建議大型組織使用超過 100 K 的裝置。 此 API 會將組織中的所有資料都提取為下載檔案。 回應包含從 Azure 儲存體下載所有資料的 URLs。 此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：1。  呼叫 API 以取得所有組織資料的下載 URLs 清單。 2.  使用下載 URLs 下載所有檔案，並視需要處理資料。

### <a name="32-properties-odata"></a>3.2 屬性 (OData) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
CveId | string | 指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。
CvssScore | string | CVE 的 CVSS 分數。
DeviceId | string | 服務中裝置的唯一識別碼。
DeviceName | string | 裝置 (FQDN) 的完整功能變數名稱。
DiskPaths | 陣列 \[ 字串\] | 在裝置上安裝產品的磁片證據。
ExploitabilityLevel | string | 此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) 
FirstSeenTimestamp | string | 第一次在裝置上看到此項產品的 CVE。
識別碼 | string | 記錄的唯一識別碼。
LastSeenTimestamp | string | 最後一次在裝置上看到 CVE。
OSPlatform | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。 如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。
RbacGroupName | string | 以角色為基礎的存取控制 (RBAC) 群組。 如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。 如果組織不包含任何 RBAC 群組，則此值會是 "None"。
RecommendationReference | string | 與此軟體相關的建議識別碼參照。
RecommendedSecurityUpdate | string | 軟體廠商提供的安全性更新名稱或描述，以解決此弱點。
RecommendedSecurityUpdateId | string | 對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼
登錄路徑陣列 \[ 字串\] | 產品已安裝在裝置中的登錄證據。
SoftwareName | string | 軟體產品的名稱。
SoftwareVendor | string | 軟體廠商的名稱。
SoftwareVersion | string | 軟體產品的版本號碼。
VulnerabilitySeverityLevel | string | 依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。

### <a name="33-properties-via-files"></a>3.3 透過檔案 (的屬性) 

屬性 (識別碼)  | 資料類型 | 描述
:---|:---|:---
匯出檔案 | 陣列 \[ 字串\]  | 用於存放組織目前快照之檔案的下載 URLs 清單。
GeneratedTime | string | 產生匯出的時間。

## <a name="see-also"></a>另請參閱

- [匯出每個裝置的安全設定評估](get-assessment-secure-config.md)

- [每個裝置匯出軟體清查評估](get-assessment-software-inventory.md)

- [每個裝置的匯出軟體漏洞評估](get-assessment-software-vulnerabilities.md)

其他相關

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
