---
title: 在 Office 365 中搜尋內容
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: 使用安全性 & 合規性中心，以快速找到 Exchange 信箱、 SharePoint 網站和 OneDrive 的位置，以及立即訊息中商務用 Skype 交談中的文件中的 [電子郵件的內容搜尋電子文件探索工具。
ms.openlocfilehash: 9978262223de059511a011358764069ef23d4340
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077797"
---
# <a name="search-for-content-in-office-365"></a>在 Office 365 中搜尋內容

使用安全性 & 合規性中心，以快速找到 Exchange 信箱、 SharePoint 網站和 OneDrive 的位置，以及立即訊息中商務用 Skype 交談中的文件中的 [電子郵件的內容搜尋工具。 您可以使用內容搜尋工具來搜尋電子郵件、 文件和立即訊息交談中 Office 365 共同作業工具，例如 Microsoft Teams 和 Office 365 群組。
  
## <a name="search-for-content"></a>搜尋內容

第一個步驟是開始使用內容搜尋工具來選擇要搜尋並設定關鍵字查詢以搜尋特定項目內容位置。 或者，您只可以為空白查詢，在目標位置傳回的所有項目。
  
- [建立並執行](content-search.md)內容搜尋 
    
- [組建搜尋查詢和使用條件](keyword-queries-and-search-conditions.md)縮小搜尋範圍 
    
- [設定搜尋權限篩選](permissions-filtering-for-content-search.md)以便電子文件探索管理員可以僅搜尋組織中的信箱或網站的子集 
    
- [執行識別碼清單搜尋](csv-file-for-an-id-list-content-search.md)來搜尋特定的電子郵件 
    
- Office 365 中的內部部署使用者的[搜尋雲端式信箱](search-cloud-based-mailboxes-for-on-premises-users.md)

- [檢視關鍵字統計資料](view-keyword-statistics-for-content-search.md)的搜尋，然後精簡查詢視結果 
    
- 您的組織已匯入至 Office 365 的[搜尋協力廠商資料](use-content-search-to-search-third-party-data-that-was-imported.md) 
    
- [大量編輯](bulk-edit-content-searches.md)的查詢，以及多個搜尋內容位置 
    
- 若要解決錯誤的內容位置的 [[重試內容搜尋](retry-failed-content-search.md)

- [保留密件副本收件者](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members)讓他們可以搜尋 


## <a name="perform-actions-on-content-you-find"></a>對您找到的內容執行動作

在執行搜尋，並調整視之後下, 一步是執行某些動作與搜尋所傳回的結果。 您可以匯出，並將結果下載到本機電腦，或在您的組織電子郵件攻擊的情況下，您可以從使用者信箱中刪除搜尋的結果。
  
- [匯出內容搜尋的結果](export-search-results.md)和下載到本機電腦 
    
- [搜尋並刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)，例如內容的病毒、 危險附件或網路釣魚郵件的郵件 
    
- [將報表匯出](export-a-content-search-report.md)結果相關的內容搜尋，而不將匯出的實際的結果 
    
- 當您匯出搜尋結果時，[[增加的下載速度](increase-download-speeds-when-exporting-ediscovery-results.md) 
    
## <a name="learn-more-about-content-search"></a>深入了解內容搜尋

內容搜尋很容易使用，但是它也是功能強大的工具。 幕後，有很多程度。 多您知道其相關資訊，並了解其行為，以及其限制，更順利就會使用它適合貴組織的搜尋和調查需求。 了解：
  
- [已局部編製索引 Exchange 和 SharePoint 中的項目](partially-indexed-items-in-content-search.md)，以及如何包含或排除它們，當您匯出及下載搜尋結果 
    
- [調查已局部編製索引的項目](investigating-partially-indexed-items-in-ediscovery.md)，並判斷您的組織暴露 
    
- [限制內容搜尋 」 工具](limits-for-content-search.md)，例如，您可以一次執行搜尋的最大數目以及您可以在單一搜尋中包含的內容位置的最大數目 
    
- [估計與實際搜尋結果](differences-between-estimated-and-actual-ediscovery-search-results.md)和原因的原因可能有其當您匯出及下載搜尋結果之間的差異 
    
- 當您匯出搜尋結果的電子郵件訊息時，您可以啟用的[搜尋結果中的重複資料刪除](de-duplication-in-ediscovery-search-results.md) 
    
## <a name="use-scripts-for-advanced-scenarios"></a>在進階案例中使用指令碼

有時候，您必須執行更進階、 複雜，且重複的內容搜尋工作。 在這些情況下，很容易且快速使用安全性 & 合規性中心中的 PowerShell 命令。 為了能夠更容易，我們已建立了數個安全性 & 合規性中心 PowerShell 指令碼，以協助您完成複雜的內容搜尋相關工作。
  
- [搜尋特定信箱和站台資料夾](use-content-search-for-targeted-collections.md)（稱為 「*目標集合*） 時您確信回應大小寫的項目位於該資料夾 
    
- [搜尋的信箱和 OneDrive 位置](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)的使用者清單 
    
- [建立、 回報及刪除多個搜尋](create-report-on-and-delete-multiple-content-searches.md)以快速且更有效地識別及 cull 搜尋資料 
    
- [複製內容搜尋](clone-a-content-search.md)，並快速比較在相同的內容位置; 上執行不同的關鍵字搜尋查詢的結果或使用指令碼以節省時間不會察覺到重新輸入大量內容的位置，當您建立新的搜尋 
    

