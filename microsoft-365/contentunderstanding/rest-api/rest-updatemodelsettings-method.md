---
title: UpdateModelSettings
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
description: 使用 REST API 來更新 SharePoint Syntex 文件了解模型的可用模型設定。
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288644"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)(查看[範例](rest-updatemodelsettings-method.md#examples))。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI 參數

|名稱 |於 |必要項目|類型|描述|
|-----|---|--------|----|-----------|
|modelFileName|查詢|對|string|Syntex 模型檔案的名稱。|

## <a name="request-headers"></a>要求標頭

| 頁首 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|目前網站的適當摘要。|

## <a name="request-body"></a>要求內文

|名稱    |類型   |描述 |
|--------|-------|-------|
|ModelSettings|string|模型設定 JSON。|
|描述|string|模型描述。|
|保留標籤| |相關聯標籤的資訊 (標籤識別碼和名稱)。|

## <a name="responses"></a>回應

| 名稱   | 類型  | 描述|
|--------|-------|------------|
|200 OK| |成功|

## <a name="examples"></a>範例

### <a name="update-model-settings-for-contoso-contract"></a>更新 Contoso 合約的模型設定

在此範例中，模型描述和「標準保留」保留標籤會更新。 保留標籤的識別碼為 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。

#### <a name="sample-request"></a>範例要求

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>範例回應

**狀態碼：** 200

## <a name="see-also"></a>另請參閱

[Syntex 文件瞭解模型 REST API](syntex-model-rest-api.md)
