---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719319"
---
# <a name="supported-microsoft-365-defender-apis"></a>支援的 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：
- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

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

所有沿路徑的 APIs 都 `/api` 使用 [OData](https://docs.microsoft.com/odata/overview) 通訊協定; 例如， https://api.security.microsoft.com/api/incidents 。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [存取 Microsoft 威脅防護 APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
