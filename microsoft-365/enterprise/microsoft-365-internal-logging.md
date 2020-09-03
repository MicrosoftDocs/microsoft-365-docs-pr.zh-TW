---
title: Microsoft 365 工程的 microsoft 365 內部記錄
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，將尋找 Microsoft 365 工程小組內部記錄運作方式的說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 08f87ba682a88a7efd93735b160af49bf5468ca2
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332505"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Microsoft 365 工程內部記錄

除了可供客戶使用的事件和記錄資料之外，microsoft 的 Microsoft 365 工程師也可使用內部記錄資料收集系統。 許多不同類型的記錄資料會從 Microsoft 365 伺服器上傳至內部的大型資料計算服務，稱為 Cosmos。 每個服務小組都會將審核記錄從各自的伺服器上傳至 Cosmos 資料庫，以進行匯總和分析。 使用稱為 Office Data Loader (ODL) 的專屬自動化工具，在特別認可的埠和通訊協定上，會透過 FIPS 140-2 驗證的 TLS 連線進行此資料傳輸。 Microsoft 365 中用來收集和處理審計記錄的工具不允許對原始的審計記錄內容或時間順序進行永久或不可逆的變更。

服務小組使用 Cosmos 做為集中式存放庫，進行應用程式使用方式的分析，以測量系統和操作效能，並尋找可能表示問題或安全性問題的 abnormalities 和模式。 每個服務小組會根據要分析的內容，將記錄的基準上傳至 Cosmos，這通常包括：

- 事件記錄檔
- AppLocker 記錄
- 效能資料
- System Center 資料
- 詳細通話記錄
- 經驗品質資料
- IIS 網頁伺服器記錄檔
- SQL Server 記錄檔
- Syslog 資料
- 安全性審核記錄檔

在將資料上傳至 Cosmos 之前，ODL 應用程式會使用清理服務，以模糊顯示任何包含客戶資料的欄位（如租使用者資訊和使用者身分識別資訊），並以雜湊值取代這些欄位。 匿名和雜湊記錄會重新寫入並上傳至 Cosmos。 服務小組對 Cosmos 中的資料執行關聯、警示及報告等範圍的查詢。 Cosmos 中的審計記錄資料保留期間是由服務小組決定。大多數的審計記錄資料會保留90天或更長的時間，以支援安全性事件調查，並符合法規保留要求。

存取儲存在 Cosmos 中的 Microsoft 365 資料會限制在授權的人員。 Microsoft 會將審計功能的管理限制于負責審計功能的服務小組成員的有限子集。 這些小組成員無法修改或刪除 Cosmos 中的資料，而且會記錄及審核 Cosmos 之記錄機制的所有變更。

每個服務小組會透過授權某些應用程式來執行特定分析，存取其記錄資料以進行分析。 例如，Microsoft 365 安全小組會透過專有的事件記錄分析程式使用來自 Cosmos 的資料，以在 Microsoft 365 實際執行環境中關聯、警示及產生可操作的報告，以進行可能的可疑活動。 這些資料中的報告是用來修正漏洞，以及改善服務的整體效能。 如果特定警示或報告需要進一步調查，服務人員可以要求將資料匯入回 Microsoft 365 服務。 因為從 Cosmos 匯入的特定記錄是在加密的，而服務人員卻沒有解密金鑰的存取權，所以目標記錄會以程式設計方式傳遞，該解密服務會將範圍的結果傳回至授權服務人員。 在此練習中找到的任何弱點，都是透過 Microsoft 的標準安全性事件管理通道來報告及上報。
