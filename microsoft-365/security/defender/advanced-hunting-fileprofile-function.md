---
title: Microsoft 365 Defender 的高級搜尋中的 FileProfile () 功能
description: 瞭解如何使用 FileProfile () 豐富您的高級搜尋查詢結果中檔案的相關資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，FileProfile，file profile，function，豐富
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382790"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

`FileProfile()`函數是[高級搜尋](advanced-hunting-overview.md)中的豐富函數，可將下列資料新增至查詢所找到的檔案。

| 欄 | 資料類型 | 描述 |
|------------|---------------|-------------|
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 錄製的動作所套用的檔案 SHA-256 |
| `MD5` | string | 錄製的動作所套用的檔案 MD5 雜湊 |
| `FileSize` | int | 檔案大小（以位元組為單位） |
| `GlobalPrevalence` | int | 由 Microsoft 全域觀測的實體實例數目 |
| `GlobalFirstSeen` | datetime | Microsoft 全球第一次觀測實體的日期和時間 |
| `GlobalLastSeen` | datetime | Microsoft 全球最後觀測實體的日期和時間 |
| `Signer` | string | 檔案的簽署者相關資訊 |
| `Issuer` | string | 發證憑證授權 (CA 的相關資訊)  |
| `SignerHash` | string | 識別簽署者的唯一雜湊值 |
| `IsCertificateValid` | 布林值 | 用於簽署檔的憑證是否有效 |
| `IsRootSignerMicrosoft` | 布林值 | 會指出根憑證的簽署者是否為 Microsoft |
| `SignatureState` | string | 檔簽章的狀態： SignedValid-已使用有效的簽章簽署檔案，SignedInvalid-已簽署該檔案，但憑證無效，未簽署-檔案不會簽署，無法進行檔案的未知資訊
| `IsExecutable` | 布林值 | 檔案是否為可遷移的可執行檔 (PE) file |
| `ThreatName` | string | 找到的任何惡意程式碼或其他威脅的偵測名稱 |
| `Publisher` | string | 發佈檔的組織名稱 |
| `SoftwareName` | 字串 | 軟體產品名稱 |

## <a name="syntax"></a>語法

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引數

- **x**-要使用的檔案識別碼欄： `SHA1` 、、 `SHA256` `InitiatingProcessSHA1` 、 `InitiatingProcessSHA256` 或; `SHA1` 如果未指定，則函數會使用
- **y**-對要濃縮的記錄數目的限制，1-1000;函數使用100（若未指定）


>[!TIP]
> 豐富函數只會顯示輔助性資訊（僅適用時）。 資訊的可用性會不同，且取決於許多因素。 當您在查詢中或建立自訂的偵測中使用 FileProfile () 時，請務必考慮到這一點。 為了獲得最佳結果，建議使用 FileProfile () 函數搭配 SHA1。

## <a name="examples"></a>範例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>僅限 Project 的 SHA1 欄並濃縮

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>豐富第一筆500記錄並列出低傳播檔

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [取得更多查詢範例](advanced-hunting-shared-queries.md)
