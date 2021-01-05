---
title: 在高級 eDiscovery 中收集案例的資料
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
description: 瞭解如何使用 Advanced eDiscovery 中的搜尋工具，識別要在調查中查看的檔組。
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751263"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>在高級 eDiscovery 中收集案例的資料

在您識別出您的案例感興趣的保管人和資料來源之後，即可識別出要深入瞭解的檔集合。 您可以使用 [Advanced eDiscovery] 中的搜尋工具，從 Microsoft 365 中的 custodial 和非 custodial 位置識別相關的檔。

在您執行搜尋之後，您可以在檢索的專案上查看統計資料，例如，專案數符合搜尋查詢的位置。 您也可以預覽結果的子集。 當您識別想要進一步檢查的檔集合時，您可以將搜尋結果新增至審閱集，以進行收集和處理。

## <a name="create-a-search"></a>建立搜尋

在 [**搜尋**] 索引標籤上選取 [**新增搜尋**]，將會啟動一個指導您建立搜尋的嚮導。 如需如何建立搜尋的詳細資訊，請參閱 [建立搜尋以收集資料](create-search-to-collect-data.md)。

在建立搜尋之後，會顯示一個包含詳細資料的浮出頁面頁面。 因為尚未完成搜尋，所以 **統計** 及 **預覽** 按鈕最初無法使用。 您可以在 [ **搜尋** ] 索引標籤上追蹤搜尋進度。

## <a name="view-search-results-and-statistics"></a>查看搜尋結果和統計資料

內容搜尋有兩個元件：統計資料 (估計) 和預覽。 每個元件都完成之後，您會看到 [**搜尋**] 索引標籤的 [搜尋] 索引標籤上的對應欄的狀態會 **顯示為 [** **已完成**]。

完成搜尋預估後，請選取搜尋以顯示飛出頁面，此頁面會顯示搜尋結果的一些高層次統計資料。 此時，[ **統計資料]** 按鈕將會作用中。 您可以選取它，以查看搜尋統計資料，例如：

- 摘要
- 主要位置
- 查詢

如需搜尋統計資料的詳細資訊，請參閱 [搜尋統計資料](search-statistics-in-advanced-ediscovery.md)。

完成預覽後， **預覽** 按鈕將會作用中。 選取它，以預覽結果的抽樣子集。

## <a name="add-search-results-to-a-review-set"></a>將搜尋結果新增至檢閱集

當您準備好收集並處理整個搜尋結果時，您可以將其新增至審閱集來執行。 如需詳細資訊，請參閱 [將資料新增至審閱集](add-data-to-review-set.md)。

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>將非 Microsoft 365 資料新增至審閱集

在案例的集合過程中，您也可以將非 Office 365 資料新增至審閱集，並與您使用「搜尋」工具收集的 Office 365 資料一起進行審閱及分析。 當您新增非 Office 365 時，您必須將它與案例中的特定系統管理員相關聯。 如需詳細資訊，請參閱 [Load 非 Microsoft 365 data into a a 審校 set](load-non-Office-365-data-into-a-review-set.md)。
