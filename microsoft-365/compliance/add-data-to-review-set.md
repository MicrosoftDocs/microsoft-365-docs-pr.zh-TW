---
title: 將搜尋結果新增至檢閱集
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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將搜尋結果或其範例新增至「高級 eDiscovery 案例審核」集。
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919975"
---
# <a name="add-search-results-to-a-review-set"></a>將搜尋結果新增至檢閱集

當您符合搜尋的結果並準備好檢查和分析這些搜尋結果時，您可以在案例中將其新增至審閱集。 將原始資料複製到審閱集也可提供高級分析工具，例如主題偵測、接近重複偵測，以及電子郵件線索識別，以協助檢查和分析處理常式。 您也可以將非 Microsoft 365 資料來源中的資料新增至審閱集，讓您除了從 Microsoft 365 收集的資料之外，還可以查看資料。

當您將搜尋結果新增至審閱集時 (的複查集會列于 [ **複查集** ] 索引標籤) 上，會發生下列情況：

- 再次執行搜尋。 這表示複製到審閱集的實際搜尋結果可能會與上次執行搜尋時所傳回的估計結果不同。

- 搜尋結果中的所有專案都會從 live services 中的原始資料來源進行複製，並複製到 Microsoft 雲端中的安全 Azure 儲存位置。

- 所有專案 (（包括內容和中繼資料) ）都是重新編制索引，因此複查集中的所有資料在複查案例資料期間都會完全可供搜尋。 當您在案例調查期間搜尋考核集中的資料時，會產生完全和 fast 搜尋的資料。

- 在將電子郵件及附加的檔案新增至審閱集時，會解密在搜尋結果中傳回的電子郵件訊息 [，並將](encryption.md) 其附加至搜尋結果中傳回的電子郵件。 您可以在複查集中複查及查詢解密的檔。 您必須被指派 RMS 解密角色，才能將解密的電子郵件附件新增至審閱集。 如需詳細資訊，請參閱 [Microsoft 365 eDiscovery tools 中的解密](ediscovery-decryption.md)。

若要將資料新增至審閱集，請按一下 [ **搜尋** ] 索引標籤上的搜尋，然後按一下彈出頁面上的 [ **將結果新增至審閱集** ]。

您可以新增至現有的複查集，或建立新的審閱集。  若要新增至新的審閱集，請指定名稱，然後按一下 [ **新增** ] 以顯示飛出頁面。

![選取複查集和設定收集選項](../media/AeD_AddToReviewSet.png)

將資料新增至審閱集是一個長時間執行的程式。 此套裝程式含從原始資料來源收集 Microsoft 365 (中的專案，例如，從信箱和網站) ，將其複製到 Azure 存放位置 (此複製程式也稱為 *攝取* ) ，然後再重新索引項目目。 您可以在 [ **作業** ] 索引標籤或 [ **搜尋** ] 索引標籤上，透過監視 [ **新增資料至審閱集合** ] 欄中的狀態，追蹤進度。 完成審閱集處理之後，按一下案例中的 [ **檢查集合** ] 索引標籤，然後按一下 [複查集]，以開始篩選、檢查、標示及匯出審閱集中的資料。

## <a name="define-options-to-scope-your-collection-for-review"></a>定義選項來限定您的集合以供審閱

當您將搜尋內容新增至現有或新的審閱集時，您可以使用下列選項來收集要複查的內容：

- **包括版本 SharePoint (Beta)** ：您可以使用此選項，根據集合的版本限制和搜尋參數，來啟用 SharePoint 檔所有版本的集合。 選取此選項會大幅增加新增至審閱集之專案的大小。

- **交談檢索選項** ：新增至審閱集的專案會針對執行緒交談啟用，以協助檢查前後交談內容中的內容。 如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。

- **啟用新式附件的取回** 功能：使用此選項可包含集合中新式附件或連結的檔案，以便進一步複查。 如需與現代附件相關的可搜尋屬性的詳細資訊，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。

## <a name="add-a-sample-to-a-review-set"></a>將範例新增至審閱集

如果您想要在將所有搜尋的結果新增至審閱集之前，先驗證搜尋結果，您可以將搜尋結果的範例新增至審閱集，而不是新增任何專案。

若要將範例新增至審閱集，請按一下 [ **搜尋** ] 索引標籤上的搜尋，然後按一下彈出頁面上的 [ **範例** ]。 在 [ **抽樣參數** ] 頁面上，選擇下列其中一個選項：

- **信賴等級%** 和 **置信區間%** -新增至審閱集的專案將由您設定的統計參數所決定。 如果當採樣結果時，通常會使用信賴等級和間隔，請在下拉式方塊中指定這些結果。 否則，請使用預設設定。

- **隨機範例%** -新增至審閱集的專案是以隨機選取搜尋所傳回之總專案數目的指定百分比為基礎。

選取及設定上述其中一個選項之後，請選擇要新增範例的複查集，然後按一下 [ **傳送** ]。 您也可以在 [ **工作** ] 索引標籤或 [ **搜尋** ] 索引標籤上，監控 [ **已新增資料至審閱集合** ] 欄中的狀態，以追蹤進度。

## <a name="optical-character-recognition"></a>光學字元辨識

當您將搜尋結果新增至審閱集時，在 [Advanced eDiscovery] 中 (OCR) 功能會自動從影像提取文字，並包含包含已新增至審閱集之資料的影像文字。 您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。 這可讓您對影像中的文字進行進一步的複查和分析。 疏鬆檔案、電子郵件附件和內嵌的圖像支援 OCR。 如需 OCR 支援的圖像檔案格式清單，請參閱 [Advanced eDiscovery 中的支援檔案類型](supported-filetypes-ediscovery20.md#image)。

您必須為您在高級 eDiscovery 中所建立的每個案例啟用 OCR 功能。 如需詳細資訊，請參閱 [設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。
