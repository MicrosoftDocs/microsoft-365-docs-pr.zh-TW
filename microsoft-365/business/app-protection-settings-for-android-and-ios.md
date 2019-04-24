---
title: 設定 Android 或 iOS 裝置的 App 保護設定
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
ms.openlocfilehash: e81ff8a4bd71dbbbf7ccc31249d450e03f4bd241
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277437"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="ad9c4-103">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="ad9c4-104">建立應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="ad9c4-104">Create an app management policy</span></span>

1. <span data-ttu-id="ad9c4-105">使用全域系統管理員認證登入[Microsoft 365 商務版系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=837890)。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-105">Sign in to [Microsoft 365 Business admin center ](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="ad9c4-106">在系統管理中心中，選擇 [**裝置** \> **原則** \> **新增原則**。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-106">In the admin center, choose **Devices** \> **Policies** \> **Add policy**.</span></span>
  
3. <span data-ttu-id="ad9c4-107">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-107">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="ad9c4-108">[**原則類型**] 下選擇 [ **Android 版的應用程式管理**」 或 「 您想要建立的原則組合而定的**IOS 版的應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-108">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="ad9c4-109">展開 [**裝置遺失或遭竊時保護工作檔案**及**管理使用者如何存取行動裝置上的 Office 檔案**\>設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-109">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="ad9c4-110">**管理使用者如何存取行動裝置上的 Office 檔案**的預設為**關閉，** 但建議您將它**開啟**，並接受預設值。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-110">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="ad9c4-111">如需詳細資訊，請參閱[可用的設定](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-111">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="ad9c4-112">您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="ad9c4-114">下一步] 決定**人員會收到這些設定？**</span><span class="sxs-lookup"><span data-stu-id="ad9c4-114">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="ad9c4-115">如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-115">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="ad9c4-116">最後，選擇 [**完成**] 以儲存原則，並將它指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="ad9c4-117">編輯應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="ad9c4-117">Edit an app management policy</span></span>

1. <span data-ttu-id="ad9c4-118">在 [**原則**] 卡片中，選擇 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-118">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="ad9c4-119">在 [**編輯原則**] 窗格中，選擇您想要變更的原則</span><span class="sxs-lookup"><span data-stu-id="ad9c4-119">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="ad9c4-120">若要變更的原則中的值的每一項設定旁邊，選擇 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-120">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="ad9c4-121">當您變更值時，系統會將變更內容儲存到原則。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-121">When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="ad9c4-122">當您完成時，關閉 [**編輯原則**] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-122">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="ad9c4-123">刪除應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="ad9c4-123">Delete an app management policy</span></span>

1. <span data-ttu-id="ad9c4-124">在 [**原則**] 卡片中，選擇 [**刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-124">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="ad9c4-125">在 [**刪除原則**] 窗格中，選擇您想要刪除的原則\>**選取**，然後**確認**来刪除原則或您選擇的原則。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-125">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="ad9c4-126">可用的設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-126">Available settings</span></span>

<span data-ttu-id="ad9c4-127">下表針對用來保護裝置上的工作檔案的設定，以及控管使用者透過行動裝置存取 Office 檔案方式的設定，提供相關的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-127">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="ad9c4-128">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-128">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="ad9c4-129">保護工作檔案的設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-129">Settings that protect work files</span></span>

<span data-ttu-id="ad9c4-130">以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：</span><span class="sxs-lookup"><span data-stu-id="ad9c4-130">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ad9c4-131">設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-131">Setting</span></span>  <br/> |<span data-ttu-id="ad9c4-132">描述</span><span class="sxs-lookup"><span data-stu-id="ad9c4-132">Description</span></span>  <br/> |
|<span data-ttu-id="ad9c4-133">在下列天數之後刪除非作用中裝置上的工作檔案</span><span class="sxs-lookup"><span data-stu-id="ad9c4-133">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="ad9c4-134">如果裝置在您於此處指定的天數內未有人使用，裝置上儲存的任何工作檔案會自動遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-134">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-135">強制使用者將所有工作檔案儲存到商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="ad9c4-135">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="ad9c4-136">如果**開啟**此設定時，只可以使用儲存的工作檔案的位置會商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-136">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-137">加密工作檔案</span><span class="sxs-lookup"><span data-stu-id="ad9c4-137">Encrypt work files</span></span>  <br/> |<span data-ttu-id="ad9c4-138">保持**在**此設定，以便透過加密功能保護工作檔案。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-138">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="ad9c4-139">即使裝置遺失或遭竊，任何其他人都無法讀取您的公司資料。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-139">Even if the device is lost or stolen, no one will be able to read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="ad9c4-140">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-140">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="ad9c4-141">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="ad9c4-141">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ad9c4-142">設定</span><span class="sxs-lookup"><span data-stu-id="ad9c4-142">Setting</span></span>  <br/> |<span data-ttu-id="ad9c4-143">描述</span><span class="sxs-lookup"><span data-stu-id="ad9c4-143">Description</span></span>  <br/> |
|<span data-ttu-id="ad9c4-144">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="ad9c4-144">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="ad9c4-145">如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-145">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-146">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="ad9c4-146">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="ad9c4-147">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-147">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-148">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="ad9c4-148">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="ad9c4-149">此設定決定閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-149">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-150">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="ad9c4-150">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="ad9c4-151">聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-151">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="ad9c4-152">這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-152">This means that the user can modify the operating system, which can make the device more subject to malware.</span></span> <span data-ttu-id="ad9c4-153">**此設定時**，會封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-153">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="ad9c4-154">允許使用者從 Office App 複製內容到個人 App</span><span class="sxs-lookup"><span data-stu-id="ad9c4-154">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="ad9c4-155">我們執行預設允許此行為，但如果設定為**上**，使用者無法複製資訊工作檔案中的個人檔案。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-155">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="ad9c4-156">如果設定為**關閉**，使用者將無法將公司帳戶中的資訊複製到個人 app 或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad9c4-156">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

