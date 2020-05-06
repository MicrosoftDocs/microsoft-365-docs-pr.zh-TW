---
title: 高級 eDiscovery 的版本資訊
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
description: 本文包含用於高級 eDiscovery 的版本資訊，包括已知問題、已修復的問題和新功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45a4647856fef0186840ec5465bb9250e5d78de4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034617"
---
# <a name="release-notes-for-advanced-ediscovery"></a>高級 eDiscovery 的版本資訊

「高級 eDiscovery」的公開預覽程式是取得近期功能和更新之初期存取的方法。 若要取得最新功能的初期存取，只要在安全性 & 合規性中心建立並使用高級 eDiscovery 案例即可。 請參閱[建立新的案例](create-new-ediscovery-case.md)。

## <a name="known-issues"></a>已知問題

**Microsoft Forms**

- 在2019年1月31日之前所建立之表單的資料，在使用高級 eDiscovery 中的搜尋工具來搜尋保管人信箱時，將無法進行搜尋。 在此日期之後建立的表單可供搜尋。

- 使用者建立的表單仍可接收回應，即使在建立表單的使用者已遭刪除之後。 不過，當使用高級 eDiscovery 中的搜尋工具來搜尋保管人信箱時，這些回應的對應資料（在刪除保管人信箱之後所發生的資料）將無法搜尋。
 
**Microsoft Sway**

- 如果使用者在刪除使用者帳戶的使用者帳戶之前，在該 sway 的擁有者上進行編輯，則在使用高級 eDiscovery 的搜尋工具來搜尋保管人信箱時，這些變更可能不會是可搜尋的。 當您收到已刪除帳戶的信號時，sway 會立即封鎖對該 sway 所做的變更。 不過，在接收到此信號之前，您很可能會編輯 sway。

## <a name="issues-fixed-in-this-release"></a>在此版本中修復的問題

- DCR：未編制索引的專案和孤立專案的例外狀況處理
- DCR：保留通知
- DCR：電子檔探索中的保管人

## <a name="whats-new"></a>新功能

- **安全性 & 規範中心的重新設計導覽**--「高級 eDiscovery」具有全新的外觀與風格。 使用高級 eDiscovery 來管理更多案例工作流程。

- **案例管理**–還有其他對新案例類型的支援。 您也可以選取及儲存近期和最愛的案例。 使用新的儀表板，追蹤並監控各案例內的活動。

- **保管人管理**–在案例中，以資料管理員的身分新增和移除使用者。

- **Exchange、OneDrive 及小組整合**–自動將使用者的目前信箱、商務用 OneDrive，以及 Microsoft 小組網站新增至案例。 

- **管理員通訊**–代表您的組織傳送和管理法律封存通知。

- **管理員入口網站**–供保管人的新入口網站存取其使用中保留通知。

- **深入編制索引**–根據需要重新編目部分索引的專案。

- **錯誤修正**–修正或下載處理錯誤;這包括針對大型檔案類型、受密碼保護的檔案等等的修復支援。 

- **搜尋的增強功能**-透過識別保管人和/或位置來建立搜尋。

- **複查集**–管理、追蹤及審核一組靜態的檔。

- **複習**–使用原生、文字和近原生模式，查看新增至您的審閱集的檔。

- **標記密文、標記和批註**–在您審閱檔時標記密文、套用標記，並做為批註。
  
- **分析-已安裝的回顧**–利用高級 eDiscovery 分析，在審校集內尋找、搜尋及挑選結果。

- **工作**–追蹤長時間執行程式的狀態。

- **新的審計活動**–追蹤和查看高級 eDiscovery 的新的「審核」活動。
