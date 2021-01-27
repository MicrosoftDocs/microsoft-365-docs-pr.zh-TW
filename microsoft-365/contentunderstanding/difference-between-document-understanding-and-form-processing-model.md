---
title: 文件瞭解和表單處理模型之間的差異
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 描述文件瞭解和表單處理模型之間的差異
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975874"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>文件瞭解和表單處理模型之間的差異 


Microsoft SharePoint Syntex 中的內容瞭解可讓您識別並分類上傳至 SharePoint 文件庫的文件，以及擷取每個檔案的相關資訊。  例如，當文件上傳到 SharePoint 文件庫時，所有識別為 *[採購單]* 的檔案都將被分類，然後顯示在自訂文件庫檢視中。 此外，還可以從每個檔案中提取特定資訊（例如，*PO 號* 和 *總額*），並將其作為欄顯示在文件庫檢視中。 

內容瞭解讓您建立 *模型* 來識別和擷取所需的資訊。 模型在協助解決搜尋、業務流程、合規性和許多其他方面的業務問題方面具有價值。

您可以使用兩種模型類型：

- [文件瞭解模型](document-understanding-overview.md)
- [表單處理模型](form-processing-overview.md)

雖然這兩種模型通常用於相同用途，但以下列出的關鍵差異會影響您可以使用哪種模型。

> [!NOTE]
> 如需有關表單處理和文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>結構化、非結構化和半結構化內容

使用文件瞭解模型從非結構化文件（如信件或合約）中識別和擷取資料，這些文件中要擷取的文字實體位於句子或文件的特定區域中。 例如，非結構化文件可以是可以用不同方式撰寫的合同續約函。 不過，資訊會持續存在於每個合同續約文件的本文中，例如文字字串 *服務開始日期* 後接著實際日期。

使用表單處理模型來識別檔案並從結構化或半結構化文件（如表單或發票）中擷取資料。 表單處理模型經過訓練，能够從範例文件中瞭解表單的版面配置，並學會查找需要從類似位置擷取的資料。 表單通常具有更具結構化的版面配置，其中實體皆位於同一個位置 (例如，在稅務表單中的社會保險號碼)。

> [!NOTE]
> 您必須具有内容中心網站的存取權限才能建立文件瞭解模型或將其套用至 SharePoint 文件庫。 


## <a name="where-models-are-created"></a>建立模型的位置

文件瞭解模型在 SharePoint 內容中心網站中建立和管理。 

> [!NOTE]
> 如需有關輸入檔的詳細資訊，請參閱[表單處理模型需求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。 

表單處理模型是在 PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)中建立，但建立是直接從 SharePoint 文件庫啟動。 文件庫必須先啟用表單處理模型建立，使用者才能建立表單處理模型。 系統管理員可以在內容瞭解系統管理員設定中啟用表單處理模型建立。 表單處理模型使用 PowerAutomate 流程以在文件上傳到文件庫時處理這些檔案。

當您建立文件瞭解模型時，將建立儲存在 SharePoint 內容類型庫中的 [新 SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)。 或者，您可以視需要使用現有內容類型來定義模型。

表單處理模型也會建立 [新 SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，而且也會儲存在 SharePoint 內容類型庫中。

## <a name="where-they-can-be-applied"></a>可以套用的位置

您可以將文件瞭解模型套用至您有權存取的 SharePoint 文件庫。 使用內容中心建立文件瞭解模型，並將它套用至不同的文件庫。 内容中心使您能够更集中地控制文件瞭解模型的使用方式和套用位置。 注意：此資訊還必須匯總到内容中心。

表單處理模型目前只能套用到您建立它們時使用的 SharePoint 文件庫。 這可讓擁有網站存取權的授權使用者建立表單處理模型。 請注意，您的系統管理員必須在 SharePoint 文件庫啟用表單處理，以供授權使用者使用之。

 ## <a name="see-also"></a>另請參閱
[訓練：使用 AI Builder 改善商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[文件瞭解概觀](document-understanding-overview.md)

[表單處理概觀](form-processing-overview.md)

[SharePoint Syntex 簡介](index.md)
