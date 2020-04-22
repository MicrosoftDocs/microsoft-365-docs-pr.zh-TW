---
title: 匯出內容搜尋報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 您可以匯出搜尋結果報告，而不是在 Office 365 的安全性 & 規範中心中匯出內容搜尋的實際結果。 報告包含搜尋結果摘要及檔，其中包含每個要匯出之專案的詳細資訊。
ms.openlocfilehash: 63acc8701973519f959ced9822333e893e6fd863
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615927"
---
# <a name="export-a-content-search-report"></a>匯出內容搜尋報告

在 [安全性 & 規範中心] （以及從與 eDiscovery 案例相關聯的內容搜尋）中匯出搜尋結果的完整集合時，您可以匯出在匯出搜尋結果時所產生的相同報告。
  
當您匯出報表時，它會下載到與內容搜尋同名的資料夾，但附加 *_ReportsOnly*。 例如，如果內容搜尋命名為*ContosoCase0815*，則會將報告下載至名為*ContosoCase0815_ReportsOnly*的資料夾。 如需報告中所包含檔的清單，請參閱[報告的內容](#whats-included-in-the-report)。

## <a name="before-you-begin"></a>開始之前

- 若要匯出內容搜尋報告，您必須在安全性 & 規範中心內指派符合性搜尋管理角色。 此角色會指派給內建的 eDiscovery 管理員和組織管理角色群組。 組織管理角色群組預設不會指派給它。 如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。
    
- 當您匯出報告時，資料會暫時儲存在 Microsoft 雲端的唯一 Azure 存放區中，然後再下載到本機電腦。 請確定您的組織可以連線到 Azure 中的端點，也就是** \*blob.core.windows.net** （萬用字元代表匯出的唯一識別碼）。 搜尋結果資料會在建立後的兩周從 Azure 存放區刪除。 
    
- 您用來匯出搜尋結果的電腦必須符合下列系統需求：
    
  - 32位或64位版本的 Windows 7 和更新版本
    
  - Microsoft .NET Framework 4。7
    
- 您必須使用下列其中一種支援的瀏覽器執行 eDiscovery 匯出工具<sup>1</sup>：

  - Microsoft Edge <sup>2</sup>

    OR

  - Microsoft Internet Explorer 10 和更新版本

  > [!NOTE]
  > <sup>1</sup> Microsoft 不會製造協力廠商擴充模組或 ClickOnce 應用程式的附加元件。 使用不受支援的瀏覽器匯出搜尋結果時，不支援協力廠商分機或附加元件。<br/>
  > <sup>2</sup>由於 Microsoft Edge 的最近變更，因此預設不再啟用 ClickOnce 支援。 如需在 Edge 中啟用 ClickOnce 支援的相關指示，請參閱[使用 Microsoft Edge 中的 EDiscovery 匯出工具](configure-edge-to-export-search-results.md)。

- 如果預估內容搜尋所傳回的結果總大小超過 2 TB，則匯出報表失敗。 若要順利匯出報告，請嘗試縮小範圍並重新執行搜尋，使結果的預估大小小於 2 TB。

- 匯出內容搜尋報告時，會依據同時執行的匯出數目上限及單一使用者可執行檔匯出數目上限而產生計數。 如需匯出限制的相關資訊，請參閱[匯出內容搜尋結果](export-search-results.md#export-limits)。

## <a name="generate-and-download-a-content-search-report"></a>產生及下載內容搜尋報告

產生及下載內容搜尋報告的步驟，與實際匯出搜尋結果類似。
  
## <a name="step-1-generate-the-report-for-export"></a>步驟1：產生要匯出的報告

第一步是準備報表，以下載至電腦匯出。 當您報告時，報表檔會上傳至 Microsoft 雲端中的 Azure 存放區。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在安全性 & 規範中心的左窗格中，按一下 [**搜尋** \> **內容搜尋**]。
    
4. 在 [**內容搜尋**] 頁面上，選取搜尋。 
    
5. 在詳細資料窗格中，在 [**將報告匯出至電腦**] 底下，按一下 [**產生報告**]。
    
    > [!NOTE]
    > 如果搜尋的結果超過7天，系統會提示您更新搜尋結果。 如果發生這種情況，請取消匯出，按一下 [詳細資料] 窗格中所選搜尋的 [**更新搜尋結果**]，然後在結果更新後再次啟動報告匯出。 
  
6. 在 [**匯出報告**] 頁面的 [**包含搜尋中的這些專案**] 底下，選擇下列其中一個選項：
    
    - 只匯出已編制索引的專案
    
    - 匯出已編制索引及未編制索引的專案
    
    - 只匯出未編制索引的專案
    
    如需未編制索引之專案的詳細資訊，請參閱[內容搜尋中已部分索引的專案](partially-indexed-items-in-content-search.md)。
    
7. 選擇包含所有 SharePoint 檔版本的搜尋統計資料。 只有在搜尋的內容來源包含 SharePoint 或 OneDrive 商務網站時，才會顯示此選項。
    
8. 按一下 [**產生報告**]。
    
    搜尋結果報告已準備好下載，這表示會將報告檔上傳至 Microsoft 雲端中的 Azure 儲存體區域。 當報告可供下載時，[**下載報告**] 連結會顯示在 [詳細資料] 窗格中的 [**匯出報告至電腦**] 底下。 
    
> [!NOTE]
> 您也可以匯出與 eDiscovery 案例相關聯之內容搜尋的報告。 若要執行此動作，請移至**ediscovery** \> **ediscovery**，選取案例， **Edit** ![然後按一下 [](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)編輯編輯圖示]。 在 [**搜尋**] 頁面上，選取搜尋，然後按一下 [**匯出** ![匯出搜尋結果](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \>圖示] [**匯出報告**]。 
  
## <a name="step-2-download-the-report"></a>步驟2：下載報表

下一步是將報告從 Azure 存放區下載到您的本機電腦。
  
1. 在您產生報告之搜尋的 [詳細資料] 窗格中，在 [**將報告匯出至電腦**] 底下，按一下 [**下載報告**]。
    
    [**下載報告**] 頁面隨即顯示，並包含下列有關下載至電腦之報告的資訊。 
    
    - 將下載的專案數。
    
    - 預估將要下載之專案的總大小。
    
    - 是否要匯出索引或未編制索引的索引。 未編制索引的專案是指具有可識別格式的專案、已加密的專案，或因其他原因而未建立索引的專案。
    
    - SharePoint 檔的版本是否會下載。
    
    - 報表匯出程式的狀態。 即使報表準備未完成，也可以開始下載報表。
    
2. 在 [**匯出金鑰**] 底下，按一下 [**複製到剪貼**簿]。 您可以在步驟5中使用此機碼下載報告。
    
    > [!IMPORTANT]
    > 由於任何人都可以安裝並啟動 eDiscovery 匯出工具，然後使用此機碼來下載搜尋報告，請務必採取預防措施來保護此機碼，就像您保護密碼或其他安全性相關的資訊一樣。 
  
3. 按一下 [**下載報告**]。
    
4. 如果系統提示您安裝**EDiscovery 匯出工具**，請按一下 [**安裝**]。
    
5. 在 [ **EDiscovery 匯出工具**] 中，在適當的方塊中貼上您在步驟2中複製的匯出金鑰。
    
6. 按一下 **[流覽]** 以指定您要下載報表的位置。 
    
7. 按一下 [開始]**** 將搜尋結果下載至您的電腦。 
    
    **EDiscovery 匯出工具**會顯示匯出程式的狀態資訊，包括要下載之其餘專案的數位（和大小）的預估。 匯出程式完成後，您可以在下載檔案的位置存取檔案。 
    
> [!NOTE]
> 您可以下載與 eDiscovery 案例相關聯的內容搜尋報告。 若要執行此動作，請移至**ediscovery** \> **ediscovery**，選取案例， **Edit** ![然後按一下 [](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)編輯編輯圖示]。 在 [**匯出**] 頁面上，選取報告匯出，然後按一下 [詳細資料] 窗格中的 [**下載報告**]。 
  
## <a name="whats-included-in-the-report"></a>報告中包含的內容

當您產生及匯出內容搜尋結果的報告時，會下載下列檔：
  
- **匯出摘要：** 包含匯出摘要的 Excel 檔。 這包括下列資訊：搜尋的內容來源數目、每個內容位置的搜尋結果數目、預估的專案數、要匯出的實際專案數，以及所要匯出之專案的預估和實際大小。 
    
    > [!NOTE]
    > 如果您在匯出報告時包含未編制索引的專案，未編制索引的專案數目會包含在已預計的搜尋結果總數和下載之搜尋結果的總數（如果您要匯出搜尋結果，則是在 [匯出摘要] 報告中列出）。 換句話說，將下載的專案總數等於估計的結果總數和未編制索引的專案總數。 
  
- **資訊清單：** 包含在搜尋結果中的每個專案相關資訊的資訊清單檔案（XML 格式）。 
    
- **結果：** 包含每一列的 Excel 檔，其中包含每個要連同搜尋結果一起匯出之索引項目目的相關資訊。 針對電子郵件，結果記錄檔包含每封郵件的相關資訊，包括： 
    
  - 來源信箱中郵件的位置（包括郵件是在主要或封存信箱中）。
    
  - 傳送或接收郵件的日期。
    
  - 郵件的主旨行。
    
  - 郵件的寄件者和收件者。
    
    針對來自 SharePoint 和 OneDrive 商務網站的檔，結果記錄檔包含每個檔的相關資訊，包括：
    
  - 檔的 URL。
    
  - 檔所在之網站集合的 URL。
    
  - 上次修改檔的日期。
    
  - 檔的名稱（位於結果記錄檔的 [主旨] 欄中）。
    
    > [!NOTE]
    > **結果**報告中的列數應該等於搜尋結果的總數減去 [未**編制索引的專案**] 報告中所列的總專案數。 
  
- 未**編制索引的專案：** Excel 檔，包含搜尋結果中所包含之任何未編制索引項目目的相關資訊。 如果您在產生搜尋結果報告時未包含未編制索引的專案，則此報告仍會下載，但會是空的。
