---
title: 規劃商務 Microsoft 365 的設定
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 深入瞭解移動至 Microsoft 365 商務的需求和考慮。
ms.openlocfilehash: b4d2b5d500b73b62c67d3f8126b6313484e2bc78
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297029"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>規劃商務 Microsoft 365 的設定

本文適用于已訂閱 Microsoft 365 for business plan 的人員。
  
在將組織移至 Microsoft 365 之前，必須先滿足您的需求，以及您必須進行的資訊，以及您必須進行的決策。


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>在您執行安裝精靈之前必須準備好的資訊

當您準備好執行安裝精靈並將您的網域移至 Microsoft 365 時，以下是您必須準備的資訊：
  
- 您要新增至 Microsoft 365 的人員清單。 即使您已將其新增至 Microsoft 365，如果您要更新網域資訊，您必須在這裡輸入他們的名稱。

- 如何將使用者識別碼和密碼通知員工，以供登入。 您要透過電話告知對方相關資訊嗎？ 還是要傳送相關資訊到他們的個人電子郵件地址？ 他們無法存取其電子郵件，因此您無法使用。

- 如果您有組織的功能變數名稱 (例如 contoso.com) **，且** 您計畫使用 Microsoft 電子郵件，則必須知道您的網域註冊所在的位置，並且具備登入資訊。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>當您執行 Microsoft 365 安裝精靈時會發生什麼事

安裝精靈會逐步引導您在電腦上安裝 Microsoft 365 應用程式、新增及驗證您的網域、新增使用者並指派授權給他們，以及連接您的網域。

> [!NOTE]
> 如果您需要 [指派系統管理員 Microsoft 365 角色](../add-users/assign-admin-roles.md)給您新增至嚮導的使用者，您可以稍後在 [**使用者**] 頁面上進行。 
  
如果您未完成安裝精靈，您可以隨時從系統 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **設定** 完成安裝工作。 從這裡，您可以從其他電子郵件服務遷移電子郵件和連絡人、變更您系統管理員帳戶的網域、管理帳單資訊、新增或移除使用者、重設密碼，以及執行其他商務功能。 如需安裝精靈與 **安裝程式** 頁面之間差異的詳細資訊，請參閱 [Microsoft 365 安裝精靈與設定頁面之間的差異](o365-setup-wizard-and-setup-page.md)。

如果您遇到任何困難，請致電與我們連絡。[我們隨時為您效勞！](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何時不應使用設定精靈：Active Directory 同步處理和混合式環境

有幾種情況會包含從內部部署環境遷移資料或使用者，或設定包含目錄同步處理的混合系統。 如果您處在任一類別中，請遵循下列文章中的指示：
  
- 若要設定目錄同步處理與您的內部部署 Active directory，請參閱[設定 Microsoft 365 的目錄同步](../../enterprise/set-up-directory-synchronization.md)處理，並瞭解 Microsoft 365 中的不同身分識別模型，並閱讀[瞭解 Microsoft 365 身分識別及 Azure Active Directory](../../enterprise/about-microsoft-365-identity.md)。

- 若要設定 Exchange 混合式，您可在下列找到關於引導您完成所有不同設定混合式 Exchange 的方式之整組指示 (包括設定 DNS 記錄)：[Exchange Server 部署助理](/exchange/exchange-deployment-assistant)

- 若要設定 SharePoint 混合式 (尤其是混合式搜尋和網站功能)，請參閱[在 SharePoint 中的混合式搜尋](/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>移至 Microsoft 365 一次或分階段

- **您是否要移動組織，以便同時 Microsoft 365 全部專案？** 如果是的話，請將您的網域移至 Microsoft 365 立即。 從執行 Microsoft 365 安裝精靈開始;它會提示您設定您的網域。

- **您想要逐漸移至 Microsoft 365 嗎？** 如果您想要依下列順序移至 Microsoft 365，請略過執行 Microsoft 365 安裝精靈，並考慮以下列順序採用 Microsoft 365 功能：

    1. [將您的員工新增至 Microsoft 365](../add-users/add-users.md) ，讓他們可以下載及安裝 Office 應用程式。

    2. [下載及安裝 Office App](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以便在電腦和裝置上使用 Word、Excel 和 PowerPoint。

    3. [設定](#plan-for-teams)要用於會議的 Microsoft Teams。

    4. [將您的內容移至 Microsoft 365 雲端儲存](set-up-file-storage-and-sharing.md) (OneDrive 或 SharePoint 小組網站) 。

    5. 當您準備好時，請在 [系統 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)] 的左功能窗格中，選取 [ **安裝** ]，然後使用 [ **設定** ] 頁面來 [移動您的網域和電子郵件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>檢查您的裝置是否符合系統需求

您組織中的每個人都可以在最多五部 pc 和 mac 上安裝 Office 2016 套件應用程式 (Word、Excel、PowerPoint 等) 。 如需相關資訊，請參閱安裝商務用 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)的作業系統和電腦需求。
  
行動應用程式可以安裝在 iOS、Android 和 Windows 裝置上。 如需了解行動裝置和瀏覽器的相關支援資訊，請瀏覽 [Office 的系統需求](https://go.microsoft.com/fwlink/?LinkId=534827)。
  
## <a name="plan-for-email"></a>規劃電子郵件

如果您打算從現有的電子郵件服務移至 Microsoft 365，通常需要兩天的時間來進行切換。
  
### <a name="plan-for-email-downtime"></a>規劃電子郵件服務停機
  
如果您要將 Microsoft 365 用於您的電子郵件：
  
- 若要將您的商務電子郵件地址 (例如，將 *\@ contoso.com*) 從其他電子郵件服務移至 Microsoft 365，您必須將郵件傳遞至新的 Microsoft 365 信箱。 若要執行此動作，請選取 [**設定**] 頁面上的 [**遷移使用者的資料**]，我們將引導您完成您在網域主機上進行的更新（逐步逐步進行）。

- 更新您的網域主機後，相關變更通常在 1 到 2 小時內就會生效。 不過，請注意，在網際網路上更新的變更有時可能需要長達72小時。

- 因為您可能會發生電子郵件停機時間，所以建議您在晚上或週末切換至 Microsoft 電子郵件時，收到較少的電子郵件。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>移動現有電子郵件、連絡人和行事曆的相關規劃
  
如果您要使用 Microsoft 365 您的電子郵件帳戶，您可以將現有的電子郵件、連絡人及行事曆帶給您。 在大多數情況下，[ **安裝** ] 頁面會協助您移動現有的電子郵件和連絡人。 我們也提供移動一或多個信箱的逐步指南。
  
|**信箱數量**|**建議**|
|:-----|:-----|
|只有幾個信箱  <br/> |如果您不想要使用「 **安裝** 」頁面來遷移信箱，您可以讓信箱擁有者遷移其自己的電子郵件和連絡人。 請參閱[將電子郵件和連絡人遷移至 Microsoft 365 for business](migrate-email-and-contacts-admin.md)。  <br/> |
|多個信箱  <br/> |如果您是從 Gmail 進行遷移，請參閱[將 G Suite 信箱遷移至 Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。  <br/> 如果您是從另一個電子郵件提供者（包括 Exchange）進行遷移，請參閱[將多個電子郵件帳戶遷移到 Microsoft 365 的方式](/Exchange/mailbox-migration/mailbox-migration)。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>規劃檔案儲存空間與移轉

Microsoft 365 為個人、小型組織和企業提供雲端儲存空間。 如需有關存放位置的指導，請參閱在[Microsoft 365 中儲存檔的位置](../../business-video/store-files.md)。
  
- **您可以將數百個檔案移** 至 [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB)或 [SharePoint 小組網站](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 您一次可以上傳 100 個檔案。 預設的檔案大小上限為 2GB，因此請勿上傳超過此限制的檔案。
  
- **如果您想要將幾千個檔案移** 至 Microsoft 365 儲存體，請參閱 [SharePoint 線上限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)。 建議您使用移轉工具，或考慮雇用[合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來協助您進行移轉。 如需如何移轉大量檔案的相關資訊，請參閱 [SharePoint Online 與 OneDrive 移轉使用者指南](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。
  
## <a name="plan-for-teams"></a>規劃 Teams

您可以使用 Microsoft Teams，撥打您的組織中的其他人撥打您的訂閱。 例如，如果您的組織有10名人員，您可以在沒有任何特殊設定的情況下，使用 Teams 呼叫和 IM。 如需詳細資訊，請參閱[立即開始使用 Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start)。

若為較大的組織，或者您是從商務用 Skype、內部部署或混合部署開始，請參閱 how [to 向外 Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams)。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>規劃與 Active Directory 或其他軟體整合

- **您要與內部部署的 Active Directory 整合嗎？** 您可以使用 Azure Active Directory 連線，將您的內部部署 Active Directory 與 Microsoft 365 整合。 如需相關指示，請參閱[設定 Microsoft 365 的目錄同步](../../enterprise/set-up-directory-synchronization.md)處理。
  
- **您是否要將 Microsoft 365 與其他公司所做的軟體整合？** 如果您需要將 Microsoft 365 與組織中的其他軟體整合，建議您考慮[雇用合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來協助您進行部署。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>您是否需要人員協助您設定 Microsoft 365？

- **如果您的員工少於 50 人：**

  - **尋求協助，我們會致電您**。 在您購買 Microsoft 365 後，您就可以存取系統管理中心 (不需要執行安裝程式，即可) 取得此。 在系統管理中心的底部，選取 [ **需要協助]？** 請描述您的問題，我們會致電您。 
  - **[Microsoft 365 商務支援人員](../../business-video/get-help-support.md)，請致電您的問題**。 我們隨時為您效勞！ 
  - **請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)**。 如果您很短的時間，或具備高級需求 (例如，將數以千計的檔案移至 Microsoft 365 雲端儲存區，或與其他軟體) 整合，有經驗的合作夥伴可能會有很大的説明。 

- **如果您有超過50名員工**，可使用 FastTrack 的內 [架中心](https://go.microsoft.com/fwlink/?LinkId=517115) 來協助您進行部署。