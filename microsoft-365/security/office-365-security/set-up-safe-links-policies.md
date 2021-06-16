---
title: 為 Office 365 設定 Microsoft Defender 中的安全連結原則
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
description: 系統管理員可以瞭解如何在 Microsoft Defender 中查看、建立、修改及刪除安全連結原則及全域安全連結設定，以供 Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929824"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bcdd0-103">為 Office 365 設定 Microsoft Defender 中的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bcdd0-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="bcdd0-104">**Applies to**</span></span>
- [<span data-ttu-id="bcdd0-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="bcdd0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bcdd0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcdd0-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="bcdd0-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="bcdd0-108">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bcdd0-109">安全連結是[Microsoft Defender](defender-for-office-365.md)中的功能 Office 365，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 與連結的時間。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="bcdd0-110">如需詳細資訊，請參閱[Microsoft Defender 中 Office 365 的安全連結](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="bcdd0-111">沒有內建或預設的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="bcdd0-112">若要取得 URLs 的安全連結掃描，您必須建立一個或多個安全連結原則，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdd0-113">您可以在安全連結原則 **以外** 的安全連結保護中，設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="bcdd0-114">如需相關指示，請參閱[設定 Microsoft Defender 中安全連結的通用設定 Office 365](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="bcdd0-115">您可以在 Microsoft 365 Defender 入口網站或 PowerShell 中設定安全連結原則，以在 PowerShell 中使用信箱的合格 Microsoft 365 組織 (Exchange Online Exchange Online;組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Microsoft Defender Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-115">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="bcdd0-116">安全連結原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="bcdd0-117">**安全連結原則**：開啟安全連結保護，開啟即時 URL 掃描，指定在傳遞郵件之前是否等候即時掃描，請開啟 [內部郵件的掃描]，指定是否要在 URLs 追蹤使用者按一下，並指定是否允許使用者按一下原始 URL 的 trough。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="bcdd0-118">**安全連結規則**：指定原則套用至) 的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcdd0-119">系統管理員應考慮 SafeLinks 的不同設定設定。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="bcdd0-120">其中一個可用選項是在 SafeLinks 中包含使用者身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="bcdd0-121">這項功能可讓 *安全行動小組* 調查可能的使用者損損、採取糾正動作和限制昂貴的違規行為。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="bcdd0-122">當您在 Microsoft 365 Defender 入口網站中管理安全連結原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="bcdd0-123">當您建立安全連結原則時，實際上是建立安全連結規則和關聯的安全連結原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="bcdd0-124">當您修改安全連結原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="bcdd0-125">所有其他設定都會修改相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="bcdd0-126">當您移除安全連結原則時，會移除安全連結規則和相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="bcdd0-127">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="bcdd0-128">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bcdd0-129">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="bcdd0-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bcdd0-130">您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="bcdd0-131">若要直接移至 [ **安全連結** ] 頁面，請使用 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="bcdd0-132">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bcdd0-133">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bcdd0-134">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bcdd0-135">若要建立、修改和刪除安全連結原則，您必須是 Microsoft 365 Defender 入口網站的 **組織管理** 或 **安全性管理員** 角色群組成員，**以及** Exchange Online 中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="bcdd0-136">若要對安全連結原則進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bcdd0-137">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)和[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="bcdd0-138">將使用者新增至 Microsoft 365 admin center 中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bcdd0-139">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="bcdd0-140">.</span><span class="sxs-lookup"><span data-stu-id="bcdd0-140">.</span></span> <span data-ttu-id="bcdd0-141">- [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **View-Only 組織管理** 角色群組也會提供該功能的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="bcdd0-142">如需安全連結原則的建議設定，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="bcdd0-143">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="bcdd0-144">[新功能會連續新增至 Microsoft Defender 以供 Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="bcdd0-145">新增新功能時，您可能需要調整現有的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="bcdd0-146">使用 Microsoft 365 Defender 入口網站建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="bcdd0-147">在 Microsoft 365 Defender 入口網站中建立自訂安全連結原則，會同時為這兩者建立安全連結規則和相關聯的安全連結原則，同時也會同時使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="bcdd0-148">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-149">在 [ **安全連結** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="bcdd0-150">[ **新增安全連結原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="bcdd0-151">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="bcdd0-152">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="bcdd0-153">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="bcdd0-154">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bcdd0-155">在出現的 **設定** 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bcdd0-156">**在郵件中選取未知可能惡意 URLs 的動作**：選取 [ **開啟** ]，可對電子郵件中的連結啟用安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="bcdd0-157">**在 Microsoft Teams 內選取未知或可能惡意 URLs 的動作**：選取 [**開啟**] 以啟用 Teams 中的連結的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="bcdd0-158">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此設定可在電子郵件訊息中啟用連結的即時掃描。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="bcdd0-159">**等候 URL 掃描完成後，才能傳遞郵件**：選取此設定可等到即時 URL 掃描完成之後，才會傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="bcdd0-160">套用 **安全連結至組織內傳送的電子郵件**：選取此設定可將安全連結原則套用至內部寄件者和內部收件者之間的郵件。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="bcdd0-161">**請勿追蹤使用者點擊：請** 將此設定保留為未選取狀態，以啟用追蹤使用者按一下電子郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="bcdd0-162">**不允許使用者依序按一下原始 url**：選取此設定可在 [警告頁面](safe-links.md#warning-pages-from-safe-links)中，禁止使用者按一下原始 url。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="bcdd0-163">**請勿重新寫入下列 URLs**：允許存取以安全連結封鎖的指定 URLs。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="bcdd0-164">在方塊中，輸入您想要的 URL 或值，然後按一下</span><span class="sxs-lookup"><span data-stu-id="bcdd0-164">In the box, type the URL or value that you want, and then click</span></span> ![新增按鈕圖示](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="bcdd0-166">.</span><span class="sxs-lookup"><span data-stu-id="bcdd0-166">.</span></span>

     <span data-ttu-id="bcdd0-167">若要移除現有的專案，請選取該專案，然後按一下</span><span class="sxs-lookup"><span data-stu-id="bcdd0-167">To remove an existing entry, select it and then click</span></span> ![刪除按鈕圖示](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="bcdd0-169">.</span><span class="sxs-lookup"><span data-stu-id="bcdd0-169">.</span></span>

     <span data-ttu-id="bcdd0-170">如需輸入語法，請參閱「 [不要重新寫入下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="bcdd0-171">如需這些設定的詳細資訊，請參閱 Microsoft Teams 的電子郵件訊息和[安全連結設定](safe-links.md#safe-links-settings-for-microsoft-teams)[的安全連結設定](safe-links.md#safe-links-settings-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="bcdd0-172">如需標準和嚴格原則設定的建議值，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="bcdd0-173">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bcdd0-174">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="bcdd0-175">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="bcdd0-176">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="bcdd0-177">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="bcdd0-178">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-178">Click **Add a condition**.</span></span> <span data-ttu-id="bcdd0-179">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="bcdd0-180">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="bcdd0-181">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="bcdd0-182">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="bcdd0-183">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="bcdd0-184">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="bcdd0-185">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="bcdd0-186">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="bcdd0-187">若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="bcdd0-188">若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="bcdd0-189">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="bcdd0-190">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="bcdd0-191">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="bcdd0-192">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bcdd0-193">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="bcdd0-194">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="bcdd0-195">完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="bcdd0-196">使用 Microsoft 365 Defender 入口網站來查看安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-196">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="bcdd0-197">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-197">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-198">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="bcdd0-199">「即時」顯示原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="bcdd0-199">The policy details appear in a fly out</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="bcdd0-200">使用 Microsoft 365 Defender 入口網站修改安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-200">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="bcdd0-201">在 Microsoft 365 Defender 入口網站中，移至 [\***原則] & 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-201">In the Microsoft 365 Defender portal, go to \***Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-202">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bcdd0-203">在 [原則詳細資料] 顯示的 [飛出] 中，按一下 [ **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="bcdd0-204">[飛出] 中的可用設定與 [[使用 Microsoft 365 Defender 入口網站建立安全連結原則](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)] 一節中所述相同。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-204">The available settings in the fly out that appears are identical to those described in the [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="bcdd0-205">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="bcdd0-206">啟用或停用安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="bcdd0-207">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-207">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-208">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="bcdd0-209">將切換開關向左移動以停用原則：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-209">Move the toggle to the left to disable the policy:</span></span> ![關閉原則](../../media/scc-toggle-off.png)<span data-ttu-id="bcdd0-211">.</span><span class="sxs-lookup"><span data-stu-id="bcdd0-211">.</span></span>

   - <span data-ttu-id="bcdd0-212">將切換開關向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-212">Move the toggle to the right to enable the policy:</span></span> ![開啟原則](../../media/scc-toggle-on.png)<span data-ttu-id="bcdd0-214">.</span><span class="sxs-lookup"><span data-stu-id="bcdd0-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="bcdd0-215">設定安全連結原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="bcdd0-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="bcdd0-216">根據預設，安全連結原則的優先順序會根據在 (較舊的原則中所建立的順序，優先順序低於舊版的原則) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="bcdd0-217">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="bcdd0-218">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="bcdd0-219">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="bcdd0-220">安全連結原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="bcdd0-221">在 Microsoft 365 Defender 入口網站中，您可以在建立安全連結原則之後，才變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-221">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="bcdd0-222">在 PowerShell 中，您可以在建立安全連結規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="bcdd0-223">若要變更原則的優先順序，請在清單中向上或向下移動原則 (您無法直接修改 Microsoft 365 Defender 入口網站) 中的 **優先順序** 號碼。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span>

1. <span data-ttu-id="bcdd0-224">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-224">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-225">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bcdd0-226">在顯示的 [原則詳細資料] 中，按一下 [可用優先順序] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="bcdd0-227">**優先順序** 值為 **0** 的安全連結原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="bcdd0-228">具有最低 **優先順序** 值的安全連結原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="bcdd0-229">如果您有三個或更多的安全連結原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="bcdd0-230">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="bcdd0-231">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="bcdd0-232">使用 Microsoft 365 Defender 入口網站移除安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-232">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="bcdd0-233">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-233">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bcdd0-234">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bcdd0-235">在顯示的 [原則詳細資料] 中，按一下 [ **刪除原則**]，然後在出現的警告對話方塊中按一下 [ **是]** 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="bcdd0-236">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="bcdd0-237">如先前所述，安全連結原則包含安全連結原則和安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="bcdd0-238">在 PowerShell 中，安全連結原則與安全連結規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="bcdd0-239">您可以使用 **\* -SafeLinksPolicy** Cmdlet 來管理安全連結原則，也可以使用 **\* -SafeLinksRule** Cmdlet 來管理安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="bcdd0-240">在 PowerShell 中，您必須先建立安全連結原則，然後建立安全連結規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="bcdd0-241">在 PowerShell 中，您可以分別修改 [安全連結原則] 和 [安全連結] 規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="bcdd0-242">當您移除 PowerShell 的安全連結原則時，不會自動移除對應的安全連結規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="bcdd0-243">使用 PowerShell 建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="bcdd0-244">在 PowerShell 中建立安全連結原則的過程包括兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="bcdd0-245">建立安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="bcdd0-246">建立安全連結規則，以指定套用規則的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="bcdd0-247">您可以建立新的安全連結規則，並將現有的未關聯的安全連結原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="bcdd0-248">安全連結規則無法與一個以上的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="bcdd0-249">您可以在建立原則之前，于 Microsoft 365 Defender 入口網站的新安全連結原則上設定下列設定 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="bcdd0-250">_在_ `$false` **New-SafeLinksRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="bcdd0-251">在 _\<Number\>_ **New-SafeLinksRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="bcdd0-252">在您將原則指派至安全連結規則之前，您在 PowerShell 中建立的新安全連結原則不會顯示在 Microsoft 365 Defender 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-252">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="bcdd0-253">步驟1：使用 PowerShell 建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="bcdd0-254">若要建立安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="bcdd0-255">如需 _DoNotRewriteUrls_ 參數所使用之專案語法的詳細資訊，請參閱 [[不要重新寫入下列 URLs] 清單中的輸入語法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="bcdd0-256">如需使用 **Set-SafeLinksPolicy** Cmdlet 修改現有的安全連結原則時可用於 _DoNotRewriteUrls_ 參數的其他語法，請參閱本文稍後的 [使用 PowerShell 修改安全連結原則](#use-powershell-to-modify-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="bcdd0-257">此範例會建立名為 Contoso 的安全連結原則，並提供下列值：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="bcdd0-258">開啟電子郵件訊息中的 URL 掃描和重新寫入。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="bcdd0-259">開啟 Teams (中的 URL 掃描。點擊 [只供預覽]) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="bcdd0-260">開啟已按一下的即時掃描 URLs，包括指向檔案的按一下連結。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="bcdd0-261">等候 URL 掃描完成後，才能傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="bcdd0-262">開啟內部郵件的 URL 掃描及重新寫入。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="bcdd0-263">追蹤與安全連結保護 (相關的使用者按一下。我們不會使用 _DoNotTrackUserClicks_ 參數，而預設值則是 $false，這表示會追蹤) 的使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="bcdd0-264">不允許使用者依序按一下原始 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="bcdd0-265">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="bcdd0-266">步驟2：使用 PowerShell 建立安全連結規則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="bcdd0-267">若要建立安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="bcdd0-268">此範例會建立名為 Contoso 的安全連結規則，且具有下列條件：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="bcdd0-269">此規則會與名為 Contoso All 的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="bcdd0-270">此規則會套用至 contoso.com 網域中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="bcdd0-271">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="bcdd0-272"> (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="bcdd0-273">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="bcdd0-274">使用 PowerShell 來查看安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="bcdd0-275">若要查看現有的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bcdd0-276">本範例會傳回所有安全連結原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="bcdd0-277">此範例會傳回名為 Contoso 主管的安全連結原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="bcdd0-278">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="bcdd0-279">使用 PowerShell 來查看安全連結規則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="bcdd0-280">若要查看現有的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bcdd0-281">本範例會傳回所有安全連結規則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="bcdd0-282">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="bcdd0-283">此範例會傳回名為 Contoso 主管的安全連結規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="bcdd0-284">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="bcdd0-285">使用 PowerShell 修改安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="bcdd0-286">您無法在 PowerShell 中重新命名安全連結原則 (**Set-SafeLinksPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="bcdd0-287">當您重新命名 Microsoft 365 Defender 入口網站中的安全連結原則時，您只是重新命名安全連結 _規則_。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-287">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="bcdd0-288">在 PowerShell 中修改安全連結原則的唯一進一步考慮，就是 (「[不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) 的 _DoNotRewriteUrls_ 參數可用語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="bcdd0-289">若要新增將取代任何現有專案的值，請使用下列語法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="bcdd0-290">若要新增或移除值，而不影響其他現有的專案，請使用下列語法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="bcdd0-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="bcdd0-291">否則，當您建立安全連結原則時，可以使用相同的設定，如本文稍早的 [步驟1：使用 PowerShell 建立安全連結原則](#step-1-use-powershell-to-create-a-safe-links-policy) 一節所述。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="bcdd0-292">若要修改安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="bcdd0-293">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="bcdd0-294">使用 PowerShell 修改安全連結規則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="bcdd0-295">當您在 PowerShell 中修改安全連結規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="bcdd0-296">若要啟用或停用現有的安全連結規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="bcdd0-297">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全連結規則](#step-2-use-powershell-to-create-a-safe-links-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="bcdd0-298">若要修改安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="bcdd0-299">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="bcdd0-300">使用 PowerShell 來啟用或停用安全連結規則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="bcdd0-301">啟用或停用 PowerShell 中的安全連結規則可啟用或停用安全連結規則和指派的安全連結原則)  (的整體安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="bcdd0-302">若要啟用或停用 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="bcdd0-303">本範例會停用名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bcdd0-304">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bcdd0-305">如需詳細的語法及參數資訊，請參閱 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="bcdd0-306">使用 PowerShell 設定安全連結規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="bcdd0-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="bcdd0-307">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-307">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="bcdd0-308">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-308">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="bcdd0-309">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-309">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="bcdd0-310">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-310">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="bcdd0-311">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-311">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="bcdd0-312">若要設定 PowerShell 中安全連結規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="bcdd0-313">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-313">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="bcdd0-314">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-314">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="bcdd0-315">若要在建立新規則時設定其優先順序，請改用 **New-SafeLinksRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="bcdd0-316">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="bcdd0-317">使用 PowerShell 移除安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="bcdd0-318">當您使用 PowerShell 來移除安全連結原則時，並不會移除對應的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="bcdd0-319">若要移除 PowerShell 中的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="bcdd0-320">此範例會移除名為「行銷部門」的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="bcdd0-321">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="bcdd0-322">使用 PowerShell 移除安全連結規則</span><span class="sxs-lookup"><span data-stu-id="bcdd0-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="bcdd0-323">當您使用 PowerShell 來移除安全連結規則時，並不會移除對應的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="bcdd0-324">若要移除 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="bcdd0-325">此範例會移除名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bcdd0-326">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="bcdd0-327">若要確認安全連結正在掃描郵件，請檢查可用的 Microsoft Defender Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="bcdd0-328">如需詳細資訊，請參閱[View Office 365 的 Defender 報告](view-reports-for-mdo.md)]，然後[在 Microsoft 365 Defender 入口網站中使用 Explorer](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bcdd0-329">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="bcdd0-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="bcdd0-330">若要確認您是否已成功建立、修改或移除安全連結原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="bcdd0-331">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-331">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="bcdd0-332">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="bcdd0-333">若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bcdd0-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="bcdd0-334">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，以 \<Name\> 原則或規則名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="bcdd0-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```