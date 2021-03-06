---
title: 新增或移除電腦標記 API
description: 瞭解如何使用 [新增或移除電腦標記 API]，新增或移除 Microsoft Defender for Endpoint 中電腦的標記。
keywords: api、graph api、支援的 api、標記、電腦標記
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769818"
---
# <a name="add-or-remove-machine-tags-api"></a>新增或移除電腦標記 API

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

新增或移除特定 [電腦](machine.md)的標記。

## <a name="limitations"></a>限制

1. 您可以根據您設定的保留期間，在上次查看的機器上進行開機自檢。

2. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)

許可權類型 |    權限    |    許可權顯示名稱
:---|:---|:---
應用程式 |    ReadWrite。所有 |    「讀取及寫入所有機器資訊」
委派 (工作或學校帳戶)  | ReadWrite | 「讀取及寫入機器資訊」

>[!Note]
> 使用使用者認證取得權杖時：
>
>- 使用者至少必須具備下列角色許可權：「管理安全性設定」。 如需詳細資訊，請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊 () 
>- 使用者必須能夠存取機器（根據電腦群組設定） (請參閱 [建立及管理電腦群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | string | application/json。 **必要欄位**。

## <a name="request-body"></a>要求正文

在要求主體中，提供具有下列參數的 JSON 物件：

參數 |    類型    | 描述
:---|:---|:---
值 |    字串 |    標記名稱。 **必要欄位**。
動作    | Enum |    新增或移除。 允許的值為： "Add" 或 "Remove"。 **必要欄位**。


## <a name="response"></a>回應

如果成功，這個方法會傳回 200-Ok 回應碼和回應內文中的更新電腦。

## <a name="example"></a>範例

**請求**

以下是新增電腦標記之要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- 若要移除電腦標記，請將動作設定為 "Remove"，而不是在要求主體中的 ' Add '。
