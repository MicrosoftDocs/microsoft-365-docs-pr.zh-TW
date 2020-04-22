---
title: 進階電子文件探索
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: 深入瞭解高級 eDiscovery 如何協助您分析資料、簡化檔檢查，並做出有效 eDiscovery 的決策。
ms.openlocfilehash: 554b8cfc5209ce0764e712c3aff4338347bc2881
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631834"
---
# <a name="advanced-ediscovery-classic"></a>進階電子文件探索 (傳統版)

> [!IMPORTANT]
> 當我們繼續投資較新版的先進 eDiscovery 時，我們宣佈退休的是「高級 ediscovery」（也稱為「*高級電子檔探索」（經典）* 或*advanced ediscovery 1.0*版）。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。 
  
透過高級電子檔探索，您可以更好地瞭解資料，並減少 eDiscovery 成本。 「高級 eDiscovery」可協助您分析非結構化資料、執行更有效率的檔檢查，並作出決策以減少 eDiscovery 的資料。 您可以使用儲存在 Exchange Online 中的資料、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 365 群組和 Microsoft 團隊。 您可以在 [安全性與合規性中心] 中執行 eDiscovery 搜尋，以搜尋群組、個別信箱和網站中的內容，然後使用「高級 eDiscovery」分析搜尋結果。 當您在高級 eDiscovery 中準備用於分析的搜尋結果時，光學字元辨識功能可讓您從影像提取文字。 這項功能可讓高級 eDiscovery 的強大文字分析功能能夠套用到圖像檔案。
  
Advanced eDiscovery 可透過接近重複偵測和電子郵件線索分析等功能識別冗余資訊，以簡化並加速檔審閱過程。 相關性功能會套用預測編碼技術來識別相關的檔。 「高級 eDiscovery」會從您的範例檔的標記決策中瞭解，並套用統計及自我教學技術，計算資料集中每個檔的相關性。 這可讓您將重點放在重要檔上，並在案例策略、挑選資料和優先順序檢查等方面作出及時的決策決策。
  
 **為何要成為高級電子檔探索？** 在 Office 365 的現有 eDiscovery 功能集中建立高級 eDiscovery。 例如，您可以使用安全&amp;規範中心中的「搜尋」功能，對組織中的所有內容來源執行初始搜尋，以找出並收集可能與特定法律案例相關的資料。 接著，您可以套用 text analytics、機器學習及高級 eDiscovery 的相關性/預測性編碼功能，對該資料執行分析。 這可協助您的組織快速處理成千上萬的電子郵件訊息、檔，以及其他種類的資料，以找出最可能與特定相關的專案。 
 
> [!NOTE]
> 「高級 eDiscovery」需要 Office 365 E3，具有您組織的「高級規範附加元件」或「E5」訂閱。 如果您沒有這項計畫，且想要嘗試使用 Advanced eDiscovery，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 情況 下。 簡化後的資料集可以從 Office 365 匯出，以供進一步複查。 
  
## <a name="get-started"></a>入門

開始使用高級 eDiscovery 的最快捷方式是建立案例並準備安全性 & 規範中心的搜尋結果，並在 [Advanced eDiscovery] 中載入這些結果，然後執行 [快速分析] 以分析案例資料，然後將結果匯出以進行外部審閱。
  
- [快速瞭解](quick-setup-for-advanced-ediscovery.md)高級 eDiscovery 工作流程 
    
- 使用安全性 & 合規性中心建立案例、指派 eDiscovery 許可權及新增案例成員，以設定高級 eDiscovery 的[使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)。 
    
- 在高級電子檔探索的案例中[準備及載入搜尋資料](prepare-data-for-advanced-ediscovery.md) 
    
- 將[非 Office 365 資料載入](import-non-office-365-data-into-advanced-ediscovery.md)到案例中，以在高級 eDiscovery 中進行分析 
    
- [使用快速分析](use-express-analysis-in-advanced-ediscovery.md)以快速分析案例中的資料，然後輕鬆匯出結果 
    
## <a name="analyze-data"></a>分析資料

在 [Advanced eDiscovery] 中載入搜尋資料後，您將使用 [分析] 模組開始進行分析。 分析程式的第一個部分包括將檔案組織成一組獨特的檔案、重複的專案，以及近乎重複的專案（也稱為檔相似性）。 然後，您可以將資料再次組織成分層結構化的電子郵件執行緒及主題，並選擇性地設定 [忽略文字篩選]，以排除特定文字的分析。 然後，您會執行分析並查看結果。
  
- [深入瞭解檔相似性](understand-document-similarity-in-advanced-ediscovery.md)，以準備在高級 eDiscovery 中分析資料 
    
- 設定臨近重複、主題及電子郵件執行緒[的選項](set-analyze-options-in-advanced-ediscovery.md)，然後執行分析模組 
    
- 設定 [忽略文字和文字字串加以分析] 的 [[忽略文字] 篩選器](set-ignore-text-in-advanced-ediscovery.md);當您執行相關性分析時，這些篩選也會略過文字 
    
- [查看](view-analyze-results-in-advanced-ediscovery.md)分析處理常式的結果 
    
- 設定分析處理常式的[高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
## <a name="set-up-relevance-training"></a>設定相關性訓練

在 [Advanced eDiscovery] 中的預測編碼（稱為「相關性」），可讓您在小型檔上進行決策（有關是否相關），讓系統在您要尋找的專案上進行訓練。
  
- [瞭解如何設定相關性訓練](manage-relevance-setup-in-advanced-ediscovery.md)、標記與案例相關的檔案，以及定義案例問題 
    
- [定義案例問題](define-issues-and-assign-users.md)，並將每個問題指派給將訓練檔的使用者 
    
- 將匯入的檔案新增至將新增至相關性訓練的[目前或新的負載](set-up-loads-to-add-imported-files.md)。 「負載」是新增至案例，然後用於相關性訓練的新批次檔 
    
- 定義可以新增至相關性訓練的[突出顯示關鍵字](define-highlighted-keywords-and-advanced-options.md)。 這可協助您更好地識別與案例相關的檔案 
    
## <a name="run-the-relevance-module"></a>執行相關性模組

設定訓練後，您就可以執行相關性模組，並評估訓練設定的有效性。 這會產生相關性排名，可協助您決定是否需要執行其他訓練，或是否準備好開始標籤與案例相關的標記。
  
- [深入瞭解](use-relevance-in-advanced-ediscovery.md)根據檔案的範例集合，相關性處理常式和進行評估、標記、追蹤和重新培訓的處理過程 
    
- [瞭解評估](assessment-in-relevance-in-advanced-ediscovery.md)，熟悉案例的專家會回顧一組案例檔案，並判斷相關性訓練的效能 
    
- [評估案例](tagging-and-assessment-in-advanced-ediscovery.md)檔案，以計算訓練設定的效能（稱為「* 豐富程度」），然後將檔案標記為相關或不適用於您的案例。 這可協助您判斷目前的訓練是否足夠，或者是否應該調整訓練設定。 
    
- 完成評估之後請[執行相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)，然後再將檔案標記為相關的問題或與您為案例定義的問題無關。 
    
- [追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)程式，判斷相關性訓練是否已達到評估目標（也稱為「* 穩定的訓練狀態」），或是否需要進行更多訓練;您也可以針對每個案例問題，查看相關性結果 
    
- 根據[相關性分析作出決策](decision-based-on-the-results-in-advanced-ediscovery.md)，以判斷可匯出以供審閱之一組所產生之案例檔案的大小 
    
- [測試相關性分析的品質](test-relevance-analysis-in-advanced-ediscovery.md)，以驗證相關性過程中所進行的挑選決定 
    
## <a name="export-results"></a>匯出結果

在「高級 eDiscovery」中分析案例資料的最後一個步驟，就是匯出分析的結果以進行外部考核。
  
- [瞭解匯出案例資料](export-case-data-in-advanced-ediscovery.md)
    
- [匯出案例資料](export-results-in-advanced-ediscovery.md)
    
- [檢視批次歷程記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
    
- [匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>其他的高級電子檔探索工具

「高級 eDiscovery」提供其他工具和功能，除了分析案例資料、相關性分析和匯出資料之外。
  
- [執行高級 eDiscovery 報告](run-reports-in-advanced-ediscovery.md)
    
- [定義案例與租使用者設定](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高級 eDiscovery 公用程式](use-advanced-ediscovery-utilities.md)
