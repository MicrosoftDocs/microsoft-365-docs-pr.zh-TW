---
title: 讓使用者能夠存取安全性與合規性中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須先獲指派 Microsoft 365 Security & 合規性中心的許可權，才能管理任何安全性或規範功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6071bb6260e0c0f524eb6e5d4e78c78fa8ff750
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036665"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="e1cdb-103">讓使用者能夠存取安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="e1cdb-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="e1cdb-104">在安全性 & 規範中心內，必須將許可權指派給使用者，才能管理任何安全性或規範功能。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="e1cdb-105">在安全性 & 規範中心內，以全域管理員或 OrganizationManagement 角色群組成員的身分，您可以將這些許可權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="e1cdb-106">使用者只能管理您授予權利給他們的安全性或符合性功能。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="e1cdb-107">如需您可以授與安全性 & 規範中心使用者之不同許可權的詳細資訊，請參閱[安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1cdb-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e1cdb-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1cdb-109">您必須是全域系統管理員或安全性 & 規範中心的 OrganizationManagement 角色群組成員，才可完成本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="e1cdb-110">安全性 & 合規性中心的角色群組可能會具有與 Exchange Online 中的角色群組類似的名稱，但它們不是相同的。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="e1cdb-111">角色群組成員資格不會在 Exchange Online 與安全性 & 合規性中心共用。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="e1cdb-112">委派存取許可權（結合）具有「管理者代表」（AOBO）許可權的合作夥伴無法存取安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e1cdb-113">使用系統管理中心，讓另一位使用者能夠存取安全性 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="e1cdb-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e1cdb-114">登[入並移](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="e1cdb-115">在 Microsoft 365 系統管理中心中，開啟 [系統**管理中心**]，然後按一下 [**安全性 & 合規性**]。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="e1cdb-116">在 [安全性 & 規範中心] 中，移至 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="e1cdb-117">從清單中，選擇您要新增使用者的角色群組，然後按一下 [**編輯** ![編輯圖示](../../media/O365-MDM-CreatePolicy-EditIcon.gif)]。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="e1cdb-118">在 [**成員**] 底下的角色群組的 [內容] 頁面中](../../media/ITPro-EAC-AddIcon.gif) ，按一下 [**新增**![新增圖示]，然後選取您要新增的使用者名稱（或使用者）。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="e1cdb-119">當您選取要新增至角色群組的所有使用者時，請按一下 [\*\*新增-\> \*\* ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="e1cdb-120">按一下 [儲存]，將變更儲存到角色群組。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e1cdb-121">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e1cdb-121">How do you know this worked?</span></span>

1. <span data-ttu-id="e1cdb-122">在 [安全性 & 規範中心] 中，移至 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="e1cdb-123">從清單中，選取要查看成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="e1cdb-124">在右側的角色群組詳細資料中，您可以查看角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e1cdb-125">使用 PowerShell 授予另一個使用者存取安全性 & 規範中心的許可權</span><span class="sxs-lookup"><span data-stu-id="e1cdb-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e1cdb-126">[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e1cdb-127">使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="e1cdb-128">**參數**：</span><span class="sxs-lookup"><span data-stu-id="e1cdb-128">**Parameters**:</span></span>

   - <span data-ttu-id="e1cdb-129">_Identity_是要新增成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="e1cdb-130">_Member_是信箱、通用安全性群組（USG），或要新增至角色群組的電腦。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="e1cdb-131">您一次只能指定一個成員。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="e1cdb-132">如需語法及參數的詳細資訊，請參閱[Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e1cdb-133">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e1cdb-133">How do you know this worked?</span></span>

<span data-ttu-id="e1cdb-134">若要確認您是否已授予使用者對安全性 & 合規性中心的存取權，請使用**Get-RoleGroupMember** Cmdlet 來查看「組織管理」角色群組中的成員，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="e1cdb-135">如需語法及參數的詳細資訊，請參閱[Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="e1cdb-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).</span></span>
