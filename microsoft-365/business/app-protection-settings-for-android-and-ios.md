---
title: 設定 Android 或 iOS 裝置的 App 保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何建立、 編輯或刪除應用程式管理原則及保護工時 Android 或 iOS 裝置上的檔案。
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866689"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>設定 Android 或 iOS 裝置的 App 保護設定

## <a name="create-an-app-management-policy"></a>建立應用程式管理原則

1. 使用全域系統管理員認證登入 [Microsoft 365 商務版](https://portal.office.com)。 
    
2. 在管理中心的 [**裝置原則**在卡片上，選擇 [**新增原則**]。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. 在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。 
    
4. **原則類型**] 下選擇 [ **For Android 應用程式管理**或想要建立的一組原則根據**IOS 的應用程式管理**]。 
    
5. 依序展開 [**保護工作檔案遺失或竊裝置的時機**和**管理使用者如何存取行動裝置上的 Office 檔案**\>您想方式進行設定。**管理使用者如何存取行動裝置上的 Office 檔案**的預設為**關閉，** 但建議您**加以開啟**並接受預設值。如需詳細資訊，請參閱[可用的設定](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings)。 
    
    您一律可以回復成預設值使用**預設設定重設**] 連結。 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. 接下來決定**誰將會得到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**，並選擇 [將會得到這些設定的安全性群組\>**選取**。
    
7. 最後，選擇 [**完成**儲存原則]，並將其指派給裝置。 
    
## <a name="edit-an-app-management-policy"></a>編輯應用程式管理原則

1. **原則**在卡片上，選擇 [**編輯原則**]。
    
2. 在 [**編輯原則**] 窗格中，選擇您想要變更的原則 
    
3. 選擇 [每個原則中的值變更設定] 旁的 [**編輯**]。值變更後，會自動儲存成原則 
    
4. 完成時，關閉 [**編輯原則**] 窗格中。 
    
## <a name="delete-an-app-management-policy"></a>刪除應用程式管理原則

1. **原則**在卡片上，選擇 [**刪除原則**]。
    
2. 在 [**刪除原則**] 窗格中，選擇您想要刪除之的原則\>**選取**，然後**確認**来刪除的原則或您所選擇的原則。 
    
## <a name="available-settings"></a>可用的設定

下表針對用來保護裝置上的工作檔案的設定，以及控管使用者透過行動裝置存取 Office 檔案方式的設定，提供相關的詳細資訊。
  
 如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>保護工作檔案的設定

以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|在下列天數之後刪除非作用中裝置上的工作檔案  <br/> |如果裝置在您於此處指定的天數內未有人使用，裝置上儲存的任何工作檔案會自動遭到刪除。  <br/> |
|強制使用者將所有工作檔案儲存到商務用 OneDrive  <br/> |**在**此設定時，才可使用儲存工作檔案的位置會 OneDrive for Business。  <br/> |
|加密工作檔案  <br/> |使加密由保護工時檔案保留**在**此設定。即使遺失或竊裝置，沒有人將能夠讀取您公司的資料。<br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定閒置多久之後，系統會提示使用者重新登入。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明使用者可能會有 jailbroken 或根目錄的裝置。這表示使用者可以修改作業系統，可讓裝置多受限於惡意程式碼。**在**此設定時封鎖這些裝置。<br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> |我們不要允許這根據預設，但如果設定為**在**使用者無法複製資訊工時檔案中個人的檔案。如果設定為**關閉**時，使用者將無法將資訊從工時帳戶複製到個人的應用程式或個人帳戶。<br/> |
   

  

