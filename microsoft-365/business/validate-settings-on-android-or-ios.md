---
title: 驗證 Android 或 iOS 裝置上的 app 保護設定
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 3879084b42e8c00cc4abcd86c1a3d6761c0697a6
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718892"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>驗證 Android 或 iOS 裝置上的 app 保護設定

請遵循下列各節中的指示來驗證 Android 或 iOS 裝置上的 app 保護設定。
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>檢查使用者裝置上所運作的 app 保護設定

在您[設定 Android 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。 
  
首先，請確定將原則套用至您即將來進行驗證的應用程式。
  
1. 在 Microsoft 365 商務版[系統管理中心](https://portal.office.com)中，移至 [**原則** \> **編輯原則**。
    
2. 對於您建立安裝程式，在設定] 或 [另一個原則，您建立，並確認它強制執行該針對 Outlook，例如，選擇 [ **Android 版的應用程式原則**。 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>檢查 [需要 PIN 或指紋才能存取 Office App] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**需要 PIN 或指紋才能存取 Office app**設為**上**。
  
![請確定需要 PIN 或指紋才能存取 Office app 設定為 [開啟。](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。
    
2. 系統也會提示您輸入的 pin 碼，或使用指紋。
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>驗證 [嘗試失敗幾次之後重設 PIN ] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**重設 PIN 的天數之後失敗的嘗試**設為某個數字。 這是預設值為 5。 
  
1. 在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。
    
2. 根據原則指定的次數重複輸入不正確的 PIN。 您會看到提示，指出**已達到 PIN 嘗試限制**重設 pin 碼。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. 按下 [**重設 pin 碼**]。 您將提示以使用者的 Microsoft 365 商務版認證登入，然後才能設定新的 pin 碼。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定

在 [**編輯原則**] 窗格中，選擇**防範遺失或遭竊的裝置**旁邊的 [**編輯**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定，**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**上**。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 開啟包含附件的電子郵件，然後點選附件資訊旁邊的向下箭號圖示。
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    您會看到**無法儲存到裝置**上螢幕底部。 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > 目前 Android 裝置無法儲存到商務用 OneDrive，因此您只會看到本機儲存已遭到封鎖。 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**要求使用者重新登入之後 Office app 閒置的**設為分鐘數。 這是預設的 30 分鐘。 
  
1. 在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 現在，您應該會看到 Outlook 的收件匣。請不要觸控 Android 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。
    
3. 在 Android 裝置上存取 Outlook。
    
4. 系統會提示您輸入 pin 碼，您可以再次存取 Outlook 之前。
    
### <a name="validate-protect-work-files-with-encryption"></a>驗證 [使用加密保護工作檔案] 設定

在 [**編輯原則**] 窗格中，選擇**防範遺失或遭竊的裝置**旁邊的 [**編輯**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定**使用加密保護工作檔案**設為**上**，並**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**關閉**。
  
1. 在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 開啟包含幾個影像檔案附件的電子郵件。
    
3. 點選附件資訊旁邊的向下箭號圖示以儲存附件。
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. 系統可能會提示您允許 Outlook 存取裝置上的相片、媒體和檔案。 點選 [**允許**]。
    
5. 在畫面底端，選擇 [儲存**至裝置**，然後再開啟 [**圖片庫**] app。 
    
6. 您應該會在清單中看到一張經過加密的相片 (或數張相片，如果您儲存了多個影像檔案附件的話)。這張相片可能會在 [圖片] 清單中顯示為灰色的方形，中央有以白色圓圈包住的白色驚嘆號。
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>檢查使用者裝置上的 App 保護設定是否可正常運作

在您[設定 iOS 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。 
  
首先，請確定將原則套用至您即將來進行驗證的應用程式。
  
1. 在 Microsoft 365 商務版[系統管理中心](https://portal.office.com)中，移至 [**原則** \> **編輯原則**。
    
2. 對於您建立安裝程式，在設定] 或 [另一個原則，您建立，並確認它強制執行該 outlook，例如，選擇 [ **iOS 版的應用程式原則**。 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>驗證 [設定需要 PIN 才能存取 Office App] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**需要 PIN 或指紋才能存取 Office app**設為**上**。
  
![請確定需要 PIN 或指紋才能存取 Office app 設定為 [開啟。](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。
    
2. 系統也會提示您輸入的 pin 碼，或使用指紋。
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>驗證 [嘗試失敗幾次之後重設 PIN ] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**重設 PIN 的天數之後失敗的嘗試**設為某個數字。 這是預設值為 5。 
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。
    
2. 根據原則指定的次數重複輸入不正確的 PIN。 您會看到提示，指出**已達到 PIN 嘗試限制**重設 pin 碼。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. 按 **[確定]**。 您將提示以使用者的 Microsoft 365 商務版認證登入，然後才能設定新的 pin 碼。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定

在 [**編輯原則**] 窗格中，選擇**防範遺失或遭竊的裝置**旁邊的 [**編輯**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定，**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**上**。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 開啟包含附件的電子郵件、 開啟附件，並選擇畫面底部的 [**儲存**。 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. 您應該只會看到一個適用於商務用 OneDrive 的選項。 如果沒有，請點選 [**新增帳戶**，然後從 [**新增儲存體帳戶**] 畫面中選取 [**商務用 OneDrive** 。 在系統提示時提供使用者的 Microsoft 365 商務版以登入。 
    
    點選 [**儲存**]，然後選取 [**商務用 OneDrive**。
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定

在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**要求使用者重新登入之後 Office app 閒置的**設為分鐘數。 這是預設的 30 分鐘。 
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 現在，您應該會看到 Outlook 的收件匣。請不要觸控 iOS 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。
    
3. 在 iOS 裝置上存取 Outlook。
    
4. 系統會提示您輸入 pin 碼，您可以再次存取 Outlook 之前。
    
### <a name="validate-protect-work-files-with-encryption"></a>驗證 [使用加密保護工作檔案] 設定

在 [**編輯原則**] 窗格中，選擇**防範遺失或遭竊的裝置**旁邊的 [**編輯**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定**使用加密保護工作檔案**設為**上**，並**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**關閉**。
  
1. 在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。
    
2. 開啟包含幾個影像檔案附件的電子郵件。
    
3. 點選附件，然後點選 [**儲存**] 選項。 
    
4. 從主畫面開啟**相片**」 app。 您應該會看到一張經過加密的相片被儲存 (或數張相片，如果您儲存多個影像檔案附件的話)。 
    
---

