---
title: 設定 Windows 10 裝置的應用程式保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何建立的應用程式管理原則，以及保護 Windows 10 裝置上的工作檔案。
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278155"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="279de-103">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="279de-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="279de-104">建立適用於 Windows 10 的應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="279de-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="279de-105">如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。</span><span class="sxs-lookup"><span data-stu-id="279de-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="279de-106">登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=837890)使用全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="279de-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="279de-107">選擇 [移至系統管理中心的 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="279de-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="279de-108">在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。</span><span class="sxs-lookup"><span data-stu-id="279de-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="279de-109">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="279de-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="279de-110">[**原則類型**] 下選擇 [**用於 Windows 10 應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="279de-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="279de-111">[\* \* 裝置類型 \* \*，選擇 [**個人**] 或 [**公司所擁有**。</span><span class="sxs-lookup"><span data-stu-id="279de-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="279de-112">**加密工作檔案**會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="279de-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="279de-113">**防止使用者複製到個人檔案的公司資料並強制他們將工作將檔案儲存到商務用 OneDrive**如果設定為**在**您不想要在其電腦上的工作檔案儲存的使用者。</span><span class="sxs-lookup"><span data-stu-id="279de-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="279de-114">依序展開 [**管理使用者如何存取裝置上的 Office 檔案**\>設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="279de-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="279de-115">**管理使用者如何存取行動裝置上的 Office 裝置**已**關閉**，根據預設，但建議您將它**開啟**，並接受預設值。</span><span class="sxs-lookup"><span data-stu-id="279de-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="279de-116">如需詳細資訊，請參閱[可用的設定](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="279de-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="279de-117">您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。</span><span class="sxs-lookup"><span data-stu-id="279de-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="279de-118">依序展開 [**修復 Windows 裝置上的資料**，並建議，您將它**開啟**。</span><span class="sxs-lookup"><span data-stu-id="279de-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="279de-p103">您必須先建立資料修復代理憑證，才能瀏覽至其位置。如需相關指示，請參閱[建立並驗證加密檔案系統 (EFS) 資料修復代理 (DRA) 憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="279de-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="279de-p104">根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。只有該使用者可以開啟並解密該檔案。不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。系統管理員可以使用資料修復代理程式 (DRA) 憑證來解密該檔案。</span><span class="sxs-lookup"><span data-stu-id="279de-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="279de-126">如果您想要新增其他網域或 SharePoint Online 的位置，以確保所有列出的應用程式中的檔案會受到保護，請展開 [**保護其他網路及雲端位置**]。</span><span class="sxs-lookup"><span data-stu-id="279de-126">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected.</span></span> <span data-ttu-id="279de-127">如果您需要為任何欄位輸入多個項目，請在每個項目之間插入分號 (;)。</span><span class="sxs-lookup"><span data-stu-id="279de-127">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="279de-129">下一步] 決定**人員會收到這些設定？**</span><span class="sxs-lookup"><span data-stu-id="279de-129">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="279de-130">如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="279de-130">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="279de-131">最後，選擇 [**新增]** 以儲存原則，並將它指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="279de-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="279de-132">可用的設定</span><span class="sxs-lookup"><span data-stu-id="279de-132">Available settings</span></span>

<span data-ttu-id="279de-133">下列設定可用來管理使用者如何存取 Office 工作檔案。</span><span class="sxs-lookup"><span data-stu-id="279de-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="279de-134">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="279de-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="279de-135">**設定**</span><span class="sxs-lookup"><span data-stu-id="279de-135">**Setting**</span></span>|<span data-ttu-id="279de-136">**描述**</span><span class="sxs-lookup"><span data-stu-id="279de-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="279de-137">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="279de-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="279de-138">如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="279de-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="279de-139">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="279de-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="279de-140">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="279de-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="279de-141">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="279de-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="279de-142">此設定決定閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="279de-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

