---
title: 在 Office 365 中設定標準或已設定目標發行選項
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何在 Microsoft 365 系統管理中心中設定新的產品與功能更新發行選項。
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251613"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="5b326-103">在 Office 365 中設定標準或已設定目標發行選項</span><span class="sxs-lookup"><span data-stu-id="5b326-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="5b326-p101">有了 Office 365，您就可以在新的產品更新及功能推出時收到這些更新，而不必每幾年進行所費不貲的更新。您可以管理組織收到這些更新的方式。例如，您可以註冊以在早期取得發行的更新，讓您的組織率先收到更新。您可以指定僅特定人員收到這些更新。或者，您可以維持預設的發行排程，於稍後收到更新。本文說明不同的發行選項，以及您可以如何將它運用於您的組織。</span><span class="sxs-lookup"><span data-stu-id="5b326-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5b326-p102">本文中所描述的 Office 365 更新適用於 Office 365、SharePoint Online 和 Exchange Online。這些不適用於商務用 Skype 及相關服務。這些發行選項是有特定對象，並且是發佈 Office 365 變更的最佳方式，但無法保證永遠適用所有更新。</span><span class="sxs-lookup"><span data-stu-id="5b326-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="5b326-113">發行驗證如何運作</span><span class="sxs-lookup"><span data-stu-id="5b326-113">How it works - release validation</span></span>

<span data-ttu-id="5b326-114">第一次測試及驗證由功能小組進行，然後由整個 Office 365 功能小組進行，後面接著所有 Microsoft 的任何新的版本。</span><span class="sxs-lookup"><span data-stu-id="5b326-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="5b326-115">內部測試和驗證之後, 的下一個步驟是**已設定目標發行**（先前稱為初次發行計劃） 選擇加入的客戶。</span><span class="sxs-lookup"><span data-stu-id="5b326-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="5b326-116">在每個發行週期，Microsoft 都會收集意見反應，並透過監視關鍵使用計量，進一步驗證品質。</span><span class="sxs-lookup"><span data-stu-id="5b326-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="5b326-117">這樣一系列的漸進式驗證，都是為了確保全球發行能夠盡可能完善。</span><span class="sxs-lookup"><span data-stu-id="5b326-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="5b326-118">下圖是發行的圖片說明：</span><span class="sxs-lookup"><span data-stu-id="5b326-118">The releases are pictured in the following figure.</span></span> 
  
![驗證週期版 Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="5b326-120">針對重大更新，Office 客戶一開始會由[Microsoft 365 藍圖](https://products.office.com/business/office-365-roadmap)獲得通知。</span><span class="sxs-lookup"><span data-stu-id="5b326-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="5b326-121">當更新變得更接近推出，它會傳達透過[Office 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。</span><span class="sxs-lookup"><span data-stu-id="5b326-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="5b326-122">您必須透過[系統管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)存取您的訊息中心 Office 365 或 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b326-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="5b326-123">Office 365 家用版方案的使用者沒有系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5b326-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="5b326-124">標準發行</span><span class="sxs-lookup"><span data-stu-id="5b326-124">Standard release</span></span>

<span data-ttu-id="5b326-125">這是預設選項： 您和您的使用者收到最新的更新時正在廣泛發行給所有客戶。</span><span class="sxs-lookup"><span data-stu-id="5b326-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="5b326-126">很好的作法是將大部分使用者在**標準發行**和 IT 專業人員和電源中的使用者來評估新功能，並準備小組**已設定目標發行**至支援商務使用者和主管。</span><span class="sxs-lookup"><span data-stu-id="5b326-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5b326-127">如果您從已設定目標發行切換回標準發行，您的使用者可能無法存取尚未到達標準發行的功能。</span><span class="sxs-lookup"><span data-stu-id="5b326-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="5b326-128">已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="5b326-128">Targeted release</span></span>

<span data-ttu-id="5b326-p106">使用此選項時，您和您的使用者將成為第一批使用最新更新的人員，並可率先提供意見反應來協助改進產品。您可以選擇讓個人或整個組織率先收到更新。</span><span class="sxs-lookup"><span data-stu-id="5b326-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5b326-p107">較大或較複雜的更新可能需要比其他更新更長的時間，以免對使用者造成負面影養。我們無法保持發行的確切時間表。</span><span class="sxs-lookup"><span data-stu-id="5b326-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="5b326-133">適用於整個組織的已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="5b326-133">Targeted release for entire organization</span></span>

<span data-ttu-id="5b326-134">如果您[在系統管理中心的 [版本] 選項設定](#set-up-the-release-option-in-the-admin-center)此選項，您所有的使用者會收到已設定目標發行 」 體驗。</span><span class="sxs-lookup"><span data-stu-id="5b326-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="5b326-135">針對超過 300 個使用者的組織，建議您針對此選項使用測試訂閱。</span><span class="sxs-lookup"><span data-stu-id="5b326-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="5b326-136">如需測試訂閱資訊，請連絡您的 Microsoft 連絡人。</span><span class="sxs-lookup"><span data-stu-id="5b326-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="5b326-137">適用於已選取使用者的已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="5b326-137">Targeted release for selected users</span></span>

<span data-ttu-id="5b326-138">如果您[在系統管理中心的 [版本] 選項設定](#set-up-the-release-option-in-the-admin-center)此選項，您可以定義特定使用者，通常是電源，以接收搶先特色與功能。</span><span class="sxs-lookup"><span data-stu-id="5b326-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="5b326-139">已設定目標發行的優點</span><span class="sxs-lookup"><span data-stu-id="5b326-139">Benefits of Targeted release</span></span>

<span data-ttu-id="5b326-140">已設定目標發行可讓系統管理員、變更管理員，或者任何負責 Office 365 更新的人員為即將到來的變更做好準備，方法是：</span><span class="sxs-lookup"><span data-stu-id="5b326-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="5b326-141">在新的更新發行給組織中的所有使用者之前，對更新進行測試與驗證。</span><span class="sxs-lookup"><span data-stu-id="5b326-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="5b326-142">在更新全球發行之前準備使用者通知與文件。</span><span class="sxs-lookup"><span data-stu-id="5b326-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="5b326-143">針對即將到來的變更準備內部技術支援中心。</span><span class="sxs-lookup"><span data-stu-id="5b326-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="5b326-144">瀏覽合規性與安全性審查。</span><span class="sxs-lookup"><span data-stu-id="5b326-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="5b326-145">使用功能控制項 (如果適用的話) 來控制發行給使用者的更新。</span><span class="sxs-lookup"><span data-stu-id="5b326-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="5b326-146">在系統管理中心中設定發行選項</span><span class="sxs-lookup"><span data-stu-id="5b326-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="5b326-p109">您可以依照下列步驟，變更您的組織收到 Office 365 更新的方式。您必須是 Office 365 中的全域系統管理員才能加入。</span><span class="sxs-lookup"><span data-stu-id="5b326-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5b326-p110">以下變更可能需要 24 小時的時間，才能在 Office 365 中生效。如果您在啟用已設定目標發行後選擇退出，使用者可能會無法存取尚未到達排定發行的功能。</span><span class="sxs-lookup"><span data-stu-id="5b326-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="5b326-151">在系統管理中心，移至 [**設定** > **設定**，並在 [**組織設定檔**] 索引標籤上，選擇 [**發行喜好設定**。</span><span class="sxs-lookup"><span data-stu-id="5b326-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="5b326-152">若要停用已設定目標的發行，請選取 [**標準發行**，然後選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="5b326-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="5b326-153">若要啟用已設定目標的發行您的組織中的所有使用者，請選取 [**已設定目標發行的所有人**，然後選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="5b326-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="5b326-154">若要啟用已設定目標的發行的部分人員在組織中，選取**所選使用者的已設定目標發行**，然後選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="5b326-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="5b326-155">若要新增一位使用者在時間，或將它們新增大量**上傳的使用者**，選擇 [**選取使用者**。</span><span class="sxs-lookup"><span data-stu-id="5b326-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="5b326-156">當您新增完使用者後，請選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="5b326-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="5b326-157">取得 Office 已設定目標發行版本</span><span class="sxs-lookup"><span data-stu-id="5b326-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="5b326-p111">若要安裝 Office 已設定目標發行組建，[請遵循以下步驟](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead)。完成後您就能夠提早使用 Windows 傳統型 Office 2016 新功能。</span><span class="sxs-lookup"><span data-stu-id="5b326-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="5b326-160">深入了解</span><span class="sxs-lookup"><span data-stu-id="5b326-160">Learn more</span></span>

<span data-ttu-id="5b326-161">探索如何取得有關即將來臨的 Office 365 更新和發行的通知您[Office 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)中的 [[管理的郵件](https://docs.microsoft.com/office365/admin/manage/message-center)。</span><span class="sxs-lookup"><span data-stu-id="5b326-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
