---
title: 從 Office 365 商務進階版移轉到 Microsoft 365 商務版
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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何將業務移至 Microsoft 365 商務版。
ms.openlocfilehash: 3e45ba13e4cfe772829f545219bf86a9a3317d59
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285628"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="423f0-103">從 Office 365 商務進階版移轉到 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="423f0-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="423f0-104">如果您已經有 Office 365 商務版訂閱，例如 Office 365 商務進階版，您可以輕鬆地將授權新增至 Microsoft 365 商務版，並將它們指派給部分或所有使用者。</span><span class="sxs-lookup"><span data-stu-id="423f0-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="423f0-105">您無法使用 [[切換方案](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton)] 按鈕尚未升級為 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="423f0-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="423f0-106">新增 Microsoft 365 商務版授權</span><span class="sxs-lookup"><span data-stu-id="423f0-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="423f0-107">您有兩種方法可以取得 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="423f0-107">You have two ways to get Microsoft 365 Business.</span></span> <span data-ttu-id="423f0-108">如果您有合作夥伴，他或她可以購買 Microsoft 365 商務版您從[Microsoft 合作夥伴中心](get-microsoft-365-business.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-108">If you have a partner, he or she can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md).</span></span> <span data-ttu-id="423f0-109">您的合作夥伴也可以協助您轉換到 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="423f0-109">Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="423f0-110">如果您管理自己的訂閱，您可以[連絡銷售人員](https://www.microsoft.com/microsoft-365/business)購買 Microsoft 365 商務版授權。</span><span class="sxs-lookup"><span data-stu-id="423f0-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="423f0-111">請參閱 <<c0>新增、 變更或刪除訂閱顧問合作夥伴以了解如何開始使用與合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="423f0-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="423f0-112">如果您給定購買您授權的連結，您將會逐步執行精靈像以下這樣。</span><span class="sxs-lookup"><span data-stu-id="423f0-112">If you are given a link to purchase your licences, you will walk through a wizard like the one below.</span></span> <span data-ttu-id="423f0-113">選擇 [**是]，新增到我的帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="423f0-113">Choose **Yes, add it to my account**.</span></span> <span data-ttu-id="423f0-114">您也可以選擇的授權數目與付款的方法。</span><span class="sxs-lookup"><span data-stu-id="423f0-114">You can also pick the number of licences and the method of payment.</span></span>
  
![在 Microsoft 365 商務版直接購買連結中，選擇要新增到您目前的帳戶，或註冊新的帳戶。](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="423f0-116">將 Microsoft 365 授權指派</span><span class="sxs-lookup"><span data-stu-id="423f0-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="423f0-117">一旦您已購買新授權，且這是您沒有在第一次，Microsoft 365 商務版設定橫幅會顯示在系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="423f0-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="423f0-118">安裝程式橫幅 」 是有機會加入新的使用者，新的網域，並將新使用者的電子郵件移轉。</span><span class="sxs-lookup"><span data-stu-id="423f0-118">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="423f0-119">如果您不執行任何計劃，您仍應該通過精靈，然後選擇 [使它消失從 [系統管理] 首頁上的預設選項。</span><span class="sxs-lookup"><span data-stu-id="423f0-119">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![選擇 [在 Microsoft 365 商務版上的啟動安裝程式已準備好設定橫幅。](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="423f0-121">Choose **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="423f0-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="423f0-122">在**個人化登入和電子郵件**] 頁面上，您可以藉由選擇**連接您已經擁有網域**，如果您想要使用這個機會將另一個網域新增至您的訂閱新增網域。</span><span class="sxs-lookup"><span data-stu-id="423f0-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="423f0-123">如果您已設定網域，第二個欄位會指出，並會**繼續使用**像是\<_您的網域名稱_\> **的電子郵件和登入**。  </span><span class="sxs-lookup"><span data-stu-id="423f0-123">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="423f0-124">如果您尚未設定網域加上您的訂閱，它會像是**繼續使用** \<_貴公司 name.onmicrosoft.com_ \> **的電子郵件和登入**。  </span><span class="sxs-lookup"><span data-stu-id="423f0-124">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="423f0-125">選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="423f0-125">Choose **Next**.</span></span>
    
    ![在 [登入的個人化] 和 [電子郵件] 頁面中，選擇 [新增網域，或使用您使用一個。](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="423f0-127">在 [**新增新使用者**] 頁面中，您可以新增新的使用者，如果您有想要指派至 Microsoft 365 商務版授權的新員工。</span><span class="sxs-lookup"><span data-stu-id="423f0-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="423f0-128">如果您沒有新員工加入而且想要將授權指派給現有的使用者，請選擇 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="423f0-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="423f0-129">在 \* \* 遷移電子郵件訊息 \* \*] 頁面上，您可以選擇任何您在步驟 3 中新增的新使用者的電子郵件移轉。</span><span class="sxs-lookup"><span data-stu-id="423f0-129">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="423f0-130">您也可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="423f0-130">You can skip this step also.</span></span> <span data-ttu-id="423f0-131">選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="423f0-131">Choose **Next**.</span></span>
    
5. <span data-ttu-id="423f0-132">在最後一個頁面上，選擇 [**移至系統管理中心**，並那里繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="423f0-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="423f0-133">在系統管理中心，移至 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="423f0-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="423f0-134">選取您要指派， **Microsoft 365 商務版**授權的使用者，然後選擇 [旁的 [**編輯\*\*\*\*產品授權**。</span><span class="sxs-lookup"><span data-stu-id="423f0-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![在 [使用者] 卡片中，選擇 [產品授權] 旁的 [編輯]。](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="423f0-136">在 [**產品授權**滑動**Microsoft 365 商務版\*\*\*\*上** \> **儲存**，然後**關閉**。</span><span class="sxs-lookup"><span data-stu-id="423f0-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="423f0-137">一旦您已購買的初始授權的 Microsoft 365 商務版，您現在也可以新增更多在**帳單** \> **購買服務**。</span><span class="sxs-lookup"><span data-stu-id="423f0-137">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**.</span></span> <span data-ttu-id="423f0-138">在 [**購買服務**] 頁面上您可以按一下省略符號 [ **Microsoft 365 商務版**] 卡片上，然後選擇 [購買更多**變更授權數量**。</span><span class="sxs-lookup"><span data-stu-id="423f0-138">On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="423f0-139">保護使用者裝置和檔案</span><span class="sxs-lookup"><span data-stu-id="423f0-139">Protect user devices and files</span></span>

<span data-ttu-id="423f0-140">您已指派授權給 Microsoft 365 商務版之後，您可以開始保護使用者的裝置和檔案。</span><span class="sxs-lookup"><span data-stu-id="423f0-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="423f0-141">在系統管理中心中，在左側導覽中，移至 [**裝置** \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="423f0-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="423f0-142">在 [**裝置原則**] 頁面上，選擇 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="423f0-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="423f0-143">在 [**新增原則**] 窗格中輸入原則的名稱，，然後從下拉式清單中選擇 [**原則類型**。</span><span class="sxs-lookup"><span data-stu-id="423f0-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="423f0-144">您可以設定應用程式原則保護 Android 和 iPhone 裝置以及 Windows 10 上的檔案，您可以設定公司擁有 Windows 10 裝置的裝置設定原則。</span><span class="sxs-lookup"><span data-stu-id="423f0-144">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="423f0-145">請參閱下列連結，如需詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="423f0-145">See the following links for details:</span></span>
    
  - [<span data-ttu-id="423f0-146">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="423f0-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="423f0-147">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="423f0-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="423f0-148">設定適用於 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="423f0-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![在 [新增原則] 窗格中，輸入名稱，然後選擇 [原則類型從下拉式清單功能表。](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="423f0-150">一旦您設定原則時，您和您的員工可以設定裝置：</span><span class="sxs-lookup"><span data-stu-id="423f0-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="423f0-151">如果您的 Windows 已經不在 Windows Pro Creator 更新，您必須[升級至 Windows [專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="423f0-152">如需 Windows 裝置步驟，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="423f0-153">如需 Android 手機和 Iphone 步驟，請參閱[為 Microsoft 365 商務版使用者的行動裝置上設定](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="423f0-154">若要自動安裝 Office 用戶端應用程式，請參閱[準備 Office 用戶端部署 Microsoft 365 商務版](prepare-for-office-client-deployment.md)和[自動安裝或解除安裝 Windows 10 裝置上的 Office](auto-install-or-uninstall-office.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


