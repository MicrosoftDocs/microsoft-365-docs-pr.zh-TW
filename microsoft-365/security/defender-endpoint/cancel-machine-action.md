---
title: 取消電腦動作 API
description: 瞭解如何取消已啟動的機器動作
keywords: api、graph api、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879697"
---
#   <a name="cancel-machine-action-api"></a>取消電腦動作 API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

取消已啟動的機器動作，該動作尚未處於最終狀態 (已完成、取消、失敗) 。

## <a name="limitations"></a>限制

1.  此 API 的速率限制為每分鐘100個通話，每小時1500個通話。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。

|     許可權類型     |     權限     |    許可權顯示名稱     |
|-|-|-|
|    <br>應用程式    |    <br>CollectForensic<br>   電腦隔離   <br>RestrictExecution<br>   電腦。掃描<br>   下架<br>   StopAndQuarantine<br>   LiveResponse    |    收集辯論   <br>隔離電腦<br>限制程式碼執行<br>  掃描電腦<br>  下架機<br>   停止和隔離<br>   在特定電腦上執行 live 回應    |
|    <br>委派 (工作或學校帳戶)     |    CollectForensic<br>   電腦隔離    <br>RestrictExecution<br>   電腦。掃描<br>   下架<br>   StopAndQuarantineMachine。 LiveResponse    |    收集辯論<br>   隔離電腦<br>  限制程式碼執行<br> 掃描電腦<br>下架機<br> 停止和隔離<br> 在特定電腦上執行 live 回應    |


## <a name="http-request"></a>HTTP 要求

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>要求標頭

| 名稱      | 類型 | 描述                 |
|---------------|----------|---------------------------------|
| 授權 | 字串   | 載荷 {token}。 此為必要動作。   |
| Content-Type  | string   | application/json。 此為必要動作。 |

## <a name="request-body"></a>要求正文

| 參數 | 類型 | 描述                        |
|---------------|----------|----------------------------------------|
| 留言       | 字串   | 與取消動作相關聯的批註。  |

## <a name="response"></a>回應

若成功，這個方法會傳回200，具有機器動作實體的 Ok 回應碼。 如果找不到具有指定識別碼的 machine action 實體-找不到404。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>相關主題

- [取得機器動作 API](get-machineaction-object.md)