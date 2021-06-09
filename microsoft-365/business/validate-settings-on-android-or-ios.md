---
title: 驗證 Android 或 iOS 裝置上的應用程式保護設定
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 瞭解如何在您的 Android 或 iOS 裝置中驗證 Microsoft 365 商務進階版應用程式保護設定。
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578060"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>驗證 Android 或 iOS 裝置上的應用程式保護設定

依照下列各節中的指示驗證 Android 或 iOS 裝置上的應用程式保護設定。
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>檢查使用者裝置上的應用程式保護設定是否正常運作

在您[設定 Android 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。 
  
首先，請確定原則套用至您要驗證的應用程式。
  
1. 在 Microsoft 365 商務進階版系統 [管理中心](https://portal.office.com)，移至 [**原則**] [ \> **編輯原則**]。
    
2. 針對安裝時所建立的設定，選擇 [ **Android 應用程式原則**]，或選擇您建立的其他原則，然後驗證是否強制執行 Outlook，例如。 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>檢查 [需要 PIN 或指紋才能存取 Office App] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **需要 PIN 或指紋才能存取 Office 應用程式** 設定為 [**開啟**]。
  
![請確定 [需要 PIN 或指紋才能存取 Office 應用程式] 設定為 [開啟]。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入。
    
2. 系統也會提示您輸入 PIN 或使用指紋。
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>驗證 [嘗試失敗幾次之後重設 PIN ] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定在 [失敗嘗試次數] 設定為 [一定] 數位 **後重設 PIN 碼失敗**。 預設為5。 
  
1. 在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入。
    
2. 根據原則指定的次數重複輸入不正確的 PIN。 您會看到一則提示，指出已 **接通 Pin 嘗試限制** 以重設 pin 碼。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. 按下 [ **重設 PIN**]。 系統會提示您使用使用者的 Microsoft 365 商務進階版認證進行登入，然後必須設定新的 PIN 碼。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定

在 [**編輯原則**] 窗格中，選擇 [防止 **遺失或被盜裝置防護**] 旁的 [**編輯**]，然後在 **裝置遺失或遭竊時展開 [保護工作檔**]，並確定 [**強制使用者將所有工作檔案儲存至商務用 OneDrive** ] 設定為 [**開啟**]。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 開啟包含附件的電子郵件，然後點選附件資訊旁邊的向下箭號圖示。
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    您將會看到畫面底部 **無法儲存至裝置** 。 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > 目前 Android 裝置無法儲存到商務用 OneDrive，因此您只會看到本機儲存已遭到封鎖。 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **Office 已閒置的應用程式中，需要使用者重新登入**，且已設定為數分鐘的時間。 預設為30分鐘。 
  
1. 在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 現在，您應該會看到 Outlook 的收件匣。請不要觸控 Android 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。
    
3. 在 Android 裝置上重新存取 Outlook。
    
4. 您必須先輸入 PIN 碼，才能再存取 Outlook。
    
### <a name="validate-protect-work-files-with-encryption"></a>驗證 [使用加密保護工作檔案] 設定

在 [**編輯原則**] 窗格中，選擇 [**針對遺失或被盜的裝置加以防護**] 旁邊的 [**編輯**]，然後在 **裝置遺失或遭竊時** 展開 [保護工作檔]，並確定 [**保護具有加密的工作** 檔] 已設為 [**開啟**]，然後 **強制使用者將所有工作檔案儲存到商務用 OneDrive** 已設定為 [**關閉**]。
  
1. 在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 開啟包含一些影像檔附件的電子郵件。
    
3. 點選附件資訊旁邊的向下箭號圖示以儲存附件。
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. 系統可能會提示您允許 Outlook 存取裝置上的相片、媒體和檔案。 按 [ **允許**]。
    
5. 在螢幕底部，選擇 [ **儲存至裝置** ]，然後開啟 **圖庫** 應用程式。 
    
6. 您應該會在清單中看到一張經過加密的相片 (或數張相片，如果您儲存了多個影像檔案附件的話)。這張相片可能會在 [圖片] 清單中顯示為灰色的方形，中央有以白色圓圈包住的白色驚嘆號。
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>檢查使用者裝置上的 App 保護設定是否可正常運作

在您[設定 iOS 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。 
  
首先，請確定原則套用至您要驗證的應用程式。
  
1. 在 Microsoft 365 商務進階版系統 [管理中心](https://portal.office.com)，移至 [**原則**] [ \> **編輯原則**]。
    
2. 針對安裝時所建立的設定，選擇 **iOS 的應用程式原則**，或選擇您建立的其他原則，然後在 Outlook 中驗證是否強制執行。 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>驗證 [設定需要 PIN 才能存取 Office App] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **需要 PIN 或指紋才能存取 Office 應用程式** 設定為 [**開啟**]。
  
![請確定 [需要 PIN 或指紋才能存取 Office 應用程式] 設定為 [開啟]。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入。
    
2. 系統也會提示您輸入 PIN 或使用指紋。
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>驗證 [嘗試失敗幾次之後重設 PIN ] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定在 [失敗嘗試次數] 設定為 [一定] 數位 **後重設 PIN 碼失敗**。 預設為5。 
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入。
    
2. 根據原則指定的次數重複輸入不正確的 PIN。 您會看到一則提示，指出已 **接通 Pin 嘗試限制** 以重設 pin 碼。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. 按 **[確定]**。 系統會提示您使用使用者的 Microsoft 365 商務進階版認證進行登入，然後必須設定新的 PIN 碼。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定

在 [**編輯原則**] 窗格中，選擇 [防止 **遺失或被盜裝置防護**] 旁的 [**編輯**]，然後在 **裝置遺失或遭竊時展開 [保護工作檔**]，並確定 [**強制使用者將所有工作檔案儲存至商務用 OneDrive** ] 設定為 [**開啟**]。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 開啟包含附件的電子郵件，開啟附件，然後選擇畫面底部的 [ **儲存** ]。 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. 您應該只會看到一個適用於商務用 OneDrive 的選項。 如果不是，請點擊 [**新增帳戶**]，然後從 [**新增儲存體帳戶**] 畫面中選取 [**商務用 OneDrive** ]。 當系統提示時，提供使用者的 Microsoft 365 商務進階版登入。 
    
    按一下 [**儲存**]，然後選取 [**商務用 OneDrive**]。
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定

在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **Office 已閒置的應用程式中，需要使用者重新登入**，且已設定為數分鐘的時間。 預設為30分鐘。 
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 現在，您應該會看到 Outlook 的收件匣。請不要觸控 iOS 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。
    
3. 再次存取 iOS 裝置上的 Outlook。
    
4. 您必須先輸入 PIN 碼，才能再存取 Outlook。
    
### <a name="validate-protect-work-files-with-encryption"></a>驗證 [使用加密保護工作檔案] 設定

在 [**編輯原則**] 窗格中，選擇 [**針對遺失或被盜的裝置加以防護**] 旁邊的 [**編輯**]，然後在 **裝置遺失或遭竊時** 展開 [保護工作檔]，並確定 [**保護具有加密的工作** 檔] 已設為 [**開啟**]，然後 **強制使用者將所有工作檔案儲存到商務用 OneDrive** 已設定為 [**關閉**]。
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。
    
2. 開啟包含一些影像檔附件的電子郵件。
    
3. 點擊附件，然後點擊它底下的 [ **儲存** ] 選項。 
    
4. 從主畫面開啟 **相片** 應用程式。 您應該會看到一張經過加密的相片被儲存 (或數張相片，如果您儲存多個影像檔案附件的話)。 
    
---

