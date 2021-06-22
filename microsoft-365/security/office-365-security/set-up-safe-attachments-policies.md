---
title: 在 Microsoft Defender 中設定 Office 365 的保管庫附件原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 瞭解如何定義保管庫附件原則，以利用電子郵件中的惡意檔案保護您的組織。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054328"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="eab32-103">在 Microsoft Defender 中設定 Office 365 的保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eab32-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="eab32-104">**Applies to**</span></span>
- [<span data-ttu-id="eab32-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="eab32-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eab32-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eab32-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="eab32-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](whats-new-in-defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="eab32-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="eab32-108">如果您是尋找 Outlook 中附件掃描相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="eab32-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="eab32-109">保管庫附件是[Microsoft Defender 中用於 Office 365](whats-new-in-defender-for-office-365.md)的功能，可使用虛擬環境在[Exchange Online Protection (EOP) 中的反惡意程式碼保護](anti-malware-protection.md)（但傳送至收件者）之後，檢查輸入電子郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="eab32-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="eab32-110">如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 附件](safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="eab32-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="eab32-111">沒有內建或預設的保管庫附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="eab32-112">若要取得保管庫電子郵件附件掃描的附件，您必須建立一個或多個保管庫附件原則，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="eab32-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="eab32-113">您可以在 Microsoft 365 Defender 入口網站中設定保管庫附件原則，或在 Exchange Online 中使用信箱 PowerShell (PowerShell Microsoft 365 使用中的信箱 Exchange Online;組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Defender Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="eab32-114">保管庫附件原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="eab32-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="eab32-115">**安全附件原則**：指定未知惡意程式碼偵測的動作，是否要將具有惡意軟體附件的郵件傳送至指定的電子郵件地址，以及是否要在保管庫附件掃描無法完成時傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="eab32-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="eab32-116">**安全附件規則**：指定原則套用至) 的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="eab32-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="eab32-117">當您在 Microsoft 365 Defender 入口網站中管理保管庫附件原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="eab32-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="eab32-118">當您建立保管庫附件原則時，實際上是同時建立安全附件規則和相關聯的安全附件原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="eab32-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="eab32-119">當您修改保管庫附件原則時，與名稱、優先順序、啟用或停用的名稱或收件者篩選器相關的設定會修改安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="eab32-120">所有其他設定會修改關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="eab32-121">當您移除保管庫附件原則時，會移除安全附件規則和相關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="eab32-122">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="eab32-123">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫附件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)」一節。</span><span class="sxs-lookup"><span data-stu-id="eab32-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="eab32-124">在 [保管庫附件設定] 的 [通用設定] 區域中，設定不依賴保管庫附件原則的功能。</span><span class="sxs-lookup"><span data-stu-id="eab32-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="eab32-125">如需相關指示，請參閱在[保管庫中](safe-docs.md)[開啟 SharePoint、OneDrive 及 Microsoft Teams 及 Microsoft 365 E5 檔的保管庫附件](turn-on-mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="eab32-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eab32-126">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="eab32-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eab32-127">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="eab32-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="eab32-128">若要直接移至 [**保管庫附件**] 頁面，請使用 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="eab32-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="eab32-129">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="eab32-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="eab32-130">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="eab32-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eab32-131">您必須具備下列許可權，才可執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="eab32-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eab32-132">若要建立、修改和刪除保管庫附件原則，您必須是 Microsoft 365 Defender 入口網站中 **組織管理** 或 **安全性管理員** 角色群組的成員，**以及** Exchange Online 中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="eab32-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="eab32-133">若要取得保管庫附件原則的唯讀存取權，您必須是 Microsoft 365 Defender 入口網站中 **全域讀取器** 或 **安全性讀者** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="eab32-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="eab32-134">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="eab32-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="eab32-135">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eab32-135">**Notes**:</span></span>

  - <span data-ttu-id="eab32-136">將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="eab32-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eab32-137">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="eab32-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="eab32-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="eab32-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="eab32-139">如需保管庫附件原則的建議設定，請參閱[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="eab32-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="eab32-140">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="eab32-141">使用 Microsoft 365 Defender 入口網站建立保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="eab32-142">在 Microsoft 365 Defender 入口網站中建立自訂的保管庫附件原則，會同時使用相同的名稱建立安全附件規則和關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="eab32-143">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-143">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-144">在 [**保管庫附件**] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。</span><span class="sxs-lookup"><span data-stu-id="eab32-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="eab32-145">原則精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="eab32-145">The policy wizard opens.</span></span> <span data-ttu-id="eab32-146">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eab32-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="eab32-147">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="eab32-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="eab32-148">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="eab32-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="eab32-149">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="eab32-150">在出現的 [ **使用者和網域** ] 頁面上，識別原則套用至 (收件者條件) 的內部收件者：</span><span class="sxs-lookup"><span data-stu-id="eab32-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="eab32-151">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="eab32-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="eab32-152">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="eab32-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="eab32-153">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="eab32-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="eab32-154">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="eab32-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="eab32-155">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="eab32-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="eab32-156">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="eab32-156">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="eab32-158">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="eab32-158">next to the value.</span></span>

   <span data-ttu-id="eab32-159">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="eab32-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="eab32-160">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="eab32-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="eab32-161">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="eab32-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="eab32-162">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="eab32-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="eab32-163">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="eab32-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="eab32-164">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="eab32-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="eab32-165">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="eab32-166">在 [**設定**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eab32-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="eab32-167">**保管庫附件未知的惡意程式碼回應**：請選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eab32-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="eab32-168">**Off**：一般而言，我們不建議此值。</span><span class="sxs-lookup"><span data-stu-id="eab32-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="eab32-169">**監視**</span><span class="sxs-lookup"><span data-stu-id="eab32-169">**Monitor**</span></span>
     - <span data-ttu-id="eab32-170">**封鎖**：這是預設值，以及標準及嚴格的預設 [安全性原則](preset-security-policies.md)中的建議值。</span><span class="sxs-lookup"><span data-stu-id="eab32-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="eab32-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="eab32-171">**Replace**</span></span>
     - <span data-ttu-id="eab32-172">**動態傳遞 (預覽功能)**</span><span class="sxs-lookup"><span data-stu-id="eab32-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="eab32-173">這些值會在[保管庫附件原則設定](safe-attachments.md#safe-attachments-policy-settings)中說明。</span><span class="sxs-lookup"><span data-stu-id="eab32-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="eab32-174">**以偵測到的附件重新導向郵件**：如果您選取 [ **啟用重新導向**]，您可以在 [ **傳送** 包含惡意程式碼附件的電子郵件] 方塊中，指定電子郵件地址，以傳送包含惡意程式碼附件進行分析和調查的郵件。</span><span class="sxs-lookup"><span data-stu-id="eab32-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="eab32-175">標準和嚴格原則設定的建議是啟用重新定向。</span><span class="sxs-lookup"><span data-stu-id="eab32-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="eab32-176">如需詳細資訊，請參閱[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="eab32-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="eab32-177">**如果掃描無法完成 (超時或) 錯誤，請套用保管庫附件偵測回應**。保管庫附件指定的動作會對郵件採取 **未知惡意程式碼回應**，即使保管庫附件掃描無法完成也是一樣。</span><span class="sxs-lookup"><span data-stu-id="eab32-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="eab32-178">如果您選取此選項，請永遠選取 [ **啟用重新導向** ]，並指定電子郵件地址以傳送包含惡意程式碼附件的郵件。</span><span class="sxs-lookup"><span data-stu-id="eab32-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="eab32-179">否則，郵件可能會遺失。</span><span class="sxs-lookup"><span data-stu-id="eab32-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="eab32-180">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="eab32-181">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="eab32-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="eab32-182">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="eab32-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="eab32-183">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="eab32-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="eab32-184">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="eab32-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="eab32-185">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="eab32-186">使用 Microsoft 365 Defender 入口網站來查看保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="eab32-187">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-187">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-188">在 [**保管庫附件**] 頁面上，下列屬性會顯示在原則清單中：</span><span class="sxs-lookup"><span data-stu-id="eab32-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="eab32-189">**名稱**</span><span class="sxs-lookup"><span data-stu-id="eab32-189">**Name**</span></span>
   - <span data-ttu-id="eab32-190">**狀態**</span><span class="sxs-lookup"><span data-stu-id="eab32-190">**Status**</span></span>
   - <span data-ttu-id="eab32-191">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="eab32-191">**Priority**</span></span>

3. <span data-ttu-id="eab32-192">當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="eab32-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="eab32-193">使用 Microsoft 365 Defender 入口網站修改保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="eab32-194">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-194">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-195">在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eab32-196">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="eab32-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="eab32-197">如需這些設定的詳細資訊，請參閱本文前面的[使用 Microsoft 365 Defender 入口網站來建立保管庫附件原則](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="eab32-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="eab32-198">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="eab32-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="eab32-199">啟用或停用保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="eab32-200">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-200">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-201">在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eab32-202">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eab32-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="eab32-203">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="eab32-204">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="eab32-205">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="eab32-206">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="eab32-207">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="eab32-208">設定保管庫附件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="eab32-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="eab32-209">根據預設，保管庫附件原則的優先順序是根據在 (較舊的原則中建立的順序，而不是舊的原則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eab32-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="eab32-210">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="eab32-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="eab32-211">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="eab32-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="eab32-212">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="eab32-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="eab32-213">保管庫附件原則會以處理的順序顯示， (第一個原則的 **優先順序** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="eab32-214">**附注**：在 Microsoft 365 Defender 入口網站中，您可以在建立保管庫附件原則之後，才變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="eab32-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="eab32-215">在 PowerShell 中，您可以在建立安全附件規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eab32-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="eab32-216">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="eab32-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="eab32-217">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="eab32-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="eab32-218">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-218">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-219">在 [**保管庫附件**] 頁面上，按一下 [名稱]，從清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eab32-220">在出現的 [原則詳細資料] 浮出視窗頂端，您會看到 [ **增加優先順序** ] 或 [ **降低] 優先順序** ，取決於目前的優先順序值和原則數目：</span><span class="sxs-lookup"><span data-stu-id="eab32-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="eab32-221">**優先順序** 值為 **0** 的原則只有 [**降低優先順序**] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="eab32-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="eab32-222">具有最低 **優先順序** 值的原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="eab32-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="eab32-223">如果您有三個或多個原則，則最高和最低優先順序值之間的原則都具有 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="eab32-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="eab32-224">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="eab32-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="eab32-225">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="eab32-226">使用 Microsoft 365 Defender 入口網站移除保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="eab32-227">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-227">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="eab32-228">在 [**保管庫附件**] 頁面上，按一下原則的名稱，從清單中選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="eab32-229">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="eab32-230">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="eab32-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="eab32-231">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="eab32-232">如先前所述，保管庫附件原則是由安全附件原則和安全附件規則所組成。</span><span class="sxs-lookup"><span data-stu-id="eab32-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="eab32-233">在 PowerShell 中，安全附件原則與安全附件規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="eab32-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="eab32-234">您可以使用 **\* -SafeAttachmentPolicy** Cmdlet 來管理安全附件原則，也可以使用 **\* -SafeAttachmentRule** Cmdlet 來管理安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="eab32-235">在 PowerShell 中，您先建立安全附件原則，然後建立可識別套用規則之原則的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="eab32-236">在 PowerShell 中，您可以分別修改安全附件原則和安全附件規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="eab32-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="eab32-237">當您從 PowerShell 中移除安全附件原則時，不會自動移除對應的安全附件規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="eab32-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="eab32-238">使用 PowerShell 建立保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="eab32-239">在 PowerShell 中建立保管庫附件原則是兩個步驟的程式：</span><span class="sxs-lookup"><span data-stu-id="eab32-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="eab32-240">建立安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="eab32-241">建立安全附件規則，以指定套用規則的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="eab32-242">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eab32-242">**Notes**:</span></span>

- <span data-ttu-id="eab32-243">您可以建立新的安全附件規則，並將現有的、未關聯的安全附件原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="eab32-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="eab32-244">安全附件規則無法與一個以上的安全附件原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="eab32-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="eab32-245">您可以在建立原則之前，于 Microsoft 365 Defender 入口網站上無法使用 PowerShell 中的新安全附件原則上設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eab32-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="eab32-246">_在_ `$false` **New-SafeAttachmentRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="eab32-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="eab32-247">在 _\<Number\>_ **New-SafeAttachmentRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eab32-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="eab32-248">在您將原則指派至安全附件規則之前，您在 PowerShell 中所建立的新安全附件原則不會顯示在 Microsoft 365 Defender 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="eab32-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="eab32-249">步驟1：使用 PowerShell 建立安全附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="eab32-250">若要建立安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="eab32-251">此範例會建立名為 Contoso 的安全附件原則，並提供下列值：</span><span class="sxs-lookup"><span data-stu-id="eab32-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="eab32-252">保管庫檔掃描時，封鎖所找到之惡意程式碼的郵件， (我們不會使用 _Action_ 參數，且預設值為 `Block`) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="eab32-253">已啟用重新導向，而且找到包含惡意程式碼的郵件會傳送至 sec-ops@contoso.com 進行分析和調查。</span><span class="sxs-lookup"><span data-stu-id="eab32-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="eab32-254">如果保管庫附件掃描無法使用或遇到錯誤，請勿傳遞郵件 (我們不會使用 _ActionOnError_ 參數，預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="eab32-255">如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eab32-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="eab32-256">步驟2：使用 PowerShell 建立安全附件規則</span><span class="sxs-lookup"><span data-stu-id="eab32-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="eab32-257">若要建立安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="eab32-258">此範例會建立名為 Contoso 的安全附件規則，且具有下列條件：</span><span class="sxs-lookup"><span data-stu-id="eab32-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="eab32-259">此規則會與名為 Contoso All 的安全附件原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="eab32-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="eab32-260">此規則會套用至 contoso.com 網域中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="eab32-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="eab32-261">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eab32-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="eab32-262"> (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="eab32-263">如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="eab32-264">使用 PowerShell 來查看安全附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="eab32-265">若要查看現有的安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="eab32-266">本範例會傳回所有安全附件原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="eab32-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="eab32-267">此範例會傳回名為 Contoso 主管的安全附件原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eab32-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="eab32-268">如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eab32-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="eab32-269">使用 PowerShell 來查看安全附件規則</span><span class="sxs-lookup"><span data-stu-id="eab32-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="eab32-270">若要查看現有的安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="eab32-271">本範例會傳回所有安全附件規則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="eab32-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="eab32-272">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab32-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="eab32-273">此範例會傳回名為 Contoso 主管的安全附件規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eab32-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="eab32-274">如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="eab32-275">使用 PowerShell 修改安全附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="eab32-276">您無法在 PowerShell 中重新命名安全附件原則 (**Set-SafeAttachmentPolicy** Cmdlet 沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="eab32-277">當您重新命名 Microsoft 365 Defender 入口網站的保管庫附件原則時，您只會重新命名安全附件 _規則_。</span><span class="sxs-lookup"><span data-stu-id="eab32-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="eab32-278">否則，當您建立安全附件原則時，就會使用相同的設定，如本文稍早 [使用 [步驟1：使用 PowerShell 來建立安全附件原則](#step-1-use-powershell-to-create-a-safe-attachment-policy) ] 區段所述。</span><span class="sxs-lookup"><span data-stu-id="eab32-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="eab32-279">若要修改安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="eab32-280">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eab32-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="eab32-281">使用 PowerShell 修改安全附件規則</span><span class="sxs-lookup"><span data-stu-id="eab32-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="eab32-282">當您在 PowerShell 中修改安全附件規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="eab32-283">若要啟用或停用現有的安全附件規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="eab32-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="eab32-284">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全附件規則](#step-2-use-powershell-to-create-a-safe-attachment-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="eab32-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="eab32-285">若要修改安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="eab32-286">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="eab32-287">使用 PowerShell 來啟用或停用安全附件規則</span><span class="sxs-lookup"><span data-stu-id="eab32-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="eab32-288">啟用或停用 PowerShell 中的安全附件規則可啟用或停用整個保管庫附件原則 (安全附件規則和指派的安全附件原則) 。</span><span class="sxs-lookup"><span data-stu-id="eab32-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="eab32-289">若要啟用或停用 PowerShell 中的安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="eab32-290">本範例會停用名為「行銷部門」的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="eab32-291">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="eab32-292">如需詳細的語法及參數資訊，請參閱 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 和 [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="eab32-293">使用 PowerShell 設定安全附件規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="eab32-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="eab32-294">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="eab32-294">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="eab32-295">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="eab32-295">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="eab32-296">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="eab32-296">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="eab32-297">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="eab32-297">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="eab32-298">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="eab32-298">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="eab32-299">若要設定 PowerShell 中安全附件規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="eab32-300">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="eab32-300">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="eab32-301">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="eab32-301">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="eab32-302">**附注**：若要在建立新規則時設定其優先順序，請改為在 **New-SafeAttachmentRule** Cmdlet 上使用 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="eab32-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="eab32-303">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="eab32-304">使用 PowerShell 移除安全附件原則</span><span class="sxs-lookup"><span data-stu-id="eab32-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="eab32-305">當您使用 PowerShell 來移除安全附件原則時，並不會移除對應的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="eab32-306">若要移除 PowerShell 中的安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="eab32-307">此範例會移除名為 Marketing 部門的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="eab32-308">如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eab32-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="eab32-309">使用 PowerShell 移除安全附件規則</span><span class="sxs-lookup"><span data-stu-id="eab32-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="eab32-310">當您使用 PowerShell 來移除安全附件規則時，並不會移除對應的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="eab32-311">若要在 PowerShell 中移除安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eab32-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="eab32-312">本範例會移除名為 Marketing 部門的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="eab32-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="eab32-313">如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="eab32-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="eab32-314">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eab32-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="eab32-315">若要確認您是否已成功建立、修改或移除保管庫附件原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="eab32-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="eab32-316">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> 的「**威脅原則** 原則」 \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="eab32-316">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="eab32-317">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="eab32-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="eab32-318">若要查看更多詳細資料，請按一下 [名稱]，然後在 [飛出] 中查看詳細資料，從清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="eab32-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="eab32-319">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，以 \<Name\> 原則或規則名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="eab32-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="eab32-320">若要驗證保管庫附件是否正在掃描郵件，請檢查可用的 Defender 以取得 Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="eab32-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="eab32-321">如需詳細資訊，請參閱[View Office 365 的 Defender 報告](view-reports-for-mdo.md)]，然後[在 Microsoft 365 Defender 入口網站中使用 Explorer](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="eab32-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
