---
title: Office 365 中增益集在系統管理中心的管理部署
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
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
description: 了解如何在系統管理中心使用集中式部署，將增益集部署至您的組織中使用者和群組。
ms.openlocfilehash: b2fe57bd2b3b51ac5097723613c608580da06bea
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361948"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中管理 Office 365 增益集的部署

Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。 身為系統管理員，您可以在組織中部署 Office 增益集的使用者。 您可以在 Microsoft 365 系統管理中心中使用 [集中式部署] 功能。
  
集中式的部署] 是建議且最功能豐富的方法，大部分的系統管理員將增益集部署至使用者和組織中的群組。 如需有關如何判斷貴組織是否可支援 [集中式部署] 的詳細資訊，請參閱[判斷您的 Office 365 組織是否適合使用 [集中式部署] 來部署增益集](centralized-deployment-of-add-ins.md)。
  
[集中式部署] 提供下列優點：
  
- 直接給使用者、 群組中，透過多個使用者或租用戶中的每個人都全域系統管理員可以指派增益集。
    
- 當相關 Office 應用程式啟動時，系統會自動為使用者下載增益集。如果增益集支援增益集命令，增益集會自動顯示在 Office 應用程式的 [功能區] 中。
    
- 增益集不會再出現的使用者如果系統管理員會關閉或刪除增益集，或者使用者已從 Azure Active Directory 或增益集指派給群組。
    
> [!NOTE]
>  對於 Word，Excel 及 PowerPoint 使用[SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)將增益集部署到未連線到 Office 365 及 （或） 支援的 SharePoint 增益集所需的內部部署環境中的使用者。 >  針對 Outlook，請使用 Exchange 控制台來在未連線到 Office 365 的內部部署環境中進行部署。 > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 增益集的建議方式

請考慮採用分階段的方式來推出增益集，這樣有助於確保增益集部署順利進行。我們的建議方案如下：
  
1. 為一小組商務專案關係人以及 IT 部門的成員推行增益集。評估部署是否成功，如果成功，則請繼續進行步驟 2。
    
2. 為企業中將需使用增益集的一大組人員推行。同樣地，請評估成果，如果一切順利，則請繼續進行完整部署的下一個步驟。
    
3. 為目標對象使用者完全推行。
    
視目標對象的大小規模而定，您可能會想要新增或移除推行步驟。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>部署 Office 增益集使用系統管理中心

開始之前，請參閱[判斷您的 Office 365 組織是否適合使用 [集中式部署] 來部署增益集](centralized-deployment-of-add-ins.md)。

  
1. 在系統管理中心，移至 [**設定** \> **增益集**] 頁面。
    
2. 選取 [**部署增益集**] 頁面的頂端。 在 [概觀] 頁面上，選取 [**下一步**]。
    
3. 選取一個選項，並遵循指示。
  
4. 如果您選取 [從 Office 市集新增增益集] 選項，您現在可以讓您增益集的選取範圍。 請注意，您可以檢視可用增益集透過類別的**建議為您**、**評等**，或**名稱**。 您只能從 Office 市集新增免費的增益集。 目前尚不支援付費增益集。 一旦您已經選取增益集，您必須同意才能繼續執行一些其他條款和條件。 <br/><br/> 附註： 使用 Office 市集選項時，更新和增強功能的增益集將會自動可供您無需介入的使用者。

5. 在下一個頁面上，選取**所有人**、**特定使用者/群組**或**只是我**來指定增益集部署至使用者。 使用 [搜尋] 方塊，尋找您要將增益集部署到哪個使用者或群組。 <br/>附註： 了解適用於增益集的狀態。 請參閱本主題稍後介紹的[增益集狀態](#add-in-states)。
  
6. 選取 [**部署**]。
  
7. 增益集已部署時，會顯示綠色刻度。 您可以遵循若要測試的增益集已部署成功] 頁面上的指示。

> [!NOTE]
> 使用者可能需要重新啟動 Office，以查看出現在應用程式的功能區上的 [增益集] 圖示。 Outlook 增益集可能需要最多 12 小時才會出現在使用者的功能區上。
    
8. 完成後，選取 [**下一步**]。 如果您已部署至只給您自己，您可以在才能部署到多個使用者選取**有權存取增益集的變更**。



如果您已部署增益集以外自行貴組織的成員，請遵循顯示才能有效地宣布增益集的部署指示。 <br/>您現在會在 Office 365 中看見您的增益集以及其他 App。
  
將增益集部署到使用者和群組後，建議您告知他們，這樣他們才會知道已經可以使用增益集。 請考慮傳送電子郵件給他們，說明使用增益集的時機與方法，並解說增益集對於提升工作效率有何幫助。 包含或連結到相關的說明內容或常見問題集，如果使用者有任何增益集的問題可能會幫助。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>將增益集指派給使用者和群組時的考慮事項

系統管理員可以將增益集指派給所有人或特定的使用者和群組。 每個選項都有其意涵：
  
- **所有人**： 顧名思義，此選項會將指定的增益集給租用戶中的每位使用者。 請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。 
    
- **使用者**： 如果您的增益集指派給個別使用者，然後增益集部署到新的使用者，您必須先新增該使用者。 移除使用者時也是如此。 
    
- **群組**： 如果您將增益集指派給群組，新增至群組的使用者將會自動指派增益集。 此外，移除群組中的使用者後，該使用者就會失去增益集的存取權。 在任何一種情況下，身為系統管理員的您都不需要執行額外的動作。 

- **僅自己**： 如果您將增益集指派給只給您自己，這樣會將指定的增益集至您的帳戶。 這是理想如果您想要測試增益集第一次。
    
最適合貴組織的選項取決於您的設定。 不過，建議透過群組執行指派。 身為系統管理員，比起每次必須變更指派的使用者，使用群組來管理增益集及控制這些群組的成員資格可能會比較輕鬆。 另一方面，在某些情況下，您可能會想要將存取權限制於一小組使用者以內，因而指派特定的使用者。 因此，您必須以手動方式管理被指派的使用者。
  
### <a name="add-in-states"></a>增益集狀態

增益集可以是在**開啟**或**關閉**狀態。
  
|**State**|**狀態如何發生**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |系統管理員上傳增益集，並將其指派給使用者或群組。  <br/> |被指派增益集的使用者和群組會在相關用戶端中看見增益集。  <br/> |
|**已關閉**  <br/> |系統管理員已關閉增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> 如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。  <br/> |
|**Deleted**  <br/> |系統管理員已刪除增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> |
   
請考慮刪除增益集，如果沒有人在有人使用。 如果只有在一年的某些特殊時段需要使用增益集，關閉增益集可能會是比較合理的做法。
  
### <a name="security-of-office-add-ins"></a>Office 增益集的安全性

Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：
  
- 顯示資料。
    
- 閱讀使用者的文件以提供內容相關服務。
    
- 從使用者的文件讀取及寫入資料，以提供值給該使用者。
    
如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://go.microsoft.com/fwlink/p/?linkid=846362) (尤其是「分析 Office 增益集」一節)。
  
若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](https://go.microsoft.com/fwlink/p/?linkid=848863) (英文)。
  
更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。
  
增益集的更新會以下列方式進行：
  
- **-營運增益集：** 在此情況下，系統管理員明確上傳資訊清單，其中的增益集需要系統管理員上傳新的資訊清單檔案，以支援中繼資料變更。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

    > [!NOTE]
    > 系統管理員不需要若要移除的 LOB 增益集進行更新。   在增益集] 區段中，系統管理員可以只是按一下 LOB 增益集，然後選擇右下角中的**更新] 按鈕**。 只有當新的增益集的版本是大於的現有的增益集，將運作更新。   
    
- **Office 市集增益集：** 當系統管理員選取增益集從 Office 市集，如果增益集更新 Office 市集中時，增益集將會更新稍後集中式部署。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

### <a name="edit-add-in-access"></a>編輯增益集的存取

張貼部署，系統管理員也可以修改增益集的使用者存取。

1. 在系統管理中心，移至 [**設定** > **服務 & 增益集**] 頁面。

2. 選取已部署的增益集。

3. 按一下在 [**誰可以存取**的 [**編輯**]。
4. 儲存所做的變更。
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>防止增益集的下載項目，藉由關閉 Office 市集總所有用戶端 (除了 Outlook)

> [!NOTE]
> Outlook 增益集安裝的管理方式的[不同程序](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)。

為組織，您可能想要防止新 Office 增益集從 Office 市集下載。 這可以用搭配集中式部署來確保只有組織核准增益集部署到組織內的使用者。
  
若要關閉增益集擷取：
  
1. 在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。
    
3. 選取 [**使用者所擁有的應用程式與服務**]。
    
4. 清除，讓使用者可存取 Office 存放區] 選項。

這會防止所有使用者取得下列增益集從存放區。
  
- 增益集的 Word、 Excel 及 PowerPoint 2016 中：
    
  - Windows
    
  - Mac
    
  - 辦公室
    
  - iOS （僅限 ipad 版）
    
- 收購**AppSource**內開始
    
- 增益集在 Office 365
    
嘗試存取存放區的使用者會看到下列訊息：**連到顯示抱歉，Office 365 已設定為防止 Office 市集新增寫的個別擷取**
  
關閉 Office 市集的支援位於下列版本：
  
- Windows: 16.0.9001-目前無法使用。
    
- Mac: 16.10.18011401-目前無法使用。
    
- iOS: 2.9.18010804-目前無法使用。
    
- Web-目前無法使用。
    
這不防止系統管理員從 Office 市集增益集指派使用集中式部署。
  
若要防止使用者登入 Microsoft 帳戶後，您可以限制使用組織的帳戶登入。 如需詳細資訊，請查看[以下](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年人獲取和取得增益集從存放區

一般資料保護規定 (GDPR) 會變成有效歐盟規定 2018 年 5 月 25 日。 它會提供使用者的權限和其資料的保護。 GDPR 的層面是未成年人獲取不能有傳送給其父或守護者未核准的廠商其個人資料。 定義為次要的特定保留取決於個別所在的區域。
  
有關於家長的同意法定之擔保規定的區域包含美國、 南韓、 英國及歐盟地區。 這些區域中，次要粗俗 （透過 Azure Active Directory) 從市集取得任何新 Office 增益集並執行增益集已先前取得的。 國家/地區而法定之擔保規定，會沒有下載限制。
  
使用者決定要在 Azure Active Directory 中指定的資料為基礎的次要。 租用戶系統管理員負責宣告法律保留天數群組和該使用者的家長的同意。
  
如果父/守護者 consents 來使用特定的增益集次要，租用戶系統管理員可以將該增益集部署至所有已獲同意未成年人獲取使用集中式的部署。
  
若要設為 GDPR 合規性的未成年人獲取您必須確保下列組建 Office 的其中一個可部署在您的學校/組織。
  
 **如 Word、 Excel、 PowerPoint 和 Project**: 
  
|||
|:-----|:-----|
|**平台** <br/> |**組建號碼** <br/> |
|Windows 版 office 2016 專業增強版每月  <br/> |9001.2138   <br/> |
|Office 2016 專業增強版的半年  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 2016 for iOS （僅限 ipad 版）  <br/> |2.12.18032600  <br/> |
|網頁版 Office  <br/> |不適用  <br/> |
   
 **Outlook**: 
  
|||
|:-----|:-----|
|**平台** <br/> |**組建號碼** <br/> |
|Outlook 2016 for Windows (MSI)  <br/> |建立沒有 TBD  <br/> |
|Outlook 2016 for Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|IOS 版 outlook 行動裝置  <br/> |2.75.0  <br/> |
|Android 版行動裝置的 outlook  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |不適用  <br/> |
   
 **Office 2013 需求**
  
Word、 Excel 及 PowerPoint 2013 for Windows 會支援相同的次要檢查，如果已啟用 Active Directory Authentication Library (ADAL)。 有兩個選項的符合性下, 一步] 所述。
  
- **啟用 ADAL**。 本文說明如何啟用 ADAL for Office 2013：[使用 Office 365 的 Office 用戶端啟用新式驗證](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)。<br/>您也必須設定[Windows 裝置上的 Office 2013 啟用新式驗證](../security-and-compliance/enable-modern-authentication.md)所述啟用 ADAL 登錄機碼。<br/>此外，您需要安裝的下列年 4 月更新 Office 2013:
    
  - [說明 Office 2013 的安全性更新： 2018 年 4 月 10 日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018 年 4 月 3 日，更新適用於 Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **請不要啟用 ADAL**。 如果您無法啟用 ADAL Office 2013 中的，我們建議是使用群組原則來關閉 office 用戶端的存放區。 如何關閉 Office 設定的應用程式的資訊是位[在這裡](https://technet.microsoft.com/library/cc178992.aspx)。
    
## <a name="end-user-experience-with-add-ins"></a>使用者的增益集使用體驗

既然您已部署增益集，使用者就可以開始在他們的 Office 應用程式中使用 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。增益集會顯示在增益集支援的所有平台上。
  
如果增益集支援增益集命令，命令會顯示在 Office 功能區上。 在下列範例中，顯示**Search Citation**命令**引文**增益集。 

![具有搜尋引文的 office 功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果已部署的增益集不支援增益集命令，或如果您想要檢視所有部署增益集，您可以透過 **「 我的增益集**檢視它們。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 選取**插入\>我的增益集**。 
    
2. 在 [Office 增益集] 視窗中選取 [**系統管理**] 索引標籤。 
    
3. 連按兩下 [增益集在您部署更早版本 （在本例中為**Citations** ）。 <br/>![系統管理] 索引標籤的 [Office 增益集] 頁面上](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. **家用版**功能區上，選取 [**取得增益集**]。<br/>![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)
  
2. 選取左側的 [**系統管理**

## <a name="delete-the-add-in"></a>刪除增益集

您也可以刪除已部署的增益集。

1. 在系統管理中心，移至 [**設定** > **服務 & 增益集**] 頁面。

2. 選取已部署的增益集。

3. 按一下 [**刪除增益集**]。 移除在右下角的 [增益集] 按鈕。
4. 驗證您的選項，然後選擇 [**移除增益集**。
  
## <a name="learn-more"></a>深入了解

深入了解如何建立及建置 [Office 增益集](https://go.microsoft.com/fwlink/p/?linkid=846362)。
  
[使用集中式部署 PowerShell cmdlet 來管理增益集](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)。
  
[疑難排解： 使用者找不到增益集](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
