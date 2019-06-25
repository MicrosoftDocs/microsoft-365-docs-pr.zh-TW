---
title: 增加威脅防護
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: 取得在 Microsoft 365 商務版中增加保護層級的協助
ms.openlocfilehash: 2ebf6994cc7ba4026c5985e6b7accfc832ab003c
ms.sourcegitcommit: c7ea55e36484d64db3f3af8e111a83cfc634143e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "35192647"
---
# <a name="increase-threat-protection"></a>增加威脅防護

本文可協助您加強 Microsoft 365 訂閱中的保護, 以防範網路釣魚、惡意程式碼和其他威脅。 這些建議適用于增加安全性需求的組織, 例如政治活動、法律辦公室和健康護理診所。 

在您開始之前, 請先檢查您的 Office 365 安全分數。 Office 365 安全分數會根據您的一般活動和安全性設定來分析您的 Office 365 組織安全性, 並會指定分數。 請記下您目前的分數。 採取本文中建議的動作可提高您的分數。 目標不會達到最大分數, 但請注意, 保護您的環境不會對使用者的生產力造成不良影響的機會。 

如需詳細資訊, 請參閱[Microsoft 安全分數](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)。


## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提升郵件中惡意程式碼的保護層級

您的 Office 365 或 Microsoft 365 環境包含對惡意程式碼的防護, 但是您可以使用常用於惡意程式碼的檔案類型來封鎖附件, 以增加這種保護。 若要以電子郵件擴充惡意程式碼保護:
  
1. 移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳號憑證登入。 
    
2. 在 [Office 365 安全性&amp;規範中心] 的左功能窗格中, 選擇 [**威脅管理**] 下的 [**原則** \> **反惡意**代碼]。
    
3. 按兩下預設原則, 以編輯此全公司原則。
    
4. 按一下 [**設定**]。
    
5. 在 [**常用附件類型篩選**] 底下, 選取 [**開啟**]。 封鎖的檔案類型會列在此控制項下方的視窗中。  請確定您新增這些 filetypes:
   - ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、ht、hta、inf、jse、mdz、.pcd、、cmd、、、、、、、、、、、  <br/> 如有需要, 您可以稍後新增或刪除檔案類型。
    
6. 按一下 [儲存]****。
    
如需詳細資訊, 請參閱[反惡意程式碼保護](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。
  


## <a name="protect-against-ransomware"></a>防止勒索軟體

勒索軟體會透過加密檔案或鎖定電腦螢幕, 來限制資料存取權。 然後, 它會要求「ransom」 (通常是 Bitcoin 的 cryptocurrencies 形式) 來 extort 金錢, 並在 exchange 中存取資料。 
  
您可以透過建立一或多個郵件流程規則來封鎖勒索軟體 (這些副檔名會在 [在[郵件中提高惡意程式碼的防護等級](#raise-the-level-of-protection-against-malware-in-mail)] 步驟中新增), 或警告使用者收到這些郵件, 以防止勒索代碼電子郵件中的附件。

除了您在上一個步驟中封鎖的檔案之外, 也建議您先建立規則, 以在開啟包含宏的 Office 檔案附件之前警告使用者。 您可以在宏內隱藏勒索軟體, 因此我們會警告使用者不要從他們不知道的人開啟這些檔案。

若要建立郵件傳輸規則:
  
1. 移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理中心, 然後選擇 [系統**管理中心** \> ] [ **Exchange**]。
    
2. 在 [**郵件流程**] 類別中, 按一下 [**規則**]。
    
3. 按一下**+**[], 然後按一下 [**建立新規則**]。
    
4. 按一下對話方塊底部的 [**更多選項**], 以查看完整的選項群組。 
    
5. 在下表中套用規則的設定。 除非您想要變更這些設定, 否則預設保留其預設值。
    
6. 按一下 [儲存]****。
    
|**設定**|**開啟 Office 檔案的附件之前警告使用者**||
|:-----|:-----|:-----|
|名稱  <br/> |反惡意軟體規則: 警告使用者  <br/>  |
|若要套用此規則。 . .  <br/> |任何附件。 . . 副檔名相符。 . .  <br/> |
|指定字詞或片語  <br/> |新增下列檔案類型:  <br/> normal.dotm、.docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm  <br/>|
|請執行下列動作。 . .  <br/> |以郵件通知收件者  <br/> |
|提供訊息文字  <br/> |請勿從您不知道的人開啟這些類型的檔案, 因為它們可能含有惡意程式碼的宏。  <br/> |
   
如需詳細資訊，請參閱：
  
- [如何處理勒索軟體](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [還原您的 OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>停止電子郵件的自動轉寄功能

取得使用者信箱存取權的駭客可以透過將信箱設為自動轉寄電子郵件, 來竊取您的郵件。 即使沒有使用者的認知, 也可能會發生這種情況。 您可以設定郵件流程規則, 避免發生這種情況。 
  
若要建立郵件傳輸規則, 請觀看[這段簡短的影片](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7), 或遵循下列步驟:
  
1. 在 Microsoft 365 系統管理中心, 按一下 [系統**管理中心** \> ] [ **Exchange**]。
    
2. 在 [**郵件流程**] 類別中, 按一下 [**規則**]。
    
3. 按一下**+**[], 然後按一下 [**建立新規則**]。
    
4. 按一下對話方塊底部的 [**更多選項**], 以查看完整的選項群組。 
    
5. 套用下表中的設定。 除非您想要變更這些設定, 否則預設保留其預設值。
    
6. 按一下 [儲存]****。
    
|**設定**|**開啟 Office 檔案的附件之前警告使用者**|
|:-----|:-----|
|名稱  <br/> |防止自動將電子郵件轉寄至外部網域  <br/> |
|將此規則套用至 .。。  <br/> |寄件者。 . . 為 external/internal。 . . 組織內部  <br/> |
|新增條件  <br/> |郵件屬性。 . . 包含郵件類型。 . . 自動轉寄  <br/> |
|請執行下列動作 .。。  <br/> |封鎖郵件。 . . 拒絕郵件並包含說明。  <br/> |
|提供訊息文字  <br/> |因為安全性的原因, 無法自動將電子郵件轉寄到此組織外部。  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>保護您的電子郵件免受網路釣魚攻擊

如果您已為 Office 365 或 Microsoft 365 環境設定一或多個自訂網域, 您可以設定目標的反網路釣魚保護。 ATP 反網路釣魚防護, 部分的 Office 365 高級威脅防護, 可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。 如果您尚未設定自訂網域, 則不需要執行此動作。
  
我們建議您先建立一個原則, 以保護最重要的使用者和您的自訂網域, 以開始使用這項保護。 

  
若要建立 ATP 反網路釣魚原則, 請觀看[這個簡短的訓練影片](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), 或完成下列步驟:
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。 
    
2. 在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。
    
3. 在 [**原則**] 頁面上, 選擇 [ **ATP 反網路釣魚**]。
    
4. 在 [**反網路釣魚**] 頁面上, 選取 [ **+ 建立**]。 [! 注意] 會啟動嚮導, 以逐步定義您的反網路釣魚原則。
    
5. 請按照下表中的建議, 指定原則的名稱、描述和設定。 如需詳細資訊, 請參閱[瞭解 ATP 反網路釣魚原則選項](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。 
    
6. 檢查您的設定之後, 請視需要選擇 [**建立這個原則**] 或 [**儲存**]。
    

|**設定或選項**<br/>|**建議設定** <br/>|
|:-----|:-----|
|名稱  <br/> |網域和最有價值的活動人員  <br/> |
|描述  <br/> |確保最重要的人員和我們的網域不會受到類比。  <br/> |
|新增要保護的使用者  <br/> |選取 **+ [新增條件], 收件者是**。 輸入使用者名稱, 或輸入候選人、活動管理員及其他重要職員成員的電子郵件地址。 您最多可以新增20個要防止模擬的內部和外部地址。  <br/> |
|新增要保護的網域  <br/> |選取 **+ 新增條件, 收件者網域是**。 輸入與您的 Microsoft 365 訂閱相關聯的自訂網域 (如果您定義了的話)。 您可以輸入一個以上的網域。  <br/> |
|選擇動作  <br/> |如果由模擬的使用者傳送電子郵件: 選擇 [**將郵件重新導向至另一個電子郵件地址**], 然後輸入安全性系統管理員的電子郵件地址。例如,*劉愛琳<span><span>@contoso .com*。          如果由模擬的網域傳送電子郵件: 選擇 [**隔離郵件**]。  <br/> |
|信箱智慧  <br/> |根據預設, 當您建立新的反網路釣魚原則時, 會選取信箱智慧。 將此設定保留為 [**開啟**] 以取得最佳結果。  <br/> |
|新增信任的寄件者和網域  <br/> |您可以在這裡新增您自己的網域或任何其他信任的網域。  <br/> |
|套用至  <br/> |選取 **[收件**者] 網域。 在**其中任何一項**下, 選取 **[選擇**]。 選取 [ **+ 新增**]。 選取功能變數名稱旁的核取方塊, 例如*contoso。<span>com <span> *, 然後選取清單中的 [**新增**]。 選取 [**完成**]。  <br/> |
   
如需詳細資訊, 請參閱[設定 Office 365 ATP 反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。
  
## <a name="protect-against-malicious-attachments-files-and-links-with-advanced-threat-protection-atp"></a>使用高級威脅防護 (ATP) 來防止惡意附件、檔案及連結

![指向的橫幅https://aka.ms/aboutM365preview。](../business/media/m365admincenterchanging.png)

首先, 請確定<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>您在系統管理中心開啟新的系統管理中心預覽;開啟**新系統管理中心**文字旁的切換功能。

   ![新的系統管理中心預覽。](media/previewon.png)

如果您沒有在租使用者中看到含卡的 [**安裝**] 頁面, 請參閱如何在 Office 365 安全性&amp;與合規性中心完成這些步驟。 請參閱[設定安全性 & 合規性中心內的 atp 安全附件](#set-up-atp-safe-attachments-in-the-security--compliance-center), 並[設定安全性 & 規範中心內的 atp 安全連結](#set-up-atp-safe-links-in-the-security--compliance-center)。

1.  在左側導覽中, 選擇 [**安裝**]。
2. 在 [**設定**] 頁面**** 上, 選擇 [**增加來自高級威脅的保護**]。</br></br>
    ![選擇 [從高級威脅提升保護]。](media/startatp.png) 

3. 在 [**從高級威脅增加保護**] 頁面上, 選擇 [**開始**]。
4. 在開啟的窗格上, 選取 [電子郵件中的**連結和附件**] 旁的核取方塊、[**在 SharePoint、OneDrive 及小組中掃描**檔案] 和 [掃描**專案以尋找惡意內容**] 下的**office 桌面和 office Online 應用程式中的連結**。

      - 在 [**電子郵件中的連結和附件**] 底下, 輸入 [所有使用者], 或您要掃描其電子郵件的特定使用者。

    ![檢查所有的核取方塊, 以增加 protestion 的高級威脅。](media/setatp.png)
5. 選擇 [**建立原則**] 以開啟 ATP 安全附件和 atp 安全連結。

### <a name="set-up-atp-safe-attachments-in-the-security--compliance-center"></a>設定安全性 & 合規性中心內的 ATP 安全附件

人們會定期傳送、接收和共用附件, 例如檔、簡報、試算表等等。 只要查看電子郵件訊息, 就不一定容易知道附件是否安全或惡意。 Office 365 高級威脅防護包括 ATP 安全附件保護, 但是預設不會開啟此保護。 建議您建立新的規則, 以開始使用此保護。 這項保護延伸至 SharePoint、OneDrive 及 Microsoft 團隊中的檔案。
  
若要建立 ATP 安全附件原則, 請觀看[這段簡短的影片](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), 或完成下列步驟:
  
1. 移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳戶登入。 
    
2. 在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。
    
3. 在 [原則] 頁面上, 選擇 [ **ATP 安全附件**]。
    
4. 在 [安全附件] 頁面上, 選取 [**開啟 SharePoint、OneDrive 及 Microsoft 團隊**版的 ATP] 核取方塊, 以廣泛套用這種保護。 
    
5. 選取**+** 以建立新原則。 
    
6. 套用下表中的設定。 
    
7. 檢查您的設定之後, 請視需要選擇 [**建立這個原則**] 或 [**儲存**]。
    

|**設定或選項**|**建議設定** <br/>|
|:-----|:-----|
|名稱  <br/> |封鎖目前和未來已偵測到惡意程式碼的電子郵件。  <br/> |
|描述  <br/> |封鎖目前和未來的電子郵件和附件偵測到的惡意程式碼。  <br/> |
|儲存附件未知的惡意軟體回應  <br/> |Select **block-封鎖目前和未來的電子郵件和附件偵測到的惡意**代碼。  <br/> |
|在偵測上重新導向附件  <br/> |啟用重新導向 (選取此方塊) 輸入系統管理員帳戶或隔離的信箱設定。          如果惡意程式碼掃描附件時超時或發生錯誤, 請套用上述選取範圍 (選取此方塊)。  <br/> |
|套用至  <br/> |收件者網域是。 . . 選取您的網域。  <br/> |
   
如需詳細資訊, 請參閱[設定 Office 365 ATP 反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。
  
### <a name="set-up-atp-safe-links-in-the-security--compliance-center"></a>設定安全性 & 合規性中心內的 ATP 安全連結

駭客有時會在電子郵件或其他檔案的連結中隱藏惡意的網站。 Office 365 ATP 安全連結 (ATP 安全連結) 是 Office 365 高級威脅防護的一部分, 可提供電子郵件訊息和 Office 檔中的網頁位址 (Url) 驗證, 以協助保護您的組織。 保護是透過 ATP 安全連結原則所定義。
  
我們建議您執行下列動作:
  
- 修改預設原則以提升保護。
    
- 新增針對您網域中的所有收件者的新原則。
    
若要設定 ATP 安全連結, 請觀看[這個簡短的訓練影片](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), 或完成下列步驟:
  
1. 移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳戶登入。 
    
2. 在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。
    
3. 在 [原則] 頁面上, 選擇 [ **ATP 安全連結**]。
    
若要修改預設原則:
  
1. 在 [安全連結] 頁面的 [**適用于整個組織的原則**] 下, 選取**預設**原則。 
    
2. 在 [**電子郵件除外的設定**] 下, 選取 [ **office 365 專業增強版]、[office For iOS 和 Android**]。
    
3. 按一下 [儲存]****。 
    
若要建立以您網域中的所有收件者為目標的新原則:
  
1. 在 [安全連結] 頁面上, 按一下**+** [套用**至整個組織的原則**] 下的 [建立新原則]。 
    
2. 套用下表所列的設定。
    
3. 按一下 [儲存]****。 

|**設定或選項**|**建議設定** <br/>|
|:-----|:-----|
|名稱  <br/> |網域中所有收件者的安全連結原則  <br/> |
|選取郵件中未知潛在惡意 Url 的動作  <br/> |**當使用者按一下連結時, 會重新寫入並檢查已知惡意連結清單中的 [On url**]。  <br/> |
|使用安全附件掃描可下載的內容  <br/> |選取此方塊。  <br/> |
|套用至  <br/> |收件者網域是。 . . 選取您的網域。  <br/> |
   
如需詳細資訊, 請參閱[Office 365 ATP 安全連結](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。
  
## <a name="turn-on-the-unified-audit-log"></a>開啟統一的審計記錄檔

在安全性&amp;與合規性中心開啟 [審核記錄搜尋] 之後, 您可以在記錄中保留系統管理員和其他使用者活動, 並加以搜尋。 

您必須在 Exchange Online 中指派「審核記錄」角色, 以在 Microsoft 365 商務版訂閱中開啟或關閉審核記錄搜尋。 根據預設, 此角色會指派給 Exchange 系統管理中心的 [許可權] 頁面上的 [規範管理] 和 [組織管理] 角色群組。 Microsoft 365 中的全域系統管理員預設為此群組的成員。

1. 若要開啟 [審核記錄搜尋], 請移至系統管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , 然後在左側導覽中選擇 [系統**管理中心**] 底下的 [**規範**]。 
2. 在 [ **Microsoft 365 規範**] 頁面上, 選擇 [**更多資源**], 然後在**Office &amp; 365 安全性中心**卡片上**開啟**。

    ![選擇 [Office 365 安全性 & 合規性轎車] 上的 [開啟]。](media/gotosecandcomp.png)
3. 在 [安全性與合規性] 頁面上, 選擇 [**搜尋**], 然後按一下 [**審核記錄搜尋**]。
1. 在 [**審核記錄搜尋**] 頁面的頂端, 選擇 [**開啟審計**]。

功能開啟後, 您就可以搜尋檔案、資料夾及許多活動。 如需詳細資訊, 請參閱[search the audit log](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)。

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>調整 SharePoint 和 OneDrive 檔案和資料夾的匿名共用設定

(將預設的匿名連結到期時間變更為14天, 將預設共用類型變更為「特定人員」)若要變更 OneDrive 和 SharePoint 的共用設定:
1. 移至系統管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , 然後在左側導覽中選擇 [系統**管理中心**] 底下的 [ **SharePoint** ]。 
2. 在 SharePoint 系統管理中心, 移至 [**原則** \> ] [**共用**]。
3. 在 [**共用**] 頁面的 [檔案**和資料夾連結**] 下, 選取 [**特定人員**], 然後在 **[任何人] 連結的 [高級設定]** 底下, 選取 [**這些連結必須在這幾天內到期**], 然後輸入 14 (或其他數目的您想要限制連結壽命的天數)。

    ![選擇 [特定人員], 並將 [連結到期] 設定為14天。](media/anyonelinks.png)

## <a name="activity-alerts"></a>活動警示

您可以使用活動提醒追蹤系統管理員和使用者活動, 並偵測組織中的惡意程式碼和資料遺失保護事件。 您的訂閱包含一組預設原則, 但您也可以另外建立自訂原則。 如需詳細資訊, 請參閱[警示原則](https://docs.microsoft.com/office365/securitycompliance/alert-policies)。 例如, 如果您將重要檔案儲存在 SharePoint 中, 而不想讓任何人在外部共用, 您可以建立通知, 讓您在某人進行共用時提醒您。

下圖顯示 Microsoft 365 商務版隨附的預設原則。 <br/><br/>
    ![Microsoft 365 商務版隨附的預設警示原則。](media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>停用或管理行事曆共用

您可以防止組織中的人員共用其行事曆, 也可以管理他們可以共用的專案。 例如, 您可以將共用限制為僅限共用空閒/忙碌的時間。

1. 移至<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>系統管理中心, 然後選擇 [**設定** \> **服務] & 增益集**
2. 在 [**服務] & 增益集**] 頁面上, 選擇 [行事**曆**], 然後選擇您組織中的人員是否可以與擁有 Office 365 或 Exchange 的人員或任何人共用其行事曆。 
    如果您選擇與任何人共用, 您可以決定只共用空閒/忙碌資訊。

3. 選擇頁面底部的 [**儲存變更**]。

    下圖顯示不允許行事曆共用。 </br></br>
    ![顯示為不允許的外部行事曆共用的螢幕擷取畫面。](media/nocalendarsharing.png)

    下圖顯示使用只含空閒/忙碌資訊之電子郵件連結的行事曆共用時的設定。

   ![與任何人共用行事曆空閒/忙碌的螢幕擷取畫面。](media/sharefreebusy.png)

如果允許您的使用者共用其行事曆, 請參閱[這些指示](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)瞭解如何從網頁上的 Outlook 共用。