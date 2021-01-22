---
title: Microsoft 365 Defender 進 (尋找中的 FileProfile () 函數
description: 瞭解如何使用 FileProfile () 來豐富進位搜尋查詢結果中檔案的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、FileProfile、檔案設定檔、函數、擴充
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929547"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

此 `FileProfile()` 函數是進一步搜尋中的擴充 [函數](advanced-hunting-overview.md) ，會將下列資料新增到查詢找到的檔案中。

| 欄 | 資料類型 | 描述 |
|------------|-------------|-------------|
| SHA1 | 字串 | 記錄動作已套用的檔案 SHA-1 |
| SHA256 | string | 已記錄動作所適用于檔案的 SHA-256 |
| MD5 | string | 已記錄動作所針對之檔案的 MD5 雜湊 |
| FileSize | int | 檔案大小 ，以位元組為單位 |
| GlobalPrevalence | int | Microsoft 全域觀察之實體的實例數目 |
| GlobalFirstSeen | datetime | Microsoft 全域第一次觀察實體的日期和時間 |
| GlobalLastSeen | datetime | Microsoft 全域上次觀察實體的日期和時間 |
| 簽名 | string | 檔案簽署者的資訊 |
| 發行者 | string | 發行憑證授權單位 (CA)  |
| SignerHash | string | 識別簽簽者的唯一雜湊值 |
| IsCertificateValid | 布林值 | 用來簽署檔案的憑證是否有效 |
| IsRootSignerMicrosoft | 布林值 | 指出根憑證的簽署者是否為 Microsoft |
| IsExecutable | 布林值 | 檔案為可攜式可執行檔 (PE) 檔案 |
| ThreatName | string | 找到任何惡意攻擊或其他威脅的偵測名稱 |
| Publisher | string | 發佈檔案的組織名稱 |
| SoftwareName | 字串 | 軟體產品名稱 |

## <a name="syntax"></a>語法

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引數

- **x**—未指定時，會使用檔案識別碼資料行：、、或 `SHA1` `SHA256` ; `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 函數
- **y**— 限制要豐富記錄的數量，1-1000;函數使用 100 未指定時

## <a name="examples"></a>範例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>只預計 SHA1 欄並豐富

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>豐富前 500 個記錄，並列出低品質檔案

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
