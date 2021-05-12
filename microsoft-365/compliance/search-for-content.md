---
title: 搜尋內容
f1.keywords:
- NOCSH
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
description: 使用安全性 & 合規性中心的內容搜尋 eDiscovery 工具，可在商務用 Skype 中，以快速找到 Exchange 信箱中的電子郵件、SharePoint 網站中的檔，以及 OneDrive 位置和立即訊息交談。
ms.openlocfilehash: 80234a512d13deda29a61073bec62990d135f30e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333683"
---
# <a name="search-for-content-using-the-content-search-tool"></a>使用內容搜尋工具搜尋內容

使用安全性 & 合規性中心的內容搜尋工具，在商務用 Skype 中的 Exchange 信箱、SharePoint 網站中的檔、OneDrive 位置及立即訊息交談中，快速尋找電子郵件。 您可以使用內容搜尋工具，在 Microsoft Teams 和 Microsoft 365 群組等共同作業工具中搜尋電子郵件、檔和立即訊息交談。
  
## <a name="search-for-content"></a>搜尋內容

第一步是開始使用內容搜尋工具來選擇要搜尋的內容位置，並設定關鍵字查詢以搜尋特定專案。 或者，您可以只保留查詢空白，並傳回目標位置中的所有專案。
  
- [建立並執行](content-search.md) 內容搜尋

- [功能參考] 內容搜尋 (content-search-reference.md) 

- [建立搜尋查詢和使用條件](keyword-queries-and-search-conditions.md) 以縮小搜尋範圍 

- [設定搜尋許可權篩選](permissions-filtering-for-content-search.md) ，使 eDiscovery 管理員只會搜尋組織中的信箱或網站的子集 

- [執行識別碼清單搜尋](csv-file-for-an-id-list-content-search.md) 以搜尋特定的電子郵件 

- 在 Microsoft 365 中搜尋內部部署使用者的[雲端架構信箱](search-cloud-based-mailboxes-for-on-premises-users.md)

- 查看搜尋結果的[關鍵字統計資料](view-keyword-statistics-for-content-search.md)，然後在必要時精煉查詢

- 搜尋貴組織已匯入至 Microsoft 365 的[協力廠商資料](use-content-search-to-search-third-party-data-that-was-imported.md)

- [大量編輯](bulk-edit-content-searches.md) 查詢和內容位置以進行多個搜尋

- [重試內容搜尋](retry-failed-content-search.md) 以解決內容位置錯誤

- [保留密件副本](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) 收件者，以便進行搜尋 

## <a name="perform-actions-on-content-you-find"></a>對所找到的內容執行動作

在您執行搜尋並視需要加以調整之後，下一步是針對搜尋傳回的結果執行某些動作。 您可以將結果匯出並下載到您的本機電腦上，或在組織的電子郵件攻擊案例中，從使用者信箱中刪除搜尋結果。
  
- [匯出內容搜尋的結果](export-search-results.md) ，並將其下載到您的本機電腦 

- [搜尋並刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md) ，例如內容為病毒、危險附件或網路釣魚郵件的郵件

- [匯出](export-a-content-search-report.md) 內容搜尋結果的報告，但不匯出實際結果 

## <a name="learn-more-about-content-search"></a>深入瞭解內容搜尋

內容搜尋很容易使用，但也是功能強大的工具。 在幕後，有許多事情會發生。 您對它的瞭解越多，並瞭解其行為及其限制，您就能更順利地使用它來滿足您組織的搜尋和調查需求。 深入瞭解：
  
- [Exchange 和 SharePoint 中已部分索引的專案](partially-indexed-items-in-content-search.md)，以及當您匯出及下載搜尋結果時要包含或排除的專案

- [調查已部分索引的專案](investigating-partially-indexed-items-in-ediscovery.md) ，並決定貴組織對它們的危險性

- [內容搜尋工具的限制](limits-for-content-search.md)，例如，您可以一次執行的搜尋數目上限，以及可以包含在單一搜尋中的最大內容位置數目。

- 當您匯出及下載搜尋結果時，[預估和實際搜尋結果](differences-between-estimated-and-actual-ediscovery-search-results.md)的原因可能有差異。

- 當您匯出搜尋結果的電子郵件時，您可以啟用的[搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除

## <a name="use-scripts-for-advanced-scenarios"></a>使用腳本進行高級案例

有時候，您必須執行更高級、複雜和重複的內容搜尋工作。 在這些情況下，在安全性 & 規範中心使用 PowerShell 命令會變得更輕鬆快捷。 為了簡化這項作業，我們已建立了許多安全性 & 合規性中心 PowerShell 腳本，協助您完成複雜的內容搜尋相關工作。
  
- [搜尋特定的信箱和網站資料夾](use-content-search-for-targeted-collections.md) (稱為 * 目標集合) 當您確信回應案例的專案位於該資料夾中時

- [在信箱和 OneDrive 位置搜尋](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)使用者清單 

- [建立、報告和刪除多個搜尋](create-report-on-and-delete-multiple-content-searches.md) ，以快速且有效地識別及挑選搜尋資料 

- [複製內容搜尋](clone-a-content-search.md) 並快速比較不同關鍵字搜尋查詢的結果在相同的內容位置上執行;或者，您可以使用腳本，在您建立新的搜尋時不必重新輸入大量的內容位置，以節省時間