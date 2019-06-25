---
title: 加強 Microsoft 365 商務的威脅防護
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 設定 Office 365 高級威脅防護, 並保護機密資料。
ms.openlocfilehash: b6e9941eee9de4f295b0f8056c1c91b7076e530c
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668380"
---
# <a name="increase-threat-protection"></a>增加威脅防護

本文可協助您加強 Microsoft 365 訂閱中的保護, 以防範網路釣魚、惡意程式碼和其他威脅。 這些建議適用于對安全性有較高需求的組織, 例如法律辦公室和健康護理診所。

在您開始之前, 請先檢查您的 Office 365 安全分數。 Office 365 安全分數會根據您的一般活動和安全性設定來分析您的 Office 365 組織安全性, 並會指定分數。 請記下您目前的分數。 採取本文中建議的動作可提高您的分數。 目標不會達到最大分數, 但請注意, 保護您的環境不會對使用者的生產力造成不良影響的機會。 

如需詳細資訊, 請參閱[Microsoft 安全分數](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)。

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提升郵件中惡意程式碼的保護層級

您的 Office 365 或 Microsoft 365 環境包含對惡意程式碼的防護, 但是您可以使用常用於惡意程式碼的檔案類型來封鎖附件, 以增加這種保護。 若要以電子郵件加強惡意程式碼保護:
  
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
|提供訊息文字  <br/> |請勿從您不知道的人員那裡開啟這類檔案, 因為它們可能含有惡意程式碼的宏。  <br/> |
   
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
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>使用 ATP 安全附件來防止惡意附件和檔案

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
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>使用 ATP 安全連結來防禦網路釣魚攻擊

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

## <a name="go-to-intune-admin-center"></a>移至 Intune 系統管理中心

1. 登入[Azure 入口網站](https://portal.azure.com/)。

2. 選取 [**所有服務**], 然後在 [**搜尋**] 方塊中輸入*Intune* 。

3. 顯示結果後, 按一下 [ **Microsoft Intune** ] 旁的 [開始], 讓其成為最愛且易於尋找。

除了系統管理中心之外, 您還可以使用 Intune 來註冊及管理組織的裝置。 如需詳細資訊, 請參閱[Windows 裝置的註冊方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和[Intune 所管理之裝置的註冊選項](https://docs.microsoft.com/intune/enrollment-options)的功能。
