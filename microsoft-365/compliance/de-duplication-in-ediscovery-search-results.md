---
title: 電子文件探索搜尋結果中的重複資料刪除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: 您可以選擇取消重複，以便只有一個電子郵件訊息的複本匯出即使多個執行個體的相同的訊息可能會有不同的信箱中找到匯出 eDiscovery 搜尋結果。
ms.openlocfilehash: f3a0291c2c611814e35528e87f5a3897c4e8ba59
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076265"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>電子文件探索搜尋結果中的重複資料刪除

本文說明如何運作的 eDiscovery 搜尋結果的重複資料刪除，並說明的重複資料刪除演算法的限制。
  
當使用 Office 365 電子文件探索工具來匯出 eDiscovery 搜尋的結果，您必須取消重複的結果，都要匯出的選項。 案例 當您啟用重複資料刪除 （根據預設，重複資料刪除未啟用），即使多個相同的郵件執行個體可能已找到所搜尋之信箱中匯出只有一個電子郵件訊息的複本。 重複資料刪除幫助您節省時間以減少您必須檢閱和分析搜尋結果會匯出之後的項目數。 但是請務必了解重複資料刪除的運作方式，並請注意，有可能會導致一個唯一的項目在匯出程序會標示為 「 重複的演算法的限制。
  
## <a name="how-duplicate-messages-are-identified"></a>如何重複的郵件會被識別

Office 365 電子文件探索工具來判斷郵件是否有重複使用下列電子郵件屬性的組合：
  
- **InternetMessageId**這個屬性會指定電子郵件訊息，也就是指的是特定郵件的特定版本的全域唯一識別碼的網際網路郵件識別碼。 寄件者的電子郵件用戶端程式或主機會將郵件傳送的電子郵件系統，即可產生此識別碼。 如果某人傳送郵件給一個以上的收件者，網際網路訊息 ID 會相同郵件的每個執行個體。 原始郵件的後續修訂會收到不同的郵件識別碼。 

- **ConversationTopic**這個屬性會指定的郵件之交談記錄的主旨。 **ConversationTopic**屬性的值是字串，描述交談的整體主題。 保育所組成的初始訊息及回覆傳送給初始郵件的所有郵件。 相同對話中的郵件具有**ConversationTopic**屬性相同的值。 此屬性的值通常是產生交談的初始訊息的主旨行。 

- **BodyTagInfo** -這是內部的 Exchange 儲存區屬性。 此屬性的值被計算藉由檢查郵件內文中的各種屬性。 此屬性用來識別郵件內文中的差異。 

EDiscovery 匯出程序，這三個屬性會比較每個符合搜尋準則的郵件。 如果這些屬性都是相同的兩個 （或多個） 的郵件，這些郵件經判定為重複項目，其結果是如果啟用重複資料刪除，則將匯出的只有一個郵件副本。 匯出的郵件稱為 [來源的項目]。 會包含在匯出的搜尋結果**Results.csv**和**Manifest.xml**報告包含重複郵件的相關資訊。 在**Results.csv**檔案中，是由有**重複項目**] 欄中的值，識別重複的郵件。 此欄中的值會比對郵件所匯出的**項目識別碼**] 欄中的值。 
  
下列圖形顯示如何重複的郵件會顯示在搜尋結果匯出**Results.csv**和**Manifest.xml**報告中。 這些報告未包含電子郵件內容先前所述，使用中的重複資料刪除演算法。 相反地，報告包含指派給項目依據] 的 Exchange 儲存區的**項目識別碼**屬性。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv 報表 （在 Excel 中檢視）
  
![檢視 Results.csv 報表中的重複項目的相關資訊](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml 報表 （在 Excel 中檢視）
  
![Manifest.xml 報告中檢視重複的項目相關資訊](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
此外，其他屬性，從重複的郵件會包含在匯出報告。 這包括重複的郵件位於，該郵件已傳送至通訊群組，以及是否無法傳遞郵件。 會 [副本] 或 [密件副本位置的分散式另一位使用者的信箱。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>重複資料刪除演算法的限制

有可能會導致唯一項目取得標示重複的項目重複資料刪除演算法一些已知的限制。 請務必了解這些限制，以便您可以決定要使用的選用重複資料刪除功能。
  
還有一種情況，其中的重複資料刪除功能可能誤識別為重複的郵件，並不將它匯出 （但仍引用為匯出報告中重複）。 以下是使用者編輯但不會傳送郵件。 例如，假設使用者在 Outlook 中選取一則訊息、 複製郵件的內容並再將它貼在新郵件。 然後使用者藉由移除或新增附件，或變更的主旨或本文本身有變更下列其中一個副本。 如果這兩個訊息符合查詢的 eDiscovery 搜尋，如果匯出搜尋結果時，會啟用重複資料刪除，將會匯出只有一個訊息。 因此即使原始郵件或複製的郵件已變更，都不修訂郵件已傳送， **InternetMessageId**、 **ConversationTopic**和**BodyTagInfo**屬性的值未更新，因此。 但如先前所述，這兩種郵件將會列在匯出報告 
  
也可以將唯一的郵件標示為重複項目，「 寫入時複製頁面保護 」 功能啟用時，如同正在訴訟暫止或就地保留信箱的大小寫。 「 寫入時複製 」 功能會複製原始郵件 （並將它儲存在使用者的 [可復原的項目] 資料夾的 [版本] 資料夾中） 儲存至原始項目修訂之前。 在此情況下，修訂的副本和 （在 [可復原的項目] 資料夾中） 原始郵件可能會被視為重複的郵件，因此只有一個會匯出。
  
> [!IMPORTANT]
> 重複資料刪除演算法的限制可能會影響您的搜尋結果的品質，如果您不應該啟用重複資料刪除當您匯出的項目。 如果在這一節所述的情況是不太可能是在您的搜尋結果中的因素，而且您想要減少很可能是重複的項目數目，您應該考慮啟用重複資料刪除。 
  
## <a name="more-information"></a>詳細資訊

- 匯出使用下列的 eDiscovery 工具之一的搜尋結果時，適用這篇文章中的資訊：

  - 在 Office 365 規範中心] 中的內容搜尋

  - Exchange Online 中的就地 eDiscovery

  - SharePoint Online 中的 eDiscovery 中心

- 如需有關匯出搜尋結果的詳細資訊，請參閱：

  - [匯出內容搜尋](export-search-results.md)

  - [匯出內容搜尋報告](export-a-content-search-report.md)

  - [匯出就地 eDiscovery 搜尋結果至 PST 檔案](https://go.microsoft.com/fwlink/p/?linkid=832671)

  - [在 eDiscovery 中心匯出內容及建立報告](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
