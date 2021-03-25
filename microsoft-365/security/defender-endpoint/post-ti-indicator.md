---
title: 提交或更新指示器 API
description: 瞭解如何使用提交或更新指示器 API，在 Microsoft Defender for Endpoint 中提交或更新新的指示器實體。
keywords: api，graph api，支援的 api，submit，ti，標記，更新
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187131"
---
# <a name="submit-or-update-indicator-api"></a>提交或更新指示器 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述
提交或更新新的 [指示器](ti-indicator.md) 實體。
<br>不支援 IPs 的 CIDR 標記法。

## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。
2. 每個租使用者的活動指示器限制為15000。 


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Ti ReadWrite |  「讀取和寫入指示器」
應用程式 |   Ti ReadWrite 所有 |  「讀取及寫入所有指示器」
委派 (工作或學校帳戶)  |    Ti ReadWrite |  「讀取和寫入指示器」


## <a name="http-request"></a>HTTP 要求
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | string | application/json。 **必要欄位**。

## <a name="request-body"></a>要求正文
在要求主體中，提供具有下列參數的 JSON 物件：

參數 | 類型    | 描述
:---|:---|:---
indicatorValue | 字串 | [指示器](ti-indicator.md)實體的身分識別。 **Required**
indicatorType | Enum | 指標的類型。 可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。 **Required**
action | Enum | 將在組織中探索指示器時所採取的動作。 可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。 **Required**
應用程式 | 字串 | 與指示器相關聯的應用程式。 **Optional**
標題 | String | 指示器警示標題。 **Required**
描述 | 字串 | 標記的描述。 **Required**
expirationTime | DateTimeOffset | 指示器的到期時間。 **Optional**
嚴重性 | Enum | 指標的嚴重性。 可能的值為：「資訊」、「低」、「中」和「高」。 **Optional**
recommendedActions | 字串 | TI 指標警示建議的動作。 **Optional**
rbacGroupNames | 字串 | 標記將套用到的 RBAC 群組名稱的以逗號分隔的清單。 **Optional**


## <a name="response"></a>回應
- 如果成功，這個方法會傳回 200-OK 回應碼，以及回應內文中建立/更新的 [指示器](ti-indicator.md) 實體。
- 若失敗：此方法會傳回 400-錯誤要求。 錯誤的要求通常會指出不正確的正文。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>相關主題
- [管理指示器](manage-indicators.md)
