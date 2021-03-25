---
title: 依標記 API 尋找裝置
description: 尋找所有包含 specifc 標記的裝置
keywords: api，支援的 api，get，裝置，尋找，尋找裝置，依標記，標記
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200146"
---
# <a name="find-devices-by-tag-api"></a>依標記 API 尋找裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
依[標記](machine-tags.md)尋找[電腦](machine.md)。
<br>```startswith``` 支援查詢。 

## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Read。所有 |  「讀取所有機器設定檔」
應用程式 |   ReadWrite。所有 | 「讀取及寫入所有機器資訊」
委派 (工作或學校帳戶)  | 電腦. 讀取 | 「讀取機器資訊」
委派 (工作或學校帳戶)  | ReadWrite | 「讀取及寫入機器資訊」

>[!Note]
> 使用使用者認證取得權杖時：
> - 回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 
> - 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
> - 回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。

## <a name="request-uri-parameters"></a>要求 URI 參數

名稱 | 類型 | 描述
:---|:---|:---
Tag | 字串 | 標記名稱。 **必要欄位**。
useStartsWithFilter | 布林值 | 設為 true 時，搜尋會尋找所有具有標籤名稱的標籤以查詢中指定的標記開始的所有裝置。 預設值為 false。 此為選擇性欄位。

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功-200 OK （含回應內的機器清單）。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```