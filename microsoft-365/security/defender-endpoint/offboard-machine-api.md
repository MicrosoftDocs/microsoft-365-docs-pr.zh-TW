---
title: 下架 machine API
description: 瞭解如何使用 API，從 Windows Defender 高級威脅防護 (WDATP) 中，下架裝置。
keywords: api、graph api、支援的 api、收集調查套件
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
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187123"
---
# <a name="offboard-machine-api"></a>下架 machine API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
下架裝置從 Defender 取得端點。


## <a name="limitations"></a>限制
 - 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> Windows 10、版本1703和更新版本或 Windows Server 2019 及更新版本都支援此 API。 MacOS 或 Linux 裝置不支援此 API。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   下架 |  ' 下架電腦 '
委派 (工作或學校帳戶)  |    下架 |  ' 下架電腦 '

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者需要「全域 Admin」 AD 角色
>- 使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
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

## <a name="response"></a>回應
如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
