---
title: 進位搜尋架構中的 DeviceFileCertificateInfo 資料表
description: 瞭解進位搜尋架構之 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、數位簽章、憑證、檔案簽署、DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931311"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進 `DeviceFileCertificateInfo` 位搜尋架構 [中的資料表](advanced-hunting-overview.md) 包含有關檔案簽署憑證的資訊。 此表格使用從憑證驗證活動取得的資料，會定期在端點上的檔案上執行。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `IsSigned` | 布林值 | 指出檔案是否已簽署 |
| `SignatureType` | string | 指出簽章資訊是在檔案本身中讀取為內嵌內容，或從外部目錄檔案讀取 |
| `Signer` | string | 檔案簽署者的資訊 |
| `SignerHash` | string | 識別簽簽者的唯一雜湊值 |
| `Issuer` | string | 有關發行憑證授權單位 (CA)  |
| `IssuerHash` | string | 唯一雜湊值識別會發行憑證授權單位 (CA)  |
| `CertificateSerialNumber` | string | 憑證的識別碼，是發行憑證授權單位 (CA)  |
| `CrlDistributionPointUrls` | string |  列出網路共用 URL 的 JSON 陣列，其中包含憑證和憑證吊銷清單 (CLS)  |
| `CertificateCreationTime` | datetime | 建立憑證的日期和時間 |
| `CertificateExpirationTime` | datetime | 憑證設定到期日的日期和時間 |
| `CertificateCountersignatureTime` | datetime | 憑證簽錯的日期和時間 |
| `IsTrusted` | 布林值 | 根據 WinVerifyTrust 函數的結果來判斷檔案是否受信任，該函數會檢查不明的根憑證資訊、不正確簽章、撤銷的憑證，以及其他可問屬性 |
| `IsRootSignerMicrosoft` | 布林值 | 指出根憑證的簽署者是否為 Microsoft |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用。 | 

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
