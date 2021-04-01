---
title: 在 Microsoft SharePoint Syntex 中重新命名擷取器
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
description: 了解在 Microsoft SharePoint Syntex 中重新命名擷取器的方式及原因。
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445957"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中重新命名擷取器

有時，如果您想要以不同的名稱來指稱擷取的資料欄位，您可能需要重新命名擷取器。 例如，貴組織決定變更其合約文件，並在文件中將「顧客」指稱為「客戶」。 如果您在模型中擷取「顧客」欄位，您可以選擇將其重新命名為「客戶」。

當您將更新的模型同步處理至 SharePoint 文件庫時，您的文件庫檢視中將會顯示新的「客戶」欄。 您的檢視會保留過去活動的「顧客」欄，但會為模型所處理的所有新文件更新「客戶」欄。 

> [!IMPORTANT]
>  請務必將更新的模型同步處理至您先前已加以套用的文件庫，以顯示新欄名稱。 

## <a name="rename-an-extractor"></a>重新命名擷取器

請遵循下列步驟重新命名實體擷取器。

1. 從內容中心選取 **[模型]** 查看您的模型清單。

2. 在 **[模型]** 頁面的 **[名稱]** 欄中，選取要重新命名其擷取器的模型。

3. 在 **[實體]** 下，選取要重新命名的擷取器名稱，然後選取 **[重新命名]**。</br>

    ![實體擷取器區段的螢幕擷取畫面，顯示已選取的擷取器 ，且醒目提示 [重新命名] 選項。](../media/content-understanding/entity-extractor-rename.png) </br>

4. 在 **[重新命名實體擷取器]** 面板：

   a. 在 **[新名稱]** 下，輸入擷取器的新名稱。</br>

    ![顯示實體擷取器面板的螢幕擷取畫面。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (選用) 在 **[設定]** 下，選取您是否要相關聯現有的網站欄。

5. 選取 **[重新命名]**。

## <a name="see-also"></a>另請參閱
[建立擷取器](create-an-extractor.md)

[建立分類器](create-a-classifier.md)

[重新命名模型](rename-a-model.md)

[說明類型](explanation-types-overview.md)

[在建立擷取器時運用字詞庫分類法](leverage-term-store-taxonomy.md)

[文件了解概觀](document-understanding-overview.md)

[套用模型](apply-a-model.md) 
