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
description: 瞭解如何從一項審閱集選取檔，並在 Advanced eDiscovery 案例中個別使用另一組檔案。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285177"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>從另一個檢閱集將資料新增至檢閱集

在某些情況下，您可能需要從一部審閱集選取檔，並在另一個審校集內個別使用這些檔。 當您已在檢閱集中剔除內容，並想要對資料的子集執行分析時，這特別有用。

請遵循本文中的工作流程，將其中一個複查集的內容新增至另一個。

## <a name="create-a-review-set"></a>建立審閱集

開始之前，您必須建立要將資料新增至其中的審閱集。  您可以在案例的 [ **複查集** ] 索引標籤上新增新的審閱集。 如需詳細資訊，請參閱 [建立審閱集](managing-review-sets.md#create-a-review-set)。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>步驟1：識別要新增至其他審閱集的內容

您可以選取來源檢閱集的特定文件，或選取由檢閱集查詢所傳回的所有項目，即可將內容從一個檢閱集新增到另一個檢閱集。 若要新增選取的專案，請選取專案，然後選取 [ **動作**]，然後選取 [ **新增至其他審閱集**]。

![在 [動作] 功能表中新增至其他審閱集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>步驟2：指定新增至其他審閱集的選項

在 [ **新增至其他審閱集選項** ] 飛入頁面中，選擇您想要新增專案的審閱集。 選擇是否要新增 **所有搜尋結果** 或 **選取的專案**。  **其他資訊** 提供的選項可包含專案中的所有中繼資料，以及是否要在將檔新增至新的審閱集時，透過選取 [ **標籤** ] 核取方塊) 從來源複查集中包含標記 (。  

![將資料新增至另一個評審集的選項](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

按一下 **[確定]** 之後，會建立新的工作 (，並將 **資料新增至另一個評審集**) ，以將內容新增至另一個評審集。 您可以移至 [ **工作** ] 索引標籤，監視此工作的進度。 如需詳細資訊，請參閱 [管理工作](managing-jobs-ediscovery20.md)。
