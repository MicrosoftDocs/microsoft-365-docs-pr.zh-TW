---
title: 取得與網域相關的警示 API
description: 瞭解如何使用「取得網域相關的警示」 API，以在 Microsoft Defender for Endpoint 中檢索與特定網域位址相關的提醒。
keywords: api、graph api、支援的 api、get、domain、相關、警示
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772254"
---
# <a name="get-domain-related-alerts-api"></a>取得與網域相關的警示 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
會檢索與特定網域位址相關的 [警示](alerts.md) 集合。


## <a name="limitations"></a>限制
1. 您可以根據您設定的保留期間，查詢上次更新的警示。
2. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


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
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
>- 回應只會包含使用者有權存取之裝置的警示（取決於裝置群組設定） (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>要求標頭

| 頁首        | 值  |
|:--------------|:-------|
| 授權 | 字串 |

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功且網域存在-200 OK （含 [警示](alerts.md) 實體的清單）。 如果網域不存在-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
