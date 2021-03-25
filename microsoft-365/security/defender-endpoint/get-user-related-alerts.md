---
title: 取得使用者相關的警示 API
description: 使用 Microsoft Defender for Endpoint，檢索與指定之使用者識別碼相關的提醒集合。
keywords: api、graph api、支援的 api、get、user、相關的警示
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
ms.technology: mde
ms.openlocfilehash: cff4530cfa4ecd6b0d918a9112e7be3c0f30209c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166383"
---
# <a name="get-user-related-alerts-api"></a>取得使用者相關的警示 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述
會檢索與指定之使用者識別碼相關的警示集合。


## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   警示。已讀取。所有 |    「讀取所有警示」
應用程式 |   警示。 ReadWrite。 |   「讀取及寫入所有警示」
委派 (工作或學校帳戶)  | 警示。讀取 | 「讀取警示」
委派 (工作或學校帳戶)  | 警示。 ReadWrite | 「讀取及寫入警示」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data」。 如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)。
>- 回應只會包含使用者有權存取之裝置的警示（取決於裝置群組設定） (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
GET /api/users/{id}/alerts
```

**識別碼不是完整的 UPN，只是使用者名稱。 (例如，若要取得 user1@contoso.com 的警示，請使用/api/users/user1/alerts)**

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。


## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功且使用者存在-200 OK。 如果使用者不存在-找不到404。 


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
