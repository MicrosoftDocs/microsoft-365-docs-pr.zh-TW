---
title: Microsoft Defender ATP 中的自訂偵測綜述
ms.reviewer: ''
description: 瞭解您可以如何使用高級搜尋來建立自訂偵測並產生警示
keywords: 自訂偵測、警示、偵測規則、高級搜尋、搜尋、查詢、回應動作、間隔、mdatp、microsoft defender atp
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500646"
---
# <a name="custom-detections-overview"></a>自訂偵測概觀

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


透過自訂偵測，您可以主動監視和回應各種事件和系統狀態，包括可疑的破壞活動和設定不當的裝置。 您可以使用自動觸發警示和回應動作的可自訂偵測規則來執行這項作業。

自訂偵測可與 [高級搜尋](advanced-hunting-overview.md)搭配使用，其提供強大且靈活的查詢語言，涵蓋網路的大量事件和系統資訊。 您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。

自訂偵測提供：
- 從高級搜尋查詢所建立之規則的偵測警示
- 適用于檔案和裝置的自動回應動作

## <a name="related-topics"></a>相關主題
- [建立偵測規則](custom-detection-rules.md)
- [查看及管理偵測規則](custom-detections-manage.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
