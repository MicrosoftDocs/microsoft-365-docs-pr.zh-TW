---
title: 規劃您的商務用 Office 365 設定
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 深入瞭解設定 Office 365 for business 所需的功能。
ms.openlocfilehash: bf2db70a77f6ddaf3a2bae04180f0f5be9dbaf05
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212158"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>規劃您的商務用 Office 365 設定

本文適用於已訂閱 Office 365 商務版方案的使用者。
  
將組織移至 Office 365 之前，您需要判斷一些事項，以及您必須準備的資訊。
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>執行 Office 365 設定精靈之前的必備資訊

當您準備好執行 Office 365 設定精靈以及將網域移到 Office 365 時，您必須取得下列必備資訊：
  
- 要加入 Office 365 的人員清單。即使您已將對方加入 Office 365，也仍必須在此輸入對方的名稱，才能更新網域資訊。

- 將登入用 Office 365 使用者識別碼和密碼告知員工的方式。您要透過電話告知對方相關資訊嗎？還是要傳送相關資訊到他們的個人電子郵件地址？他們還無法存取自己的 Office 365 電子郵件，因此您無法使用這個方法。

- 如果您有組織的功能變數名稱（例如 contoso.com） **，而**您計畫使用 Office 365 電子郵件，則必須知道您的網域註冊所在的位置，並且具備登入資訊。

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>執行 Office 365 設定精靈時會發生什麼狀況？

安裝精靈會逐步引導您在電腦上安裝 Office 365 應用程式、新增及驗證您的網域、新增使用者並指派授權給他們，以及連接您的網域。

> [!NOTE]
> 如果您需要[將 Office 365 for business 中的系統管理員角色指派](../add-users/assign-admin-roles.md)給您新增至嚮導的使用者，您可以稍後在 [**使用者**] 頁面上進行。 
  
如果您未完成安裝精靈，您可以隨時從系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **設定**完成安裝工作。 從這裡，您可以從其他電子郵件服務遷移電子郵件和連絡人、變更您系統管理員帳戶的網域、管理帳單資訊、新增或移除使用者、重設密碼，以及執行其他商務功能。 如需安裝精靈與**安裝程式**頁面之間差異的詳細資訊，請參閱[Office 365 安裝精靈與安裝程式頁面之間的差異](o365-setup-wizard-and-setup-page.md)。

如果您在任何時刻都停滯，請撥打 us。 [我們在這裡協助您！](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何時不應使用設定精靈：Active Directory 同步處理和混合式環境

有幾種情況會包含從內部部署環境遷移資料或使用者，或設定包含目錄同步處理的混合系統。 如果您處在任一類別中，請遵循下列文章中的指示：
  
- 若要設定內部部署 Active Directory 的目錄同步處理，請參閱[設定 Office 365 中的目錄同步作業](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)，而若要了解 Office 365 中不同的識別模型，請參閱[了解 Office 365 身分識別和 Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity)。

- 若要設定 Exchange 混合式，您可在下列找到關於引導您完成所有不同設定混合式 Exchange 的方式之整組指示 (包括設定 DNS 記錄)：[Exchange Server 部署助理](https://aka.ms/exdeploy)

- 若要設定 SharePoint 混合式 (尤其是混合式搜尋和網站功能)，請參閱[在 SharePoint 中的混合式搜尋](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>同時或分階段移至 Office 365

- **您想要同時將組織移至 Office 365 嗎？** 若是的話，請立即著手規劃，以便將網域移到 Office 365。 首先，執行 Office 365 設定精靈；精靈會提供提示，協助您設定網域。

- **您是否要逐步移至 Office 365？** 如果您想分階段漸進式移到 Office 365，請跳過 Office 365 設定精靈，並考慮按照下列順序採用 Office 365 功能：

    1. [將您的員工加入 Office 365](../add-users/add-users.md) ，以便讓他們下載及安裝 Office App。

    2. [下載及安裝 Office App](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)，以便在電腦和裝置上使用 Word、Excel 和 PowerPoint。

    3. [設定 Microsoft 團隊](#plan-for-teams)以用於會議。

    4. [將您的內容移至 Office 365 雲端儲存體](set-up-file-storage-and-sharing.md)（OneDrive 或 SharePoint 小組網站）。

    5. 當您準備好時，請在 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)] 的左功能窗格中，選取 [**安裝**]，然後使用 [**設定**] 頁面來[移動您的網域和電子郵件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>檢查您的裝置是否符合系統需求

組織中的每個人都可以在最多五部 Pc 和 Mac 上安裝 Office 2016 套件應用程式（Word、Excel、PowerPoint 等等）。 如需相關資訊，請參閱安裝商務用 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)的作業系統和電腦需求。
  
行動應用程式可以安裝在 iOS、Android 和 Windows 裝置上。 如需了解行動裝置和瀏覽器的相關支援資訊，請瀏覽 [Office 的系統需求](https://go.microsoft.com/fwlink/?LinkId=534827)。
  
## <a name="plan-for-email"></a>規劃電子郵件

如果您打算將現有的電子郵件服務移至 Office 365，通常需要兩天的時間來進行切換。
  
### <a name="plan-for-email-downtime"></a>規劃電子郵件服務停機
  
如果您要使用 Office 365 收發電子郵件：
  
- 若要將商務電子郵件地址（例如*rob@contoso.com*）從其他電子郵件服務移至 Office 365，您必須將郵件指引傳送至新的 Office 365 信箱。 若要執行此動作，請選取 [**設定**] 頁面上的 [**遷移使用者的資料**]，我們將引導您完成您在網域主機上進行的更新（逐步逐步進行）。

- 更新您的網域主機後，相關變更通常在 1 到 2 小時內就會生效。 不過，請注意，在網際網路上更新的變更有時可能需要長達72小時。

- 由於您的電子郵件服務可能會停機，建議您將切換到 Office 365 電子郵件的作業安排在晚上或週末這類較少來信的時段。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>移動現有電子郵件、連絡人和行事曆的相關規劃
  
如果要透過 Office 365 來使用您的電子郵件帳戶，您可以一併移轉現有的電子郵件、連絡人和行事曆。 在大多數情況下，[**安裝**] 頁面會協助您移動現有的電子郵件和連絡人。 我們也提供移動一或多個信箱的逐步指南。
  
|**信箱數量**|**建議**|
|:-----|:-----|
|只有幾個信箱  <br/> |如果您不想要使用「**安裝**」頁面來遷移信箱，您可以讓信箱擁有者遷移其自己的電子郵件和連絡人。 請參閱[將電子郵件和連絡人移轉到商務用 Office 365](migrate-email-and-contacts-admin.md)。  <br/> |
|多個信箱  <br/> |如果您是從 Gmail 進行遷移，請參閱[將 G Suite 信箱遷移至 Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。  <br/> 如果您是從另一個電子郵件提供者（包括 Exchange）進行遷移，請參閱[將多個電子郵件帳戶遷移至 Office 365 的方式](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>規劃檔案儲存空間與移轉

Office 365 為個人、小型組織和企業提供雲端儲存空間。 如需不同位置適合儲存哪些內容的相關指導，請參閱[您可以在 Office 365 中儲存文件的位置](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx)。
  
- **您可以將數百個檔案移**至[OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx)或[SharePoint 小組網站](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242)。 您一次可以上傳 100 個檔案。 預設的檔案大小上限為 2GB，因此請勿上傳超過此限制的檔案。
  
- **如果您想要將數千個檔案移**到 Office 365 儲存體，請參閱[SharePoint 線上限制](https://go.microsoft.com/fwlink/p/?LinkID=856113)。 建議您使用移轉工具，或考慮雇用[合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來協助您進行移轉。 如需如何移轉大量檔案的相關資訊，請參閱 [SharePoint Online 與 OneDrive 移轉使用者指南](https://go.microsoft.com/fwlink/?LinkId=723574)。
  
## <a name="plan-for-teams"></a>規劃小組

您可以使用 Microsoft 團隊撥打您的組織中的其他人員撥打您的訂閱。 例如，如果您的組織有10名人員，您可以使用沒有任何特殊設定的小組通話和 IM。 如需詳細資訊，請參閱[立即開始使用 Microsoft 團隊](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)。

若為較大的組織，或從商務用 Skype、內部部署或混合部署開始，請參閱[如何向外推廣 Microsoft 團隊](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>規劃與 Active Directory 或其他軟體整合

- **您要與內部部署的 Active Directory 整合嗎？** 您可以使用 Azure Active Directory 連線來整合內部部署的 Active Directory 與 Office 365。 如需相關指示，請參閱 [在 Office 365 中設定目錄同步處理](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。
  
- **您是否要將 Office 365 與其他公司製作的軟體整合？** 如果您需要將 Office 365 與組織中的其他軟體整合，建議您考慮[雇用合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來協助您進行部署。
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>您想讓他人協助您設定 Office 365 嗎？

- **如果您的員工少於 50 人：**

  - **尋求協助，我們會致電您**。 購買 Office 365 之後，您可以存取系統管理中心（您不需要執行安裝程式即可取得）。 在系統管理中心的底部，選取 [**需要協助]？** 請描述您的問題，我們會致電您。 
  - **如需問題，請致電[Office 365 For Business Support](../contact-support-for-business-products.md) **。 我們隨時為您效勞！ 
  - **請考慮聘用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)**。 如果您時間不足，或是有進階需求 (例如將數千個檔案移到 Office 365 雲端儲存空間，或是要與其他軟體整合)，經驗豐富的合作夥伴可助您一臂之力。 

- **如果您有超過50名員工**，可使用 FastTrack 的內[架中心](https://go.microsoft.com/fwlink/?LinkId=517115)來協助您進行部署。 
