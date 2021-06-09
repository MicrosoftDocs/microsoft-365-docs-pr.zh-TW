---
title: 依設備群組列出曝光排名
description: 依設備群組來檢索曝光分數的清單。
keywords: api、graph api、支援的 api、get、洩密分數、裝置群組、裝置群組暴露分數
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a7f343db64174fe3c48eaf8b584b03b53921edcb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843611"
---
# <a name="list-exposure-score-by-device-group"></a>依設備群組列出曝光排名

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

會檢索與特定網域位址相關的警示集合。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 | Read。所有 | 「讀取威脅和弱點管理得分」
委派 (工作或學校帳戶)  | 讀取 | 「讀取威脅和弱點管理得分」

## <a name="http-request"></a>HTTP 要求

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>要求標頭

| 名稱        | 類型 | 描述
|:--------------|:-------|:--------------|
| 授權 | 字串 | 載荷 {token}。**必要**。

## <a name="request-body"></a>要求正文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回 200 OK，顯示回應內文中每個裝置群組資料的暴露分數清單。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a>回應

以下是回應的範例。

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>相關主題

- [風險威脅 & 弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威脅 & 漏洞洩密分數](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
