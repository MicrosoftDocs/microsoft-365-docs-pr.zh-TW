---
title: 預先探索中的搜尋統計資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 透過查看在高級 eDiscovery 中執行集合搜尋之後所產生的統計資料，以驗證搜尋結果。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750774"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>在高級 eDiscovery 中搜尋統計資料

驗證搜尋結果的一種方式是查看結果的統計資料，以確保其符合您的預期。 搜尋完成時，會在 [搜尋詳細資料] 浮出控制項上顯示高層級統計資料：

- 搜尋所檢索的專案數目及數量

- 在搜尋位置中找到的部分索引或未編制索引的專案數目及數量

- 已搜尋的信箱和位置數目。
若要查看詳細的統計資料，請按一下 [搜尋詳細資料] 飛入中的「統計資料」。

## <a name="summary-view"></a>摘要視圖

在摘要視圖中，您可以看到搜尋結果依位置類型所細分 (例如 Exchange) 。 您可以在每個位置類型上查看：

- 專案符合搜尋條件的位置數目

- 從這些位置符合搜尋條件的專案數

- 符合搜尋條件的專案總容量。

## <a name="top-locations-view"></a>頂端位置視圖

在 [頂端位置] 視圖中，您會看到具有最相符專案的個別位置。 針對每個位置，您會看到：

- 位置名稱 (例如 SharePoint URL) 

- 位置類型

- 符合搜尋條件的專案數

- 符合搜尋條件的專案總容量。

## <a name="queries-view"></a>查詢檢視

如果您已在查詢中使用 (c:s) 關鍵字或關鍵字列，則您可以在每個位置類型的查詢檢視中查看查詢明細。 針對每個位置類型，您會看到：

- 部分：此欄會包含 "Primary" 或 "關鍵字" 一字。 "Primary" 表示列在整個查詢中呈現統計資料，而 "關鍵字" 則表示其中一個查詢元件。

- 查詢：列所參照的實際查詢元件。 如果 Part 是 "Primary"，這會是整個查詢;如果 Part 是 "關鍵字"，您會在這裡看到其中一個查詢元件。
  
  - 當您搜尋所有的 contentin 信箱 (但未指定任何關鍵字) 時，實際的查詢 (大小 >= 0) ，這樣就會傳回所有專案。
  
  - 當您搜尋商務網站的線上 SharePoint 和 OneDrive 時，會新增下列兩個元件：
    
    - 不 IsExternalContent:1-排除內部部署 SharePoint 組織中的任何內容
    
    - 非 isOneNotePage： 1-排除所有的 OneNote 檔案，因為這些檔案會是符合搜尋查詢的任何檔的重複專案。

- 專案符合搜尋條件的位置數目。

- 從這些位置符合搜尋條件的專案數。

- 符合搜尋條件的專案總容量。
