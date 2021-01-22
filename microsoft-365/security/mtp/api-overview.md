---
title: Microsoft 365 Defender API 概觀
description: 瞭解 Microsoft 365 Defender 中可用的 API
keywords: api， apis， overview， incident， incidents， threat搜尋， microsoft 365 defender
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
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930999"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender API 概觀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender 建在整合就緒的平臺上。

使用 Microsoft 365 Defender API，根據共用事件和進一搜尋資料表自動化工作流程。

- **[結合事件佇列](api-incident.md)** - 在事件 API 下將完整攻擊範圍及所有受影響資產分組，以著重于關鍵專案。

- **[搜尋跨產品](api-advanced-hunting.md)** 威脅 - 利用您安全性小組的組織知識，建立自己的自訂查詢來篩選收集于多個保護產品上的原始資料，以尋找入侵符號。

除了這些 Microsoft 365 Defender 專用 API，我們每一個其他安全性產品都公開了其他 [API，](api-articles.md) 説明您充分利用其獨特功能。

## <a name="learn-more"></a>深入了解

| **瞭解如何存取 API** |
|-|
| [瞭解 API 配額與授權](api-terms.md) |
| [存取 Microsoft 365 Defender API](api-access.md) |
| **Build apps** |
| [建立'Hello world'App](api-hello-world.md) |
| [建立應用程式以代表使用者存取 Microsoft 365 Defender API](api-create-app-user-context.md) |
| [建立應用程式以在沒有使用者的情況下存取 Microsoft 365 Defender](api-create-app-web.md) |
| [建立具有 Microsoft 365 Defender API 多租使用者合作夥伴存取權的應用程式](api-partner-access.md) |
| **疑難排解及維護您的應用程式** |
| [瞭解 API 錯誤碼](api-error-codes.md) |
| [使用 Azure 金鑰庫管理應用程式中的秘訣](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [將 OAuth 2.0 授權用於使用者登錄](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
