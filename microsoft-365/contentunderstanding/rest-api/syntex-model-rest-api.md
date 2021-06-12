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
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="11e74-103">SharePoint Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="11e74-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="11e74-104">您可以使用 SharePoint REST 介面來建立文件瞭解模型、將模型套用或移除至一或多個文件庫，以及取得或更新模型的資訊。</span><span class="sxs-lookup"><span data-stu-id="11e74-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="11e74-105">SharePoint Online (以及 SharePoint 2016 及更新版本內部部署) REST 服務支援使用 OData $batch 查詢選項，將多個要求合併為單一呼叫服務。</span><span class="sxs-lookup"><span data-stu-id="11e74-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="11e74-106">有關程式碼範例的詳細資訊和連結，請參閱[使用 REST API 執行批次要求](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="11e74-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="11e74-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="11e74-107">Prerequisites</span></span>

<span data-ttu-id="11e74-108">在開始使用之前，請確定您熟悉下列內容：</span><span class="sxs-lookup"><span data-stu-id="11e74-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="11e74-109">認識 SharePoint REST 服務</span><span class="sxs-lookup"><span data-stu-id="11e74-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="11e74-110">使用 SharePoint REST 端點完成基本作業</span><span class="sxs-lookup"><span data-stu-id="11e74-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="11e74-111">REST 命令</span><span class="sxs-lookup"><span data-stu-id="11e74-111">REST commands</span></span>

<span data-ttu-id="11e74-112">下列 REST 命令可用於使用 Syntex 文件瞭解模型：</span><span class="sxs-lookup"><span data-stu-id="11e74-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="11e74-113">[建立模型](rest-createmodel-method.md) – 建立模型及其相關聯的內容類型。</span><span class="sxs-lookup"><span data-stu-id="11e74-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="11e74-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – 取得或更新 SharePoint Syntex 文件瞭解模型的資訊。</span><span class="sxs-lookup"><span data-stu-id="11e74-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="11e74-115">[GetByTitle](rest-getbytitle-method.md) – 使用模型標題取得或更新 SharePoint Syntex 文件瞭解模型的資訊。</span><span class="sxs-lookup"><span data-stu-id="11e74-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="11e74-116">[套用模型](rest-applymodel-method.md) – 將訓練過的文件瞭解模型套用 (或同步處理) 至一或多個文件庫。</span><span class="sxs-lookup"><span data-stu-id="11e74-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="11e74-117">[取得模型和文件庫](rest-getmodelandlibraryinfo.md) – 取得模型及其已套用之文件庫的資訊。</span><span class="sxs-lookup"><span data-stu-id="11e74-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="11e74-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – 更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)。</span><span class="sxs-lookup"><span data-stu-id="11e74-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="11e74-119">[BatchDelete](rest-batchdelete-method.md) – 從一或多個文件庫移除已套用的文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="11e74-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="11e74-120">[建立分類要求](rest-createclassificationrequest.md) - 使用已套用模型建立要求，以將指定的檔案分類。</span><span class="sxs-lookup"><span data-stu-id="11e74-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="11e74-121">案例</span><span class="sxs-lookup"><span data-stu-id="11e74-121">Scenarios</span></span>

<span data-ttu-id="11e74-122">請注意下列從方法名稱來看並不直觀的案例範例。</span><span class="sxs-lookup"><span data-stu-id="11e74-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="11e74-123">如需詳細資訊，請參閱每篇文章。</span><span class="sxs-lookup"><span data-stu-id="11e74-123">For more information, see each article.</span></span>

<span data-ttu-id="11e74-124">建立模型方法只會建立模型物件及其關聯的內容類型。</span><span class="sxs-lookup"><span data-stu-id="11e74-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="11e74-125">您首先需要在內容中心訓練模型，才能將模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="11e74-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="11e74-126">套用模型方法可用來設定目的文件庫上的模型，以分類文件和選擇性擷取其他資訊。</span><span class="sxs-lookup"><span data-stu-id="11e74-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="11e74-127">此 API 也支援批次將模型套用於多個文件庫。</span><span class="sxs-lookup"><span data-stu-id="11e74-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="11e74-128">移除模型方法只是從先前已套用模型的一或多個文件庫移除模型。</span><span class="sxs-lookup"><span data-stu-id="11e74-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="11e74-129">如果您想要刪除模型，必須先從已套用模型的所有文件庫移除模型。</span><span class="sxs-lookup"><span data-stu-id="11e74-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="11e74-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="11e74-130">See also</span></span>

[<span data-ttu-id="11e74-131">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="11e74-131">Document understanding overview</span></span>](../document-understanding-overview.md)

