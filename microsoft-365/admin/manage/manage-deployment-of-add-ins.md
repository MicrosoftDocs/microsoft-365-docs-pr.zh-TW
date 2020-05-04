---
title: 管理系統管理中心內增益集的部署
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用系統管理中心的集中式部署，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: 30f2c08aa895f63ed529b4390d208e3daa9d6d7b
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011708"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心中管理增益集的部署

Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。 作為系統管理員，您可以為組織中的使用者部署 Office 增益集。 您可以使用 Microsoft 365 系統管理中心的 [集中式部署] 功能來執行此動作。
  
若要將增益集部署至組織內的使用者和群組，[集中式部署] 是建議和功能最豐富的方法。 如需如何判斷您的組織是否可支援集中式部署的詳細資訊，請參閱判斷您的組織是否可使用[集中式部署增益集](centralized-deployment-of-add-ins.md)。
  
[集中式部署] 提供下列優點：
  
- 全域管理員可以將增益集直接指派給使用者、透過群組將增益集指派給多位使用者，或租使用者指派給每個人。
    
- 當相關 Office 應用程式啟動時，系統會自動為使用者下載增益集。如果增益集支援增益集命令，增益集會自動顯示在 Office 應用程式的 [功能區] 中。
    
- 如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或指派給的群組中移除該使用者，就不再顯示使用者的增益集。
    
> [!NOTE]
>  Word、Excel 及 PowerPoint 會使用[SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。 > Outlook 使用 Exchange 控制台，在內部部署環境中部署，但不連接至 Microsoft 365。 > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 增益集的建議方式

請考慮採用分階段的方式來推出增益集，這樣有助於確保增益集部署順利進行。我們的建議方案如下：
  
1. 為一小組商務專案關係人以及 IT 部門的成員推行增益集。評估部署是否成功，如果成功，則請繼續進行步驟 2。
    
2. 為企業中將需使用增益集的一大組人員推行。同樣地，請評估成果，如果一切順利，則請繼續進行完整部署的下一個步驟。
    
3. 為目標對象使用者完全推行。
    
視目標對象的大小規模而定，您可能會想要新增或移除推行步驟。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用系統管理中心部署 Office 增益集

開始之前，請參閱[判斷集中式部署的增益集是否適用于您的組織](centralized-deployment-of-add-ins.md)。

  
1. 在系統管理中心中，移至 [**設定** \> **增益集**] 頁面。
    
2. 在頁面頂端，選取 [**部署增益集**]。 在 [概覽] 頁面上，選取 **[下一步]**。
    
3. 選取 [選項]，然後依照指示執行。
  
4. 如果您選取 [從 Office 書店新增增益集] 選項，您現在可以將增益集選取範圍。 請注意，您可以透過**為您建議的**類別、**評級**或**名稱**來查看可用的增益集。 您只能從 Office 市集新增免費的增益集。 目前尚不支援付費增益集。 在您選取增益集之後，您必須同意一些額外的條款及條件，才能繼續進行。 <br/><br/> 附注：使用 Office Store 選項時，系統會自動將增益集的更新及增強功能提供給使用者，而不需要您介入。

5. 在下一個頁面上，選取 [**所有人**]、[**特定使用者/群組**] 或 [**僅限我**]，以指定要部署增益集的人員。 使用 [搜尋] 方塊，尋找您要將增益集部署到哪個使用者或群組。 <br/>附注：瞭解適用于增益集的其他狀態。 請參閱本主題稍後介紹的[增益集狀態](#add-in-states)。
  
6. 選取 [**部署**]。
  
7. 部署增益集時，會出現綠色的勾選標記。 您可以依照頁面上的指示測試增益集是否已成功部署。

> [!NOTE]
> 使用者可能需要重新開機 Office，才能看到增益集圖示出現在應用程式的功能區上。 在使用者的功能區上顯示 Outlook 增益集時，最多可能需要12小時。
    
8. 完成時，選取 **[下一步]**。 如果您只是自行部署，您可以選取 [**變更擁有增益集的存取**權]，以部署至其他使用者。



如果您已將增益集部署至組織的成員以外的成員，請遵循顯示的指示，以有效宣告增益集的部署。 <br/>現在，您可以在 Microsoft 365 中看到增益集和其他應用程式。
  
將增益集部署到使用者和群組後，建議您告知他們，這樣他們才會知道已經可以使用增益集。 請考慮傳送電子郵件給他們，說明使用增益集的時機與方法，並解說增益集對於提升工作效率有何幫助。 包含或連結至相關的說明內容或 FAQs，可協助使用者是否有任何問題增益集。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>將增益集指派給使用者和群組時的考慮事項

系統管理員可以將增益集指派給所有人或特定的使用者和群組。 每個選項都有其意涵：
  
- **所有人**：顧名思義，此選項會將增益集指派給租使用者中的每位使用者。 請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。 
    
- **使用者**：如果您將增益集指派給個別使用者，然後若要將增益集部署至新的使用者，您必須先新增該使用者。 移除使用者時也是如此。 
    
- **群組**：如果您將增益集指派給群組，則新增至群組的使用者會自動被指派增益集。 此外，移除群組中的使用者後，該使用者就會失去增益集的存取權。 在任何一種情況下，身為系統管理員的您都不需要執行額外的動作。 

- **僅限我**：如果您將增益集指派給您自己，就會將增益集指派給您的帳戶。 如果您想要先測試增益集，這是理想的選擇。
    
您的組織適合的選項取決於您的設定。 不過，建議透過群組執行指派。 身為系統管理員，比起每次必須變更指派的使用者，使用群組來管理增益集及控制這些群組的成員資格可能會比較輕鬆。 另一方面，在某些情況下，您可能會想要將存取權限制於一小組使用者以內，因而指派特定的使用者。 因此，您必須以手動方式管理被指派的使用者。
  
### <a name="add-in-states"></a>增益集狀態

增益集可以處於 [**開啟**] 或 [**關閉**] 狀態。
  
|**State**|**狀態如何發生**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |系統管理員上載增益集，並將其指派給使用者或群組。  <br/> |被指派增益集的使用者和群組會在相關用戶端中看見增益集。  <br/> |
|**已關閉**  <br/> |系統管理員已關閉增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> 如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。  <br/> |
|**Deleted**  <br/> |系統管理員已刪除增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> |
   
如果沒有人再使用增益集，請考慮刪除增益集。 如果只有在一年的某些特殊時段需要使用增益集，關閉增益集可能會是比較合理的做法。
  
### <a name="security-of-office-add-ins"></a>Office 增益集的安全性

Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：
  
- 顯示資料。
    
- 閱讀使用者的文件以提供內容相關服務。
    
- 從使用者的文件讀取及寫入資料，以提供值給該使用者。
    
如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://go.microsoft.com/fwlink/p/?linkid=846362) (尤其是「分析 Office 增益集」一節)。
  
若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](https://go.microsoft.com/fwlink/p/?linkid=848863) (英文)。
  
更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。
  
增益集的更新會以下列方式進行：
  
- **企業營運增益集：** 在此情況下，管理員明確上傳資訊清單的地方，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

    > [!NOTE]
    > 管理員不需要移除 LOB 增益集進行更新。   在 [增益集] 區段中，系統管理員只要按一下 LOB 增益集，然後選擇右下角的 [**更新] 按鈕**即可。 只有當新增益集的版本高於現有增益集的版本時，更新才會運作。   
    
- **Office Store 增益集：** 當系統管理員從 Office Store 中選取增益集時，如果 Office Store 中的增益集更新，增益集將在稍後的集中式部署中更新。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

### <a name="edit-add-in-access"></a>編輯增益集存取

部署後，系統管理員也可以修改使用者對增益集的存取權。

1. 在系統管理中心中，移至 [**設定** > **服務] & 增益集**] 頁面。

2. 選取部署的增益集。

3. 按一下 [在**誰可以存取**] 底下的 [**編輯**]。
4. 儲存變更。
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>關閉所有用戶端（Outlook 除外）的 Office Store 以避免增益集下載

> [!NOTE]
> Outlook 增益集安裝是由[不同](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)的程式管理。

做為組織，您可能想要防止從 Office Store 下載新的 Office 增益集。 這可以與集中式部署搭配使用，以確保只有組織認可的增益集部署至組織內的使用者。
  
若要關閉增益集採集：
  
1. 在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。
    
3. 選取 [**使用者擁有的應用程式和服務**]。
    
4. 清除 [讓使用者存取 Office store] 選項。

這會防止所有使用者從存放區中取得下列增益集。
  
- Word、Excel 及 PowerPoint 2016 的增益集，來自：
    
  - Windows
    
  - Mac
    
  - 辦公室
    
    
- 從**AppSource**中開始的購置
    
- Microsoft 365 中的增益集
    
嘗試存取儲存區的使用者會看到下列訊息：**對不起，Microsoft 365 已設定為防止個別購買 Office store 增益集。**
  
下列版本提供支援關閉 Office 書店的功能：
  
- Windows： 16.0.9001-目前可供使用。
    
- Mac： 16.10.18011401-目前可供使用。
    
- iOS： 2.9.18010804-目前可供使用。
    
- 目前可用的 web。
    
這不會讓系統管理員使用集中式部署從 Office Store 指派增益集。
  
若要防止使用者使用 Microsoft 帳戶登入，您可以限制登入只使用組織帳戶。 如需詳細資訊，請參閱[此處](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>對存放區中的增益集進行未成年人和取得

一般資料保護規定（GDPR）是一種歐盟法規，它會生效25，2018。 它可讓使用者具備及保護其資料的權力。 其中一個 GDPR 的其中一個方面是，所有未成年人都無法將其個人資料傳送給他們的父系或監護人未獲核准的協力廠商。 定義為次要的特定年齡取決於個人所在的地區。
  
法律規定具有「父母同意」規定的地區包括美國、韓國、英國和歐盟。 對於這些地區，次要會封鎖（透過 Azure Active Directory）從存放區取得任何新的 Office 增益集，並執行先前取得的增益集。 對於沒有法令規定的國家，將不會有下載限制。
  
根據 Azure Active Directory 中所指定的資料，將使用者判斷為次要。 承租人管理員負責宣告法律年齡群組和該使用者的「父母同意」。
  
如果父項/監護人 consents 使用特定增益集，則租使用者管理員可以使用集中式部署，將該增益集部署至所有已同意的未成年人。
  
若要 GDPR 相容性，您必須確定在學校/組織中部署下列 Office 組建中的其中一項。
  
 **Word、Excel、PowerPoint 及專案**： 
  
|||
|:-----|:-----|
|**平台** <br/> |**組建號碼** <br/> |
|適用于企業的 Microsoft 365 應用程式（每月通道）  <br/> |9001.2138   <br/> |
|適用于企業的 Microsoft 365 應用程式（半年通道）  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|網頁版 Office  <br/> |不適用  <br/> |
   
 **Outlook**： 
  
|||
|:-----|:-----|
|**平台** <br/> |**組建號碼** <br/> |
|Outlook 2016 for Windows （MSI）  <br/> |建立無待定  <br/> |
|Outlook 2016 for Windows （C2R）  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|iOS 的 Outlook mobile  <br/> |2.75.0  <br/> |
|適用于 Android 的 Outlook mobile  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |不適用  <br/> |
   
 **Office 2013 需求**
  
如果已啟用 Active Directory 驗證程式庫（ADAL），Windows 的 Word、Excel 及 PowerPoint 2013 會支援相同的次要檢查。 規範有兩個選項，如接下來所述。
  
- **啟用 ADAL**。 本文說明如何啟用 ADAL for Office 2013：搭配[使用 Microsoft 365 新式驗證與 office 用戶端](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)。<br/>您也需要將登錄機碼設定為啟用 ADAL，如在[Windows 裝置上啟用 Office 2013 新式驗證](../security-and-compliance/enable-modern-authentication.md)中所述。<br/>此外，您必須安裝下列 Office 2013 的四月更新：
    
  - [Office 2013 的安全性更新說明：4月10日（2018）](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日，Office 2013 的更新（KB4018333）](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **不要啟用 ADAL**。 如果您無法在 Office 2013 中啟用 ADAL，我們建議使用「群組原則」來關閉 Office 用戶端的存放區。 有關如何關閉 Office 相關應用程式設定的資訊位於[這裡](https://technet.microsoft.com/library/cc178992.aspx)。
    
## <a name="end-user-experience-with-add-ins"></a>使用者的增益集使用體驗

既然您已部署增益集，使用者就可以開始在他們的 Office 應用程式中使用 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。增益集會顯示在增益集支援的所有平台上。
  
如果增益集支援增益集命令，命令會顯示在 Office 功能區上。 在下列範例中，會出現**引文**增益集的命令**搜尋引文**。 

![具有搜尋引文的 Office 功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的增益集不支援增益集命令，或是您想要查看所有已部署的增益集，您可以透過**My 增益集**進行查看。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 選取 **[ \>插入我的增益集**]。 
    
2. 在 [Office 增益集] 視窗中，選取 [**管理受管理**] 索引標籤。 
    
3. 按兩下您先前部署的增益集（在此範例中為 [**引文**]）。 <br/>![[Office 增益集] 頁面的 [管理受管理] 索引標籤](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在 [**首頁**] 功能區上，選取 [**取得增益集**]。<br/>![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)
  
2. 選取左側導覽中的 [系統**管理管理**]。

## <a name="delete-the-add-in"></a>刪除增益集

您也可以刪除已部署的增益集。

1. 在系統管理中心中，移至 [**設定** > **服務] & 增益集**] 頁面。

2. 選取部署的增益集。

3. 按一下 [**刪除] Add-In**。 移除右下角的增益集按鈕。
4. 驗證您的選擇，然後選擇 [**移除增益集**]。
  
## <a name="learn-more"></a>深入了解

深入了解如何建立及建置 [Office 增益集](https://go.microsoft.com/fwlink/p/?linkid=846362)。
  
[使用集中式部署 PowerShell Cmdlet 來管理增益集](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)。
  
[疑難排解：使用者未看到增益集](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
