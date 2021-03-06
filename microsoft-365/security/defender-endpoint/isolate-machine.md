---
title: 隔離電腦 API
description: 瞭解如何使用隔離機器 API，隔離裝置，使其無法存取 Microsoft Defender for Endpoint 中的外部網路。
keywords: api，graph api，支援的 api，隔離裝置
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772110"
---
# <a name="isolate-machine-api"></a>隔離電腦 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
隔離裝置以存取外部網路。


## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   電腦隔離 |   「隔離電腦」
委派 (工作或學校帳戶)  | 電腦隔離 |  「隔離電腦」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
>- 使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 


## <a name="http-request"></a>HTTP 要求
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
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
留言 |   字串 |    與動作相關聯的批註。 **必要欄位**。
IsolationType   | 字串 |  隔離類型。 允許的值為： "Full" 或 "選擇性"。

**IsolationType** 控制要執行的隔離類型，可以是下列其中一項：
- 完整-完全隔離
- 選擇性–只限制有限的應用程式存取網路 (請參閱 [隔離裝置的網路](respond-machine-alerts.md#isolate-devices-from-the-network) 以取得詳細資料) 


## <a name="response"></a>回應
如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- 若要從隔離釋放裝置，請參閱 [從隔離裝置發行裝置](unisolate-machine.md)。
