---
title: 為 Microsoft 365 商務版使用者設定 Windows 裝置
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 瞭解如何設定執行 Windows 10 Pro for Microsoft 365 商務版使用者的 Windows 裝置，以啟用集中式管理及安全性控制。
ms.openlocfilehash: ecd9f5aa348d29d34e77061657619c015b09c41a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402951"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="7ebd4-103">為 Microsoft 365 商務版使用者設定 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="7ebd4-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="7ebd4-104">為 Microsoft 365 商務版使用者設定 Windows 裝置的必要條件</span><span class="sxs-lookup"><span data-stu-id="7ebd4-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="7ebd4-105">在您可以為 Microsoft 365 商務版使用者設定 Windows 裝置之前，請確定所有 Windows 裝置都執行 Windows 10 專業版，版本1703（創意者更新）。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="7ebd4-106">Windows 10 專業版是部署 Windows 10 商務版的必要條件，也就是一組雲端服務和裝置管理功能，可補充 Windows 10 專業人員，並啟用 Microsoft 365 商務版的集中式管理及安全性控制。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="7ebd4-107">如果您有執行 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 Pro 的 Windows 裝置，您的 Microsoft 365 商務版特優訂閱可讓您執行 Windows 10 升級。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="7ebd4-108">如需有關如何將 Windows 裝置升級到 Windows 10 專業版 Creators Update 的資訊，請按照本主題中的步驟進行：[將 Windows 裝置升級到 Windows 專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="7ebd4-109">請參閱 Verify the device the the the the device the the [AZURE AD](#verify-the-device-is-connected-to-azure-ad) to verify the the the the the the the the the the</span><span class="sxs-lookup"><span data-stu-id="7ebd4-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="7ebd4-110">觀賞有關將 Windows 連接至 Microsoft 365 的簡短影片。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="7ebd4-111">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="7ebd4-112">將 Windows 10 裝置加入到貴組織的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ebd4-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="7ebd4-113">當您組織中的所有 Windows 裝置都已升級至 Windows 10 Pro 創意者更新，或已執行 Windows 10 Pro 編寫者更新時，您可以將這些裝置加入您組織的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="7ebd4-114">裝置加入後，系統會自動升級至 Windows 10 商務版，這是 Microsoft 365 商務版 Premium 訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="7ebd4-115">適用於全新或新升級的 Windows 10 專業版裝置</span><span class="sxs-lookup"><span data-stu-id="7ebd4-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="7ebd4-116">針對執行 Windows 10 專業版 Creators Update 的全新裝置，或針對已升級到 Windows 10 專業版 Creators Update 但未完成 Windows 10 裝置設定的裝置，請按照這些步驟進行。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="7ebd4-117">流覽 Windows 10 裝置安裝程式，直到您看到 [**您要如何設定？** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="7ebd4-119">在這裡，選擇 [**為組織設定**]，然後輸入 Microsoft 365 商務版的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="7ebd4-120">完成 Windows 10 裝置設定。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="7ebd4-p103">完成後，使用者將連線到貴組織的 Azure AD。請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="7ebd4-123">適用於已設定且執行 Windows 10 專業版的裝置</span><span class="sxs-lookup"><span data-stu-id="7ebd4-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="7ebd4-124">**將使用者連線到 Azure AD：**</span><span class="sxs-lookup"><span data-stu-id="7ebd4-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="7ebd4-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span><span class="sxs-lookup"><span data-stu-id="7ebd4-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="7ebd4-127">在 [**設定**] 中，移至 [**帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="7ebd4-129">在 [**資訊**] 頁面上，按一下 [**存取工作或 school** \> **Connect]**。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="7ebd4-131">在 [**設定公司或學校帳戶**] 對話方塊的 [**替代動作**] 下，選擇 [將**此裝置加入 Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="7ebd4-133">在 [**讓您登入**] 頁面上，輸入您 \> **下一個**工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="7ebd4-134">在 [**輸入密碼**] 頁面上，輸入您的密碼登 \> **入**。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="7ebd4-136">在 [**確定這是您的組織**] 頁面上，確認資訊正確無誤，然後按一下 [**加入**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="7ebd4-137">已**全部設定！**</span><span class="sxs-lookup"><span data-stu-id="7ebd4-137">On the **You're all set!**</span></span> <span data-ttu-id="7ebd4-138">頁面上，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-138">page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="7ebd4-140">如果您將檔案上傳至商務用 OneDrive，請將檔案同步回原處。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="7ebd4-141">如果您使用協力廠商工具來遷移設定檔和檔案，也請將其同步處理至新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="7ebd4-142">驗證裝置已連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ebd4-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="7ebd4-143">若要驗證您的同步處理狀態，請在 [**設定**] 中的 [**存取工作或學校**] 頁面上，按一下 [**已連線到**_ \<organization name\> _ **]** 區域，以公開按鈕**資訊**並中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-143">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="7ebd4-144">按一下 [**資訊**] 以取得同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-144">Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="7ebd4-145">在 [同步處理狀態] 頁面上，按一下 [同步處理] 將最新的行動裝置管理原則下載到 PC 上。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="7ebd4-146">若要開始使用 Microsoft 365 商務版帳戶，請移至 Windows [**開始**] 按鈕，以滑鼠右鍵按一下您目前的帳戶圖片，然後**切換帳戶**。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="7ebd4-147">使用您的組織電子郵件和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="7ebd4-149">驗證裝置已升級到 Windows 10 商務版</span><span class="sxs-lookup"><span data-stu-id="7ebd4-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="7ebd4-150">請確認您的 Azure AD 加入 Windows 10 裝置已升級到 Windows 10 商務版，成為 Microsoft 365 商務版 Premium 訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="7ebd4-151">移至 [**設定** \> **系統**] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="7ebd4-152">確認該版本顯示**Windows 10 商務\*\*\*\*版**。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="7ebd4-154">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7ebd4-154">Next steps</span></span>

<span data-ttu-id="7ebd4-155">若要設定行動裝置，請參閱為[microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。若要設定裝置保護或應用程式保護原則，請參閱[管理 Microsoft 365 for Business](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebd4-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="7ebd4-156">如需設定及使用 Microsoft 365 商務版 Premium 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7ebd4-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="7ebd4-157">商務用 Microsoft 365 訓練影片</span><span class="sxs-lookup"><span data-stu-id="7ebd4-157">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
