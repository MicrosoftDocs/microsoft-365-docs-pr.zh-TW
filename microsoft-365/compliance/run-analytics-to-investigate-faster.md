---
title: 執行分析以更快速地調查
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
description: 瞭解如何流量分析工具（如近期重複偵測）、電子郵件執行緒及主題，以加速調查。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7c5103adabadf88028351f0314bcdfaa2cd4d0f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035845"
---
# <a name="run-analytics-to-investigate-faster"></a>執行分析以更快速地調查

當證據集合很大時，可能很難全部檢查。 一組證據通常包含相同或類似的電子郵件訊息或檔的多個複本。 資料調查（預覽）提供了許多分析工具，可協助您減少需要檢查的檔量，而不會遺失任何資訊。 若要深入瞭解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

若要分析證據集中的資料：

1. 設定調查的分析設定。 如需詳細資訊，請參閱[設定搜尋及分析設定](configure-search-analytics-settings.md)。

2. 開啟證據集。

3. 按一下 [**管理證據**]。

4. 在 [**分析**] 底下，按一下 [**分析**]。

您可以在調查中檢查 [**工作**] 索引標籤上的分析進度。 觸發的工作類型稱為「執行**分析**」。

 分析完成之後，您可以在右邊的窗格中看到您正在審閱之檔的確切重複或臨近狀態的清單。 若要選取您要查看之檔的所有副本，您可以使用此面板輕鬆執行此動作。 若要深入瞭解此面板上的其他功能，請參閱[查看證據中的資料](review-data-in-evidence.md)。 

您也可以流量分析的輸出（如主題），在證據內執行其他查詢。 如需詳細資訊，請參閱[在證據中查詢資料](evidence-query.md)。

## <a name="analytics-report"></a>分析報告

若要查看您的證據的分析報告：

1. 開啟證據集。

2. 按一下 [**管理證據**]。

3. 在 [**分析**] 底下，按一下 [**查看報告**]。

報表的分析有四個元件：

- **細目**-在證據集內找到的原始電子郵件、附件及檔數目。

- **電子郵件**-inclusives、包含的 minuses、包含的副本或無上述的 eamil 郵件數目。
   - Inclusives：電子郵件執行緒中的最後一封郵件，其中包含所有先前的記錄，需要複查。
   - 包含 minuses：包含一或多個需要審閱之不同附件的執行緒中的郵件。
   - 包含副本：是另一個包含或非獨佔減號郵件（主旨和主體）複本的郵件。

- **附件**-在相同的證據中，不同電子郵件附件的唯一或重複的電子郵件附件數目。

- **檔（不包括電子郵件附件）** -需要複查的特殊檔數量，例如，接近重複集的最具代表性檔或另一個檔的完全相同的檔）。
