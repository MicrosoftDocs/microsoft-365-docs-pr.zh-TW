---
title: 從事件 API 建立警示
description: 瞭解如何使用 [建立警示 API]，在 Microsoft Defender for Endpoint 中的事件上建立新的警示。
keywords: api、graph api、支援的 api、get、警示、資訊、識別碼
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
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289460"
---
# <a name="create-alert-api"></a>建立警示 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述

在 **事件** 上建立新的 [警示](alerts.md)。

- 需要有 **Microsoft Defender For Endpoint 事件** 才能建立警示。
- 您必須從要求中的事件提供3個參數： **事件時間**、 **電腦識別碼** 及 **報表識別碼**。 請參閱下面範例。
- 您可以使用在高級搜尋 API 或入口網站中找到的事件。
- 如果在相同的裝置上有相同標題的開啟警示，新建立的警示會與其合併。
- 自動調查會在透過 API 建立的提醒上自動啟動。

## <a name="limitations"></a>限制

1. 此 API 的速率限制為每分鐘15次通話。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | 警示。 ReadWrite。 | 「讀取及寫入所有警示」
委派 (工作或學校帳戶)  | 警示。 ReadWrite | 「讀取及寫入警示」

> [!NOTE]
> 使用使用者認證取得權杖時：
>
> - 使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
> - 使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要**。
Content-Type | 字串 | application/json。 **必要**。

## <a name="request-body"></a>要求內文

在要求內，請提供下列值 (所有必要) ：

屬性	 | 類型 | 說明
:---|:---|:---
eventTime | DateTime (UTC)  | 從高級搜尋取得之事件的確切時間（字串）。 例如， ```2018-08-03T16:45:21.7115183Z``` **必要**。
reportId | 字串 | 從高級搜尋取得的事件 reportId。 **必要**。
machineId | 字串 | 識別事件之裝置的識別碼。 **必要**。
嚴重性 | 字串 | 警示的嚴重性。 屬性值為：「低 '、' 中」及 ' 高」。 **必要**。
標題 | String | 提醒的標題。 **必要**。
描述 | 字串 | 警示的描述。 **必要**。
recommendedAction| 字串 | 在分析警示時，安全性監察官建議採取的動作。 **必要**。
類別| 字串 | 警示的類別。 屬性值包括： "General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"InitialAccess"、"LateralMovement"、""、"PrivilegeEscalation"、"SuspiciousActivity"、"持久性"、""、"勒索軟體"、"" （ **必要**）。

## <a name="response"></a>回應

如果成功，這個方法會傳回 200 OK 及回應內文中的新 [警示](alerts.md) 物件。 如果找不到具有指定屬性的事件 (_reportId_、 _eventTime_ 及 _MachineId_) -找不到404。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
