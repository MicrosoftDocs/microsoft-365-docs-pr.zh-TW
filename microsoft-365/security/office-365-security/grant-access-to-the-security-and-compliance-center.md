---
title: 讓使用者能夠存取安全性與合規性中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須先獲指派 Microsoft 365 Security & 合規性中心的許可權，才能管理任何安全性或規範功能。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab02773a19e1b5881858104097b0b03e4385b40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907217"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="bc14e-103">讓使用者能夠存取安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="bc14e-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bc14e-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="bc14e-104">**Applies to**</span></span>
- [<span data-ttu-id="bc14e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bc14e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bc14e-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="bc14e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bc14e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc14e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bc14e-108">在安全性 & 規範中心內，必須將許可權指派給使用者，才能管理任何安全性或規範功能。</span><span class="sxs-lookup"><span data-stu-id="bc14e-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="bc14e-109">在安全性 & 規範中心內，以全域管理員或 OrganizationManagement 角色群組成員的身分，您可以將這些許可權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="bc14e-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="bc14e-110">使用者只能管理您授予權利給他們的安全性或符合性功能。</span><span class="sxs-lookup"><span data-stu-id="bc14e-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="bc14e-111">如需您可以授與安全性 & 規範中心使用者之不同許可權的詳細資訊，請參閱 [安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bc14e-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bc14e-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="bc14e-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bc14e-113">您必須是全域系統管理員或安全性 & 規範中心的 OrganizationManagement 角色群組成員，才可完成本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="bc14e-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="bc14e-114">安全性 & 合規性中心的角色群組可能會具有與 Exchange Online 中的角色群組類似的名稱，但它們不是相同的。</span><span class="sxs-lookup"><span data-stu-id="bc14e-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="bc14e-115">角色群組成員資格不會在 Exchange Online 與安全性 & 合規性中心共用。</span><span class="sxs-lookup"><span data-stu-id="bc14e-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="bc14e-116">委派存取許可權 () 協力廠商使用管理代表 (AOBO) 許可權無法存取安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="bc14e-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="bc14e-117">使用安全性 & 合規性中心，讓另一個使用者能夠存取安全性 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="bc14e-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="bc14e-118">開啟安全性 & 合規性中心 <https://protection.office.com> ，然後移至 [ **許可權**]。</span><span class="sxs-lookup"><span data-stu-id="bc14e-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="bc14e-119">若要直接移至 [ **許可權** ] 索引標籤，請開啟 <https://protection.office.com/permissions> 。</span><span class="sxs-lookup"><span data-stu-id="bc14e-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="bc14e-120">從角色群組的清單中，選擇角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="bc14e-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="bc14e-121">在 [**成員**] 底下的角色群組的 [內容] 頁面中，按一下 [**新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.gif) ，然後選取您要新增的使用者 (名稱或使用者) 。</span><span class="sxs-lookup"><span data-stu-id="bc14e-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="bc14e-122">當您選取要新增至角色群組的所有使用者時，請按一下 [**新增- \>** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bc14e-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="bc14e-123">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bc14e-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="bc14e-124">使用安全性 & 規範中心 PowerShell 授予另一個使用者存取安全性 & 規範中心的許可權</span><span class="sxs-lookup"><span data-stu-id="bc14e-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="bc14e-125">[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bc14e-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bc14e-126">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bc14e-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="bc14e-127">如需詳細的語法及參數問題，請參閱 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="bc14e-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bc14e-128">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="bc14e-128">How do you know this worked?</span></span>

<span data-ttu-id="bc14e-129">若要確認您是否已成功授與安全性 & 規範中心的存取權，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="bc14e-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="bc14e-130">在 [安全性 & 規範中心] 中，移至 [ **許可權** ]，然後選取角色群組。</span><span class="sxs-lookup"><span data-stu-id="bc14e-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="bc14e-131">在開啟的 [詳細資料] 浮出控制項中，驗證角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bc14e-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="bc14e-132">在 [安全性 & 規範中心] PowerShell 中， \<RoleGroupName\> 以角色群組的名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bc14e-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="bc14e-133">如需詳細的語法及參數資訊，請參閱 [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="bc14e-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>