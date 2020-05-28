---
title: 設定 Android 或 iOS 裝置的 App 保護設定
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 瞭解如何在 Android 或 iOS 裝置上建立、編輯或刪除應用程式管理原則，以及保護工作檔。
ms.openlocfilehash: 01c50e6660d8d8640a2bff2794ee0ea8a69188c8
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401047"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="a7cdf-103">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-103">Set app protection settings for Android or iOS devices</span></span>

![指向的橫幅 https://aka.ms/aboutM365preview 。](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="a7cdf-105">建立應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="a7cdf-105">Create an app management policy</span></span>

1. <span data-ttu-id="a7cdf-106">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="a7cdf-107">在左側導覽中，選擇 [**裝置** \> **原則**] [ \> **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="a7cdf-108">在 [**新增原則**] 窗格中，輸入這個原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="a7cdf-109">在 [**原則類型**] 底下，選擇 [適用于**Android 的應用程式管理**] 或 [**應用程式管理] iOS**，視您想要建立的原則組而定。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="a7cdf-110">擴充**當裝置遺失或遭竊時保護工作檔**，並**管理使用者如何在行動裝置上存取 Office**檔案。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="a7cdf-111">設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-111">Configure the settings how you would like.</span></span> <span data-ttu-id="a7cdf-112">**管理使用者如何在行動裝置上存取 Office**檔案的方式預設為**關閉**，但建議您**將其開啟**並接受預設值。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="a7cdf-113">如需詳細資訊，請參閱[可用設定](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="a7cdf-114">您可以隨時使用 [**重設預設值設定**] 連結，以回到預設設定。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="a7cdf-116">下一步決定**誰將取得這些設定？**</span><span class="sxs-lookup"><span data-stu-id="a7cdf-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="a7cdf-117">如果您不想要使用預設的 [**所有使用者**] 安全性群組，請選擇 [**變更**]，然後選擇 [會選取下列設定的安全性群組] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="a7cdf-118">最後，選擇 [**完成**] 以儲存原則，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="a7cdf-119">編輯應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="a7cdf-119">Edit an app management policy</span></span>

1. <span data-ttu-id="a7cdf-120">在 [**原則**] 卡片上，選擇 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="a7cdf-121">在 [**編輯原則**] 窗格中，選擇您要變更的原則</span><span class="sxs-lookup"><span data-stu-id="a7cdf-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="a7cdf-122">選擇每個設定旁的 [**編輯**]，以變更原則中的值。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="a7cdf-123">當您變更值時，會自動儲存于原則中。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="a7cdf-124">完成後，請關閉 [**編輯原則**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="a7cdf-125">刪除應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="a7cdf-125">Delete an app management policy</span></span>

1. <span data-ttu-id="a7cdf-126">在 [**原則**] 頁面上，選擇原則，然後**刪除**。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="a7cdf-127">在 [**刪除原則**] 窗格中，選擇 [**確認**]，以刪除您選擇的原則或原則。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="a7cdf-128">可用的設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-128">Available settings</span></span>

<span data-ttu-id="a7cdf-129">下表提供可在裝置上保護工作檔案的詳細資訊，以及控制使用者如何從行動裝置存取 Office 檔案的設定。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="a7cdf-130">如需詳細資訊，請參閱 how [To Intune for a protection features In Microsoft 365 Business Premium map To Intune settings](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="a7cdf-131">保護工作檔案的設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-131">Settings that protect work files</span></span>

<span data-ttu-id="a7cdf-132">以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：</span><span class="sxs-lookup"><span data-stu-id="a7cdf-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7cdf-133">設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-133">Setting</span></span>  <br/> |<span data-ttu-id="a7cdf-134">說明</span><span class="sxs-lookup"><span data-stu-id="a7cdf-134">Description</span></span>  <br/> |
|<span data-ttu-id="a7cdf-135">在下列天數之後刪除非作用中裝置上的工作檔案</span><span class="sxs-lookup"><span data-stu-id="a7cdf-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="a7cdf-136">如果裝置沒有用於您在此處指定的天數，將會自動刪除該裝置上儲存的任何工作檔。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="a7cdf-137">強制使用者將所有工作檔案儲存到商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="a7cdf-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="a7cdf-138">若此設定為 [**開啟**]，則唯一可用的工作檔案儲存位置為商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="a7cdf-139">加密工作檔案</span><span class="sxs-lookup"><span data-stu-id="a7cdf-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="a7cdf-140">將此設定保持**開啟**，讓工作檔案受到加密保護。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="a7cdf-141">即使裝置遺失或被盜，任何人都無法讀取您的公司資料。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="a7cdf-142">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="a7cdf-143">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="a7cdf-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7cdf-144">設定</span><span class="sxs-lookup"><span data-stu-id="a7cdf-144">Setting</span></span>  <br/> |<span data-ttu-id="a7cdf-145">說明</span><span class="sxs-lookup"><span data-stu-id="a7cdf-145">Description</span></span>  <br/> |
|<span data-ttu-id="a7cdf-146">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="a7cdf-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="a7cdf-147">如果此設定是**在**使用者在其行動裝置上使用 Office 應用程式之前，除了使用者的使用者名稱和密碼以外，還必須提供另一種形式的驗證。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="a7cdf-148">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="a7cdf-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="a7cdf-149">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="a7cdf-150">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="a7cdf-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="a7cdf-151">此設定會決定使用者在有多久之後才會收到重新登入的時間。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="a7cdf-152">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="a7cdf-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="a7cdf-153">聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-153">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="a7cdf-154">這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-154">This means that the user can modify the operating system, which can make the device more subject to malware.</span></span> <span data-ttu-id="a7cdf-155">當此設定為 [**開啟**] 時，即會封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-155">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="a7cdf-156">不允許使用者從 Office 應用程式複製內容到個人應用程式</span><span class="sxs-lookup"><span data-stu-id="a7cdf-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="a7cdf-157">我們預設會允許這麼做，但如果設定為**開啟**，使用者可以將工作檔案中的資訊複製到個人檔案。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="a7cdf-158">如果設定為 [**關閉**]，使用者將無法將工作帳戶中的資訊複製到個人應用程式或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="a7cdf-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
