---
title: Microsoft 365 內部租使用者共同作業
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/08/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: 深入瞭解 Microsoft 365 共同作業如何跨承租人和組織運作，允許不同的組織安全地協同運作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529d4a320fe9aefa5d1ddfbac56742991dbd732d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688593"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 內部租使用者共同作業

本文說明在兩個 Microsoft 365 承租人之間進行共同作業的幾種方式。 適用于 Microsoft 365 系統管理員。
  
假設有兩個組織、Fabrikam 和 Contoso 都有 Microsoft 365 for business 租使用者，而且他們想要在數個專案上共同運作;有些會執行的時間有限，有些則在進行中。 Fabrikam 和 Contoso 如何讓其人員和團隊能夠更有效率地以安全方式跨不同的 Microsoft 365 承租人進行共同作業？ Microsoft 365 和 Azure Active Directory B2B 協同功能一起提供數個選項。 本文說明 Fabrikam 和 Contoso 可以考慮的幾個主要案例。
  
Microsoft 365 內部租使用者共同作業選項包括針對檔案和交談使用中央位置、使用 IM、語音/視頻通話進行通訊，以及保護資源和應用程式的存取。 使用下表來選取解決方案並深入瞭解。
  
## <a name="exchange-online-collaboration-options"></a>Exchange Online 協同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|與其他 Microsoft 365 組織共用行事曆  <br/> |管理員可以在 Exchange Online 中設定不同層級的行事曆存取，以允許公司與其他企業共同作業，並讓使用者共用排程 (空閒/忙碌資訊) 與其他人  <br/> |[在 Exchange Online 中共用](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) <br/> [Exchange Online 中的組織關係](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) <br/> [在 Exchange Online 中建立組織關聯性](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) <br/> [在 Exchange Online 中修改和組織關聯性](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) <br/> [在 Exchange Online 中移除組織關聯性](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) <br/> [與外部使用者共用行事曆](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) <br/> |
|控制使用者如何與組織外部的人員共用其行事曆  <br/> |管理員會將共用原則套用至使用者信箱，以控制可與其共用的使用者和授與的存取層級  <br/> |[Exchange Online 中的共用原則](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) <br/> [在 Exchange Online 中建立共用原則](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) <br/> [將共用原則套用到 Exchange Online 中的信箱](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) <br/> [修改、停用或移除 Exchange Online 中的共用原則](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) <br/> |
|設定安全的電子郵件通道，以及控制夥伴組織的郵件流程  <br/> |管理員建立連接器，以將安全性套用至夥伴組織或服務提供者的郵件交換。 連接器會透過傳輸層安全性 (TLS) 來強制進行加密，並允許夥伴傳送電子郵件的功能變數名稱或 IP 位址範圍的限制。  <br/> |[Exchange Online 如何使用 TLS 來保護電子郵件連線](https://technet.microsoft.com/library/mt163898.aspx) <br/> [使用連接器設定郵件流程](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) <br/> [Exchange Online 中的遠端網域](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) <br/> [為夥伴組織設定安全郵件流程的連接器](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) <br/> [Exchange Online 的郵件流程最佳作法 (概述) ](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) <br/> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint 線上及 OneDrive 商務共同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|與外部使用者共用網站與檔  <br/> |管理員在租使用者中設定共用，或為 Microsoft 帳戶驗證、工作或學校帳戶驗證或來賓帳戶設定網站集合層級  <br/> |[管理您的 SharePoint Online 環境外部共用](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> [依網域限制 SharePoint 和 OneDrive 內容的共用](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) <br/> [使用 SharePoint 線上做為企業對企業 (B2B) 外部網路解決方案](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) <br/> |
|追蹤和控制使用者的外部共用  <br/> |Business file 物主的 OneDrive，以及 SharePoint 線上使用者設定網站與檔共用，並建立追蹤共用的通知  <br/> |[為商務用 OneDrive 設定外部共用的通知](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) <br/> [共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) <br/> |
   
## <a name="skype-for-business-collaboration-options"></a>商務用 Skype 協同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|商務用 skype Online-與其他商務用 Skype 使用者的 IM、通話及顯示狀態  <br/> |管理員可以為商務用 Skype Online 使用者啟用 IM、進行音訊/視頻通話，並查看其他 Microsoft 365 承租人中的使用者狀態。  <br/> |[允許使用者連絡外部商務用 Skype 使用者](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94) <br/> |
|商務用 skype Online-使用 Skype (消費者) 使用者的 IM、通話及顯示狀態  <br/> |系統管理員可以讓商務用 Skype Online 使用者使用 Skype (使用者) 使用者的 IM、通話及查看狀態。  <br/> |[讓商務用 Skype 使用者新增 Skype 連絡人](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460) <br/> |
   
## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B 協同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|Azure AD B2B 協同作業-透過將外部使用者新增至組織目錄中的群組來共用內容  <br/> |一個 Microsoft 365 租使用者的全域管理員可以邀請其他 Microsoft 365 租使用者加入其目錄、將這些外部使用者新增至群組，並授與內容的存取權，例如，群組的 SharePoint 網站和文件庫。  <br/> |[何謂 Azure AD B2B 協同預覽？](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) <br/> [Azure AD B2B：新的更新使跨部門 collab 輕鬆](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) <br/> [外部共用和 Azure Active Directory B2B 協同作業](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) <br/> [Azure Active Directory B2B 協同 API 和自訂](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) <br/> [Azure AD 和身分識別： Azure AD B2B 共同作業 (商務對企業的整合](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) <br/> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 協同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|Microsoft 365 群組-位於一個集中位置的電子郵件、行事曆、OneNote 及共用檔  <br/> |「業務基本版」、「商務版特優」、「教育版」及「企業版 E1」、「E3」和 E5 方案都支援群組。 一個 Microsoft 365 租使用者中的人員可以建立群組，並邀請另一個 Microsoft 365 承租人中的人員做為來賓使用者。 也適用于 Dynamics CRM。  <br/> |[深入了解 Microsoft 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br/> [Microsoft 365 群組中的來賓存取權](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) <br/> [部署 Microsoft 365 群組](https://technet.microsoft.com/library/dn896591.aspx) <br/> |
   
## <a name="yammer-collaboration-options"></a>Yammer 共同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|Yammer-透過企業社交媒體共同作業  <br/> |除非 Yammer 系統管理員已停用建立外部群組的功能，否則使用者可以建立外部群組，透過交談在 Yammer 中共同作業、類似和追蹤文章、共用檔案和線上聊天的功能。  <br/> |[在 Yammer 建立及管理外部群組](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a) (機器翻譯) <br/> |
   
## <a name="teams-collaboration-options"></a>小組共同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|在小組中與組織外部的使用者共同作業  <br/> |邀請 Microsoft 365 租使用者的全域管理員需要啟用小組中的外部共同作業。 全域管理員及小組擁有者現在可以邀請具有電子郵件地址的任何人，以在小組中共同作業。  <br/> 系統管理員也可以管理和編輯其承租人中已存在的客人。  <br/> |[授權來賓存取](https://docs.microsoft.com/microsoftteams/teams-dependencies) <br/> [在小組中開啟或關閉來賓存取](https://docs.microsoft.com/microsoftteams/set-up-guests) <br/> [使用 PowerShell 控制來賓存取](https://docs.microsoft.com/microsoftteams/guest-access-powershell) <br/> [來賓存取檢查清單](https://docs.microsoft.com/microsoftteams/guest-access-checklist) <br/> [查看來賓使用者](https://docs.microsoft.com/microsoftteams/view-guests) <br/> [編輯來賓使用者資訊](https://docs.microsoft.com/microsoftteams/edit-guests-information) <br/> |
|小組擁有者可以邀請和管理來賓在其團隊中共同作業的方式。  <br/> |小組擁有人可在其小組中對來賓的工作進行其他控制。  <br/> |[新增來賓](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) <br/> [將來賓新增至團隊](https://docs.microsoft.com/microsoftteams/add-guests) <br/> [管理小組中的來賓存取](https://docs.microsoft.com/microsoftteams/manage-guests) <br/> [查看團隊成員或管道中的人員](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> |
|其他承租人的客人可以查看小組的內容，以及與其他成員共同作業  <br/> |無。  <br/> |[來賓存取體驗](https://docs.microsoft.com/microsoftteams/guest-experience) <br/> |

## <a name="power-bi-collaboration-options"></a>Power BI 協同作業選項

|**共用目標**|**管理動作**|**How to 資訊**|
|:-----|:-----|:-----|
|Power BI 可讓外部來賓使用者透過連結使用共用的內容。 這可讓組織中的使用者以安全的方式在組織之間散佈內容。<br/> | Power BI 系統管理員可以控制使用者是否可以邀請外部使用者來查看組織內的內容。 <br/> |[使用 Azure AD B2B 將 Power BI 內容散佈給外部來賓使用者](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) <br/> |
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>瞭解 Microsoft 365 內部租使用者共同作業的相關觀點

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>共用使用者帳戶、授權、訂閱及儲存

每個組織都維護自己的使用者帳戶、身分識別、安全性群組、訂閱、授權和儲存區。 人員可使用 Microsoft 365 中的共同作業功能和共用原則及安全性設定，在維護公司資產的控制權時，提供必要資訊的存取權。
  
- **使用者帳戶：** 在內部部署 Active Directory 目錄服務中的承租人或分割區之間，無法共用帳戶，帳戶無法重複。 
    
- **授權 &amp; 訂閱：** 在 Microsoft 365 中，授權計畫中的授權 (也稱為 SKUs 或 Microsoft 365 方案) 讓使用者能夠存取為這些計畫定義的 Microsoft 365 服務。 
    
- **儲存區：** 在 Microsoft 365 方案中，SharePoint Online 的軟體界限和限制會與信箱儲存限制分開管理。 信箱儲存限制是使用 Exchange Online 來設定和管理。 在這兩種情況下，儲存體都無法共用跨承租人。 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>我們是否可以跨 Microsoft 365 承租人共用網域命名空間？

否。 虛名網域（例如 fabrikam.com 或 tailspintoys.com）每次只能與一個承租人關聯並使用。 每個租使用者都必須有自己的命名空間;UPN、SMTP 和 SIP 命名空間無法在承租人間共用。
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>混合式元件和 Microsoft 365 內部租使用者共同作業的情況為何？

內部部署混合式元件（例如 Exchange 組織和 Azure AD Connect）無法在多個承租人間分割。
  

