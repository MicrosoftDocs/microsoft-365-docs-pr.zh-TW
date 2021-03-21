---
title: 在稽核記錄中搜尋電子文件探索活動
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 瞭解當指派電子檔探索許可權的使用者在安全性 & 合規性中心執行內容搜尋和核心 eDiscovery 工作時所記錄的事件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7324cf610373202cdc24f48c23dc0647d4a21ea8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922485"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>在稽核記錄中搜尋電子文件探索活動

在安全性 & 合規性中心或執行對應 PowerShell Cmdlet 的核心 eDiscovery 和高級 eDiscovery) 中，可 (內容搜尋和 eDiscovery 相關的活動，並記錄在審核記錄檔中。 當系統管理員或 eDiscovery 管理員 (或任何已指派 eDiscovery 許可權的使用者) 在安全性 & 合規性中心執行下列內容搜尋及核心 eDiscovery 工作時，會記錄事件。
  
- 建立及管理核心和高級 eDiscovery 案例

- 建立、開啟及編輯 [內容搜尋]

- 執行 [內容搜尋] 動作，例如預覽、匯出及刪除搜尋結果

- 在高級電子檔探索中管理保管人和審查集

- 設定 [內容搜尋] 的權限篩選

- 管理電子文件探索系統管理員角色

> [!IMPORTANT]
> 本文所述的活動只是使用安全性 & 規範中心所執行的 eDiscovery 工作結果。 在 Exchange Online 中使用 In-Place eDiscovery 工具或 SharePoint Online 中的 eDiscovery 中心所執行的 eDiscovery 工作不會包含在內。 
  
如需搜尋審核記錄、所需許可權及匯出搜尋結果的詳細資訊，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何搜尋及流覽 eDiscovery 活動

目前，您必須在審計記錄中執行一些特定工作以查看 eDiscovery 活動。 方法如下。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。

2. 使用您的公司或學校帳戶登入。

3. 在左窗格中，按一下 [ **搜尋**]，然後按一下 [ **審核記錄搜尋**]。

4. 在 [ **活動** ] 下拉式清單中，于 [ **eDiscovery 活動** ] 或 [ **高級 eDiscovery 活動**] 底下，按一下一或多個要搜尋的活動。

    > [!NOTE]
    > [ **活動** ] 下拉式清單中也包含一組名為「 **eDiscovery Cmdlet** 」的活動，會傳回 Cmdlet 審核記錄檔中的記錄。
  
5. 選取 [日期和時間範圍]，以顯示在該期間內發生的 eDiscovery 事件。 

6. 在 [ **使用者** ] 方塊中，選取一或多個要顯示搜尋結果的使用者。 將此方塊保留空白，可傳回所有使用者的專案。

7. 按一下 **[搜尋]** 以使用您的搜尋準則執行搜尋。

8. 搜尋結果顯示後，您可以按一下 [ **篩選結果** ] 以篩選或排序所產生的活動記錄。 不幸的是，您無法使用篩選來明確排除某些活動。 

9. 若要查看活動的詳細資料，請按一下搜尋結果清單中的活動記錄。 

    隨即會顯示 [飛出] 頁面，其中包含事件記錄中的詳細 **內容** 。 若要顯示其他詳細資料，請按一下 [ **詳細資訊**]。 如需這些屬性的說明，請參閱 [eDiscovery 活動的詳細](#detailed-properties-for-ediscovery-activities) 內容一節。

10. 如有需要，您可以將審核記錄搜尋結果匯出至 CSV 檔案，然後使用 Excel Power Query 功能格式化及篩選這些記錄。 如需詳細資訊，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md)。

## <a name="ediscovery-activities"></a>電子文件探索活動

下表說明當系統管理員或 eDiscovery 管理員使用安全性 & 合規性中心執行 eDiscovery 相關的活動時，或在安全性 & 規範中心 PowerShell 中執行對應指令程式時所記錄的內容搜尋和核心 eDiscovery 活動。 另外請注意，當您搜尋此清單中的活動時，會傳回在 [高級] 中執行的一些活動。
  
> [!NOTE]
> 本節所述的 eDiscovery 活動提供與下一節所述 eDiscovery Cmdlet 活動類似的資訊。 我們建議您使用本節所述的 eDiscovery 活動，因為它們會出現在審計記錄搜尋結果的30分鐘內。 在審計記錄搜尋結果中顯示 eDiscovery Cmdlet 活動最多需要24小時。 
  
|**易記名稱**|**作業**|**對應 Cmdlet**|**描述**|
|:-----|:-----|:-----|:-----|
|新增成員至 eDiscovery 案例  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |使用者已新增為 eDiscovery 案例的成員。 就像是案例的成員，使用者可以根據是否已獲指派必要許可權來執行各種案例相關的任務。  <br/> |
|變更的內容搜尋  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |已變更現有的內容搜尋。 變更可包括新增或移除內容位置或編輯搜尋查詢。  <br/> |
|變更 eDiscovery 系統管理員成員資格  <br/> |CaseAdminUpdated  <br/> |更新-eDiscoveryCaseAdmin  <br/> |您組織中的 eDiscovery 管理員清單已變更。 當 eDiscovery 管理員的清單取代為一組新的使用者時，就會記錄此活動。 如果新增或移除單一使用者，就會記錄 CaseAdminAdded 作業。  <br/> |
|已變更的 eDiscovery 案例  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |電子檔探索案例已變更。 變更包括關閉開啟案例或開啟關閉的案例。  <br/> |
|變更 eDiscovery 案例成員資格  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |電子檔探索案例的成員資格清單已變更。 當所有成員都取代為一組新的使用者時，就會記錄此活動。 如果新增或移除單一成員，則會記錄 CaseMemberAdded 或 CaseMemberRemoved 作業。  <br/> |
|變更的搜尋許可權篩選  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |已變更搜尋許可權篩選。  <br/> |
|已變更的 eDiscovery 案例保留變更搜尋查詢  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |已變更與 eDiscovery 案例相關聯的查詢型保留。 可能的變更包括編輯查詢或日期範圍以進行查詢型保留。  <br/> |
|已下載內容搜尋預覽專案  <br/> |PreviewItemDownloaded  <br/> |N/A  <br/> |使用者透過按一下 [ **下載原始專案** ] 連結) 預覽搜尋結果，將專案下載到本機電腦 (。  <br/> |
|列出的內容搜尋預覽專案  <br/> |PreviewItemListed  <br/> |N/A  <br/> |使用者按一下 [ **預覽搜尋結果** ] 來顯示 [預覽搜尋結果] 頁面，該頁面會從內容搜尋結果列出最多1000個專案。  <br/> |
|已查看內容搜尋預覽專案  <br/> |PreviewItemRendered  <br/> |N/A  <br/> |EDiscovery 管理員會在預覽搜尋結果時按一下以查看專案。  <br/> |
|建立內容搜尋  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |已建立新的內容搜尋。  <br/> |
|已建立 eDiscovery 系統管理員  <br/> |CaseAdminAdded  <br/> |載入 eDiscoveryCaseAdmin  <br/> |使用者已新增為組織中的 eDiscovery 系統管理員。  <br/> |
|建立的 eDiscovery 案例  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |已建立 eDiscovery 案例。 當案例建立時，您只需要為其命名。 其他與案例相關的工作，例如新增成員、建立保留，以及建立與案例相關聯的內容搜尋會導致記錄其他事件。  <br/> |
|已建立搜尋許可權篩選  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |已建立搜尋許可權篩選。  <br/> |
|針對 eDiscovery 案例保留建立搜尋查詢  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |已建立與 eDiscovery 案例相關聯的查詢型保留。  <br/> |
|刪除的內容搜尋  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |已刪除現有的內容搜尋。  <br/> |
|刪除的 eDiscovery 系統管理員  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |已從您的組織中刪除 eDiscovery 系統管理員。  <br/> |
|已刪除的 eDiscovery 案例  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |電子檔探索案例已刪除。 在刪除案例之前，必須先移除與案例相關聯的任何保留。  <br/> |
|已刪除的搜尋許可權篩選  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |已刪除搜尋許可權篩選。  <br/> |
|已刪除電子檔探索案例保留的搜尋查詢  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |已刪除與 eDiscovery 案例相關聯的查詢型保留。 從保留中移除查詢通常是刪除保留的結果。 當刪除保留或保留查詢時，就會釋放保留的內容位置。  <br/> |
|下載內容搜尋的匯出  <br/> |SearchExportDownloaded  <br/> |N/A  <br/> |使用者將內容搜尋的結果下載到本機電腦。 在下載搜尋結果之前，必須先啟動「 **內容搜尋** 」活動的「匯出」。  <br/> |
|預覽內容搜尋的結果  <br/> |SearchPreviewed  <br/> |N/A  <br/> |使用者預覽內容搜尋的結果。  <br/> |
|已清除的內容搜尋結果  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |使用者透過執行 **New-ComplianceSearchAction-Purge** 命令來清除內容搜尋的結果。  <br/> |
|已移除內容搜尋的分析  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |「內容搜尋準備動作」 (，可為已刪除的「高級 eDiscovery) 準備搜尋結果。 如果準備動作尚未過去兩周，請從 Microsoft Azure 儲存體區域中刪除準備好進行高級 eDiscovery 的搜尋結果。 如果準備動作超過2周，則此事件表示只刪除對應的準備動作。  <br/> |
|已移除內容搜尋的匯出  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |已刪除內容搜尋匯出動作。 如果匯出動作不是兩周以前，則已刪除上傳至 Microsoft Azure 儲存體區域的搜尋結果。 如果匯出動作超過2周，則此事件表示只刪除對應的「匯出」動作。  <br/> |
|已從電子檔探索案例中移除成員  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |已移除使用者，成為 eDiscovery 案例的成員。  <br/> |
|移除內容搜尋的預覽結果  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |已刪除內容搜尋預覽動作。  <br/> |
|已移除在內容搜尋中執行的清除動作  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |已刪除內容搜尋清除動作。  <br/> |
|已移除搜尋報告  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |已刪除「內容搜尋匯出報告」動作。  <br/> |
|開始分析內容搜尋  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |內容搜尋的結果是準備好在高級 eDiscovery 中進行分析。  <br/> |
|已開始內容搜尋  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |已開始內容搜尋。 當您使用安全性 & 規範中心 GUI 建立或變更內容搜尋時，會自動啟動搜尋。 如果您使用 **New-ComplianceSearch** 或 **Set-ComplianceSearch** Cmdlet 來建立或變更搜尋，則必須執行 **Start-ComplianceSearch** 指令程式，以啟動搜尋。  <br/> |
|已開始匯出內容搜尋  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |使用者匯出內容搜尋的結果。  <br/> |
|已開始匯出報告  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |使用者已匯出內容搜尋報告。  <br/> |
|已停止內容搜尋  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |使用者停止內容搜尋。  <br/> |
|(無)|CaseViewed|Get-ComplianceCase|使用者在安全性與合規性中心的「 **eDiscovery** 」頁面上，或執行 Cmdlet 查看案例清單。|
|(無)|SearchViewed|Get-ComplianceSearch|使用者在安全性與合規性中心的 [搜尋] 索引標籤上，或執行 Cmdlet，在 [ **搜尋** ] 索引標籤) 上查看的內容搜尋清單 (。 當使用者透過按一下案例) 中的 [ **搜尋** ] 索引標籤或執行 **Get-ComplianceSearch 案例** ] 命令，來查看與 eDiscovery (案例相關聯的內容搜尋清單時，也會記錄此活動。|
|(無)|ViewedSearchExported|Get-ComplianceSearchAction 匯出|使用者可以查看 [安全性與合規性中心] 中的 [ **匯出** ] 索引標籤) 上的內容搜尋匯出 (工作清單，或執行 Cmdlet。 當使用者在) 案例中的 [匯出] 索引標籤上，或執行 [ **Get-ComplianceSearchAction-Case 匯出**] 命令，在 [**匯出**] 索引標籤中查看匯出 (工作清單時，也會記錄此活動。|
|(無)|ViewedSearchPreviewed|Get-ComplianceSearchAction 預覽|使用者在安全性與合規性中心或執行 Cmdlet 預覽內容搜尋的結果。|
|||||
  
## <a name="advanced-ediscovery-activities"></a>進階電子文件探索活動

下表說明記錄在審核記錄中的高級 eDiscovery 活動。 這些 (活動除了相關的 eDiscovery 活動之外，還可用於協助您追蹤高級 eDiscovery 案例中的活動進展。

|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|已將資料新增至另一個檢閱集|AddWorkingSetQueryToWorkingSet|使用者已將一個檢閱集中的文件新增至不同檢閱集。|
|已將資料新增至檢閱集|AddQueryToWorkingSet|使用者已將搜尋結果從與進階電子文件探索案例相關的內容搜尋新增至檢閱集。|
|已將非 Microsoft 365 的資料新增至檢閱集|AddNonOffice365DataToWorkingSet|使用者已將非 Microsoft 365 的資料新增至檢閱集。|
|已將修復的文件新增至檢閱集|AddRemediatedData|使用者將已修正索引錯誤的文件上傳至檢閱集。|
|已分析檢閱集中的資料|RunAlgo|使用者已對檢閱集中的文件執行分析。|
|已標註檢閱集中的文件|AnnotateDocument|使用者已標註檢閱集中的文件。 標註包含校訂文件中的內容。|
|比較載入集合|LoadComparisonJob|使用者比較了檢閱集中的兩個不同載入集合。 載入集合會在案例相關內容搜尋中的資料新增至檢閱集後建立。|
|已將校訂後的文件轉換為 PDF|BurnJob|使用者已將檢閱集中所有已校訂的文件轉換為 PDF 檔案。|
|已建立檢閱集|CreateWorkingSet|使用者已建立檢閱集。|
|已建立檢閱集搜尋|CreateWorkingSetSearch|使用者已建立搜尋查詢來搜尋檢閱集中的文件。|
|已建立標籤|CreateTag|使用者已在檢閱集中建立標籤群組。 標籤群組可以包含一個或多個子標籤。 這些標籤可用來標記檢閱集中的文件。|
|已刪除檢閱集搜尋|DeleteWorkingSetSearch|使用者已刪除檢閱集中的搜尋查詢。|
|已刪除標籤|DeleteTag|使用者已在檢閱集中刪除標籤或標籤群組。|
|已下載文件|DownloadDocument|使用者已從檢閱集下載文件。|
|已編輯標籤|UpdateTag|使用者已變更檢閱集中的標籤。|
|已從檢閱集匯出文件|ExportJob|使用者已從檢閱集匯出文件。|
|已修改案例設定|UpdateCaseSettings|使用者已修改案例的設定。 案例設定包括案例資訊、存取權限及控制搜尋和分析行為的設定。|
|已修改檢閱集搜尋|UpdateWorkingSetSearch|使用者已編輯檢閱集中的搜尋查詢。|
|已預覽檢閱集搜尋|PreviewWorkingSetSearch|使用者已預覽檢閱集中的搜尋查詢結果。|
|已修復錯誤的文件|ErrorRemediationJob|使用者已修正包含索引錯誤的檔案。|
|已標記文件|TagFiles|使用者已標記檢閱集中的文件。|
|已標記查詢結果|TagJob|使用者已標記檢閱集中所有符合搜尋查詢準則的文件。|
|已檢視檢閱集中的文件|ViewDocument|使用者已檢視檢閱集中的文件。|
|||

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery Cmdlet 活動

下表列出當系統管理員或使用者利用安全性 & 合規性中心，或是在已連線到組織之安全性 & 合規性中心的遠端 PowerShell 中執行對應的指令程式時，所記錄的 Cmdlet 審核記錄記錄。 「審計記錄」記錄中的詳細資訊與此表中所列的指令程式活動和上一節所述 eDiscovery 活動的不同。
  
如先前所述，在審計記錄搜尋結果中顯示 eDiscovery Cmdlet 活動時，最多需要24小時的時間。
  
> [!TIP]
> 下 **表的 [作業] 欄中** 的指令程式連結至 TechNet 的對應 Cmdlet 說明主題。 請移至 Cmdlet 說明主題，以取得每個 Cmdlet 可用參數的描述。 與 Cmdlet 搭配使用的參數和參數值，會包含在每個已記錄的 eDiscovery Cmdlet 活動的「審核記錄」專案中。 
  
|**易記名稱**|**Operation (Cmdlet)**|**描述**|
|:-----|:-----|:-----|
|在 eDiscovery 案例中建立保留  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |已針對 eDiscovery 案例建立保留。 您可以使用或不指定內容來源來建立保留。 如果指定內容來源，將會在審計記錄專案中加以識別。  <br/> |
|已從 eDiscovery 案例刪除保留  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |已刪除與 eDiscovery 案例相關聯的保留。 刪除保留會釋放保留中的所有內容位置。 刪除保留也會導致刪除與保留相關聯的案例保留規則 (請參閱下列 **Remove-CaseHoldRule**) 。  <br/> |
|在 eDiscovery 案例中變更了保留  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |已變更與 eDiscovery 相關聯的保留。 可能的變更包括新增或移除內容位置或關閉 (停用) 保留。  <br/> |
|針對 eDiscovery 案例保留建立搜尋查詢  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |已建立與 eDiscovery 案例相關聯的查詢型保留。  <br/> |
|已刪除電子檔探索案例保留的搜尋查詢  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |已刪除與 eDiscovery 案例相關聯的查詢型保留。 從保留中移除查詢通常是刪除保留的結果。 當刪除保留或保留查詢時，就會釋放保留的內容位置。  <br/> |
|已變更的 eDiscovery 案例保留變更搜尋查詢  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |已變更與 eDiscovery 案例相關聯的查詢型保留。 可能的變更包括編輯查詢或日期範圍以進行查詢型保留。  <br/> |
|建立的 eDiscovery 案例  <br/> |[新 Get-compliancecase](/powershell/module/exchange/new-compliancecase) <br/> |已建立 eDiscovery 案例。 當案例建立時，您只需要為其命名。 其他與案例相關的工作，例如新增成員、建立保留，以及建立與案例相關聯的內容搜尋會導致記錄其他事件。  <br/> |
|已刪除的 eDiscovery 案例  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |電子檔探索案例已刪除。 在刪除案例之前，必須先移除與案例相關聯的任何保留。  <br/> |
|已變更的 eDiscovery 案例  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |電子檔探索案例已變更。 變更包括關閉開啟案例或開啟關閉的案例。  <br/> |
|新增成員至 eDiscovery 案例  <br/> |[載入 ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |使用者已新增為 eDiscovery 案例的成員。 就像是案例的成員，使用者可以根據是否已獲指派必要許可權來執行各種案例相關的任務。  <br/> |
|已從電子檔探索案例中移除成員  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |已移除使用者，成為 eDiscovery 案例的成員。  <br/> |
|變更 eDiscovery 案例成員資格  <br/> |[更新-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |電子檔探索案例的成員資格清單已變更。 當所有成員都取代為一組新的使用者時，就會記錄此活動。 如果新增或移除單一成員，將會記錄 **ComplianceCaseMember** 或 **Remove-ComplianceCaseMember** 作業。  <br/> |
|建立內容搜尋  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |已建立新的內容搜尋。  <br/> |
|刪除的內容搜尋  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |已刪除現有的內容搜尋。  <br/> |
|變更的內容搜尋  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |已變更現有的內容搜尋。 變更可包括新增或移除搜尋及編輯搜尋查詢的內容位置。  <br/> |
|已開始內容搜尋  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |已開始內容搜尋。 當您使用安全性 & 規範中心 GUI 建立或變更內容搜尋時，會自動啟動搜尋。 如果您使用 **New-ComplianceSearch** 或 **Set-ComplianceSearch** Cmdlet 來建立或變更搜尋，則必須執行 **Start-ComplianceSearch** 指令程式，以啟動搜尋。  <br/> |
|已停止內容搜尋  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |已停止執行的內容搜尋。  <br/> |
|建立內容搜尋動作  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |已建立內容搜尋動作。 內容搜尋動作包括預覽搜尋結果、匯出搜尋結果、在高級 eDiscovery 中準備搜尋結果以進行分析，以及永久刪除符合內容搜尋之搜尋準則的專案。  <br/> |
|已刪除內容搜尋動作  <br/> |[Remove-New-compliancesearchaction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |已刪除內容搜尋動作。  <br/> |
|已建立搜尋許可權篩選  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |已建立搜尋許可權篩選。  <br/> |
|已刪除的搜尋許可權篩選  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |已刪除搜尋許可權篩選。  <br/> |
|變更的搜尋許可權篩選  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |已變更搜尋許可權篩選。  <br/> |
|已建立 eDiscovery 系統管理員  <br/> |[載入 eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |使用者已新增為組織中的 eDiscovery 系統管理員。  <br/> |
|刪除的 eDiscovery 系統管理員  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |已從您的組織中刪除 eDiscovery 系統管理員。  <br/> |
|變更 eDiscovery 系統管理員成員資格  <br/> |[更新-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |您組織中的 eDiscovery 管理員清單已變更。 當 eDiscovery 管理員的清單取代為一組新的使用者時，就會記錄此活動。 新增或移除單一使用者時，會記錄 **eDiscoveryCaseAdmin** 或 **Remove-eDiscoveryCaseAdmin** 作業。  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>EDiscovery 活動的詳細屬性

下表說明當您按一下搜尋結果中所列 eDiscovery 活動的 [**詳細** 資料] 頁面上的 [**詳細資訊**] 時所包含的屬性。 當您匯出「審核記錄」搜尋結果時，這些屬性也會包含在 CSV 檔案中。 EDiscovery 活動的審計記錄記錄不會包含下列每個詳細的屬性。 
  
> [!TIP]
> 當您匯出搜尋結果時，CSV 檔案會包含一個名為 **Detail** 的欄，其中包含多重值屬性中下表所述的詳細屬性。 您可以使用 Excel 中的 Power Query 功能，將此欄分割成多個欄，使每個屬性都有自己的資料行。 這可讓您排序和篩選其中一個或多個屬性。 如需詳細資訊，請參閱 [搜尋審計記錄](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)檔中的「將搜尋結果匯出至檔案」一節。 
  
|**屬性**|**描述**|
|:-----|:-----|
|案例  <br/> |已建立、變更或刪除的 eDiscovery 案例的身分識別 (GUID) 。  <br/> |
|ClientApplication  <br/> |eDiscovery Cmdlet 活動的值為此屬性的 **EMC** 。 這表示使用安全性 & 規範中心 GUI 或在 PowerShell 中執行 Cmdlet 所執行的活動。  <br/> |
|ClientIP  <br/> |記錄活動時所使用之裝置的 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。  <br/> |
|ClientRequestId  <br/> | 針對 eDiscovery 活動，此屬性通常是空白的。  <br/> |
|CmdletVersion  <br/> |組織中所執行的安全性 & 規範中心版本的組建編號。  <br/> |
|CreationTime  <br/> |當 eDiscovery 活動完成時，在協調世界時 (UTC) 的日期和時間。  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 組織的名稱。  <br/> |
|ExchangeLocations  <br/> |在 eDiscovery 案例中，包含在內容搜尋中或置於保留狀態的 Exchange Online 信箱。  <br/> |
|排除  <br/> |從內容搜尋排除的信箱或網站位置，或在 eDiscovery 案例中保留的位置。  <br/> |
|ExtendedProperties  <br/> |內容搜尋、內容搜尋動作或電子檔探索案例中的其他屬性，例如執行活動時所使用的物件 GUID 和對應的指令程式和 Cmdlet 參數。  <br/> |
|識別碼  <br/> |報表專案的識別碼。 識別碼可唯一識別審核記錄專案。  <br/> |
|NonPIIParameters  <br/> | (的參數清單，但沒有任何值與 Operation 屬性中標出的指令程式) 搭配使用。 此屬性所列的參數與 [Parameters] 屬性中列出的參數相同。  <br/> |
|ObjectId  <br/> |物件的 GUID 或名稱 (例如，「內容搜尋」或「eDiscovery 案例」) ，由 Operation 屬性中所列的活動所建立、變更或刪除）。 這個物件也會在審計記錄搜尋結果的 [專案] 欄中識別。  <br/> |
|ObjectType  <br/> |使用者建立、刪除或修改的 eDiscovery 物件類型。例如，內容搜尋動作 (預覽、匯出或清除) 、eDiscovery 案例或內容搜尋。  <br/> |
|作業  <br/> |對應至所執行 eDiscovery 活動的作業名稱。  <br/> |
|OrganizationId  <br/> |Microsoft 365 組織的 GUID。  <br/> |
|參數  <br/> |與對應 Cmdlet 搭配使用之參數的名稱和值。  <br/> |
|PublicFolderLocations  <br/> |在 Exchange Online 中的公用資料夾位置，包含在內容搜尋中，或在 eDiscovery 案例中放入暫止。  <br/> |
|查詢  <br/> |與活動相關聯的搜尋查詢，例如內容搜尋或以查詢為基礎的保留。  <br/> |
|RecordType  <br/> |由 record 指示的作業類型。 值 **18** 表示與 [eDiscovery Cmdlet activity](#ediscovery-cmdlet-activities) 區段中所列之活動相關的事件。 值為 **24** 會指出與 [ [如何搜尋及查看 eDiscovery 活動](#how-to-search-for-and-view-ediscovery-activities) ] 區段中所列之活動相關的事件。  <br/> |
|ResultStatus  <br/> |會指出作業屬性) 中 (指定的動作是否成功。  <br/> |
|SecurityComplianceCenterEventType  <br/> |表示活動為安全性 & 規範中心事件。 此屬性的所有 eDiscovery 活動的值都是 **0** 。  <br/> |
|SharepointLocations  <br/> |在 eDiscovery 案例中，包含在內容搜尋中或置於保留狀態的 SharePoint 線上網站。  <br/> |
|StartTime  <br/> |開始 eDiscovery 活動時，以協調世界時 (UTC) 的日期和時間。  <br/> |
|UserId  <br/> |執行活動的使用者 (在作業屬性) 中指定導致記錄被記錄。 系統帳戶所執行的 eDiscovery 活動記錄 (例如 NT AUTHORITY\SYSTEM) 也會包含在審計記錄檔中。  <br/> |
|UserKey  <br/> |在 UserId 屬性中所識別之使用者的替代識別碼。 針對 eDiscovery 活動，此屬性的值通常與 UserId 屬性相同。  <br/> |
|UserServicePlan  <br/> |您的組織所使用的訂閱。 針對 eDiscovery 活動，此屬性通常是空白的。  <br/> |
|UserType  <br/> |執行作業的使用者類型。 下列值表示使用者類型。  <br/> 0一般使用者。 2組織中的系統管理員。 3 A Microsoft 資料中心系統管理員或資料中心系統帳戶。 4系統帳戶。 5應用程式。 6 A 服務主體。 |
|版本  <br/> |會指出由記錄的操作屬性) 所識別之活動 (的版本號碼。  <br/> |
|工作負載  <br/> |發生活動的 Theservice。 針對 eDiscovery 活動，此值是 **SecurityComplianceCenter**。  <br/> |