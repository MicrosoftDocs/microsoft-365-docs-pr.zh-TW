---
title: 將組織的 PST 檔案匯入至 Office 365 概觀
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 適用於系統管理員：了解在安全性與合規性中心使用「匯入」服務來將電子郵件資料 (PST 檔案) 大量匯入至 Exchange Online 的使用者信箱。 本主題提供常見問題集，並說明 PST 匯入程序的運作方式。
ms.openlocfilehash: 309fde077cdf456ba33656c29f9e325aac1820e3
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807122"
---
# <a name="overview-of-importing-your-organizations-pst-files-to-office-365"></a>將組織的 PST 檔案匯入至 Office 365 概觀

> [!NOTE]
> 本文適用於系統管理員。 您是否正嘗試匯入 PST 檔案到自己的信箱？ 請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人和行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)

您可以使用安全性與合規性中心的「匯入」服務將 PST 檔案快速大量匯入到 Office 365 組織中的 Exchange Online 信箱。 有兩種方法可將 PST 檔案匯入到 Office 365：

- **網路上傳**![雲端上傳](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - 透過網路將 PST 檔案上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。 然後使用 Office 365 匯入服務將 PST 資料匯入 Office 365 組織中的信箱。 

- **磁碟機寄送**![硬碟](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - 將 PST 檔案複製到 BitLocker 加密硬碟，並實際寄送磁碟機給 Microsoft。 當 Microsoft 收到硬碟時，資料中心人員會將資料上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。 然後使用 Office 365 匯入服務將資料匯入 Office 365 組織中的信箱。

## <a name="step-by-step-instructions"></a>逐步指示
  
請參閱下列其中一個主題以取得將組織 PST 檔案大量匯入至 Office 365 的詳細逐步指示。 

- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)

- [使用磁碟機寄送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>匯入 PST 檔案的運作方式

以下是完整 PST 匯入程序的圖例和說明。 圖例顯示主要工作流程，並醒目提示網路上傳和磁碟機寄送方法之間的差異。
  
![PST 匯入程序的工作流程](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **將 PST 匯入工具和金鑰下載到私人 Azure 儲存體位置** - 第一個步驟是下載用於上傳 PST 檔案的工具和存取金鑰，或將它們複製到硬碟。 您可以從安全性與合規性中心的**匯入**頁面取得這些工具和便捷鍵。 此金鑰提供您 (或在磁碟機寄送時提供給 Microsoft 資料中心人員) 將 PST 檔案上傳到私人且安全的 Azure 儲存體位置的必要權限。 此便捷鍵專屬於貴組織，並在 PST 檔案上傳到 Microsoft Cloud 後，協助防止未經授權存取 PST 檔案。 將 PST 檔案匯入至 Office 365 不會要求貴組織具有不同的 Azure 訂閱。 
    
2. **上傳或複製的 PST 檔案** - 下一個步驟取決於您使用網路上傳或磁碟機寄送來匯入 PST 檔案。 在這兩種情況下，您會使用上一個步驟中取得的工具和安全儲存體金鑰。
    
    - **網路上傳**AzCopy.exe 工具 (於步驟 1 中下載) 用於上傳 PST 檔案並將其儲存在 Microsoft Cloud 中的 Azure 儲存體位置。 上傳 PST 檔案的 Azure 儲存體位置與 Office 365 組織所在的地區性 Microsoft 資料中心相同。
    
      若要上傳，您想要匯入 Office 365 的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。
    
    - **磁碟機寄送**WAImportExport.exe 工具 (於步驟 1 下載) 是用於將 PST 檔案複製到硬碟。 此工具會以 BitLocker 加密硬碟，然後將 PST 複製到硬碟。 如同網路上傳，您想要複製到硬碟的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。
    
3. **建立 PST 匯入對應檔案** - PST 檔案上傳到 Azure 儲存體位置或複製到硬碟後，下一個步驟是建立逗點分隔值 (CSV) 檔案，以指定要匯入 PST 檔案的使用者信箱 (PST 檔案可匯入使用者的主要信箱或封存信箱)。 Office 365 匯入服務會使用此資訊匯入 PST 檔案。 
    
4. **建立 PST 匯入工作** - 下一個步驟是在安全性與合規性中心的 [匯入]**** 頁面建立 PST 匯入工作，然後提交上一個步驟中建立的 PST 匯入對應檔案。 若為網路上傳 (因為 PST 檔案已上傳到 Azure)，Office 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。 
    
    若為磁碟機寄送，此時程序中會發生一些其他事項。
    
    - 您實際將硬碟寄送給 Microsoft 資料中心 (建立匯入工作時，會顯示 Microsoft 資料中心的寄送地址)。
    
    - Microsoft 收到硬碟之後，資料中心的人員會為貴組織將硬碟上的 PST 檔案上傳到 Azure 儲存體位置。 如先前所解釋，您的 PST 檔案會上傳至 Office 365 組織所在的相同地區性 Microsoft 資料中心的 Azure 儲存體位置。
    
      > [!NOTE]
      > Microsoft 收到硬碟後，會在 7 到 10 個工作天內將硬碟上的 PST 檔案上傳至 Azure。

      如同網路上傳程序，Office 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。
    
    - Microsoft 會將硬碟寄回給您。
    
5. **篩選將匯入到信箱的 PST 資料** - 建立匯入工作後 (且磁碟機寄送工作的 PST 檔案上傳到 Azure 儲存體位置後)，Office 365 會透過找出項目的留存時間和包括在 PST 檔案中的不同訊息類型，(以安全的方式) 分析 PST 檔案中的資料。 分析完成且準備好匯入資料後，您可以選擇匯入 PST 檔案中所包含的所有資料，或設定控制匯入資料的篩選條件來調整要匯入的資料。 
    
6. **開始 PST 匯入工作** - 開始匯入工作後，Office 365 會使用 PST 匯入對應檔案中的資訊，將 PST 檔案從 Azure 儲存體位置匯入至使用者信箱。 匯入工作的狀態資訊 (包括匯入的每個 PST 檔案的相關資訊) 會顯示在安全性與合規性中心的 [匯入 PST 檔案]**** 頁面。 匯入工作完成時，工作的狀態會設為**完成**。
  
## <a name="why-import-email-data-to-office-365"></a>為什麼要將電子郵件資料匯入 Office 365？

- 這是將組織的封存訊息資料匯入 Office 365 的好方法。
    
- 您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際匯入目標信箱的 PST 檔案項目。 這能讓您藉由設定控制匯入資料的篩選條件來調整要匯入的資料。 
    
- 將電子郵件資料匯入至 Office 365 可讓您透過下列方式協助解決組織的法務遵循需求︰
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)和[無限制封存](unlimited-archiving.md)以提供使用者額外的信箱儲存空間。 
    
  - 將信箱置於[訴訟暫止](https://go.microsoft.com/fwlink/?linkid=841243)來保留內容。 
    
  - 使用[內容搜尋工具](content-search.md)搜尋信箱內容。 
    
  - 使用[電子文件探索案例](ediscovery-cases.md)來管理貴組織的法律調查 
    
  - 使用安全性與合規性中心的[保留原則](retention-policies.md)來控制信箱內容的保留時間，並在保留期間結束後刪除內容。 

  - 使用[通訊合規性原則](communication-compliance.md)檢查郵件，以確認郵件符合郵件標準的規範，並新增分類類型。
    
- 將資料匯入 Office 365 可協助防止資料遺失。 匯入 Office 365 的電子郵件資料會繼承 Exchange Online 的高可用性功能。
    
- Office 365 的電子郵件資料儲存在雲端上，所以使用者從各種裝置都能取得資料。
    
## <a name="importing-sharepoint-data-to-office-365"></a>將 SharePoint 資料匯入 Office 365

您也可以將檔案和文件匯入 Office 365 組織中的 SharePoint 網站和 OneDrive 帳戶。 如需詳細資訊，請參閱下列文章：

- [移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 移轉工具簡介](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [使用 PowerShell 移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [使用 Azure 資料箱將檔案共用內容移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>關於將 PST 檔案匯入至 Office 365 的常見問題
  
以下是一些關於使用 Office 365 匯入服務將 PST 檔案大量匯入 Office 365 信箱的常見問題解答。 
  
- [使用網路上傳來匯入 PST 檔案](#using-network-upload-to-import-pst-files)
  
- [使用磁碟機寄送來匯入 PST 檔案](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>使用網路上傳來匯入 PST 檔案

 **必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**
  
您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Office 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。
  
此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：
  
- 您必須在 Exchange Online 中獲派郵件收件者角色。 根據預設，這個角色會指派給組織管理及收件者管理角色群組。

    或
    
- 您必須是您 Office365 組織中的全域系統管理員。

> [!TIP]
> 建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。 若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。 
  
 **哪些地區提供網路上傳服務？**
  
網路上傳的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。我們會盡快在更多地區提供網路上傳服務。
  
 **使用網路上傳匯入 PST 檔案的費用為何？**
  
Using network upload to import PST files is free.
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。
  
 **哪些版本的 PST 檔案格式支援匯入 Office 365？**
  
有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。 我們建議您使用 Unicode PST 檔案格式來匯入檔案。 不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。 如需有關匯入 ANSI PST 檔案的資訊，請參閱[使用網路上傳將 PST 檔案匯入 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074) 中的步驟 4。
  
此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。
  
 **將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**
  
使用網路上傳方法來匯入 PST 檔案會將這些檔案上傳到名為 **ingestiondata** 的 Azure Blob 容器。 如果安全性與合規性中心的 [匯入 PST 檔案]**** 頁面目前沒有進行中的匯入工作，則 Azure 中 **ingestiondata** 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。 這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]**** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。
  
 **需要多久的時間才能將 PST 檔案匯入信箱？**
  
這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。 將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入到 Office 365 信箱。 如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Office 365 的方法。 如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。
  
如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。 同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。
  
 **匯入 PST 檔案時，是否有郵件大小限制？**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。
  
 **PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**
  
是。 匯入程序不會變更任何原始的訊息中繼資料。
  
 **針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**
  
是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。
  
 **我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
### <a name="using-drive-shipping-to-import-pst-files"></a>使用磁碟機寄送來匯入 PST 檔案

 **必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**
  
您必須獲派信箱匯入匯出角色才能將 PST 檔案匯入 Office 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。
  
此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：
  
- 您必須在 Exchange Online 中獲派郵件收件者角色。 根據預設，這個角色會指派給組織管理及收件者管理角色群組。
    
    或
    
- 您必須是您 Office365 組織中的全域系統管理員。
    
> [!TIP]
> 建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。 若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。 
  
 **哪些地區提供磁碟機寄送服務？**
  
磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。 我們會盡快在更多地區提供磁碟機寄送服務。
  
 **有哪些商業授權合約支援磁碟機寄送？**
  
Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入 Office 365 的磁碟機寄送服務。 Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。
  
 **使用磁碟機寄送將 PST 檔案匯入 Office 365 的費用為何？**
  
使用磁碟機寄送將 PST 檔案匯入 Office 365 信箱的費用為每 GB 的資料 $2 美元。 例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。 您可以與夥伴合作來支付匯入費用。 如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Office 365 合作夥伴或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **哪些類型的硬碟支援磁碟機寄送？**
  
Office 365 匯入服務只支援使用 2.5 吋固態硬碟 (SSD)，或是 2.5 吋或 3.5 吋 SATA II/III 內接式硬碟。 您可以使用最多 10 TB 的硬碟。 匯入作業時，只會處理硬碟上的第一個資料磁碟區。 資料磁碟區必須為 NTFS 格式。 若要將資料複製到硬碟，您可以直接使用 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III 連接器進行連接，或者使用外接式 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III USB 轉接頭進行外接。
  
> [!IMPORTANT]
> Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。 此外，位於外部硬碟外殼內的碟無法使用。 請不要使用外接式硬碟。 
  
 **可以寄送幾個硬碟來進行單一匯入工作？**
  
最多可以寄送 10 個硬碟來進行單一匯入工作。
  
 **寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**
  
這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。
  
 **硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**
  
硬碟送達 Microsoft 資料中心後，需要 7 到 10 個工作天，才能將 PST 檔案上傳到貴組織的 Azure 儲存體位置。 PST 檔案會上傳到名為 `ingestiondata` 的 Azure Blob 容器。 
  
 **需要多久的時間才能將 PST 檔案匯入信箱？**
  
PST 檔案上傳到 Azure 儲存體區域之後，Office 365 會以安全的方式分析 PST 檔案中的資料，來識別 PST 檔案所含項目的保存時間和各種訊息類型。 這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。 始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入到 Office 365 信箱。 如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Office 365 的方法。 如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。
  
如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。 同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。
  
 **Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**
  
貴組織的 Azure 儲存體位置 (儲存在名為 `ingestiondata` 的 Blob 容器) 中的所有 PST 檔案，會在最新的匯入工作於安全性與合規性中心的 [匯入 PST 檔案]**** 頁面上建立完成的 30 天後遭到刪除。 
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]**** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。 
  
 **哪些版本的 PST 檔案格式支援匯入 Office 365？**
  
有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。 我們建議您使用 Unicode PST 檔案格式來匯入檔案。 不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。 如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁碟機寄送將組織 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。
  
此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。
  
 **匯入 PST 檔案時，是否有郵件大小限制？**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。
  
 **PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**
  
是。 匯入程序不會變更任何原始的訊息中繼資料
  
 **針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**
  
是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。
  
 **我是否可以使用磁碟機寄送將 PST 檔案匯入 Office 365 中的非作用中的信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
 **Microsoft 是否可以先將硬碟清空再寄回給我？**
  
否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。
  
 **Microsoft 是否可以先將硬碟銷毀再寄回給我？**
  
否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。
  
 **哪些快遞服務支援將硬碟寄回客戶？**
  
如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。
  
 **將硬碟寄回需要多少費用？**
  
實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。
  
 **我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**
  
是。
  
 **如果我需要將硬碟寄到其他國家/地區，我需要採取什麼動作嗎？**
  
您寄給 Microsoft 的硬碟可能會跨國際邊界。在這種情況下，您必須負責確保硬碟和當中的資料可依據相關法律進口和/或出口。寄送硬碟之前，請與您的顧問確認磁碟機和當中的資料可以合法地寄到指定的 Microsoft 資料中心，以確保 Microsoft 能夠及時收到您的硬碟。
