---
title: Microsoft 生產力分數-內容共同作業
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: 87f89af527e2a1b843a9b70fbef590b69d920f7d
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804594"
---
# <a name="content-collaboration--people-experiences"></a>內容共同作業–人員經驗

生產力分數可協助您使用有關人員如何使用 Microsoft 365 應用程式，以及支援這些應用程式的技術體驗，來轉換作業的運作方式。 分數會反映您的組織&#39;人員和技術經驗的效能，並與您的組織（如您的組織）比較您的分數。 內容共同作業是一項位於人員經驗底下的措施。 請參閱  [生產力分數綜述](productivity-score.md)。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>為什麼您的組織&#39;的內容共同作業分數很重要

組織生產力的基本 pillar 是人們如何在檔案中共同作業。 透過 Microsoft 365 的內容，使用者存取、建立、修改和與其他人的內容共同作業。 「調查」顯示當人們使用線上檔案共同作業時，每個人每週平均會節約100分鐘。 請參閱 [證據](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

## <a name="how-we-calculate-the-content-collaboration-score"></a>如何計算內容共同作業分數

我們提供主要的洞察力，包含內容共同作業的主要計量。 然後，下列詳述的計分架構用於計算您的分數。

### <a name="primary-insight"></a>主要洞察力

適用于商務和 SharePoint 的 Microsoft OneDrive 可讓使用者在不同的裝置和應用程式中輕鬆地建立、讀取和探索 Microsoft 365 中的個人和共用內容。 他們也可讓使用者安全地共用內容和共同作業。 主要的洞察力包含每個人都可以使用 OneDrive 商務及 SharePoint 的資訊。 此外，它會分解有關為商務和 SharePoint OneDrive 所儲存之內容讀取、建立及共同作業的詳細資料。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="來自通訊共同作業分數的主要洞察力。":::


考慮此資訊的類型包括 Word、Excel、PowerPoint、OneNote 和 PDF 檔。

1. **標頭：** 顯示有權存取 OneDrive 或 SharePoint 誰對內容進行共同作業的人員所占的百分比。
2. **Body：** 提供詳細資訊，說明如何在線上讀取和建立線上檔案，以在檔案上協同作業。
3. **視覺效果 (目前狀態) ：**
    - 藍色的水平線條，藍色的部分代表透過 OneDrive 或 SharePoint 誰是 **讀者、建立者** 或在過去28天內的線上檔上的 **合作者** ，而啟用檔共同作業的人員百分比。

        其定義如下：</br>
        **讀者：** 在 OneDrive 或 SharePoint 中存取或下載線上檔案的人員。</br>
        建立 **者：** 建立、修改、上傳、同步處理、存回、複製或移動線上 OneDrive 或 SharePoint 檔案的人員。</br>
        **合作者：** 使用 OneDrive 或 SharePoint 與線上檔案共同作業的人員。 如果有兩個人是共同作業者在建立或修改的線上 Office 應用程式或 PDF 之後，在28天的時段內讀取或編輯，則為合作者。

        > [!NOTE]
        > 視覺化效果中考慮的檔案包括線上及儲存至 OneDrive 或 SharePoint 的 Word、Excel、PowerPoint、OneNote 或 PDF 檔。 

    - 反白顯示分數的 (分子/分母) ，用來計算每個水準條中所表達的百分比。
    
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

趨勢視覺化效果圖顯示讀取者、建立者和合作者的主要深入分析重要測量線趨勢線，在過去的180天。 圖表上的每個資料點都是過去28天的活動匯總。 每個建立者資料點都提供在 X 軸上的每個日期之過去28天內，標記為「建立者」的所有人員計數。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="來自通訊共同作業分數的主要洞察力。":::

### <a name="scoring-framework"></a>計分架構

「內容共同作業分數」會度量人員是否要在 OneDrive 或 SharePoint 的線上 Office 檔案（例如 Word、Excel、PowerPoint、OneNote 或 PDF）上一致地閱讀、建立或共同作業。

## <a name="explore-how-your-organization-collaborates"></a>探索您的組織如何進行通力協作

我們也會提供資訊，協助您深入瞭解組織中的人員如何對內容進行共同作業。 這些額外的衡量不會直接對您的生產力評分產生貢獻，但可協助您建立行動計畫，以優化人員的運作方式。

### <a name="creating-files-to-onedrive-or-sharepoint"></a>建立檔案以 OneDrive 或 SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="來自通訊共同作業分數的主要洞察力。":::

1. **標頭：** 會強調在 Microsoft 365 Office 應用程式上，在 OneDrive 或 SharePoint 上建立檔案的活動人員所占的百分比。
2. **Body：** 提供 OneDrive 和 SharePoint 中的內容建立值的相關資訊。
3. **視覺效果：** 視覺化效果中的分解是指使用 Microsoft Office 應用程式在 OneDrive 和 SharePoint 中建立檔案的人員，如下所示：
      - **OneDrive：** 列的藍色 (彩色) 部分，列上的分數表示在 Office 應用程式上，在 OneDrive 上建立內容的活動人員的百分比，如下所示：
        - 分子：過去28天內，在 OneDrive 中建立、修改、上傳、同步處理、存回、複製或移動線上 Office 檔案的人員人數。</br>
        - 分母：在過去28天內，可以存取 OneDrive 或 SharePoint 並存取 office 檔案的人員人數。
      - **SharePoint：** 列的藍色 (彩色) 部分，列上的分數代表在 Office 應用程式上作用中的人員的百分比，以及在 SharePoint 上建立內容，如下所示：</br>
         - 分子：建立、修改、上傳、同步處理、存回、複製或移動線上 Office 檔案 (Microsoft Word、Excel、PowerPoint 或 OneNote 檔案) 于過去28天內 SharePoint 內的人員人數。</br>
        - 分母：在過去28天內，可以存取 OneDrive 或 SharePoint 並存取 Office 檔案的人員人數。

4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="use-of-attachments-in-email"></a>在電子郵件中使用附件

:::image type="content" source="../../media/emailattachments.png" alt-text="來自通訊共同作業分數的主要洞察力。":::

1. **標頭：** 會強調在電子郵件中使用附件但未儲存至 OneDrive 或 SharePoint 之人員所占的百分比。
2. **Body：** 提供從共同作業和安全性觀點共用線上檔案的連結值的相關資訊。
3. **視覺效果：** 視覺化效果中的分解是表示在電子郵件中附加內容的人員在 OneDrive 或 SharePoint 上使用不同模式 (檔案的程度。線上檔的連結;和嵌入在電子郵件) 中的連結：
      - **附加檔案：** 列的藍色 (彩色) 部分和列的分數 (分子/分母) 表示在電子郵件中使用附件的人員百分比。
        - 分子：將檔案附加至最近28天內未儲存至 OneDrive 或 SharePoint 的電子郵件人數
        - 分母：過去28天內，在電子郵件中以任何形式使用附件的人員人數
      - **線上檔的連結：** 列的藍色 (彩色) 部分，而分數線上的分數 (分子/分母) 代表使用附件的人員百分比，以及在電子郵件中附加檔案連結。
        - 分子：附加到線上檔案的電子郵件連結的人員人數 (儲存至 OneDrive 或 SharePoint 在過去28天內) 。
        - 分母：在過去28天內，在電子郵件中以任何形式使用附件的人員人數。
      - **在電子郵件中嵌入連結：** 列的藍色 (彩色) 部分，列上的分數表示在電子郵件內嵌入連結的人員百分比。
        - 分子：在線上檔的電子郵件中嵌入連結的人員人數 (儲存至 OneDrive 或 SharePoint) 上的28天內）
        - 分母：過去28天內，在電子郵件中以任何形式使用附件的人員人數
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="sharing-of-online-files"></a>線上檔共用

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="來自通訊共同作業分數的主要洞察力。":::

1. **標頭：** 會強調對從外部共用檔案 OneDrive 或 SharePoint 具有存取權的人員百分比。
2. **Body：** 提供系統管理員&#39; 能夠變更組織中的檔案共用設定，以啟用最適合組織之共同作業層級的相關資訊。
3. **視覺效果：** 代表有權存取 OneDrive 或 SharePoint 之人員在內部或外部共用檔案的程度：
      - **外部：** 列的藍色 (彩色) 部分和分數線上的分數 (分子/分母) 代表具有 OneDrive 或 SharePoint 的存取權，以及從外部共用檔案的人員百分比。
        -  分子：過去28天內，已共用檔案的外部人員人數
        - 分母：在過去28天內，至少有一天可以存取 OneDrive 或 SharePoint 的人員總數
      - **僅限內部：** 列的藍色 (彩色) 部分和分數線上的分數 (分子/分母) 代表具有 OneDrive 或 SharePoint 的存取權，而且只會在內部共用檔案的使用者百分比。
        - 分子：在過去28天內，只在內部共用檔案的人員人數
        - 分母：在過去28天內，至少有一天可以存取 OneDrive 或 SharePoint 的人員總數
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="intensity-of-files-collaborated-on"></a>共同開啟的檔案密度

:::image type="content" source="../../media/intensityofcollab.png" alt-text="來自通訊共同作業分數的主要洞察力。":::

1. **標頭：** 這會強調使用者有權存取 OneDrive 或 SharePoint 誰在4個以上的檔案上進行共同作業的使用者百分比。
2. **Body：** 這會提供人員如何利用線上檔案以改善共同作業的相關資訊。
3. **視覺效果：** 這會根據共同作業的檔案數目，顯示有權存取 OneDrive 或 SharePoint 的人員的散佈。 這會透過下列4個類別進行顯示 (每個欄的藍色部分，分數代表可存取 OneDrive 或 SharePoint 屬於該類別的人員的百分比) ：
      - **無共同作業：**
        - **分子：** 過去28天內，未在任何檔案上進行共同作業的人員人數
        - **分母：** 可以存取 OneDrive 或 SharePoint 至少前28天之1天的人員總數
      - **1-3 檔上的共同作業：**
        - **分子：** 過去28天內，在1-3 檔案上共同作業的人員人數
        - **分母：** 在過去28天內，至少有一個人能夠存取 OneDrive 或 SharePoint 的人員總數
      - **4-10 檔上的共同作業：**
        - **分子：** 過去28天內，在4-10 檔案上共同作業的人員人數
        - **分母：** 在過去28天內，至少有一天可以存取 OneDrive 或 SharePoint 的人員總數
      - **11或以上檔案共同作業：**
        - **分子：** 過去28天內，在11個以上的檔案上共同作業的人員人數
        - **分母：** 在過去28天內，至少有一個人能夠存取 OneDrive 或 SharePoint 的人員總數
        
4. **資源連結：** 選取此連結可查看 [說明] 內容。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive 和 SharePoint 的網路效能強度

:::image type="content" source="../../media/networkperfstrength.png" alt-text="來自通訊共同作業分數的主要洞察力。":::

1. **標頭：** 會強調所有測試的裝置所占的百分比，而這些裝置的網路連線速度 OneDrive 和 SharePoint 都不佳。 
2. **Body：** 提供有關共同作業效能為何重要的資訊。 
3. **視覺化效果：** 顯示在 OneDrive 和 SharePoint 方面具有不同網路連線效能層級的裝置百分比。
      - **80-100 (最佳)** ：線條的深綠色 (彩色) 部分代表具有最佳效能的裝置百分比。
      - **60-80** ：紅色) 部分的綠色 (，代表裝置的網路效能分數在60-80 之間的百分比。 
      - **40-60** ：灰色) 部分的橙色 (表示裝置的百分比與40-60 之間的網路效能分數。 
      - **20-40** ：紅色的 (彩色) 部分表示裝置的百分比，其網路效能分數介於20-40 之間。 
      - **0-20** ：黑 red (彩色) 部分會占0-20 的最差網路效能分數。 

### <a name="people-in-your-organization"></a>組織中的人員

本節會提供與所顯示之所有真知灼見相關之活動的使用者層級詳細資料，協助您採取行動所要重點的度量。

下列各欄是在使用者層級的表格中呈現：

- [使用者 **名稱** ] 是使用者的電子郵件地址。
- [ **顯示名稱** ] 是使用者的完整名稱。
- [ **上次活動日期** ] 指的是使用者最後一次執行與過去28天內的內容共同作業相關的活動
- **部門：** 使用者&#39;s 部門，在 Azure Active Directory (AAD) 中定義
- **公司：** 使用者&#39;s 公司，如 AAD 中所定義
- **國家/地區：** 使用者&#39;的國家/地區，如 AAD 中所定義
- **狀態：** 使用者&#39;s 狀態，如 AAD 中所定義
- **城市：** 使用者&#39;s 城，如 AAD 中所定義
- **OneDrive：** 布林值，指出使用者是否有存取 tor OneDrive 至少一次的28天的1。
- **SharePoint：** 布林值，指出是否至少有一位使用者有權 toSharePoint 至少1天的最後28天。
- **存取的 Office 檔案：** 布林值，指出使用者是否已透過 Microsoft Word、Excel、PowerPoint 或 OneNote 在過去28天記憶體取的檔。
- 已 **在 OneDrive 上建立檔案：** 布林值，指出在過去28天內，在 OneDrive 上建立、修改、上傳、同步處理、存回、複製或移動的線上檔案 (于 Microsoft Word、Excel、PowerPoint 或 OneNote) 中。
- 已 **在 SharePoint 上建立檔案：** 布林值，指出在過去28天內，在 SharePoint 上建立、修改、上傳、同步處理、存回、複製或移動的線上檔案 (于 Microsoft Word、Excel、PowerPoint 或 OneNote) 中。
- **讀取天數：** 使用者在 Microsoft Word、Excel、PowerPoint、OneNote 或 PDF) 中 (所存取或下載之線上檔案的天數，在過去28天內 OneDrive 或 SharePoint。
- 建立 **者天數：** 最近28天內，在 Microsoft Word、Excel、PowerPoint、OneNote 或 PDF) OneDrive 中建立、修改、上傳、同步處理、存回、複製或移動的線上檔案的天數 (。
- **檔共同作業：** 在過去28天內，OneDrive 或 SharePoint 人員共同開啟的線上檔案數目。
- **內部共用** 的檔案：在過去28天內，OneDrive 或 SharePoint 組織中與其他人共用的人員的線上檔案數目。
- **外部共用** 的檔案：在過去28天內，OneDrive 或 SharePoint 與組織外部其他人員共用的人員的線上檔案數目。
- **電子郵件傳送的附件：** 布林值，指出使用者是否已傳送含檔案的電子郵件 (不在 OneDrive 上，或在過去的28天內 SharePoint) 做為附件。
- 以 **電子郵件傳送的線上檔附件：** 布林值，指出在過去28天內，是否要使用 OneDrive 或 SharePoint) 附件的方式傳送電子郵件，以連結到或上的線上檔案 (。
- **嵌入線上檔案的連結：** 布林值，指出在過去28天內，在電子郵件內文中 OneDrive 或 SharePoint) 嵌入的電子郵件中，是否有線上檔案的連結 (。

## <a name="related-content"></a>相關內容

[Microsoft 365 應用程式健康情況–技術經驗](apps-health.md) (文章) \
[通訊–人員經驗](communication.md) (文章) \
[會議–人員經驗](meetings.md) (文章) \
[行動–人員體驗](mobility.md) (文章) \
) \ 中 (篇文章[的隱私權控制措施分數](privacy.md)
[團隊合作–人員經驗](teamwork.md) (文章) 
