---
title: 取得事件 API
description: 瞭解如何使用取得事件 API，在 Microsoft 365 Defender 中取得單一事件。
keywords: api、graph api、支援的 api、get、file、hash
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289604"
---
# <a name="get-incident-information-api"></a>取得事件資訊 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述

依識別碼來檢索特定事件

## <a name="limitations"></a>限制

1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | Incident。已讀取。所有 | 「讀取所有事件」
應用程式 | Incident。 ReadWrite。 | 「讀取和寫入所有事件」
委派 (工作或學校帳戶)  | 事件。讀取 | 「讀取事件」
委派 (工作或學校帳戶)  | Incident。 ReadWrite | 「讀取和寫入事件」

> [!NOTE]
>
> 使用使用者認證取得權杖時：
>
> - 使用者至少必須具備下列角色許可權：「View Data」
> - 回應只會包含使用者所公開的事件

## <a name="http-request"></a>HTTP 要求

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要**。

## <a name="request-body"></a>要求內文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回 200 OK，以及回應內文中的事件實體。 如果找不到具有指定識別碼的事件-找不到404。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
