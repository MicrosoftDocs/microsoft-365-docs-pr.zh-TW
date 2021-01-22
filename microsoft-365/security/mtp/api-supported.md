---
title: 支援的 Microsoft 365 Defender API
description: 支援的 Microsoft 365 Defender API
keywords: MTP、API、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926195"
---
# <a name="supported-microsoft-365-defender-apis"></a>支援的 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：
- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>可用的 API 清單

文章 | 描述
-|-
[進階搜捕 API](api-advanced-hunting.md) | 執行進位搜尋查詢。
[事件 API](api-incident.md) | 列出及更新事件，以及其他實際工作。

### <a name="endpoint-uris"></a>端點 URI

兩個主要 API 的基本 URI 為： https://api.security.microsoft.com . 若要獲得更佳的績效，請使用較靠近您地理位置的伺服器：

- 美國：api-us.security.microsoft.com
- 歐洲：api-eu.security.microsoft.com
- 英國：api-uk.security.microsoft.com

權杖可以存取來取得 https://api.security.microsoft.com 。

路徑上的所有 API `/api` 都使用 [OData](https://docs.microsoft.com/odata/overview) Protocol;例如 https://api.security.microsoft.com/api/incidents 。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender API 概觀](api-overview.md)
- [存取 Microsoft 威脅防護 API](api-access.md)
- [瞭解 API 限制與授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
