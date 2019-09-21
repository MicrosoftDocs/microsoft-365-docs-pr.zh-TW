---
title: 再試一次 「 內容搜尋 」 來解決錯誤的內容位置
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 用於解決有內容位置錯誤的內容搜尋中的 [重試] 按鈕。
ms.openlocfilehash: 91c656a05111391ad93e03946cf367133f2c25a2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078174"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>再試一次 「 內容搜尋 」 來解決錯誤的內容位置

當您在安全性與合規性中心中使用內容搜尋來搜尋大量的信箱時，您可能會收到類似下列的搜尋錯誤：

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

這些錯誤 （錯誤代碼的 CS001-002、 CS003-002、 CS008 009、 CS012-002 和其他錯誤的表單 CS0XX 0XX） 表示內容搜尋來搜尋特定的內容位置; 已經失敗在這個範例中，沒有搜尋兩個信箱。 內容搜尋的彈出式視窗狀態的詳細資訊] 頁面上會顯示這些錯誤。

## <a name="cause-of-content-location-errors"></a>內容位置錯誤的原因

當您搜尋大量的信箱，搜尋會分配到千分位 Microsoft 資料中心中的伺服器。 在任何時候，特定伺服器可能是在重新開機狀態或容錯移轉備援副本的過程中。 在這些情況下，以擷取資料的內容搜尋的要求會逾時。 在前一個範例中，錯誤為失敗的信箱已搜尋逾時的結果。

## <a name="resolving-content-location-errors"></a>解決內容位置錯誤

重新啟動搜尋會通常會導致在不同伺服器上類似的錯誤。 而不是重新啟動搜尋時，按一下 [搜尋結果頁面頂端會顯示 [**重試**] 按鈕。

![按一下 [重試] 按鈕，以解決內容位置錯誤](media/retrycontentsearch3.png)

這會導致重試一次僅針對失敗的信箱搜尋。 當您再試一次搜尋時，會保留已成功傳回的結果。

## <a name="tips-to-avoid-content-location-errors"></a>若要避免內容位置錯誤的祕訣

以下是一些加法原因的內容位置錯誤和的一些秘訣可協助您避免它們搜尋大量信箱時。

- 要搜尋的信箱可能會因為使用者活動忙碌中。 在此情況下，搜尋服務可能節流可防止信箱變成無法使用本身擷取。 若要避免此問題，請嘗試執行搜尋期間非上班時間。

- 搜尋查詢可能會從信箱正在擷取太多內容。 如果可能的話，請試著使用關鍵字、 日期範圍和搜尋條件縮小搜尋範圍。

- 太多的關鍵字或當您建立搜尋查詢中使用[關鍵字] 清單中](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)的關鍵字片語。 當您執行搜尋查詢使用關鍵字] 清單中時，基本上執行服務的每一列的個別搜尋關鍵字] 清單中，因此可以產生統計資料。 如果您在搜尋查詢中使用關鍵字] 清單中，最小化的關鍵字清單中的列數或分成較小的清單中的數字的關鍵字，建立不同的搜尋，為每個關鍵字清單。

  > [!NOTE]
  > 若要協助減少大型關鍵字清單所導致的問題，您現在有限的最大值為 20 列在 [關鍵字] 清單中的搜尋查詢。

- 正在同時執行太多的搜尋在同一個信箱。 如果可能，請嘗試在任何一個信箱上一次執行一個搜尋。

- 在單一搜尋中搜尋太多的信箱。 搜尋非常大量的信箱時，會增加的內容位置錯誤的機率。 如果可能，請嘗試執行多個搜尋，使每個搜尋組織中包含信箱的子集。

- 在信箱上正在執行必要的維護。 雖然此原因可能很少發生，有點等候時收到之後的內容位置錯誤，然後再重試搜尋。
