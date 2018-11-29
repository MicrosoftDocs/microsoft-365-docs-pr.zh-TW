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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866689"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="5608b-103">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="5608b-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="5608b-104">建立應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="5608b-104">Create an app management policy</span></span>

1. <span data-ttu-id="5608b-105">使用全域系統管理員認證登入 [Microsoft 365 商務版](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="5608b-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="5608b-106">在管理中心的 [**裝置原則**在卡片上，選擇 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="5608b-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="5608b-108">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="5608b-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="5608b-109">**原則類型**] 下選擇 [ **For Android 應用程式管理**或想要建立的一組原則根據**IOS 的應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="5608b-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="5608b-p101">依序展開 [**保護工作檔案遺失或竊裝置的時機**和**管理使用者如何存取行動裝置上的 Office 檔案**\>您想方式進行設定。**管理使用者如何存取行動裝置上的 Office 檔案**的預設為**關閉，** 但建議您**加以開啟**並接受預設值。如需詳細資訊，請參閱[可用的設定](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings)。</span><span class="sxs-lookup"><span data-stu-id="5608b-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="5608b-113">您一律可以回復成預設值使用**預設設定重設**] 連結。</span><span class="sxs-lookup"><span data-stu-id="5608b-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="5608b-p102">接下來決定**誰將會得到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**，並選擇 [將會得到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="5608b-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="5608b-117">最後，選擇 [**完成**儲存原則]，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="5608b-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="5608b-118">編輯應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="5608b-118">Edit an app management policy</span></span>

1. <span data-ttu-id="5608b-119">**原則**在卡片上，選擇 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="5608b-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="5608b-120">在 [**編輯原則**] 窗格中，選擇您想要變更的原則</span><span class="sxs-lookup"><span data-stu-id="5608b-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="5608b-p103">選擇 [每個原則中的值變更設定] 旁的 [**編輯**]。值變更後，會自動儲存成原則</span><span class="sxs-lookup"><span data-stu-id="5608b-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="5608b-123">完成時，關閉 [**編輯原則**] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="5608b-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="5608b-124">刪除應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="5608b-124">Delete an app management policy</span></span>

1. <span data-ttu-id="5608b-125">**原則**在卡片上，選擇 [**刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="5608b-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="5608b-126">在 [**刪除原則**] 窗格中，選擇您想要刪除之的原則\>**選取**，然後**確認**来刪除的原則或您所選擇的原則。</span><span class="sxs-lookup"><span data-stu-id="5608b-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="5608b-127">可用的設定</span><span class="sxs-lookup"><span data-stu-id="5608b-127">Available settings</span></span>

<span data-ttu-id="5608b-128">下表針對用來保護裝置上的工作檔案的設定，以及控管使用者透過行動裝置存取 Office 檔案方式的設定，提供相關的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5608b-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="5608b-129">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5608b-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="5608b-130">保護工作檔案的設定</span><span class="sxs-lookup"><span data-stu-id="5608b-130">Settings that protect work files</span></span>

<span data-ttu-id="5608b-131">以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：</span><span class="sxs-lookup"><span data-stu-id="5608b-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5608b-132">設定</span><span class="sxs-lookup"><span data-stu-id="5608b-132">Setting</span></span>  <br/> |<span data-ttu-id="5608b-133">描述</span><span class="sxs-lookup"><span data-stu-id="5608b-133">Description</span></span>  <br/> |
|<span data-ttu-id="5608b-134">在下列天數之後刪除非作用中裝置上的工作檔案</span><span class="sxs-lookup"><span data-stu-id="5608b-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="5608b-135">如果裝置在您於此處指定的天數內未有人使用，裝置上儲存的任何工作檔案會自動遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="5608b-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="5608b-136">強制使用者將所有工作檔案儲存到商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="5608b-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="5608b-137">**在**此設定時，才可使用儲存工作檔案的位置會 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="5608b-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="5608b-138">加密工作檔案</span><span class="sxs-lookup"><span data-stu-id="5608b-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="5608b-p104">使加密由保護工時檔案保留**在**此設定。即使遺失或竊裝置，沒有人將能夠讀取您公司的資料。</span><span class="sxs-lookup"><span data-stu-id="5608b-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="5608b-141">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="5608b-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="5608b-142">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="5608b-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5608b-143">設定</span><span class="sxs-lookup"><span data-stu-id="5608b-143">Setting</span></span>  <br/> |<span data-ttu-id="5608b-144">描述</span><span class="sxs-lookup"><span data-stu-id="5608b-144">Description</span></span>  <br/> |
|<span data-ttu-id="5608b-145">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="5608b-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="5608b-146">如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5608b-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="5608b-147">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="5608b-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="5608b-148">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="5608b-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="5608b-149">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="5608b-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="5608b-150">此設定決定閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="5608b-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="5608b-151">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="5608b-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="5608b-p105">聰明使用者可能會有 jailbroken 或根目錄的裝置。這表示使用者可以修改作業系統，可讓裝置多受限於惡意程式碼。**在**此設定時封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="5608b-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="5608b-155">允許使用者從 Office App 複製內容到個人 App</span><span class="sxs-lookup"><span data-stu-id="5608b-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="5608b-p106">我們不要允許這根據預設，但如果設定為**在**使用者無法複製資訊工時檔案中個人的檔案。如果設定為**關閉**時，使用者將無法將資訊從工時帳戶複製到個人的應用程式或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="5608b-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

