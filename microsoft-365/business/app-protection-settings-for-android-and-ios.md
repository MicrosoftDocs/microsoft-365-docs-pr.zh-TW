---
title: 設定 Android 或 iOS 裝置的 App 保護設定
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 瞭解如何在 Android 或 iOS 裝置上建立、編輯或刪除應用程式管理原則，以及保護工作檔。
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580287"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>設定 Android 或 iOS 裝置的 App 保護設定

本文適用于 Microsoft 365 商務進階版。

## <a name="create-an-app-management-policy"></a>建立應用程式管理原則

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 
    
2. 在左側導覽中，選擇 [ **裝置** \> **原則**] [ \> **新增**]。
  
3. 在 [ **新增原則** ] 窗格中，輸入這個原則的唯一名稱。 
    
4. 在 [ **原則類型**] 底下，選擇 [適用于 **Android 的應用程式管理** ] 或 [ **應用程式管理] iOS**，視您想要建立的原則組而定。 
    
5. 擴充 **當裝置遺失或遭竊時保護工作** 檔案，並 **管理使用者如何存取行動裝置上的 Office** 檔案。 設定您想要的設定。 **管理使用者在行動裝置上存取 Office** 檔案的方式預設為 **關閉**，但建議您 **將其開啟** 並接受預設值。 如需詳細資訊，請參閱 [可用設定](#available-settings)。 
    
    您可以隨時使用 [ **重設預設值設定** ] 連結，以回到預設設定。 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. 下一步決定 **神秘會取得這些設定嗎？** 如果您不想要使用預設的 [ **所有使用者** ] 安全性群組，請選擇 [ **變更**]，然後選擇 [會選取下列設定的安全性群組] \> ****。
    
7. 最後，選擇 [ **完成** ] 以儲存原則，並將其指派給裝置。 
    
## <a name="edit-an-app-management-policy"></a>編輯應用程式管理原則

1. 在 [ **原則** ] 卡片上，選擇 [ **編輯原則**]。
    
2. 在 [ **編輯原則** ] 窗格中，選擇您要變更的原則 
    
3. 選擇每個設定旁的 [ **編輯** ]，以變更原則中的值。 當您變更值時，會自動儲存于原則中。
    
4. 完成後，請關閉 [ **編輯原則** ] 窗格。 
    
## <a name="delete-an-app-management-policy"></a>刪除應用程式管理原則

1. 在 [ **原則** ] 頁面上，選擇原則，然後 **刪除**。
    
2. 在 [ **刪除原則** ] 窗格中，選擇 [ **確認** ]，以刪除您選擇的原則或原則。 
    
## <a name="available-settings"></a>可用的設定

下表提供可在裝置上保護工作檔案的詳細資訊，以及控制使用者如何存取其行動裝置的 Office 檔案的設定。
  
 如需詳細資訊，請參閱[Microsoft 365 商務進階版如何對應至 Intune 設定中的保護功能](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>保護工作檔案的設定

以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|在下列天數之後刪除非作用中裝置上的工作檔案  <br/> |如果裝置沒有用於您在此處指定的天數，將會自動刪除該裝置上儲存的任何工作檔。  <br/> |
|強制使用者將所有工作檔案儲存到商務用 OneDrive  <br/> |若此設定為 [**開啟**]，則只有商務用 OneDrive 工作檔案的可用儲存位置。  <br/> |
|加密工作檔案  <br/> |將此設定保持 **開啟** ，讓工作檔案受到加密保護。 即使裝置遺失或被盜，任何人都無法讀取您的公司資料。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是 **在使用者在** 其行動裝置上使用 Office 應用程式之前，除了使用者的使用者名稱和密碼以外，還必須提供另一種形式的驗證。<br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定會決定使用者在有多久之後才會收到重新登入的時間。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。 這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。 當此設定為 [ **開啟**] 時，即會封鎖這些裝置。  <br/> |
|不允許使用者將內容從 Office 應用程式複製到個人應用程式  <br/> |我們預設會允許這麼做，但如果設定為 **開啟**，使用者可以將工作檔案中的資訊複製到個人檔案。 如果設定為 [ **關閉**]，使用者將無法將工作帳戶中的資訊複製到個人應用程式或個人帳戶。  <br/> |
