---
title: Advanced 搜尋架構中的 DeviceFileCertificateInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、數位簽章、憑證、檔簽署、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058452"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[！附注] `DeviceFileCertificateInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔簽署憑證的相關資訊。 此表格使用從憑證驗證活動取得的資料，定期對端點上的檔案執行。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
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
- [了解結構描述](advanced-hunting-schema-reference.md)
