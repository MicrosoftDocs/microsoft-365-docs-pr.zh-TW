---
title: 規劃您的商務用 Microsoft 365 設定
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 瞭解移轉商務用 Microsoft 365 時的需求與考慮事項。
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926819"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>規劃您的商務用 Microsoft 365 設定

本文適用于訂閱商務用 Microsoft 365 方案的人。
  
將貴組織移往 Microsoft 365 之前，您需要符合一些需求、需要的資訊，以及必須做出的決策。


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>執行設定精靈之前手邊的資訊

當您準備好執行設定精靈，將網域移至 Microsoft 365 時，您需要備好以下資訊：
  
- 您想要新增到 Microsoft 365 的人清單。 即使您已將它們新增到 Microsoft 365，如果您要更新您的網域資訊，您必須在此輸入其名稱。

- 您將如何通知員工他們的使用者識別碼和密碼，以便他們進行登錄。 您要透過電話告知對方相關資訊嗎？ 還是要傳送相關資訊到他們的個人電子郵件地址？ 他們無法存取其電子郵件，因此您因此無法使用它。

- 如果您的組織有功能變數名稱 (例如 contoso.com) ，而且您打算使用 Microsoft 電子郵件，您必須知道在哪裡註冊您的網域並擁有註冊資訊。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>執行 Microsoft 365 設定精靈時會發生什麼情況

設定精靈會逐步引導您在電腦上安裝 Microsoft 365 App、新增和驗證網域、新增使用者並指派授權給他們，以及連接您的網域。

> [!NOTE]
> 如果您需要將商務用 [Microsoft 365](../add-users/assign-admin-roles.md) 中的系統管理員角色指派給精靈中新增的使用者，您可以稍後在使用者頁面上 **執行** 這項操作。 
  
如果您沒有完成設定精靈，您隨時都可以從系統管理中心設定 [完成設定](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **工作**。 您可以從這裡移移其他電子郵件服務的電子郵件和連絡人、變更系統管理員帳戶的網域、管理帳單資訊、新增或移除使用者、重設密碼，以及執行其他商務功能。 有關設定精靈和設定頁面之間的差異詳細資訊，請參閱 Microsoft  [365](o365-setup-wizard-and-setup-page.md)設定精靈和設定頁面之間的差異。

如果您遇到任何無法連絡的問題，請打電話給我們。 [我們在此説明您！](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何時不應使用設定精靈：Active Directory 同步處理和混合式環境

有一些情境會涉及從內部部署環境移移資料或使用者，或設定包含目錄同步處理的混合式系統。 如果您屬於這兩種類別，請遵循下列文章中的指示：
  
- 若要設定與內部部署 Active Directory 的目錄同步處理，請參閱 [設定 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)的目錄同步處理，若要瞭解 Microsoft 365 中不同的身分識別模式，請閱讀瞭解 [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)身分識別與 Azure Active Directory。

- 若要設定 Exchange 混合式，您可在下列找到關於引導您完成所有不同設定混合式 Exchange 的方式之整組指示 (包括設定 DNS 記錄)：[Exchange Server 部署助理](https://aka.ms/exdeploy)

- 若要設定 SharePoint 混合式 (尤其是混合式搜尋和網站功能)，請參閱[在 SharePoint 中的混合式搜尋](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>一次或階段全部移至 Microsoft 365

- **您想要將貴組織一次全部移至 Microsoft 365 嗎？** 若是如此，請規劃將網域馬上移至 Microsoft 365。 首先執行 Microsoft 365 設定精靈;它會提示您設定您的網域。

- **您想要逐漸移往 Microsoft 365 嗎？** 如果您想要階段性地移往 Microsoft 365，請略過執行 Microsoft 365 設定精靈，並考慮按照下列順序採用 Microsoft 365 功能：

    1. [將員工新增到 Microsoft 365，](../add-users/add-users.md) 以便下載並安裝 Office App。

    2. [下載及安裝 Office App](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以便在電腦和裝置上使用 Word、Excel 和 PowerPoint。

    3. [設定 Microsoft Teams](#plan-for-teams) 以用於您的會議。

    4. [將內容移至 OneDrive](set-up-file-storage-and-sharing.md) 或 SharePoint 小組網站的 Microsoft 365 (儲存空間) 。

    5. 當您準備好時，請在系統管理中心 [](https://go.microsoft.com/fwlink/p/?linkid=2024339)選取左側流覽窗格中的設定，然後使用 **設定頁面來** 移動 [您的網域和電子郵件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>檢查您的裝置是否符合系統需求

貴組織的每個人都可以在最多五部 PC 和 Mac 上安裝 Office 2016 應用程式套件 (Word、Excel、PowerPoint 等) 。 如需相關資訊，請參閱安裝商務用 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)的作業系統和電腦需求。
  
行動裝置 App 可以安裝在 iOS、Android 和 Windows 裝置上。 如需了解行動裝置和瀏覽器的相關支援資訊，請瀏覽 [Office 的系統需求](https://go.microsoft.com/fwlink/?LinkId=534827)。
  
## <a name="plan-for-email"></a>規劃電子郵件

如果您打算從現有的電子郵件服務移移至 Microsoft 365，切換通常會需要兩天的時間。
  
### <a name="plan-for-email-downtime"></a>規劃電子郵件服務停機
  
如果您要使用 Microsoft 365 電子郵件：
  
- 若要將公司電子郵件地址 (例如 *rob \@ contoso.com*) 從另一個電子郵件服務移至 Microsoft 365，您必須將郵件引導至新的 Microsoft 365 信箱。 若要這麼做，**請選取設定** 頁面上的遷移使用者資料，我們會逐步引導您完成在網域主機上的更新。

- 更新您的網域主機後，相關變更通常在 1 到 2 小時內就會生效。 但請注意，變更有時最多可能需要 72 小時才能在網際網路上更新。

- 由於您的電子郵件服務可能會中斷，建議您計畫在晚上或週末收到較少的電子郵件時切換到 Microsoft 電子郵件。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>移動現有電子郵件、連絡人和行事曆的相關規劃
  
如果您要將 Microsoft 365 用於電子郵件帳戶，您可以一併攜帶現有的電子郵件、連絡人和日曆。 在 **大部分** 情況下，設定頁面可協助移動現有的電子郵件和連絡人。 我們也提供移動一或多個信箱的逐步指南。
  
|**信箱數量**|**建議**|
|:-----|:-----|
|只有幾個信箱  <br/> |如果您不想使用設定頁面來移動信箱，您可以讓信箱擁有者自行移動電子郵件和連絡人。 請參閱[將電子郵件和連絡人遷移到商務用 Microsoft 365。](migrate-email-and-contacts-admin.md)  <br/> |
|多個信箱  <br/> |如果您要從 Gmail 移移，請參閱將 G Suite 信箱移[移至 Microsoft 365。](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> 如果您要從包括 Exchange 在內的其他電子郵件提供者移移，請參閱將多個電子郵件帳戶移移 [至 Microsoft 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>規劃檔案儲存空間與移轉

Microsoft 365 提供個人、小型組織和企業的雲端儲存空間。 若要瞭解儲存位置的哪些內容，請參閱 [您可以在 Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)中儲存檔的位置。
  
- **您可以將數百個檔案移至** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) 或 [SharePoint 小組網站](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 您一次可以上傳 100 個檔案。 預設的檔案大小上限為 2GB，因此請勿上傳超過此限制的檔案。
  
- **如果您要將數千** 個檔案移至 Microsoft 365 儲存空間，請查閱 [SharePoint Online 限制](https://go.microsoft.com/fwlink/p/?LinkID=856113)。 建議您使用移轉工具，或考慮雇用[合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來協助您進行移轉。 如需如何移轉大量檔案的相關資訊，請參閱 [SharePoint Online 與 OneDrive 移轉使用者指南](https://go.microsoft.com/fwlink/?LinkId=723574)。
  
## <a name="plan-for-teams"></a>規劃 Teams

您可以使用 Microsoft Teams 撥打電話給組織中訂閱的其他人員。 例如，如果貴組織有 10 人，您可以使用 Teams 互相通話和互發 IM，而不需要任何特殊設定。 詳細資訊請參閱開始使用[Microsoft Teams。](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)

若是較大型的組織，或如果您是從商務用 Skype、內部部署或混合式部署開始，請參閱如何推出[Microsoft Teams。](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>規劃與 Active Directory 或其他軟體整合

- **您要與內部部署的 Active Directory 整合嗎？** 您可以使用 Azure Active Directory Connect 整合內部部署 Active Directory 與 Microsoft 365。 有關指示，請參閱 [設定 Microsoft 365 的目錄同步處理](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)。
  
- **您想要將 Microsoft 365 與其他公司所開發的軟體整合嗎？** 如果您需要將 Microsoft 365 與貴組織的其他軟體整合，建議您考慮雇用合作夥伴[](https://go.microsoft.com/fwlink/?linkid=391089)來説明您部署。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>您是否希望某人説明您設定 Microsoft 365？

- **如果您的員工少於 50 人：**

  - **請尋求協助，我們會打電話給您**。 購買 Microsoft 365 之後，您可以存取系統 (因此不需要執行設定，也不需要執行設定，) 。 在系統管理中心底部，選取需要 **協助嗎？** 描述您的問題，我們會打電話給您。 
  - **如 [有疑問，請打電話給 Microsoft 365](../contact-support-for-business-products.md) 商務支援人員**。 我們隨時為您效勞！ 
  - **考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)**。 如果您時間很短，或是有進 (例如將數千個檔案移動到 Microsoft 365 雲端儲存空間，或與其他軟體) 整合，經驗豐富的合作夥伴可說是大幫手。 

- **如果您的員工超過 50** 人， [您可以使用 FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) 上線中心來説明您部署。 
