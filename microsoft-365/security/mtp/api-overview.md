---
title: Microsoft 365 Defender APIs 概述
description: 深入瞭解 Microsoft 365 Defender 中可用的 APIs
keywords: api，api，綜述，事件，事件，威脅搜尋，microsoft 365 defender
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719187"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender APIs 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender 是以整合就緒平臺為基礎。

使用 Microsoft 365 Defender APIs，根據共用的事件和高級搜尋表來自動化工作流程。

- **[結合的事件佇列](api-incident.md)** -著重于將完整的攻擊範圍和所有受影響的資產分組在事件 API 底下的重要事項。

- **[跨產品威脅搜尋](api-advanced-hunting.md)** -利用您的安全小組的組織知識，透過建立您自己的自訂查詢，以透過跨多個保護產品所收集的原始資料來進行保護，以尋找損害的跡象。

除了這些 Microsoft 365 Defender 特有的 APIs 之外，其他所有的安全性產品都會公開 [其他 APIs](api-articles.md) ，以協助您利用其獨特的功能。

## <a name="learn-more"></a>深入了解

| **瞭解如何存取 APIs** |
|-|
| [深入瞭解 API 配額和授權](api-terms.md) |
| [存取 Microsoft 365 Defender APIs](api-access.md) |
| **Build apps** |
| [建立 "Hello world" 應用程式](api-hello-world.md) |
| [建立應用程式以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md) |
| [建立應用程式以存取沒有使用者的 Microsoft 365 Defender](api-create-app-web.md) |
| [建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式](api-partner-access.md) |
| **疑難排解及維護您的應用程式** |
| [瞭解 API 錯誤代碼](api-error-codes.md) |
| [使用 Azure Key Vault 管理應用程式中的機密](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [針對使用者登入執行 OAuth 2.0 授權](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
