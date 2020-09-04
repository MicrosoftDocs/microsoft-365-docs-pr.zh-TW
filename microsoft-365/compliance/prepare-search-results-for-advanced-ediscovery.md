---
title: 準備進階電子文件探索的搜尋結果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 瞭解如何在安全性 & 規範中心準備內容搜尋的結果，以利用高級 eDiscovery 工具進行進一步的分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b403987c39d1ddcc1f22fd0abbeba85e60591414
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358565"
---
# <a name="prepare-search-results-for-advanced-ediscovery-classic"></a>準備進階電子文件探索 (傳統版) 的搜尋結果

> [!IMPORTANT]
> 隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。 

在安全性 & 合規性中心與 eDiscovery 案例相關聯的搜尋順利執行後，您可以使用高級 eDiscovery 準備進一步分析的搜尋結果，這樣可讓您分析大型的非結構化資料集，並減少與法律案例相關的資料量。 Advanced eDiscovery 的功能包括：
  
- **光學字元辨識** -當您準備高級 ediscovery 的搜尋結果時，光學字元辨識 (OCR) 功能會自動從影像析取文字，並將其包含在載入至高級 eDiscovery 以進行分析的搜尋結果中。 疏鬆檔案、電子郵件附件和內嵌的圖像支援 OCR。 這可讓您將高級 eDiscovery (的文字分析功能，套用至近乎重複的電子郵件執行緒、主題及預測編碼) ，以影像檔案中的文字內容。 「高級 eDiscovery OCR」支援下列圖像檔案格式：

    - GIF
    - JPEG
    - Jpg
    - PNG
    - TIFF
    
- **近乎重複的偵測** -可讓您更有效率地組織資料評審，所以一個人會檢查類似檔的群組。 這有助於防止多個檢閱者查看相同檔的不同版本。 
    
- **電子郵件執行緒** -協助您識別電子郵件線索中的唯一郵件，這樣您就只會專注于每封郵件中的新資訊。 在電子郵件線索中，第二封郵件會包含第一封郵件。 同樣地，後續郵件也會包含所有先前的郵件。 電子郵件執行緒功能可移除整個電子郵件執行緒中的每封郵件。 
    
- **主題** -除了關鍵字搜尋統計資料之外，可協助您取得資料的重要洞察力。 主題協助調查：將相關的檔分組，讓您在內容中查看檔。 使用主題時，您可以查看一組檔的相關主題、判斷任何重迭的各項，然後識別相關資料的橫截面。 
    
- **預測編碼** -可讓您針對您所要的專案，對系統進行訓練，其方式是讓您 (決定是否在一小部分檔上) 相關事項。 [！注意] 高級 eDiscovery 會根據您在分析資料集中的所有檔時的指導方針) 套用該教學 (。 根據這種教學，「高級 eDiscovery」會提供相關性排名，讓您根據哪一種檔最可能與案例相關的檔決定要檢查的檔。 
    
- **匯出資料以供審閱應用程式**  -您可以在完成分析並減少資料集後，從 Advanced EDiscovery 和 Microsoft 365 匯出資料。 匯出套件包含 CSV 檔案，其中包含匯出內容和分析中繼資料中的屬性。 然後，您可以將此匯出套件匯入 eDiscovery 考核應用程式。 
    
## <a name="get-licenses-and-permissions"></a>取得授權和許可權

- 若要使用「高級 eDiscovery」分析使用者的資料，使用者 (必須指派 Office 365 E5 授權的資料) 的管理員。 或者，您可以將高級 eDiscovery 獨立授權指派給使用 Office 365 E1 或 E3 授權的使用者。 獲指派案例的系統管理員和合規性監察官，以及使用高級 eDiscovery 來分析資料，不需要 E5 授權。 
    
- 您必須是 eDiscovery 管理員或安全性 & 合規性中心的 eDiscovery 管理員，才能準備高級 eDiscovery 的搜尋結果。 eDiscovery 管理員為 eDiscovery 管理員角色群組的成員。 eDiscovery 系統管理員也是 eDiscovery 管理員角色群組的成員，但已獲指派其他 eDiscovery 權限。 如需指派 eDiscovery 系統管理員許可權的相關指示，請參閱 [eDiscovery 案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步驟1。
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>步驟1：準備高級 eDiscovery 的搜尋結果

您可以準備與 eDiscovery 案例相關聯之搜尋的結果。 當您準備高級 eDiscovery 的搜尋結果時，會將資料上傳並暫時儲存在 Microsoft 雲端的唯一 Windows Azure 儲存體區域中。 此時，OCR 功能會從搜尋結果中的影像提取文字。 在 [步驟 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)中，會在高級 eDiscovery 中載入此文字和其他搜尋結果資料至案例。
  
1. 在 [安全性 & 規範中心] 中，按一下 [ **ediscovery** \> **ediscovery** ] 以顯示組織中案例的清單。 
    
2. 在 [高級 eDiscovery] 中，按一下您要準備搜尋結果以進行分析的案例旁邊的 [ **開啟** ]。 
    
3. 在案例的 **首頁** 上，按一下 [ **搜尋**]，然後選取搜尋。
    
4. 在詳細資料窗格的 [ **分析具有高級 eDiscovery 的結果**] 底下，按一下 [ **準備用於分析的結果**]。
    
    > [!NOTE]
    > 如果搜尋的結果是早於 7 天前，則會提示您更新搜尋結果。 
  
5. 在**準備供分析的結果**的頁面上，執行下列動作︰  
    
    - 選擇準備好編制索引的專案、索引及未編制索引的專案，或只在高級 eDiscovery 中分析未編制索引的專案。
    
    - 選擇是否要在符合搜尋準則的 SharePoint 上，包含找到的所有檔版本。 這個選項只在搜尋內容來源包含網站時才會出現。
    
    - 指定在準備工作完成時，是否要將通知訊息傳送 (或) 複製到人員，以及在高級 eDiscovery 中處理資料時已準備好。
    
6. 按一下 [準備]****。
    
    搜尋結果是準備好使用高級 eDiscovery 進行分析。
    
7. 在詳細資料窗格中，按一下 [ **檢查準備狀態** ] 以顯示準備程式的資訊。 完成準備程式後，您可以移至高級 eDiscovery 中的案例處理資料，以進行分析。 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>步驟2：將搜尋結果資料新增至高級 eDiscovery 中的案例
<a name="step2"> </a>

準備完成後，下一步是移至 [Advanced eDiscovery] 並載入搜尋結果資料 (已上傳至 Microsoft 雲端中的 Azure 儲存體區域 ) 高級 eDiscovery 中的案例。 如先前所述，若要存取高級 eDiscovery，您必須是 Security & 合規性中心的 eDiscovery 系統管理員或高級 eDiscovery 中的系統管理員。
  
> [!NOTE]
> 從安全性 & 合規性中心，將資料新增至高級 eDiscovery 的情況所需的時間，視 eDiscovery 搜尋的結果大小而定。 
  
1. 在 [安全性 & 規範中心] 中，按一下 [ **ediscovery** \> **ediscovery** ] 以顯示組織中案例的清單。 
    
2. 在 [高級 eDiscovery] 中，按一下您想要在其中載入資料之案例旁邊的 [ **開啟** ]。 
    
3. 在案例的 [首頁]**** 頁面上，按一下 [切換至進階電子文件探索]****。 
    
    ![按一下 [切換至高級 eDiscovery]，以在 [高級 eDiscovery] 中開啟案例。](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    隨即會顯示 [連線 **至高級 eDiscovery** ] 進度列。 當您連線至「高級 eDiscovery」時，容器清單會顯示在案例的 [設定] 頁面上。 
    
    ![案例會顯示在高級 eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     這些容器代表您在步驟1的高級 eDiscovery 中準備分析的搜尋結果。 請注意，在安全性 & 合規性中心的情況下，容器的名稱與搜尋的名稱相同。 清單中的容器是您準備的容器。 如果不同的使用者已為高級 eDiscovery 準備好搜尋結果，對應的容器將不會包含在清單中。 
    
4. 若要在高級 eDiscovery 的案例中從容器中載入搜尋結果資料，請選取容器，然後按一下 [ **處理**]。
    
## <a name="next-steps"></a>後續步驟

在將 eDiscovery 搜尋的結果新增至案例之後，下一步是使用「高級 eDiscovery」工具來分析資料，並識別回應特定法律案例的內容。 如需使用高級 eDiscovery 的詳細資訊，請參閱 [Advanced ediscovery (傳統) ](office-365-advanced-ediscovery.md)。
  
## <a name="more-information"></a>其他相關資訊

當您準備用於高級 eDiscovery 的分析時，搜尋結果中所包含的任何 RMS 加密電子郵件都會解密。 預設會為 eDiscovery 管理員角色群組的成員啟用此解密功能。 這是因為 RMS 解密管理角色會指派給此角色群組。 請記住下列有關解密電子郵件訊息的事項：
  
- 目前，此解密功能不包括 SharePoint 和商務網站 OneDrive 的加密內容。 匯出時，只會解密 RMS 加密的電子郵件。
    
- 如果 RMS 加密的電子郵件中有附件 (例如檔或其他電子郵件訊息) 也加密，則只會解密最上層的電子郵件。
    
- 如果您需要在準備高級 eDiscovery 的搜尋結果時，防止某人解密 RMS 加密的郵件，您必須建立自訂角色群組 (，方法是複製內建的 eDiscovery 管理員角色群組) 然後從自訂角色群組中移除 RMS 解密管理角色。 然後將您不想要將郵件解密的人員新增為自訂角色群組的成員。
