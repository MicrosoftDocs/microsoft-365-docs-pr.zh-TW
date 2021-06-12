---
title: SharePoint Syntex 文件瞭解模型 REST API
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
description: SharePoint Syntex 文件瞭解模型 REST API 概觀。
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904193"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>SharePoint Syntex 文件瞭解模型 REST API

您可以使用 SharePoint REST 介面來建立文件瞭解模型、將模型套用或移除至一或多個文件庫，以及取得或更新模型的資訊。 

SharePoint Online (以及 SharePoint 2016 及更新版本內部部署) REST 服務支援使用 OData $batch 查詢選項，將多個要求合併為單一呼叫服務。 

有關程式碼範例的詳細資訊和連結，請參閱[使用 REST API 執行批次要求](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md)。

## <a name="prerequisites"></a>必要條件

在開始使用之前，請確定您熟悉下列內容：

- [認識 SharePoint REST 服務](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [使用 SharePoint REST 端點完成基本作業](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a>REST 命令

下列 REST 命令可用於使用 Syntex 文件瞭解模型：

- [建立模型](rest-createmodel-method.md) – 建立模型及其相關聯的內容類型。
- [GetByUniqueId](rest-getbyuniqueid-method.md) – 取得或更新 SharePoint Syntex 文件瞭解模型的資訊。
- [GetByTitle](rest-getbytitle-method.md) – 使用模型標題取得或更新 SharePoint Syntex 文件瞭解模型的資訊。
- [套用模型](rest-applymodel-method.md) – 將訓練過的文件瞭解模型套用 (或同步處理) 至一或多個文件庫。
- [取得模型和文件庫](rest-getmodelandlibraryinfo.md) – 取得模型及其已套用之文件庫的資訊。
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – 更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)。
- [BatchDelete](rest-batchdelete-method.md) – 從一或多個文件庫移除已套用的文件瞭解模型。
- [建立分類要求](rest-createclassificationrequest.md) - 使用已套用模型建立要求，以將指定的檔案分類。

## <a name="scenarios"></a>案例

請注意下列從方法名稱來看並不直觀的案例範例。 如需詳細資訊，請參閱每篇文章。

建立模型方法只會建立模型物件及其關聯的內容類型。 您首先需要在內容中心訓練模型，才能將模型套用至文件庫。

套用模型方法可用來設定目的文件庫上的模型，以分類文件和選擇性擷取其他資訊。 此 API 也支援批次將模型套用於多個文件庫。

移除模型方法只是從先前已套用模型的一或多個文件庫移除模型。 如果您想要刪除模型，必須先從已套用模型的所有文件庫移除模型。


## <a name="see-also"></a>另請參閱

[文件瞭解概觀](../document-understanding-overview.md)

