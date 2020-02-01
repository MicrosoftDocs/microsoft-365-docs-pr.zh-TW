---
title: 搜尋統計資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: ''
ms.openlocfilehash: df5ad2ce1d40421e43cdd5e8c3fd4dd5efe1c6f7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597540"
---
# <a name="search-statistics"></a>搜尋統計資料

您可以驗證您的搜尋結果的其中一個方法是查看周圍您若要確保其符合您預期的結果的統計資料。 搜尋完成時，搜尋的詳細資訊彈出式視窗會顯示高層級的統計資料：
- 數目與搜尋所擷取的項目數量
- 數目和磁碟區的已局部編製索引/未建立索引的搜尋位置中找到的項目
- 搜尋信箱和位置的數目。
若要檢視更詳細的統計資料，請按一下 [從搜尋的詳細資訊彈出式視窗上 「 統計資料 」。

## <a name="summary"></a>摘要

在 [摘要] 檢視中，您可以看到細分依位置類型 (如 Exchange) 的搜尋結果。 每個位置類型，您可以看到：
- 位置會有符合搜尋條件的項目數目
- 這些符合搜尋條件的位置中的項目數
- 總量符合搜尋條件的項目。

## <a name="top-locations"></a>上方的位置

在頂端的位置] 檢視中，您會看到最相符項目與個別的位置。 為每個位置中，您會看到：
- 位置名稱 (例如 SharePoint URL)
- 位置類型
- 符合搜尋條件的項目數目
- 總量符合搜尋條件的項目。

## <a name="queries"></a>查詢

如果您已在查詢中使用 (c:s) 關鍵字或關鍵字的資料列，您可以看到您的查詢，查詢每個位置類型的檢視中的明細。 每個位置類型，您會看到：

- 組件： 此欄會讓 word 「 主要 」 或 「 關鍵字 」。 「 主要 」 表示 [列呈現統計資料，在整個查詢，而 「 關鍵字 」 表示下列其中一個查詢元件。

- 查詢： 實際的查詢元件列參照。 如果部分是 「 主要 」，這將會在整個查詢;如果組件 」 關鍵字 」，您會看到下列其中一個查詢元件。
  
  - 當您搜尋所有 contentin 信箱 （藉由不指定任何關鍵字） 時，實際的查詢是 (大小 >= 0)，所以會傳回所有項目
  
  - 當您搜尋 SharePoint Online 和 OneDrive for Business 網站時，會新增兩個下列元件：
    
    - 不 isexternalcontent: 1-從內部部署 SharePoint 組織排除任何內容
    
    - 不 isOneNotePage: 1-排除所有 OneNote 檔案，因為這些是重複的任何符合搜尋查詢的文件。

- 位置會有符合搜尋條件的項目數目。

- 從下列位置，複製符合搜尋條件的項目數。

- 總量符合搜尋條件的項目。