---
title: 在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組
f1.keywords:
- NOCSH
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
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 瞭解如何建立、編輯或刪除安全性群組。
ms.openlocfilehash: 8f76b5fa803ea43e53e89cf6479eb7572a2857c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537592"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="77a9c-103">在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="77a9c-104">在 [Microsoft 365 **群組**] 頁面上，您可以建立使用者帳戶群組，供您在 SharePoint 線上和 CRM online 中指派相同的許可權。</span><span class="sxs-lookup"><span data-stu-id="77a9c-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="77a9c-105">例如，管理員可以建立安全性群組以授與 SharePoint 網站存取權給特定群組的人員。</span><span class="sxs-lookup"><span data-stu-id="77a9c-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="77a9c-106">只有全域及使用者管理管理員擁有建立、編輯或刪除安全性群組的權限；如需管理員角色的詳細資訊，請參閱 [指派管理員角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="77a9c-107">您也可以使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來傳送電子郵件或指派權限給使用者群組，以及使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來授與網站及網站集合權限與存取權給使用者。</span><span class="sxs-lookup"><span data-stu-id="77a9c-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="77a9c-108">打算使用網站信箱？</span><span class="sxs-lookup"><span data-stu-id="77a9c-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="77a9c-109">透過安全性群組新增而不是個別新增至 SharePoint 網站的所有使用者僅能從 SharePoint 使用網站信箱。</span><span class="sxs-lookup"><span data-stu-id="77a9c-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="77a9c-110">這些使用者將無法從 Outlook 存取網站信箱。</span><span class="sxs-lookup"><span data-stu-id="77a9c-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="77a9c-111">如需詳細資訊，請參閱[使用 Microsoft 365 群組，而不是網站信箱](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="77a9c-112">管理系統管理中心的安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="77a9c-113">新增安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-113">Add a security group</span></span>

1. <span data-ttu-id="77a9c-114">在 Microsoft 365 系統管理中心，移至 [**群組**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="77a9c-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="77a9c-115">在 [ **群組** ] 頁面上，選取 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="77a9c-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="77a9c-116">在 [ **選擇群組類型** ] 頁面上，選擇 [ **安全性**]。</span><span class="sxs-lookup"><span data-stu-id="77a9c-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="77a9c-117">遵循步驟完成群組的建立。</span><span class="sxs-lookup"><span data-stu-id="77a9c-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="77a9c-118">新增成員至安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="77a9c-119">在 [ **群組** ] 頁面上選取安全性群組名稱，然後在 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="77a9c-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="77a9c-120">在 [群組] 窗格中，選取 [ **新增成員** ]，然後從清單中選擇人員，或在 **搜尋** 方塊中輸入您要新增的人員名稱，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="77a9c-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="77a9c-121">若要移除成員，請選取其名稱旁邊的 X。</span><span class="sxs-lookup"><span data-stu-id="77a9c-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="77a9c-122">編輯安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-122">Edit a security group</span></span>

1. <span data-ttu-id="77a9c-123">在系統管理中心中，移至 [ **群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="77a9c-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="77a9c-124">在 [ **群組** ] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="77a9c-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77a9c-125">在 [設定] 窗格中，選取 **[一般** ] 索引標籤或 [ **成員** ] 索引標籤，即可編輯群組詳細資料或成員。</span><span class="sxs-lookup"><span data-stu-id="77a9c-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="77a9c-126">刪除安全性群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-126">Delete a security group</span></span>

1. <span data-ttu-id="77a9c-127">在系統管理中心中，移至 [**群組**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="77a9c-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="77a9c-128">在 [ **群組** ] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="77a9c-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77a9c-129">選取 [ **刪除群組** (wasetbin 圖示) ]，然後選取 [ **刪除**] 加以確認。</span><span class="sxs-lookup"><span data-stu-id="77a9c-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="77a9c-130">一旦刪除群組，請選取 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="77a9c-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="77a9c-131">Exchange Online 和 SharePoint Online 中的群組</span><span class="sxs-lookup"><span data-stu-id="77a9c-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="77a9c-132">如果您想要建立使用者群組，以便同時將電子郵件傳送給他們，您可以移至 [**管理** \> **Exchange** 收件者 \>  \> **群組**]，以在 Exchange 系統管理中心進行。</span><span class="sxs-lookup"><span data-stu-id="77a9c-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="77a9c-133">接下來，選取 [**新增**] ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) ，然後選取您要建立的群組類型：</span><span class="sxs-lookup"><span data-stu-id="77a9c-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="77a9c-134">**通訊群組**：用於發送訊息至使用者群組。</span><span class="sxs-lookup"><span data-stu-id="77a9c-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="77a9c-135">也稱為  *啟用郵件功能的通訊群組* 或  *通訊群組清單*。</span><span class="sxs-lookup"><span data-stu-id="77a9c-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="77a9c-136">如需詳細資訊，請參閱 [管理通訊群組](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="77a9c-137">**安全性群組**：可以用來將訊息發送至使用者群組，或是用於授與資源的存取權限。</span><span class="sxs-lookup"><span data-stu-id="77a9c-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="77a9c-138">這個群組又稱為 *啟用郵件功能的安全性群組*。</span><span class="sxs-lookup"><span data-stu-id="77a9c-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="77a9c-139">如需詳細資訊，請參閱 [管理擁有郵件功能的安全性群組](/Exchange/recipients/mail-enabled-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="77a9c-140">**動態通訊群組**：每次傳送郵件時，此通訊群組類型就會根據您所定義的篩選和條件重新計算收件者清單。</span><span class="sxs-lookup"><span data-stu-id="77a9c-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="77a9c-141">如需詳細資訊，請參閱 [管理動態通訊群組](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="77a9c-142">在 Exchange 系統管理中心建立通訊群組和擁有郵件功能的安全性群組之後，其名稱和使用者清單會出現在 [**安全性群組**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="77a9c-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="77a9c-143">您可以在這兩個位置刪除這些群組，但是僅可在 Exchange 系統管理中心對這些群組進行編輯。</span><span class="sxs-lookup"><span data-stu-id="77a9c-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="77a9c-144">動態通訊群組不會顯示在 [ **安全性群組** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="77a9c-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="77a9c-145">SharePoint 群組會在您建立網站集合時自動建立。</span><span class="sxs-lookup"><span data-stu-id="77a9c-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="77a9c-146">預設群組會使用 SharePoint 中的預設權限等級 (有時稱為 SharePoint 角色) 來授與使用者權限與存取權。</span><span class="sxs-lookup"><span data-stu-id="77a9c-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="77a9c-147">如需詳細資訊，請參閱[Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="77a9c-148">安全性群組與我在 SharePoint 中建立的安全性群組有何不同？</span><span class="sxs-lookup"><span data-stu-id="77a9c-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="77a9c-149">安全性群組可以與 SharePoint、Exchange、MDM、Windows 等搭配使用。</span><span class="sxs-lookup"><span data-stu-id="77a9c-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="77a9c-150">您在 SharePoint 中所建立的安全性群組只能透過該 SharePoint 網站集合加以識別。</span><span class="sxs-lookup"><span data-stu-id="77a9c-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="77a9c-151">我需要使用安全性群組來保護組織的安全嗎？</span><span class="sxs-lookup"><span data-stu-id="77a9c-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="77a9c-152">否。</span><span class="sxs-lookup"><span data-stu-id="77a9c-152">No.</span></span> <span data-ttu-id="77a9c-153">這只是另一種可管理組織安全性的方式。</span><span class="sxs-lookup"><span data-stu-id="77a9c-153">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="77a9c-154">您可以永遠授與使用者許可權，並個別地存取網站。</span><span class="sxs-lookup"><span data-stu-id="77a9c-154">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="77a9c-155">不過，使用安全性群組，您可以輕鬆管理較大的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="77a9c-155">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="77a9c-156">我可以將電子郵件傳送至安全性群組嗎？</span><span class="sxs-lookup"><span data-stu-id="77a9c-156">Can I send email to a security group?</span></span>

<span data-ttu-id="77a9c-157">是。</span><span class="sxs-lookup"><span data-stu-id="77a9c-157">Yes.</span></span> <span data-ttu-id="77a9c-158">不過，如果您想要使用群組進行電子郵件及共同作業，建議您改為[建立 Microsoft 365 群組](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="77a9c-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
