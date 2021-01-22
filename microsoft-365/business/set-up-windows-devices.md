---
title: 為 Microsoft 365 商務進版使用者設定 Windows 裝置
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 瞭解如何設定使用 Windows 10 Pro for Microsoft 365 商務進版使用者的 Windows 裝置，啟用集中式管理和安全性控制。
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928717"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="c8868-103">為 Microsoft 365 商務進版使用者設定 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="c8868-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="c8868-104">為 Microsoft 365 商務進版使用者設定 Windows 裝置的先決條件</span><span class="sxs-lookup"><span data-stu-id="c8868-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="c8868-105">在您為 Microsoft 365 商務進版使用者設定 Windows 裝置之前，請確認所有 Windows 裝置均是使用 Windows 10 專業版版本 1703 (Creators Update) 。</span><span class="sxs-lookup"><span data-stu-id="c8868-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="c8868-106">Windows 10 專業版是部署 Windows 10 商務版的先決條件，它是一組加強 Windows 10 專業版並啟用 Microsoft 365 商務進版集中管理和安全性控制功能的雲端服務和裝置管理功能。</span><span class="sxs-lookup"><span data-stu-id="c8868-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="c8868-107">如果您擁有執行 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 專業版之 Windows 裝置，您的 Microsoft 365 商務進版訂閱就有權升級 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="c8868-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="c8868-108">如需有關如何將 Windows 裝置升級到 Windows 10 專業版 Creators Update 的資訊，請按照本主題中的步驟進行：[將 Windows 裝置升級到 Windows 專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="c8868-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="c8868-109">請參閱 [驗證裝置已連接到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認您擁有升級，或確認升級成功。</span><span class="sxs-lookup"><span data-stu-id="c8868-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="c8868-110">觀看有關將 Windows 連接到 Microsoft 365 的短片。</span><span class="sxs-lookup"><span data-stu-id="c8868-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="c8868-111">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="c8868-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="c8868-112">將 Windows 10 裝置加入到貴組織的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8868-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="c8868-113">當貴組織的所有 Windows 裝置已升級到 Windows 10 專業版 Creators Update 或已執行 Windows 10 專業版 Creators Update 時，您可以將這些裝置加入到貴組織的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c8868-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="c8868-114">加入裝置後，裝置會自動升級至 Windows 10 商務版，這是 Microsoft 365 商務進版訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8868-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="c8868-115">適用於全新或新升級的 Windows 10 專業版裝置</span><span class="sxs-lookup"><span data-stu-id="c8868-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="c8868-116">針對執行 Windows 10 專業版 Creators Update 的全新裝置，或針對已升級到 Windows 10 專業版 Creators Update 但未完成 Windows 10 裝置設定的裝置，請按照這些步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c8868-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="c8868-117">完成 Windows 10 裝置設定，直到您到達要如何設定 **？** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c8868-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="c8868-119">在這裡， **選擇為組織設定** ，然後輸入您的 Microsoft 365 商務進版使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c8868-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="c8868-120">完成 Windows 10 裝置設定。</span><span class="sxs-lookup"><span data-stu-id="c8868-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="c8868-p103">完成後，使用者將連線到貴組織的 Azure AD。請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認。</span><span class="sxs-lookup"><span data-stu-id="c8868-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="c8868-123">適用於已設定且執行 Windows 10 專業版的裝置</span><span class="sxs-lookup"><span data-stu-id="c8868-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="c8868-124">**將使用者連線到 Azure AD：**</span><span class="sxs-lookup"><span data-stu-id="c8868-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="c8868-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span><span class="sxs-lookup"><span data-stu-id="c8868-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="c8868-127">在 **設定** 中，請 **前往帳戶**。</span><span class="sxs-lookup"><span data-stu-id="c8868-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="c8868-129">在 **[您的資訊>** 頁面上，按一下 **[存取公司或學校** \> **連結**。</span><span class="sxs-lookup"><span data-stu-id="c8868-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="c8868-131">在 [**設定公司或學校帳戶** 對話方塊上，替代動作下，選擇 **[加入此裝置至 Azure Active Directory。**</span><span class="sxs-lookup"><span data-stu-id="c8868-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="c8868-133">在 **Let's get you in page，** enter your work or school \> **account Next.**</span><span class="sxs-lookup"><span data-stu-id="c8868-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="c8868-134">在輸入 **密碼頁面上**，輸入您的密碼 \> **。。**</span><span class="sxs-lookup"><span data-stu-id="c8868-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="c8868-136">在確定 **這是您的組織頁面上**，確認資訊正確無誤，**然後加入宣告。**</span><span class="sxs-lookup"><span data-stu-id="c8868-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="c8868-137">一 **切都已設定好了！**</span><span class="sxs-lookup"><span data-stu-id="c8868-137">On the **You're all set!**</span></span> <span data-ttu-id="c8868-138">page，ssesse **Done**.</span><span class="sxs-lookup"><span data-stu-id="c8868-138">page, chosse **Done**.</span></span>
  
   ![在確定這是您的組織畫面上，選擇](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="c8868-140">如果您將檔案上傳至商務用 OneDrive，請將檔案同步回原處。</span><span class="sxs-lookup"><span data-stu-id="c8868-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="c8868-141">如果您使用協力廠商工具來轉移設定檔和檔案，也請將其同步處理至新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="c8868-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="c8868-142">驗證裝置已連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8868-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="c8868-143">若要驗證您的同步處理狀態，請在 Access 公司或學校頁面的設定中，選取已連結至 _ _ 區域來顯示按鈕資訊與中斷 \<organization name\> **連結**。 </span><span class="sxs-lookup"><span data-stu-id="c8868-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="c8868-144">選擇 **資訊** 以取得您的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="c8868-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="c8868-145">在同步 **處理狀態頁面上\*\*\*\*，選擇同步** 處理以在 PC 上取得最新的行動裝置管理政策。</span><span class="sxs-lookup"><span data-stu-id="c8868-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="c8868-146">若要開始使用 Microsoft 365 商務進版帳戶，請前往 **Windows** [開始> 按鈕，以滑鼠右鍵按一下您目前的帳戶圖片，然後 **切換帳戶**。</span><span class="sxs-lookup"><span data-stu-id="c8868-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="c8868-147">使用您的組織電子郵件和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="c8868-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="c8868-149">確認電腦已升級到 Windows 10 商務版</span><span class="sxs-lookup"><span data-stu-id="c8868-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="c8868-150">確認您的 Azure AD 加入 Windows 10 裝置已升級至 Windows 10 商務版，做為 Microsoft 365 商務進版訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8868-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="c8868-151">請前往 **設定** \> **系統** \> **關於**。</span><span class="sxs-lookup"><span data-stu-id="c8868-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="c8868-152">確認版本 **顯示** **Windows 10 商務版**。</span><span class="sxs-lookup"><span data-stu-id="c8868-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="c8868-154">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c8868-154">Next steps</span></span>

<span data-ttu-id="c8868-155">若要設定行動裝置，請參閱為[Microsoft 365](set-up-mobile-devices.md)商務進版使用者設定行動裝置。若要設定裝置保護或 App 保護政策，請參閱管理商務用[Microsoft 365。](manage.md)</span><span class="sxs-lookup"><span data-stu-id="c8868-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="c8868-156">更多有關設定和使用 Microsoft 365 商務進版</span><span class="sxs-lookup"><span data-stu-id="c8868-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="c8868-157">商務用 Microsoft 365 訓練影片</span><span class="sxs-lookup"><span data-stu-id="c8868-157">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
