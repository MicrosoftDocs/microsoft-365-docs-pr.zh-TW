---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: 使用 REST API 從一或多個程式庫移除已套用的文件瞭解模型。
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287450"
---
# <a name="batchdelete"></a>BatchDelete

從一或多個程式庫移除已套用的文件瞭解模型。 請注意，必須先從所有程式庫移除模型，才能刪除模型 (請參閱[範例](rest-batchdelete-method.md#examples))。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>URI 參數

無

## <a name="request-headers"></a>要求標頭

| 頁首 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要。|

## <a name="request-body"></a>要求內文

| 名稱 | 必要項目 | 類型 | 說明 |
|--------|-------|--------|------------|
|出版物|是|MachineLearningPublicationEntityData[]|MachineLearningPublicationEntityData 的集合，每個集合會指定模型和目的文件庫。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名稱 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|是|string|模型檔案的唯一識別碼。|
|TargetSiteUrl|是|string|目標程式庫網站的完整 URL。|
|TargetWebServerRelativeUrl|是|string|目標程式庫網頁的伺服器相對 URL。|
|TargetLibraryServerRelativeUrl|是|string|目標程式庫的伺服器相對 URL。|

## <a name="response"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|200 OK||這是自訂的 API，用來支援從多個文件庫移除模型。在部分成功的情況下，仍可以傳回 200 OK，而且呼叫者必須檢查回應內文，以了解是否已成功從文件庫移除模型。|

## <a name="response-body"></a>回應本文

| 名稱   | 類型  | 說明|
|--------|-------|------------|
|TotalSuccesses|int|成功從文件庫移除的模型總數。|
|TotalFailures|int|無法從文件庫中移除的模型總數。|
|詳細資料|MachineLearningPublicationResult[]|MachineLearningPublicationResult 的集合，每個集合會指定將模型從文件庫中移除的詳細結果。|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| 名稱   | 類型  | 說明|
|--------|-------|------------|
|StatusCode|int|HTTP 狀態碼。|
|ErrorMessage|字串|錯誤訊息，說明將模型套用至文件庫時發生的錯誤。|
|出版物|MachineLearningPublicationEntityData|它會指定模型資訊和目的文件庫。| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名稱 | 類型 | 描述 |
|--------|--------|------------|
|ModelUniqueId|string|模型檔案的唯一識別碼。|
|TargetSiteUrl|string|目標程式庫網站的完整 URL。|
|TargetWebServerRelativeUrl|string|目標程式庫網頁的伺服器相對 URL。|
|TargetLibraryServerRelativeUrl|string|目標程式庫的伺服器相對 URL。|

## <a name="examples"></a>範例

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>從存放庫網站中的合約文件庫移除模型

在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

#### <a name="sample-request"></a>範例要求

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>範例回應

在回應中，TotalFailures 和 TotalSuccesses 是指從指定程式庫中移除之模型的失敗和成功次數。

**狀態碼：** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>另請參閱

[Syntex 文件瞭解模型 REST API](syntex-model-rest-api.md)
