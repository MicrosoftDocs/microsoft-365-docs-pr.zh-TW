---
title: 管理 Advanced eDiscovery 中的工作
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
description: Advanced eDiscovery 工作可協助您追蹤長時間執行程式的狀態，以執行各種 Advanced eDiscovery 任務。
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471076"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>管理 Advanced eDiscovery 中的工作

以下是工作 (的清單，其中通常是 Advanced eDiscovery 中案例的 [**作業**] 索引標籤上追蹤的執行時間長的處理常式) 。 使用和管理案例時，使用者動作會觸發這些工作。

| 工作類型            | 描述     |
| :----------------- | :----------     |
|將資料新增至審閱集 | 使用者新增集合至審閱集。 此工作包含兩個子工作： </br>• **Export** -會產生集合中的專案清單。 </br>•**攝取 & 索引**-集合中符合搜尋查詢的專案會複製到 Azure 儲存體位置 (在稱為 *攝取*) 的程式中，然後重新編制索引 Azure 儲存體位置中的專案。 當查詢及分析資料集中的專案時，會使用這個新的索引。 </br></br>如需詳細資訊，請參閱 [將搜尋結果新增至審閱集](add-data-to-review-set.md)。 |
|將資料新增至另一個考核集 | 使用者在相同的情況下，從一部審閱集將檔新增至不同的審閱集。 如需詳細資訊，請參閱 [從另一個複查集新增資料至審閱集](add-data-to-review-set-from-another-review-set.md)。|
|將非 Microsoft 365 資料新增至審閱集 | 使用者將非 Microsoft 365 資料上傳至審閱集。 在此程式中，資料也會編制索引。 例如，從內部部署檔案伺服器或用戶端電腦上的檔案上傳至審閱集。 如需詳細資訊，請參閱[Load 非 Microsoft 365 data into a a 審校 set](load-non-office-365-data-into-a-review-set.md)。| 
|將修正的資料新增至審閱集 | 會修正具有處理錯誤的資料，並將其重新載入回評審集。 如需詳細資訊，請參閱：</br>• [處理資料時的錯誤修正](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [單一專案錯誤修正](single-item-error-remediation.md)| 
|比較負載設定 | 使用者查看審閱集中不同的負載集之間的差異。 載入集合是將資料新增至檢閱集的執行個體。 例如，如果您將兩個不同搜尋的結果新增至相同的審閱集，每個搜尋會代表一個負載集。 |
|交談重建|當使用者將搜尋結果新增至交談複查集時，Microsoft Teams 中的立即訊息交談 (也稱為「) *執行緒交談*」，以在 PDF 檔案中重建。 當使用者按一下 [動作] 時，也會觸發此工作，> 在評論集中 **建立交談 pdf** 。 如需詳細資訊，請參閱[Advanced eDiscovery 中的審閱交談](conversation-review-sets.md)。
|將 redacted 檔轉換成 PDF|在使用者 annotates 審閱集中的檔並編寫一部分之後，他們可以選擇將 redacted 檔轉換成 PDF 檔案。 這可確保在匯出檔以進行簡報時，redacted 部分不會顯示。 如需詳細資訊，請參閱 [View documents in 審閱集](annotating-and-redacting-documents.md)。 |
|預估搜尋結果 | 在使用者建立及執行或重新執行草稿收集之後，搜尋工具會搜尋索引中符合搜尋查詢的專案，並準備包含搜尋的所有專案的數目和總大小，以及搜尋的資料來源數目。  如需詳細資訊，請參閱 [收集案例的資料](collecting-data-for-ediscovery.md)。 | 
|準備要匯出的資料 | 使用者從審閱集匯出檔。 匯出程式完成後，即可將匯出的資料下載到本機電腦。 如需詳細資訊，請參閱 [匯出案例資料](exporting-data-ediscover20.md)。 | 
|準備進行錯誤解決 |當使用者在案例的 [**處理**] 索引標籤上選取檔案並在錯誤視圖中建立新的錯誤修正時，程式中的第一個步驟是將具有處理錯誤的檔案上傳至 Microsoft 雲端中的 Azure 儲存體位置。 此工作追蹤上傳程式的進度。 如需錯誤修正工作流程的詳細資訊，請參閱 [在處理資料時進行錯誤修正](error-remediation-when-processing-data-in-advanced-ediscovery.md)。 | 
|準備搜尋預覽 | 在使用者建立並執行新的草稿集合 (或重新執行現有的草稿集合) 時，搜尋工具會準備出項目的範例子集， (符合可以預覽的搜尋查詢) 。 預覽搜尋結果可協助您決定搜尋的效能。  如需詳細資訊，請參閱 [收集案例的資料](collecting-data-for-ediscovery.md#view-search-results-and-statistics)。 | 
|重新索引保管人資料 | 當您將系統管理員新增至案例時，系統管理員所選取資料來源中的所有部分索引項目目都會由稱為「 *高級索引*」的處理常式重新編制索引。 當您按一下案例的 [**處理**] 索引標籤上的 [**更新索引] 索引** 標籤，以及在 [保管人屬性] 飛出頁面上更新特定保管人的索引時，也會觸發此工作。 如需詳細資訊，請參閱 [Advanced a 的保管人資料索引](indexing-custodian-data.md)。
|執行分析 | 使用者透過執行 Advanced eDiscovery 分析工具（例如接近重複偵測、電子郵件執行緒分析和主題分析）來分析複查集中的資料。 如需詳細資訊，請參閱 [分析審閱集中的資料](analyzing-data-in-review-set.md)。 | 
|標記檔 | 當使用者在審閱集中審閱檔時，當使用者按一下 [**標記] 面板** 中的 [**開始標記] 工作** 時，就會觸發此工作。 使用者可以在審閱集內重新標記檔，然後在 [view 檔] 面板中大量選取檔，以啟動此工作。 如需詳細資訊，請參閱 [標記檔中的審閱集](tagging-documents.md)。 | 
|||

## <a name="job-status"></a>工作狀態

下表說明工作的不同狀態狀態。

| 狀態           | 描述     |
| :----------------- | :----------     |
| 已提交 | 已建立新的工作。  工作提交日期和時間會顯示在 [**工作**] 索引標籤上的 [**建立**] 欄中。 |
| 提交失敗 | 工作提交失敗。  您應嘗試重新執行觸發工作的動作。 |
| 進行中。 | 工作正在進行中，您可以在 [ **工作** ] 索引標籤中監控工作進度。 |
| 成功 | 工作順利完成。 工作已完成的日期和時間會顯示在 [**工作**] 索引標籤上的 [**完成**] 欄中。 |
| 部分成功 | 工作成功。 當工作未找到任何已部分編制索引的資料 (也稱為未編制索引的 *資料*) 部分的保管人資料來源中時，通常會傳回此狀態。  |
| 失敗 | 工作失敗。  您應嘗試重新執行觸發工作的動作。 如果作業失敗第二次，我們建議您聯繫 Microsoft 支援部門，並提供工作的支援資訊。 |
|||
