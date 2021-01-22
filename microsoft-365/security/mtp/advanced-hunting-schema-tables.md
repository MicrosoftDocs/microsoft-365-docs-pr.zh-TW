---
title: Microsoft 365 Defender 進位搜尋架構中的資料表
description: 了解進階搜捕結構描述中的表格，以明白您可以執行威脅搜捕查詢的資料
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料
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
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925041"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解進階搜捕結構描述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進 [位搜尋](advanced-hunting-overview.md) 架構是由提供事件資訊或裝置、警示、身分身分和其他實體類型的多個資料表所建立。 若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。

## <a name="get-schema-information-in-the-security-center"></a>在安全性中心中取得架構資訊
在建構查詢時，使用內建的架構參照來快速取得架構中每個資料表的下列相關資訊：

- **資料表** 描述 —資料表中包含的資料類型以及該資料的來源。
- **資料** 行 — 資料表中的所有資料行。
- **動作類型**—資料行 `ActionType` 中可能的值，代表資料表支援的事件種類。 此資訊只會提供給包含事件資訊的資料表。
- **範例查詢**-利用表格方式的範例查詢。

### <a name="access-the-schema-reference"></a>存取架構參照
若要快速存取架構參照，請在架構表示法中選取資料表名稱旁邊的 View 參照動作。 您也可以選取架構 **參照** 來搜尋資料表。   

![顯示如何存取入口網站內架構參照的圖像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>瞭解架構資料表
以下參考列出結構描述中的所有表格。 每個表格名稱都會連結到描述該表格之欄名稱的頁面。 資料表與資料行名稱也會列在安全性中心，做為進位搜尋畫面中架構表示的一部分。

| 表格名稱 | 描述 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 與警示相關聯的檔案、IP 位址、URL、使用者或裝置 |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 來自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender 的身分識別通知，包括嚴重性資訊和威脅分類  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | 雲端應用程式和服務中的檔案相關活動 |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | 涉及 Office 365 和其他雲端應用程式和服務中帳戶和物件的事件 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多種事件種類，包括由安全性控制項觸發的事件，例如 Windows Defender 防毒軟體和惡意探索保護 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | 從端點上的憑證驗證事件取得之已簽署檔案的憑證資訊 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 檔案建立、修改及其他檔案系統事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 載入事件 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 電腦資訊，包括作業系統資訊 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 裝置上的登錄與其他驗證事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 網路連結與相關事件 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 裝置的網路內容，包括實體介面卡、IP 和 MAC 位址，以及已連接的網路和網域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 程序建立與相關事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 登錄項目的建立及修改 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | 裝置上的軟體庫存和這些軟體產品的任何已知弱點 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 公開披露弱點的知識庫，包括是否公開提供惡意探索代碼 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 附加至電子郵件之檔案的資訊 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件 |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 將電子郵件送達收件者的信箱之後，在傳送後發生的安全性事件 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 電子郵件 URL 相關資訊 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | 涉及內部部署網域控制站執行 Active Directory (AD) 。 下表涵蓋網域控制站上的一系列身分識別相關事件及系統事件。 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | 各種來源的帳戶資訊，包括 Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory 和 Microsoft 線上服務上的驗證事件 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Active Directory 物件的查詢，例如使用者、群組、裝置和網域 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
