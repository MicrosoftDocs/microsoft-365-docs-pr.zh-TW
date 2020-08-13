---
title: Advanced 搜尋架構中的 DeviceFileCertificateInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，數位簽章，憑證，檔簽署，DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 33f9c726839f17afbb935c6d028cc4eaa5b74843
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649448"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

適用於：****
- Microsoft 威脅防護

[！附注] `DeviceFileCertificateInfo` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含檔簽署憑證的相關資訊。 此表格使用從憑證驗證活動取得的資料，定期對端點上的檔案執行。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `IsSigned` | 布林值 | 指出檔是否已簽署 |
| `SignatureType` | string | 會指出簽章資訊是做為內嵌內容，還是從外部目錄檔讀取 |
| `Signer` | string | 檔案的簽署者相關資訊 |
| `SignerHash` | string | 識別簽署者的唯一雜湊值 |
| `Issuer` | string | 發證憑證授權 (CA 的相關資訊)  |
| `IssuerHash` | string | 唯一的雜湊值，用以識別發證憑證授權 (CA)  |
| `CertificateSerialNumber` | string | 發證憑證授權 (CA 所獨有之憑證的識別碼)  |
| `CrlDistributionPointUrls` | string |  JSON 陣列，列出包含憑證和憑證吊銷清單 (Crl 的網路共用 URLs)  |
| `CertificateCreationTime` | datetime | 建立憑證的日期和時間 |
| `CertificateExpirationTime` | datetime | 將憑證設為到期的日期和時間 |
| `CertificateCountersignatureTime` | datetime | 反署憑證的日期和時間 |
| `IsTrusted` | 布林值 | 會指出是否要根據 WinVerifyTrust 函式的結果來信任檔案，該函數會檢查未知的根憑證資訊、不正確簽章、吊銷的憑證，以及其他可疑屬性 |
| `IsRootSignerMicrosoft` | 布林值 | 會指出根憑證的簽署者是否為 Microsoft |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。 | 

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式及身分識別搜尋](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
