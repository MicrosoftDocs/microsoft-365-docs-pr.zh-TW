---
title: 管理 EOP 中的群組
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何在 Exchange Online Protection （EOP）中建立及管理 Exchange 組織的擁有郵件功能的群組。
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034399"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="02386-103">管理 EOP 中的群組</span><span class="sxs-lookup"><span data-stu-id="02386-103">Manage groups in EOP</span></span>

 <span data-ttu-id="02386-104">您可以使用 Exchange Online Protection （EOP）為 Exchange 組織建立擁有郵件功能的群組。</span><span class="sxs-lookup"><span data-stu-id="02386-104">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="02386-105">您也可以使用 EOP 來定義或更新組屬性，以指定成員資格、電子郵件地址及其他群組的群組內容。</span><span class="sxs-lookup"><span data-stu-id="02386-105">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="02386-106">您可以根據您的需求，建立通訊群組和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="02386-106">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="02386-107">您可以使用 Exchange 系統管理中心（EAC）或透過遠端 Windows PowerShell 建立這些群組。</span><span class="sxs-lookup"><span data-stu-id="02386-107">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="02386-108">擁有郵件功能的群組類型</span><span class="sxs-lookup"><span data-stu-id="02386-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="02386-109">您可以為您的 Exchange 組織建立兩種類型的群組：</span><span class="sxs-lookup"><span data-stu-id="02386-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="02386-110">通訊群組是電子郵件使用者的集合（如小組或其他的特別小組），其需要接收或傳送有關感興趣之共同領域的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="02386-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="02386-111">通訊群組專用於散佈電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="02386-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="02386-112">在 EOP 中，通訊群組是指任何擁有郵件功能的群組，不論其是否有安全性內容。</span><span class="sxs-lookup"><span data-stu-id="02386-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="02386-113">安全性群組是需要系統管理員角色存取許可權之電子郵件使用者的集合。</span><span class="sxs-lookup"><span data-stu-id="02386-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="02386-114">例如，您可能想要授與特定群組的使用者系統管理員角色許可權，讓他們可以設定反垃圾郵件和反惡意程式碼設定。</span><span class="sxs-lookup"><span data-stu-id="02386-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02386-115">根據預設，所有擁有郵件功能的新安全性群組都需要驗證所有寄件者。</span><span class="sxs-lookup"><span data-stu-id="02386-115">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="02386-116">這可防止外部寄件者傳送郵件給擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="02386-116">This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="02386-117">開始之前</span><span class="sxs-lookup"><span data-stu-id="02386-117">Before you begin</span></span>

- <span data-ttu-id="02386-118">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="02386-118">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="02386-119">若要查看您需要的許可權，請參閱[EOP 中的功能許可權](feature-permissions-in-eop.md)主題中的「通訊群組和安全性群組」專案。</span><span class="sxs-lookup"><span data-stu-id="02386-119">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="02386-120">若要開啟 Exchange 系統管理中心，請參閱 exchange [Online Protection 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="02386-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="02386-121">請注意，使用 Exchange Online Protection PowerShell Cmdlet 來建立及管理群組時，您可能會遇到節流。</span><span class="sxs-lookup"><span data-stu-id="02386-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="02386-122">本主題中的 PowerShell 程式使用批次處理方法，可導致幾分鐘的傳播延遲，然後才會顯示命令的結果。</span><span class="sxs-lookup"><span data-stu-id="02386-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="02386-123">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="02386-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="02386-124">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="02386-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="02386-125">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="02386-125">Having problems?</span></span> <span data-ttu-id="02386-126">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="02386-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="02386-127">在 EAC 中建立群組</span><span class="sxs-lookup"><span data-stu-id="02386-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="02386-128">在 EAC 中，**移至** \> [收件者**群組**]。</span><span class="sxs-lookup"><span data-stu-id="02386-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="02386-129">依您的需求](../../media/ITPro-EAC-AddIcon.gif)而定，按一下 [**新增新增** ![圖示]，然後按一下 [**通訊群組**或**安全性群組**]。</span><span class="sxs-lookup"><span data-stu-id="02386-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="02386-130">在 [**新增通訊群組**] 或 [**新增安全性群組**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="02386-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="02386-131">**顯示名稱**：輸入貴組織獨有的顯示名稱，並有意義的 EOP 使用者。</span><span class="sxs-lookup"><span data-stu-id="02386-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="02386-132">顯示名稱是必要項目。</span><span class="sxs-lookup"><span data-stu-id="02386-132">The display name is required.</span></span>

   - <span data-ttu-id="02386-133">**別名**：輸入最多64個字元的群組別名，您的組織是唯一的。</span><span class="sxs-lookup"><span data-stu-id="02386-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="02386-134">EOP 使用者在 [To：] （電子郵件）行中輸入別名，別名會解析為群組的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="02386-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="02386-135">如果您變更別名，群組的主要 SMTP 位址也會變更，並會包含新的別名。</span><span class="sxs-lookup"><span data-stu-id="02386-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="02386-136">別名為必要項目。</span><span class="sxs-lookup"><span data-stu-id="02386-136">The alias is required.</span></span>

   - <span data-ttu-id="02386-137">**描述**：輸入群組的描述，以供人員瞭解群組的用途。</span><span class="sxs-lookup"><span data-stu-id="02386-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="02386-138">**擁有**者：根據預設，建立群組的人員是擁有者。</span><span class="sxs-lookup"><span data-stu-id="02386-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="02386-139">您**可以選擇 [新增** ![加入圖示](../../media/ITPro-EAC-AddIcon.gif)] 來新增擁有者。</span><span class="sxs-lookup"><span data-stu-id="02386-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="02386-140">所有群組都必須至少一個擁有者。</span><span class="sxs-lookup"><span data-stu-id="02386-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="02386-141">擁有者不一定必須是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="02386-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="02386-142">[**成員**]：使用此區段可新增群組成員，並指定使用者加入或離開群組時是否需要核准。</span><span class="sxs-lookup"><span data-stu-id="02386-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="02386-143">若要將成員新增至群組， **Add** ![請按一下 [](../../media/ITPro-EAC-AddIcon.gif)新增新增] 圖示。</span><span class="sxs-lookup"><span data-stu-id="02386-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="02386-144">按一下 **[確定]** 回到原始頁面。</span><span class="sxs-lookup"><span data-stu-id="02386-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="02386-145">完成後，按一下 [**儲存**] 以建立群組。</span><span class="sxs-lookup"><span data-stu-id="02386-145">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="02386-146">新的群組應該出現在群組清單中。</span><span class="sxs-lookup"><span data-stu-id="02386-146">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="02386-147">編輯或移除 EAC 中的群組</span><span class="sxs-lookup"><span data-stu-id="02386-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="02386-148">In the EAC, navigate to **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="02386-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="02386-149">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="02386-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="02386-150">若要編輯群組：在群組清單中，按一下您要查看或變更的群組，然後按一下 [**編輯** ![編輯圖示](../../media/ITPro-EAC-EditIcon.gif)]。</span><span class="sxs-lookup"><span data-stu-id="02386-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="02386-151">您可以更新一般設定、新增或移除群組擁有者，並視需要新增或移除群組成員。</span><span class="sxs-lookup"><span data-stu-id="02386-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="02386-152">若要移除群組：選取群組，然後按一下 [**移除** ![移除](../../media/ITPro-EAC-RemoveIcon.gif)圖示]。</span><span class="sxs-lookup"><span data-stu-id="02386-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="02386-153">完成變更之後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="02386-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="02386-154">使用遠端 Windows PowerShell 建立、編輯或移除群組</span><span class="sxs-lookup"><span data-stu-id="02386-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="02386-155">本節提供在 Exchange Online Protection PowerShell 中建立群組和變更其屬性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="02386-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="02386-156">它也顯示如何移除現有的群組。</span><span class="sxs-lookup"><span data-stu-id="02386-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="02386-157">使用遠端 Windows PowerShell 建立群組</span><span class="sxs-lookup"><span data-stu-id="02386-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="02386-158">這個範例會使用[New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) Cmdlet 來建立具有 itadmin 別名的通訊群組，以及名稱為 IT 系統管理員的名稱。</span><span class="sxs-lookup"><span data-stu-id="02386-158">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="02386-159">它也會將使用者新增為群組的成員。</span><span class="sxs-lookup"><span data-stu-id="02386-159">It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="02386-160">**附注**：若要建立安全性群組而不是通訊群組，請使用`Security` *Type*參數的值。</span><span class="sxs-lookup"><span data-stu-id="02386-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="02386-161">若要確認您是否已成功建立 IT 管理員群組，請執行下列命令以顯示新群組的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="02386-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="02386-162">如需詳細的語法及參數資訊，請參閱[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)。</span><span class="sxs-lookup"><span data-stu-id="02386-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="02386-163">若要取得群組中的成員清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="02386-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="02386-164">如需詳細的語法及參數資訊，請參閱[Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="02386-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="02386-165">若要取得所有群組的完整清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="02386-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="02386-166">使用遠端 Windows PowerShell 變更群組的屬性</span><span class="sxs-lookup"><span data-stu-id="02386-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="02386-167">使用 PowerShell （而非 EAC）的優點是能夠變更多個群組的屬性。</span><span class="sxs-lookup"><span data-stu-id="02386-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="02386-168">以下是一些使用 Exchange Online Protection PowerShell 變更群組屬性的範例。</span><span class="sxs-lookup"><span data-stu-id="02386-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="02386-169">這個範例會使用變更西雅圖員工群組的主要 SMTP 位址（也稱為回復位址）來 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="02386-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="02386-170">如需詳細的語法及參數資訊，請參閱[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="02386-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="02386-171">若要確認您是否已成功變更群組的屬性，請執行下列命令來確認新的值：</span><span class="sxs-lookup"><span data-stu-id="02386-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="02386-172">本範例會更新西雅圖 Employees 群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="02386-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="02386-173">請使用逗點分隔所有成員。</span><span class="sxs-lookup"><span data-stu-id="02386-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="02386-174">如需詳細的語法及參數資訊，請參閱[EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="02386-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="02386-175">若要取得群組西雅圖員工中所有成員的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="02386-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="02386-176">使用遠端 Windows PowerShell 移除群組</span><span class="sxs-lookup"><span data-stu-id="02386-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="02386-177">本範例會使用移除名為 IT 管理員的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="02386-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="02386-178">如需詳細的語法及參數資訊，請參閱[Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="02386-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="02386-179">若要確認群組已移除，請執行下列命令，並確認已刪除群組（在此例中為「It 系統管理員」）。</span><span class="sxs-lookup"><span data-stu-id="02386-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
