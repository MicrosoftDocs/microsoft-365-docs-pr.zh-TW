---
title: 稽核記錄中的詳細內容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: 本文提供匯出 Office 365 審計記錄檔結果時所包含之其他屬性的說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a82b0d1c651db166ea5a8cb370383d36b6d37e5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035705"
---
# <a name="detailed-properties-in-the-audit-log"></a>稽核記錄中的詳細內容

當您從安全性 & 合規性中心匯出審計記錄搜尋的結果時，您可以選擇下載符合搜尋準則的所有結果。 若要執行此動作，請選取 [**匯出結果** \> ] [**審計記錄搜尋**] 頁面上的 [**下載所有結果**]。 如需詳細資訊，請參閱[搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。
  
 當您匯出審計記錄搜尋的所有結果時，會將統一審核記錄中的原始資料複製到您的本機電腦上下載的逗號分隔值（CSV）檔案。 此檔案包含名為**AuditData**欄中每個審計記錄的其他資訊。 此資料行包含來自審計記錄檔之多個屬性的多重值屬性。 此多重值屬性中的每個**屬性：值**組合都是以逗號分隔。 
  
下表說明多重屬性**AuditData**欄中所包含的屬性（取決於發生事件的服務）。 **具有此屬性欄的 Office 365 服務會**指出包含屬性的服務和活動類型（使用者或系統管理員）。 如需這些屬性的詳細資訊，或是本主題中可能未列出的屬性，請參閱[Management ACTIVITY API Schema](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以在 Excel 的 Power Query 中使用 JSON 轉換功能，將**AuditData**欄分割成多個欄，使每個屬性都有自己的資料行。 這樣您就可以排序及篩選一或多個屬性。 若要瞭解如何執行這項操作，請參閱[匯出、設定及查看審核記錄](export-view-audit-log-records.md)檔。 
  
|**屬性**|**描述**|**具有此屬性的 Microsoft 365 服務**|
|:-----|:-----|:-----|
|演員|執行動作的使用者或服務帳戶。|Azure Active Directory|
|AddOnName|已新增、移除或更新小組中的附加元件的名稱。 Microsoft 小組中的附加元件類型為 bot、連接器或 tab 鍵。|Microsoft Teams|
|AddOnType|已新增、移除或更新的小組中的附加元件類型。 下列值表示附加元件的類型。  <br/> **1** -表示 bot。<br/> **2** -表示連接器。<br/> **3** -表示 tab 鍵。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory 事件的類型。 下列值表示事件的類型。  <br/> **0** -表示帳戶登入事件。<br/> **1** -表示 Azure 應用程式安全性事件。|Azure Active Directory|
|ChannelGuid|Microsoft 小組通道的識別碼。 通道所在的團隊是由**TeamName**和**TeamGuid**屬性識別。|Microsoft Teams|
|ChannelName|Microsoft 小組通道的名稱。 通道所在的團隊是由**TeamName**和**TeamGuid**屬性識別。|Microsoft Teams|
|用戶端|用於登入事件的用戶端裝置、裝置 OS 和裝置瀏覽器（例如，Nokia Lumia 920;Windows Phone 8;IE Mobile 11）。|Azure Active Directory|
|ClientInfoString|用於執行作業的電子郵件客戶程式資訊，例如瀏覽器版本、Outlook 版本及行動裝置資訊|Exchange （信箱活動）|
|ClientIP|記錄活動時所使用之裝置的 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。<br/><br/> 針對某些服務，此內容中顯示的值可能是受信任應用程式的 IP 位址（例如，在 web 應用程式上的 Office）代表使用者呼叫服務，而不是執行活動之人員所使用之裝置的 IP 位址。 <br/><br/>此外，針對執行 Azure Active Directory 相關事件的系統管理員活動（或系統帳戶所執行的活動），未記錄 IP 位址，且 ClientIP 屬性的值為`null`。 |Azure Active Directory、Exchange SharePoint|
|CreationTime|使用者執行活動時的日期和時間（隨用通用時間（UTC））。|全部|
|DestinationFileExtension|複製或移動之檔案的副檔名。 此屬性只會針對 FileCopied 和 FileMoved 使用者活動顯示。|SharePoint|
|Destinationfilename 檔案|複製或移動的檔案名。 此屬性只會針對 FileCopied 及 FileMoved 動作顯示。|SharePoint|
|DestinationRelativeUrl|複製或移動檔案所在之目的地資料夾的 URL。 **SiteURL**、 **DestinationRelativeURL**及**destinationfilename 檔案**屬性的值組合，就是**ObjectID**屬性的值，也就是複製之檔案的完整路徑名稱。 此屬性只會針對 FileCopied 和 FileMoved 使用者活動顯示。|SharePoint|
|EventSource|識別 SharePoint 中發生的事件。 可能的值為**SharePoint**和**ObjectModel**。|SharePoint|
|ExternalAccess|若為 Exchange 系統管理員活動，請指定此 Cmdlet 是由組織中的使用者、Microsoft datacenter 人員或資料中心服務帳戶，還是由委派的系統管理員執行。 值**為 False**表示您組織中的人員已執行 Cmdlet。 值**True**表示此 Cmdlet 是由資料中心人員、資料中心服務帳戶或委派的管理員執行。  <br/> 在 [Exchange 信箱] 活動中，指定是否由組織外部的使用者存取信箱。|Exchange|
|ExtendedProperties|Azure Active Directory 事件的擴充屬性。|Azure Active Directory|
|ID|報表專案的識別碼。 識別碼可唯一識別報表專案。|全部|
|InternalLogonType|保留給內部使用。|Exchange （信箱活動）|
|ItemType|已存取或修改的物件類型。 可能的值包括**File**、 **Folder**、 **Web**、 **Site**、**承租人**和**DocumentLibrary**。|SharePoint|
|LoginStatus|識別可能發生的登入失敗。|Azure Active Directory|
|LogonType|信箱存取的類型。 下列值表示存取信箱的使用者類型。  <br/><br/> **0** -表示信箱擁有者。<br/> **1** -表示系統管理員。<br/> **2** -表示代理人。 <br/>**3** -指出 Microsoft datacenter 中的傳輸服務。<br/> **4** -表示 Microsoft datacenter 中的服務帳戶。 <br/>**6** -表示委派的管理員。|Exchange （信箱活動）|
|MailboxGuid|已存取之信箱的 Exchange GUID。|Exchange （信箱活動）|
|MailboxOwnerUPN|擁有所存取信箱之人員的電子郵件地址。|Exchange （信箱活動）|
|成員|列出已從小組中新增或移除的使用者。 下列值指出已指派使用者的角色類型。  <br/><br/> **1** -表示擁有者角色。<br/> **2** - 代表「成員」角色。<br/> **3** - 代表「來賓」角色。 <br/><br/>成員屬性也會包含貴組織名稱與成員的電子郵件。|Microsoft Teams|
|ModifiedProperties （Name、NewValue、OldValue）|會包含系統管理員事件的屬性，例如，將使用者新增為網站成員或網站集合管理員群組。 此屬性包括已修改的屬性名稱（例如，網站管理員群組）修改後的屬性的新值（例如新增為網站管理員的使用者，以及已修改物件的先前值）。|全部（系統管理活動）|
|ObjectId|針對 Exchange 系統管理員審核記錄，指令程式所修改的物件名稱。  <br/> SharePoint 活動中，使用者所存取之檔案或資料夾的完整 URL 路徑名稱。  <br/> 針對 Azure AD 活動，已修改的使用者帳戶名稱。|全部|
|作業|使用者或系統管理員活動的名稱。 此屬性的值會對應至 [**活動**] 下拉式清單中選取的值。 如果已選取 [**顯示所有活動的結果**]，該報告將會包含所有服務之所有使用者和系統管理員活動的專案。 如需在審計記錄檔中記錄的作業/活動的描述，請參閱在[Office 365 搜尋「審核記錄](search-the-audit-log-in-security-and-compliance.md)」中的 [**審核的活動**] 索引標籤。  <br/> 若為 Exchange 系統管理員活動，這個屬性會識別所執行之 Cmdlet 的名稱。|全部|
|OrganizationId|組織的 GUID。|全部|
|路徑|所存取郵件所在的信箱資料夾名稱。 此屬性也會識別建立郵件所在的資料夾 a 或複製/移至該資料夾。|Exchange （信箱活動）|
|參數|針對 Exchange 系統管理活動，所有參數的名稱和值都是與 Operation 屬性中識別的指令程式搭配使用。|Exchange （系統管理活動）|
|RecordType|由 record 指示的作業類型。 下列值會指出記錄類型。  <br/><br/> **1** -表示來自 Exchange 系統管理員審核記錄檔的記錄。 <br/>**2** -指出 Exchange 信箱審計記錄檔中對 singled 信箱專案所執行之作業的記錄。 <br/>**3** -也指出 Exchange 信箱審計記錄檔的記錄。 這種記錄類型表示已對來源信箱中的多個專案執行此作業（例如，將多個專案移至 [刪除的郵件] 資料夾或永久刪除多個專案）。 <br/>**4** -表示 SharePoint 中的網站管理員作業，例如系統管理員或指派網站許可權的使用者。 <br/>**6** -表示 SharePoint 中的檔或資料夾相關作業，例如使用者查看或修改檔案。 <br/>**8** -表示在 Azure Active Directory 中執行的系統管理員作業。 <br/>**9** -表示在 Azure Active Directory 中 OrgId 登入事件。 此記錄類型已被取代。 <br/>**10** -指出由 Microsoft 人員在資料中心執行的安全性 Cmdlet 事件。 <br/>**11** -表示 SharePoint 中的資料遺失防護（DLP）事件。<br/> **12** -表示 Sway 事件。 <br/>**13** -當使用統一的 DLP 原則進行設定時，會指出 Exchange 中的 DLP 事件。 不支援以 Exchange 郵件流程規則（也稱為傳輸規則）為基礎的 DLP 事件。<br>**14** -表示 SharePoint 中的共用事件。<br/> **15** -指出 Azure Active Directory 中的安全權杖服務（STS）登入事件。 <br/>**18** -表示安全性 & 規範中心事件。 <br/>**19** -表示在非常短的期間內重複活動所產生的匯總 Exchange 信箱作業。 <br/>**20** -表示 Power BI 事件。 <br/>**21**-表示 Dynamics 365 事件。<br/>**22** -表示 Yammer 事件。 <br/>**23** -表示商務用 Skype 事件。 <br/>**24** -表示 eDiscovery 事件。 這種記錄類型表示在安全性與合規性中心執行內容搜尋及管理 eDiscovery 案例所執行的活動。 如需詳細資訊，請參閱在[審核記錄中搜尋 eDiscovery 活動](search-for-ediscovery-activities-in-the-audit-log.md)。<br/>**25、26或 27** -表示 Microsoft 團隊事件。 <br/>**28** -指出來自 Exchange Online Protection 和 Office 365 高級威脅防護的網路釣魚和惡意程式碼事件。<br/>**29** -表示來自 Exchange Online Protection 和 Office 365 高級威脅防護的提交事件。<br/>**30** -表示 Microsoft 電源自動化（以前稱為 microsoft Flow）事件。<br/> **31** -指出高級 eDiscovery 事件。<br/> **32** -表示 Microsoft Stream 事件。<br/> **33** -表示 SharePoint 中與 DLP 分類相關的事件。<br/>**35** -表示 Microsoft 專案事件。 <br/> **36** -指出 SharePoint 清單事件。<br/>**37** -表示與 SharePoint 批註相關的事件。 <br/>**38** -會指出與安全性與合規性中心中的保留原則和保留標籤相關的事件。  <br/>**40** -指出安全性和相容性警示信號所產生的事件。<br/> **41** -表示 Office 365 高級威脅防護中的安全連結時間區塊和封鎖覆寫事件。<br/>**42** -會指出與安全性 & 規範中心的真知灼見和報告相關的事件。<br/>**44** -指出 Workplace Analytics 事件。 <br/>**45** -表示 Power Apps 事件。 <br/> **47** -針對 SharePoint、OneDrive 和 Microsoft 團隊中的檔案，顯示 Office 365 高級威脅防護的網路釣魚和惡意程式碼事件。<br/> **49** -表示醫療保健的 Microsoft 小組中的[患者應用程式](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit)事件。 <br/>**50** -表示與 MailItemsAccessed 信箱審核動作相關的事件。 <br/>**51**表示與反垃圾郵件和郵件衛生相關的事件。 <br/>**52** -表示與資料洞察力 REST API 相關的事件。<br/>**53** -表示與資訊屏障原則的應用程式相關的事件。 如需詳細資訊，請參閱[定義資訊障礙的原則](information-barriers-policies.md)。 <br/>**54** -指出 SharePoint 清單專案事件。<br/>**55** -指出 SharePoint 內容類型事件。<br/> **56** -指出 SharePoint 清單欄位事件。 <br/>**62** -表示電子郵件攻擊活動相關事件。 如需詳細資訊，請參閱[Office 365 ATP 中的市場即時檢視](https://docs.microsoft.com/microsoft-365/security/office-365-security/campaigns)。<br/>**64** -表示自動化調查和回應事件。 如需詳細資訊，請參閱[Office 365 中的自動化調查和回應（AIR）](../security/office-365-security/automated-investigation-response-office.md)<br/>**65** -表示隔離審計記錄事件。<br/>**66** -表示 Microsoft Forms 事件。<br/>**68** -指出 Exchange 中的通訊相容性事件。 如需詳細資訊，請參閱[Microsoft 365 中的通訊相容性](communication-compliance.md)。<br/>**69** -表示與客戶金鑰加密相關的事件。 如需詳細資訊，請參閱[Office 365 中的服務加密與客戶金鑰](customer-key-overview.md)。 
|ResultStatus|會指出動作（在**操作**屬性中指定）是否成功。  <br/> 若為 Exchange 系統管理員活動，此值為**True** （成功）或**False** （失敗）。|全部  <br/>|
|SecurityComplianceCenterEventType|表示活動為安全性 & 規範中心事件。 所有安全性 & 規範中心活動的值都為**0** ，此屬性。|安全性與合規性中心|
|SharingType|指派給共用資源之使用者的共用許可權類型。 此使用者已在**UserSharedWith**屬性中識別。|SharePoint|
|網站|使用者所存取的檔案或資料夾所在之網站的 GUID。|SharePoint|
|SiteUrl|使用者所存取的檔案或資料夾所在之網站的 URL。|SharePoint|
|SourceFileExtension|使用者所存取之檔案的副檔名。 如果所存取的物件是資料夾，則此屬性會是空白的。|SharePoint|
|SourceFileName|使用者存取的檔案名或資料夾名稱。|SharePoint|
|SourceRelativeUrl|資料夾的 URL，該資料夾包含使用者所存取的檔案。 **SiteURL**、 **SourceRelativeURL**及**SourceFileName**屬性的值組合，會與**ObjectID**屬性的值相同，也就是使用者所存取之檔案的完整路徑名稱。|SharePoint|
|主旨|已存取之郵件的主旨行。|Exchange （信箱活動）|
|TabType| 在團隊中新增、移除或更新的索引標籤類型。 此屬性的可能值如下：  <br/><br/> **Excel pin** -excel 索引標籤。  <br/> **擴充**-所有第一方和協力廠商應用程式;例如類別排程、VSTS 和表單。  <br/> **記事**-OneNote] 索引標籤。  <br/> **Pdfpin** -[PDF] 索引標籤。  <br/> **Powerbi** -A PowerBI] 索引標籤。  <br/> **Powerpointpin** -PowerPoint] 索引標籤。  <br/> **Sharepointfiles** -SharePoint] 索引標籤。  <br/> **網頁**-已釘上的網站索引標籤。  <br/> **Wiki-tab** -A wiki 索引標籤。  <br/> **WorDPIn** -[Word] 索引標籤。|Microsoft Teams|
|Target|在其上執行動作（在**操作**屬性中識別）的使用者。 例如，如果將來賓使用者新增至 SharePoint 或 Microsoft 小組，該使用者就會列在此屬性中。|Azure Active Directory|
|TeamGuid|Microsoft 小組中的團隊識別碼。|Microsoft Teams|
|TeamName|Microsoft 小組中的小組名稱。|Microsoft Teams|
|UserAgent|使用者瀏覽器的相關資訊。 瀏覽器提供此資訊。|SharePoint|
|UserDomain|執行動作之使用者（主角）的承租人組織的身分識別資訊。|Azure Active Directory|
|UserId|執行動作（在**Operation**屬性中指定）會導致記錄記錄的使用者。 審核記錄中也會包含系統帳戶（如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM）所執行之活動的審計記錄。 UserId 屬性的另一個一般值是 app@sharepoint。 這表示執行該活動的「使用者」是具有 SharePoint，代表使用者、系統管理員或服務執行組織範圍內的動作（例如搜尋 SharePoint 網站或 OneDrive 帳戶）的應用程式所需的許可權。 如需詳細資訊，請參閱[稽核記錄中的 app\@sharepoint 使用者](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)。 |全部|
|UserKey|在**UserID**屬性中所識別之使用者的替代識別碼。 例如，這個屬性會填入 SharePoint 中使用者執行之事件的 passport 唯一識別碼（PUID）。 此屬性也可能會指定與系統帳戶執行之其他服務和事件中發生之事件的**UserID**屬性相同的值。|全部|
|UserSharedWith|共用資源的使用者。 如果**Operation**屬性的值為**SharingSet**，則會包含此屬性。 此使用者也會列在報告中的 [**共用與**] 欄位。|SharePoint|
|UserType|執行作業的使用者類型。 下列值表示使用者類型。 <br/> <br/> **0** -一般使用者。 <br/>**2** -您的 Microsoft 365 組織中的系統管理員。<sup>1</sup> <br/>**3** -A Microsoft 資料中心系統管理員或資料中心系統帳戶。 <br/>**4** -系統帳戶。 <br/>**5** -應用程式。 <br/>**6** -A 服務主體。<br/>**7** -自訂原則。<br/>**8** -系統原則。|全部|
|版本|會指出記錄的活動版本號碼（由**Operation**屬性識別）。|全部|
|工作負載|發生活動的 Microsoft 365 服務。|全部|
||||

> [!NOTE]
><sup>1</sup>針對 Azure Active Directory 相關事件，系統管理員的值不會用於審計記錄。 管理員執行的活動的審計記錄會指出一般使用者（例如**UserType： 0**）會執行活動。 **UserID**屬性會識別執行活動的人員（一般使用者或系統管理員）。<br/>

當您查看特定事件的詳細資料時，當您按一下 [**詳細資訊**] 時，也會顯示上述屬性。
  
![按一下 [更多資訊] 以檢視稽核記錄事件記錄的詳細屬性。](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
