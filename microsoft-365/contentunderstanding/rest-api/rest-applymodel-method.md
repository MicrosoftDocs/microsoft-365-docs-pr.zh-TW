---
title: 批次套用模型
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
description: 使用 REST API 將文件瞭解模型套用至一或多個程式庫。
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286534"
---
# <a name="batch-apply-model"></a>批次套用模型

將訓練過的文件瞭解模型套用 (或同步處理) 至一或多個文件庫 (查看[範例](rest-applymodel-method.md#examples))。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__中繼資料|是|string|在 SPO 上設定物件 Meta。 一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}。|
|出版物|是|MachineLearningPublicationEntityData[]|MachineLearningPublicationEntityData 的集合，每個集合會指定模型和目的文件庫。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名稱 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|是|string|模型檔案的唯一識別碼。|
|TargetSiteUrl|是|string|目標程式庫網站的完整 URL。|
|TargetWebServerRelativeUrl|是|string|目標程式庫網頁的伺服器相對 URL。|
|TargetLibraryServerRelativeUrl|是|string|目標程式庫的伺服器相對 URL。|
|ViewOption|否|string|指定是否要將新模型檢視設定為程式庫預設值。|

## <a name="response"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|201 已建立||這是自訂的 API，用來支援套用模型至多個文件庫。在部分成功的情況下，仍可以傳回 201 已建立，而且呼叫者必須檢查回應內文，以了解是否已成功將模型套用至文件庫。|

## <a name="response-body"></a>回應本文

| 名稱   | 類型  | 說明|
|--------|-------|------------|
|TotalSuccesses|int|成功套用至文件庫的模型總數。|
|TotalFailures|int|無法套用至文件庫的模型總數。|
|詳細資料|MachineLearningPublicationResult[]|MachineLearningPublicationResult 的集合，每個集合會指定將模型套用至文件庫的詳細結果。|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>將模型套用至存放庫網站中的合約文件庫

在此範例中，Contoso 合約文件了解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

#### <a name="sample-request"></a>範例要求

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>範例回應

在回應中，TotalFailures 和 TotalSuccesses 是指要套用至指定程式庫之模型的失敗和成功次數。

**狀態碼:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>另請參閱

[Syntex 文件瞭解模型 REST API](syntex-model-rest-api.md)
