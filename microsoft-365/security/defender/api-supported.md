---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: Microsoft 365 Defender、APIs、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935722"
---
# <a name="supported-microsoft-365-defender-apis"></a>支援的 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

## <a name="list-of-available-apis"></a>可用 APIs 的清單

文章 | 描述
-|-
[進階搜捕 API](api-advanced-hunting.md) | 執行高級搜尋查詢。
[事件 API](api-incident.md) | 列出和更新事件，以及其他實用工作。

### <a name="endpoint-uris"></a>端點 URIs

主要 APIs 的基底 URI 是： https://api.security.microsoft.com 。 為了獲得較佳的效能，請使用與您的地理位置更接近的伺服器：

- 美國： api-us.security.microsoft.com
- 歐洲： api-eu.security.microsoft.com
- 英國： api-uk.security.microsoft.com

您可以透過存取來取得權杖 https://api.security.microsoft.com 。

所有沿路徑的 APIs 都 `/api` 使用 [OData](/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [存取 Microsoft 365 Defender APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)