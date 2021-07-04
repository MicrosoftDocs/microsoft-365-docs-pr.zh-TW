---
title: 刪除指示器 API。
description: 瞭解如何使用刪除指示器 API，在 Microsoft Defender for Endpoint 中刪除識別碼實體。
keywords: api、public api、支援的 api、delete、ti 指標、實體、識別碼
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289916"
---
# <a name="delete-indicator-api"></a>刪除指示器 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述

依識別碼刪除 [指示器](ti-indicator.md) 實體。

## <a name="limitations"></a>限制

此 API 的速率限制為每分鐘100個通話，每小時1500個通話。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | Ti ReadWrite | 「讀取及寫入 TI 指標 '
應用程式 | Ti ReadWrite 所有 | 「讀取和寫入指示器」

## <a name="http-request"></a>HTTP 要求

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要**。

## <a name="request-body"></a>要求內文

空白

## <a name="response"></a>回應

如果指示器存在並成功刪除-204 OK （沒有內容）。

如果找不到具有指定識別碼的指示器-找不到404。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
