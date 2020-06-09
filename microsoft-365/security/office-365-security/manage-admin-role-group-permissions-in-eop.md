---
title: 管理 EOP 中的角色群組
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 系統管理員可以瞭解如何在 exchange Online Protection 中指派或移除 Exchange 系統管理中心（EAC）中的許可權。
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616511"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="7f2f1-103">在獨立版 EOP 中管理角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="7f2f1-104">在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，您可以使用 Exchange 系統管理中心（EAC）將使用者新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="7f2f1-105">將使用者新增至角色群組，可讓使用者執行特定系統管理員工作的許可權。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="7f2f1-106">您也可以從角色群組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="7f2f1-107">如需角色和角色群組的詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f2f1-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="7f2f1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7f2f1-109">若要開啟 Exchange 系統管理中心（EAC），請參閱[獨立 EOP 中的 Exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7f2f1-110">若要開啟獨立 EOP PowerShell，請參閱[Connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7f2f1-111">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7f2f1-112">具體說來，您需要角色管理角色，預設會指派給 OrganizationManagement （全域系統管理員）角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="7f2f1-113">如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7f2f1-114">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7f2f1-115">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="7f2f1-115">Having problems?</span></span> <span data-ttu-id="7f2f1-116">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="7f2f1-117">使用 EAC 來管理角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="7f2f1-118">使用 EAC 來查看角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="7f2f1-119">在 EAC 中，移至 [**許可權**] [ \> **管理員角色**]。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="7f2f1-120">您組織中的所有角色群組都會列在這裡。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="7f2f1-121">選取角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-121">Select a role group.</span></span> <span data-ttu-id="7f2f1-122">[詳細資料] 窗格會顯示**名稱**、**描述**、**指派的角色**，並由角色群組**進行管理**。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="7f2f1-123">您也可以按一下 [**編輯**編輯圖示] 來查看此資訊 ![ ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="7f2f1-124">使用 EAC 來建立角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="7f2f1-125">當您建立新的角色群組時，您可以自行設定所有設定（在建立群組或之後）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="7f2f1-126">或者，您可以複製現有的角色群組並加以修改。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="7f2f1-127">在 EAC 中，移至 [**許可權**] [系統 \> **管理員角色**]，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="7f2f1-128">**手動建立新的角色群組** \*\*：按一下 [新增\*\* ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="7f2f1-129">**複製現有的角色群組**：選取您要複製的角色群組，然後按一下 [**複製** ![ 複製圖示] ](../../media/ITPro-EAC-CopyIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="7f2f1-130">在出現的 [**新增角色群組**] 視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="7f2f1-131">**名稱**：輸入角色群組的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="7f2f1-132">**描述**：輸入角色群組的選用描述。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="7f2f1-133">**角色**：按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 或 [**移除** ![ ITPro-EAC-RemoveIcon] ](../../media/ITPro-EAC-RemoveIcon.gif) ，以選取或修改指派給角色群組的角色。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="7f2f1-134">**成員**：按一下 [ **add** ![ Add icon] ](../../media/ITPro-EAC-AddIcon.png) 或 [**移除** ![ ITPro-EAC-RemoveIcon] ](../../media/ITPro-EAC-RemoveIcon.gif) 以修改角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="7f2f1-135">完成作業後，按一下 [**儲存**] 以建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="7f2f1-136">使用 EAC 修改角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="7f2f1-137">在 EAC 中，移至 [**許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="7f2f1-138">當您修改角色群組時，當您建立角色群組時，可以使用相同的選項。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="7f2f1-139">您可以：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-139">You can:</span></span>

- <span data-ttu-id="7f2f1-140">變更名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-140">Change the name and description.</span></span>

- <span data-ttu-id="7f2f1-141">新增及移除管理角色（建立或移除角色指派）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="7f2f1-142">新增及移除成員。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-142">Add and remove members.</span></span>

<span data-ttu-id="7f2f1-143">**附注**：部分角色群組（例如，組織管理）限制您可以從群組中移除的角色。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="7f2f1-144">使用 EAC 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="7f2f1-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="7f2f1-145">在 EAC 中，移至 [**許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="7f2f1-146">在開啟的角色群組屬性頁面的 [ **Memebers** ] 區段中，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="7f2f1-147">按一下 [**新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7f2f1-148">在出現的頁面中，尋找 wou 想要加入的使用者，然後按一下 [**載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="7f2f1-149">選取 [使用者]，然後視需要按一下 [**增加->** ] 多次。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="7f2f1-150">完成後，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="7f2f1-151">選取您要移除的使用者，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="7f2f1-152">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7f2f1-153">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="7f2f1-154">使用 EAC 移除角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="7f2f1-155">您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="7f2f1-156">在 EAC 中，移至 [**許可權**] [ \> **管理員角色**]。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="7f2f1-157">選取您要移除的角色群組，然後按一下 [**刪除** ![ 刪除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="7f2f1-158">在出現的確認視窗中，按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="7f2f1-159">使用 PowerShell 管理角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="7f2f1-160">使用獨立 EOP PowerShell 來查看角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="7f2f1-161">若要查看角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="7f2f1-162">此範例會傳回所有角色群組的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="7f2f1-163">此範例會傳回名為 [收件者管理員] 之角色群組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="7f2f1-164">此範例會傳回使用者 Julia 為成員的所有角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="7f2f1-165">您需要為 Julia 使用 DistinguishedName （DN）值，您可以透過執行下列命令來找到： `Get-User -Identity Julia | Format-List DistinguishedName` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="7f2f1-166">如需詳細的語法及參數資訊，請參閱[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="7f2f1-167">使用獨立 EOP PowerShell 建立角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="7f2f1-168">當您建立新的角色群組時，您可以手動設定所有設定（在建立群組或之後）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="7f2f1-169">或者，您可以複製現有的角色群組並加以修改。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="7f2f1-170">若要手動建立新的角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="7f2f1-171">_Roles_參數會使用下列語法，指定要指派給角色群組的管理角色 `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="7f2f1-172">您可以使用**Get-ManagementRole** Cmdlet 來查看可用的角色。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="7f2f1-173">_Members_參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="7f2f1-174">您可以指定使用者、擁有郵件功能的通用安全性群組（Usg）或其他角色群組（安全性主體）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="7f2f1-175">此範例會使用下列設定建立名為「限制收件者管理」的新角色群組：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="7f2f1-176">「郵件收件者」角色會指派給角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="7f2f1-177">使用者 Kim 和聖馬丁會新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="7f2f1-178">若要複製現有的角色群組，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="7f2f1-179">使用下列語法，將您要複製的角色群組儲存在變數中：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="7f2f1-180">使用下列語法建立新的角色群組：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="7f2f1-181">_Members_參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="7f2f1-182">您可以指定使用者、擁有郵件功能的通用安全性群組（Usg）或其他角色群組（安全性主體）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="7f2f1-183">此範例會將組織管理角色群組複製到名為 "有限的組織管理" 的新角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="7f2f1-184">角色群組成員為 Isabelle、Carter 及 Lukas。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="7f2f1-185">如需詳細的語法及參數資訊，請[New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="7f2f1-186">使用獨立 EOP PowerShell 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="7f2f1-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="7f2f1-187">**Add-RoleGroupMember**和**Remove-RoleGroupMember** Cmdlet 會一次新增或移除個別成員。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="7f2f1-188">**Update-RoleGroupMember**資訊清單可以取代或修改現有的成員清單。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="7f2f1-189">角色群組的成員可以是使用者、擁有郵件功能的通用安全性群組（Usg），或其他角色群組（安全性主體）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="7f2f1-190">若要修改角色群組的成員，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="7f2f1-191">若要以您指定的值_取代_現有的現有成員清單，請使用下列語法： `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="7f2f1-192">若要_選擇性地修改_現有的成員清單，請使用下列語法： `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="7f2f1-193">此範例會將「服務台」角色群組的所有目前成員，取代為指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="7f2f1-194">本範例會從服務台角色群組上的成員清單中新增 Daigoro Akai 並移除 Valeria Barrio。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="7f2f1-195">如需詳細的語法及參數資訊，請參閱[Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="7f2f1-196">使用獨立 EOP PowerShell 移除角色群組</span><span class="sxs-lookup"><span data-stu-id="7f2f1-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="7f2f1-197">您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="7f2f1-198">若要移除自訂角色群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="7f2f1-199">本範例移除「訓練系統管理員」角色群組。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="7f2f1-200">如需詳細的語法及參數資訊，請參閱 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7f2f1-201">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="7f2f1-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="7f2f1-202">若要確認您是否已成功複製角色群組，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="7f2f1-203">在 EAC 中，移至 [**許可權**] [系統 \> **管理員角色**]，然後確認角色群組已列出（或未列出）。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="7f2f1-204">選取角色群組，並確認詳細資料窗格中的設定，或按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 以驗證設定。</span><span class="sxs-lookup"><span data-stu-id="7f2f1-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="7f2f1-205">在 Exchange Online PowerShell 中， \<Role Group Name\> 以角色群組的名稱取代，並執行下列命令，以確認角色群組存在（或不存在），並確認設定：</span><span class="sxs-lookup"><span data-stu-id="7f2f1-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
