---
title: 在高級 eDiscovery 中分析複查集中的資料
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
description: 深入瞭解分析高級 eDiscovery 案例時可用於組織檔組的工具。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033817"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在高級 eDiscovery 中分析複查集中的資料

當收集的檔數目很大時，可能很難全部查看。 「高級 eDiscovery」提供許多工具來分析檔，以減少檔數量，以減少不會遺失資訊的檔數量，以及協助您以一致的方式組織檔。 若要深入瞭解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

若要分析審閱集中的資料：

1. 設定案例的分析設定。 如需詳細資訊，請參閱[設定搜尋及分析設定](configure-search-analytics-settings.md)。

2. 開啟您要分析的複查集。

3. 按一下 [**管理審閱集**]。

4. **針對審閱集按一下 [執行分析**]。

您可以在案例的 [**作業**] 索引標籤上檢查分析進度。

 分析完成之後，您可以查看分析報告、在分析的輸出集內執行查詢（請參閱在[您的複查集中查詢](review-set-search.md)），以及查看指定檔的相關檔（請參閱複查[資料在評審集中](reviewing-data-in-review-set.md)）。

## <a name="analytics-report"></a>分析報告

若要查看複查集的分析報告：

1. 開啟審閱集。

2. 按一下 [**管理審閱集**]。

3. 按一下 [**查看報告**]。

報告中有七個元件可供分析：

- **目標人口：** 在審閱集中找到的電子郵件訊息、附件和鬆散檔的數目。

- **檔（不含附件）：** 旋轉的鬆散檔數目、重複接近的樞紐分析表或其他檔的完全相同的數目。

- **電子郵件：** Inclusives、包含的副本、包含的 minuses 或無上述的電子郵件數目。

- **附件：** 審閱集中其他電子郵件附件的唯一或重複的電子郵件附件數目。

- **依類型的檔數目：** 以 file extension 識別的檔案數目。

- **檔來源來源：** 內容摘要（依其原始的資料來源）。

- **依處理匯總的檔：** 依考核集流程的內容摘要。 
