---
title: 搜尋統計資料
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
description: 搜尋統計資料是驗證搜尋結果的有效方式，並顯示在 [搜尋詳細資料] 飛出頁面的 [狀態] 底下。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc6aea96e86388ae7ecfa0fa545bc5571eeff0cd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035835"
---
# <a name="search-statistics"></a>搜尋統計資料

調查資料事件時，驗證搜尋結果的有效方式，就是查看搜尋結果的統計資料，以確定其符合您的預期。 當搜尋執行完畢時，下列高層級的統計資料會顯示在 [搜尋詳細資料] 浮出頁面的 [**狀態**] 底下：

![搜尋詳細資料彈出頁面上的 statisics](../media/SearchDetailsFlyout.png)

- 符合搜尋準則之專案的預估數目和大小。

- 部分索引項目目（也稱為未編制索引的*專案*）的數目和大小，這些專案不可搜尋，但位於搜尋中所包含的內容位置中。

- 已搜尋的信箱和網站數目。

若要查看詳細的統計資料，請按一下 [搜尋詳細資料] 彈出頁面上的 [**統計資料]** 在 [**搜尋統計資料]** 頁面上，您可以查看搜尋摘要、包含符合搜尋結果之專案的頂端位置，以及搜尋查詢的詳細統計資料。

![搜尋統計資料下拉式清單](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>摘要

在**摘要**視圖中，您可以看到搜尋結果依位置類型所細分（例如，位置包含 Exchange 信箱和 SharePoint 網站）。 每個位置類型會顯示下列資訊：

- 專案符合搜尋準則的位置數目。

- 每個符合搜尋準則的位置類型中的專案總數。

- 符合搜尋準則之每個位置類型專案的總大小。

## <a name="top-locations"></a>主要位置

在 [**頂端位置**] 視圖中，您會看到專案中的個別內容位置，其專案與搜尋準則相符。 針對每個內容位置，會顯示下列資訊：

- 位置的名稱;信箱的電子郵件地址，以及 SharePoint 網站的 URL

- 位置類型

- 符合搜尋準則的專案數

- 符合搜尋準則之所有專案的總大小。

## <a name="queries"></a>查詢

在 [**查詢**] 視圖中，您可以查看每個搜尋查詢元件的詳細資料。 [！注意] 如果您在搜尋查詢中使用關鍵字清單，您可以在**查詢**視圖中查看增強的統計資料，以顯示符合每個關鍵字或關鍵字片語的專案數。 這可協助您快速識別查詢的哪些部分最為有效（也是最低）。 

下列資訊會顯示在 [**查詢**] 視圖中：

 - **位置類型**-列中所顯示之統計資料的內容位置類型。

- **Part** -此欄會顯示下列其中一個值： **Primary**或**關鍵字**。 **主要**表示列是針對整個查詢所呈現的統計資料;**關鍵字**表示列中的統計資料是針對其中一個查詢元件。

- **Condition** -列所參照之搜尋查詢的實際查詢元件。 如果**Part**欄中的值為**主要**值，則會顯示整個搜尋查詢的統計資料。如果值為**關鍵字**，則會顯示 [**查詢**] 欄中所顯示之查詢元件的統計資料。 例如，如果使用關鍵字清單，則會顯示其中一個關鍵字的統計資料。

  以下是有關 [**查詢**] 欄中所顯示之統計資料的一些其他事項：
  
  - 當您搜尋信箱中的所有內容（但未指定任何關鍵字）時，實際的查詢是 **（大小 >= 0）** ，因此會傳回所有專案。
  
  - 當您搜尋 SharePoint 和 OneDrive 網站時，會將下列兩個元件新增至搜尋查詢：
    
    **不 IsExternalContent:1** -這會排除內部部署 SharePoint 組織中的任何內容
    
    **非 isOneNotePage： 1-不**包括所有的 OneNote 檔案，因為這會是符合搜尋查詢之任何檔的重複專案。

- **搜尋中的位置**具有符合搜尋查詢的專案的內容位置，顯示在列中的 part/condition。 請注意，如果封存信箱包含符合搜尋準則的專案，則會算作個別的位置。

- **Items** -符合顯示在列中之 part/condition 之搜尋準則的專案總數。

- **Size** -符合顯示在列中之 part/condition 之搜尋準則的專案總數。

