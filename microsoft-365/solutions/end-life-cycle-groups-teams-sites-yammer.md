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
recommendations: false
description: 群組、小組和 Yammer 的生命週期選項結束。
ms.openlocfilehash: fccdf838b7ebec6a1ab1fae2f709824bfbd3b6d1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538828"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>群組、小組和 Yammer 的生命週期選項結束

Microsoft 365群組和 Microsoft Teams 會使用多個連線的服務。 刪除群組或小組時，也會刪除聯機服務中的大部分資訊。 本文說明在刪除之前，將資訊移出群組或小組以保留資訊的選項。

不再需要之群組或小組的常見作法是將檔案移出小組，並將其封存在另一個位置（例如 SharePoint 文件庫）。 這種作法是以舊版的功能儲存在檔案和資料夾中，並透過電子郵件進行通訊。

下表概述與群組和團隊相關聯的服務，以及每個服務中找到的主要內容類型：

|服務|內容類型|
|:------|:---------------|
|Teams|通道交談，通道中的檔案|
|Forms|調查架構和結果|
|OneNote|筆記本|
|Outlook|郵件和行事曆|
|Planner|Project 狀態與任務資訊|
|Power Automate|工作流程|
|Power BI|資料、報表及儀表板|
|網頁上的 Project|Project 方案|
|藍圖|藍圖|
|SharePoint|檔、清單、Teams 通道 wiki 資料|
|Stream|影片|
|Yammer|交談|

在刪除群組或小組時，也會刪除大部分相關聯的資源。 例外狀況包括：

- 資料流程中的影片會保留並由上傳/錄製的人員所擁有
- Power Automate 中的流程會保留，且由建立者所擁有。
- 網路 Project 中的 Project 和藍圖資料會保留在 cd 中，而且可以個別還原。

群組和團隊會在虛刪除狀態的30天內保留，而且可以隨時還原。 不過，在30天之後，會從 Microsoft 365 環境清除任何相關聯的資源，例如服務和內容。 由保留原則保護的任何內容仍可透過 eDiscovery 搜尋取得。

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>群組聯機服務的生命週期結束考慮

在刪除群組或小組時，小組和群組擁有者必須考慮三個重要區域。

**內容**

當團隊不再存在時，是否需要保留內容？ 是否足以依賴 Microsoft 365 的保留功能，或是某些應用程式和服務中的部分內容不會提供保留？ 內容是否需要保留以進行記錄管理、封存或日後使用，以及參考的目的？

為了避免任何可能的資料遺失，在封存或刪除任何小組之前，必須先提出這些問題。

**服務**

內容是否需要保留在目前的運作表單中？ 例如，Power BI 報表是否需要繼續存取？ 表單結果是否需要在視覺摘要視圖中使用？ SharePoint 是連結或內嵌在任何地方的清單嗎？

在刪除基礎群組之前，必須先提出這些問題，因為匯出內容可能不夠。

**客人**

當來賓被邀請給小組時，會在主機組織的 Azure Active Directory 中建立來賓帳戶，然後再將其新增至小組。 當小組遭到刪除時，不會將來賓從 Azure Active Directory 中移除。 當來賓無法存取未與其共用的群組、網站、小組或內容時，他們仍然可能使用 Microsoft Teams 等功能，例如開始交談、語音和影片通話，以及使用應用程式。

小組或群組擁有者可以從組織外部邀請某人，以將其新增至小組，以成為 Azure Active Directory 中的客人。 不過，小組擁有者無法從 Azure Active Directory 中移除訪客。 只有全域系統管理員或使用者管理員才能執行帳戶刪除。

請務必執行來賓檢查，並瞭解是否需要在小組成員刪除時從 Azure Active Directory 中移除來賓。 來賓保留在目錄中的方式可能是有效的案例，例如，其他小組的成員或使用其他 Microsoft 365 或 Azure 服務。

## <a name="teams"></a>Teams

Teams 特有的內容主要是以交談的形式。

無法使用原生 Microsoft Teams 功能複製或移動通道中的交談。 不過，您可以使用 Graph API 匯出。

此外，如果將保留原則套用至 Teams，便會透過 eDiscovery 搜尋保留並使用交談。 使用高級 eDiscovery，您可以[重建 Teams 聊天交談](/microsoft-365/compliance/conversation-review-sets)。


### <a name="archiving-a-team"></a>封存小組

封存 [小組](/microsoftteams/archive-or-delete-a-team) 的好處是，它會提供小組的完整存取權。 即使使用者未使用中，使用者仍可流覽通道交談及開啟檔案。 此外，如果有必要繼續處理團隊 (例如，如果專案是) 擴充的，就可以 unarchived。

當小組以擁有者的方式封存時，它會為小組中的內容，將其設為唯讀，而且如果選取此項，則關聯的 SharePoint 網站。 此項動作的目標是確保通道中的交談會以現有的狀態保留，以及檔案和 wiki 等 SharePoint 型內容。

在 SharePoint 網站中，沒有可見的變更。 不過，不會對任何檔案或清單進行任何變更，因為 Microsoft 365 群組的 SharePoint 許可權已設定為 **網站訪客**。 這包括小組的 OneNote 筆記本，該筆記本儲存于 SharePoint 網站內的網站資產庫。

當您封存小組時，基礎 Microsoft 365 群組仍會受制于到期原則 (如果設定) ，則擁有者必須繼續更新團隊。

當團隊的通道交談和 SharePoint 網站內容設定為唯讀時，與其他相關服務不會套用相同的功能：

- 也可以建立、修改和刪除規劃器桶和工作。
- 表單仍可接收提交。
- Outlook 信箱仍可接收電子郵件。
- Power BI 的儀表板、報表和資料仍可修改。
- 專案和路線圖仍可在網頁 Project 中編輯。
- 影片仍可在資料流程中上傳、修改和刪除。
- Power Automate 中的資料流程仍可建立、修改、刪除，並會繼續執行。  (如果需要將訊息張貼至已封存小組的通道，它們會失敗。 ) 

## <a name="forms"></a>Forms

雖然表單可以從個別帳戶移至群組，但無法將它移動或複製到另一個群組。 當小組已刪除時，表單有三個可用選項。

**複製表單**

您可以將表單 [共用成範本](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)，讓其他使用者可以將它複製到自己的帳戶或群組。 這不會保留結果提交中的資料;僅限表單結構（如問題和設定）。

**將結果匯出至試算表**

如果必須保留表單回應的資料，可將[結果匯出至 Excel 試算表](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)來完成。 這只會將問題及其回應當做資料匯出，不包含表單所建立的圖形。

**刪除表單**

當刪除群組時，也會導致刪除任何關聯的表單，群組成員可以 [直接將其刪除](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) ，而不是群組的擁有者。 不過，這是一個不會提供任何其他好處的手動步驟。

## <a name="onenote"></a>OneNote

包含在群組中的 OneNote 筆記本儲存于關聯 SharePoint 網站中的網站資產庫。 雖然筆記本檔案有時候可以分散在多個個別的檔案中，但無法獨立複製及開啟。 相反地，必須使用 OneNote 2016 移動或匯出 OneNote 筆記本的內容。

**將頁面及區段移至另一個筆記本**

[將頁面或區段個別移至另一個筆記本](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) ，可讓擁有者有機會清除其資料，並只採取需要保留的功能。

**將整個筆記本當做套件匯出**

如果整個筆記本必須保留現有的結構，則可以將它[匯出為 OneNote 的套件](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309)檔案，然後匯入到新的位置。 相反地，您可以使用這種方法，將內容保留在單一檔案中，而不是現有的多檔結構。

**列印為 PDF**

在某些筆記本內容必須保留以供參考或記錄的情況下，個別頁面可 [列印到 PDF，並儲存在其他位置](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。

## <a name="mailbox-and-calendar"></a>信箱和行事曆

使用與群組相關聯的信箱並不常見，即使在小組通道內已進行許多交談也是一樣。 信箱只會儲存直接以電子郵件傳送給它的電子郵件，而不包含直接傳送到通道的電子郵件。

在某些情況下，儲存在信箱內的電子郵件可能是會議、Planner 任務更新及其他應用程式或系統所產生郵件的通知。 請務必檢查信箱的內容，以判斷是否應該保留或刪除內容。

如果在 Exchange 中套用保留原則，電子郵件和行事曆專案會透過 eDiscovery 搜尋加以保留並可用。

**匯出郵件和行事曆**

小組或群組成員可以將[信箱和行事曆的內容匯出至 Outlook 資料/個人儲存體 (PST) ](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)檔案。 您可以將此檔案儲存在其他地方，也可以將內容匯入至不同的信箱。 因為 PST 檔案的內容無法在 Outlook 中開啟，也不建議使用，而且檔案本身可能會損毀。

**IT-執行內容遷移**

管理員可以使用協力廠商工具，在沒有任何使用者干涉的情況下，在信箱間遷移電子郵件和行事曆內容。 一個可能的儲存位置是專門建立以充當群組信箱內容「封存」的共用信箱。

## <a name="planner"></a>Planner

每個群組或小組可以有多個計畫。 在離補程式期間很重要，以確保每個計畫的保留要求都有問題。 就像其他服務一樣，在 Planner 中有幾種方式可用於離板內容。

**將計畫匯出至試算表**

如果只需要保留記錄保留用途的計畫複本，最簡單的方法是將[計畫匯出至 Excel 試算表](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。 這是單向動作-從試算表匯入計畫沒有任何選擇。

> [!IMPORTANT]
> 將計畫匯出至 Excel 會在計畫內取得大部分資訊，但不會包含批註、連結或檔案。

**將任務複製並移動到另一個計畫**

將工作複製或移動至其他計畫似乎是方案，個別的工作只能在相同群組內的 [計畫間複製或移動](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) 。 若要刪除與方案關聯的群組，這不會備份資料。

**複製整個計畫**

您也可以 [複製整個計畫](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。 無法對現有的群組進行複製。 複製計畫將會建立新的群組。 此外，複製整個方案時，不會包含批註、工作分派、連結、附件或日期。

## <a name="power-automate"></a>Power Automate

在 Power Automate 中建立並與群組或小組相關聯的資料流程不屬於群組。 它們是由建立者所擁有，只與其他使用者和群組共用。 當群組或小組遭到刪除時，不會受到影響。

**變更流程的擁有權**

如果流程需要繼續運作，任何擁有者都可以新增其他使用者或 Microsoft 365 群組做為擁有者。

**匯出流程**

如果流程不需要繼續運作，但需要保留以供將來使用，則可以將它 [匯出為](https://flow.microsoft.com/blog/import-export-bap-packages/) 檔案，然後再匯入。

## <a name="power-bi"></a>Power BI

Power BI 資料和工作區可以獨立于群組和團隊運作，類似于其他工作負載提供不同的 boarded 的方式。

**將報表複製到另一個工作區**

若您在刪除群組或小組之後需要報表，可以將其[從現有的工作區複製到 Power BI 中的其他工作區](/power-bi/connect-data/service-datasets-copy-reports)。

**從儀表板或報表匯出資料**

相反地，如果報表不再需要使用中，但資料必須保留，則可以將資料[匯出至 Excel](/power-bi/visuals/power-bi-visualization-export-data)。

## <a name="project"></a>Project

在 web Project 中建立的專案和路線圖會與 Microsoft 365 群組產生關聯，並具有離群的方式，類似于 Power BI。

**將專案指派給另一個群組**

如果專案需要在群組或小組的生命週期內保留其功能狀態，可將其[指派給不同的 Microsoft 365 群組](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project)。 這可以使用 Dynamics 365 系統管理中心完成。

**從專案或藍圖匯出資料**

您可以使用 Dynamics 365 系統管理中心，將 [專案中的使用者資料匯出](/project-for-the-web/export-user-data-from-project-for-the-web) 至試算表。 資料也可以匯出至 Project 檔案 (。MPP) 和 XML 檔案格式使用 PowerShell。

## <a name="sharepoint"></a>SharePoint

小組通道中的所有檔案都會儲存在相關聯群組的 SharePoint 網站中。 在某些情況下，檔以外的內容可能會存在於 SharePoint 中，例如清單或頁面。

檔案一般會儲存在 SharePoint 網站中的三個主要位置：

- 頁面-網站頁面庫
- 頁面中使用的圖像–網站資產庫
- 通道中的檔案–文件庫
- wiki 頁面– Teams wiki 資料庫

如果網站有一個或多個子網站，將需要針對每個子網站重複解除加入處理常式。 如果團隊包含專用通道，則每個通道都有個別的 SharePoint 網站。

從群組或小組中移除檔案時，請務必注意，這些檔案可能與不是群組或小組成員的使用者共用。 您可能想要將即將進行的變更傳遞給他們。

**下載檔案**

儲存在上述其中一個文件庫中 SharePoint 的檔案，都可以[下載到本機電腦](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。

**移動檔**

此外，檔案也可以[移至 SharePoint 中的另一個位置，例如在不同網站中的文件庫](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)。

**匯出清單**

儲存在 SharePoint 清單內的資料可[匯出至 Excel 試算表](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)，並重新匯入至另一個網站中的清單。

或者，您可以使用協力廠商工具來遷移網站間的清單，以保留函數、清單視圖、格式及其他屬性。

**「匯出」 wiki 檔案**

小組通道內的 Wiki 內容會儲存在相關聯 SharePoint 網站的專用文件庫中的 HTML 格式檔案。 他們無法輕易匯出及匯入另一個通道 wiki，但是可以轉換成 HTML 檔案，並以網頁方式開啟。

## <a name="microsoft-stream"></a>Microsoft Stream

如同 Power Automate，與群組或小組相關聯的資料流程實際上並未歸群組所有，也不會在刪除群組時刪除。 資料流程中的影片是由上傳或建立影片的人員所擁有，即使他們將使用者或群組新增為擁有者也是一樣。 錄製在 Teams 通道中的會議是由開始錄製的人員所擁有。

**新增其他擁有者**

因為在刪除群組時，影片會保留在資料流程中，所以原始擁有者可以 [與其他使用者和群組共用影片，甚至將其新增為擁有](/stream/portal-edit-video)者。

**下載影片**

在影片不需要保留在資料流程中或必須儲存在其他位置（例如記錄管理系統）的情況下，擁有者可以在 [本機上下載](/stream/portal-download-video)。

## <a name="yammer"></a>Yammer

與 Microsoft Teams 中的交談不同的是，Yammer 提供使用者和系統管理員選項來移動或匯出交談。

**將交談移至另一個群組或群組**

任何使用者都可以將交談移至另一個 Yammer 群組，而不只是擁有人或系統管理員。 在[傳統的 Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)和[新的 Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)介面中都可以這麼做。

**匯出網路資料**

Yammer 網路系統管理員[匯出網路資料](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 不過，這樣做會匯出整個網路的所有交談。 所產生的匯出會列出群組識別碼。 您可以根據此識別碼來篩選交談。

## <a name="related-topics"></a>相關主題

[移除離職員工和安全資料](/microsoft-365/admin/add-users/remove-former-employee)
