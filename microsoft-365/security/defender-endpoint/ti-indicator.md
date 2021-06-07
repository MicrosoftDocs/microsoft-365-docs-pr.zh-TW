---
title: 指示器資源類型
description: 使用 Microsoft Defender for Endpoint 指定實體詳細資料及定義指示器的到期日。
keywords: api、支援的 api、get、TiIndicator、指示器、最近
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771378"
---
# <a name="indicator-resource-type"></a>指示器資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 請參閱入口網站中的對應 [指示器頁面](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) 。 

方法|傳回類型 |描述
:---|:---|:---
[清單指示器](get-ti-indicators-collection.md) | [指標](ti-indicator.md) 收集 | 清單 [指示器](ti-indicator.md) 實體。
[提交指示器](post-ti-indicator.md) | [指標](ti-indicator.md) | 提交或更新 [指示器](ti-indicator.md) 實體。
[匯入指標](import-ti-indicators.md) | [指標](ti-indicator.md) 收集 | 提交或更新 [指示器](ti-indicator.md) 實體。
[刪除指示器](delete-ti-indicator-by-id.md) | 無內容 | 會刪除 [指示器](ti-indicator.md) 實體。


## <a name="properties"></a>屬性
屬性	 |  類型    |   描述
:---|:---|:---
id | 字串 | [指示器](ti-indicator.md)實體的身分識別。
indicatorValue | 字串 | [指標](ti-indicator.md)的值。
indicatorType | Enum | 指標的類型。 可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。
應用程式 | 字串 | 與指示器相關聯的應用程式。 
action | Enum | 將在組織中探索指示器時所採取的動作。 可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。
sourceType | Enum | 若使用者 (所建立的指標，則為 "user"，例如，從入口網站) 「AadApp」，以防它透過 API 使用自動應用程式提交。
源 | string | 提交指標的使用者/應用程式名稱。
createdBy | 字串 | 提交指標之使用者/應用程式的唯一身分識別。
lastUpdatedBy | 字串 | 上次更新標記的使用者/應用程式的身分識別。
creationTimeDateTimeUtc | DateTimeOffset | 建立指示器的日期和時間。
expirationTime | DateTimeOffset | 指示器的到期時間。
lastUpdateTime | DateTimeOffset | 上次更新指示器的時間。
嚴重性 | Enum | 指標的嚴重性。 可能的值為：「資訊」、「低」、「中」和「高」。
標題 | String | 指示器標題。
描述 | 字串 | 標記的描述。
recommendedActions | 字串 | 標記的建議動作。
rbacGroupNames | 字串清單 | RBAC 設備群組名稱，其標記是公開和作用中的。 空清單，以防它公開至所有裝置。


## <a name="json-representation"></a>Json 標記法

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
