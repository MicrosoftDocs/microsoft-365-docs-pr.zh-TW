---
title: 在整合式應用程式入口網站中測試及部署合作夥伴的 Microsoft 365 Apps
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 針對組織中的使用者和群組，從 Microsoft 365 系統管理中心中的整合式應用程式入口網站，尋找、測試及部署 microsoft 和 microsoft 合作夥伴應用程式。
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007054"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>在整合式應用程式入口網站中測試及部署合作夥伴的 Microsoft 365 Apps

Microsoft 365 系統管理中心可讓您靈活地從單一位置部署單一 store 應用程式、自訂業務線和 Microsoft 365 夥伴應用程式。 在整合式應用程式中，可以存取 Microsoft 系統管理中心設定中的位置。 透過 Microsoft 合作夥伴從整合的應用程式入口網站尋找、測試及完整部署已購買和授權的應用程式，可提供您組織所需的便利性和優點，讓商務服務定期更新並有效地運作。

如需購買及授權 Microsoft 365 來自組織之合作夥伴的應用程式的詳細資訊，請參閱[從 Microsoft 365 系統管理中心管理及部署 Microsoft 365 Apps](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。

如需合作夥伴如何建立這些應用程式的詳細資訊，請參閱 how [to plan a SaaS plan for the 商業性 marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

整合式應用程式入口網站只有全域系統管理員才能存取，而且只能供全球客戶使用。 以及主權和政府雲彩不提供此功能。

整合式應用程式入口網站會顯示應用程式的清單，其中包含部署組織之協力廠商的單一應用程式和 Microsoft 365 應用程式。 只會列出 web 應用程式、SPFx 應用程式 Office 增益集及 Teams 應用程式。 若為 web 應用程式，您可以看到兩種類型的應用程式。

- SaaS appsource.microsoft.com 中提供的應用程式，並可由系統管理員用來代表組織授與部署。
- 使用 office 增益集連結的 SAML 畫廊應用程式。

## <a name="manage-apps-in-the-integrated-apps-portal"></a>在整合式應用程式入口網站中管理應用程式

您可以管理從夥伴購買及授權的 Microsoft 365 Apps 的測試和部署。

1. 在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。

2. 選擇 [**可供** 使用的應用程式]**狀態** 的應用程式，以開啟 [**管理**] 窗格。 **可供使用的更多應用程式** 狀態，可讓您知道還有其他尚未部署的 isv 的整合。

3. 在 [ **概覽** ] 索引標籤上，選取 [ **部署**]。 某些應用程式會要求您先新增使用者，才能選擇 [部署]。

4. 選取 [  **使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織**]、[ **特定使用者/群組** ] 或 [ **僅自己**]。 如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。 特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。

5. 選取 [ **更新** ]，然後 **完成**。 您現在可以在 [概覽] 索引標籤上選取 [部署]。

6. 查看應用程式資訊，然後選取 [ **部署**]。

7. 在 [部署已完成] 頁面上，選取 [ **完成** ]，並在 [ **概覽** ] 索引標籤上複查測試或完整部署的詳細資料。

8. 若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [管理] 窗格，然後更新應用程式。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>尋找已發佈的應用程式進行測試和完整部署

您可以在 [整合式應用程式] 頁面上，找出未出現在清單中的已發佈應用程式，並加以測試及完全部署。 透過從系統管理中心購買及授權應用程式，您可以從單一位置將 Microsoft 和 Microsoft 合作夥伴應用程式新增至您的清單。

1. 在系統管理中心的左側導覽中，選擇 [**設定**]，然後選擇 [**整合式應用程式**]。

2. 選取 [ **取得應用** 程式] 以取得應用程式的視圖。

3. 在 [ **Microsoft 365 Apps** 發佈的應用程式] 頁面上，選擇您要部署的應用程式，方法是選擇 [**立即取得**]。 顯示的應用程式主要是 Word、PowerPoint、Excel、Outlook 增益集、Teams 應用程式，以及以 SharePoint 技術 (建立 SharePoint 架構應用程式) 。 接受許可權，然後選取 [ **繼續**]。

5. 在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。

    如果選取的應用程式連結到 ISV 所提供的 SaaS，則 [設定] 頁面上會出現屬於此連結提供之部分的所有其他應用程式。 如果您選擇部署所有應用程式，請選取 **[下一步]**。 否則，請選取 [ **編輯**]，然後選擇您要部署的應用程式。 某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。

6. 選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。

    特定的使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。 如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。

7. 選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。 列出每個應用程式的應用程式功能和許可權。 若應用程式需要同意，請選取 [ **接受許可權**]。 只有全域系統管理員可以授與同意。

8. 選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。 您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。 在 Microsoft 365 系統管理中心中，您可以看到每個已部署應用程式的狀態，以及您部署應用程式的日期。

> [!NOTE]
> 若應用程式先前部署自整合的應用程式入口網站，則 **部署類型** 是 **自訂的。**

## <a name="unsupported-scenarios"></a>不支持的案例

在下列情況下，您將無法從整合型應用程式入口網站部署單一 store 應用程式或 Microsoft 365 Apps。

- 同一個增益集會連結至多個 SaaS 提供。
- SaaS 提供會連結至增益集，但不會與 Microsoft Graph 整合，也不會提供任何 AAD 應用程式識別碼。
- SaaS 提供會連結至增益集，但是為 Microsoft Graph 整合所提供的 AAD 應用程式識別碼，可跨多個 SaaS 提供共用。

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload 自訂的企業營運應用程式，以進行測試及完整部署

1. 在系統管理中心的左側導覽中，選擇 [**設定**]，然後選擇 [**整合式應用程式**]。

2. 選取 [ **Upload 自訂應用程式**]。 只支援自訂行的應用程式（適用于 Word、PowerPoint Excel 和 Outlook）。

3. 從您的裝置 Upload 資訊清單檔案，或加入 URL 連結。 某些應用程式會要求您先新增使用者，才能選擇 [部署]。

4. 選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。

    特定的使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。 如果您想要等待將應用程式部署到整個組織，您也可以選擇 [ **測試部署** ]。

5. 選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。 列出應用程式的應用程式功能和許可權。 若應用程式需要同意，請選取 [ **接受許可權**]。 只有全域系統管理員可以授與同意。

6. 選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。 您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>準備在整合式應用程式中部署增益集

Office 增益集可協助您個人化檔，並簡化存取網頁上資訊的方式 (請參閱開始使用 Office 增益集) 。 

增益集提供下列優點： 

- 當相關的 Office 應用程式啟動時，增益集就會自動下載。 如果增益集支援增益集命令，增益集會自動出現在 Office 應用程式中的功能區。 

- 如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或將增益集指派給的群組中移除使用者，則使用者不再出現增益集。 

在三個桌面平臺 Windows，Mac 和線上 Office 應用程式都支援增益集。 iOS 和 Android (Outlook 僅限行動增益集) ，也支援此功能。 

增益集最多可能需要24小時才能顯示所有使用者的用戶端。 

目前 Exchange 系統管理員和全域系統管理員都可以從整合式應用程式部署增益集。   

### <a name="before-you-begin"></a>開始之前

部署增益集需要使用者使用 Microsoft 365 企業版授權 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。 使用者也需要使用其組織識別碼登入 Office) 並擁有 Exchange Online 和使用中 Exchange Online 信箱。 您的訂閱目錄必須是 in 或同盟 to Azure Active Directory。 

部署不支援下列各項： 

- 目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集 
- 內部部署目錄服務 
- 增益集部署至 Exchange 部署信箱 
-  (COM) 或 Visual Studio Tools for Office (VSTO) 增益集的元件物件模型部署。 
- 不包含 Exchange Online 的 Microsoft 365 部署，例如 Microsoft 365 Apps 的商務及 Microsoft 365 Apps Enterprise。  

### <a name="office-requirements"></a>Office要求 

若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項： 
- 在 Windows 裝置上，Microsoft 365 企業版授權的版本1704或更新版本 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。 
- 在 Mac 上，版本15.34 或更新版本。 

若為 Outlook，您的使用者必須使用下列其中一項： 
- 版本1701或更新版本的 Microsoft 365 企業版授權 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。 
- Office Professional Plus 2019 或 Office Standard 2019 的版本1808或更新版本。 
- 16.0.4494.1000 或更新版本的 Office Professional Plus 2016 (MSI) 或 Office Standard 2016 (MSI) 。
    > [!NOTE]
    > MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。  
- 15.0.4937.1000 或更新版本的 Office Professional Plus 2013 (MSI) 或 Office Standard 2013 (MSI) 。
- 適用于 Mac 的 Office 2016 版本16.0.9318.1000 或更新版本。 
- 2.75.0 或更新版本的 Outlook mobile for iOS。 
- 2.2.145 或更新版本的 Outlook mobile for Android。 



### <a name="exchange-online-requirements"></a>Exchange Online 需求 
Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。 部署增益集的系統管理員和接收這些增益集的使用者，必須位於支援 OAuth 驗證的 Exchange Online 版本上。 

請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。 您可以使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)PowerShell Cmdlet 來驗證每個使用者的 OAuth 連線能力   。 

### <a name="user-and-group-assignments"></a>使用者和群組指派
目前支援將增益集部署至大多數 Azure Active Directory 支援的群組，包括 Microsoft 365 群組、通訊群組清單和安全性群組。 部署支援最上層群組或沒有父項群組的群組中的使用者，但不支援具有父項群組的嵌套群組或群組中的使用者。 

> [!NOTE]
> 目前不支援未啟用郵件功能的安全性群組。 

在下列範例中，會將 Sandra、Sheila 及銷售部門群組指派給增益集。 由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。 

![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>確認群組是否包含巢狀群組

The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook. 如果您在電子郵件的 [ **至**] 欄位中輸入組名，   然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。 在下列範例中，測試群組的 Outlook 連絡人卡片的 [ **成員**] 索引標籤   不會顯示任何使用者，而且只會顯示兩個子群組。 

![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

You can do the opposite query by resolving the group to see if it's a member of any group. 在下列範例中，您可以在 Outlook 連絡人卡片的 [ <b>成員資格</b>] 索引標籤上看到，   子群組1是 Test group 的成員。 

![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

請注意，您可以使用 Azure Active Directory Graph API 來執行查詢，以找出群組中群組的清單。 如需詳細資訊，請參閱 [群組上的 Operations |圖形 API 參照](/previous-versions/azure/ad/graph/api/groups-operations)。 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 增益集的建議方法 
若要使用逐步式方法來推出增益集，建議您執行下列作業： 
1. 針對小組的商務專案關係人以及 IT 部門的成員推出增益集。 您可以開啟旗標 **為測試部署**。 如果部署成功，請移至步驟2。 

2. 向商務中的更多人員推出增益集。 請再次評估結果，如果成功，則繼續進行完整部署。 

3. 對所有使用者執行完整的展示。 從 [ **這是測試部署**] 中關閉旗標。 

視目標物件的大小而定，您可以新增或移除向外展開步驟。  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用系統管理中心部署 Office 增益集 

1. 在系統管理中心中，選取 [ **設定**]，然後選取 [ **整合式應用程式**]。 

2. 選取頁面頂端的 [ **取得應用程式** ]。 AppSource 會以內嵌的格式載入。 請搜尋增益集或透過按一下左側導覽上的 [產品] 來尋找。  若增益集已由 ISV 連結至 SaaS 應用程式或其他應用程式及增益集，且 SaaS 應用程式是付費應用程式，則會顯示一個對話方塊，以購買授權或部署。 不論您已購買授權，還是不可以繼續進行部署。 選取 [部署 **]**。  

3. 您將會看到 [設定 **] 頁面中** 列出所有的應用程式。 如果您沒有部署應用程式的許可權或正確存取權，將會反白顯示各自的資訊。 您可以選取您要部署的應用程式。 選取 **[下一步]**，即可查看 [ **使用者** ] 頁面。 若增益集尚未透過 ISV 連結，您會路由傳送至 [使用者] 頁面。 

4. 選取 [ **所有人**]、[ **特定使用者/群組**] 或 [ **僅限我**]，   以指定要部署增益集的人員。 使用 [搜尋] 方塊尋找特定的使用者或群組。 如果您要測試增益集，請選取 [ **這是測試部署**]。 

5. 選取 [下一步]。 所有應用程式功能和許可權會顯示在單一窗格中，如果應用程式有 Microsoft 365 認證，則會顯示認證資訊。 選取憑證標誌可讓使用者查看有關憑證的詳細資訊。  

6. 請複習，然後選取 **[完成部署]**。  

7. 部署增益集時，會出現綠色的「滴答」圖示。 依照頁面上的指示測試增益集。 

> [!NOTE]
> 使用者可能需要重新開機 Office 來查看應用程式功能區上的增益集圖示。 Outlook 增益集最多可能需要24小時才能出現在應用程式功能區上。 

建議使用已部署增益集的使用者和群組。 請考慮傳送描述何時及如何使用增益集的電子郵件。 包含或連結，以協助內容或 FAQs 如果增益集發生問題，可能會協助使用者。 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>將增益集指派給使用者和群組時的考慮事項 

全域管理員和 Exchange 系統管理員可以將增益集指派給每個人或特定使用者和群組。 每個選項都有其意涵： 

- **所有人**  此選項會將增益集指派給組織中的每一位使用者。 請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。 

- **使用者**  如果您將增益集指派給個別使用者，然後將增益集部署至新的使用者，您必須先新增新的使用者。 

- **群組**  如果您將增益集指派給群組，則新增至群組的使用者會自動指派增益集。 當使用者從群組中移除時，使用者將無法存取增益集。 在這兩種情況下，系統管理員不需要其他的動作。 

- **僅自己**  如果您將增益集指派給您自己，增益集就會指派給您的帳戶，這是測試增益集的理想選擇。 

組織的右選項視您的設定而定。 不過，我們建議您使用群組來進行工作分派。 身為系統管理員，您可能會發現使用群組來管理增益集及控制這些群組的成員資格，而不是每次指派個別使用者。 在某些情況下，您可能會想要限制一小部分使用者的存取，只要手動指派使用者給特定的使用者。 

### <a name="more-about-office-add-ins-security"></a>更多關於 Office 增益集的安全性 
Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：
- 顯示資料。 
- 閱讀使用者的文件以提供內容相關服務。 
- 從使用者的文件讀取及寫入資料，以提供值給該使用者。  

如需 Office 增益集類型和功能的相關資訊，請參閱 [Office 增益集平臺概述](/office/dev/add-ins/overview/office-add-ins)，尤其是「剖析 office 增益集」一節。 

若要與使用者的檔互動，增益集必須宣告資訊清單中所需的許可權。 五層級 JavaScript API 存取許可權模型為工作窗格增益集的使用者提供隱私權及安全性的基礎。Office 書店中的大部分增益集是層級 ReadWriteDocument，幾乎所有增益集至少都支援 ReadDocument 層級。 如需許可權等級的詳細資訊，請參閱 [要求用於內容和工作窗格增益集的 API 許可權](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)。 

更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。 

增益集的更新會以下列方式進行： 
- **企業營運增益集**：在此情況下，系統管理員明確上傳資訊清單的位置，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

- **Office store 增益集**：當系統管理員從 office store 中選取增益集時，如果 office store 中的增益集更新，下次相關的 Office 應用程式啟動時，增益集就會更新。 Web 應用程式可以隨時變更。 

> [!NOTE]
> Word、Excel 及 PowerPoint 會使用 [SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)   ，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。 Outlook 使用 Exchange 控制台在內部部署環境中部署，但不連接至 Microsoft 365。  

## <a name="add-in-states"></a>增益集狀態
增益集可以處於 [開啟] 或 [ ****   關閉] ****   狀態。 

| 狀態 | 狀態如何發生 | 影響 |
|:-----|:-----|:-----|
|**Active**  <br/> |系統管理員上載增益集，並將其指派給使用者或群組。  <br/> |被指派增益集的使用者和群組會在相關用戶端中看見增益集。  <br/> |
|**已關閉**  <br/> |系統管理員已關閉增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> 如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。  <br/> |
|**Deleted**  <br/> |系統管理員已刪除增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> |
 
如果沒有人再使用增益集，請考慮刪除增益集。 例如，如果增益集只會在一年的特定時間內使用，則關閉增益集可能會有意義。 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>使用系統管理中心管理 Office 增益集

部署後，系統管理員也可以管理使用者對增益集的存取。 

1. 在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。 
2. 在 [整合式應用程式] 頁面上，它會顯示應用程式的清單，這些應用程式會是單一增益集，也就是與其他應用程式連結的增益集。 
3. 選取 ****   [ **可供** 使用的應用程式狀態] 的應用程式   ，以開啟 [ **管理**   ] 窗格。  **可供使用的更多應用程式** 狀態，可   讓您知道還有其他尚未部署的 isv 的整合。 
4. 在 [ **概覽**] 索引標籤上   ，選取 [ **部署**]。 某些應用程式會要求您先新增使用者，才能選擇 [部署]。 
5. 選取 [ **使用者**]，選取 [ **這是測試部署**]，然後選取 [ **整個組織**]、[ **特定使用者/群組**]   或 [ **僅自己**]。  ****   如果您想要等待將應用程式部署至整個組織，也可以選取 [測試部署]。 特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。 
6. 選取 [ **更新**]   ，然後選取 [**完成**]。 您現在可以在 [**概覽**] 索引標籤上選取 [**部署**]。 
7. 查看應用程式資訊，然後選取 [ **部署**]。
8. 在  ****   [**部署已完成**] 頁面上，選取 [完成]，然後在 [ **概覽**] 索引標籤上複查測試或完整部署的詳細資料   。 
9. 若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [ **管理** ] 窗格，然後更新應用程式。 
10. 若只要更新使用者，請選取 [ **使用者** ] 索引標籤並進行適當的變更。 在進行變更後選取 [ **更新** ]。  

## <a name="delete-an-add-in"></a>刪除增益集

您也可以刪除已部署的增益集。

1. 在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。
2. 選取任何列以顯示管理窗格。 
3. 選取 [ **設定** ] 索引標籤。 
4. 選取您要刪除的增益集，然後選取 [ **移除**]。  

> [!NOTE]
>  如果增益集是由另一個系統管理員部署，則 [移除] 按鈕將會停用。 只有已部署應用程式或全域管理員的系統管理員可以刪除增益集。

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Exchange 系統管理員無法部署增益集的情況 

有兩種情況可供 Exchange 管理員無法部署增益集：
- 若增益集需要 MS Graph APIs 的許可權，且需要全域系統管理員的同意。
- 如果增益集連結至兩個或多個增益集和 webapps，且有至少一個增益集是由另一個系統管理員部署 (exchange/全域) ，且使用者指派不一致。 僅當所有已部署的應用程式的使用者指派相同時，我們才允許部署增益集。  


## <a name="frequently-asked-questions"></a>常見問題集

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>我需要哪些系統管理員角色才能存取整合式應用程式？

只有全域管理員才能存取整合式應用程式。 在其他系統管理員的左側導覽中，整合式應用程式不會顯示。

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>為什麼我會在左導覽的 [設定] 底下看到增益集，但不是集成應用程式？

原因如下：

- 登入的系統管理員是 Exchange 管理員。
- 客戶位於以及主權雲端，但整合型應用程式體驗可供以及主權雲端客戶使用。

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>我可以從整合式應用程式部署哪些應用程式？

整合式應用程式允許部署 Web 應用程式、Teams 應用程式、Excel、PowerPoint、Word、Outlook 增益集及 SPFx 應用程式。 針對增益集，整合式應用程式支援部署 Exchange 線上信箱，而非內部部署 Exchange 信箱。

### <a name="can-administrators-delete-or-remove-apps"></a>管理員可以刪除或移除應用程式嗎？

是。 全域管理員可以刪除或移除應用程式。

- 從清單視圖中選取應用程式。 **在 [設定**] 索引標籤上，選取要移除的應用程式。  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>以及主權雲端中是否有整合式應用程式？

否。 無法以及主權 cloud 客戶的整合式應用程式。

### <a name="is-integrated-apps-available-in-government-clouds"></a>政府雲端中是否有整合式應用程式？

否。 政府雲端客戶無法使用整合式應用程式。
