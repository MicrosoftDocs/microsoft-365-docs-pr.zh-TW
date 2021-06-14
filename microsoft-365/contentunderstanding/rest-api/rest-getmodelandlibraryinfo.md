---
title: 取得模型和程式庫資訊
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
description: 使用 REST API 來取得模型及套用其所在程式庫的相關資訊。
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904188"
---
# <a name="get-model-and-library-information"></a>取得模型和程式庫資訊

取得模型及套用其所在程式庫的相關資訊 (請參閱[範例](rest-getmodelandlibraryinfo.md#examples))。

## <a name="http-request"></a>HTTP 要求

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a>URI 參數

| 名稱 | 於 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|查詢|True|GUID|模型檔案的唯一識別碼。|

## <a name="request-headers"></a>要求標頭

| 標頭 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|


## <a name="request-body"></a>要求內文

| 名稱 | 必要項目 | 類型 | 描述 |
|--------|-------|--------|------------|
|ModelUniqueId|是|string|模型檔案的唯一識別碼。|
|TargetSiteUrl|是|string|目標程式庫網站的完整 URL。|
|TargetWebServerRelativeUrl|是|string|目標程式庫網頁的伺服器相對 URL。|
|TargetLibraryServerRelativeUrl|是|string|目標程式庫的伺服器相對 URL。|
|TargetLibraryRemoved|是|int|指出是否已移除目標程式庫的旗標。|

## <a name="response"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|200 OK| |成功|
|201 已建立| |請注意，由於此 API 支援將模型套用至多個程式庫，因此即使將模型套用至其中一個程式庫失敗，也可能傳回 201。 <br>檢查回應內文，了解模型是否成功套用至所有指定的程式庫。 如需詳細資料，請參閱[要求內文](rest-getmodelandlibraryinfo.md#request-body)。|

## <a name="examples"></a>範例

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a>取得存放庫網站中合約模型和主要文件庫的資訊

在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

#### <a name="sample-request"></a>範例要求

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a>範例回應

**狀態碼：** 200

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a>另請參閱

[Syntex 文件瞭解模型 REST API](syntex-model-rest-api.md)
