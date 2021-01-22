---
title: 常見的 Microsoft 365 Defender REST API 錯誤碼
description: 瞭解常見的 Microsoft 365 Defender REST API 錯誤碼
keywords: api， 錯誤， 程式碼， 常見錯誤， mtp， api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928387"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>常見的 Microsoft 365 Defender REST API 錯誤碼

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 威脅防護

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

任何 Microsoft 365 Defender API 上的作業可能會返回錯誤碼。 每個錯誤回應都會包含錯誤訊息，可協助解決問題。 表格區段的錯誤訊息欄提供一些範例訊息。 實際郵件的內容會根據觸發回應的因素而不同。 在表格中以角括弧表示變數內容。

## <a name="error-codes"></a>錯誤碼

錯誤碼 | HTTP 狀態碼 | 訊息
-|-|-
BadRequest | BadRequest (400)  | 一般錯誤要求錯誤訊息。
ODataError | BadRequest (400)  | 不正確 OData URI 查詢 \<the specific error is specified\> 。
InvalidInput | BadRequest (400)  | 不正確輸入 \<the invalid input\> 。
InvalidRequestBody | BadRequest (400)  | 不正確要求內方。
InvalidHashValue | BadRequest (400)  | 雜湊 \<the invalid hash\> 值無效。
InvalidDomainName | BadRequest (400)  | 功能變數名稱 \<the invalid domain\> 無效。
InvalidIpAddress | BadRequest (400)  | IP \<the invalid IP\> 位址無效。
InvalidUrl | BadRequest (400)  | URL \<the invalid URL\> 無效。
MaximumBatchSizeExceeded | BadRequest (400)  | 已超過批次大小上限。 收到 \<batch size received\> ：，允許：{batch size allowed}。
MissingRequiredParameter | BadRequest (400)  | 參數 \<the missing parameter\> 遺失。
OsPlatformNotSupported | BadRequest (400)  | 不支援 \<the client OS Platform\> 作業系統平臺執行此動作。
ClientVersionNotSupported | BadRequest (400)  | \<The requested action\> 支援用戶端版本及 \<supported client version\> 更新版本。
未經 授權 | 未經授權的 (401)  | 未經 授權 <br /><br />*注意：通常是由無效或過期的授權標題所導致。*
禁止 | 禁止 (403)  | 禁止 <br /><br />*注意：有效的權杖，但動作許可權不足*。
DisabledFeature | 禁止 (403)  | 未啟用租使用者功能。
不允許的Operation | 禁止 (403)  | \<the disallowed operation and the reason\>.
NotFound | 找不到 (404)  | 一般找不到錯誤訊息。
ResourceNotFound | 找不到 (404)  | 找不到 \<the requested resource\> 資源。
InternalServerError | 內部伺服器錯誤 (500)  | *注意：沒有錯誤訊息，請重試作業，或如果無法解決，請聯絡 Microsoft*

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
> 本參數會區分大小寫。

如果您遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 錯誤，這可能是因為錯字所造成。 檢閱 API 檔，並檢查提交的參數是否與相關範例相符。

## <a name="tracking-id"></a>追蹤識別碼

每個錯誤回應都包含用於追蹤的唯一識別碼參數。 此參數的屬性名稱為 *目標*。 當我們詢問錯誤時，附加此識別碼將可協助我們找出問題的根本原因。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender API 概觀](api-overview.md)
- [支援的 Microsoft 365 Defender API](api-supported.md)
- [存取 Microsoft 365 Defender API](api-access.md)
- [瞭解 API 限制與授權](api-terms.md)
