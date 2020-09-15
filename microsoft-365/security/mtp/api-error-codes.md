---
title: 常見的 Microsoft 威脅防護 REST API 錯誤代碼
description: 深入瞭解常見的 Microsoft 威脅防護 REST API 錯誤代碼
keywords: api、錯誤、代碼、常見錯誤、mtp、api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650209"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a>常見的 Microsoft 威脅防護 REST API 錯誤代碼

適用於：****
- Microsoft 威脅防護

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

下表所列的錯誤代碼可能會由任何 Microsoft 威脅防護 APIs 上的操作所傳回。

每個錯誤回應都會包含一則錯誤訊息，可協助您解決問題。

郵件是可變更的普通文字。

在頁面底部，您可以找到回應範例。

錯誤碼 |HTTP 狀態碼 |訊息 
:---|:---|:---
BadRequest | BadRequest (400)  | 一般錯誤要求錯誤訊息。
ODataError | BadRequest (400)  | OData URI 查詢無效 () 指定特定錯誤。
InvalidInput | BadRequest (400)  | 不正確輸入 {不正確輸入}。
InvalidRequestBody | BadRequest (400)  | 不正確要求正文。
InvalidHashValue | BadRequest (400)  | 雜湊值 {不正確雜湊} 無效。
InvalidDomainName | BadRequest (400)  | 功能變數名稱 {不正確網域} 無效。
InvalidIpAddress | BadRequest (400)  | IP 位址 {不正確 IP} 無效。
InvalidUrl | BadRequest (400)  | URL {不正確 URL} 無效。
MaximumBatchSizeExceeded | BadRequest (400)  | 超過批次大小上限。 已接收： {已接收的批次大小}，允許： {允許的批次大小}。
MissingRequiredParameter | BadRequest (400)  | 參數 {遺失的參數} 缺失。
OsPlatformNotSupported | BadRequest (400)  | 作業系統平臺 {用戶端作業系統平臺} 不支援此動作。
ClientVersionNotSupported | BadRequest (400)  | {用戶端版本 {支援的用戶端版本} 和更新版本支援要求的動作}。
未經 授權 | 未經授權的 (401)  | 未經授權的 (通常會無效或過期的授權標頭) 。
禁止 | 禁止 (403)  | 已禁止 (有效的權杖，但動作) 的許可權不足。
DisabledFeature | 禁止 (403)  | 未啟用租使用者功能。
DisallowedOperation | 禁止 (403)  | {不允許的作業及原因}。
NotFound | 找不到 (404)  | 找不到一般錯誤訊息。
ResourceNotFound | 找不到 (404)  | Resource {找不到要求的資源}。
InternalServerError | 內部伺服器錯誤 (500)  |  (沒有錯誤訊息，請重試此作業，或與我們聯繫（如果它未解決）) 

## <a name="body-parameters-are-case-sensitive"></a>主體參數區分大小寫

提交的主體參數目前是區分大小寫的。
<br>如果您遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 錯誤，這可能是由錯誤的參數大寫或小寫字母所導致。
<br>建議您複查 API 檔頁面，並檢查提交的參數是否符合相關的範例。

## <a name="correlation-request-id"></a>關聯要求識別碼

每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。
<br>此參數的屬性名稱為 "target"。
<br>當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助找出問題的根本原因。

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

