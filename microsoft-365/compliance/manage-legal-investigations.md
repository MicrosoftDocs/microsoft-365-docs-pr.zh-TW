---
title: 管理 Office 365 中的法律調查
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 在 Office 365 安全性 & 合規性中心] 中使用 eDiscovery 案例，來管理貴組織的法律調查。 如果您有 E5 訂閱，您可以進一步分析案例資料，藉由使用文字分析、 機器學習和進階電子文件的預測式編碼功能。
ms.openlocfilehash: c6b5b3048039a8c92d120d2b9f46d6d22d9ccee0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077192"
---
# <a name="manage-legal-investigations-in-office-365"></a>管理 Office 365 中的法律調查

組織有許多原因可回應涉及特定主管或組織中的其他員工的法律案件。 這可能需要快速尋找及保留需進一步調查的特定資訊的電子郵件、 文件、 立即訊息對話和日常工作中的人員所使用的其他內容位置中。 您可以安全 & 與規範中心使用 eDiscovery 案例工具來執行這些結構元件及其他許多類似的活動。
  
[管理法律調查與 eDiscovery 案例](#manage-legal-investigations-with-ediscovery-cases)
  
[分析使用 Office 365 進階電子文件探索案例資料](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**想知道如何 Microsoft 管理其電子文件探索調查嗎？** 以下是[技術白皮書：](https://go.microsoft.com/fwlink/?linkid=852161)您可以下載說明我們如何使用相同的 Office 365 搜尋和調查工具來管理我們的內部的 eDiscovery 工作流程。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>管理法律調查與 eDiscovery 案例

eDiscovery 案例可讓您控制可以建立、 存取及管理組織中的 eDiscovery 案例。 若要新增成員並控制哪些類型的動作，他們可以執行、 保留內容位置相關的法律案件，以及使用內容搜尋 」 工具來搜尋位置保留的內容，可能會回應您的案例使用案例。 然後您也可以匯出及下載進一步外部的檢閱者所使用的結果。 如果您的 Office 365 組織有 E5 訂閱，您也可以準備進階 eDiscovery 中分析的搜尋結果。
  
- 若要進行的[管理您的 eDiscovery 工作流程](ediscovery-cases.md)來建立和使用 eDiscovery 案例的每個法律調查您的組織有 
    
- [指派 eDiscovery 權限](assign-ediscovery-permissions.md)控制可以建立及管理組織中的 eDiscovery 案例 
    
- [設定合規性界限](tagging-and-assessment-in-advanced-ediscovery.md)來控制可搜尋電子文件探索管理員的使用者內容位置 
    
- 在您的組織中[搜尋的內容](search-for-content.md) 
    
- [準備進階電子文件探索案例內容](prepare-search-results-for-advanced-ediscovery.md)，您可以執行分析使用進階電子文件探索的強大分析工具，例如光學字元辨識、 電子郵件執行緒，和預測撰寫程式碼 
    
### <a name="use-scripts-for-advanced-scenarios"></a>在進階案例中使用指令碼

如前一節所列的內容搜尋案例指令碼，我們也建立了一些安全性 & 合規性中心 PowerShell 指令碼，以協助您管理 eDiscovery 案例。
  
- [建立 eDiscovery 保留報告](create-a-report-on-holds-in-ediscovery-cases.md)，其中包含所有的資訊保留組織中的 eDiscovery 案例相關聯 
    
- [新增信箱和 OneDrive 位置](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)之清單使用者 eDiscovery 保留 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>分析使用 Office 365 進階電子文件探索案例資料

Office 365 進階電子文件為基礎以上各節所述的內容搜尋和 eDiscovery 功能。 您建立的 eDiscovery 案例之後，就地 custodian 位置上的暫留，以及收集資料，可能會回應的情況下，您可以再進一步分析資料所使用的文字分析、 機器學習和進階預測式編碼功能eDiscovery。 這可協助您快速處理上千個電子郵件、 文件和其他幾種類型的資料來尋找最有可能這些項目相關的特定案例的組織。 而且，我們，以便您可以順暢地管理安全性 & 合規性中心內的大小寫相同已整合案例管理和進階電子文件。
  
> [!NOTE]
> 若要分析使用進階電子文件的使用者資料，使用者 (資料的 custodian) 必須被指派 Office 365 E5 授權。 或者，使用 Office 365 E1 或 E3 授權的使用者可被指派的進階電子文件獨立授權。 系統管理員和法務人員對於已指派給的情況下，並使用進階電子文件探索分析資料不需要 E5 授權。 
  
### <a name="get-started"></a>開始使用

若要開始使用進階電子文件的最快方式是建立案例和準備搜尋結果安全性 & 合規性中心中的，載入進階電子文件，在這些結果，然後執行 Express 分析，以分析案例資料，然後將匯出的結果外部的檢閱。
  
- [取得的快速概觀](quick-setup-for-advanced-ediscovery.md)的進階電子文件工作流程 
    
- 藉由建立案例、 指派 eDiscovery 權限，以及新增案例的成員，所有使用安全性 & 合規性中心的進階電子文件的 [[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md) 
    
- [準備和負載搜尋資料](prepare-data-for-advanced-ediscovery.md)至進階電子文件中的案例 
    
- [載入非 Office 365 資料](import-non-office-365-data-into-advanced-ediscovery.md)中狀況分析進階電子文件中 
    
- [使用快速分析](use-express-analysis-in-advanced-ediscovery.md)，以快速分析案例中的資料，並輕鬆地匯出結果 
    
### <a name="analyze-data"></a>分析資料

搜尋資料載入至進階電子文件中的案例之後，您將使用分析模組，若要開始分析它。 分析程序的第一個部分組成組織成群組的唯一檔案、 重複、 檔案及近似重複項目 （也叫做文件相似性）。 然後您會將資料組織到電子郵件執行緒和佈景主題的階層結構化群組的一次並選擇性地設定略過分析從排除特定文字的文字篩選器。 然後執行分析，並檢視結果。
  
- [解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)準備進階 eDiscovery 中分析資料 
    
- 近似重複項目、 佈景主題，以及電子郵件執行緒，然後執行 [分析] 模組的 [[設定選項](set-analyze-options-in-advanced-ediscovery.md) 
    
- 若要排除的文字和文字字串正在分析;[設定忽略文字篩選器](set-ignore-text-in-advanced-ediscovery.md)這些篩選器也將會忽略文字，當您執行相關性分析 
    
- 分析程序[檢視結果](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析處理程序[設定進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
### <a name="set-up-relevance-training"></a>設定相關性訓練

預測編碼 （稱為的相關性） 在 [進階電子文件探索可讓您訓練上您要尋找的可讓您進行決策 （某個項目是否相關與否） 的系統上一小群的文件。
  
- [解如何設定相關性訓練](manage-relevance-setup-in-advanced-ediscovery.md)，標記與案例相關的檔案，並定義案例問題 
    
- [定義案例問題](define-issues-and-assign-users.md)，並將每一項問題指派給將訓練檔案的使用者 
    
- [新增匯入的檔案到目前或新的負載](set-up-loads-to-add-imported-files.md)，將會加入至相關性訓練;負載是新的批次的檔案新增至案例並再使用相關性訓練 
    
- [定義反白顯示關鍵字](define-highlighted-keywords-and-advanced-options.md)，可以新增至相關性訓練;這可協助您更妥善地找出與案例相關的檔案 
    
### <a name="run-the-relevance-module"></a>執行相關性模組

在設定訓練之後, 您準備好執行相關性模組，以及評估此結果的相關性排名，可協助您決定如果您需要執行額外的訓練，或如果您已準備好開始標記檔案儲存為訓練設定的效率相關至您的案例。
  
- 標記、 追蹤及重新訓練[了解相關性處理程序](use-relevance-in-advanced-ediscovery.md)及反覆執行的程序的評估，根據檔案的範例設定 
    
- [解評定](assessment-in-relevance-in-advanced-ediscovery.md)，其中案例專家熟悉檢閱一組案例的檔案，並決定相關性訓練的有效性 
    
- [評估案例檔案](tagging-and-assessment-in-advanced-ediscovery.md)來計算 （稱為*豐富性*） 的有效性的訓練設定]，然後為相關或與您的大小寫; 不相關的標記檔案這可協助您判斷是否目前訓練已足夠，或者，您應調整訓練設定。 
    
- [執行相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)之後評估已完成，且然後再次重申標記檔案儲存為相關或與您已定義的問題不相關的案例 
    
- 若要判斷評估目標 （又稱為*穩定訓練狀態*），或是否需要更多的訓練;，是否已達到相關性訓練的[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)程序您也可以檢視每個案例問題的相關性結果 
    
- [根據相關性分析進行決策](decision-based-on-the-results-in-advanced-ediscovery.md)來判斷案例的結果集的大小檔案，可以匯出而進行檢閱 
    
- 若要驗證揀選相關性處理程序期間所做的決策的[測試相關性分析的品質](test-relevance-analysis-in-advanced-ediscovery.md) 
    
### <a name="export-results"></a>匯出結果

案例中分析資料進階電子文件的最後一個步驟是匯出進行外部檢閱分析的結果。
  
- [了解如何匯出案例資料](export-case-data-in-advanced-ediscovery.md)
    
- [匯出案例資料](export-results-in-advanced-ediscovery.md)
    
- [檢視批次歷程記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
    
- [匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>其他進階電子文件探索工具

進階電子文件提供額外的工具及分析案例資料，相關性分析，並將資料匯出以外的功能。
  
- [執行進階電子文件探索報表](run-reports-in-advanced-ediscovery.md)
    
- [定義案例與租用戶設定](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [進階電子文件探索公用程式](use-advanced-ediscovery-utilities.md)
