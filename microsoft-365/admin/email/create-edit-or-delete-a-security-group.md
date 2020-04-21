---
title: 在 Microsoft 365 admin center 中建立、編輯或刪除安全性群組
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 瞭解如何建立、編輯或刪除安全性群組。
ms.openlocfilehash: 689adb46bdec4d4f669482af6b5467fdcf63482c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628876"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="28082-103">在 Microsoft 365 admin center 中建立、編輯或刪除安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="28082-104">在 [Microsoft 365**群組**] 頁面上，您可以建立使用者帳戶群組，供您在 SharePoint ONLINE 和 CRM online 中指派相同的許可權。</span><span class="sxs-lookup"><span data-stu-id="28082-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="28082-105">例如，管理員可以建立安全性群組以授與 SharePoint 網站存取權給特定群組的人員。</span><span class="sxs-lookup"><span data-stu-id="28082-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="28082-106">只有全域及使用者管理管理員擁有建立、編輯或刪除安全性群組的權限；如需管理員角色的詳細資訊，請參閱 [指派管理員角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="28082-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="28082-107">您也可以使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來傳送電子郵件或指派權限給使用者群組，以及使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來授與網站及網站集合權限與存取權給使用者。</span><span class="sxs-lookup"><span data-stu-id="28082-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="28082-108">打算使用網站信箱？</span><span class="sxs-lookup"><span data-stu-id="28082-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="28082-109">透過安全性群組新增而不是個別新增至 SharePoint 網站的所有使用者僅能從 SharePoint 使用網站信箱。</span><span class="sxs-lookup"><span data-stu-id="28082-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="28082-110">這些使用者將無法從 Outlook 存取網站信箱。</span><span class="sxs-lookup"><span data-stu-id="28082-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="28082-111">如需詳細資訊，請參閱[使用 Microsoft 365 群組，而不是網站信箱](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28082-111">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="28082-112">管理系統管理中心的安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="28082-113">新增安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-113">Add a security group</span></span>

1. <span data-ttu-id="28082-114">在 Microsoft 365 系統管理中心中，移至 [**群組** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28082-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="28082-115">在 [**群組**] 頁面上，選取 [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="28082-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="28082-116">在 [**選擇群組類型**] 頁面上，選擇 [**安全性**]。</span><span class="sxs-lookup"><span data-stu-id="28082-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="28082-117">遵循步驟完成群組的建立。</span><span class="sxs-lookup"><span data-stu-id="28082-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="28082-118">新增成員至安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="28082-119">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="28082-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="28082-120">在 [**群組**] 頁面上選取安全性群組名稱，然後在 [**成員**] 索引標籤上，選取 [**全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="28082-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="28082-121">在 [群組] 窗格中，選取 [**新增成員**]，然後從清單中選擇人員，或在**搜尋**方塊中輸入您要新增的人員名稱，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28082-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="28082-122">若要移除成員，請選取其名稱旁邊的 X。</span><span class="sxs-lookup"><span data-stu-id="28082-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="28082-123">在 [**群組**] 頁面上選取安全性群組名稱，然後選取 [**成員**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="28082-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="28082-124">在 [群組] 窗格中，選取 [**新增成員**]，然後從清單中選擇人員，或在**搜尋**方塊中輸入您要新增的人員名稱，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28082-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="28082-125">若要移除成員，請選取其名稱旁邊的 X。</span><span class="sxs-lookup"><span data-stu-id="28082-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="28082-126">在 [**群組**] 頁面上選取安全性群組名稱，然後選取 [**成員**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="28082-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="28082-127">在 [群組] 窗格中，選取 [**新增成員**]，然後從清單中選擇人員，或在**搜尋**方塊中輸入您要新增的人員名稱，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28082-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="28082-128">若要移除成員，請選取其名稱旁邊的 X。</span><span class="sxs-lookup"><span data-stu-id="28082-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="28082-129">編輯安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="28082-130">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="28082-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="28082-131">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28082-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="28082-132">在 [**群組**] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="28082-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="28082-133">在 [設定] 窗格中，選取 **[一般**] 索引標籤或 [**成員**] 索引標籤，即可編輯群組詳細資料或成員。</span><span class="sxs-lookup"><span data-stu-id="28082-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="28082-134">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28082-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="28082-135">在 [**群組**] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="28082-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="28082-136">在 [安全性群組] 窗格中，選取 [**名稱**] 或 [**成員**] 索引標籤旁邊的 [**編輯**]，以編輯群組詳細資料或成員。</span><span class="sxs-lookup"><span data-stu-id="28082-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="28082-137">完成變更之後，請選取 [**儲存** \> **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="28082-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="28082-138">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28082-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="28082-139">在 [**群組**] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="28082-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="28082-140">在 [安全性群組] 窗格中，選取 [**名稱**] 或 [**成員**] 索引標籤旁邊的 [**編輯**]，以編輯群組詳細資料或成員。</span><span class="sxs-lookup"><span data-stu-id="28082-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="28082-141">完成變更之後，請選取 [**儲存** > **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="28082-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="28082-142">刪除安全性群組</span><span class="sxs-lookup"><span data-stu-id="28082-142">Delete a security group</span></span>

1. <span data-ttu-id="28082-143">在系統管理中心中，移至 [**群組** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28082-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="28082-144">在 [**群組**] 頁面上，選取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="28082-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="28082-145">選取 [**刪除群組**（wasetbin 圖示）]，然後選取 [**刪除**] 加以確認。</span><span class="sxs-lookup"><span data-stu-id="28082-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="28082-146">一旦刪除群組，請選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="28082-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="28082-147">Exchange Online 和 SharePoint Online 中的群組</span><span class="sxs-lookup"><span data-stu-id="28082-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="28082-148">如果您想要建立使用者群組，以便同時將電子郵件傳送給他們，您可以移至「**管理** \> **Exchange** \> **Recipients** \>收件者」**群組**，在 Exchange 系統管理中心中執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="28082-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="28082-149">接下來， \*\* \*\* ![選取 [](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)新增]，然後選取您要建立的群組類型：</span><span class="sxs-lookup"><span data-stu-id="28082-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="28082-150">**通訊群組**：用於發送訊息至使用者群組。</span><span class="sxs-lookup"><span data-stu-id="28082-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="28082-151">也稱為*啟用郵件功能的通訊群組*或*通訊群組清單*。</span><span class="sxs-lookup"><span data-stu-id="28082-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="28082-152">如需詳細資訊，請參閱 [管理通訊群組](https://technet.microsoft.com/library/bb124513.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28082-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="28082-153">**安全性群組**：可以用來將訊息發送至使用者群組，或是用於授與資源的存取權限。</span><span class="sxs-lookup"><span data-stu-id="28082-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="28082-154">這個群組又稱為*啟用郵件功能的安全性群組*。</span><span class="sxs-lookup"><span data-stu-id="28082-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="28082-155">如需詳細資訊，請參閱[管理擁有郵件功能的安全性群組](https://technet.microsoft.com/library/bb123521.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28082-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="28082-156">**動態通訊群組**：每次傳送郵件時，此通訊群組類型就會根據您所定義的篩選和條件重新計算收件者清單。</span><span class="sxs-lookup"><span data-stu-id="28082-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="28082-157">如需詳細資訊，請參閱[管理動態通訊群組](https://technet.microsoft.com/library/bb123722.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28082-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="28082-158">在 Exchange 系統管理中心建立通訊群組和擁有郵件功能的安全性群組之後，其名稱和使用者清單會出現在 [**安全性群組**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="28082-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="28082-159">您可以在這兩個位置刪除這些群組，但是僅可在 Exchange 系統管理中心對這些群組進行編輯。</span><span class="sxs-lookup"><span data-stu-id="28082-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="28082-160">動態通訊群組不會顯示在 [**安全性群組**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="28082-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="28082-161">SharePoint 群組會在您建立網站集合時自動建立。</span><span class="sxs-lookup"><span data-stu-id="28082-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="28082-162">預設群組會使用 SharePoint 中的預設權限等級 (有時稱為 SharePoint 角色) 來授與使用者權限與存取權。</span><span class="sxs-lookup"><span data-stu-id="28082-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="28082-163">如需詳細資訊，請參閱[Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28082-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="28082-164">安全性群組與我在 SharePoint 中建立的安全性群組有何不同？</span><span class="sxs-lookup"><span data-stu-id="28082-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="28082-165">安全性群組可以與 SharePoint、Exchange、MDM、Windows 等搭配使用。</span><span class="sxs-lookup"><span data-stu-id="28082-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="28082-166">您在 SharePoint 中所建立的安全性群組只能透過該 SharePoint 網站集合加以識別。</span><span class="sxs-lookup"><span data-stu-id="28082-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="28082-167">我需要使用安全性群組來保護組織的安全嗎？</span><span class="sxs-lookup"><span data-stu-id="28082-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="28082-168">否。</span><span class="sxs-lookup"><span data-stu-id="28082-168">No.</span></span> <span data-ttu-id="28082-169">這只是另一種可管理組織安全性的方式。</span><span class="sxs-lookup"><span data-stu-id="28082-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="28082-170">您可以永遠授與使用者許可權，並個別地存取網站。</span><span class="sxs-lookup"><span data-stu-id="28082-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="28082-171">不過，使用安全性群組，您可以輕鬆管理較大的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="28082-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="28082-172">我可以將電子郵件傳送至安全性群組嗎？</span><span class="sxs-lookup"><span data-stu-id="28082-172">Can I send email to a security group?</span></span>

<span data-ttu-id="28082-173">是。</span><span class="sxs-lookup"><span data-stu-id="28082-173">Yes.</span></span> <span data-ttu-id="28082-174">不過，如果您想要使用群組進行電子郵件及共同作業，建議您改為[建立 Microsoft 365 群組](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="28082-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
