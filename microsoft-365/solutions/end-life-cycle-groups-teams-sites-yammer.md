---
title: 群組、小組和 Yammer 的生命週期選項結束
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 群組、小組和 Yammer 的生命週期選項結束。
ms.openlocfilehash: 3720f63f99711a09d02675f10a7d639fe1bedc65
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377172"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>群組、小組和 Yammer 的生命週期選項結束

Microsoft 365 群組和 Microsoft 團隊使用各種相連的服務。 刪除群組或小組時，也會刪除聯機服務中的大部分資訊。 本文說明在刪除之前，將資訊移出群組或小組所要保留的選項。

不再需要之群組或小組的常見作法是將檔案移出小組，並將它們儲存在其他位置，例如做為存放庫或封存的 SharePoint 文件庫。 這項作法是以舊版的功能儲存在檔案和資料夾內，並透過電子郵件進行通訊。

下表概述與群組和團隊相關聯的服務，以及每個服務中找到的主要內容類型：

|服務|內容類型|
|:------|:---------------|
|Teams|通道交談，通道中的檔案|
|Forms|調查架構和結果|
|OneNote|筆記本|
|Outlook|郵件和行事曆|
|Planner|專案狀態與任務資訊|
|自動功耗|工作流程|
|Power BI|資料、報表及儀表板|
|網頁上的專案|專案計劃|
|藍圖|藍圖|
|SharePoint|檔、清單、小組通道 wiki 資料|
|Stream|影片|
|Yammer|交談|

在刪除群組或小組時，也會刪除大部分相關聯的資源。 這包括資料流程中的部分例外狀況–這些例外狀況會保留，而且仍然歸上傳/記錄的人員所擁有，也就是在電源自動化中流動。 Web 上 Project 中的專案和藍圖資料會保留在 CD 中，而且可以個別還原。

群組和團隊會在虛刪除狀態的30天內保留，而且可以隨時還原。 不過，在30天之後，任何關聯的資源（如服務和內容）都會從 Microsoft 365 環境中完全清除。 由保留原則保護的任何內容仍可透過 eDiscovery 搜尋取得。

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>群組聯機服務的生命週期結束考慮

在刪除群組或小組時，小組和群組擁有者必須考慮三個重要區域。

**內容**

當團隊不再運作或存在時，是否需要保留內容？ 是否足以依賴 Microsoft 365 的保留功能，或是某些應用程式和服務中的部分內容未提供保留？ 內容是否需要保留以進行記錄管理目的，以供進行封存，或用於將來使用與參考的目的？

在封存或刪除任何小組之前，必須先提出這些問題，以避免任何可能的資料遺失。

**服務**

在各個應用程式和服務的內容之上，是否必須保持在目前的運作表單中？ 例如，Power BI report 是否需要繼續可供存取，是否需要在視覺摘要視圖中使用表單結果、清單是否 SharePoint 連結或內嵌在任何地方？

類似內容考慮，在刪除基礎群組之前，必須先提出這些問題，因為只是匯出內容可能不夠。

**客人**

當來賓被邀請給小組時，工作流程會在主機組織的 Azure Active Directory 中建立其身分識別，然後再將其新增至團隊。 當小組遭到刪除時，不會從 Azure Active Directory 中移除來賓，也就是 Microsoft 團隊環境中仍然存在的來賓。 當來賓無法存取未與其共用的群組、網站、小組或內容時，他們仍有可能會利用 Microsoft 團隊中的功能，例如發起聊天、語音和影片通話，以及使用應用程式。

小組或群組擁有者可以邀請外部使用者變成 Azure Active Directory 中的來賓，將其新增至小組，以及將其從小組中移除。 不過，小組擁有者無法從 Azure Active Directory 中移除來賓–這只可由全域系統管理員或使用者管理員執行。

因此，請務必執行來賓檢查，並瞭解在小組刪除時，是否需要從 Azure Active Directory 移除來賓。 來賓保留在目錄中的方式可能是有效的案例，例如一或多個其他小組的成員，或是使用其他 Microsoft 365 或 Azure 服務。

## <a name="teams"></a>Teams

小組特有的內容主要是以交談的形式。

無法使用原生 Microsoft 團隊功能複製或移動通道中的交談。 不過，您可以使用圖形 API 來匯出。

此外，如果將保留原則套用至小組，便會透過 eDiscovery 搜尋保留並提供交談。  (在 eDiscovery 搜尋中找到的專案可以匯出，但原始來源沒有任何內容或結構，只是個別的郵件。 ) 

### <a name="archiving-a-team"></a>封存小組

封存 [小組](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) 的好處是，它會提供小組的完整存取權，這樣使用者仍可流覽通道交談，也可在未使用的情況下開啟檔案。 此外，如果需要繼續處理，小組也可以 unarchived (例如在專案延伸) 中的情況。

當團隊以擁有者的方式封存時，會針對小組中的內容以及所選的 SharePoint 網站，將其設為唯讀的成員。 此項動作的目標是確保通道中的交談會以現有的狀態保留，以及檔案和 wiki 等 SharePoint 型內容。

在 SharePoint 網站中，沒有可見的變更，不過，當 Microsoft 365 群組的 SharePoint 型許可權群組設定為 [網站訪客層級] 時，不會對任何檔或清單進行任何變更。 這包括小組的 OneNote 筆記本，因為這是儲存在 SharePoint 網站內的網站資產庫中。

當您封存小組時，基本的 Microsoft 365 群組仍會受制于到期原則 (如果設定) ，也就是擁有者必須繼續更新團隊。

當團隊的通道交談和 SharePoint 網站內容設定為唯讀時，其他關聯服務不會套用相同的功能：

- 您仍然可以建立、修改和刪除規劃器桶和任務
- 表單仍可接收提交
- Outlook 信箱仍可接收電子郵件
- Power BI 儀表板、報告和資料仍可修改
- 專案和路線圖仍可在 web 上的 Project 中編輯
- 影片仍可在資料流程中上傳、修改和刪除
- 仍可建立、修改和刪除流量，但會繼續執行 (但如果需要將郵件張貼至封存) 小組的通道，也會失敗

## <a name="forms"></a>Forms

雖然表單可以從個別帳戶移至群組，但無法將它移動或複製到另一個群組。 當小組已刪除時，表單有三個可用選項。

**複製表單**

您可以將表單 [共用成範本](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)，讓其他使用者可以將它複製到自己的帳戶或群組。 這不會保留結果提交中的資料;僅限表單結構（如問題和設定）。

**將結果匯出至試算表**

如果需要保留表單回應的資料，可將 [結果匯出至 Excel 試算表，以](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)達到此目的。 這只會將問題及其回應當做資料匯出，不包含表單所建立的圖形。


**刪除表單**

雖然刪除群組也會導致刪除任何關聯的表單，但是群組成員可以直接將 [其刪除](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) ，而不是群組的擁有者–但這是手動步驟，不會提供任何額外的利益。

## <a name="onenote"></a>OneNote

包含在群組中的 OneNote 筆記本儲存于關聯 SharePoint 網站中的網站資產庫。 雖然筆記本檔案有時候會分散在多個個別的檔案中，但無法直接複製與開啟。 相反地，必須使用 OneNote 2016 移動或匯出 OneNote 筆記本的內容。

**將頁面及區段移至另一個筆記本**

[將頁面或區段個別移至另一個筆記本](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) ，可讓擁有者有機會清除其資料，並只採取需要保留的功能。

**將整個筆記本當做套件匯出**

如果整個筆記本必須保留現有的結構，則可以將它 [匯出為 OneNote 的套件](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) 檔案，然後匯入到新的位置。 您也可以使用這種方法，將內容保留在單一檔案中，而不是保留現有的多檔結構。

**列印為 PDF**

在某些筆記本內容必須保留以供參考或記錄的情況下，個別頁面可 [列印到 PDF，並儲存在其他位置](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。

## <a name="mailbox-and-calendar"></a>信箱和行事曆

使用群組相關聯的信箱並不常見，即使已在小組通道內執行許多交談也是一樣。 信箱只會儲存直接以電子郵件傳送給它的電子郵件，不包括直接傳送到通道的電子郵件。

在某些情況下，儲存在信箱內的電子郵件，只會是會議、Planner 任務更新及其他應用程式或系統產生郵件的通知。 請務必檢查信箱的內容，以判斷是否應該保留或刪除內容。

若將保留原則套用至 Exchange，電子郵件和行事曆專案便會透過 eDiscovery 搜尋保留並提供。

**匯出郵件和行事曆**

小組或群組成員可以將 [信箱和行事曆的內容匯出至 Outlook 資料/個人儲存區 (PST) ](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)檔案。 您可以將此檔案儲存在其他地方，也可以將內容匯入至不同的信箱。 不建議使用，因為 PST 檔案的內容無法搜尋，也不會在 Outlook 中開啟，而且檔案本身可能會損毀。

**IT-執行內容遷移**

管理員可以使用協力廠商工具，在沒有任何使用者干涉的情況下，在信箱間遷移電子郵件和行事曆內容。 一個可能的儲存位置是專門建立以充當群組信箱內容「封存」的共用信箱。

## <a name="planner"></a>Planner

每個群組或小組可以有多個計畫。 在脫離程式期間很重要，以確保每個計畫都會針對其內容是否保留進行處理。 就像其他產品一樣，有數種方法可以下架規劃中的內容。

**將計畫匯出至試算表**

如果只需要保留記錄保留用途的計畫複本，最簡單的方法是將 [方案匯出至 Excel 試算表](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。 這是單向的動作，因為沒有從試算表匯入計畫的選項。

> [!IMPORTANT]
> 將計畫匯出至 Excel 會在計畫內取得大部分資訊，但不會包含批註、連結或檔案。

**將任務複製並移動到另一個計畫**

雖然這似乎是一種解決方案，但只有在相同群組內的 [計畫間複製或移動](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) 個別工作，否則會在刪除與方案關聯的群組時，對福利產生否定。

**複製整個計畫**

您也可以 [複製整個計畫](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。 不過，這不能是現有的群組，甚至是在相同的群組內。 複製計畫將會建立新的群組。 此外，複製整個計畫時，不會包含批註、工作分派、連結、附件或日期。

## <a name="power-automate"></a>自動功耗

在 [自動] 與群組或小組相關的流程中建立的流程不屬於群組，而是由建立者所擁有，只是與其他使用者和群組共用。 當群組或小組遭到刪除時，不會受到影響。

**變更流程的擁有權**

如果工作流程需要繼續運作，任何擁有者都只可以新增其他使用者或 Microsoft 365 群組做為擁有者。

**匯出流程**

如果工作流程不需要繼續運作，但需要保留以供將來使用，則可以將它 [匯出為](https://flow.microsoft.com/blog/import-export-bap-packages/) 檔案，然後再匯入。

## <a name="power-bi"></a>Power BI

Power BI 資料和工作區可以獨立于群組和團隊運作，如其他工作負載提供不同的 offboarded 方式。

**將報表複製到另一個工作區**

如果報表需要在群組或小組的生命週期內保留其功能狀態，則可以 [從現有的工作區將它複製到 POWER BI 中的另一個工作區](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)。

**從儀表板或報表匯出資料**

或者，如果報表不再需要使用中，但資料必須保留，則可以 [匯出至 Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)。

## <a name="project"></a>Project

在 web 上的 Project 中建立的專案和路線圖可以與 Microsoft 365 群組相關聯，並提供與 Power BI 類似的脫離方式。

**將專案指派給另一個群組**

如果專案需要在群組或小組的生命週期內保留其功能狀態，則可以使用 Dynamics 365 系統管理中心將其 [指派給不同的 Microsoft 365 群組](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 。

**從專案或藍圖匯出資料**

您可以使用 Dynamics 365 系統管理中心，將 [專案中的使用者資料匯出](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 至試算表，或是使用 PowerShell 腳本可以將資料匯出至 project file (。MPP) 和 XML 檔案格式。

## <a name="sharepoint"></a>SharePoint
「小組通道」中的所有檔案都會儲存在相關群組 SharePoint 網站的文件庫中。 在某些情況下，檔以外的內容可能會存在於 SharePoint 中，例如清單或頁面。
檔案一般會儲存在 SharePoint 網站中的三個主要位置：

- 頁面-網站頁面庫
- 頁面中使用的圖像–網站資產庫
- 通道中的檔案–文件庫
- Wiki 頁面-小組 Wiki 資料庫

如果網站上有一個或多個子網站，則每個子網站都必須重複執行脫離程式。 如果團隊包含專用通道，則每個通道都有個別的 SharePoint 網站。

當您從群組或小組中移除檔案時，請務必注意，這些檔案可能與不是群組或小組成員的使用者共用， (不論組織的內部或外部) ，也可能會對他們進行即將進行的變更。

**下載檔案**

如以上所述的其中一個文件庫中儲存的檔案 SharePoint，可將這些檔案 [下載到本機電腦](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。

**移動檔**

此外，檔案也可以移至 SharePoint 中的另一個位置，例如在不同網站中的文件庫。
參考： https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**匯出清單** 儲存在 SharePoint 清單內的資料可 [匯出至 Excel 試算表](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)，並再次匯入至另一個網站中的清單。

或者，您可以使用協力廠商工具來遷移網站間的清單，以保留函數、清單視圖、格式及其他屬性。

**「匯出」 wiki 檔案**

小組通道內的 Wiki 內容會儲存在相關聯 SharePoint 網站的專用文件庫中的 HTML 格式檔案。 他們無法輕易匯出及匯入另一個通道 wiki，但是可以轉換成 HTML 檔案，並以網頁方式開啟。

## <a name="microsoft-stream"></a>Microsoft Stream

如同電源自動化，與群組或小組相關聯之資料流程中的影片實際上不是歸群組所有，而且在刪除群組時不會被刪除。 資料流程中的影片是由上傳或建立影片的人員所擁有，即使他們將使用者或群組新增為擁有者也是一樣。 在小組管道記錄的會議情況也是如此。它們是由啟動錄製的人員所擁有。

**新增其他擁有者**

當影片保留在資料流程中時，不論群組刪除為何，原始擁有者可以 [與其他使用者和群組共用影片，甚至將其新增為擁有](https://docs.microsoft.com/stream/portal-edit-video)者。

**下載影片**

在影片不需要保留在資料流程中或必須儲存在其他位置（例如記錄管理系統）的情況下，擁有者可以在 [本機上下載](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

與 Microsoft 小組中的交談不同的是，Yammer 提供使用者和系統管理員選項來移動或匯出交談。

**將交談移至另一個群組或群組**

任何使用者都可以將交談移至其他 Yammer 群組，而不只是擁有者或系統管理員。 在 [傳統的 yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)中也可以這種方式，以及 [新的 yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) 介面。

**匯出網路資料**

Yammer 網路系統管理員可以執行 [網路資料的匯出](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)，但這樣做會匯出整個網路的所有交談。 產生的匯出但是會列出群組識別碼，因此可以根據這種方式來篩選交談。
