---
title: 更新電腦實體 API
description: 瞭解如何使用此 API 更新電腦標記。 您可以更新 tags 和 devicevalue 屬性。
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985628"
---
# <a name="update-machine"></a>更新電腦 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
更新現有 [電腦](machine.md)的屬性。
<br>可更新的屬性為： ```machineTags``` 和 ```deviceValue``` 。


## <a name="limitations"></a>限制
1. 您可以更新 API 中提供的電腦。 
2. 更新機器只會將標記附加到 tag 集合。 如果有標籤存在，必須將它們包含在本文的 tags 集合中。
3. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   ReadWrite。所有 | 「讀取及寫入所有機器的機器資訊」
委派 (工作或學校帳戶)  | ReadWrite | 「讀取及寫入機器資訊」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「警示調查」。 如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)。
>- 使用者必須根據裝置群組設定，才能存取與警示相關聯的裝置。 如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。

## <a name="http-request"></a>HTTP 要求
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | 字串 | application/json。 **必要欄位**。


## <a name="request-body"></a>要求內文
在要求內文中，提供應該更新之相關欄位的值。
<br>在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。 
<br>為了達到最佳效能，您不應包含尚未變更的現有值。

屬性	 | 類型 | 描述
:---|:---|:---
machineTags | String 集合 | [電腦](machine.md)標記的集合。
deviceValue | 可為 null 的列舉 | [裝置的值](tvm-assign-device-value.md)。 可能的值為： ' Normal '、' Low ' 和 ' High '。

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，以及回應內文中的 [machine](machine.md) 實體具有更新的屬性。 如果本文中的機器標記集合中不包含現有的電腦標記-400 無效輸入，以及通知遺失標記/s 的訊息。
如果找不到具有指定識別碼的電腦-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
