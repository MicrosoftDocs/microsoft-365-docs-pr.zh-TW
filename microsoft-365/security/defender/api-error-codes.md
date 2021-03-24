---
title: 常見的 Microsoft 365 Defender REST API 錯誤碼
description: 深入瞭解常見的 Microsoft 365 Defender REST API 錯誤碼
keywords: api、錯誤、代碼、常見錯誤、mtp、api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ab564ddb0263b501b6aca979f2148dfb5cf92758
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060591"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>常見的 Microsoft 365 Defender REST API 錯誤碼

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 威脅防護

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

錯誤代碼可能會在任何 Microsoft 365 Defender APIs 上的操作傳回。 每個錯誤回應都會包含一則錯誤訊息，可協助您解決問題。 [資料表] 區段中的 [錯誤訊息] 欄提供一些範例訊息。 實際郵件的內容會因觸發回應的因素而異。 在表格中，依角括弧顯示變數內容。

## <a name="error-codes"></a>錯誤碼

錯誤碼 | HTTP 狀態碼 | 郵件
-|-|-
BadRequest | BadRequest (400)  | 一般錯誤要求錯誤訊息。
ODataError | BadRequest (400)  | 不正確 OData URI 查詢 \<the specific error is specified\> 。
InvalidInput | BadRequest (400)  | 輸入無效 \<the invalid input\> 。
InvalidRequestBody | BadRequest (400)  | 不正確要求正文。
InvalidHashValue | BadRequest (400)  | 雜湊值 \<the invalid hash\> 無效。
InvalidDomainName | BadRequest (400)  | 功能變數名稱 \<the invalid domain\> 無效。
InvalidIpAddress | BadRequest (400)  | IP 位址 \<the invalid IP\> 無效。
InvalidUrl | BadRequest (400)  | URL \<the invalid URL\> 無效。
MaximumBatchSizeExceeded | BadRequest (400)  | 超過批次大小上限。 已接收： \<batch size received\> ，允許： {允許的批次大小}。
MissingRequiredParameter | BadRequest (400)  | \<the missing parameter\>缺少參數。
OsPlatformNotSupported | BadRequest (400)  | \<the client OS Platform\>此動作不支援作業系統平臺。
ClientVersionNotSupported | BadRequest (400)  | \<The requested action\> 支援用戶端版本和更新版本 \<supported client version\> 。
未經 授權 | 未經授權的 (401)  | 未經 授權 <br /><br />*附注：通常是由無效或過期的授權標頭所造成。*
禁止 | 禁止 (403)  | 禁止 <br /><br />*附注：有效的權杖，但動作的許可權不足*。
DisabledFeature | 禁止 (403)  | 未啟用租使用者功能。
DisallowedOperation | 禁止 (403)  | \<the disallowed operation and the reason\>.
NotFound | 找不到 (404)  | 找不到一般錯誤訊息。
ResourceNotFound | 找不到 (404)  | \<the requested resource\>找不到資源。
InternalServerError | 內部伺服器錯誤 (500)  | *附注：沒有錯誤訊息，請重試作業，或與 Microsoft 聯繫（如果它未解決）*

## <a name="examples"></a>範例

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a>Body 參數

> [!IMPORTANT]
> 主體參數會區分大小寫。

如果您遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 錯誤，可能是因為鍵入錯誤所造成。 請複查 API 檔，並檢查提交的參數是否符合相關的範例。

## <a name="tracking-id"></a>追蹤識別碼

每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。 此參數的屬性名稱為 *target*。 當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助我們找出問題的根本原因。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [支援的 Microsoft 365 Defender API](api-supported.md)
- [存取 Microsoft 365 Defender APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
