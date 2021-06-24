---
title: 在 Microsoft Defender 中設定 Office 365 的保管庫連結原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中查看、建立、修改和刪除保管庫連結原則及全域保管庫連結設定。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108208"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="374cb-103">在 Microsoft Defender 中設定 Office 365 的保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="374cb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="374cb-104">**Applies to**</span></span>
- [<span data-ttu-id="374cb-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="374cb-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="374cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="374cb-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="374cb-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="374cb-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="374cb-108">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="374cb-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="374cb-109">保管庫[Microsoft Defender for Office 365](defender-for-office-365.md)中的連結提供郵件流程內輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 與連結的時間。</span><span class="sxs-lookup"><span data-stu-id="374cb-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="374cb-110">如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 連結](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="374cb-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="374cb-111">沒有內建或預設的保管庫連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="374cb-112">若要取得保管庫的連結掃描 URLs，您需要建立一個或多個保管庫連結原則，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="374cb-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="374cb-113">您可以在保管庫連結原則 **之外**，設定保管庫連結保護的全域設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="374cb-114">如需相關指示，請參閱[Configure global settings for 保管庫 Office 365 的 Microsoft Defender 中的連結](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="374cb-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="374cb-115">系統管理員應考慮保管庫連結的不同設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="374cb-116">其中一個可用選項是將使用者身分識別資訊加入保管庫連結中。</span><span class="sxs-lookup"><span data-stu-id="374cb-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="374cb-117">這項功能可讓 *安全行動小組* 調查可能的使用者損損、採取糾正動作和限制昂貴的違規行為。</span><span class="sxs-lookup"><span data-stu-id="374cb-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="374cb-118">您可以設定 Microsoft 365 Defender 入口網站中的保管庫連結原則或 PowerShell (Exchange Online PowerShell，以供具有 Microsoft 365 信箱的合格 Exchange Online 組織使用。組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Microsoft Defender Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="374cb-119">保管庫連結原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="374cb-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="374cb-120">**安全連結原則**：開啟保管庫連結保護，開啟即時 URL 掃描，指定在傳遞郵件之前是否等候即時掃描，請開啟 [內部郵件的掃描]，指定是否要在 URLs 上追蹤使用者按一下，並指定是否允許使用者按一下 [trough] 至原始 URL。</span><span class="sxs-lookup"><span data-stu-id="374cb-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="374cb-121">**安全連結規則**：指定原則套用至) 的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="374cb-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="374cb-122">當您在 Microsoft 365 Defender 入口網站中管理保管庫連結原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="374cb-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="374cb-123">當您建立保管庫連結原則時，實際上是建立安全連結規則和關聯的安全連結原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="374cb-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="374cb-124">當您修改保管庫連結原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="374cb-125">所有其他設定都會修改相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="374cb-126">當您移除保管庫連結原則時，會移除安全連結規則和相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="374cb-127">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="374cb-128">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫連結原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="374cb-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="374cb-129">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="374cb-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="374cb-130">您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="374cb-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="374cb-131">若要直接移至 [**保管庫連結**] 頁面，請使用 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="374cb-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="374cb-132">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="374cb-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="374cb-133">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="374cb-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="374cb-134">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="374cb-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="374cb-135">若要建立、修改和刪除保管庫連結原則，您必須是 Microsoft 365 Defender 入口網站中 **組織管理** 或 **安全性管理員** 角色群組的成員，**以及** Exchange Online 中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="374cb-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="374cb-136">若要對保管庫連結原則進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="374cb-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="374cb-137">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="374cb-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="374cb-138">將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="374cb-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="374cb-139">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="374cb-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="374cb-140">.</span><span class="sxs-lookup"><span data-stu-id="374cb-140">.</span></span> <span data-ttu-id="374cb-141">- [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **View-Only 組織管理** 角色群組也會提供該功能的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="374cb-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="374cb-142">如需保管庫連結原則的建議設定，請參閱[保管庫連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="374cb-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="374cb-143">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="374cb-144">[新功能會連續新增至 Microsoft Defender 以供 Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="374cb-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="374cb-145">新增新功能時，您可能需要調整現有的保管庫連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="374cb-146">使用 Microsoft 365 Defender 入口網站建立保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="374cb-147">在 Microsoft 365 Defender 入口網站中建立自訂的保管庫連結原則，會同時使用相同的名稱建立安全連結規則和相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="374cb-148">在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-149">在 [**保管庫連結**] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。</span><span class="sxs-lookup"><span data-stu-id="374cb-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="374cb-150">隨即會開啟 [**新增保管庫連結原則**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="374cb-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="374cb-151">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="374cb-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="374cb-152">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="374cb-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="374cb-153">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="374cb-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="374cb-154">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="374cb-155">在出現的 [ **使用者和網域** ] 頁面上，識別原則套用至 (收件者條件) 的內部收件者：</span><span class="sxs-lookup"><span data-stu-id="374cb-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="374cb-156">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="374cb-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="374cb-157">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="374cb-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="374cb-158">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="374cb-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="374cb-159">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="374cb-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="374cb-160">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="374cb-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="374cb-161">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="374cb-161">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="374cb-163">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="374cb-163">next to the value.</span></span>

   <span data-ttu-id="374cb-164">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="374cb-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="374cb-165">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="374cb-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="374cb-166">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="374cb-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="374cb-167">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="374cb-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="374cb-168">**排除這些使用者、群組和網域**：若要新增原則套用至 (收件者例外狀況) 的內部收件者例外狀況，請選取此選項並設定例外狀況。</span><span class="sxs-lookup"><span data-stu-id="374cb-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="374cb-169">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="374cb-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="374cb-170">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="374cb-171">在出現的 [ **保護設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="374cb-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="374cb-172">**在郵件中選取未知可能惡意 URLs 的動作**：選擇 [**開啟**]，可對電子郵件中的連結啟用保管庫連結保護。</span><span class="sxs-lookup"><span data-stu-id="374cb-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="374cb-173">如果您開啟此設定，則可以使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="374cb-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="374cb-174">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此選項可在電子郵件訊息中啟用連結的即時掃描。</span><span class="sxs-lookup"><span data-stu-id="374cb-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="374cb-175">如果您在下列設定上開啟此設定，請使用：</span><span class="sxs-lookup"><span data-stu-id="374cb-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="374cb-176">**等候 URL 掃描完成後，才會傳遞郵件**：選取此選項可等到即時 URL 掃描完成之後，才會傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="374cb-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="374cb-177">套用 **保管庫連結至組織內傳送的電子郵件**：選取此選項可將保管庫連結原則套用至內部寄件者和內部收件者之間的郵件。</span><span class="sxs-lookup"><span data-stu-id="374cb-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="374cb-178">**在 Microsoft Teams 內選取未知或可能惡意 URLs 的動作**：選取 [**開啟**] 以啟用 Teams 中連結的保管庫連結保護。</span><span class="sxs-lookup"><span data-stu-id="374cb-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="374cb-179">**請勿追蹤使用者點擊：請** 將此設定保留為未選取狀態，以啟用追蹤使用者按一下電子郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="374cb-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="374cb-180">**不允許使用者依序按一下原始 url**：選取此選項，可在 [警告頁面](safe-links.md#warning-pages-from-safe-links)中封鎖使用者按一下原始 url。</span><span class="sxs-lookup"><span data-stu-id="374cb-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="374cb-181">**請勿重新寫入下列 URLs**：允許存取保管庫連結所封鎖的指定 URLs。</span><span class="sxs-lookup"><span data-stu-id="374cb-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="374cb-182">在方塊中，輸入您想要的 URL 或值，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="374cb-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="374cb-183">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="374cb-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="374cb-184">若要移除現有的專案，請按一下</span><span class="sxs-lookup"><span data-stu-id="374cb-184">To remove an existing entry, click</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="374cb-186">專案旁邊。</span><span class="sxs-lookup"><span data-stu-id="374cb-186">next to the entry.</span></span>

     <span data-ttu-id="374cb-187">如需輸入語法，請參閱「 [不要重新寫入下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="374cb-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="374cb-188">如需這些設定的詳細資訊，請參閱[保管庫連結設定保管庫的電子郵件訊息](safe-links.md#safe-links-settings-for-email-messages)和[Microsoft Teams 的連結設定](safe-links.md#safe-links-settings-for-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="374cb-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="374cb-189">如需標準和嚴格原則設定的建議值，請參閱[保管庫連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="374cb-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="374cb-190">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="374cb-191">在出現的 [ **通知** ] 頁面上，選取下列其中一個值，以瞭解 **您要如何通知使用者？**：</span><span class="sxs-lookup"><span data-stu-id="374cb-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="374cb-192">**使用預設通知文字**</span><span class="sxs-lookup"><span data-stu-id="374cb-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="374cb-193">**使用自訂通知文字**：如果您選取這個值 (長度不能超過200個字元) 時，會出現下列設定：</span><span class="sxs-lookup"><span data-stu-id="374cb-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="374cb-194">**使用 Microsoft 翻譯工具進行自動當地語系化**</span><span class="sxs-lookup"><span data-stu-id="374cb-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="374cb-195">**自訂通知文字**：在此方塊中輸入自訂通知文字。</span><span class="sxs-lookup"><span data-stu-id="374cb-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="374cb-196">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="374cb-197">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="374cb-198">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="374cb-199">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="374cb-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="374cb-200">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="374cb-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="374cb-201">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="374cb-202">使用 Microsoft 365 Defender 入口網站來查看保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="374cb-203">在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-204">在 [**保管庫連結**] 頁面上，下列屬性會顯示在保管庫連結原則的清單中：</span><span class="sxs-lookup"><span data-stu-id="374cb-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="374cb-205">**名稱**</span><span class="sxs-lookup"><span data-stu-id="374cb-205">**Name**</span></span>
   - <span data-ttu-id="374cb-206">**狀態**</span><span class="sxs-lookup"><span data-stu-id="374cb-206">**Status**</span></span>
   - <span data-ttu-id="374cb-207">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="374cb-207">**Priority**</span></span>

3. <span data-ttu-id="374cb-208">當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="374cb-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="374cb-209">使用 Microsoft 365 Defender 入口網站修改保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="374cb-210">在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-211">在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="374cb-212">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="374cb-213">如需這些設定的詳細資訊，請參閱在本文中[使用 Microsoft 365 Defender 入口網站來建立保管庫連結原則](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="374cb-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="374cb-214">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="374cb-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="374cb-215">啟用或停用保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="374cb-216">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-217">在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="374cb-218">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="374cb-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="374cb-219">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="374cb-220">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="374cb-221">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="374cb-222">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="374cb-223">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="374cb-224">設定保管庫連結原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="374cb-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="374cb-225">根據預設，保管庫連結的優先順序是根據在 (較舊原則中建立的順序，而不是舊原則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="374cb-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="374cb-226">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="374cb-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="374cb-227">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="374cb-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="374cb-228">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="374cb-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="374cb-229">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="374cb-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="374cb-230">**附注**：</span><span class="sxs-lookup"><span data-stu-id="374cb-230">**Note**:</span></span>

- <span data-ttu-id="374cb-231">在 Microsoft 365 Defender 入口網站中，您只可以在建立保管庫連結原則之後，變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="374cb-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="374cb-232">在 PowerShell 中，您可以在建立安全連結規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="374cb-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="374cb-233">保管庫連結原則會依顯示的連續處理 (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="374cb-234">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="374cb-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="374cb-235">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-236">在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="374cb-237">在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：</span><span class="sxs-lookup"><span data-stu-id="374cb-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="374cb-238">**優先順序** 值為 **0** 的原則只有 [**降低優先順序**] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="374cb-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="374cb-239">具有最低 **優先順序** 值的原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="374cb-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="374cb-240">如果您有三個或多個原則，則最高和最低優先順序值之間的原則都具有 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="374cb-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="374cb-241">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="374cb-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="374cb-242">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="374cb-243">使用 Microsoft 365 Defender 入口網站移除保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="374cb-244">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="374cb-245">在 [**保管庫連結**] 頁面上，按一下 [名稱] 以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="374cb-246">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="374cb-247">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="374cb-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="374cb-248">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="374cb-249">如先前所述，保管庫連結原則包含安全連結原則和安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="374cb-250">在 PowerShell 中，安全連結原則與安全連結規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="374cb-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="374cb-251">您可以使用 **\* -SafeLinksPolicy** Cmdlet 來管理安全連結原則，也可以使用 **\* -SafeLinksRule** Cmdlet 來管理安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="374cb-252">在 PowerShell 中，您必須先建立安全連結原則，然後建立安全連結規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="374cb-253">在 PowerShell 中，您可以分別修改 [安全連結原則] 和 [安全連結] 規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="374cb-254">當您移除 PowerShell 的安全連結原則時，不會自動移除對應的安全連結規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="374cb-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="374cb-255">使用 PowerShell 建立保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="374cb-256">在 PowerShell 中建立保管庫連結原則的過程包括兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="374cb-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="374cb-257">建立安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="374cb-258">建立安全連結規則，以指定套用規則的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="374cb-259">您可以建立新的安全連結規則，並將現有的未關聯的安全連結原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="374cb-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="374cb-260">安全連結規則無法與一個以上的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="374cb-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="374cb-261">您可以在建立原則之前，在 PowerShell 中的新安全連結原則上設定下列設定 Microsoft 365 Defender，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="374cb-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="374cb-262">_在_ `$false` **New-SafeLinksRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="374cb-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="374cb-263">在 _\<Number\>_ **New-SafeLinksRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="374cb-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="374cb-264">在您將原則指派至安全連結規則之前，您在 PowerShell 中所建立的新安全連結原則不會顯示在 Microsoft 365 Defender 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="374cb-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="374cb-265">步驟1：使用 PowerShell 建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="374cb-266">若要建立安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="374cb-267">如需 _DoNotRewriteUrls_ 參數所使用之專案語法的詳細資訊，請參閱 [[不要重新寫入下列 URLs] 清單中的輸入語法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="374cb-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="374cb-268">如需使用 **Set-SafeLinksPolicy** Cmdlet 修改現有的安全連結原則時可用於 _DoNotRewriteUrls_ 參數的其他語法，請參閱本文稍後的 [使用 PowerShell 修改安全連結原則](#use-powershell-to-modify-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="374cb-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="374cb-269">此範例會建立名為 Contoso 的安全連結原則，並提供下列值：</span><span class="sxs-lookup"><span data-stu-id="374cb-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="374cb-270">開啟電子郵件訊息中的 URL 掃描和重新寫入。</span><span class="sxs-lookup"><span data-stu-id="374cb-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="374cb-271">開啟 Teams (中的 URL 掃描。點擊 [只供預覽]) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="374cb-272">開啟已按一下的即時掃描 URLs，包括指向檔案的按一下連結。</span><span class="sxs-lookup"><span data-stu-id="374cb-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="374cb-273">等候 URL 掃描完成後，才能傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="374cb-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="374cb-274">開啟內部郵件的 URL 掃描及重新寫入。</span><span class="sxs-lookup"><span data-stu-id="374cb-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="374cb-275">追蹤與保管庫連結保護相關的使用者點擊 (我們不使用 _DoNotTrackUserClicks_ 參數，預設值為 $false，這表示會追蹤使用者按一下) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="374cb-276">不允許使用者依序按一下原始 URL。</span><span class="sxs-lookup"><span data-stu-id="374cb-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="374cb-277">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="374cb-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="374cb-278">步驟2：使用 PowerShell 建立安全連結規則</span><span class="sxs-lookup"><span data-stu-id="374cb-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="374cb-279">若要建立安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="374cb-280">此範例會建立名為 Contoso 的安全連結規則，且具有下列條件：</span><span class="sxs-lookup"><span data-stu-id="374cb-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="374cb-281">此規則會與名為 Contoso All 的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="374cb-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="374cb-282">此規則會套用至 contoso.com 網域中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="374cb-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="374cb-283">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="374cb-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="374cb-284"> (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="374cb-285">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="374cb-286">使用 PowerShell 來查看安全連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="374cb-287">若要查看現有的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="374cb-288">本範例會傳回所有安全連結原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="374cb-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="374cb-289">此範例會傳回名為 Contoso 主管的安全連結原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="374cb-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="374cb-290">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="374cb-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="374cb-291">使用 PowerShell 來查看安全連結規則</span><span class="sxs-lookup"><span data-stu-id="374cb-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="374cb-292">若要查看現有的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="374cb-293">本範例會傳回所有安全連結規則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="374cb-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="374cb-294">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="374cb-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="374cb-295">此範例會傳回名為 Contoso 主管的安全連結規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="374cb-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="374cb-296">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="374cb-297">使用 PowerShell 修改安全連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="374cb-298">您無法在 PowerShell 中重新命名安全連結原則 (**Set-SafeLinksPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="374cb-299">當您重新命名 Microsoft 365 Defender 入口網站的保管庫連結原則時，您只會重新命名安全連結 _規則_。</span><span class="sxs-lookup"><span data-stu-id="374cb-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="374cb-300">在 PowerShell 中修改安全連結原則的唯一進一步考慮，就是 (「[不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) 的 _DoNotRewriteUrls_ 參數可用語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="374cb-301">若要新增將取代任何現有專案的值，請使用下列語法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="374cb-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="374cb-302">若要新增或移除值，而不影響其他現有的專案，請使用下列語法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="374cb-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="374cb-303">否則，當您建立安全連結原則時，可以使用相同的設定，如本文稍早的 [步驟1：使用 PowerShell 建立安全連結原則](#step-1-use-powershell-to-create-a-safe-links-policy) 一節所述。</span><span class="sxs-lookup"><span data-stu-id="374cb-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="374cb-304">若要修改安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="374cb-305">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="374cb-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="374cb-306">使用 PowerShell 修改安全連結規則</span><span class="sxs-lookup"><span data-stu-id="374cb-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="374cb-307">當您在 PowerShell 中修改安全連結規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="374cb-308">若要啟用或停用現有的安全連結規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="374cb-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="374cb-309">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全連結規則](#step-2-use-powershell-to-create-a-safe-links-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="374cb-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="374cb-310">若要修改安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="374cb-311">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="374cb-312">使用 PowerShell 來啟用或停用安全連結規則</span><span class="sxs-lookup"><span data-stu-id="374cb-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="374cb-313">啟用或停用 PowerShell 中的安全連結規則可啟用或停用整個保管庫連結原則 (安全連結規則和指派的安全連結原則) 。</span><span class="sxs-lookup"><span data-stu-id="374cb-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="374cb-314">若要啟用或停用 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="374cb-315">本範例會停用名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="374cb-316">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="374cb-317">如需詳細的語法及參數資訊，請參閱 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="374cb-318">使用 PowerShell 設定安全連結規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="374cb-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="374cb-319">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="374cb-319">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="374cb-320">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="374cb-320">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="374cb-321">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="374cb-321">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="374cb-322">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="374cb-322">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="374cb-323">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="374cb-323">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="374cb-324">若要設定 PowerShell 中安全連結規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="374cb-325">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="374cb-325">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="374cb-326">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="374cb-326">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="374cb-327">若要在建立新規則時設定其優先順序，請改用 **New-SafeLinksRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="374cb-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="374cb-328">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="374cb-329">使用 PowerShell 移除安全連結原則</span><span class="sxs-lookup"><span data-stu-id="374cb-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="374cb-330">當您使用 PowerShell 來移除安全連結原則時，並不會移除對應的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="374cb-331">若要移除 PowerShell 中的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="374cb-332">此範例會移除名為「行銷部門」的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="374cb-333">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="374cb-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="374cb-334">使用 PowerShell 移除安全連結規則</span><span class="sxs-lookup"><span data-stu-id="374cb-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="374cb-335">當您使用 PowerShell 來移除安全連結規則時，並不會移除對應的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="374cb-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="374cb-336">若要移除 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="374cb-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="374cb-337">此範例會移除名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="374cb-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="374cb-338">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="374cb-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="374cb-339">若要驗證保管庫的連結是否正在掃描郵件，請檢查可用的 Microsoft Defender 以 Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="374cb-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="374cb-340">如需詳細資訊，請參閱[View Office 365 的 Defender 報告](view-reports-for-mdo.md)]，然後[在 Microsoft 365 Defender 入口網站中使用 Explorer](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="374cb-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="374cb-341">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="374cb-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="374cb-342">若要確認您是否已成功建立、修改或移除保管庫連結原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="374cb-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="374cb-343">在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **威脅原則** \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="374cb-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="374cb-344">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="374cb-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="374cb-345">若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="374cb-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="374cb-346">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，以 \<Name\> 原則或規則名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="374cb-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
