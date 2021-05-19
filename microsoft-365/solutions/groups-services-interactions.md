---
title: 群組服務互動
ms.reviewer: ''
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
description: 群組服務互動
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539200"
---
# <a name="groups-services-interactions"></a>群組服務互動

Microsoft 365群組為 Microsoft 365 平臺內的一些服務和工作負載提供了共同的結構，可為使用者提供連線的體驗。 在其核心中，有 Microsoft 365 群組提供：

-  (Azure AD) 管理成員資格的方式
- 郵件和交談的位置若要執行 (Exchange 信箱、Microsoft Teams Yammer) 
- 儲存 (SharePoint 的檔案位置) 
- 排程 (Exchange 的行事曆) 
- 用於 (OneNote 的記錄的捕獲筆記) 

在建立群組時，也會布建許多其他資源，但是直到第一次從服務存取後，才會顯示這些資源：

- 用於管理群組工作 (Planner) 的主機板
- 用於報告 (Power BI 的工作區) 
- 共用影片 (Microsoft Stream) 的區域
- 共用表單 (表單的區域) 

在 Microsoft 365，其他服務可以與 Microsoft 365 群組互動，以將其他功能和功能提供給群組成員。
這包括下列範例：

- 應用程式的 Power Apps
- 工作流程的 Power Automate
- 以瀑布式專案管理為基礎的網頁和藍圖 Project
- 以通道為基礎之交談的 Teams
- Yammer 感興趣的社區

## <a name="user-interactions-with-groups"></a>與群組的使用者互動

Microsoft 365群組可以從各種介面建立及管理，既包括系統管理員和使用者。 

### <a name="administrative-experiences"></a>管理體驗

管理員可以從一些工作負載系統管理中心、支援腳本的命令列介面，以及與 Graph API 互動的自訂應用程式，建立及管理 Microsoft 365 群組。 這只是 Yammer 群組的例外狀況，必須從 Yammer web 介面中建立。

**相關設定**

跨越可管理群組設定的各種管理介面，有數個重疊，您應該注意。

**Microsoft 365 系統管理中心**

在 Microsoft 365 系統管理中心中，預設會啟用群組的來賓存取權，就像允許擁有者新增來賓的能力一樣。 此系統管理中心中的群組沒有進一步的組織層級控制項可用。

**Azure AD 系統管理中心**

Azure AD 系統管理中心提供的控制措施是使用者是否可以建立群組或指派 Azure 入口網站的擁有者，以及到期及命名原則設定。

系統管理中心還提供許多來賓邀請控制措施，可超越 Microsoft 365 系統管理中心以外的程度，例如限制非擁有者是否也可以邀請來賓的能力。

**SharePoint**

SharePoint 網站是以擁有者、成員及訪客安全性群組的方式建立，其前兩個對應到其 Microsoft 365 群組。 雖然 SharePoint Online 網站的成員資格通常是由關聯的 Microsoft 365 群組管理，但不是雙向關聯。 Microsoft 365 群組層級成員資格的任何變更都會反映在 SharePoint 中，但如果 SharePoint 群組中的成員資格變更，則不會反映在 Microsoft 365 群組中。

### <a name="user-experiences"></a>使用者經驗

使用者可以從 Microsoft 365 中的數個服務建立群組，而且在其他使用者只能與群組共用。

下列服務允許使用者建立群組：
                         
Outlookweb SharePoint 資料流程 Microsoft Teams 的 Planner Project Yammer

**群組的建立限制**

控制小組的蔓延的常見方法是限制哪些使用者可以建立。 這只能透過限制建立群組來完成。 這樣做會影響從其他服務（可能為使用者必要）建立群組的能力。 Microsoft 365群組不支援限制從某些應用程式或服務建立群組，同時允許其他使用者的功能。

群組建立限制的體驗會因應用程式和服務而異：


|應用程式或服務|體驗|
|:-------------|:---------|
|Outlook|從 [人員] 頁面的新功能表移除 [**新增群組**] 選項|
|Planner|**新計畫** 說明已關閉群組建立功能，並提供將計畫新增至現有的群組|
|網頁和藍圖的 Project|**建立群組** 功能表說明群組建立限制，並建議使用現有的群組。|
|SharePoint|仍然可以建立未連接至群組的小組網站。|
|Stream|**群組** 選項不會出現在 [ **建立] 功能表** 底下。|
|Teams|使用者無法使用新的群組建立小組，但仍然可以建立利用現有群組的小組。<br><br>[**建立小組**] 按鈕會取代為 **群組中的 [建立小組**] 按鈕。|
|Yammer|[**建立群組**] 選項會從 [主要群組/社區] 導覽中移除。|

## <a name="services-interactions-with-groups"></a>與群組的服務互動

請參閱 Microsoft 365 海報中的群組，以取得不同群組類型的相關資訊、建立與管理的方式，以及少數的管理建議。

[![群組資訊圖的縮圖影像](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

下表提供 Microsoft 365 群組與各種服務互動的概覽：

|產品|功能|服務<br>是否存在沒有群組的情況？|服務是否可以<br>建立群組？|刪除<br>實例刪除群組？|
|:---|:---|:---|:---|:---|
|Azure AD|成員資格、群組控制項、來賓|是|是|是|
|Exchange|行事曆、信箱|是|是|是|
|表單|Form|是|否|否|
|OneNote|筆記本|是|否|否|
|Planner|工作面板|否|是|是|
|Power Apps 應用程式|應用程式|是|否|否|
|Power Automate|工作流程|是|否|否|
|Power BI (古典) |Workspace|否|是|是|
|Power BI (新) |Workspace|是|否|是|
|Project 網頁版|Project 計畫|是|是|否|
|藍圖|藍圖|是|是|否|
|SharePoint|網站|是|是|是|
|Stream|通道、影片|是|是|是|
|Teams|團隊|否|是|是|
|Yammer|群組|是|是|是|

當上表提供與 Microsoft 365 服務的群組互動的高層次概述時，您應該瞭解許多細微差別和複雜的情況。 下列各節將深入瞭解特定工作負載及其與群組的互動。

## <a name="azure-ad"></a>Azure AD

Azure AD 在 Microsoft 365 中提供基礎的身分識別管理功能。

**提供給群組的主要功能**

- 群組成員資格
- 命名原則
- 到期原則
- 客人
- 群組的建立限制

**Azure AD 是否可以建立群組？**

是的，可以從 Azure AD 建立 Microsoft 365 群組，既可以透過管理網頁入口網站，也可以透過 PowerShell 或 Graph API。

**Azure AD 是否存在沒有群組的情況？**

是的，Azure AD 執行的服務數目很多，與 Microsoft 365 群組沒有關系。 每個 Microsoft 365 群組都代表 Azure AD 中的一個物件。

**每個群組是否可以有多個 Azure AD 實例？**

否，Azure AD 只有一個實例。

**Azure AD 是否可以與多個群組相關聯？**

是的，因為 Azure AD 是提供群組成員資格服務的基礎平臺。

**Azure AD 與群組的關聯是否可以變更？**

否，Azure AD 是群組存在所在的基礎平臺。

**刪除此實例後，會刪除群組嗎？**

刪除 Azure AD 中的群組將會刪除相關的群組相關服務和內容。

## <a name="teams"></a>Teams

Teams 是一個以聊天為中心的工作區，可提供單一介面，以與各種 Microsoft 和協力廠商服務互動，以提升共同作業。

根據預設，當建立小組時，與 Microsoft 365 群組相關聯的信箱和行事曆會從 Exchange 中的全域通訊清單及 Outlook 中隱藏。 如果使用者想要在相同的 Microsoft 365 群組上使用 Outlook 和 Teams，系統管理員可以手動覆寫此方式。

**提供給群組的主要功能**

- 交談
- 通道 &] 索引標籤
- 會議

**可以 Teams 建立群組嗎？**

是的，建立新的小組將會建立新的 Microsoft 365 群組。 您也可以為目前沒有的群組建立小組。

**是否有小組沒有群組？**

否，不可能有小組沒有群組。

**每個群組可以有多個團隊嗎？**

否，小組和群組之間的關聯性是1:1。

**小組是否可以與多個群組相關聯？**

否，小組自身只能與單一群組相關聯。

**小組與群組的關聯是否可以變更？**

否，小組只會與其最初關聯的群組相關聯。

**刪除小組是否刪除群組？**

是，刪除 Microsoft Teams 中的團隊將會刪除群組、群組相關聯的服務和內容。

## <a name="exchange"></a>Exchange

Exchange Online 提供郵件、行事曆、連絡人及相關聯的功能。 在群組的內容中，只有單一資源與整個服務實例相關聯–而非相關聯。

**提供給群組的主要功能**

- 信箱和行事曆
- 能夠以電子郵件傳送所有群組成員
- 儲存體 eDiscovery 目的 Teams 通道交談、Planner 批註

**可以 Exchange 建立群組嗎？**

是的，您可以從 Exchange Online 系統管理中心，以及從 Outlook 中建立群組。 您也可以將 Exchange 通訊群組清單轉換成 Microsoft 365 群組。

**是否 Exchange 存在沒有群組的情況？**

是的，Exchange Online 提供許多服務，包括共用信箱和行事曆，沒有任何群組關聯。

**每個群組是否可以有多個 Exchange 信箱或行事曆實例？**

否，群組只能有單一 Exchange Online 信箱和行事曆。

**信箱和行事曆是否可以與多個群組相關聯 Exchange？**

否，信箱和行事曆與群組之間有1:1 的關係。 您可以與其他使用者或群組共用信箱，但這不會建立任何形式的服務關聯。

**Exchange 信箱或行事曆與群組的關聯是否可以變更？**

否，信箱和行事曆無法變更為不同的群組。 不過，您可以在 Outlook 中或使用協力廠商工具，將內容從一個信箱移至另一個信箱。

**刪除信箱會刪除群組嗎？**

是的，在 Exchange 中刪除信箱將會刪除群組相關聯的服務和內容。

## <a name="forms"></a>表單

表單提供 web 型問卷調查和測驗。

**提供給群組的主要功能**

- 表單的擁有權

**表單是否可以建立群組？**

否，表單無法建立群組。

**表單是否有沒有群組的功能？**

是的，您可以直接在使用者的帳戶中建立調查和測驗。

**每個群組可以有多個表單嗎？**

是的，可以有多個表單與一個群組相關聯。

**表單是否可與多個群組相關聯？**

否，表單只可與單一群組相關聯。

**表單與群組的關聯是否可以變更？**

否，表單與群組建立關聯 (，或從個別) 取得擁有權時，無法將它移到另一個群組中。

**刪除表單會刪除群組嗎？**

否，不可能從表單介面中刪除群組，只能從個別表單刪除。

## <a name="onenote"></a>OneNote

OneNote 是數位筆記本應用程式。 以群組建立的 OneNote 筆記本是關聯 SharePoint 網站中的檔案，而不是群組聯機服務。

**提供給群組的主要功能**

- 儲存在群組相關 SharePoint 庫中的共用筆記本 () 

**可以 OneNote 建立群組嗎？**

否，OneNote 應用程式無法建立群組。

**是否有沒有群組的 OneNote 筆記本？**

是，筆記本可以直接在 OneDrive 或其他共用位置建立。

**每個群組是否可以有多個 OneNote 筆記本？**

是的，預設會建立筆記本，而且可以新增其他人，但是來自群組相關服務的任何 OneNote 連結，都不會進入預設的筆記本。

**OneNote 的筆記本是否可以與多個群組產生關聯？**

否，筆記本會儲存在群組相關聯的 SharePoint 網站文件庫中，並從各種介面連結。 不過，您可以與其他群組共用，其方式與個人共用的方式相同。

**筆記本與群組的關聯是否可以變更？**

否，筆記本本身會與群組產生關聯，而且可以從其他群組聯機服務直接存取，但是可以在 OneNote 應用程式內，將內容從一個筆記本移至另一個。

**刪除筆記本刪除群組嗎？**

否，但如果刪除 OneNote 筆記本，某些群組相關服務中的連結可能會中斷。

## <a name="planner"></a>Planner

Planner 是輕量群組任務管理服務。

**提供給群組的主要功能**

- 管理群組任務的外掛程式

**Planner 是否可以建立群組？**

是的，建立計畫將會建立新的群組。

**Planner 面板是否不存在群組？**

否，計畫必須與群組產生關聯。

**每個群組可以有多個方案嗎？**

是，每個群組可以有多個方案。

**方案是否可以與多個群組相關聯？**

否，計畫只依靠群組成員資格來決定存取權。

**方案與群組的關聯是否可以變更？**

否，但是複製計畫會建立新的群組。

> [!NOTE]
> 任何其他應用程式所建立的群組不會自動顯示給使用者的 Planner。 若要先存取董事會，必須從另一個以群組為基礎的介面開啟它，例如 Outlook。

**刪除方案刪除群組嗎？**

是的，刪除方案將會刪除群組和群組相關聯的服務和內容。

## <a name="power-apps"></a>Power Apps

Power Apps 提供不含程式碼的應用程式開發畫布。

**提供給群組的主要功能**

- 可以將應用程式與群組共用，以執行及修改

**可以 Power Apps 建立群組嗎？**

否，Power Apps 無法建立 Microsoft 365 群組。

**是否 Power Apps 存在沒有群組的功能？**

是的，您可以在 Power Apps 內建立應用程式，並將其存放在建立者帳戶中，直到共用或發佈。

**每個群組可以有多個應用程式嗎？**

是的，可以有多個應用程式與群組共用。

**是否可以將應用程式與多個群組相關聯？**

是的，您可以使用多個群組共用應用程式。

**應用程式與群組的關聯是否可以變更？**

是的，因為 Power Apps 與 Microsoft 365 群組之間的關聯只會共用–該應用程式仍會與建立者一起使用。

> [!IMPORTANT]
> [群組必須先啟用安全性，應用程式才能與其共用](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。

**刪除應用程式時，是否要刪除群組？**

否，應用程式不會連線至群組，而不是與其共用。

## <a name="power-automate"></a>Power Automate

 (以前稱為 Microsoft Flow) 的 Power Automate 會提供工作流程和自動化服務。

**提供給群組的主要功能**

- 工作流程可以與群組共用，以執行及修改。

**可以 Power Automate 建立群組嗎？**

否，Power Automate 無法在與一個群組相關聯的內容中建立 Microsoft 365 群組。

不過，您可以建立流程來執行各種作業，例如建立 Azure AD 安全性群組或更新 Microsoft 365 群組的成員資格。

**是否有不含群組的流程？**

是的，流程可以在 Power Automate 內建立，且位於建立者帳戶內，直到共用或發佈。

**每個群組是否可以有多個資料流程？**

是的，可以有多個資料流程與群組共用。

**流程是否可以與多個群組相關聯？**

是，可以與多個群組共用流程。

**流程與群組的關聯是否可以變更？**

是的，因為 Power Automate 與 Microsoft 365 群組之間的關聯只會共用–該流程仍會與建立者一起存在。

**刪除流程會刪除群組嗎？**

否，像 Power Apps，資料流程並未連接至群組，而不是與其共用。

## <a name="power-bi-classic"></a>Power BI (古典) 

Power BI 提供互動式資料導向儀表板和報表。

**提供給群組的主要功能**

- 資料包告

**可以 Power BI 建立群組嗎？**

是的，建立傳統的工作區將會建立 Microsoft 365 群組。

**是否有不含群組的 Power BI 傳統工作區？**

否， [Power BI 中的傳統工作區必須與群組產生關聯](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。

**每個群組是否可以有多個 Power BI 工作區？**

否，傳統的工作區和群組之間的關係為1:1。

**工作區是否可以與多個群組相關聯？**

從技術上而言，在使用群組建立傳統的工作區時，內容可以與使用者和安全性群組在群組外共用。

**工作區與群組的關聯是否可以變更？**

否，傳統的工作區本身會與群組產生關聯，但是可以在 Power BI 介面內將內容移至另一個工作區，或是在本機上匯出內容。

**刪除工作區後，是否要刪除群組？**

是，在 Power BI 中刪除工作區將會刪除群組和群組相關聯的服務和內容。

## <a name="power-bi-new"></a>Power BI (新) 

Power BI 提供互動式資料導向儀表板和報表。

在 Power BI 中建立新的工作區時，不會建立 Microsoft 365 群組，以任何其他方式建立群組，會在 Power BI 中建立新的 (非傳統) 的工作區。

**提供給群組的主要功能**

- 資料包告

**可以 Power BI 建立群組嗎？**

不能，無法從新的 Power BI 介面建立 Microsoft 365 群組。

**是否有不含群組的新 Power BI 工作區？**

是的，您可以在 Power BI 中建立報表和工作區，而不會與 Microsoft 365 群組相關聯。

**每個群組是否可以有多個工作區？**

是的，[可透過單一群組共用 Power BI 所建立的多個工作區](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。

**工作區是否可以與多個群組相關聯？**

否，Power BI 所建立的工作區只能與單一群組相關聯。

**工作區與群組的關聯是否可以變更？**

[是] 和 [否]。 由 Power BI 所建立的工作區一次只能與一個群組相關聯，但隨時可以變更關聯。 群組 Power BI 中所建立的工作區會永久關聯至該群組。

**刪除工作區後，是否要刪除群組？**

是，在 Power BI 中刪除工作區將會刪除群組和群組相關聯的服務和內容。

## <a name="project-for-the-web"></a>Project 網頁版

Project 網頁提供建立專案計劃、甘特圖及路標的功能。
提供給群組的主要功能。

- Project 方案

**網頁可以 Project 建立群組嗎？**

是的，您可以直接從網頁 Project 建立新的 Microsoft 365 群組。

**是否有沒有群組的專案？**

是的專案可以存在，但不會與 Microsoft 365 群組產生關聯，但是任務的指派需要群組關聯。

**每個群組是否可以有多個專案？**

是的，您可以在單一群組中連接多個專案。

**專案是否可以與多個群組相關聯？**

否，專案只能與單一群組相關聯。

**專案與群組的關聯是否可以變更？**

否，建立與群組的關聯之後，就無法變更。

**刪除專案時是否刪除群組？**

否，在網站的 Project 中刪除專案不會刪除群組。

## <a name="roadmap"></a>藍圖

藍圖提供使用 web 和 Project Online Project 建立專案藍圖的功能。

**提供給群組的主要功能**

- Project 路線圖

**藍圖是否可以建立群組？**

是的，您可以直接從藍圖建立新的 Microsoft 365 群組。

**是否有沒有群組的藍圖？**

是的，路線圖可以存在，而不與 Microsoft 365 群組相關聯，但是共用藍圖需要群組關聯。

**每個群組是否可以有多個路線圖？**

是的，您可以將多個藍圖連線到單一群組。

**藍圖是否可以與多個群組相關聯？**

否，藍圖只會與單一群組相關聯。

**藍圖與群組的關聯是否可以變更？**

否，建立與群組的關聯之後，就無法變更。

**刪除藍圖之後刪除群組嗎？**

否，刪除藍圖不會刪除群組。

## <a name="sharepoint"></a>SharePoint

SharePoint 是以網路為基礎的內容管理平臺，可提供許多 Microsoft 365 服務的儲存服務等功能。

**提供給群組的主要功能**

- 文件庫
- 存放 OneNote 筆記本的存放庫
- Teams wiki 檔案的儲存體

**可以 SharePoint 建立群組嗎？**

是的，在 SharePoint 中建立小組網站時，預設會建立 Microsoft 365 群組。 您也可以建立群組，並選擇性地建立現有網站的團隊。

**是否有沒有群組的 SharePoint 網站？**

是的，SharePoint 提供許多非群組相關的服務和網站，例如通訊和 hub 網站。 

**每個群組可以有多個網站嗎？**

否，每個群組只能有一個網站。 Teams 中的專用通道使用未連接至群組的其他網站。

**是否可以將網站與多個群組相關聯？**

技術否，但在使用群組建立網站時，內容可以與其他群組共用。

**網站與群組的關聯是否可以變更？**

否，網站本身會與群組產生關聯，但是可以在 SharePoint 介面內，透過在本機匯出內容，或使用協力廠商工具，將內容移至介面中的另一個網站。

**刪除網站刪除群組嗎？**

是，在 SharePoint 中刪除網站會刪除群組和群組相關聯的服務和內容。

## <a name="stream"></a>Stream

Microsoft Stream 是一種影片主控和共用平臺。

**提供給群組的主要功能**

- 影片儲存體
- 會議錄製 Teams
- 影片通道

**Stream 是否可以建立群組？**

是的，您可以直接從 Stream 建立新的 Microsoft 365 群組。

**是否有不含群組的資料流程？**

是的，視頻通道和影片可以存在於 Stream 中，但不會與群組產生關聯。

**每個群組是否可以有多個影片和通道？**

是的，每個群組中可以有多個影片和頻道。

**影片或通道是否可以與多個群組產生關聯？**

是的，雖然使用群組建立影片或通道，但可與其他群組共用。

**與其群組的關聯是否可以變更？**

是和否;Stream 中的影片是由原始的上載程式或會議錄製器所擁有，因此可以與任何群組相關聯，但是影片通道只會與其最初建立所在的群組相關聯。

**刪除影片或頻道會刪除群組嗎？**

否，刪除影片或頻道不會刪除群組。 不過，在 Stream 中刪除群組本身會刪除與群組相關聯的服務和內容，但實際的影片除外。

## <a name="yammer"></a>Yammer

Yammer 是一種企業社交平臺，可促進組織內部及組織之間的社區參與。

在 Yammer 中建立群組 (以前稱為「群組」 ) 會建立信箱，但目前卻不會使用此功能。

與 Yammer 相關聯的 Microsoft 365 群組無法與 Microsoft Teams 中的小組一起使用。

**提供給群組的主要功能**

- 交談區域

**可以 Yammer 建立 Microsoft 365 群組嗎？**

是的，在 Yammer 中建立新群組時，會建立新的 Microsoft 365 群組，如果已連線平臺，而且使用者具備建立群組的能力。

在 Yammer 自身以外的任何介面或服務中，都不能建立具有相關 Microsoft 365 群組的 Yammer 群組。

**Yammer 群組是否存在沒有 Microsoft 365 群組？**

是的，您可以建立沒有 Microsoft 365 群組的 Yammer 群組。

如果 Yammer 平臺未連接至 Microsoft 365 群組，或使用者沒有建立 Microsoft 365 群組的能力，Yammer 群組建立時不會有 Microsoft 365 群組關聯。

**每個 Microsoft 365 群組可以有多個 Yammer 群組嗎？**

否，Yammer 群組與 Microsoft 365 群組之間的關聯性是1:1。

**Yammer 群組是否可以與多個 Microsoft 365 群組相關聯？**

否，Yammer 群組只會與單一 Microsoft 365 群組相關聯。 您可以與其他 Yammer 群組共用或移動公告。

**Yammer 群組與 Microsoft 365 群組的關聯是否可以變更？**

否，Yammer 群組只會與其原來關聯的 Microsoft 365 群組相關聯。

**刪除 Yammer 群組是否刪除 Microsoft 365 群組？**

是，在 Yammer 中刪除群組將會刪除相關的 Microsoft 群組和群組相關的服務和內容。

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)