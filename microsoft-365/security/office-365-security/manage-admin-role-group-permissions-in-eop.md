---
title: 管理 EOP 中的角色群組
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 系統管理員可以瞭解如何在 exchange Online Protection 中指派或移除 Exchange 系統管理中心 (EAC) 中的許可權。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289922"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="d77fc-103">在獨立版 EOP 中管理角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d77fc-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="d77fc-104">**Applies to**</span></span>
-  [<span data-ttu-id="d77fc-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="d77fc-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="d77fc-106">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，您可以使用 Exchange 系統管理中心 (EAC) 將使用者新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="d77fc-107">將使用者新增至角色群組，可讓使用者執行特定系統管理員工作的許可權。</span><span class="sxs-lookup"><span data-stu-id="d77fc-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="d77fc-108">您也可以從角色群組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="d77fc-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="d77fc-109">如需角色和角色群組的詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d77fc-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d77fc-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d77fc-111">若要 (EAC) 開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d77fc-112">若要開啟獨立 EOP PowerShell，請參閱 [Connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d77fc-113">您必須先在 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="d77fc-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="d77fc-114">具體說來，您需要 **角色管理** 角色，其預設會指派給「 **組織管理** 」角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="d77fc-115">如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="d77fc-116">如需適用于本文中程式的鍵盤快速鍵的詳細資訊，請參閱 exchange [Online 中 exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="d77fc-117">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="d77fc-117">Having problems?</span></span> <span data-ttu-id="d77fc-118">在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="d77fc-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="d77fc-119">使用 EAC 來管理角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="d77fc-120">使用 EAC 來查看角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="d77fc-121">在 EAC 中，移至 [ **許可權**] [ \> **管理員角色**]。</span><span class="sxs-lookup"><span data-stu-id="d77fc-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="d77fc-122">您組織中的所有角色群組都會列在這裡。</span><span class="sxs-lookup"><span data-stu-id="d77fc-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="d77fc-123">選取角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-123">Select a role group.</span></span> <span data-ttu-id="d77fc-124">[詳細資料] 窗格會顯示 **名稱**、 **描述**、 **指派的角色**，並由角色群組 **進行管理** 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="d77fc-125">您也可以按一下 [ **編輯** 編輯圖示] 來查看此資訊 ![ ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="d77fc-126">使用 EAC 來建立角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="d77fc-127">當您建立新的角色群組時，您可以在建立群組或) 之後，自行設定所有設定 (。</span><span class="sxs-lookup"><span data-stu-id="d77fc-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="d77fc-128">或者，您可以複製現有的角色群組並加以修改。</span><span class="sxs-lookup"><span data-stu-id="d77fc-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="d77fc-129">在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d77fc-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="d77fc-130">**手動建立新的角色群組** \*\*：按一下 [新增\*\* ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="d77fc-131">**複製現有的角色群組**：選取您要複製的角色群組，然後按一下 [ **複製** ![ 複製圖示] ](../../media/ITPro-EAC-CopyIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="d77fc-132">在出現的 [ **新增角色群組** ] 視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d77fc-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="d77fc-133">**名稱**：輸入角色群組的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="d77fc-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="d77fc-134">**描述**：輸入角色群組的選用描述。</span><span class="sxs-lookup"><span data-stu-id="d77fc-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="d77fc-135">**角色**：按一下 [ **新增** ![ 新增圖示] ](../../media/ITPro-EAC-AddIcon.png) 或 [ **移除** ![ 移除] 圖示 ](../../media/ITPro-EAC-RemoveIcon.gif) ，以選取或修改指派給角色群組的角色。</span><span class="sxs-lookup"><span data-stu-id="d77fc-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="d77fc-136">**成員**：按一下 [ **新增** ![ 新增圖示] ](../../media/ITPro-EAC-AddIcon.png) 或 [ **移除** ![ 移除] 圖示 ](../../media/ITPro-EAC-RemoveIcon.gif) 可修改角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="d77fc-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="d77fc-137">完成作業後，按一下 [ **儲存** ] 以建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="d77fc-138">使用 EAC 修改角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="d77fc-139">在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="d77fc-140">當您修改角色群組時，當您建立角色群組時，可以使用相同的選項。</span><span class="sxs-lookup"><span data-stu-id="d77fc-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="d77fc-141">您可以：</span><span class="sxs-lookup"><span data-stu-id="d77fc-141">You can:</span></span>

- <span data-ttu-id="d77fc-142">變更名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="d77fc-142">Change the name and description.</span></span>

- <span data-ttu-id="d77fc-143">新增或移除管理角色 (建立或移除角色指派) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="d77fc-144">新增及移除成員。</span><span class="sxs-lookup"><span data-stu-id="d77fc-144">Add and remove members.</span></span>

<span data-ttu-id="d77fc-145">**附注**：有些角色群組 (例如，「組織管理」) 會限制您可以從群組中移除的角色。</span><span class="sxs-lookup"><span data-stu-id="d77fc-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="d77fc-146">使用 EAC 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="d77fc-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="d77fc-147">在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="d77fc-148">在開啟的角色群組屬性頁面的 [ **成員** ] 區段中，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d77fc-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="d77fc-149">按一下 [ **新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="d77fc-150">在出現的頁面中，尋找 wou 想要加入的使用者，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="d77fc-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="d77fc-151">選取 [使用者]，然後視需要按一下 [ **增加->** ] 多次。</span><span class="sxs-lookup"><span data-stu-id="d77fc-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="d77fc-152">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="d77fc-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="d77fc-153">選取您要移除的使用者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="d77fc-154">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d77fc-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d77fc-155">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="d77fc-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="d77fc-156">使用 EAC 移除角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="d77fc-157">您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="d77fc-158">在 EAC 中，移至 [ **許可權**] [ \> **管理員角色**]。</span><span class="sxs-lookup"><span data-stu-id="d77fc-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="d77fc-159">選取您要移除的角色群組，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="d77fc-160">在出現的確認視窗中，按一下 [ **是]** 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="d77fc-161">使用 PowerShell 管理角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="d77fc-162">使用獨立 EOP PowerShell 來查看角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="d77fc-163">若要查看角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d77fc-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="d77fc-164">此範例會傳回所有角色群組的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="d77fc-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="d77fc-165">此範例會傳回名為 [收件者管理員] 之角色群組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d77fc-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="d77fc-166">此範例會傳回使用者 Julia 為成員的所有角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="d77fc-167">您需要針對 Julia 使用 DistinguishedName (DN) 值，您可以透過執行下列命令來找到： `Get-User -Identity Julia | Format-List DistinguishedName` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="d77fc-168">如需詳細的語法及參數資訊，請參閱 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="d77fc-169">使用獨立 EOP PowerShell 建立角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="d77fc-170">當您建立新的角色群組時，您可以在建立群組或) 後，以手動方式 (設定所有設定。</span><span class="sxs-lookup"><span data-stu-id="d77fc-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="d77fc-171">或者，您可以複製現有的角色群組並加以修改。</span><span class="sxs-lookup"><span data-stu-id="d77fc-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="d77fc-172">若要手動建立新的角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d77fc-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="d77fc-173">_Roles_ 參數會使用下列語法，指定要指派給角色群組的管理角色 `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="d77fc-174">您可以使用 **Get-ManagementRole** Cmdlet 來查看可用的角色。</span><span class="sxs-lookup"><span data-stu-id="d77fc-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="d77fc-175">_Members_ 參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="d77fc-176">您可以指定使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="d77fc-177">此範例會使用下列設定建立名為「限制收件者管理」的新角色群組：</span><span class="sxs-lookup"><span data-stu-id="d77fc-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="d77fc-178">「郵件收件者」角色會指派給角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="d77fc-179">使用者 Kim 和聖馬丁會新增為成員。</span><span class="sxs-lookup"><span data-stu-id="d77fc-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="d77fc-180">若要複製現有的角色群組，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d77fc-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="d77fc-181">使用下列語法，將您要複製的角色群組儲存在變數中：</span><span class="sxs-lookup"><span data-stu-id="d77fc-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="d77fc-182">使用下列語法建立新的角色群組：</span><span class="sxs-lookup"><span data-stu-id="d77fc-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="d77fc-183">_Members_ 參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="d77fc-184">您可以指定使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="d77fc-185">此範例會將組織管理角色群組複製到名為 "有限的組織管理" 的新角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="d77fc-186">角色群組成員為 Isabelle、Carter 及 Lukas。</span><span class="sxs-lookup"><span data-stu-id="d77fc-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="d77fc-187">如需詳細的語法及參數資訊，請 [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="d77fc-188">使用獨立 EOP PowerShell 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="d77fc-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="d77fc-189">**Add-RoleGroupMember** 和 **Remove-RoleGroupMember** Cmdlet 會一次新增或移除個別成員。</span><span class="sxs-lookup"><span data-stu-id="d77fc-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="d77fc-190">**Update-RoleGroupMember** 資訊清單可以取代或修改現有的成員清單。</span><span class="sxs-lookup"><span data-stu-id="d77fc-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="d77fc-191">角色群組的成員可以是使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="d77fc-192">若要修改角色群組的成員，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d77fc-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="d77fc-193">若要以您指定的值 _取代_ 現有的現有成員清單，請使用下列語法： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="d77fc-194">若要 _選擇性地修改_ 現有的成員清單，請使用下列語法： `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="d77fc-195">此範例會將「服務台」角色群組的所有目前成員，取代為指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="d77fc-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="d77fc-196">本範例會從服務台角色群組上的成員清單中新增 Daigoro Akai 並移除 Valeria Barrio。</span><span class="sxs-lookup"><span data-stu-id="d77fc-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="d77fc-197">如需詳細的語法及參數資訊，請參閱 [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="d77fc-198">使用獨立 EOP PowerShell 移除角色群組</span><span class="sxs-lookup"><span data-stu-id="d77fc-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="d77fc-199">您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="d77fc-200">若要移除自訂角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d77fc-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="d77fc-201">本範例移除「訓練系統管理員」角色群組。</span><span class="sxs-lookup"><span data-stu-id="d77fc-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="d77fc-202">如需詳細的語法及參數資訊，請參閱 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="d77fc-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d77fc-203">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d77fc-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="d77fc-204">若要確認您是否已成功複製角色群組，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d77fc-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="d77fc-205">在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，然後確認角色群組 (列出] 或 [未列出]) 。</span><span class="sxs-lookup"><span data-stu-id="d77fc-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="d77fc-206">選取角色群組，並確認詳細資料窗格中的設定，或按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 以驗證設定。</span><span class="sxs-lookup"><span data-stu-id="d77fc-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="d77fc-207">在 Exchange Online PowerShell 中， \<Role Group Name\> 以角色群組的名稱取代，並執行下列命令，以確認角色群組存在 (或不存在) 並確認設定：</span><span class="sxs-lookup"><span data-stu-id="d77fc-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
