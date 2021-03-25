---
title: 依軟體列出裝置
description: 檢索已安裝此軟體的裝置清單。
keywords: api，graph api，支援的 api，get，列出裝置，裝置清單，依軟體的清單裝置，mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200386"
---
# <a name="list-devices-by-software"></a>依軟體列出裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

取得安裝了此軟體的裝置參考清單。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 | 已讀取軟體。所有 | 「讀取威脅和弱點管理軟體資訊」
委派 (工作或學校帳戶)  | 軟體. 讀取 | 「讀取威脅和弱點管理軟體資訊」

## <a name="http-request"></a>HTTP 要求
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>要求標頭

| 名稱        | 類型 | 描述
|:--------------|:-------|:--------------|
| 授權 | 字串 | 載荷 {token}。**必要**。

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK 和裝置清單，其中的軟體是安裝在本文中。 


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**回應**

以下是回應的範例。

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>相關主題
- [風險威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威脅 & 弱點軟體清單](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
