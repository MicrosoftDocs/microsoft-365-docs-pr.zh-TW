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
description: 說明如何從 Microsoft 365 中的核心 eDiscovery 案例中匯出及下載內容。
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310837"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>從核心電子文件探索案例匯出內容

成功執行與核心 eDiscovery 案例相關聯的搜尋之後，您可以匯出搜尋結果。 當您匯出搜尋結果時，信箱專案會下載到 PST 檔案或個別郵件。 當您從 SharePoint 和商務用 OneDrive 網站匯出內容時，會匯出原生 Office 檔和其他檔的副本。 包含每個匯出專案的資訊的 Results.csv 檔案，以及包含每個搜尋結果相關資訊的資訊清單檔)  (也會匯出。
  
## <a name="export-search-results"></a>匯出搜尋結果

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [ **核心電子** 檔探索] 頁面上，按一下您要在其中建立保留的案例名稱。

4. 在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。

5. 在飛入頁面底部的 [ **動作** ] 功能表上，按一下 [ **匯出結果**]。

   ![[動作] 功能表中的 [匯出結果] 選項](../media/ActionMenuExportResults.png)

   匯出與核心 eDiscovery 案例相關聯之搜尋結果的工作流程，與在 [ **內容搜尋** ] 頁面上匯出搜尋的搜尋結果相同。 如需逐步指示，請參閱 [匯出內容搜尋結果](export-search-results.md)。

   > [!NOTE]
   > 當您匯出搜尋結果時，您可以選擇啟用重復資料刪除，這樣一來，即使在搜尋的信箱中找到多個相同郵件的實例，也只會匯出電子郵件的一個副本。 如需有關重復資料刪除以及如何識別重複專案的詳細資訊，請參閱 [eDiscovery 搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除。

   在您開始匯出後，搜尋結果即會做好下載準備，這表示它們會傳送至 microsoft 雲端中的 microsoft 所提供的 Azure 儲存體位置。
  
6. 按一下案例中的 [ **匯出** ] 索引標籤，顯示匯出工作清單。
  
   ![在核心 eDiscovery 案例的 [匯出] 索引標籤上匯出工作](../media/CoreeDiscoveryExport.png)

   您可能 **需要按一下 [** 重新整理] 以更新匯出工作清單，使其顯示您建立的匯出工作。 匯出工作與對應的搜尋同名， **_Export** 附加至搜尋名稱。

7. 按一下您建立的匯出工作，以在飛入頁面上顯示狀態資訊。 此資訊包含已轉接至 Azure 儲存體位置之專案的百分比。

8. 所有專案都已轉接後，按一下 [ **下載結果** ]，將搜尋結果下載至您的本機電腦。 如需下載搜尋結果的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-2-download-the-search-results)中的步驟2。

### <a name="more-information-about-exporting-searches-from-a-case"></a>從案例中匯出搜尋的詳細資訊

- 如需匯出搜尋結果時所包含匯出檔案的詳細資訊，請參閱 [匯出內容搜尋報告](export-a-content-search-report.md#whats-included-in-the-report)。

- 如果您重新開機匯出，對組成匯出工作之搜尋查詢所做的任何變更，都不會影響所檢索的搜尋結果。 當您重新開機匯出時，在建立匯出工作時所執行的相同組合搜尋查詢工作會再次執行。

- 此外，如果您重新開機匯出，會複製到 Azure 儲存體位置的搜尋結果會覆寫先前的結果。 先前所複製的結果將不會下載。
