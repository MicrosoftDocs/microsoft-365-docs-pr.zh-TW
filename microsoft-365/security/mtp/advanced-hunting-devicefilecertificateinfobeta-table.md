---
title: DeviceFileCertificateInfoBeta 資料表中的進階的狩獵結構描述
description: 了解簽章 DeviceFileCertificateInfoBeta 表格中的資訊的進階的狩獵結構描述檔案
keywords: 進階搜尋，搜尋，搜尋，microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、] 欄中，輸入資料的網路威脅、 數位簽章、 憑證、 簽章的檔案的威脅DeviceFileCertificateInfoBeta
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
ms.openlocfilehash: ffff2802b52fb48bd7fc88fc0d3eac425380502e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602831"
---
# <a name="devicefilecertificateinfobeta"></a>DeviceFileCertificateInfoBeta

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceFileCertificateInfoBeta` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含簽署憑證的檔案的相關資訊。 此表格會使用取自憑證驗證活動的端點上的檔案上定期執行的資料。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | 字串 | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `SHA1` | string | 記錄動作已套用的檔案 SHA-1 |
| `IsSigned` | 布林值 | 會指出是否已簽署的檔案 |
| `SignatureType` | string | 指示簽章資訊已讀取檔案本身中的內嵌內容或從外部類別目錄檔案讀取 |
| `Signer` | string | 檔案的簽署者的相關資訊 |
| `SignerHash` | string | 唯一的雜湊值，識別之簽章 |
| `Issuer` | string | 憑證授權單位 (CA) 的相關資訊 |
| `IssuerHash` | string | 唯一的雜湊值，識別發行的憑證授權單位 (CA) |
| `CertificateSerialNumber` | string | 憑證的憑證授權單位 (CA) 的唯一識別碼 |
| `CrlDistributionPointUrls` | string |  列出包含憑證和憑證撤銷清單 (Crl) 的網路共用的 Url 的 JSON 陣列 |
| `CertificateCreationTime` | datetime | 憑證已建立的日期和時間 |
| `CertificateExpirationTime` | datetime | 憑證設定到期日期和時間 |
| `CertificateCountersignatureTime` | datetime | 日期和時間已簽署的憑證 |
| `IsTrusted` | 布林值 | 會指出檔案是否信任根據檢查未知的根憑證資訊、 無效的簽章、 撤銷的憑證及其他可疑屬性 WinVerifyTrust 函式的結果 |
| `IsRootSignerMicrosoft` | 布林值 | 指出根憑證的簽署者是否為 Microsoft |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄。 | 

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)