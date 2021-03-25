---
title: 調查資源類型
description: Microsoft Defender ATP 調查實體。
keywords: api、graph api、支援的 api、get、警示、調查
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187127"
---
# <a name="investigation-resource-type"></a>調查資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

代表用於端點之 Defender 中的自動調查實體。
<br> 如需詳細資訊，請參閱 [自動調查一覽](automated-investigations.md) 。

## <a name="methods"></a>方法
方法	|傳回類型 |描述
:---|:---|:---
[清單調查](get-investigation-collection.md) | 調查集合 | 取得調查集合
[取得單一調查](get-investigation-object.md) | 調查實體 | 取得單一調查實體。
[開始調查](initiate-autoir-investigation.md) | 調查實體 | 在裝置上開始調查。


## <a name="properties"></a>屬性
屬性	 |  類型    |   描述
:---|:---|:---
id | 字串 | 調查實體的身分識別。 
startTime | DateTime 可為 Null | 建立調查的日期和時間。 
endTime | DateTime 可為 Null | 完成調查的日期和時間。 
cancelledBy | 字串 | 取消調查的使用者/應用程式識別碼。 
investigationState | Enum | 調查的目前狀態。 可能的值為： ' Unknown '、' 終止 '、' SuccessfullyRemediated '、' 良性 '、' Failed '、' PartiallyRemediated '、' PartiallyInvestigated '、' PendingApproval '、' PendingResource '、' TerminatedByUser '、' TerminatedBySystem '、' InnerFailure '、' PreexistingAlert '、' UnsupportedOs '、' UnsupportedAlertType '、' SuppressedAlert '、' '、' '。
statusDetails | 字串 | 有關調查狀態的其他資訊。
machineId | 字串 | 執行調查所在之裝置的識別碼。
computerDnsName | 字串 | 執行調查所在之裝置的名稱。
triggeringAlertId | 字串 | 觸發調查的警示識別碼。


## <a name="json-representation"></a>Json 標記法

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
