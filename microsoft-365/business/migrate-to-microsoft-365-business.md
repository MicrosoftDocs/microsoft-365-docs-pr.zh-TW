---
title: 從 Office 365 商務進階版升級至 Microsoft 365 商務版
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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 將貴公司從 Office 365 商務進階版升級至 Microsoft 365 商務版的步驟。
ms.openlocfilehash: 0732f76e5bd8540e5954bd7ea7b88061326901b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593672"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="13f79-103">從 Office 365 商務進階版升級至 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="13f79-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="13f79-104">如果您有[Office 365 商務版訂閱](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)，例如 Office 365 商務進階版，您可以輕鬆地升級至 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="13f79-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="13f79-105">如果您想要加入，升級至 Microsoft 365 商務版：</span><span class="sxs-lookup"><span data-stu-id="13f79-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="13f79-106">Windows 10 專業版 （若要執行 Windows 8 或更新版本的電腦）</span><span class="sxs-lookup"><span data-stu-id="13f79-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="13f79-107">簡單管理裝置上的商務資料的控制項</span><span class="sxs-lookup"><span data-stu-id="13f79-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="13f79-108">進階的安全性的功能。</span><span class="sxs-lookup"><span data-stu-id="13f79-108">Advanced security capabilities.</span></span>
<span data-ttu-id="13f79-109">進一步了解如何在[Microsoft.com](https://www.microsoft.com/microsoft-365/business) Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="13f79-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="13f79-110">Office 365 商務進階版和 Microsoft 365 商務版之間的差異為何？</span><span class="sxs-lookup"><span data-stu-id="13f79-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="13f79-111">我們已加入下列兩個計劃以並排比較至[Microsoft 365 商務版服務說明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)。</span><span class="sxs-lookup"><span data-stu-id="13f79-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="13f79-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="13f79-112">Before you get started</span></span>

- <span data-ttu-id="13f79-113">**何時我應該選擇先升級？**</span><span class="sxs-lookup"><span data-stu-id="13f79-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="13f79-114">升級時，選擇您想要升級**的所有使用者**指派給單一計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="13f79-115">當您選擇升級時，所有計劃使用者取得切換到另一個計劃在同一時間。</span><span class="sxs-lookup"><span data-stu-id="13f79-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="13f79-116">如果您不想要升級所有人指派給單一計劃，請購買新方案 （在此情況 Microsoft 365 商務版），以及[個別指派這些授權](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)給您想要升級每位使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="13f79-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="13f79-117">**某些附加元件可能會導致升級**如果您嘗試啟動升級，且必須防止您繼續執行的附加元件，您可以請先移除附加元件，並再新增回來稍後如果您仍然需要。</span><span class="sxs-lookup"><span data-stu-id="13f79-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span> 
- <span data-ttu-id="13f79-118">**如果您預付您計劃**沒有預付方案直接升級路徑。</span><span class="sxs-lookup"><span data-stu-id="13f79-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="13f79-119">您會知道是否您有預付的方案。 因為您設定儲存區中使用您可能已購買的產品識別碼您計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="13f79-120">合作夥伴連絡，移至 Microsoft 網上商店或請稍候，直到您預付的方案過期切換至新的計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="13f79-121">升級至 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="13f79-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="13f79-122">遵循下列步驟在[新版系統管理中心](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)購買授權：</span><span class="sxs-lookup"><span data-stu-id="13f79-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="13f79-123">登入系統管理中心在<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="13f79-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="13f79-124">移至功能窗格，然後選取 [**帳單** \> **產品 & 服務**。</span><span class="sxs-lookup"><span data-stu-id="13f79-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="13f79-125">尋找您的 Office 365 訂閱，然後選取要檢視詳細資料。</span><span class="sxs-lookup"><span data-stu-id="13f79-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![螢幕擷取畫面顯示如何尋找並選取您的訂閱在系統管理中心。](media/FindYourSubscription.png)

3. <span data-ttu-id="13f79-127">在下一個頁面上，選取 [**升級**]。</span><span class="sxs-lookup"><span data-stu-id="13f79-127">On the next page, select **Upgrade**.</span></span> 

      ![螢幕擷取畫面顯示在系統管理中心中選取 [升級] 的位置。](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="13f79-129">如果您看到訊息，指出**的升級您的訂閱不支援與在 Azure Active Directory 群組為基礎的授權**，則可以放心忽略這除非您有非常大型的組織。</span><span class="sxs-lookup"><span data-stu-id="13f79-129">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="13f79-130">組織者選取了此選項會知道他們正在使用群組為基礎的授權。</span><span class="sxs-lookup"><span data-stu-id="13f79-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="13f79-131">接下來，您可以檢視清單中的，您可以升級至 Office 計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="13f79-132">在此情況下，尋找 Microsoft 365 商務版計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="13f79-133">您可以向下捲動如果您想要查看所有 Office 應用程式及隨附於此計劃的服務。</span><span class="sxs-lookup"><span data-stu-id="13f79-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="13f79-134">**Microsoft 365 商務版**，在 [選取要新增至購物車的 Microsoft 365 商務版**升級**。</span><span class="sxs-lookup"><span data-stu-id="13f79-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="13f79-135">在 [購物車：</span><span class="sxs-lookup"><span data-stu-id="13f79-135">In the cart:</span></span>
    1. <span data-ttu-id="13f79-136">我們將會自動包含所有目前使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="13f79-136">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="13f79-137">如果您需要更多或較少的授權，您需要[購買](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)並個別指派這些授權。</span><span class="sxs-lookup"><span data-stu-id="13f79-137">If you need more or fewer licenses, you need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="13f79-138">您可以調整您想要支付的方式： 每月或每年。</span><span class="sxs-lookup"><span data-stu-id="13f79-138">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="13f79-139">選取下拉式] 功能表，可讓您選擇。</span><span class="sxs-lookup"><span data-stu-id="13f79-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="13f79-140">選取 [**移至簽出**，您會看到購買，包括針對此帳戶的付款方式項目的摘要。</span><span class="sxs-lookup"><span data-stu-id="13f79-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="13f79-141">如果有的話，您也可以新增的促銷代碼。</span><span class="sxs-lookup"><span data-stu-id="13f79-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="13f79-142">選取 [**下單**]，以完成購買。</span><span class="sxs-lookup"><span data-stu-id="13f79-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="13f79-143">若要設定新服務計劃的幾分鐘的花 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="13f79-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="13f79-144">若要檢查進度，請選取 [**檢查升級狀態**。</span><span class="sxs-lookup"><span data-stu-id="13f79-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="13f79-145">準備您的計劃之後，您可能需要完成一些額外設定步驟，在系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="13f79-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="13f79-146">在 [功能窗格中，選取 [**住家**完成任何額外的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="13f79-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="13f79-147">您會收到您不再需要的 Office 365 授權依比例的退款。</span><span class="sxs-lookup"><span data-stu-id="13f79-147">You'll receive a prorated refund for the Office 365 licenses that you no longer need.</span></span> <span data-ttu-id="13f79-148">您的銀行帳戶或信用卡將支付約兩天後設定新的計劃。</span><span class="sxs-lookup"><span data-stu-id="13f79-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="13f79-149">保護使用者裝置和檔案</span><span class="sxs-lookup"><span data-stu-id="13f79-149">Protect user devices and files</span></span>

<span data-ttu-id="13f79-150">現在，Microsoft 365 商務版授權已指派，完成步驟，以啟動保護裝置和檔案。</span><span class="sxs-lookup"><span data-stu-id="13f79-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="13f79-151">您可以使用系統管理中心瀏覽窗格中包含一些新選項。</span><span class="sxs-lookup"><span data-stu-id="13f79-151">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="13f79-152">在系統管理中心，在 [功能窗格中，移至 [**裝置** \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="13f79-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="13f79-153">在 [**裝置原則**] 頁面上，選取 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="13f79-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="13f79-154">在 [**新增原則**] 窗格中指定原則名稱 （例如，保護工作檔案），，然後從下拉式清單中選擇 [**原則類型**。</span><span class="sxs-lookup"><span data-stu-id="13f79-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span> 
    
    <span data-ttu-id="13f79-155">您可以設定應用程式原則保護 Android 和 iPhone 裝置以及 Windows 10 上的檔案，您可以設定公司擁有 Windows 10 裝置的裝置設定原則。</span><span class="sxs-lookup"><span data-stu-id="13f79-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="13f79-156">請參閱下列連結，如需詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="13f79-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="13f79-157">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="13f79-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="13f79-158">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="13f79-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="13f79-159">設定適用於 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="13f79-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="13f79-160">設定原則之後，您和您的員工可以設定裝置：</span><span class="sxs-lookup"><span data-stu-id="13f79-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="13f79-161">如果您的 Windows 裝置已不使用 Windows Pro Creator 更新，您需要[升級至 Windows [專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="13f79-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="13f79-162">如需 Windows 裝置步驟，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="13f79-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="13f79-163">如需 Android 手機和 Iphone 步驟，請參閱[為 Microsoft 365 商務版使用者的行動裝置上設定](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="13f79-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
