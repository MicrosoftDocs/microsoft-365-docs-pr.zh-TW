---
title: 從核心 eDiscovery 案例匯出及下載內容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何從核心 eDiscovery 案例匯出及下載內容。
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760297"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>從核心 eDiscovery 案例匯出內容

成功執行搜尋之後，您可以匯出搜尋結果。 當您匯出搜尋結果時，信箱專案會下載到 PST 檔案或個別郵件。 當您從商務網站的 SharePoint 和 OneDrive 匯出內容時，會匯出原生 Office 檔和其他檔的副本。 包含每個匯出專案的資訊的 Results.csv 檔案，以及包含每個搜尋結果相關資訊的資訊清單檔)  (也會匯出。
  
您可以匯出 [與案例相關聯之單一搜尋](#export-the-results-of-a-single-search) 的結果，也可以匯出 [與案例相關聯之多個搜尋](#export-the-results-of-multiple-searches)的結果。
  
## <a name="export-the-results-of-a-single-search"></a>匯出單一搜尋的結果

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [ **核心電子** 檔探索] 頁面上，選取您要從中匯出搜尋結果的案例，然後按一下 [ **開啟案例**]。

4. 在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。

5. 在案例的搜尋清單中，按一下您想要從中匯出搜尋結果的搜尋，然後按一下快顯視窗的 [ **匯出結果** ]。

    [ **匯出結果** ] 頁面隨即顯示。 

    ![匯出結果頁面](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    匯出與核心 eDiscovery 案例相關聯之搜尋結果的工作流程，與在 [ **內容搜尋** ] 頁面上匯出搜尋的搜尋結果相同。 如需逐步指示，請參閱 [匯出內容搜尋結果](export-search-results.md)。

    > [!NOTE]
    > 當您匯出搜尋結果時，您可以選擇啟用重復資料刪除，這樣一來，即使在搜尋的信箱中找到多個相同郵件的實例，也只會匯出電子郵件的一個副本。 如需有關重復資料刪除以及如何識別重複專案的詳細資訊，請參閱 [eDiscovery 搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除。

    在您開始匯出後，搜尋結果即已準備好下載，這表示它們會上傳至 Microsoft 雲端中的 Microsoft 提供 Azure 儲存位置。
  
6. 按一下 [ **匯出** ] 索引標籤，顯示案例的匯出工作清單。
  
    您可能 **需要按一下 [** 重新整理] 以更新匯出工作清單，使其顯示您建立的匯出工作。 匯出工作與對應的搜尋同名， **_Export** 附加至搜尋名稱。

7. 按一下您建立的匯出工作，以在飛入頁面上顯示狀態資訊。 此資訊包含已轉接至 Azure 儲存位置的專案百分比。

8. 所有專案都已轉接後，按一下 [ **下載結果** ]，將搜尋結果下載至您的本機電腦。 如需下載搜尋結果的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-2-download-the-search-results)中的步驟2。

## <a name="export-the-results-of-multiple-searches"></a>匯出多個搜尋的結果

除了匯出與案例相關聯之單一搜尋的結果之外，您還可以從單一匯出工作中的相同案例中匯出多個搜尋的結果。 匯出多個搜尋的結果比匯出一次搜尋的結果更快速且更容易。
  
> [!NOTE]
> 如果其中一項搜尋設定為 [保留時搜尋位置]，則您無法匯出多個搜尋的結果。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [ **核心電子** 檔探索] 頁面上，選取您要從中匯出搜尋結果的案例，然後按一下 [ **開啟案例**]。

4. 在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。
    
5. 在案例的搜尋清單中，選取您想要從中匯出搜尋結果的兩個或多個搜尋旁邊的核取方塊。 

   隨即會顯示 [ **大量動作** ] 飛出頁面。 

    ![在 [大量動作] 頁面上，按一下 [匯出結果]](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. 按一下 [ **匯出結果**]。

   [ **匯出結果** ] 頁面隨即顯示。 

    ![匯出結果頁面](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    此時，匯出與核心 eDiscovery 案例相關聯之多個搜尋結果的工作流程，與匯出單一搜尋的搜尋結果相同。 請參閱上一節中的步驟5。

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>有關匯出多個搜尋結果的詳細資訊

- 當您匯出多個搜尋的結果時，會使用 **OR** 運算子組合所有搜尋中的搜尋查詢，然後啟動合併後的搜尋。 合併搜尋的預估結果會顯示在所選匯出工作的飛出頁面中。 然後將搜尋結果複製到 Microsoft 雲端中的 Azure 儲存體位置。 複製工作的狀態也會顯示在飛入頁面上。 如先前所述，所有搜尋結果都已複製後，您可以將其下載到本機電腦。

- 所有要匯出之搜尋的關鍵字數目上限為500。 這對單一搜尋的限制相同。 這是因為匯出工作會結合使用 **OR** 運算子的所有搜尋查詢。 如果您超過此限制，將會傳回錯誤。 在此情況下，您必須從較少的搜尋中匯出結果，或是簡化您想要匯出之原始搜尋的搜尋查詢。

- 匯出的搜尋結果會依找到專案的內容位置進行組織。 這表示匯出結果中的內容位置可能會有不同搜尋傳回的專案。 例如，如果您選擇將電子郵件訊息匯出至每個信箱的一個 PST 檔案中，則 PST 檔案可能會有多個搜尋的結果。

- 如果相同內容位置的相同電子郵件專案或檔是透過您匯出的一個搜尋傳回，則只會匯出該專案的一個複本。

- 您在建立多個搜尋後，就無法編輯該匯出。 例如，您無法在匯出工作中新增或移除搜尋。 您必須建立匯出工作，以變更要匯出的搜尋結果。 在建立匯出工作之後，您只可以將結果下載至電腦、重新開機匯出或刪除匯出工作。

- 如果您重新開機匯出，對組成匯出工作之搜尋查詢所做的任何變更，都不會影響所檢索的搜尋結果。 當您重新開機匯出時，在建立匯出工作時所執行的相同組合搜尋查詢工作會再次執行。

- 此外，如果您重新開機匯出，複製到 Azure 儲存體位置的搜尋結果會覆寫先前的結果。 先前所複製的結果將不會下載。
