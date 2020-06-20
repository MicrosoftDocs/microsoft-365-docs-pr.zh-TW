---
title: 將資料從一個複查集新增至另一個複查集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何從一項審閱集選取檔，並在高級 eDiscovery 案例中個別使用另一組檔。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 433e59629ec40dbdf66b8daf6437ce84e41a3a33
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818600"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>從另一個複查集將資料新增至審閱集

在某些情況下，您可能需要從一部審閱集選取檔，並在另一個審校集內個別使用這些檔。 如果您已在評審集中 culled 內容，而且想要對資料子集執行分析，這一點特別有用。

請遵循本文中的工作流程，將其中一個複查集的內容新增至另一個。

## <a name="create-a-review-set"></a>建立審閱集

開始之前，您必須建立要將資料新增至其中的審閱集。  您可以在案例的 [**複查集**] 索引標籤上新增新的審閱集。 如需詳細資訊，請參閱[建立審閱集](managing-review-sets.md#create-a-review-set)。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>步驟1：識別要新增至其他審閱集的內容

您可以選取來源複查集內的特定檔，或選取 [複查] 集合查詢所傳回的所有專案，以將內容從一項審閱集新增至另一個。 若要新增選取的專案，請選取專案，然後選取 [**動作**]，然後選取 [**新增至其他審閱集**]。

![新增至另一個考核集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>步驟2：指定新增至其他審閱集的選項

在 [**新增至其他審閱集選項**] 飛入頁面中，選擇您想要新增專案的審閱集。 選擇是否要新增**所有搜尋結果**或**選取的專案**。  **其他資訊**提供的選項可包含專案中的所有中繼資料，以及是否要在將檔新增至新的審閱集時，從來源複查集包括標記（透過選取 [**標籤**] 核取方塊）。  

![新增至另一個考核集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

按一下 **[確定]** 後，就會建立新的工作（命名為**將資料新增至另一個複查集**），以將內容新增至另一個評審集。 您可以移至 [**工作**] 索引標籤，監視此工作的進度。 如需詳細資訊，請參閱[管理工作](managing-jobs-ediscovery20.md)。
