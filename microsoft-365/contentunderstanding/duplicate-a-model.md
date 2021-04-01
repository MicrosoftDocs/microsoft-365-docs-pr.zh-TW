---
title: 在 Microsoft SharePoint Syntex 中複製模型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解在 Microsoft SharePoint Syntex 中複製模型的方式及原因。
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445978"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中複製模型

如果您需要建立新模型，且知道現有的模型與您需要的模型非常類似，則複製文件瞭解模型可以節省您的時間和精力。

例如，名為「合約」的現有模型會分類您需要處理的相同檔案。 您的新模型會擷取一些現有的資料，但需要更新以擷取一些額外的資料。 無須從頭開始建立和訓練新模型，您可以使用重複的模型功能來建立合約模型的複本，這也會複製所有相關聯的訓練項目，例如範例檔案和實體擷取程式。

當您複製模型時，重新命名模型 (例如，重新命名為「合約續約」) 之後，就可以進行更新。 例如，您可以選擇移除一些不需要的現有已擷取欄位，然後訓練模型以擷取新的欄位 (例如「續約日期」)。

## <a name="duplicate-a-model"></a>複製模型

請遵循下列步驟來複製文件瞭解模型。

1. 從內容中心選取 **[模型]** 查看您的模型清單。

2. 在 **[模型]** 頁面上，選取您想要複製的模型。

3. 使用功能區或 **[顯示動作]** 按鈕 (在模型名稱旁邊)，選取 **[複製]**。</br>

    ![模型頁面的螢幕擷取畫面，其顯示選取的模型，且醒目提示 [複製] 選項。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. 在 **[複製模型]** 面板：

   a. 在 **[名稱]** 下，輸入要複製之模型的新名稱。</br>

    ![顯示複製模型面板的螢幕擷取畫面。](../media/content-understanding/duplicate-model-panel.png) </br>

   b. 在 **[描述]** 下，新增新模型的描述。

   c. (選用) 在 **[進階設定]** 下，選取您是否要相關聯現有的[內容類型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。

5. 選取 **[複製]**。

## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[重新命名模型](rename-a-model.md)

[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)

[說明類型](explanation-types-overview.md)

[套用模型](apply-a-model.md) 

[SharePoint Syntex 協助工具模式](accessibility-mode.md)