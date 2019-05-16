---
title: 設定 Android 或 iOS 裝置的 App 保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何建立、 編輯或刪除應用程式管理原則，和保護 Android 或 iOS 裝置上的工作檔案。
ms.openlocfilehash: 21cc1d91c2952c6e9414d3742c26547fc36016a5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073503"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>設定 Android 或 iOS 裝置的 App 保護設定

![指向橫幅https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>建立應用程式管理原則

1. 移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。 
    
2. 在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。
  
3. 在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。 
    
4. [**原則類型**] 下選擇 [ **Android 版的應用程式管理**」 或 「 您想要建立的原則組合而定的**IOS 版的應用程式管理**]。 
    
5. 展開 [**裝置遺失或遭竊時保護工作檔案**及**管理使用者如何存取行動裝置上的 Office 檔案**\>設定您想要的設定。 **管理使用者如何存取行動裝置上的 Office 檔案**的預設為**關閉，** 但建議您將它**開啟**，並接受預設值。 如需詳細資訊，請參閱[可用的設定](#available-settings)。 
    
    您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. 下一步] 決定**人員會收到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。
    
7. 最後，選擇 [**完成**] 以儲存原則，並將它指派到裝置。 
    
## <a name="edit-an-app-management-policy"></a>編輯應用程式管理原則

1. 在 [**原則**] 卡片中，選擇 [**編輯原則**]。
    
2. 在 [**編輯原則**] 窗格中，選擇您想要變更的原則 
    
3. 若要變更的原則中的值的每一項設定旁邊，選擇 [**編輯**]。 當您變更值時，系統會將變更內容儲存到原則。 
    
4. 當您完成時，關閉 [**編輯原則**] 窗格中。 
    
## <a name="delete-an-app-management-policy"></a>刪除應用程式管理原則

1. 在 [**原則**] 頁面上選擇原則，然後**刪除**。
    
2. 在 [**刪除原則**] 窗格中選擇 [**確認**刪除原則或您選擇的原則。 
    
## <a name="available-settings"></a>可用的設定

下表針對用來保護裝置上的工作檔案的設定，以及控管使用者透過行動裝置存取 Office 檔案方式的設定，提供相關的詳細資訊。
  
 如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>保護工作檔案的設定

以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|在下列天數之後刪除非作用中裝置上的工作檔案  <br/> |如果裝置在您於此處指定的天數內未有人使用，裝置上儲存的任何工作檔案會自動遭到刪除。  <br/> |
|強制使用者將所有工作檔案儲存到商務用 OneDrive  <br/> |如果**開啟**此設定時，只可以使用儲存的工作檔案的位置會商務用 OneDrive。  <br/> |
|加密工作檔案  <br/> |保持**在**此設定，以便透過加密功能保護工作檔案。 即使裝置遺失或遭竊，任何其他人都無法讀取您的公司資料。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定閒置多久之後，系統會提示使用者重新登入。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。 這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。 **此設定時**，會封鎖這些裝置。  <br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> |我們執行預設允許此行為，但如果設定為**上**，使用者無法複製資訊工作檔案中的個人檔案。 如果設定為**關閉**，使用者將無法將公司帳戶中的資訊複製到個人 app 或個人帳戶。  <br/> |
   

  

