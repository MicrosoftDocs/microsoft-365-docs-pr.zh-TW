---
title: Stream Microsoft 365 的 Defender 事件
description: 瞭解如何設定 Microsoft 365 Defender 以將高級搜尋事件傳輸至事件中心或 Azure 儲存體帳戶
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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782474"
---
# <a name="streaming-api"></a>流式處理 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>在事件中心和/或 Azure 儲存體帳戶中傳輸高級搜尋事件。

Microsoft 365Defender 可透過[高級搜尋](../defender/advanced-hunting-overview.md)向[事件中樞](/azure/event-hubs/)和/或[Azure 儲存體帳戶](/azure/event-hubs/)支援流式處理事件。



## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
[將事件傳輸至 Azure 事件中心](streaming-api-event-hub.md)| 瞭解如何在您的租使用者中啟用流式 API，並設定 Microsoft 365 Defender 以將[高級搜尋](../defender/advanced-hunting-overview.md)流式處理至事件中心。
[將事件傳輸至您的 Azure 儲存體帳戶](streaming-api-storage.md)| 瞭解如何在您的租使用者中啟用流式 API，並設定 Microsoft 365 Defender 以將[高級搜尋](advanced-hunting-overview.md)傳輸至您的 Azure 儲存體帳戶。


## <a name="related-topics"></a>相關主題
- [高級搜尋一覽](../defender/advanced-hunting-overview.md)
- [Azure 事件中心檔](/azure/event-hubs/)
- [Azure 儲存體帳戶檔](/azure/storage/common/storage-account-overview)
