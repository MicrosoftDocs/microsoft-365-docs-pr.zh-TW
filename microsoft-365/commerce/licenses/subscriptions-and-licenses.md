---
title: 了解商務用 Office 365 中的訂閱與授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: '了解的訂閱與授權在 Office 365 商務版，並知道誰可以指派授權，以及您指派授權給某人時會發生什麼情況。 '
ms.custom: okr_SMB
ms.openlocfilehash: 1a90e4b80322ad075f2149801aebd02ac07a2aef
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239734"
---
# <a name="understand-subscriptions-and-licenses-in-office-365-for-business"></a><span data-ttu-id="155de-103">了解商務用 Office 365 中的訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="155de-103">Understand subscriptions and licenses in Office 365 for business</span></span>

<span data-ttu-id="155de-104">本文說明的訂閱與授權、 之間的關係，並提供[誰可以指派授權](#find-out-who-can-assign-licenses)，[了解您指派授權給某人時會發生什麼情況](#understand-what-happens-when-you-assign-a-license-to-someone)，以及[多少部裝置可以人員上安裝 Office](#how-many-devices-can-people-install-office-on)相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="155de-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="155de-105">它還包含[了解非使用者信箱的授權](#understand-licenses-for-non-user-mailboxes)，以及[有關如何管理授權文章](#articles-about-managing-licenses)的連結。</span><span class="sxs-lookup"><span data-stu-id="155de-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="155de-106">當您購買 Office 365 訂閱商務，註冊應用程式的一組，並服務該工資上 [每月或每年。</span><span class="sxs-lookup"><span data-stu-id="155de-106">When you buy a subscription to Office 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="155de-107">應用程式和服務，您收到為訂閱的一部分取決於哪些產品上您購買，例如 Office 365 商務版或 Office 365 商務進階版。</span><span class="sxs-lookup"><span data-stu-id="155de-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Office 365 Business or Office 365 Business Premium.</span></span> <span data-ttu-id="155de-108">您可以檢閱什麼隨附[購買 Office 365] 頁面](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)上每個產品。</span><span class="sxs-lookup"><span data-stu-id="155de-108">You can review what comes with each product on the [Buy Office 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="155de-109">購買訂閱時，您會依據貴組織中的人數，指定您所需的「授權」數目。</span><span class="sxs-lookup"><span data-stu-id="155de-109">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="155de-110">完成購買後，您會為人員建立帳戶，並指派授權給每個人。</span><span class="sxs-lookup"><span data-stu-id="155de-110">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="155de-111">為您組織的需求改變時，您可以購買更多授權以容納新的人員，或重新指派授權給其他使用者，當有人離開貴組織。</span><span class="sxs-lookup"><span data-stu-id="155de-111">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="155de-112">如果您有多個訂閱，您可以針對每個訂閱指派授權給人員。</span><span class="sxs-lookup"><span data-stu-id="155de-112">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="155de-113">例如，您的所有使用者無法指派給所有 Office 365 應用程式與服務 Office 365 商務進階版訂閱的一部分時哪些使用者可能也會指派給 Visio Online 透過不同的 Visio 訂閱。</span><span class="sxs-lookup"><span data-stu-id="155de-113">For example, all of your users could be assigned to all Office 365 applications and services as part of an Office 365 Business Premium subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="155de-114">找出誰可以指派授權</span><span class="sxs-lookup"><span data-stu-id="155de-114">Find out who can assign licenses</span></span>

<span data-ttu-id="155de-p105">不同類型的系統管理員根據其角色可以有不同的授權處理方式。下表列出最常用的選項。如需系統管理員角色和權限的完整清單，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="155de-p105">Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="155de-118">**系統管理員角色**</span><span class="sxs-lookup"><span data-stu-id="155de-118">**Admin role**</span></span>|<span data-ttu-id="155de-119">**指派授權**</span><span class="sxs-lookup"><span data-stu-id="155de-119">**Assign a license**</span></span>|<span data-ttu-id="155de-120">**移除授權**</span><span class="sxs-lookup"><span data-stu-id="155de-120">**Remove a license**</span></span>|<span data-ttu-id="155de-121">**購買更多授權**</span><span class="sxs-lookup"><span data-stu-id="155de-121">**Purchase more licenses**</span></span>|<span data-ttu-id="155de-122">**刪除帳戶**</span><span class="sxs-lookup"><span data-stu-id="155de-122">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="155de-123">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="155de-123">Global admin</span></span>  <br/> |<span data-ttu-id="155de-124">是</span><span class="sxs-lookup"><span data-stu-id="155de-124">Yes</span></span>  <br/> |<span data-ttu-id="155de-125">是</span><span class="sxs-lookup"><span data-stu-id="155de-125">Yes</span></span>  <br/> |<span data-ttu-id="155de-126">是</span><span class="sxs-lookup"><span data-stu-id="155de-126">Yes</span></span>  <br/> |<span data-ttu-id="155de-127">是</span><span class="sxs-lookup"><span data-stu-id="155de-127">Yes</span></span>  <br/> |
|<span data-ttu-id="155de-128">計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="155de-128">Billing admin</span></span>  <br/> |<span data-ttu-id="155de-129">否</span><span class="sxs-lookup"><span data-stu-id="155de-129">No</span></span>  <br/> |<span data-ttu-id="155de-130">否</span><span class="sxs-lookup"><span data-stu-id="155de-130">No</span></span>  <br/> |<span data-ttu-id="155de-131">是</span><span class="sxs-lookup"><span data-stu-id="155de-131">Yes</span></span>  <br/> |<span data-ttu-id="155de-132">否</span><span class="sxs-lookup"><span data-stu-id="155de-132">No</span></span>  <br/> |
|<span data-ttu-id="155de-133">使用者管理系統管理員</span><span class="sxs-lookup"><span data-stu-id="155de-133">User management admin</span></span>  <br/> |<span data-ttu-id="155de-134">是</span><span class="sxs-lookup"><span data-stu-id="155de-134">Yes</span></span>  <br/> |<span data-ttu-id="155de-135">是</span><span class="sxs-lookup"><span data-stu-id="155de-135">Yes</span></span>  <br/> |<span data-ttu-id="155de-136">否</span><span class="sxs-lookup"><span data-stu-id="155de-136">No</span></span>  <br/> |<span data-ttu-id="155de-137">是</span><span class="sxs-lookup"><span data-stu-id="155de-137">Yes</span></span>  <br/> |
|<span data-ttu-id="155de-138">服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="155de-138">Service admin</span></span>  <br/> |<span data-ttu-id="155de-139">否</span><span class="sxs-lookup"><span data-stu-id="155de-139">No</span></span>  <br/> |<span data-ttu-id="155de-140">否</span><span class="sxs-lookup"><span data-stu-id="155de-140">No</span></span>  <br/> |<span data-ttu-id="155de-141">否</span><span class="sxs-lookup"><span data-stu-id="155de-141">No</span></span>  <br/> |<span data-ttu-id="155de-142">否</span><span class="sxs-lookup"><span data-stu-id="155de-142">No</span></span>  <br/> |
|<span data-ttu-id="155de-143">密碼系統管理員</span><span class="sxs-lookup"><span data-stu-id="155de-143">Password admin</span></span>  <br/> |<span data-ttu-id="155de-144">否</span><span class="sxs-lookup"><span data-stu-id="155de-144">No</span></span>  <br/> |<span data-ttu-id="155de-145">否</span><span class="sxs-lookup"><span data-stu-id="155de-145">No</span></span>  <br/> |<span data-ttu-id="155de-146">否</span><span class="sxs-lookup"><span data-stu-id="155de-146">No</span></span>  <br/> |<span data-ttu-id="155de-147">否</span><span class="sxs-lookup"><span data-stu-id="155de-147">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="155de-148">了解當您指派授權給某人時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="155de-148">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="155de-149">下表列出當您指派授權給某人時會自動發生的情況：</span><span class="sxs-lookup"><span data-stu-id="155de-149">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="155de-150">**如果訂閱含有此服務**</span><span class="sxs-lookup"><span data-stu-id="155de-150">**If the subscription has this service**</span></span>|<span data-ttu-id="155de-151">**會自動發生以下情況**</span><span class="sxs-lookup"><span data-stu-id="155de-151">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="155de-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="155de-152">Exchange Online</span></span>  <br/> |<span data-ttu-id="155de-153">系統會為該人員建立信箱。</span><span class="sxs-lookup"><span data-stu-id="155de-153">A mailbox is created for that person.</span></span>  <br/> |
|<span data-ttu-id="155de-154">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="155de-154">SharePoint Online</span></span>  <br/> |<span data-ttu-id="155de-155">系統會指派預設 SharePoint Online 小組網站的編輯權限給該人員。</span><span class="sxs-lookup"><span data-stu-id="155de-155">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="155de-156">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="155de-156">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="155de-157">該人員會獲得授權相關功能的存取權限。</span><span class="sxs-lookup"><span data-stu-id="155de-157">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="155de-158">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="155de-158">Office 365 ProPlus</span></span>  <br/> |<span data-ttu-id="155de-159">該人員可在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上下載 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="155de-159">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="155de-160">使用者可以在多少部裝置上安裝 Office？</span><span class="sxs-lookup"><span data-stu-id="155de-160">How many devices can people install Office on?</span></span>

<span data-ttu-id="155de-161">如果您的訂閱包含下列任何產品，每個人員都能在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="155de-161">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="155de-162">Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="155de-162">Office 365 Business</span></span>
    
- <span data-ttu-id="155de-163">Office 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="155de-163">Office 365 Business Premium</span></span>
    
- <span data-ttu-id="155de-164">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="155de-164">Office 365 ProPlus</span></span>
    
- <span data-ttu-id="155de-165">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="155de-165">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="155de-166">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="155de-166">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="155de-167">了解非使用者信箱的授權</span><span class="sxs-lookup"><span data-stu-id="155de-167">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="155de-p106">您不需要指派授權給資源信箱、會議室信箱及共用信箱，除非這些信箱超過其 50 GB 的儲存配額。如需非使用者信箱的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="155de-p106">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="155de-170">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="155de-170">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="155de-171">所有其他 Office 365 方案的 [Exchange Online 中的共用信箱](https://go.microsoft.com/fwlink/p/?linkid=847433) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="155de-171">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Office 365 plans.</span></span> 
    
- [<span data-ttu-id="155de-172">建立及管理會議室信箱</span><span class="sxs-lookup"><span data-stu-id="155de-172">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- <span data-ttu-id="155de-173">[管理設備信箱](https://go.microsoft.com/fwlink/p/?linkid=847435) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="155de-173">[Manage Equipment Mailboxes](https://go.microsoft.com/fwlink/p/?linkid=847435)</span></span>
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="155de-174">管理授權的相關文章</span><span class="sxs-lookup"><span data-stu-id="155de-174">Articles about managing licenses</span></span>

- [<span data-ttu-id="155de-175">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="155de-175">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="155de-176">從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="155de-176">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="155de-177">購買訂閱授權</span><span class="sxs-lookup"><span data-stu-id="155de-177">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="155de-178">購買其他訂閱</span><span class="sxs-lookup"><span data-stu-id="155de-178">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="155de-179">購買或編輯附加元件</span><span class="sxs-lookup"><span data-stu-id="155de-179">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="155de-180">從您的訂閱中移除授權</span><span class="sxs-lookup"><span data-stu-id="155de-180">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- <span data-ttu-id="155de-181">[解決授權衝突](../../admin/manage/resolve-license-conflicts.md) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="155de-181">[Resolve license conflicts](../../admin/manage/resolve-license-conflicts.md)</span></span>
    
- [<span data-ttu-id="155de-182">管理 Yammer 使用者授權</span><span class="sxs-lookup"><span data-stu-id="155de-182">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
