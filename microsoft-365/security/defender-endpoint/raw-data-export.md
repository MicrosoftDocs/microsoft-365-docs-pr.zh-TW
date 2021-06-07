---
title: Stream Microsoft Defender for Endpoint 事件
description: 瞭解如何設定 Microsoft Defender for Endpoint to stream Advanced 搜尋事件至事件中心或 Azure 儲存體帳戶
keywords: 原始資料匯出，流式 API，API，事件中心，Azure 儲存體，儲存體帳戶，高級搜尋，原始資料共用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771618"
---
# <a name="raw-data-streaming-api"></a>原始資料流程式處理 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>在事件中心和/或 Azure 儲存體帳戶中傳輸高級搜尋事件。

Defender for Endpoint 支援透過 [Advanced 搜尋](advanced-hunting-overview.md) 向 [事件中樞](/azure/event-hubs/) 和/或 [Azure 儲存體帳戶](/azure/event-hubs/)進行所有可用事件的資料流程。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
[將 Microsoft Defender for Endpoint 事件的資料流程傳遞給 Azure 事件中心](raw-data-export-event-hub.md)| 瞭解如何在您的租使用者中啟用流式 API，並設定 Defender for Endpoint，以將 [高級搜尋](advanced-hunting-overview.md) 流式處理至事件中心。
[Azure 儲存體帳戶的端點事件的資料流程 Defender](raw-data-export-storage.md)| 瞭解如何在您的租使用者中啟用流式 API，並設定 Defender for Endpoint，以將 [高級搜尋](advanced-hunting-overview.md) 流式處理至您的 Azure 儲存體帳戶。


## <a name="related-topics"></a>相關主題
- [高級搜尋一覽](advanced-hunting-overview.md)
- [Azure 事件中心檔](/azure/event-hubs/)
- [Azure 儲存體帳戶檔](/azure/storage/common/storage-account-overview)