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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何建立、 編輯或刪除應用程式管理原則，和保護 Android 或 iOS 裝置上的工作檔案。
ms.openlocfilehash: 68a338ffb4f9b6cab16c677f80d27481ccec4bd8
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287688"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="cca18-103">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="cca18-103">Set app protection settings for Android or iOS devices</span></span>

![指向橫幅https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="cca18-105">建立應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="cca18-105">Create an app management policy</span></span>

1. <span data-ttu-id="cca18-106">移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="cca18-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="cca18-107">在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。</span><span class="sxs-lookup"><span data-stu-id="cca18-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="cca18-108">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="cca18-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="cca18-109">[**原則類型**] 下選擇 [ **Android 版的應用程式管理**」 或 「 您想要建立的原則組合而定的**IOS 版的應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="cca18-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="cca18-110">展開 [**裝置遺失或遭竊時保護工作檔案**及**管理使用者如何存取行動裝置上的 Office 檔案**\>設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="cca18-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="cca18-111">**管理使用者如何存取行動裝置上的 Office 檔案**的預設為**關閉，** 但建議您將它**開啟**，並接受預設值。</span><span class="sxs-lookup"><span data-stu-id="cca18-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="cca18-112">如需詳細資訊，請參閱[可用的設定](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="cca18-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="cca18-113">您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。</span><span class="sxs-lookup"><span data-stu-id="cca18-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="cca18-115">下一步] 決定**人員會收到這些設定？**</span><span class="sxs-lookup"><span data-stu-id="cca18-115">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="cca18-116">如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="cca18-116">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="cca18-117">最後，選擇 [**完成**] 以儲存原則，並將它指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="cca18-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="cca18-118">編輯應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="cca18-118">Edit an app management policy</span></span>

1. <span data-ttu-id="cca18-119">在 [**原則**] 卡片中，選擇 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="cca18-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="cca18-120">在 [**編輯原則**] 窗格中，選擇您想要變更的原則</span><span class="sxs-lookup"><span data-stu-id="cca18-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="cca18-121">若要變更的原則中的值的每一項設定旁邊，選擇 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="cca18-121">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="cca18-122">當您變更值時，系統會將變更內容儲存到原則。</span><span class="sxs-lookup"><span data-stu-id="cca18-122">When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="cca18-123">當您完成時，關閉 [**編輯原則**] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="cca18-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="cca18-124">刪除應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="cca18-124">Delete an app management policy</span></span>

1. <span data-ttu-id="cca18-125">在 [**原則**] 頁面上選擇原則，然後**刪除**。</span><span class="sxs-lookup"><span data-stu-id="cca18-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="cca18-126">在 [**刪除原則**] 窗格中選擇 [**確認**刪除原則或您選擇的原則。</span><span class="sxs-lookup"><span data-stu-id="cca18-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="cca18-127">可用的設定</span><span class="sxs-lookup"><span data-stu-id="cca18-127">Available settings</span></span>

<span data-ttu-id="cca18-128">下表針對用來保護裝置上的工作檔案的設定，以及控管使用者透過行動裝置存取 Office 檔案方式的設定，提供相關的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cca18-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="cca18-129">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="cca18-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="cca18-130">保護工作檔案的設定</span><span class="sxs-lookup"><span data-stu-id="cca18-130">Settings that protect work files</span></span>

<span data-ttu-id="cca18-131">以下設定可用來在使用者的裝置遺失或遭竊時保護工作檔案：</span><span class="sxs-lookup"><span data-stu-id="cca18-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cca18-132">設定</span><span class="sxs-lookup"><span data-stu-id="cca18-132">Setting</span></span>  <br/> |<span data-ttu-id="cca18-133">描述</span><span class="sxs-lookup"><span data-stu-id="cca18-133">Description</span></span>  <br/> |
|<span data-ttu-id="cca18-134">在下列天數之後刪除非作用中裝置上的工作檔案</span><span class="sxs-lookup"><span data-stu-id="cca18-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="cca18-135">如果裝置在您於此處指定的天數內未有人使用，裝置上儲存的任何工作檔案會自動遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="cca18-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="cca18-136">強制使用者將所有工作檔案儲存到商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="cca18-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="cca18-137">如果**開啟**此設定時，只可以使用儲存的工作檔案的位置會商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="cca18-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="cca18-138">加密工作檔案</span><span class="sxs-lookup"><span data-stu-id="cca18-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="cca18-139">保持**在**此設定，以便透過加密功能保護工作檔案。</span><span class="sxs-lookup"><span data-stu-id="cca18-139">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="cca18-140">即使裝置遺失或遭竊，任何其他人都無法讀取您的公司資料。</span><span class="sxs-lookup"><span data-stu-id="cca18-140">Even if the device is lost or stolen, no one will be able to read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="cca18-141">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="cca18-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="cca18-142">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="cca18-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cca18-143">設定</span><span class="sxs-lookup"><span data-stu-id="cca18-143">Setting</span></span>  <br/> |<span data-ttu-id="cca18-144">描述</span><span class="sxs-lookup"><span data-stu-id="cca18-144">Description</span></span>  <br/> |
|<span data-ttu-id="cca18-145">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="cca18-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="cca18-146">如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cca18-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="cca18-147">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="cca18-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="cca18-148">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="cca18-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="cca18-149">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="cca18-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="cca18-150">此設定決定閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="cca18-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="cca18-151">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="cca18-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="cca18-152">聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。</span><span class="sxs-lookup"><span data-stu-id="cca18-152">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="cca18-153">這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="cca18-153">This means that the user can modify the operating system, which can make the device more subject to malware.</span></span> <span data-ttu-id="cca18-154">**此設定時**，會封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="cca18-154">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="cca18-155">允許使用者從 Office App 複製內容到個人 App</span><span class="sxs-lookup"><span data-stu-id="cca18-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="cca18-156">我們執行預設允許此行為，但如果設定為**上**，使用者無法複製資訊工作檔案中的個人檔案。</span><span class="sxs-lookup"><span data-stu-id="cca18-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="cca18-157">如果設定為**關閉**，使用者將無法將公司帳戶中的資訊複製到個人 app 或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="cca18-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

