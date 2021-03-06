---
title: 電子文件探索搜尋結果中的重複資料刪除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何消除重複的 eDiscovery 搜尋結果，只會匯出電子郵件的一個副本。
ms.openlocfilehash: 859c1c41a9f6a530cdefce5220039fbc6ba1a14e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925669"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>電子文件探索搜尋結果中的重複資料刪除

本文說明 eDiscovery 搜尋結果的重復資料消除功能的運作方式，並說明重復資料消除演算法的限制。
  
使用 eDiscovery 工具匯出 eDiscovery 搜尋的結果時，您可以選擇取消重複複製所匯出的結果。 這代表什麼意思？ 當您啟用 (重復資料刪除時，預設不會啟用重復資料刪除。) 時，只會匯出電子郵件的一個副本，即使已在搜尋的信箱中找到多個相同郵件的實例也是一樣。 重復資料刪除可協助您減少在匯出搜尋結果之後必須複查和分析的專案數，以節省時間。 不過，請務必瞭解重復資料消除的運作方式，並注意，在匯出程式中，可能會導致唯一專案標記為重複的演算法限制。
  
## <a name="how-duplicate-messages-are-identified"></a>如何識別重複的郵件

eDiscovery 工具使用下列電子郵件屬性的組合，判斷郵件是否重複：
  
- **InternetMessageId** -此屬性指定電子郵件的網際網路郵件識別碼，它是參照特定郵件特定版本的全域唯一識別碼。 此 ID 是由寄件者的電子郵件客戶程式或主機電子郵件系統產生，用來傳送郵件。 若某人傳送郵件給一個以上的收件者，則每個郵件實例的網際網路郵件識別碼都是相同的。 對原始郵件進行的後續修訂將會收到不同的郵件識別碼。 

- **ConversationTopic** -此屬性指定郵件之交談線索的主旨。 **ConversationTopic** 屬性的值是描述交談整體主題的字串。 保留包含一封初始郵件和所有傳送給初始郵件的回復郵件。 相同交談中的郵件具有相同的 **ConversationTopic** 屬性值。 此屬性的值通常是原始郵件中產生交談的主旨行。 

- **BodyTagInfo** -這是內部 Exchange 儲存區屬性。 此屬性的值是透過檢查郵件本文中的各種屬性來計算。 此屬性可用來識別郵件本文中的差異。 

在 eDiscovery 匯出過程中，會針對符合搜尋準則的每封郵件，比較這三個屬性。 如果兩個 (或多個) 郵件的這些屬性都相同，則會決定這些郵件是重複的，而結果是在啟用重復資料刪除時，只會匯出一份郵件。 匯出的郵件稱為「來源專案」。 有關重複郵件的資訊會包含在 **Results.csv** ，並 **Manifest.xml** 包含在匯出的搜尋結果中的報告。 在 **Results.csv** 檔案中，會以 [ **副本至專案** ] 欄中的值來識別重複的郵件。 此欄中的值會與匯出之郵件的 [ **專案識別** ] 欄中的值相符。 
  
下列圖形顯示重複的郵件在 **Results.csv** 中的顯示方式，以及與搜尋結果一起匯出的 **Manifest.xml** 報告。 這些報告不包括先前所述的電子郵件內容，這些內容是用於重復資料消除演算法。 相反地，報表會包含指派給專案的 **專案身分識別** 屬性 Exchange 儲存區。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a> (以 Excel) 查看的 Results.csv 報表
  
![在 Results.csv 報告中查看重複專案的相關資訊](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a> (以 Excel) 查看的 Manifest.xml 報表
  
![在 Manifest.xml 報告中查看重複專案的相關資訊](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
此外，其他來自重複郵件的屬性會包含在匯出報告中。 這包括重複郵件所在的信箱、郵件是否已傳送至通訊群組，以及郵件是否為「抄送」或「密送給其他使用者」。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>重復資料消除演算法的限制

有一些已知的重復資料消除演算法限制，可能會造成唯一專案標示為重複專案。 請務必瞭解這些限制，以便決定是否使用選用的重復資料消除功能。
  
有一種情況是重復資料刪除功能可能誤將郵件視為重複，但不會將其匯出 (，但仍將其引向「匯出報告) 中的重複專案。 這些是使用者編輯但無法傳送的訊息。 例如，假設使用者選取 Outlook 中的郵件、複製郵件的內容，然後將它貼到新的郵件中。 然後，使用者移除或新增附件，或是變更主旨行或本文本身，就會變更其中一個副本。 如果這兩封郵件符合 eDiscovery 搜尋的查詢，則會在匯出搜尋結果時啟用重復資料刪除時，只會匯出一封郵件。 因此，即使已變更原始郵件或複製的郵件，也不會傳送任何修訂的郵件，因此 **InternetMessageId** 的值、 **ConversationTopic** 和 **BodyTagInfo** 屬性不會更新。 不過，如先前所述，這兩封郵件都會列在匯出報告中。 
  
啟用「寫入時複製」頁面保護功能時，也可以將唯一的郵件標示為重複專案，就像在進行訴訟暫止或 In-Place 保留信箱的情況下。 [寫入時複製] 功能會複製原始郵件 (，並將其儲存在使用者的 [可復原的專案] 資料夾的 [版本] 資料夾中) 之前，會儲存修訂之前的專案。 在此情況下，在 [可復原的專案]) 資料夾中 (修改後的副本和原始郵件會被視為重複郵件，因此只有其中一個會被匯出。
  
> [!IMPORTANT]
> 如果重復資料刪除演算法的限制可能會影響搜尋結果的品質，則當您匯出專案時，不應啟用重復資料刪除。 若本節所述的情況不可能是搜尋結果中的因素，而且想要減少最可能重複的專案數，您應該考慮啟用重復資料刪除。 
  
## <a name="more-information"></a>其他資訊

- 當您使用下列其中一個 eDiscovery 工具匯出搜尋結果時，本文中的資訊適用：

  - Office 365 中的規範中心內的內容搜尋

  - Exchange Online 中的就地 eDiscovery

  - SharePoint Online 中的 eDiscovery 中心

- 如需匯出搜尋結果的詳細資訊，請參閱：

  - [匯出內容搜尋](export-search-results.md)

  - [匯出內容搜尋報告](export-a-content-search-report.md)

  - [將電子檔探索搜尋結果匯出至 PST 檔案 In-Place](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [在 eDiscovery 中心匯出內容及建立報告](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)