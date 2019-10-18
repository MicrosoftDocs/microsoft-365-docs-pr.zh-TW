---
title: 為 Microsoft 365 商務版使用者設定 Windows 裝置
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: '了解如何為 Microsoft 365 商務版使用者執行 Windows 10 專業版的 Windows 裝置上設定。 '
ms.openlocfilehash: 7b6fa2ce3243500c3ddcff7883fa9d8da27dcf86
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575561"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="257fd-103">為 Microsoft 365 商務版使用者設定 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="257fd-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="257fd-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="257fd-104">Prerequisites</span></span>

<span data-ttu-id="257fd-p101">請先確認所有 Windows 裝置皆執行 Windows 10 專業版的版本 1703 (Creators Update)，才能為 Microsoft 365 商務版使用者設定 Windows 裝置。Windows 10 專業版是部署 Windows 10 商務版的先決條件，它是一套加強 Windows 10 專業版的雲端服務和裝置管理功能，而且可支援 Microsoft 365 商務版的集中管理和安全性控制。</span><span class="sxs-lookup"><span data-stu-id="257fd-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="257fd-107">如果您有執行 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 專業版的 Windows 裝置，您的 Microsoft 365 商務版訂閱即符合 Windows 10 升級的資格。</span><span class="sxs-lookup"><span data-stu-id="257fd-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="257fd-108">如需有關如何將 Windows 裝置升級到 Windows 10 專業版 Creators Update 的資訊，請按照本主題中的步驟進行：[將 Windows 裝置升級到 Windows 專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="257fd-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="257fd-109">請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad)若要確認您已升級或確認升級正常運作。</span><span class="sxs-lookup"><span data-stu-id="257fd-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="257fd-110">將 Windows 10 裝置加入到貴組織的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="257fd-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="257fd-p102">一旦貴組織中的所有 Windows 裝置皆已升級到 Windows 10 專業版 Creators Update 或已執行 Windows 10 專業版 Creators Update 後，您就可以將這些裝置加入到貴組織的 Azure Active Directory。一旦加入裝置後，裝置將自動升級到 Windows 10 商務版，這是 Microsoft 365 商務版訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="257fd-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="257fd-113">適用於全新或新升級的 Windows 10 專業版裝置</span><span class="sxs-lookup"><span data-stu-id="257fd-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="257fd-114">針對執行 Windows 10 專業版 Creators Update 的全新裝置，或針對已升級到 Windows 10 專業版 Creators Update 但未完成 Windows 10 裝置設定的裝置，請按照這些步驟進行。</span><span class="sxs-lookup"><span data-stu-id="257fd-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="257fd-115">移到 Windows 10 裝置設定，直到到達**您要如何設定？** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="257fd-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="257fd-117">在這裡，選擇 [**為組織設定**，然後輸入您的使用者名稱和密碼，Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="257fd-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="257fd-118">完成 Windows 10 裝置設定。</span><span class="sxs-lookup"><span data-stu-id="257fd-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="257fd-p103">完成後，使用者將連線到貴組織的 Azure AD。請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認。</span><span class="sxs-lookup"><span data-stu-id="257fd-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="257fd-121">適用於已設定且執行 Windows 10 專業版的裝置</span><span class="sxs-lookup"><span data-stu-id="257fd-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="257fd-122">**將使用者連線到 Azure AD：**</span><span class="sxs-lookup"><span data-stu-id="257fd-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="257fd-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span><span class="sxs-lookup"><span data-stu-id="257fd-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="257fd-125">在 [**設定**] 中，移至 [**帳戶**。</span><span class="sxs-lookup"><span data-stu-id="257fd-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="257fd-127">在**您的資訊]** 頁面上，按一下 [**存取公司或學校** \> **連線**。</span><span class="sxs-lookup"><span data-stu-id="257fd-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="257fd-129">在 [**設定公司或學校帳戶**] 對話方塊中，[**其他動作**] 底下選擇 [**加入至 Azure Active Directory 此裝置**。</span><span class="sxs-lookup"><span data-stu-id="257fd-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="257fd-131">在 [**讓我們協助您登入**] 頁面上，輸入您的公司或學校帳戶\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="257fd-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="257fd-132">在 [**輸入密碼**] 頁面上，輸入您的密碼\>**登入**。</span><span class="sxs-lookup"><span data-stu-id="257fd-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="257fd-134">在**確定這是您的組織**] 頁面上，確認資訊正確，然後按一下 [**加入**。</span><span class="sxs-lookup"><span data-stu-id="257fd-134">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="257fd-135">在**一切就緒 ！**</span><span class="sxs-lookup"><span data-stu-id="257fd-135">On the **You're all set!**</span></span> <span data-ttu-id="257fd-136">] 頁面上，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="257fd-136">page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="257fd-p105">如果您將檔案上傳至商務用 OneDrive，請將檔案同步回原處。如果您使用協力廠商工具移轉個人資料和檔案，也請將這些內容同步到新的個人資料。</span><span class="sxs-lookup"><span data-stu-id="257fd-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="257fd-140">驗證裝置已連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="257fd-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="257fd-141">若要確認您的同步處理狀態，在 [**設定**] [**存取公司或學校資源**] 頁面上按一下 [在**連線至**_\<組織名稱\>_ 區域中展示 [**資訊**] 以及 [**中斷連線**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="257fd-141">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="257fd-142">按一下 [**資訊**]，以取得您同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="257fd-142">Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="257fd-143">在 [同步處理狀態] 頁面上，按一下 [同步處理] 將最新的行動裝置管理原則下載到 PC 上。</span><span class="sxs-lookup"><span data-stu-id="257fd-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="257fd-144">若要開始使用 Microsoft 365 商務版帳戶，請移至 Windows [**開始**] 按鈕，以滑鼠右鍵按一下您目前的帳戶圖片然後**切換帳戶**。</span><span class="sxs-lookup"><span data-stu-id="257fd-144">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**.</span></span> <span data-ttu-id="257fd-145">使用您的組織電子郵件和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="257fd-145">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="257fd-147">驗證裝置已升級到 Windows 10 商務版</span><span class="sxs-lookup"><span data-stu-id="257fd-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="257fd-148">驗證 Azure AD 加入的 Windows 10 裝置已升級到 Windows 10 商務版，做為 Microsoft 365 商務版訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="257fd-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="257fd-149">移至 [**設定** \> **系統** \> **有關**。</span><span class="sxs-lookup"><span data-stu-id="257fd-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="257fd-150">確認**版本**] 顯示**Windows 10 商務版**。</span><span class="sxs-lookup"><span data-stu-id="257fd-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="257fd-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="257fd-152">Next steps</span></span>

<span data-ttu-id="257fd-153">若要設定行動裝置，請參閱[為 Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。若要設定裝置保護或 App 保護原則，請參閱[管理 Microsoft 365 商務版](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="257fd-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
