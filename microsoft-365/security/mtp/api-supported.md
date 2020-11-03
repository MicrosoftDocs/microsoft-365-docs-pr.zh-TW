---
title: 支援的 Microsoft 365 Defender APIs
description: 支援的 Microsoft 365 Defender APIs
keywords: MTP、APIs、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844957"
---
# <a name="supported-microsoft-365-defender-apis"></a>支援的 Microsoft 365 Defender APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>結束點 URIs：

- 服務基底 URI 是： https://api.security.microsoft.com <br>

>[!NOTE]
>為了提高效能，您可以使用伺服器以接近地理位置：
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - 權杖購置的資源應該是： https://api.security.microsoft.com

 - Path 下的所有 APIs ```/api``` 都是 OData APIs。 舉例來說. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>可用 APIs 清單：

主題 | 描述
:---|:---
[進階搜捕 API](api-advanced-hunting.md) | 從 API 執行高級搜尋查詢。
[事件 API](api-incident.md) | 執行與事件相關的 API 通話，例如：列出事件、更新事件等等。
