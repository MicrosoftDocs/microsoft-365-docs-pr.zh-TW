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
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="d6944-103">驗證 Android 或 iOS 裝置上的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="d6944-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="d6944-104">依照下列各節中的指示驗證 Android 或 iOS 裝置上的應用程式保護設定。</span><span class="sxs-lookup"><span data-stu-id="d6944-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="d6944-105">Android</span><span class="sxs-lookup"><span data-stu-id="d6944-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="d6944-106">檢查使用者裝置上的應用程式保護設定是否正常運作</span><span class="sxs-lookup"><span data-stu-id="d6944-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="d6944-107">在您[設定 Android 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="d6944-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="d6944-108">首先，請確定原則套用至您要驗證的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6944-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="d6944-109">在 Microsoft 365 商務進階版系統 [管理中心](https://portal.office.com)，移至 [**原則**] [ \> **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="d6944-110">針對安裝時所建立的設定，選擇 [ **Android 應用程式原則**]，或選擇您建立的其他原則，然後驗證是否強制執行 Outlook，例如。</span><span class="sxs-lookup"><span data-stu-id="d6944-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="d6944-112">檢查 [需要 PIN 或指紋才能存取 Office App] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="d6944-113">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **需要 PIN 或指紋才能存取 Office 應用程式** 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![請確定 [需要 PIN 或指紋才能存取 Office 應用程式] 設定為 [開啟]。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="d6944-115">在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入。</span><span class="sxs-lookup"><span data-stu-id="d6944-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d6944-116">系統也會提示您輸入 PIN 或使用指紋。</span><span class="sxs-lookup"><span data-stu-id="d6944-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="d6944-118">驗證 [嘗試失敗幾次之後重設 PIN ] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="d6944-119">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定在 [失敗嘗試次數] 設定為 [一定] 數位 **後重設 PIN 碼失敗**。</span><span class="sxs-lookup"><span data-stu-id="d6944-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="d6944-120">預設為5。</span><span class="sxs-lookup"><span data-stu-id="d6944-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="d6944-121">在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入。</span><span class="sxs-lookup"><span data-stu-id="d6944-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d6944-122">根據原則指定的次數重複輸入不正確的 PIN。</span><span class="sxs-lookup"><span data-stu-id="d6944-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="d6944-123">您會看到一則提示，指出已 **接通 Pin 嘗試限制** 以重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="d6944-125">按下 [ **重設 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-125">Press **Reset PIN**.</span></span> <span data-ttu-id="d6944-126">系統會提示您使用使用者的 Microsoft 365 商務進階版認證進行登入，然後必須設定新的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="d6944-127">驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="d6944-128">在 [**編輯原則**] 窗格中，選擇 [防止 **遺失或被盜裝置防護**] 旁的 [**編輯**]，然後在 **裝置遺失或遭竊時展開 [保護工作檔**]，並確定 [**強制使用者將所有工作檔案儲存至商務用 OneDrive** ] 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="d6944-130">在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-131">開啟包含附件的電子郵件，然後點選附件資訊旁邊的向下箭號圖示。</span><span class="sxs-lookup"><span data-stu-id="d6944-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="d6944-133">您將會看到畫面底部 **無法儲存至裝置** 。</span><span class="sxs-lookup"><span data-stu-id="d6944-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="d6944-135">目前 Android 裝置無法儲存到商務用 OneDrive，因此您只會看到本機儲存已遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="d6944-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="d6944-136">驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="d6944-137">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **Office 已閒置的應用程式中，需要使用者重新登入**，且已設定為數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d6944-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="d6944-138">預設為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="d6944-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="d6944-139">在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-p105">現在，您應該會看到 Outlook 的收件匣。請不要觸控 Android 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。</span><span class="sxs-lookup"><span data-stu-id="d6944-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="d6944-143">在 Android 裝置上重新存取 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d6944-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="d6944-144">您必須先輸入 PIN 碼，才能再存取 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d6944-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="d6944-145">驗證 [使用加密保護工作檔案] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="d6944-146">在 [**編輯原則**] 窗格中，選擇 [**針對遺失或被盜的裝置加以防護**] 旁邊的 [**編輯**]，然後在 **裝置遺失或遭竊時** 展開 [保護工作檔]，並確定 [**保護具有加密的工作** 檔] 已設為 [**開啟**]，然後 **強制使用者將所有工作檔案儲存到商務用 OneDrive** 已設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="d6944-147">在使用者的 Android 裝置中，開啟 Outlook，並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-148">開啟包含一些影像檔附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d6944-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="d6944-149">點選附件資訊旁邊的向下箭號圖示以儲存附件。</span><span class="sxs-lookup"><span data-stu-id="d6944-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="d6944-151">系統可能會提示您允許 Outlook 存取裝置上的相片、媒體和檔案。</span><span class="sxs-lookup"><span data-stu-id="d6944-151">You may be prompted to allow Outlook to access photos, media, and files on your device.</span></span> <span data-ttu-id="d6944-152">按 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-152">Tap **Allow**.</span></span>
    
5. <span data-ttu-id="d6944-153">在螢幕底部，選擇 [ **儲存至裝置** ]，然後開啟 **圖庫** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6944-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="d6944-p107">您應該會在清單中看到一張經過加密的相片 (或數張相片，如果您儲存了多個影像檔案附件的話)。這張相片可能會在 [圖片] 清單中顯示為灰色的方形，中央有以白色圓圈包住的白色驚嘆號。</span><span class="sxs-lookup"><span data-stu-id="d6944-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="d6944-157">iOS</span><span class="sxs-lookup"><span data-stu-id="d6944-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="d6944-158">檢查使用者裝置上的 App 保護設定是否可正常運作</span><span class="sxs-lookup"><span data-stu-id="d6944-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="d6944-159">在您[設定 iOS 裝置的 App 設定](app-protection-settings-for-android-and-ios.md)以保護 App 後，可以按照這些步驟驗證您選擇的設定是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="d6944-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="d6944-160">首先，請確定原則套用至您要驗證的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6944-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="d6944-161">在 Microsoft 365 商務進階版系統 [管理中心](https://portal.office.com)，移至 [**原則**] [ \> **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="d6944-162">針對安裝時所建立的設定，選擇 **iOS 的應用程式原則**，或選擇您建立的其他原則，然後在 Outlook 中驗證是否強制執行。</span><span class="sxs-lookup"><span data-stu-id="d6944-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="d6944-164">驗證 [設定需要 PIN 才能存取 Office App] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="d6944-165">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **需要 PIN 或指紋才能存取 Office 應用程式** 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![請確定 [需要 PIN 或指紋才能存取 Office 應用程式] 設定為 [開啟]。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="d6944-167">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入。</span><span class="sxs-lookup"><span data-stu-id="d6944-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d6944-168">系統也會提示您輸入 PIN 或使用指紋。</span><span class="sxs-lookup"><span data-stu-id="d6944-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="d6944-170">驗證 [嘗試失敗幾次之後重設 PIN ] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="d6944-171">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定在 [失敗嘗試次數] 設定為 [一定] 數位 **後重設 PIN 碼失敗**。</span><span class="sxs-lookup"><span data-stu-id="d6944-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="d6944-172">預設為5。</span><span class="sxs-lookup"><span data-stu-id="d6944-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="d6944-173">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入。</span><span class="sxs-lookup"><span data-stu-id="d6944-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d6944-174">根據原則指定的次數重複輸入不正確的 PIN。</span><span class="sxs-lookup"><span data-stu-id="d6944-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="d6944-175">您會看到一則提示，指出已 **接通 Pin 嘗試限制** 以重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="d6944-177">按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d6944-177">Press **OK**.</span></span> <span data-ttu-id="d6944-178">系統會提示您使用使用者的 Microsoft 365 商務進階版認證進行登入，然後必須設定新的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="d6944-179">驗證 [強制使用者將所有工作檔案儲存到商務用 OneDrive] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="d6944-180">在 [**編輯原則**] 窗格中，選擇 [防止 **遺失或被盜裝置防護**] 旁的 [**編輯**]，然後在 **裝置遺失或遭竊時展開 [保護工作檔**]，並確定 [**強制使用者將所有工作檔案儲存至商務用 OneDrive** ] 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="d6944-182">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-183">開啟包含附件的電子郵件，開啟附件，然後選擇畫面底部的 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="d6944-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="d6944-185">您應該只會看到一個適用於商務用 OneDrive 的選項。</span><span class="sxs-lookup"><span data-stu-id="d6944-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="d6944-186">如果不是，請點擊 [**新增帳戶**]，然後從 [**新增儲存體帳戶**] 畫面中選取 [**商務用 OneDrive** ]。</span><span class="sxs-lookup"><span data-stu-id="d6944-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="d6944-187">當系統提示時，提供使用者的 Microsoft 365 商務進階版登入。</span><span class="sxs-lookup"><span data-stu-id="d6944-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="d6944-188">按一下 [**儲存**]，然後選取 [**商務用 OneDrive**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="d6944-189">驗證 [Office App 閒置這段時間之後要求使用者重新登入] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="d6944-190">在 [**編輯原則**] 窗格中，選擇 [ **Office 檔存取控制**] 旁的 [**編輯**]，然後展開 [**管理使用者存取行動裝置上 Office** 檔案的方式]，並確定 **Office 已閒置的應用程式中，需要使用者重新登入**，且已設定為數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d6944-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="d6944-191">預設為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="d6944-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="d6944-192">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-p113">現在，您應該會看到 Outlook 的收件匣。請不要觸控 iOS 裝置至少 30 分鐘 (或是其他比您在原則中指定的時間還要久的時間長度)。裝置畫面會變暗。</span><span class="sxs-lookup"><span data-stu-id="d6944-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="d6944-196">再次存取 iOS 裝置上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d6944-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="d6944-197">您必須先輸入 PIN 碼，才能再存取 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d6944-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="d6944-198">驗證 [使用加密保護工作檔案] 設定</span><span class="sxs-lookup"><span data-stu-id="d6944-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="d6944-199">在 [**編輯原則**] 窗格中，選擇 [**針對遺失或被盜的裝置加以防護**] 旁邊的 [**編輯**]，然後在 **裝置遺失或遭竊時** 展開 [保護工作檔]，並確定 [**保護具有加密的工作** 檔] 已設為 [**開啟**]，然後 **強制使用者將所有工作檔案儲存到商務用 OneDrive** 已設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d6944-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="d6944-200">在使用者的 iOS 裝置中，開啟 Outlook 並以使用者的 Microsoft 365 商務進階版認證登入，並視需要輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="d6944-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d6944-201">開啟包含一些影像檔附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d6944-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="d6944-202">點擊附件，然後點擊它底下的 [ **儲存** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="d6944-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="d6944-203">從主畫面開啟 **相片** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6944-203">Open **Photos** app from the home screen.</span></span> <span data-ttu-id="d6944-204">您應該會看到一張經過加密的相片被儲存 (或數張相片，如果您儲存多個影像檔案附件的話)。</span><span class="sxs-lookup"><span data-stu-id="d6944-204">You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

