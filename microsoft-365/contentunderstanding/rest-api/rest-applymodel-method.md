---
title: 套用模型
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
description: 使用 REST API 將文件了解模型套用至一或多個文件庫。
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904205"
---
# <a name="apply-model"></a>套用模型

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
|接受|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要。|

## <a name="request-body"></a>要求內文

| 名稱 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|是|string|模型檔案的唯一識別碼。|
TargetSiteUrl|是|string|目的文件庫網站的完整 URL。|
TargetWebServerRelativeUrl|是|string|目的文件庫之網頁的伺服器相對 URL。|
TargetLibraryServerRelativeUrl|是|string|目的文件庫的伺服器相對 URL。|
ViewOption|否|string|指定是否要將新模型檢視設定為文件庫預設值。|

## <a name="response"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|200 OK| |成功|
|201 已建立| |請注意，由於此 API 支援將模型套用至多個程式庫，因此即使將模型套用至其中一個程式庫失敗，也可讓 201 返回。 <br>檢查回應本文，了解模型是否成功套用至所有指定的程式庫。 請參閱[要求本文](rest-applymodel-method.md#request-body)取得詳細資訊。|

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

**狀態碼:** 200

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

[Syntex 文件了解模型 REST API](syntex-model-rest-api.md)
