---
title: 取得裝置安全分數
description: 會檢索組織裝置安全分數。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772302"
---
# <a name="get-device-secure-score"></a>取得裝置安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


會 [為裝置檢索您的 Microsoft 安全分數](tvm-microsoft-secure-score-devices.md)。 針對裝置的 Microsoft 安全分數較高表示您的端點對 cybersecurity 威脅攻擊的彈性程度較高。 

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Alll |   「讀取威脅和弱點管理得分」
委派 (工作或學校帳戶)  | 讀取 | 「讀取威脅和弱點管理得分」

## <a name="http-request"></a>HTTP 要求

```
GET /api/configurationScore
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。

## <a name="request-body"></a>要求正文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回 200 OK，並提供回應內文中的裝置安全分數資料。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a>回應

以下是回應的範例。

>[!NOTE]
>在這裡顯示的回應清單可能會因簡潔而截斷。 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>另請參閱

- [使用 Microsoft Defender for Endpoint OData 查詢](exposed-apis-odata-samples.md)
