---
title: 瞭解 SharePoint 和 OneDrive 的保留功能
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 瞭解保留功能在 SharePoint 以及 OneDrive 中的運作方式。
ms.openlocfilehash: 31ffce3f02e273e771ca1753474bec48b66148bb
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754137"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>瞭解 SharePoint 和 OneDrive 的保留功能

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

本文中的資訊補充了[瞭解保留功能](retention.md)的資訊，因為其資訊涵蓋了 SharePoint 和 OneDrive 專用的資訊。

若為其他工作負載，請參閱：

- [了解 Microsoft Teams 保留](retention-policies-teams.md)
- [了解 Yammer 的保留](retention-policies-yammer.md)
- [了解 Exchange 的保留](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保留與刪除包含的內容

透过應用保留原则或保留標籤，可以保留 SharePoint 或 OneDrive 網站中储存的所有檔案。

可以删除以下檔案：

- 使用保留原则時：文件庫中的所有檔案包括任何自動建立的 SharePoint 文件庫，如 **網站資產** 。
    
- 使用保留標籤時：所有文件庫中的所有檔案，以及根層級不在資料夾中的所有檔案。
    
    當您將[帶有自動套用原則的 KQL 査詢用於保留標籤](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)時，可以使用以下項目排除文件庫：`NOT(DocumentLink:"<URL to document library>")`


## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>保留功能在 SharePoint 以及 [OneDrive] 中的運作方式。

若要支援保留，SharePoint 和 OneDrive 會建立一個 [文件保留庫]（如果沒有的話）。 您可以在網站集合的頂層網站中的 [網站內容]  頁面上檢視此文件庫。 文件保留庫僅供網站集合系統管理員檢視，大部分的使用者都無法檢視。
  
如果有人嘗試變更或刪除已受保留設置規範的文件檔案，在將保留設定套用到檔案時，不論檔案的內容是否已進行變更，都會進行檔案檢查。 如果這是套用原則後的第一次變更，檔案的內容會先被複製到 [文件保留庫]，然後允許使用者變更或刪除原始內容。 您可以將網站集合中的任何內容，複製到 [文件保留庫]，不需套用保留設定。
  
計時器工作會定期清理 [文件保留庫]。 此工作會將 [文件保留庫] 中的所有內容和以內容設有保留設置的所有查詢進行比較。 比其設定的保留期間更舊的內容會從文件保留庫中刪除，以及從原始位置刪除 (如果仍然存在)。 此計時器工作會每隔七天執行一次，這表示要刪除內容最多可能需要七天的時間。
  
這項行為可使用在套用保留原則時已存在的內容。 除外，針對保留原則，任何在納入原則後的新增或建立在網站集合的新內容都將在刪除之後仍將保留。 不過，新內容在第一次編輯時並不會複製到文件保留庫，而只有在刪除時才會。 若要保留檔案的所有版本，您必須開啟[版本設定](#how-retention-works-with-document-versions-in-a-site-collection)。
  
如果使用者嘗試刪除受保留原則保護的文件庫、清單、資料夾或網站，則會收到錯誤。 如果先移動或刪除受到原則保護之資料夾中的檔案，那麼使用者就可以刪除該資料夾。 此外，[文件保留庫] 會在此階段建立，而不是在您建立保留原則或套用保留標籤時建立。 這表示，若要測試原則，您必須先編輯/刪除網站中受保留原則規範、或已套用保留標籤的文件檔案，然後瀏覽至 [文件保留庫] 檢視保留的複本。
  
將保留原則指派至 OneDrive 帳戶或 SharePoint 網站後，內容的路徑會根據保留原則為保留和刪除、僅保留或僅刪除。

當保留設定為保留及刪除時：

![SharePoint 和 OneDrive 中內容生命週期的圖表](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. 若已在保留期間 **修改或刪除內容** ，即會在文件保留庫中建立指派保留原則時即存在之原始內容的複本。 此時，計時器工作會識別保留期間已過期的項目。 這些項目會移到第二階段資源回收筒，並在 93 天結束時永久刪除。 使用者看不到第二階段資源回收筒 (只能看到第一階段資源回收筒)，但網站集合管理員可以檢視並從該處還原內容。

    > [!NOTE]
    > 為了防止意外的資料遺失，我們不再永久刪除保留文件庫中的內容。 相反地，我們只會從資源回收筒中永久刪除內容。因此，來自保留文件庫的所有內容，現在將會移至第二階段資源回收筒。
    
2. **如果未在保留期間修改或刪除內容** ，計時器工作會在保留期間結束時將此內容移至第一階段資源回收筒。 如果使用者從此處刪除內容，或清空此資源回收筒 (也就是清除)，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 系統並未對資源回收筒編製索引，因此無法提供搜尋。 如此一來，電子文件探索搜尋就找不到可放置保留的資源回收筒內容。

當保留設定為僅保留或僅刪除時，內容路徑為保留和刪除的變化：

### <a name="content-paths-for-retain-only-retention-settings"></a>僅保留保留設定的內容路徑

1. 在保留期間， **如果內容已修改或刪除** ：原始文件的複本會在文件保留庫內建立，並保留到保留期間結束時，然後文件保留庫內的複本會移至第二階段資源回收筒，並在 93 天後永久刪除。

2. 在保留期間， **如果未修改或刪除內容** ：保留期間前後沒有任何變化；文件仍會保留在其原始位置。

### <a name="content-paths-for-delete-only-retention-settings"></a>僅刪除保留設定的內容路徑

1. **如果在設定的保留期間刪除內容** ：文件會移至第一階段資源回收筒。 如果使用者從此處刪除文件，或清空此資源回收筒，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 如果在設定的期間修改內容，則在保留期間後會遵循相同的刪除路徑。

2. **如果未在設定的保留期間刪除內容** ：在設定的保留期間結束時，系統會將文件移至第一階段資源回收筒。 如果使用者從此處刪除文件，或清空此資源回收筒 (也就是清除)，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 系統並未對資源回收筒編製索引，因此無法提供搜尋。 如此一來，電子文件探索搜尋就找不到可放置保留的資源回收筒內容。

## <a name="how-retention-works-for-onenote-content"></a>OneNote 内容保留功能的運作方式

將保留原則套用至包含 OneNote 內容的位置時，不同的 OneNote 區段實際上是不同的檔案。 這意味著將根據您指定的保留設定分別保留和删除每個區段。

## <a name="how-retention-works-with-document-versions-in-a-site-collection"></a>保留原則如何使用網站集合中的文件檔案版本

版本設定是 SharePoint 和 OneDrive 中所有文件庫的功能。 根據預設，版本設定會最少保留 500 個主要版本，不過您可以增加此限制。 如需詳細資訊，請參閱[啟用和設定清單或文件庫的版本設定](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)和[版本設定如何在清單和文件庫中運作](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247)。
  
僅保留原則設定會保留在 SharePoint 網站集合或 OneDrive 帳戶中所有版本的文件檔案。 在首次編輯受到保留或僅保留原則規範的文件檔案時，原始文件檔案的版本就會被複製到 [文件保留庫]。 若有啟用版本設定功能，在刪除受到保留或僅保留設定的時，該檔案的所有版本資訊都會複製到 [文件保留庫]。 在 [文件保留庫] 中的每個文件版本都會以單一個別的項目儲存，並有各自不同的保留期間：
  
- 如果保留期間是依照內容建立的時間作為計算基礎，則每個版本的有效期限皆與原始檔案相同。 原始檔案及其不同的版本檔案皆會同時過期。

- 如果保留期間是依照內容的前次修改時間作為計算基礎，當原始檔案每次進行編修時就會產生不同的版本，其有效期限也就隨之不同。 原始檔案及其版本檔案的有效期限皆是獨立分開計算的。

> [!NOTE]
> 電子文件探索工具無法搜尋保留版本的 SharePoint 和 OneDrive 文件。

對於受限於保留原則 (或法務保存措施) 的項目，會忽略文件庫的版本設定限制，直到達到文件的保留期間為止。 在此案例中，不會自動清除舊的版本，且會防止使用者刪除版本。

如果未對網站套用保留原則，保留標籤就不會有此作用。 相反地，會採用版本設定限制，以便可自動刪除較舊的版本以容納新版本，但使用者仍無法刪除版本。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時

**SharePoint** ：

如果組織中的使用者離職，該使用者建立的任何內容將不受到影響，因為 SharePoint 被視為共同作業環境，與使用者的信箱或 OneDrive 帳戶不同。

**OneDrive** ：

如果組織中的使用者離職，任何受限於保留原則或含有保留標籤的檔案，在原則或標籤的保留期間內都會予以保留。 在此期間，所有的共用存取權都持續有效。 當保留期間到期時，內容會移至 [網站集合資源回收筒] 中，且只有系統管理員可以存取這些檔案。如果保留原則將文件檔案標示為一份記錄，這些檔案會一直保留直到保留期間結束，之後便會將它們永久刪除。

## <a name="configuration-guidance"></a>配置指導方針

如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

如果您已準備好設定 Exchange 的保留原則或保留標籤，請參閱下列指示:
- [建立及設定保留原則](create-retention-policies.md)
- [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
- [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)
