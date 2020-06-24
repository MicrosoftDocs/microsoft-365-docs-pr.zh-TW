---
title: 瞭解 Microsoft 365 for business 中的訂閱與授權
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
description: '深入瞭解 Microsoft 365 for business 中的訂閱與授權，並知道誰可以指派授權，以及當您指派授權給某人時會發生什麼情況。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844677"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="f582d-103">瞭解 Microsoft 365 for business 中的訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="f582d-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="f582d-104">本文說明訂閱與授權之間的關係，並提供其他有關[誰可以指派授權](#find-out-who-can-assign-licenses)的資訊，[瞭解當您指派授權給某人時所發生的情況](#understand-what-happens-when-you-assign-a-license-to-someone)，以及[人員可以在哪個裝置上安裝 Office](#how-many-devices-can-people-install-office-on)。</span><span class="sxs-lookup"><span data-stu-id="f582d-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="f582d-105">此外，它也包含[瞭解非使用者信箱之授權的](#understand-licenses-for-non-user-mailboxes)連結，以及[管理授權的相關文章](#articles-about-managing-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f582d-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="f582d-106">當您為商務用 Microsoft 365 購買訂閱時，您會註冊一組應用程式和服務，以每月或每年的頻率支付。</span><span class="sxs-lookup"><span data-stu-id="f582d-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="f582d-107">您在訂閱中所收到的應用程式和服務，取決於您購買的是哪一種產品，例如 Microsoft 365 Apps for business Standard 或 Microsoft 365 Business Standard。</span><span class="sxs-lookup"><span data-stu-id="f582d-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="f582d-108">您可以在「[購買 Microsoft 365」頁面](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)上查看每個產品隨附的功能。</span><span class="sxs-lookup"><span data-stu-id="f582d-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="f582d-109">您可以在適用于中小型[企業的 Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)中查看不同的授權選項</span><span class="sxs-lookup"><span data-stu-id="f582d-109">You can review different Licensing options available in [Microsoft 365 for small and medium-sized businesses](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)</span></span>

<span data-ttu-id="f582d-110">購買訂閱時，您會依據貴組織中的人數，指定您所需的「授權」數目。</span><span class="sxs-lookup"><span data-stu-id="f582d-110">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="f582d-111">完成購買後，您會為人員建立帳戶，並指派授權給每個人。</span><span class="sxs-lookup"><span data-stu-id="f582d-111">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="f582d-112">當您的組織需要變更時，您可以購買更多授權，以容納新人員，或在某人離開您的組織時，將授權重新指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="f582d-112">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="f582d-113">如果您有多個訂閱，您可以針對每個訂閱指派授權給人員。</span><span class="sxs-lookup"><span data-stu-id="f582d-113">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="f582d-114">例如，您的所有使用者都可以指派給所有 Microsoft 365 應用程式和服務做為 Microsoft 365 商務標準訂閱的一部分，而使用者的子集也可以透過個別的 Visio 訂閱指派給 Visio Online。</span><span class="sxs-lookup"><span data-stu-id="f582d-114">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="f582d-115">找出誰可以指派授權</span><span class="sxs-lookup"><span data-stu-id="f582d-115">Find out who can assign licenses</span></span>

<span data-ttu-id="f582d-116">Different types of admins can work with licenses in different ways, depending on their roles.</span><span class="sxs-lookup"><span data-stu-id="f582d-116">Different types of admins can work with licenses in different ways, depending on their roles.</span></span> <span data-ttu-id="f582d-117">The following table lists the most common options.</span><span class="sxs-lookup"><span data-stu-id="f582d-117">The following table lists the most common options.</span></span> <span data-ttu-id="f582d-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f582d-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="f582d-119">**系統管理員角色**</span><span class="sxs-lookup"><span data-stu-id="f582d-119">**Admin role**</span></span>|<span data-ttu-id="f582d-120">**指派授權**</span><span class="sxs-lookup"><span data-stu-id="f582d-120">**Assign a license**</span></span>|<span data-ttu-id="f582d-121">**移除授權**</span><span class="sxs-lookup"><span data-stu-id="f582d-121">**Remove a license**</span></span>|<span data-ttu-id="f582d-122">**購買更多授權**</span><span class="sxs-lookup"><span data-stu-id="f582d-122">**Purchase more licenses**</span></span>|<span data-ttu-id="f582d-123">**刪除帳戶**</span><span class="sxs-lookup"><span data-stu-id="f582d-123">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f582d-124">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f582d-124">Global admin</span></span>  <br/> |<span data-ttu-id="f582d-125">是</span><span class="sxs-lookup"><span data-stu-id="f582d-125">Yes</span></span>  <br/> |<span data-ttu-id="f582d-126">是</span><span class="sxs-lookup"><span data-stu-id="f582d-126">Yes</span></span>  <br/> |<span data-ttu-id="f582d-127">是</span><span class="sxs-lookup"><span data-stu-id="f582d-127">Yes</span></span>  <br/> |<span data-ttu-id="f582d-128">是</span><span class="sxs-lookup"><span data-stu-id="f582d-128">Yes</span></span>  <br/> |
|<span data-ttu-id="f582d-129">計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="f582d-129">Billing admin</span></span>  <br/> |<span data-ttu-id="f582d-130">否</span><span class="sxs-lookup"><span data-stu-id="f582d-130">No</span></span>  <br/> |<span data-ttu-id="f582d-131">否</span><span class="sxs-lookup"><span data-stu-id="f582d-131">No</span></span>  <br/> |<span data-ttu-id="f582d-132">是</span><span class="sxs-lookup"><span data-stu-id="f582d-132">Yes</span></span>  <br/> |<span data-ttu-id="f582d-133">否</span><span class="sxs-lookup"><span data-stu-id="f582d-133">No</span></span>  <br/> |
|<span data-ttu-id="f582d-134">使用者管理系統管理員</span><span class="sxs-lookup"><span data-stu-id="f582d-134">User management admin</span></span>  <br/> |<span data-ttu-id="f582d-135">是</span><span class="sxs-lookup"><span data-stu-id="f582d-135">Yes</span></span>  <br/> |<span data-ttu-id="f582d-136">是</span><span class="sxs-lookup"><span data-stu-id="f582d-136">Yes</span></span>  <br/> |<span data-ttu-id="f582d-137">否</span><span class="sxs-lookup"><span data-stu-id="f582d-137">No</span></span>  <br/> |<span data-ttu-id="f582d-138">是</span><span class="sxs-lookup"><span data-stu-id="f582d-138">Yes</span></span>  <br/> |
|<span data-ttu-id="f582d-139">服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="f582d-139">Service admin</span></span>  <br/> |<span data-ttu-id="f582d-140">否</span><span class="sxs-lookup"><span data-stu-id="f582d-140">No</span></span>  <br/> |<span data-ttu-id="f582d-141">否</span><span class="sxs-lookup"><span data-stu-id="f582d-141">No</span></span>  <br/> |<span data-ttu-id="f582d-142">否</span><span class="sxs-lookup"><span data-stu-id="f582d-142">No</span></span>  <br/> |<span data-ttu-id="f582d-143">否</span><span class="sxs-lookup"><span data-stu-id="f582d-143">No</span></span>  <br/> |
|<span data-ttu-id="f582d-144">密碼系統管理員</span><span class="sxs-lookup"><span data-stu-id="f582d-144">Password admin</span></span>  <br/> |<span data-ttu-id="f582d-145">否</span><span class="sxs-lookup"><span data-stu-id="f582d-145">No</span></span>  <br/> |<span data-ttu-id="f582d-146">否</span><span class="sxs-lookup"><span data-stu-id="f582d-146">No</span></span>  <br/> |<span data-ttu-id="f582d-147">否</span><span class="sxs-lookup"><span data-stu-id="f582d-147">No</span></span>  <br/> |<span data-ttu-id="f582d-148">否</span><span class="sxs-lookup"><span data-stu-id="f582d-148">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="f582d-149">了解當您指派授權給某人時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="f582d-149">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="f582d-150">下表列出當您指派授權給某人時會自動發生的情況：</span><span class="sxs-lookup"><span data-stu-id="f582d-150">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="f582d-151">**如果訂閱含有此服務**</span><span class="sxs-lookup"><span data-stu-id="f582d-151">**If the subscription has this service**</span></span>|<span data-ttu-id="f582d-152">**會自動發生以下情況**</span><span class="sxs-lookup"><span data-stu-id="f582d-152">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f582d-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f582d-153">Exchange Online</span></span>  <br/> |<span data-ttu-id="f582d-154">系統會為該人員建立信箱。</span><span class="sxs-lookup"><span data-stu-id="f582d-154">A mailbox is created for that person.</span></span>  <br/> <span data-ttu-id="f582d-155">若要瞭解此工作完成的 SLA，請參閱「[設定 ...」Microsoft 365 系統管理中心中的郵件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f582d-155">To learn about the SLA for this task to be completed, see ["Setting up..." messages in the Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).</span></span> |
|<span data-ttu-id="f582d-156">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f582d-156">SharePoint Online</span></span>  <br/> |<span data-ttu-id="f582d-157">系統會指派預設 SharePoint Online 小組網站的編輯權限給該人員。</span><span class="sxs-lookup"><span data-stu-id="f582d-157">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="f582d-158">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="f582d-158">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="f582d-159">該人員會獲得授權相關功能的存取權限。</span><span class="sxs-lookup"><span data-stu-id="f582d-159">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="f582d-160">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="f582d-160">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="f582d-161">該人員可在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上下載 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="f582d-161">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="f582d-162">使用者可以在多少部裝置上安裝 Office？</span><span class="sxs-lookup"><span data-stu-id="f582d-162">How many devices can people install Office on?</span></span>

<span data-ttu-id="f582d-163">如果您的訂閱包含下列任何產品，每個人員都能在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="f582d-163">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="f582d-164">Microsoft 365 Apps 商務版</span><span class="sxs-lookup"><span data-stu-id="f582d-164">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="f582d-165">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="f582d-165">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="f582d-166">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="f582d-166">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="f582d-167">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="f582d-167">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="f582d-168">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="f582d-168">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="f582d-169">了解非使用者信箱的授權</span><span class="sxs-lookup"><span data-stu-id="f582d-169">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="f582d-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="f582d-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span></span> <span data-ttu-id="f582d-171">For more about non-user mailboxes, see the following articles:</span><span class="sxs-lookup"><span data-stu-id="f582d-171">For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="f582d-172">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="f582d-172">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="f582d-173">[Exchange Online 中的共用信箱](https://go.microsoft.com/fwlink/p/?linkid=847433)，適用于所有其他 Microsoft 365 方案。</span><span class="sxs-lookup"><span data-stu-id="f582d-173">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="f582d-174">建立及管理會議室信箱</span><span class="sxs-lookup"><span data-stu-id="f582d-174">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- <span data-ttu-id="f582d-175">[管理設備信箱](https://go.microsoft.com/fwlink/p/?linkid=847435) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f582d-175">[Manage Equipment Mailboxes](https://go.microsoft.com/fwlink/p/?linkid=847435)</span></span>
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="f582d-176">管理授權的相關文章</span><span class="sxs-lookup"><span data-stu-id="f582d-176">Articles about managing licenses</span></span>

- [<span data-ttu-id="f582d-177">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f582d-177">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="f582d-178">從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="f582d-178">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="f582d-179">購買訂閱授權</span><span class="sxs-lookup"><span data-stu-id="f582d-179">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="f582d-180">購買其他訂閱</span><span class="sxs-lookup"><span data-stu-id="f582d-180">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="f582d-181">購買或編輯附加元件</span><span class="sxs-lookup"><span data-stu-id="f582d-181">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="f582d-182">從您的訂閱中移除授權</span><span class="sxs-lookup"><span data-stu-id="f582d-182">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- <span data-ttu-id="f582d-183">[解決授權衝突](../../admin/manage/resolve-license-conflicts.md) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f582d-183">[Resolve license conflicts](../../admin/manage/resolve-license-conflicts.md)</span></span>
    
- [<span data-ttu-id="f582d-184">管理 Yammer 使用者授權</span><span class="sxs-lookup"><span data-stu-id="f582d-184">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
