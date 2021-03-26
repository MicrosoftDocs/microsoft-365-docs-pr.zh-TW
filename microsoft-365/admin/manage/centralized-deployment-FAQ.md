---
title: 集中式部署常見問題集
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
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 從 Microsoft 365 系統管理中心，回顧有關集中式部署的常見問題解答。
ms.openlocfilehash: 06e3b7973a209cdf40446c5a9511713d779373b8
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221832"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="a17c8-103">集中式部署常見問題集</span><span class="sxs-lookup"><span data-stu-id="a17c8-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="a17c8-104">集中式部署是 Office 365 系統管理員將 Office 載入) PowerPoint (宏部署到組織內之使用者和群組的建議方法，只要組織符合本文所述的所有使用集中式部署的需求。</span><span class="sxs-lookup"><span data-stu-id="a17c8-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="a17c8-105">如何知道我的組織是否已設定進行集中式部署？</span><span class="sxs-lookup"><span data-stu-id="a17c8-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="a17c8-106">[！注意] 增益集的集中式部署需要使用者使用 Microsoft 365 應用程式的 enterprise (，並使用組織的登入認證來登入 Office) 並擁有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="a17c8-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="a17c8-107">您的訂閱目錄必須是在 Azure Active Directory 中或同盟至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a17c8-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="a17c8-108">僅支援線上信箱的集中式部署。</span><span class="sxs-lookup"><span data-stu-id="a17c8-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="a17c8-109">它不支援部署至內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="a17c8-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="a17c8-110">您可以使用[集中式部署相容性檢查](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)程式   ，判斷您的訂閱是否符合資格。</span><span class="sxs-lookup"><span data-stu-id="a17c8-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="a17c8-111">如何使用集中式部署來瞄準增益集使用者的指派？</span><span class="sxs-lookup"><span data-stu-id="a17c8-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="a17c8-112">集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。</span><span class="sxs-lookup"><span data-stu-id="a17c8-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="a17c8-113">集中式部署可用於最上層群組或沒有父項群組的群組中，但不適用於具有父項群組的嵌套群組或群組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a17c8-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="a17c8-114">集中式部署也是大多數 Azure Active Directory 群組的一部分，包括 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a17c8-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="a17c8-115">最好是使用群組指派，而不是個別的使用者指派，以簡化管理。</span><span class="sxs-lookup"><span data-stu-id="a17c8-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="a17c8-116">如需詳細資訊，請參閱 [使用者和群組指派](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)。</span><span class="sxs-lookup"><span data-stu-id="a17c8-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="a17c8-117">增益集需要多長時間才能顯示給所有使用者？</span><span class="sxs-lookup"><span data-stu-id="a17c8-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="a17c8-118">增益集最多可能需要24小時才能顯示所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a17c8-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="a17c8-119">增益集更新、從開啟或關閉或增益集移除的變更所需的時間也相同。</span><span class="sxs-lookup"><span data-stu-id="a17c8-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="a17c8-120">身為系統管理員，如何管理使用者對組織增益集的存取權？</span><span class="sxs-lookup"><span data-stu-id="a17c8-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="a17c8-121">為了輕鬆將增益集部署至使用者、群組或整個組織，我們建議系統管理員使用集中式部署。</span><span class="sxs-lookup"><span data-stu-id="a17c8-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="a17c8-122">如需管理使用者存取的相關資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="a17c8-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="a17c8-123">在 Outlook) 以外的所有用戶端上關閉 Office 存放區，以防止增益集下載 (</span><span class="sxs-lookup"><span data-stu-id="a17c8-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="a17c8-124">指定系統管理員和使用者可安裝和管理適用於 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="a17c8-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="a17c8-125">集中式部署會為系統管理員提供彈性，以選擇 Outlook 增益集的部署方法？</span><span class="sxs-lookup"><span data-stu-id="a17c8-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="a17c8-126">是。</span><span class="sxs-lookup"><span data-stu-id="a17c8-126">Yes.</span></span> <span data-ttu-id="a17c8-127">集中式部署為系統管理員提供彈性，為增益集部署期間的 Outlook 增益集選擇三種部署方法之一：</span><span class="sxs-lookup"><span data-stu-id="a17c8-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="a17c8-128">**固定 (預設)**  增益集會自動部署至指派的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="a17c8-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="a17c8-129">**可用** 使用者可以在 Outlook 中安裝增益集，方法是選擇 [ **首頁] > > 管理管理] 中取得更多增益集**。</span><span class="sxs-lookup"><span data-stu-id="a17c8-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="a17c8-130">**選用** 增益集會自動部署至指派的使用者，但是可以選擇將它移除。</span><span class="sxs-lookup"><span data-stu-id="a17c8-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="a17c8-131">系統管理員是否可以更新企業營運 (LOB) 增益集？</span><span class="sxs-lookup"><span data-stu-id="a17c8-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="a17c8-132">是。</span><span class="sxs-lookup"><span data-stu-id="a17c8-132">Yes.</span></span> <span data-ttu-id="a17c8-133">系統管理員可以上傳新的資訊清單檔案，以支援系統管理員部署的 LOB 增益集的中繼資料變更。增益集會在下次啟動 Office 應用程式時更新。</span><span class="sxs-lookup"><span data-stu-id="a17c8-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="a17c8-134">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="a17c8-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="a17c8-135">如需詳細資訊，請參閱企業營運營運 [增益集](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a17c8-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="a17c8-136">系統管理員是否可以關閉增益集？</span><span class="sxs-lookup"><span data-stu-id="a17c8-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="a17c8-137">是。</span><span class="sxs-lookup"><span data-stu-id="a17c8-137">Yes.</span></span> <span data-ttu-id="a17c8-138">系統管理員可以開啟或關閉其為所有使用者從 Microsoft 系統管理中心部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="a17c8-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="a17c8-139">如需詳細資訊，請參閱 [增益集狀態](./manage-addins-in-the-admin-center.md#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="a17c8-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="a17c8-140">系統管理員可以刪除或移除增益集嗎？</span><span class="sxs-lookup"><span data-stu-id="a17c8-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="a17c8-141">是。</span><span class="sxs-lookup"><span data-stu-id="a17c8-141">Yes.</span></span> <span data-ttu-id="a17c8-142">系統管理員可以從 Microsoft 系統管理中心刪除其為所有使用者部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="a17c8-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="a17c8-143">如需詳細資訊，請參閱 [刪除增益集](./manage-addins-in-the-admin-center.md#delete-an-add-in)。</span><span class="sxs-lookup"><span data-stu-id="a17c8-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="a17c8-144">使用集中式部署，系統管理員可以從 Office Store 部署付費增益集嗎？</span><span class="sxs-lookup"><span data-stu-id="a17c8-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="a17c8-145">否。</span><span class="sxs-lookup"><span data-stu-id="a17c8-145">No.</span></span> <span data-ttu-id="a17c8-146">您目前無法使用集中式部署從 Office 存放區中部署付費增益集。</span><span class="sxs-lookup"><span data-stu-id="a17c8-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="a17c8-147">我們建議您向外付費增益集的 ISV 開發人員要求資訊清單檔案或 URL。</span><span class="sxs-lookup"><span data-stu-id="a17c8-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="a17c8-148">然後，租使用者系統管理員可以使用集中式部署，將增益集部署為 LOB 增益集。</span><span class="sxs-lookup"><span data-stu-id="a17c8-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="a17c8-149">我需要哪些系統管理員角色來管理組織的增益集？</span><span class="sxs-lookup"><span data-stu-id="a17c8-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="a17c8-150">全域管理員是推薦的角色，具有增益集管理生命週期的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="a17c8-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="a17c8-151">其他系統管理員角色對增益集部署生命週期具有有限的存取權。</span><span class="sxs-lookup"><span data-stu-id="a17c8-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="a17c8-152">如果您是購買 Microsoft 365 for business 訂閱的人員，表示您是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a17c8-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="a17c8-153">您的訂閱隨附一組系統管理員角色，您可以將其指派給組織中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a17c8-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="a17c8-154">每個系統管理員角色會對應至常見商務功能，並讓您組織中的人員能夠在 Microsoft 365 系統管理中心中執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="a17c8-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="a17c8-155">如需詳細資訊，請參閱 [指派系統管理員角色](../add-users/assign-admin-roles.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="a17c8-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 