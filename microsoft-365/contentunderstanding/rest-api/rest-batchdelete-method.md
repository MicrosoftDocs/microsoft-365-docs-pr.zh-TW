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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904177"
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

| 標頭 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要。|

## <a name="request-body"></a>要求內文

| 名稱 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|是|string|模型檔案的唯一識別碼。|
TargetSiteUrl|是|string|目標程式庫網站的完整 URL。|
TargetWebServerRelativeUrl|是|string|目標程式庫網頁的伺服器相對 URL。|
TargetLibraryServerRelativeUrl|是|string|目標程式庫的伺服器相對 URL。|
ViewOption|否|string|指定是否要將新模型檢視設定為程式庫預設值。|

## <a name="response"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|200 OK| |成功|


## <a name="examples"></a>範例

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>從存放庫網站中的合約文件庫移除模型

在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

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
