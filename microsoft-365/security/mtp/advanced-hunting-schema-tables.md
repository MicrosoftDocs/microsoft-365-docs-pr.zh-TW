---
title: Microsoft 365 Defender advanced 搜尋架構中的資料表格
description: 了解進階搜捕結構描述中的表格，以明白您可以執行威脅搜捕查詢的資料
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，data
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d267219cfa36987c7372a42572d00f4441ccd0cd
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842485"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解進階搜捕結構描述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[！附注] [高級搜尋](advanced-hunting-overview.md) 架構是由多個表格組成，可提供事件資訊或裝置、警示、身分識別及其他實體類型的相關資訊。 若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。

## <a name="get-schema-information-in-the-security-center"></a>在安全性中心取得架構資訊
建立查詢時，請使用內建架構參考，快速取得架構中每個資料表的下列相關資訊：

- **資料表描述** —資料表中包含的資料類型和該資料的來源。
- **欄** -表格中的所有欄。
- **動作類型** —欄中的可能值， `ActionType` 代表資料表支援的事件種類。 這只是針對包含事件資訊的資料表提供。
- **範例查詢** --可用於功能如何使用表格的範例查詢。

### <a name="access-the-schema-reference"></a>存取架構參考
若要快速存取架構參照，請選取架構表示中的資料表名稱旁邊的 **View reference** 動作。 您也可以選取 [ **架構參考** ]，以搜尋表格。   

![顯示如何存取入口網站架構參考的影像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>瞭解架構表格
以下參考列出結構描述中的所有表格。 每個表格名稱都會連結到描述該表格之欄名稱的頁面。 表格和欄名稱也同樣列於安全性中心，成為進階搜捕畫面上結構描述代表中的一部分。

| 表格名稱 | 描述 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 與警示相關聯的檔案、IP 位址、URLs、使用者或裝置 |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 來自 Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 及 Microsoft Defender for Identity 的警示，包括嚴重性資訊和威脅分類  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | 雲端應用程式和服務中的檔相關活動 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多種事件種類，包括由安全性控制項觸發的事件，例如 Windows Defender 防毒軟體和惡意探索保護 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | 從端點上的憑證驗證事件取得的簽署檔憑證資訊 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 檔案建立、修改及其他檔案系統事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 載入事件 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 電腦資訊，包括作業系統資訊 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 裝置上的登入和其他驗證事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 網路連結與相關事件 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 電腦的網路摘要資訊，包括介面卡、IP 和 MAC 位址，以及已連結的網路和網域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 程序建立與相關事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 登錄項目的建立及修改 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | 裝置上的軟體庫存，以及這些軟體產品中的任何已知弱點 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 公開披露弱點的知識庫，包括是否公開提供惡意探索代碼 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 附加至電子郵件之檔案的相關資訊 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件 |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 有關電子郵件 URLs 的資訊 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | 與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。 此資料表涵蓋一系列身分識別相關事件，以及網域控制器上的系統事件。 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | 各來源的帳戶資訊，包括 Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory 和 Microsoft online services 上的驗證事件 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 對 Active Directory 物件（例如使用者、群組、裝置和網域）執行的查詢活動 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
