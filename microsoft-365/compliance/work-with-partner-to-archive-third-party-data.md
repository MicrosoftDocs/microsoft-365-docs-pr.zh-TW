---
title: 與合作夥伴配合以封存第三方資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定自訂連接器，以從資料來源（例如 Salesforce 交談、Yahoo Messenger 或 Yammer）匯入協力廠商資料。
ms.openlocfilehash: f76ceda12bf48d26454a47e4b0b5d6ad42fbe55d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817038"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>與合作夥伴配合以封存第三方資料

您可以與 Microsoft 合作夥伴合作，匯入協力廠商資料來源中的資料，並將其封存至 Microsoft 365。 協力廠商可為您提供自訂連接器，以設定為從協力廠商資料來源提取專案（定期），然後匯入這些專案。 夥伴連接器會將專案的內容從資料來源轉換成電子郵件訊息格式，然後將專案儲存在信箱中。 匯入協力廠商資料後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則）套用至此資料。
  
以下是與 Microsoft 合作夥伴合作以匯入協力廠商資料所需的程式和步驟。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[步驟2：建立並設定協力廠商資料信箱](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[步驟 4：提供資訊給合作夥伴](#step-4-provide-your-partner-with-information)

[步驟5：在 Azure Active Directory 中註冊協力廠商資料連線器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>協力廠商資料匯入程序的運作方式

下列圖例和描述說明協力廠商資料匯入程式在使用合作夥伴時的運作方式。
  
![協力廠商資料匯入程序的運作方式](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 客戶可以使用其選擇的合作夥伴，設定將從協力廠商資料來源提取專案的連接器，然後將這些專案匯入至 Microsoft 365。
    
2. 夥伴連接器會透過協力廠商 API （根據排程或設定的基礎）連線至協力廠商資料來源，並從資料來源提取專案。 協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。 請參閱[More information](#more-information)一節以取得郵件格式架構的描述。 
    
3. 夥伴連接器會透過已知端點透過 Exchange Web 服務（EWS），連接至 Microsoft 365 中的 Azure 服務。
    
4. Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:
    
   1. **具有對應至使用者帳戶之使用者識別碼的專案：** 如果夥伴連接器可將協力廠商資料來源中專案的使用者識別碼對應至 Office 365 中的特定使用者識別碼，該專案會複製到使用者的 [可復原的專案] 資料夾中的 [**清除**] 資料夾。 使用者無法存取 [清除] 資料夾中的項目。 不過，您可以使用 eDiscovery 工具來搜尋 [清除] 資料夾中的專案。
    
   1. **沒有對應至使用者帳戶的使用者識別碼的專案：** 如果 partner connector 無法將專案的使用者識別碼對應至特定的使用者識別碼，該專案會複製到協力廠商資料信箱的 [**收件**匣] 資料夾。 將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步驟 1：尋找協力廠商資料合作夥伴

在 Microsoft 365 中封存協力廠商資料的主要元件，是尋找和使用專用於從協力廠商資料來源捕獲資料，並將資料匯入 Office 365 的 Microsoft 合作夥伴。 在匯入資料之後，可以將其封存及保留，以及組織的其他 Microsoft 資料，例如來自 Exchange 的電子郵件，以及來自 SharePoint 和 OneDrive 商務的檔。 合作夥伴會建立從您組織的協力廠商資料來源（例如 BlackBerry、Facebook、Google +、Thomson Reuters、Twitter 及 YouTube）提取資料的連接器，並將該資料傳遞到以電子郵件形式將專案匯入 Exchange 信箱的 Office 365 API。 
  
下列各節列出參與程式以在 Office 365 中封存協力廠商資料的 Microsoft 合作夥伴（和其所支援的協力廠商資料來源）。

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17A-4 LLC](https://www.17a-4.com)支援下列協力廠商資料來源：
  
- BlackBerry
    
- Bloomberg 資料流
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs 資料流
    
- OpenText
    
- Oracle/ATG 'click-to-call' 即時說明
    
- 樞紐分析 IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 商務用 Skype (Lync/OCS)
    
- 商務用 Skype Online (Lync Online)
    
- SQL 資料庫
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com)支援下列協力廠商資料來源： 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)支援下列協力廠商資料來源： 
  
- 含樞紐分析用戶端的 AOL 
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg Chat
    
- Bloomberg 郵件
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; 顯示伺服器（v10，v v10.5.1 SU1，v 11.0，v 11.5 SU2）

- Cisco Webex 小組

- Citrix 工作區 &amp; ShareFile

- CrowdCompass

- 自訂分隔的文字檔
    
- 自訂 XML 檔案
    
- Facebook （頁面）
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- 搖擺
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- 樞紐
    
- Salesforce Chatter

- 商務用 Skype Online
    
- 商務用 Skype 2007 版 R2 - 2016 (內部部署)
    
- Slack Enterprise Grid
    
- 交響樂
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支援下列協力廠商資料來源： 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- 彭博
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com)支援下列協力廠商資料來源： 
  
- 目的
    
- American Idol
    
- Apple Juice
    
- 含樞紐分析用戶端的 AOL
    
- 阿瑞斯
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg 郵件
    
- CellTrust
    
- Chat Import
    
- Chat Real Time Logging and Policy
    
- 顫 振
    
- Cisco IM &amp; 顯示伺服器（v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1）
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
    
- Collaboration Import
    
- Collaboration Real Time Logging
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- 冰/YellowJacket
    
- IM Import
    
- IM Real Time Logging and Policy
    
- Indii Messenger
    
- Instant Bloomberg
    
- Irc
    
- 搖擺
    
- Jive 6 Real Time Logging (v6、v7)
    
- Jive Import
    
- Jxta
    
- LinkedIn
    
- Microsoft Lync (2010、2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010、2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- Msn
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- 樞紐
    
- Qq
    
- 商務用 Skype 2015
    
- SoftEther
    
- 交響樂
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- 雅虎
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba](https://www.verba.com)支援下列協力廠商資料來源： 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE 影片
    
- Cisco UCCX/UCCE 語音
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- 商務用 Skype/Lync IM
    
- 商務用 Skype/Lync Video
    
- 商務用 Skype/Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop Computer Screen
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>步驟 2：在 Office 365 中建立及設定協力廠商資料信箱

以下是建立及設定協力廠商資料信箱以將資料匯入 Office 365 的步驟。 如先前所述，如果夥伴連接器無法將專案的使用者識別碼對應至使用者帳戶，便會將專案匯入此信箱。
  
 **在 Microsoft 365 系統管理中心完成這些工作**
  
1. 建立使用者帳戶並指派 Exchange Online Plan 2 授權;請參閱[將使用者新增至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。 若要將信箱設為訴訟暫止或啟用具有無限儲存配額的封存信箱，則需要 Plan 2 授權。
    
2. 將協力廠商資料信箱的使用者帳戶新增至 Office 365 中的**Exchange 管理員系統管理員**角色。請參閱[在 Office 365 中指派系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > 請寫下此使用者帳戶的認證。 您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。 
  
 **在 Exchange 系統管理中心完成這些工作**
  
1. 從組織中的通訊錄和其他通訊清單中隱藏協力廠商資料信箱;請參閱[管理使用者信箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。 或者，您也可以執行下列 PowerShell 命令：
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 指派協力廠商資料信箱的**FullAccess**許可權，讓系統管理員或合規性監察官可以在 Outlook 桌面用戶端中開啟協力廠商資料信箱。請參閱管理收件者[的許可權](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. 針對協力廠商資料信箱啟用下列與規範相關的功能：
    
    - 啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限](enable-unlimited-archiving.md)封存。 這可讓您透過設定將協力廠商資料項目目移至封存信箱的封存原則，以釋放主要信箱中的儲存空間。 這可讓您在協力廠商資料上使用無限制的儲存體。
    
    - 將協力廠商資料信箱處於 [訴訟暫止] 狀態。 您也可以在安全性與合規性中心套用 Microsoft 365 保留原則。 保留此信箱會保留協力廠商資料項目（無限期或在指定期間內），並防止其從信箱中清除。 請參閱下列其中一個主題：
    
      - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [保留原則概觀](retention-policies.md)
    
    - 針對協力廠商資料信箱的擁有者、委派及系統管理存取啟用信箱審計記錄;請參閱[啟用信箱審核](enable-mailbox-auditing.md)。 這可讓您審核任何可存取協力廠商資料信箱之使用者執行的所有活動。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步驟 3：設定協力廠商資料的使用者信箱

下一步是設定使用者信箱以支援協力廠商資料。 使用 Exchange 系統管理中心或使用對應的 Windows PowerShell Cmdlet，完成這些工作。
  
1. 為每位使用者啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限](enable-unlimited-archiving.md)封存。
    
2. 將使用者信箱設為訴訟暫止，或套用 Microsoft 365 保留原則;請參閱下列其中一個主題： 
    
    - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [保留原則概觀](retention-policies.md)
    
    如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。

## <a name="step-4-provide-your-partner-with-information"></a>步驟 4：提供資訊給合作夥伴

最後一個步驟是向您的合作夥伴提供下列資訊，讓他們可以設定連接器，以連線至您的組織，將資料匯入至使用者信箱和協力廠商資料信箱。 
  
- 用來連線至 Office 365 中之 Azure 服務的端點：

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 您在步驟2中建立之協力廠商資料信箱的登入認證（Microsoft 365 使用者識別碼和密碼）。 協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步驟5：在 Azure Active Directory 中註冊協力廠商資料連線器

從2018年9月30日起，Office 365 中的 Azure 服務會開始使用 Exchange Online 中的新式驗證，以驗證嘗試連線至組織以匯入資料的協力廠商資料連線器。 這種變更的原因是，新式驗證提供的安全性高於目前的方法，這是根據使用先前所述端點連線至 Azure 服務之協力廠商連接器的允許清單。

若要讓協力廠商資料連線器使用全新的新式驗證方法來連線至 Office 365，您組織中的系統管理員必須同意在 Azure Active Directory 中將連接器註冊為受信任的服務應用程式。 若要允許連接器在 Azure Active Directory 中存取組織的資料，請接受許可權要求，以進行這項操作。 在您接受此要求之後，協力廠商資料連線器會新增為 Azure Active Directory 中的企業應用程式，並表示為服務主體。 如需同意程式的詳細資訊，請參閱[租使用者管理員同意](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

以下是存取及接受註冊連接器要求的步驟：

1. 移[至此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，並使用全域管理員的認證登入。

   隨即顯示下列對話方塊。 您可以展開 carets，以複查將指派給連接器的許可權。

   ![顯示 [許可權要求] 對話方塊](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. 按一下 [接受]****。

在您接受要求之後，就會顯示[Azure 入口網站](https://portal.azure.com)。 若要查看組織的應用程式清單，請按一下 [ **Azure Active Directory**  >  **企業應用程式**]。 Office 365 協力廠商資料連線器會列在**企業應用程式**blade 上。

> [!IMPORTANT]
> 在2018年9月30日之後，如果您未在 Azure Active Directory 中註冊協力廠商資料連線器，協力廠商資料將無法再匯入您組織中的信箱。 請注意，在 Azure Active Directory 中建立的協力廠商資料連線器（在2018年9月30日之前所建立），必須先在 Azure Active Directory 中註冊，請遵循步驟5中的程式。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤銷協力廠商資料連線器的同意

在您的組織 consents 至許可權要求後，若要在 Azure Active Directory 中註冊協力廠商資料連線器，您的組織可以隨時撤銷該同意。 不過，撤銷連接器的同意表示將不再將協力廠商資料來源的資料匯入 Office 365。

若要撤銷協力廠商資料連線器的同意，您可以使用 Azure 入口網站中的**Enterprise** application blade，或是使用 Office 365 PowerShell 中的 [[移除-new-msolserviceprincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) ]，從 azure Active Directory 中刪除應用程式（透過刪除對應的服務主體）。 您也可以在 Azure Active Directory PowerShell 中使用[Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) Cmdlet。
  
## <a name="more-information"></a>詳細資訊

- 如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。 夥伴連接器會使用 Office 365 API 所需的架構，匯入專案。 下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。 表格也會指出郵件屬性是否為必要的。 必須填入必要屬性。 如果專案缺少強制的屬性，則不會將它匯入至 Office 365。 匯入程式會傳回一則錯誤訊息，說明未匯入專案的原因，以及遺漏的屬性。<br/><br/>
    
    |**郵件屬性**|**強制性？**|**描述**|**範例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初在協力廠商資料來源中建立或傳送項目的使用者。 夥伴連接器會嘗試將使用者識別碼從來源專案（例如 Twitter 控制碼）對應至所有參與者（[寄件者] 和 [至] 欄位中的使用者）的使用者帳戶。 郵件副本會匯入至每個參與者的信箱。 如果無法將專案的任何參與者對應至使用者帳戶，該專案就會匯入至 Office 365 中的協力廠商封存信箱。  <br/> <br/> 識別為專案之寄件者的參與者必須在組織中有一個使用中的信箱，且該專案要匯入到該組織中。 如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收項目的使用者，如果適用於資料來源中的項目。  <br/> | `bob@contoso.com` <br/> |
    |**主題** <br/> |否  <br/> |來源項目的主旨。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日期** <br/> |是  <br/> |在客戶資料來源中，最初建立或張貼專案的日期。 例如，Twitter 郵件的日期日期。  <br/> | `01 NOV 2015` <br/> |
    |**身體** <br/> |否  <br/> |訊息或文章的內容。 對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。 在匯入程式期間，協力廠商連接器會嘗試盡可能從內容來源保持完全保真。 如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。 否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。 此屬性的內容取決於夥伴連接器和來源平臺的功能。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**附件** <br/> |否  <br/> |如果資料來源中的專案（例如 Twitter 或立即訊息交談中的 tweet）具有附加的檔案或包括影像，則協力廠商連線會先嘗試在**BODY**屬性中包含附件。 如果無法這樣做，它會新增至 * * 附件 * * 屬性。 其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |是  <br/> | 這是多重值屬性，由合作夥伴連接器建立並填入。 此屬性的格式為 `IPM.NOTE.Source.Event` 。 （此屬性必須以開頭 `IPM.NOTE` 。 這種格式與郵件類別的格式類似 `IPM.NOTE.X` 。）此屬性包含下列資訊：  <br/><br/>`Source`：指出協力廠商資料來源;例如，Twitter、Facebook 或 BlackBerry。  <br/> <br/>  `Event`：指出在產生專案的協力廠商資料來源中所執行的活動類型。例如，在 Twitter 中的 tweet 或在 Facebook 中的文章。 事件是資料來源特有的。  <br/> <br/>  此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。 例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 當專案順利匯入至 Office 365 中的信箱時，會將唯一識別碼傳回回來電者做為 HTTP 回應的一部分。 這個識別碼（稱為 `x-IngestionCorrelationID` ）可以用於後續疑難排解，供合作夥伴進行專案的端對端追蹤。 建議夥伴擷取這項資訊並加以記錄。 以下是顯示此識別碼之 HTTP 回應的範例：

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- 您可以使用安全性與合規性中心的內容搜尋工具，搜尋從協力廠商資料來源匯入信箱的專案。 若要特別針對這些匯入的專案進行搜尋，您可以在內容搜尋的關鍵字方塊中使用下列郵件屬性-值對。
    
  - **`kind:externaldata`**：使用此屬性-值對可搜尋所有協力廠商資料類型。 例如，若要搜尋從協力廠商資料來源匯入的專案，並在匯入專案的 Subject 屬性中包含 "contoso" 一詞，您可以使用關鍵字查詢 `kind:externaldata AND subject:contoso` 。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**：使用此屬性-值對只搜尋協力廠商資料的指定類型。 例如，若要在 Subject 屬性中只搜尋包含 "contoso" 一詞的 Facebook 資料，您可以使用關鍵字查詢 `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。 

  如需用於屬性的協力廠商資料類型的完整值清單 `itemclass` ，請參閱[使用內容搜尋搜尋協力廠商資料已匯入至 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)。
    
   如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰
    
  - [Office 365 中的內容搜尋](content-search.md)
    
  - [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
 
