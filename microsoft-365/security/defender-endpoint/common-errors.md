---
title: 常見 Microsoft Defender for Endpoint API 錯誤
description: 使用說明的常見 Microsoft Defender 的端點 API 錯誤清單。
keywords: api、mdatp api、錯誤、疑難排解
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
ms.technology: mde
ms.openlocfilehash: 4fc2aeb6ee5a95f7eb121abdcf4431dc6d34cd49
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893458"
---
# <a name="common-rest-api-error-codes"></a>常見的 REST API 錯誤碼

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* 下表所列的錯誤碼可能會由任何 Microsoft Defender for Endpoint APIs 上的操作所傳回。
* 除了錯誤碼之外，每個錯誤回應都會包含錯誤訊息，可協助您解決問題。
* 郵件是可變更的普通文字。
* 在頁面底部，您可以找到回應範例。

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

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
未經 授權 | 未經授權的 (401)  | 未授權 (無效或過期的授權標頭) 。
禁止 | 禁止 (403)  | 已禁止 (有效的權杖，但動作) 的許可權不足。
DisabledFeature | 禁止 (403)  | 未啟用租使用者功能。
DisallowedOperation | 禁止 (403)  | {不允許的作業及原因}。
NotFound | 找不到 (404)  | 找不到一般錯誤訊息。
ResourceNotFound | 找不到 (404)  | Resource {找不到要求的資源}。
InternalServerError | 內部伺服器錯誤 (500)  |  (無錯誤訊息，請重試作業) 
TooManyRequests |  (429 的要求太多)  | 回應會以要求數目或 CPU 來表示達到配額限制。

## <a name="body-parameters-are-case-sensitive"></a>主體參數區分大小寫

提交的主體參數目前是區分大小寫的。
<br>如果您遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 錯誤，這可能是由錯誤的參數大寫或小寫字母所導致。
<br>請參閱 API 檔頁面，並檢查提交的參數是否符合相關的範例。

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
