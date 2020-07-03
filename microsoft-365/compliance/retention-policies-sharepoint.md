---
title: 了解 SharePoint 和 OneDrive 的保留原則
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
description: 了解適用於 SharePoint 和 OneDrive 的保留原則。
ms.openlocfilehash: e7a265d39b3cca2ffb9c403cf2c87f287a9325b2
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016244"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>了解 SharePoint 和 OneDrive 的保留原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

本文中的資訊可補充[了解保留原則](retention-policies.md)，因為其包含 SharePoint 和 OneDrive 專用的資訊。

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>保留原則如何搭配 SharePoint 和 OneDrive 使用

保留原則會在網站集合層級套用。 當您在保留原則中包含 SharePoint 網站集合或 OneDrive 帳戶時，會建立文件保留庫 (如果不存在)。 您可以在網站集合的頂層網站中的 [網站內容]**** 頁面上檢視此文件庫。 文件保留庫僅供網站集合系統管理員檢視，大部分的使用者都無法檢視。
  
如有使用者嘗試變更或刪除受限於保留原則的站台內容，保留原則會先檢查內容在套用原則後是否有所變更。 如果這是套用原則後的第一次變更，保留原則會先將內容複製到文件保留庫，然後允許使用者變更或刪除原始內容。 網站集合中的任何內容都可複製到文件保留庫，即使內容不符合保留原則所使用的查詢篩選器亦然。
  
計時器工作會定期清除文件保留庫。 此工作會比較文件保留庫中的所有內容與站台上之保留原則所使用的所有查詢。 比其設定的保留期間更舊的內容會從文件保留庫中刪除，以及從原始位置刪除 (如果仍然存在)。 此計時器工作會每隔七天執行一次，這表示要刪除內容最多可能需要七天的時間。
  
這項行為適用於套用保留原則時已存在的內容。 除此之外，任何在網站集合納入保留原則後才在網站集合中建立或新增的內容，在刪除之後仍將保留。 不過，新內容在第一次編輯時並不會複製到文件保留庫，而只有在刪除時才會。 若要保留檔案的所有版本，您必須開啟[版本設定](#how-a-retention-policy-works-with-document-versions-in-a-site-collection)。
  
如果使用者嘗試刪除受保留原則保護的文件庫、清單、資料夾或網站，則會收到錯誤。 如果先移動或刪除受到原則保護之資料夾中的檔案，那麼使用者就可以刪除該資料夾。 此外，文件保留庫會在此階段建立，而不是在您建立保留原則時建立。 這表示，若要測試原則，您必須先編輯或刪除受限於保留原則的網站中的文件，然後瀏覽至文件保留庫以檢視保留的複本。
  
將保留原則指派至 OneDrive 帳戶或 SharePoint 網站後，內容的路徑會根據保留原則為保留和刪除、僅保留或僅刪除。

當保留原則為保留和刪除時：

![SharePoint 和 OneDrive 中內容生命週期的圖表](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. 若已在保留期間**修改或刪除內容**，即會在文件保留庫中建立指派保留原則時即存在之原始內容的複本。 此時，計時器工作會識別保留期間已過期的項目。 這些項目會移到第二階段資源回收筒，並在 93 天結束時永久刪除。 使用者看不到第二階段資源回收筒 (只能看到第一階段資源回收筒)，但網站集合管理員可以檢視並從該處還原內容。

    > [!NOTE]
    > 為了防止意外的資料遺失，我們不再永久刪除保留文件庫中的內容。 相反地，我們只會從資源回收筒中永久刪除內容。因此，來自保留文件庫的所有內容，現在將會移至第二階段資源回收筒。
    
2. **如果未在保留期間修改或刪除內容**，計時器工作會在保留期間結束時將此內容移至第一階段資源回收筒。 如果使用者從此處刪除內容，或清空此資源回收筒 (也就是清除)，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 系統並未對資源回收筒編製索引，因此無法提供搜尋。 如此一來，電子文件探索搜尋就找不到可放置保留的資源回收筒內容。

當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化：

#### <a name="content-paths-for-retain-only-retention-policy"></a>「僅保留」保留原則的內容路徑

1. 在保留期間，**如果內容已修改或刪除**：原始文件的複本會在文件保留庫內建立，並保留到保留期間結束時，然後文件保留庫內的複本會移至第二階段資源回收筒，並在 93 天後永久刪除。

2. 在保留期間，**如果未修改或刪除內容**：保留期間前後沒有任何變化；文件仍會保留在其原始位置。

#### <a name="content-paths-for-delete-only-retention-policy"></a>「僅刪除」保留原則的內容路徑

1. **如果在設定的保留期間刪除內容**：文件會移至第一階段資源回收筒。 如果使用者從此處刪除文件，或清空此資源回收筒，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 如果在設定的期間修改內容，則在保留期間後會遵循相同的刪除路徑。

2. **如果未在設定的保留期間刪除內容**：在設定的保留期間結束時，系統會將文件移至第一階段資源回收筒。 如果使用者從此處刪除文件，或清空此資源回收筒 (也就是清除)，則會將文件移至第二階段資源回收筒。 93 天保留期間涵蓋了第一和第二階段資源回收筒。93 天結束時，則會從文件所在的任何位置永久刪除文件 (無論是第一或第二階段資源回收筒)。 系統並未對資源回收筒編製索引，因此無法提供搜尋。 如此一來，電子文件探索搜尋就找不到可放置保留的資源回收筒內容。
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>保留原則如何搭配網站集合中的文件版本使用

版本設定是 SharePoint 和 OneDrive 中所有文件庫的功能。 根據預設，版本設定會最少保留 500 個主要版本，不過您可以增加此限制。 如需詳細資訊，請參閱[啟用和設定清單或文件庫的版本設定](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)。
  
僅保留原則會保留 SharePoint 網站集合或 OneDrive 帳戶中文件的所有版本。 受限於保留或僅保留原則的文件首次遭到編輯時，就會將原始文件版本複製到保留文件庫。 如果已啟用版本設定，受限於保留或僅保留原則的文件遭到刪除時，就會將所有版本複製到保留文件庫。 文件保留庫中的每個文件版本都會存在為個別的項目，並有其自己的保留期間：
  
- If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.
    
- If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.

> [!NOTE]
> 電子文件探索工具無法搜尋保留版本的 SharePoint 和 OneDrive 文件。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時 

**SharePoint**：

如果組織中的使用者離職，該使用者建立的任何內容將不受到影響，因為 SharePoint 被視為共同作業環境，與使用者的信箱或 OneDrive 帳戶不同。

**OneDrive**：

如果組織中的使用者離職，任何受限於保留原則或含有保留標籤的檔案，在原則或標籤的保留期間內都會予以保留。 在此期間，所有的共用存取權都持續有效。 當保留期間到期時，內容會移至 [網站集合資源回收筒] 中，且除了系統管理員以外的任何人都無法存取。如果保留原則將文件將標記為記錄，在保留期間結束前，不會刪除文件，保留期間結束後則會永久刪除。 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>如何為 SharePoint 和 OneDrive 設定保留原則

按照 [建立及設定保留原則][](create-retention-policies.md) 和 [選擇位置]**** 精靈頁面中的指示進行，選取下列其中一個選項：

- **僅將原則套用到 Exchange 電子郵件、公用資料夾、Office 365 群組、OneDrive 及 SharePoint 文件中的內容**

- **讓我選擇特定位置，** > **SharePoint 網站**、**OneDrive 帳戶**和 **Office 365 群組**。

當您選擇 **SharePoint 網站** 位置時，保留原則可保留 SharePoint 通訊網站中的內容、未透過 Office 365 群組所連結的小組網站，以及傳統網站。 此選項不支援由 Office 365 群組所連結的小組網站，而是使用套用倒群組信箱、網站和檔案中的內容的 **Office 365 群組**位置。 

當您為 SharePoint 網站指定位置時，您不需要存取網站的權限，而在 [編輯位置]**** 頁面上指定 URL 時也不會進行驗證。 不過，網站必須編制索引，而在精靈結尾將會檢查您指定的網站是否存在。 

如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。 如果您看到這則訊息，請返回精靈變更 URL 或移除網站。
