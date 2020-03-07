---
title: Office 365 進階電子文件探索
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
description: 了解 Office 365 進階電子文件探索如何協助您分析 Office 365 內的資料、 簡化文件檢閱，以及進行決策有效率 ediscovery （英文）。
ms.openlocfilehash: 2e84ada8c6ca004c0f3c50a79fa6908148770955
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557873"
---
# <a name="advanced-ediscovery-classic"></a>進階電子文件 （傳統）

> [!IMPORTANT]
> 當我們繼續投入在較新版本的進階電子文件中，我們已宣佈 Office 365 進階電子文件探索，也稱為*進階電子文件 （傳統）* 或*進階電子文件 v1.0*淘汰的網站。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。 
  
使用進階電子文件，您可以更妥善地了解您 Office 365 的資料，並降低 eDiscovery 成本。 進階電子文件可協助您分析 Office 365 內的非結構化的資料、 執行更有效率的文件檢閱，以及進行決策來減少資料 ediscovery （英文）。 您可以使用儲存在 Exchange Online、 SharePoint Online、 商務用 OneDrive、 Skype for Business、 Office 365 群組和 Microsoft Teams 的資料。 您可以執行 eDiscovery 搜尋中的安全性和合規性中心來搜尋的內容群組、 個別信箱及站台，然後分析搜尋結果與進階電子文件。 當您準備進階 eDiscovery 中分析的搜尋結果時，光學字元辨識可讓與映像的文字擷取。 這項功能可讓強大的文字的進階電子文件套用至影像檔案的分析功能。
  
進階電子文件來簡化並加速藉由識別備援資訊與功能，例如近似重複項目偵測和電子郵件執行緒分析文件檢閱程序。 相關性功能才適用預測編碼的技術，以識別相關文件。 進階電子文件可學習從範例文件上標示決策，並套用統計以及自我學習技術來計算相關性資料組中每個文件。 這可讓您專注於主要文件、 進行快速尚未明智決策案例的策略、 cull 資料，並排定優先順序檢閱。
  
 **為什麼進階電子文件探索嗎？** Office 365 進階電子文件是根據現有的 Office 365 中的 eDiscovery 功能集。 例如，您可以使用的搜尋功能在 Office 365 安全性&amp;合規性中心，以執行初始搜尋的所有內容來源以找出並收集的資料，可能是相關的特定的法律案件您組織中。 然後您可以藉由套用文字分析、 機器學習和進階電子文件的相關性/預測式編碼功能，該資料上執行分析。 這可協助您快速處理上千個電子郵件、 文件和其他幾種類型的資料來尋找最有可能這些項目相關的特定的組織 
 
> [!NOTE]
> 進階電子文件為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。 如果您不具有該計劃，並想要再試進階電子文件，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 大小寫。 減少的資料集供進一步檢閱然後匯出登出 Office 365。 
  
## <a name="get-started"></a>入門

若要開始使用進階電子文件最快的方法是建立案例和準備搜尋結果安全性 & 合規性中心中的，載入進階電子文件，在這些結果，然後執行 Express 分析，以分析案例資料，然後將匯出的結果進行外部檢閱。
  
- [取得的快速概觀](quick-setup-for-advanced-ediscovery.md)的進階電子文件工作流程 
    
- 藉由建立案例、 指派 eDiscovery 權限，以及新增案例的成員，所有使用安全性 & 合規性中心的進階電子文件的 [[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md) 
    
- [準備和負載搜尋資料](prepare-data-for-advanced-ediscovery.md)至進階電子文件中的案例 
    
- [載入非 Office 365 資料](import-non-office-365-data-into-advanced-ediscovery.md)中狀況分析進階電子文件中 
    
- [使用快速分析](use-express-analysis-in-advanced-ediscovery.md)，以快速分析案例中的資料，並輕鬆地匯出結果 
    
## <a name="analyze-data"></a>分析資料

搜尋資料載入至進階電子文件中的案例之後，您將使用分析模組，若要開始分析它。 分析程序的第一個部分組成組織成群組的唯一檔案、 重複、 檔案及近似重複項目 （也叫做文件相似性）。 然後您組織的資料重新成階層結構化群組的電子郵件執行緒和佈景主題並選擇性地設定略過分析從排除特定文字的文字篩選器。 然後您執行分析，並檢視結果。
  
- [解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)準備進階 eDiscovery 中分析資料 
    
- 近似重複項目、 佈景主題，以及電子郵件執行緒，然後執行 [分析] 模組的 [[設定選項](set-analyze-options-in-advanced-ediscovery.md) 
    
- 若要排除的文字和文字字串正在分析;[設定忽略文字篩選器](set-ignore-text-in-advanced-ediscovery.md)這些篩選器也將會忽略文字，當您執行相關性分析 
    
- 分析程序[檢視結果](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析處理程序[設定進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
## <a name="set-up-relevance-training"></a>設定相關性訓練

預測編碼 （稱為的相關性） 在 [進階電子文件探索可讓您訓練上您要尋找的可讓您進行決策 （某個項目是否相關與否） 的系統上一小群的文件。
  
- [解如何設定相關性訓練](manage-relevance-setup-in-advanced-ediscovery.md)，標記與案例相關的檔案，並定義案例問題 
    
- [定義案例問題](define-issues-and-assign-users.md)，並將每一項問題指派給將訓練檔案的使用者 
    
- [新增匯入的檔案到目前或新的負載](set-up-loads-to-add-imported-files.md)，將會加入至相關性訓練。 負載是新的批次的檔案新增至案例並再使用相關性訓練 
    
- [定義反白顯示關鍵字](define-highlighted-keywords-and-advanced-options.md)，可以新增至相關性訓練。 這可協助您更妥善地找出與案例相關的檔案 
    
## <a name="run-the-relevance-module"></a>執行相關性模組

訓練設定之後, 您準備好執行相關性模組，並評估訓練設定的效率。 這會導致相關性排名，可協助您決定如果您需要執行額外的訓練，或如果您已準備好開始標記為您的案例相關的檔案。
  
- 標記、 追蹤及重新訓練[了解相關性處理程序](use-relevance-in-advanced-ediscovery.md)及反覆執行的程序的評估，根據檔案的範例設定 
    
- [解評定](assessment-in-relevance-in-advanced-ediscovery.md)，其中案例專家熟悉檢閱一組案例的檔案，並決定相關性訓練的有效性 
    
- 要計算效率的[評估案例檔案](tagging-and-assessment-in-advanced-ediscovery.md)(稱為 * 豐富性) 的訓練設定]，然後按一下 [標記檔案儲存為相關或與您的案例不相關。 這可協助您判斷是否目前訓練已足夠，或者，您應調整訓練設定。 
    
- [執行相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)之後評估已完成，且然後再次重申標記檔案儲存為相關或與您已定義的問題不相關的案例 
    
- 若要判斷相關性訓練是否已達到您評估目標的[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)程序 (稱為 * 穩定訓練狀態)，或是否需要更多的訓練;您也可以檢視每個案例問題的相關性結果 
    
- [根據相關性分析進行決策](decision-based-on-the-results-in-advanced-ediscovery.md)來判斷案例的結果集的大小檔案，可以匯出而進行檢閱 
    
- 若要驗證揀選相關性處理程序期間所做的決策的[測試相關性分析的品質](test-relevance-analysis-in-advanced-ediscovery.md) 
    
## <a name="export-results"></a>匯出結果

案例中分析資料進階電子文件的最後一個步驟是匯出進行外部檢閱分析的結果。
  
- [了解如何匯出案例資料](export-case-data-in-advanced-ediscovery.md)
    
- [匯出案例資料](export-results-in-advanced-ediscovery.md)
    
- [檢視批次歷程記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
    
- [匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>其他進階電子文件探索工具

進階電子文件提供額外的工具及分析案例資料，相關性分析，並將資料匯出以外的功能。
  
- [執行進階電子文件探索報表](run-reports-in-advanced-ediscovery.md)
    
- [定義案例與租用戶設定](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [進階電子文件探索公用程式](use-advanced-ediscovery-utilities.md)
