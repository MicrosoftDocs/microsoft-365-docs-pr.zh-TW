---
title: 在 Advanced eDiscovery 中查看交談
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
ms.assetid: ''
description: 深入瞭解 Advanced eDiscovery (中的交談重新構建功能) ，以在 Microsoft Teams 及 Yammer 群組中重新構建、審閱及匯出聊天交談。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227184"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Advanced eDiscovery 中的交談執行緒

立即訊息是一種簡單的方法，可讓您在大型物件中提問、分享想法或快速交流。 在立即訊息平臺（如 Microsoft Teams 和 Yammer 群組），變成企業共同作業的核心，組織必須評估其 eDiscovery 工作流程如何處理這些新的通訊和共同作業形式。

Advanced eDiscovery 中的交談重建功能是專門用來協助您識別內容內容，並產生獨特的交談視圖。 這項功能可讓您有效且快速地查看完整的立即訊息交談 (也稱為像是在平臺等平臺中所產生的 *執行緒交談*) Microsoft Teams。

透過交談重建，您可以使用內建的功能來重新建立、審閱及匯出執行緒交談。 使用 Advanced eDiscovery 交談重建來：

- 在交談內保留所有郵件的唯一郵件層級中繼資料。

- 收集搜尋結果周圍的上下文相關訊息。

- 審閱、批註和密文討論執行緒的交談。

- 匯出個別的郵件或串接的交談

## <a name="terminology"></a>術語

以下是很少的定義，可協助您開始使用交談重建。

- **訊息：** 代表交談的最小單位。 郵件大小、結構及中繼資料可能會有所不同。

- **交談：** 代表一或多個郵件的群組。 在不同的應用程式中，交談可能以不同的方式呈現。 在某些應用程式中，會有明確的動作，可回復現有的郵件。 交談是以此使用者動作的結果來明確地組成。 例如，以下是 Microsoft Teams 中的通道交談的螢幕擷取畫面。

   ![Microsoft Teams通道交談](../media/threadedchat.png)

   在其他應用程式中 (例如 Teams) 中的1xN 聊天室訊息，沒有正式的回復鏈，而郵件會顯示為單一線程中的「平面河郵件」。 在這些類型的應用程式中，對話會從一段時間內發生的一組訊息中推斷出。 「軟群組」郵件的 (相對於回復鏈) 代表相關主題的「前後」交談。

## <a name="step-1-create-a-draft-collection"></a>步驟1：建立草稿集合

在您識別相關的保管人和內容位置之後，您可以建立搜尋來尋找潛在的相關內容。 在 Advanced eDiscovery 案例中的 [**集合**] 索引標籤上，您可以按一下 [**新增集合**] 並遵循該嚮導來建立集合。 如需如何建立集合、建立搜尋查詢及預覽搜尋結果的詳細資訊，請參閱 [建立草稿收集](create-draft-collection.md)。

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>步驟2：將草稿集合認可為審閱集

在集合中檢查並完成搜尋查詢之後，您可以將搜尋結果新增至審閱集。 當您將搜尋結果新增至審閱集時，原始資料會複製到 Azure 儲存體區域，以協助審閱及分析程式。 如需將搜尋結果新增至審閱集合的詳細資訊，請參閱 [認可 a 草稿集合至審閱集](commit-draft-collection.md)。

當您將專案從交談新增至審閱集時，您可以使用 [執行緒交談] 選項，從交談中收集包含符合集合之搜尋準則之專案的上下文中郵件。 選取 [執行緒交談] 選項後，可能會發生下列情況：

  ![交談檢索](../media/messagesandconversations.png)

1. 搜尋會使用關鍵字和日期範圍查詢，傳回 *郵件 3* 上的命中。 此郵件屬於較大的交談，如 *CRC1* 所示。

2. 當您將資料新增至複查集並啟用交談檢索選項時，Advanced eDiscovery 會傳回並收集 *CRC1* 中的其他專案。

3. 將專案新增至審閱集合之後，您可以從 *CRC1* 審閱所有的個別郵件。

若要啟用 [執行緒交談] 選項，請參閱 [認可 a 草稿集合至審閱集](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。

## <a name="step-3-review-and-export-threaded-conversations"></a>步驟3：審閱及匯出對話交談

在處理內容並將其新增至審閱集合之後，您可以開始查看審閱集中的資料。 檢查功能會因內容是否已新增至標準審閱集或交談複查集而有所不同。

### <a name="reviewing-conversations-in-a-standard-review-set"></a>在標準複查集中檢查交談

在標準的審閱集中，郵件會以個別專案的方式處理及顯示，類似于如何儲存在信箱資料夾中。 在此工作流程中，會以個別的專案處理每封郵件。 因此，標準的審閱集中無法使用「串接摘要」和「匯出」選項。

  ![標準複查集](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>在交談評審集中檢查交談

在交談複查集中，個別郵件會串接在一起，並以交談方式呈現。 這可讓您複查及匯出內容交談。

  ![交談複查集](../media/ConversationRSOptions.PNG)

下列各節說明如何在交談複查集中複查和匯出對話。

#### <a name="reviewing-conversations"></a>審閱交談

在交談複查集中，您可以使用下列選項來協助審閱程式。

- **依交談群組：** 將相同交談中的郵件分組，以協助使用者簡化及加速其審閱程式。

- **摘要視圖：** 顯示「執行緒交談」。 在此視圖中，您可以看見整個交談，也可以存取每個個別郵件的中繼資料。

   - 查看個別郵件的中繼資料

   - 下載個別郵件

- **文字視圖：** 會提供整個交談的解壓縮文字。

- **批註視圖：** 可讓您標記交談的執行緒化視圖。 交談中的所有郵件都會共用相同的註釋檔。

- **標記：** 在審閱集中查看交談時，您可以按一下 [編碼] 面板中的 [ **標記] 面板** ，以查看及套用標記。

- **重新執行交談轉換：** 當郵件新增至交談複查集時，會自動執行轉換工作以建立執行緒摘要及批註視圖。 如果交談重建工作失敗，您可以按一下 [動作] 以執行 [複查] 集中的 [ **動作] > 建立交談 pdf** ，以重新執行此工作。

#### <a name="exporting-conversations"></a>匯出對話

在交談複查集中，您可以設定下列選項來匯出對話：

![匯出對話的選項](../media/export.png)

1. 中繼資料選項：
   - **載入檔案：** 每個個別的郵件、電子郵件及檔都包含中繼資料。 交談中的每一封郵件都有一個資料列。
   - **標記：** 您的審閱程式中的標記會包含在中繼資料檔案中。 交談中的郵件共用相同的標記。

2. 交談選項：
   - **交談檔案：** 當您匯出對話檔時，批註的視圖會轉換為 PDF 檔案，並下載至匯出資料夾。 一個交談檔案中的郵件指向相同交談檔案的 PDF 版本。
   - **個別聊天訊息：** 當您匯出個別郵件時，交談中的每個唯一郵件都會匯出為獨立的專案。 檔會以儲存為信箱的相同格式匯出。 針對特定交談，您會收到多個 .msg 檔案。

     > [!NOTE]
     > 如果您已將批註套用至交談檔案，這些批註將不會轉移到個別的郵件。

3. 其他選項：
   - **為所有匯出的內容產生文字檔：** 為從審閱集匯出的每個交談產生一個文字檔。
   - **以 Redacted Pdf 取代匯出的內容：** 如果在複查程式期間產生 redacted 交談檔案，則匯出期間可使用這些檔案。 您可以決定是否只匯出原生檔案 (但不要選取此選項) 或是使用原生檔案的 redacted 版本取代原生檔案 (方法是選取此選項) （匯出為 PDF 檔案）。

## <a name="more-information"></a>其他相關資訊

若要深入瞭解如何在 Advanced eDiscovery 中查看案例資料，請參閱下列文章：

- [查看案例資料](view-documents-in-review-set.md)
- [分析案例資料](analyzing-data-in-review-set.md)
- [匯出案例資料](exporting-data-ediscover20.md)
