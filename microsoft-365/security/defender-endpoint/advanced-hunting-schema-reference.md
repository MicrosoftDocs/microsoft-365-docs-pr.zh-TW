---
title: 高級搜尋架構參考
description: 深入瞭解 advanced 搜尋架構中的表格，以瞭解您可以在其上執行威脅搜尋查詢的資料。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、microsoft defender for endpoint、wdatp search、query、遙測、schema reference、kusto、table、data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: fa111197dfd68cfcca40ce8a39befe20b97d1be8
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939633"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>瞭解 Microsoft Defender for Endpoint 中的高級搜尋架構

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[！附注] [高級搜尋](advanced-hunting-overview.md) 架構是由多個表格組成，可提供事件資訊或裝置及其他實體的相關資訊。 若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。

## <a name="get-schema-information-in-the-security-center"></a>在安全性中心取得架構資訊
建立查詢時，請使用內建架構參考，快速取得架構中每個資料表的下列相關資訊：

- **資料表描述**—資料表中包含的資料類型和該資料的來源。
- **欄**-表格中的所有欄。
- **動作類型**—欄中的可能值， `ActionType` 代表資料表支援的事件種類。 這只是針對包含事件資訊的資料表提供。
- **範例查詢**--可用於功能如何使用表格的範例查詢。

### <a name="access-the-schema-reference"></a>存取架構參考
若要快速存取架構參照，請選取架構表示中的資料表名稱旁邊的 **View reference** 動作。 您也可以選取 [ **架構參考** ]，以搜尋表格。

![顯示如何存取入口網站架構參考的影像](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>瞭解架構表格

下列參考會列出高級搜尋架構中的所有表格。 每個表格名稱都會連結到描述該表格之欄名稱的頁面。

表格和欄名稱也會列在「Microsoft Defender 安全中心」的 [高級搜尋] 畫面上的架構標記法中。

| 表格名稱 | 描述 |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Microsoft Defender Security Center 上的警示 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 裝置資訊，包括作業系統資訊 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 裝置的網路內容，包括配接器、IP 和 MAC 位址，以及連線的網路和網域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 程序建立與相關事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 網路連結與相關事件 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 檔案建立、修改及其他檔案系統事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 登錄項目的建立及修改 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 登入和其他驗證事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 載入事件 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多種事件種類，包括安全性控制（如 Microsoft Defender 防毒程式和 exploit protection）所觸發的事件 |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | 從端點上的憑證驗證事件取得的簽署檔憑證資訊 |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | 安裝在裝置上的軟體清單，包括其版本資訊和支援終止狀態 |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | 裝置上的軟體弱點，以及解決每個弱點的可用安全性更新清單 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 公開披露弱點的知識庫，包括是否公開提供惡意探索代碼 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應 |

>[!TIP]
>使用 [microsoft 365 Defender 中的 [高級搜尋](/microsoft-365/security/defender/advanced-hunting-overview) ]，以搜尋使用來自 Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 及 microsoft Defender 身分識別的資料威脅。 [開啟 Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)<br><br>
深入瞭解如何將您的高級搜尋工作流程從 Microsoft Defender for Endpoint 移至 Microsoft 365 Defender，以 [從 Microsoft defender For Endpoint 遷移高級搜尋查詢](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](overview-custom-detections.md)
- [高級搜尋資料架構變更](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
