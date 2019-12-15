---
title: Microsoft 威脅防護進階搜捕結構描述的資料表格
description: 了解進階搜捕結構描述中的表格，以明白您可以執行威脅搜捕查詢的資料
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、kusto、表格、資料
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910896"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解進階搜捕結構描述

**適用於：**
- Microsoft 威脅防護

[!include[Prerelease information](prerelease.md)]

[進階搜捕](advanced-hunting-overview.md)結構描述是由多個提供事件資訊或與電腦或實體相關資訊的表格所組成。 若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。

## <a name="schema-tables"></a>結構描述表格

以下參考列出結構描述中的所有表格。 每個表格名稱都會連結到描述該表格之欄名稱的頁面。 表格和欄名稱也同樣列於安全性中心，成為進階搜捕畫面上結構描述代表中的一部分。

| 表格名稱 | 描述 |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | 電腦資訊，包括作業系統資訊 |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | 電腦的網路摘要資訊，包括介面卡、IP 和 MAC 位址，以及已連結的網路和網域 |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | 程序建立與相關事件 |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | 網路連結與相關事件 |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | 檔案建立、修改及其他檔案系統事件 |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | 登錄項目的建立及修改 |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | 登入和其他驗證事件 |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | DLL 載入事件 |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | 多種事件種類，包括由安全性控制項觸發的事件，例如 Windows Defender 防毒軟體和惡意探索保護 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Office 365 電子郵件事件，包括電子郵件傳送和封鎖事件 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 有關已附加到 Office 365 電子郵件的檔案相關資訊 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Office 365 電子郵件上 URL 的相關資訊 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | 裝置上的軟體庫存，以及這些軟體產品中的任何已知弱點 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | 公開披露弱點的知識庫，包括是否公開提供惡意探索代碼 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | 威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | 由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應  |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
