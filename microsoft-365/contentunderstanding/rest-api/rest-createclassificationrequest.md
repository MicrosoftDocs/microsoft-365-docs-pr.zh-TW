---
title: 建立分類要求
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
description: 使用 REST API 建立要求，以使用訓練過的文件了解模型來分類一或多個文件。
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287230"
---
# <a name="create-classification-request"></a>建立分類要求

建立要求來使用已套用的文件了解模型分類一或多個文件 (請參閱 [範例](rest-createclassificationrequest.md#examples))。

SharePoint Online (以及 SharePoint 2016 及更高版本內部部署) REST 服務支援合併多個要求。 要求會使用 OData $batch 查詢選項合併為對服務的單一呼叫。 這個方法可用來一次將數百份文件的分類工作項目加入佇列。

## <a name="http-request"></a>HTTP 要求

```http
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a>URI 參數

無

## <a name="request-headers"></a>要求標頭

| 頁首 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要|

## <a name="request-body"></a>要求內文

|名稱    |類型   |描述 |
|--------|-------|------------|
|中繼資料(_M)|string |在 SPO 上設定物件 Meta。 一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}。 |
|TargetSiteId|GUID|要分類之檔案所在的網站識別碼。|
|TargetWebId|GUID|要分類之檔案所在的網頁識別碼。|
|TargetUniqueId|GUID|要分類之檔案的識別碼。|

## <a name="responses"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|201 已建立| |成功|

## <a name="examples"></a>範例

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>將識別碼為 "e6cff8b7-c90c-4564-b5b8-033449090932" 的檔案分類要求加入佇列

#### <a name="sample-request"></a>範例要求

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>範例回應

**狀態碼:** 201

## <a name="see-also"></a>另請參閱

[Syntex 文件瞭解模型 REST API](syntex-model-rest-api.md)
