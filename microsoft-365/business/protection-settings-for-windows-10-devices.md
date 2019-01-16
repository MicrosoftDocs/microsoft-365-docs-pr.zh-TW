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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何建立的應用程式管理原則及保護工時 Windows 10 裝置上的檔案。
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866321"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="2692f-103">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="2692f-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="2692f-104">建立適用於 Windows 10 的應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="2692f-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="2692f-105">如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。</span><span class="sxs-lookup"><span data-stu-id="2692f-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="2692f-p101">以全域管理員認證登入[Microsoft 365 Business](https://portal.office.com) 。選擇 [移至系統管理中心的 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2692f-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="2692f-108">在系統入口網站的**裝置原則**卡片、 上選擇 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="2692f-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="2692f-110">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="2692f-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2692f-111">在**原則類型**] 下選擇 [ **for Windows 10 應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="2692f-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="2692f-112">[\* \* 裝置類型 \* \*，選擇 [**個人**] 或 [**公司擁有**。</span><span class="sxs-lookup"><span data-stu-id="2692f-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="2692f-113">**加密工作檔案**會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="2692f-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="2692f-114">**防止使用者將複製的個人檔案的公司資料與強制其儲存至 OneDrive for Business 的工時檔案**如果設定為**在**您不想將儲存在其電腦上的工作檔案的使用者。</span><span class="sxs-lookup"><span data-stu-id="2692f-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="2692f-p102">依序展開 [**管理使用者如何存取裝置上的 Office 檔案**\>您想方式進行設定。**管理使用者如何存取行動裝置上的 Office 裝置**預設為**關閉，** 但建議您**加以開啟**並接受預設值。如需詳細資訊，請參閱[可用的設定](protection-settings-for-windows-10-devices.md#bkmk_settings)。</span><span class="sxs-lookup"><span data-stu-id="2692f-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="2692f-118">您一律可以回復成預設值使用**預設設定重設**] 連結。</span><span class="sxs-lookup"><span data-stu-id="2692f-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="2692f-119">依序展開 [ **Windows 裝置上的資料復原**和它建議**您開啟它**。</span><span class="sxs-lookup"><span data-stu-id="2692f-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="2692f-p103">您必須先建立資料修復代理憑證，才能瀏覽至其位置。如需相關指示，請參閱[建立並驗證加密檔案系統 (EFS) 資料修復代理 (DRA) 憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="2692f-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="2692f-p104">根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。只有該使用者可以開啟並解密該檔案。不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。系統管理員可以使用資料修復代理程式 (DRA) 憑證來解密該檔案。</span><span class="sxs-lookup"><span data-stu-id="2692f-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="2692f-p105">如果您想要新增其他網域或以確定在所有列出的應用程式中的檔案將會受到保護的 SharePoint Online 位置，展開**Protect 其他網路和雲端位置**。如果您需要為其中一個欄位中輸入一個以上的項目，請使用分號 （;） 之間的項目。</span><span class="sxs-lookup"><span data-stu-id="2692f-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="2692f-p106">接下來決定**誰將會得到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**，並選擇 [將會得到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="2692f-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="2692f-132">最後，選擇 [**新增]** 以儲存原則，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="2692f-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2692f-133">可用的設定</span><span class="sxs-lookup"><span data-stu-id="2692f-133">Available settings</span></span>

<span data-ttu-id="2692f-134">下列設定可用來管理使用者如何存取 Office 工作檔案。</span><span class="sxs-lookup"><span data-stu-id="2692f-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="2692f-135">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2692f-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="2692f-136">**設定**</span><span class="sxs-lookup"><span data-stu-id="2692f-136">**Setting**</span></span>|<span data-ttu-id="2692f-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="2692f-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2692f-138">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="2692f-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2692f-139">如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2692f-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2692f-140">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="2692f-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2692f-141">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="2692f-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2692f-142">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="2692f-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2692f-143">此設定決定閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="2692f-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

