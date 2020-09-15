---
title: 支援的 Microsoft 威脅防護 APIs
description: 支援的 Microsoft 威脅防護 APIs
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650186"
---
# <a name="supported-microsoft-threat-protection-apis"></a>支援的 Microsoft 威脅防護 APIs 
適用於：****
- Microsoft 威脅防護

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
[高級搜尋 API](api-advanced-hunting.md) | 從 API 執行高級搜尋查詢。
[事件 APIs](api-incident.md) | 執行與事件相關的 API 通話，例如：列出事件、更新事件等等。
