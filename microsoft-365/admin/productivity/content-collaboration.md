---
title: Microsoft 生產力分數-內容共同作業
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: 內容共同作業的詳細資訊-人員體驗生產力分數。
ms.openlocfilehash: 2921cc738d1325416a0a5a8ab4a8eea9456b3269
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300076"
---
# <a name="content-collaboration--people-experiences"></a>內容共同作業–人員經驗

生產力分數透過使用 Microsoft 365 和技術經驗，為您組織的數位轉換旅程提供深入瞭解。 組織的分數反映人員和技術經驗度量，可與類似組織的基準進行比較。 「內容共同作業」類別屬於人員經驗度量。 若要深入瞭解，請參閱 [生產力評分概述](productivity-score.md) ，並閱讀 [Microsoft 的隱私權聲明](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>必要條件

若要開始使用內容共同作業深入瞭解，您組織中的人員需要獲得授權：

- 商務用 OneDrive
- SharePoint
- Exchange Online

如需詳細資訊，請參閱 [將授權指派給使用者](../manage/assign-licenses-to-users.md)。

 在上述產品中的人員在過去28天內至少已使用過一次之後，您將開始查看深入瞭解。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>為什麼您的組織&#39;的內容共同作業分數很重要

數位轉換的主要層面是人們如何在檔案中共同作業。 您有 Microsoft 365 的內容，使用者就能存取、建立、修改及共同處理來自任何位置的其他人員的內容。 「調查」顯示當人們使用線上檔案共同作業時，每個人每週平均會節約100分鐘。

## <a name="how-we-calculate-the-content-collaboration-score"></a>如何計算內容共同作業分數

我們提供主要的洞察力，其中包含組織中內容共同作業的主要度量。 然後，下列所詳述的計分架構用於計算組織的分數。

> [!NOTE]
> 在2021年4月22日，我們已變更共同作業者度量的計算方式。 這會影響 [主要洞察力](#primary-insight)、檔案共同作業 [功能，以及](#number-of-files-collaborated-on)內容共同作業得分的衡量方式。 這項變更可協助減少非人力代理程式中的資料干擾 (或來自 Microsoft 及其他協力廠商應用程式的 bot) ，進而產生更準確且具可操作性的分數。

### <a name="primary-insight"></a>主要洞察力

Microsoft OneDrive 商務及 SharePoint 協助使用者輕鬆地從裝置和應用程式 Microsoft 365 中建立、讀取和探索其個人和共用內容。 他們也可讓使用者安全地共用內容和共同作業。 主要的洞察力包含每個人都可以使用商務用 OneDrive 和 SharePoint 的資訊。 此外，它會分解有關在商務用 OneDrive 和 SharePoint 中儲存的內容讀取、建立及共同作業的詳細資料。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="來自通訊共同作業分數的主要洞察力。":::


考慮此資訊的類型包括 Word、Excel、PowerPoint、OneNote 和 PDF 檔。

1. **標頭：** 顯示您的組織中有權存取 OneDrive 或 SharePoint 誰對內容進行共同作業的人員所占的百分比。
2. **Body：** 提供詳細資訊，說明如何在線上讀取和建立線上檔案，以在檔案上協同作業。
3. **視覺效果 (目前狀態) ：**
    - 藍色的水準條，藍色的部分代表透過 OneDrive 或 SharePoint 誰在過去28天內，已有讀取者 **、建立者** 或在線上檔上的 **合作者**，已啟用檔案共同作業的人員所占的百分比。

        其定義如下：</br>
        **讀者：** 在 OneDrive 或 SharePoint 中存取或下載線上檔案的人員。</br>
        建立 **者：** 建立、修改、上傳、同步處理、存回、複製或移動線上 OneDrive 或 SharePoint 檔案的人員。</br>
        **合作者：** 使用 OneDrive 或 SharePoint 與線上檔案共同作業的人員。 如果有兩位人員在建立或修改了個人 Office 應用程式或 PDF 之後，他們會在28天的時段內讀取或編輯其線上或 PDF，這兩個人都是合作者。

        > [!NOTE]
        > 視覺化效果中考慮的檔案包括線上及儲存至 OneDrive 或 SharePoint 的 Word、Excel、PowerPoint、OneNote 或 PDF 檔案。 

    - 高光 (分數的分子/分母) 是用來計算每個水準條中所表達的百分比。
    
      - **讀者：**</br>
          - 分子：在過去28天的 OneDrive 或 SharePoint 中，存取或下載線上檔案的人員人數</br>
          - 分母：可以存取 OneDrive 或 SharePoint 至少一天28天的人員人數</br>
      - **創造者：**</br>
        - 分子：在過去28天內，在 OneDrive 或 SharePoint 中建立、修改、上傳、同步處理、存回、複製或移動線上檔案的人員人數</br>
        - 分母：在過去28天內，至少有1天可以存取 OneDrive 或 SharePoint 的人員人數。 </br> 
      - **合作：**</br>
        - 分子：在過去28天 OneDrive 或 SharePoint 中，已與線上檔案共同作業的人員人數</br>
        - 分母：在過去28天內，至少有1個 OneDrive 或 SharePoint 可以存取的人員人數。

    - 每個讀者、建立者及合作者的對等基準值也會顯示為百分數。 換句話說，建立者數目的值會顯示為可存取 OneDrive 或 SharePoint 之人員人數的百分比。
    
1. **資源連結：** 選取此連結可查看排序的影片及其他相關的說明內容。


#### <a name="trend-visualization-of-primary-insight"></a>主要洞察力的趨勢視覺化

走向視覺化效果圖表會顯示最近180天內，讀者、建立者及合作者的主要深入分析重要測量的趨勢線。 圖表上的每個資料點都是過去28天的活動匯總。 每個建立者資料點都提供在 X 軸上的每個日期之過去28天內，標記為「建立者」的所有人員計數。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="圖表顯示共同作業主要洞察力的趨勢。":::

### <a name="scoring-framework"></a>計分架構

組織的內容共同作業分數是在匯總 () 組織中度量，不論人員是否一致閱讀、建立或共同作業 Office 檔，例如 Word、Excel、PowerPoint、OneNote 或 pdf，或 OneDrive 或 SharePoint。

在個別使用者層級不提供分數。

## <a name="explore-how-your-organization-collaborates"></a>探索您的組織如何進行通力協作

我們也會提供資訊，協助您深入瞭解您的組織如何對內容進行處理。 這些額外的計量不會直接對您的生產力分數產生貢獻，但可協助您建立行動計畫做為數位轉換的一部分，以協助優化人員的運作方式。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>在 OneDrive 或 SharePoint 中建立檔案

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="顯示在 OneDrive 或 SharePoint 中建立檔案的人員人數的圖表":::

1. **標頭：** 會強調 OneDrive 或 SharePoint 上建立檔案 Microsoft 365 Office 應用程式上的使用中的人員所占的百分比。
2. **Body：** 提供 OneDrive 和 SharePoint 中的內容建立值的相關資訊。
3. **視覺效果：** 視覺化效果中的分解是指使用 Microsoft Office 應用程式在 OneDrive 和 SharePoint 中建立檔案的人員，如下所示：
      - **OneDrive：** 列的藍色 (色彩) 部分，列上的分數代表在 OneDrive 上建立內容的 Office 應用程式上的使用中的人員所占的百分比，如下所示：
        - 分子：過去28天內，在 OneDrive 中建立、修改、上傳、同步處理、存回、複製或移動線上 Office 檔案的人員人數。</br>
        - 分母：在過去28天內，可以存取 OneDrive 或 SharePoint 並存取 office 檔案的人員人數。
      - **SharePoint：** 列的藍色 (彩色) 部分，列上的分數代表 Office 應用程式上的使用中的人員，以及在 SharePoint 上建立內容的百分比，如下所示：</br>
         - 分子：在過去28天內，在 PowerPoint 上建立、修改、上傳、同步處理、存回、複製或移動線上 Office 檔案 (Microsoft Word、Excel、OneNote 或) 檔的人數。</br>
        - 分母：可以存取 OneDrive 或 SharePoint，並在過去28天記憶體取 Office 檔案的人員人數。

4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="use-of-attachments-in-email"></a>在電子郵件中使用附件

**在電子郵件中使用附件** 瞭解有多少使用者在電子郵件中附加實體檔案，而不是雲端中內容的連結，並監視此數目隨時間的減少。

:::image type="content" source="../../media/emailattachments.png" alt-text="電子郵件附件的使用。":::

1. **標頭：** 會強調在電子郵件中使用附件但未儲存至 OneDrive 或 SharePoint 之人員所占的百分比。
2. **Body：** 提供從共同作業和安全性觀點共用線上檔案的連結值的相關資訊。
3. **視覺效果：** 視覺化效果中的分解是表示在電子郵件中附加內容的人員在 OneDrive 或 SharePoint 上使用不同模式 (檔案的程度。線上檔的連結;和嵌入在電子郵件) 中的連結：
      - **附加檔案：** 列的藍色 (彩色) 部分和列的分數 (分子/分母) 表示在電子郵件中使用附件的人員百分比。
        - 分子：將檔案附加至最近28天內未儲存至 OneDrive 或 SharePoint 的電子郵件人數。
        - 分母：在過去28天內，可以存取 Exchange 和 OneDrive、SharePoint 或兩者的人員人數。
      - **線上檔的連結：** 列的藍色 (彩色) 部分，而分數線上的分數 (分子/分母) 代表使用附件的人員百分比，以及在電子郵件中附加檔案連結。
        - 分子：附加線上檔案連結的人員人數 (儲存至 OneDrive 或 SharePoint) 于過去28天內的電子郵件。
        - 分母：可以存取 Exchange 和 OneDrive、SharePoint 或兩者在過去28天內的人員人數。
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="sharing-of-online-files"></a>線上檔共用

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="顯示線上共用檔人數的圖表。":::

1. **標頭：** 會強調對從外部共用檔案 OneDrive 或 SharePoint 具有存取權的人員百分比。
2. **Body：** 提供系統管理員&#39; 能夠變更組織中的檔案共用設定，以啟用最適合組織之共同作業層級的相關資訊。
3. **視覺效果：** 代表有權存取 OneDrive 或 SharePoint 之人員在內部或外部共用檔案的程度：
      - **外部：** 列的藍色 (彩色) 部分和分數線上的分數 (分子/分母) 代表具有 OneDrive 或 SharePoint 的存取權，以及從外部共用檔案的人員百分比。
        -  分子：過去28天內，已共用檔案的外部人員人數
        - 分母：在過去28天內，至少有一則可以存取 OneDrive 或 SharePoint 之人員的總數。
      - **僅限內部：** 列的藍色 (彩色) 部分和分數線上的分數 (分子/分母) 代表具有 OneDrive 或 SharePoint 的存取權，而且只會在內部共用檔案的使用者百分比。
        - 分子：在過去28天內，只在內部共用檔案的人員人數
        - 分母：在過去28天內，至少有一則可以存取 OneDrive 或 SharePoint 之人員的總數。
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="number-of-files-collaborated-on"></a>共同合作的檔案數目

:::image type="content" source="../../media/intensityofcollab.png" alt-text="圖表顯示最具共同合作的檔案數目。":::

1. **標頭：** 會強調有權存取 OneDrive 或 SharePoint 誰在4個以上的檔案上進行共同作業的人員所占的百分比。
2. **Body：** 提供人員如何利用線上檔案以改善共同作業的相關資訊。
3. **視覺效果：** 根據共同作業的檔案數目，顯示有權存取 OneDrive 或 SharePoint 的人員的散佈。 這會透過下列4個類別進行顯示 (每個欄的藍色部分，分數代表可存取 OneDrive 或 SharePoint 屬於該類別的人員的百分比) ：
      - **無共同作業：**
        - 分子：過去28天內，未在任何檔案上共同作業的人員人數。
        - 分母：能夠存取 OneDrive 或 SharePoint 至少一天28天之人員的總人員人數。
      - **1-3 檔上的共同作業：**
        - 分子：過去28天內，在1-3 檔案上共同作業的人員人數。
        - 分母：在過去28天內，至少有一個人能夠存取 OneDrive 或 SharePoint 的人員總數。
      - **4-10 檔上的共同作業：**
        - 分子：過去28天內，在4-10 檔案上共同作業的人員人數。
        - 分母：在過去28天內，至少有一個人能夠存取 OneDrive 或 SharePoint 的人員總數。
      - **11或以上檔案共同作業：**
        - 分子：過去28天內，已在11個以上的檔案上共同作業的人員人數。
        - 分母：在過去28天內，至少有一個人能夠存取 OneDrive 或 SharePoint 的人員總數。
        
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive 和 SharePoint 的網路效能強度

:::image type="content" source="../../media/networkperfstrength.png" alt-text="顯示 OneDrive 和 SharePoint 之網路效能的圖表。":::

1. **標頭：** 會強調所有測試的裝置所占的百分比，而這些裝置的網路連線速度 OneDrive 和 SharePoint 都不佳。 
2. **Body：** 提供有關共同作業效能為何重要的資訊。 
3. **視覺效果：** 顯示與 OneDrive 和 SharePoint 相關之不同網路連線效能層級的裝置百分比：
      - **81-100 (最佳)**：橫條的深綠色 (彩色) 部分代表具有最佳效能的裝置百分比。
      - **61-80**：方塊的綠色 (彩色) 部分代表裝置的網路效能分數介於60-80 之間的百分比。 
      - **41-60**：灰色) 部分的橙色 (，代表網路績效分數介於40-60 之間的裝置百分比。 
      - **21-40**：紅色的 (彩色) 部分代表裝置的百分比，其網路效能分數為20-40。 
      - **0-20**：黑 red (彩色) 部分表示裝置的最差網路效能分數為0-20。 

## <a name="related-content"></a>相關內容

[Microsoft 365 應用程式健康情況–技術經驗](apps-health.md) (文章) 
[通訊–人員經驗](communication.md) (文章) \
[會議–人員經驗](meetings.md) (文章) \
[行動–人員體驗](mobility.md) (文章) \
) \ 中 (篇文章[的隱私權控制措施分數](privacy.md)
[團隊合作–人員經驗](teamwork.md) (文章) 
