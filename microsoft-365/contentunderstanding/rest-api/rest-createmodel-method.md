---
title: 建立模型
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
description: 使用 REST API 建立模型及其相關聯的內容類型。
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904185"
---
# <a name="create-model"></a>建立模型

建立模型及其相關聯的內容類型。 請注意，這只會建立模型。 它仍然需要在內容中心進行訓練 (請參閱[範例](rest-createmodel-method.md#examples))。

## <a name="http-request"></a>HTTP 要求

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>URI 參數

無

## <a name="request-headers"></a>要求標頭

| 頁首 | 值 |
|--------|-------|
|接受|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要|

## <a name="request-body"></a>要求內文

|名稱    |類型   |描述 |
|--------|-------|------------|
|中繼資料(_M)|  |在 SPO 上設定物件 Meta。 一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}。 |
|ContentTypeGroup|string|與模型相關聯的相關聯內容類型群組。 預設為「智慧型文件內容類型」。|
|ContentTypeName|string|關聯的內容類型名稱。 建立的模型檔案將會有相同的名稱。|

## <a name="responses"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|201 已建立| |成功|

## <a name="examples"></a>範例

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>建立名為「Contoso 合約」的新文件了解模型

#### <a name="sample-request"></a>範例要求

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a>範例回應

**狀態碼:** 201

## <a name="see-also"></a>另請參閱

[Syntex 文件了解模型 REST API](syntex-model-rest-api.md)
