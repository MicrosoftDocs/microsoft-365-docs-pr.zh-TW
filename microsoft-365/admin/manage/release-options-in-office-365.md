---
title: 設定標準或目標發行選項
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 瞭解如何在 Microsoft 365 系統管理中心中，設定新產品及功能更新的發行選項。
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593942"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="6a0a1-103">設定標準或目標發行選項</span><span class="sxs-lookup"><span data-stu-id="6a0a1-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a0a1-104">本文所述的 Microsoft 365 更新適用于 Microsoft 365、SharePoint 線上及 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="6a0a1-105">這些版本選項的目標是針對 Microsoft 365 發佈變更的最佳方式，但在任何時間或所有更新皆無法保證。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="6a0a1-106">不適用於 Microsoft 365 Apps、商務用 Skype、Microsoft Teams 和相關的服務。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="6a0a1-107">如需 Microsoft 365 Apps 之版本選項的詳細資訊，請參閱[Microsoft 365 Apps 的更新通道](/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="6a0a1-108">透過 Microsoft 365，您會在新的產品更新和功能可供使用時立即收到，而不是每隔幾年執行昂貴的更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="6a0a1-109">您可以管理組織收到這些更新的方式。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="6a0a1-110">例如，您可以註冊以在早期取得發行的更新，讓您的組織率先收到更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="6a0a1-111">您可以指定僅特定人員收到這些更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="6a0a1-112">或者，您可以維持預設的發行排程，於稍後收到更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="6a0a1-113">本文說明不同的發行選項，以及您可以如何將它們用於您的組織。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="6a0a1-114">發行驗證如何運作</span><span class="sxs-lookup"><span data-stu-id="6a0a1-114">How it works - release validation</span></span>

<span data-ttu-id="6a0a1-115">任何新的版本都會先由功能小組進行測試及驗證，然後由整個 Microsoft 365 的功能小組進行測試，接著所有的 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="6a0a1-116">在內部測試及驗證之後，下一步是 **目標發行** (（先前稱為「初次發行」) 客戶加入宣告）。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="6a0a1-117">在每個發行週期，Microsoft 都會收集意見反應，並透過監視關鍵使用計量，進一步驗證品質。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="6a0a1-118">這樣一系列的漸進式驗證，都是為了確保全球發行能夠盡可能完善。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="6a0a1-119">下圖是發行的圖片說明：</span><span class="sxs-lookup"><span data-stu-id="6a0a1-119">The releases are pictured in the following figure.</span></span> 
  
![Microsoft 365 的版本驗證振鈴](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="6a0a1-121">對於重要的更新，客戶最初會收到[Microsoft 365 藍圖](https://products.office.com/business/office-365-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="6a0a1-122">當更新變得更接近時，它會透過您的[Microsoft 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)進行傳遞。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="6a0a1-123">您需要 Microsoft 365 或 Azure AD 帳戶，才能透過系統[管理中心](/office365/admin/admin-overview/about-the-admin-center)存取您的郵件中心。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="6a0a1-124">Microsoft 365 家用方案使用者沒有系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="6a0a1-125">標準發行</span><span class="sxs-lookup"><span data-stu-id="6a0a1-125">Standard release</span></span>

<span data-ttu-id="6a0a1-126">這是預設選項，當您和您的使用者廣泛發佈給所有客戶時，您就會收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="6a0a1-127">好的做法是讓大部分的使用者都是在 **標準發行** 中，也可以讓 IT 專業人員和超級使用者在 **目標版本** 中，評估新功能，並準備小組以支援商務使用者和主管人員。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6a0a1-128">如果您從已設定目標發行切換回標準發行，您的使用者可能無法存取尚未到達標準發行的功能。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="6a0a1-129">已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="6a0a1-129">Targeted release</span></span>

<span data-ttu-id="6a0a1-p106">使用此選項時，您和您的使用者將成為第一批使用最新更新的人員，並可率先提供意見反應來協助改進產品。您可以選擇讓個人或整個組織率先收到更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6a0a1-p107">較大或較複雜的更新可能需要比其他更新更長的時間，以免對使用者造成負面影養。我們無法保持發行的確切時間表。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="6a0a1-134">適用於整個組織的已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="6a0a1-134">Targeted release for entire organization</span></span>

<span data-ttu-id="6a0a1-135">如果您為此選項 [設定系統管理中心的 [發行] 選項](#set-up-the-release-option-in-the-admin-center) ，所有的使用者都將取得目標的發行體驗。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="6a0a1-136">針對超過 300 個使用者的組織，建議您針對此選項使用測試訂閱。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="6a0a1-137">如需測試訂閱資訊，請連絡您的 Microsoft 連絡人。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="6a0a1-138">適用於已選取使用者的已設定目標發行</span><span class="sxs-lookup"><span data-stu-id="6a0a1-138">Targeted release for selected users</span></span>

<span data-ttu-id="6a0a1-139">如果您為此選項 [設定系統管理中心的 [發行] 選項](#set-up-the-release-option-in-the-admin-center) ，您可以定義特定使用者（通常為 [超級使用者]）以接收可及早存取功能。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="6a0a1-140">已設定目標發行的優點</span><span class="sxs-lookup"><span data-stu-id="6a0a1-140">Benefits of Targeted release</span></span>

<span data-ttu-id="6a0a1-141">目標版本可讓系統管理員、變更管理員或其他人負責 Microsoft 365 更新，以準備即將進行的變更，其方式如下：</span><span class="sxs-lookup"><span data-stu-id="6a0a1-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="6a0a1-142">在新的更新發行給組織中的所有使用者之前，對更新進行測試與驗證。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="6a0a1-143">在更新全球發行之前準備使用者通知與文件。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="6a0a1-144">針對即將到來的變更準備內部技術支援中心。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="6a0a1-145">瀏覽合規性與安全性審查。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="6a0a1-146">使用功能控制項 (如果適用的話) 來控制發行給使用者的更新。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="6a0a1-147">設定系統管理中心的 [發行] 選項</span><span class="sxs-lookup"><span data-stu-id="6a0a1-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="6a0a1-148">您可以遵循下列步驟，變更組織接收 Microsoft 365 更新的方式。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="6a0a1-149">您必須是全域系統管理員，才能 Microsoft 365 自願加入。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6a0a1-150">最多可能需要24小時的時間，變更才會在 Microsoft 365 中生效。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="6a0a1-151">如果您在啟用已設定目標發行後選擇退出，使用者可能會無法存取尚未到達排定發行的功能。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="6a0a1-152">在系統管理中心中，移至 [**設定**  >  **Org 設定**]，然後在 [**組織設定檔**] 索引標籤下，選擇 [**發行喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="6a0a1-153">若要停用目標版本，請選取 [ **標準版本**]，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="6a0a1-154">若要為組織中的所有使用者啟用目標版本，請為 [所有人] 選取 [ **目標版本**]，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="6a0a1-155">若要為組織中的某些人員啟用目標版本，請選取 [ **目標的版本] 選取的使用者**，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="6a0a1-156">選擇 [**選取使用者**]，一次新增一個使用者，或 **Upload 使用者** 成批新增。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="6a0a1-157">當您新增使用者後，請選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="6a0a1-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6a0a1-158">Next steps</span></span>

<span data-ttu-id="6a0a1-159">探索如何在[Microsoft 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)[管理郵件](/office365/admin/manage/message-center)，以取得即將推出 Microsoft 365 更新及發行的通知。</span><span class="sxs-lookup"><span data-stu-id="6a0a1-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="6a0a1-160">相關內容</span><span class="sxs-lookup"><span data-stu-id="6a0a1-160">Related content</span></span>

<span data-ttu-id="6a0a1-161">[加入 Office 的內幕程式](https://insider.office.com/join/windows) (文章) </span><span class="sxs-lookup"><span data-stu-id="6a0a1-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
