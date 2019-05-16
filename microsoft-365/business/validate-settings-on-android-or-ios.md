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
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: d4ed70290b21b40ca9ecd5601954c429a27dc528
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072363"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="27f62-103">驗證 Android 或 iOS 裝置上的 app 保護設定</span><span class="sxs-lookup"><span data-stu-id="27f62-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="27f62-104">請依照下列索引標籤中的指示來驗證 Android 或 iOS 裝置上的 app 保護設定。</span><span class="sxs-lookup"><span data-stu-id="27f62-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="27f62-105">Android</span><span class="sxs-lookup"><span data-stu-id="27f62-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="27f62-106">檢查使用者裝置上的 App 保護設定是否可正常運作</span><span class="sxs-lookup"><span data-stu-id="27f62-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="27f62-107">在您[設定 Android 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="27f62-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="27f62-108">首先，確認原則已套用到您要驗證的 App。</span><span class="sxs-lookup"><span data-stu-id="27f62-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="27f62-109">在 Microsoft 365 商務版[系統管理中心](https://portal.office.com)前往**原則** \> **編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="27f62-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="27f62-110">對於您建立安裝程式，在設定] 或 [另一個原則，您建立，並確認它強制執行該 outlook，例如，選擇 [ **Android 版的應用程式原則**。</span><span class="sxs-lookup"><span data-stu-id="27f62-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="27f62-112">檢查 [需要 PIN 或指紋才能存取 Office App] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="27f62-113">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，設定**需要 PIN 或指紋才能存取 Office app**若要**在上**。</span><span class="sxs-lookup"><span data-stu-id="27f62-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="27f62-115">在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。</span><span class="sxs-lookup"><span data-stu-id="27f62-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="27f62-116">系統也會提示您輸入 PIN 或使用指紋。</span><span class="sxs-lookup"><span data-stu-id="27f62-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="27f62-118">驗證 [嘗試失敗幾次之後重設 PIN ] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="27f62-119">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**重設 PIN 的天數之後失敗的嘗試**設為部分number-這是預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="27f62-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="27f62-120">在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。</span><span class="sxs-lookup"><span data-stu-id="27f62-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="27f62-121">根據原則指定的次數重複輸入不正確的 PIN。</span><span class="sxs-lookup"><span data-stu-id="27f62-121">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="27f62-122">您會看到提示，指出**已達到 PIN 嘗試限制**重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="27f62-122">You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="27f62-124">按下 [**重設 pin 碼**]。</span><span class="sxs-lookup"><span data-stu-id="27f62-124">Press **Reset PIN**.</span></span> <span data-ttu-id="27f62-125">系統會提示您以使用者的 Microsoft 365 商務版認證登入，並要求您設定新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="27f62-125">You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="27f62-126">驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="27f62-127">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯\*\*\*\*防範遺失或遭竊的裝置**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定該**強制使用者將所有工作檔案都儲存到 OneDrive商務**設為**上**。</span><span class="sxs-lookup"><span data-stu-id="27f62-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="27f62-129">在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-130">開啟包含附件的電子郵件，然後點選附件資訊旁邊的向下箭號圖示。</span><span class="sxs-lookup"><span data-stu-id="27f62-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="27f62-132">您會看到**無法儲存到裝置**上螢幕底部。</span><span class="sxs-lookup"><span data-stu-id="27f62-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="27f62-134">目前 Android 裝置無法儲存到商務用 OneDrive，因此您只會看到本機儲存已遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="27f62-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="27f62-135">驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="27f62-136">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定要求使用者重新登入之後 Office app 閒置該**針對**設至部分的分鐘數-這是預設的 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="27f62-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="27f62-137">在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-p103">現在，您應該會看到 Outlook 的收件匣。請不要觸控 Android 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。</span><span class="sxs-lookup"><span data-stu-id="27f62-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="27f62-141">重新存取 Android 裝置上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="27f62-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="27f62-142">系統會提示您輸入 PIN，以便重新存取 Outlook。</span><span class="sxs-lookup"><span data-stu-id="27f62-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="27f62-143">驗證 [使用加密保護工作檔案] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="27f62-144">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯\*\*\*\*防範遺失或遭竊的裝置**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定**保護工作檔案加密**設定為 [ **]**，並且**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f62-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="27f62-145">在使用者的 Android 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-146">開啟包含幾個影像檔案附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="27f62-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="27f62-147">點選附件資訊旁邊的向下箭號圖示以儲存附件。</span><span class="sxs-lookup"><span data-stu-id="27f62-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="27f62-149">系統可能會提示您允許 Outlook 存取裝置上的相片、媒體和檔案。</span><span class="sxs-lookup"><span data-stu-id="27f62-149">You may be prompted to allow Outlook to access photos, media, and files on your device.</span></span> <span data-ttu-id="27f62-150">點選 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="27f62-150">Tap **Allow**.</span></span>
    
5. <span data-ttu-id="27f62-151">在畫面底端，選擇 [儲存**至裝置**，然後再開啟 [**圖片庫**] app。</span><span class="sxs-lookup"><span data-stu-id="27f62-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="27f62-p105">您應該會在清單中看到一張經過加密的相片 (或數張相片，如果您儲存了多個影像檔案附件的話)。這張相片可能會在 [圖片] 清單中顯示為灰色的方形，中央有以白色圓圈包住的白色驚嘆號。</span><span class="sxs-lookup"><span data-stu-id="27f62-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="27f62-155">iOS</span><span class="sxs-lookup"><span data-stu-id="27f62-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="27f62-156">檢查使用者裝置上的 App 保護設定是否可正常運作</span><span class="sxs-lookup"><span data-stu-id="27f62-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="27f62-157">在您[設定 iOS 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="27f62-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="27f62-158">首先，確認原則已套用到您要驗證的 App。</span><span class="sxs-lookup"><span data-stu-id="27f62-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="27f62-159">在 Microsoft 365 商務版[系統管理中心](https://portal.office.com)中，移至 [**原則** \> **編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="27f62-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="27f62-160">對於您建立安裝程式，在設定] 或 [另一個原則，您建立，並確認它強制執行該 outlook，例如，選擇 [ **iOS 版的應用程式原則**。</span><span class="sxs-lookup"><span data-stu-id="27f62-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="27f62-162">驗證 [設定需要 PIN 才能存取 Office App] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="27f62-163">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，設定**需要 PIN 或指紋才能存取 Office app**若要**在上**。</span><span class="sxs-lookup"><span data-stu-id="27f62-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="27f62-165">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。</span><span class="sxs-lookup"><span data-stu-id="27f62-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="27f62-166">系統也會提示您輸入 PIN 或使用指紋。</span><span class="sxs-lookup"><span data-stu-id="27f62-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="27f62-168">驗證 [嘗試失敗幾次之後重設 PIN ] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="27f62-169">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定，**重設 PIN 的天數之後失敗的嘗試**設為部分number-這是預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="27f62-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="27f62-170">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入。</span><span class="sxs-lookup"><span data-stu-id="27f62-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="27f62-171">根據原則指定的次數重複輸入不正確的 PIN。</span><span class="sxs-lookup"><span data-stu-id="27f62-171">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="27f62-172">您會看到提示，指出**已達到 PIN 嘗試限制**重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="27f62-172">You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="27f62-174">按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27f62-174">Press **OK**.</span></span> <span data-ttu-id="27f62-175">系統會提示您以使用者的 Microsoft 365 商務版認證登入，並要求您設定新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="27f62-175">You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="27f62-176">驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="27f62-177">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯\*\*\*\*防範遺失或遭竊的裝置**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定該**強制使用者將所有工作檔案都儲存到 OneDrive商務**設為**上**。</span><span class="sxs-lookup"><span data-stu-id="27f62-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="27f62-179">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-180">開啟包含附件的電子郵件、 開啟附件，並選擇畫面底部的 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="27f62-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="27f62-182">您應該只會看到一個適用於商務用 OneDrive 的選項。</span><span class="sxs-lookup"><span data-stu-id="27f62-182">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="27f62-183">如果不沒有，請點選 [**新增帳戶**，並從 [**新增儲存體帳戶**] 畫面中選取 [**商務用 OneDrive** 。</span><span class="sxs-lookup"><span data-stu-id="27f62-183">If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="27f62-184">在系統提示時提供使用者的 Microsoft 365 商務版以登入。</span><span class="sxs-lookup"><span data-stu-id="27f62-184">Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="27f62-185">點選 [**儲存**]，然後選取 [**商務用 OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="27f62-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="27f62-186">驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="27f62-187">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯** **Office 文件存取控制**，依序展開 [**管理使用者如何存取行動裝置上的 Office 檔案**，並確定要求使用者重新登入之後 Office app 閒置該**針對**設至部分的分鐘數-這是預設的 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="27f62-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="27f62-188">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-p109">現在，您應該會看到 Outlook 的收件匣。請不要觸控 iOS 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。</span><span class="sxs-lookup"><span data-stu-id="27f62-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="27f62-192">重新存取 iOS 裝置上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="27f62-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="27f62-193">系統會提示您輸入 PIN，以便重新存取 Outlook。</span><span class="sxs-lookup"><span data-stu-id="27f62-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="27f62-194">驗證 [使用加密保護工作檔案] 設定</span><span class="sxs-lookup"><span data-stu-id="27f62-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="27f62-195">在 [**編輯原則**] 窗格中，選擇旁的 [**編輯\*\*\*\*防範遺失或遭竊的裝置**、 展開**裝置遺失或遭竊時保護工作檔案**，並確定**保護工作檔案加密**設定為 [ **]**，並且**強制使用者將儲存到商務用 OneDrive 的所有工作檔案**設為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="27f62-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="27f62-196">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務版認證登入及輸入 PIN (如果系統要求的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="27f62-197">開啟包含幾個影像檔案附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="27f62-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="27f62-198">點選附件，然後點選 [**儲存**] 選項。</span><span class="sxs-lookup"><span data-stu-id="27f62-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="27f62-199">從主畫面開啟**相片**」 app。</span><span class="sxs-lookup"><span data-stu-id="27f62-199">Open **Photos** app from the home screen.</span></span> <span data-ttu-id="27f62-200">您應該會看到一張經過加密的相片被儲存 (或數張相片，如果您儲存多個影像檔案附件的話)。</span><span class="sxs-lookup"><span data-stu-id="27f62-200">You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

