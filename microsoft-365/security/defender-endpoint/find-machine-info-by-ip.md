---
title: 依內部 IP API 尋找裝置資訊
description: 使用此 API 來建立與在內部 IP 中尋找特定時間戳記的裝置專案相關的呼叫。
keywords: ip，api，graph api，支援的 api，尋找裝置，裝置資訊
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166466"
---
# <a name="find-device-information-by-internal-ip-api"></a>依內部 IP API 尋找裝置資訊

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

依內部 IP 尋找裝置。

>[!NOTE]
>時間戳記必須在過去30天內。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | Read。所有 | 「讀取所有機器設定檔」
應用程式 | ReadWrite。所有 | 「讀取及寫入所有機器資訊」

## <a name="http-request"></a>HTTP 要求
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。


## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功且機器存在-200 OK。
如果找不到任何機器-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**回應**

以下是回應的範例。

回應會傳回在時間戳記之前和之後16分鐘內，報告此 IP 位址的所有裝置清單。 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
