---
title: 重試內容搜尋以解決內容位置錯誤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在調查過程中，您可以使用 [重試] 按鈕來解析內容位置發生錯誤的內容搜尋。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311817"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>重試內容搜尋以解決內容位置錯誤

當您在安全性與合規性中心使用內容搜尋來搜尋大量信箱時，可能會收到與錯誤類似的搜尋錯誤：

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

這些錯誤 (的錯誤碼為 CS001-002、CS003-002、CS008-009、CS012-002，以及其他表單 CS0XX-0XX 的錯誤) 表示內容搜尋無法搜尋特定的內容位置;在此範例中，未搜尋兩個信箱。 這些錯誤會顯示在內容搜尋的 [狀態詳細資料浮出] 頁面上。

## <a name="cause-of-content-location-errors"></a>內容位置錯誤的原因

搜尋大量信箱時，搜尋會在 Microsoft 資料中心的數千部伺服器間散佈。 在任何時候，特定伺服器都可能是在重新開機狀態，或在容錯移轉至多餘副本的程式中。 在這兩種情況下，內容搜尋要求取得的資料將會超時。在上一個範例中，失敗的信箱錯誤是搜尋超時的結果。

## <a name="resolving-content-location-errors"></a>解決內容位置錯誤

重新開機搜尋通常會在不同的伺服器上導致類似的錯誤。 若不重新開機搜尋，請按一下顯示在搜尋結果頁面頂端的 [ **重試** ] 按鈕。

![按一下 [重試] 按鈕以解決內容位置錯誤](../media/retrycontentsearch3.png)

這會導致僅對失敗的信箱重試搜尋。 當您重試搜尋時，會保留已成功傳回的其他結果。

## <a name="tips-to-avoid-content-location-errors"></a>避免內容位置錯誤的提示

以下是內容位置錯誤的一些額外原因，以及協助您在搜尋大量信箱時避免出現問題的一些秘訣。

- 正在搜尋的信箱可能由於使用者活動而忙碌。 在此情況下，搜尋服務可能會節流自身，以防止信箱變得無法使用。 若要避免這種情況，請試著在非上班時間執行搜尋。

- 搜尋查詢可能會從信箱中檢索太多的內容。 如果可能的話，請嘗試使用關鍵字、日期範圍和搜尋條件來縮小搜尋範圍。

- 使用 [關鍵字清單](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)建立搜尋查詢時，關鍵字或關鍵字片語太多。 當您執行使用關鍵字清單的搜尋查詢時，此服務實質上會針對關鍵字清單中的每一列執行個別的搜尋，以產生統計資料。 如果您是在搜尋查詢中使用關鍵字清單，請將關鍵字清單中的列數減至最少，或是將數位關鍵字分割成較小的清單，並為每個關鍵字清單建立不同的搜尋。

  > [!NOTE]
  > 為了避免大型關鍵字清單所造成的問題，您目前限制在搜尋查詢的關鍵字清單中，最多可有20列。

- 在相同的信箱上同時執行太多搜尋。 如果可能的話，請嘗試一次在任何一個信箱上執行一個搜尋。

- 搜尋單一搜尋中的信箱太多。 搜尋大量信箱時，內容位置錯誤的發生幾率會增加。 如果可能的話，請嘗試執行多個搜尋，讓每個搜尋都包含您組織中的信箱子集。

- 在信箱上執行必要的維護。 雖然這種原因很少發生，請稍候片刻後再收到內容位置錯誤，然後再試一次搜尋。
