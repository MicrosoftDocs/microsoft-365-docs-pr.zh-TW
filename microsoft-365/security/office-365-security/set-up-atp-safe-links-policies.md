---
title: 設定 Microsoft Defender for Office 365 中的安全連結原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中查看、建立、修改及刪除安全連結原則及全域安全連結設定。
ms.openlocfilehash: 7a00b73855302f5046afa0605fd7188007394ed7
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683160"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d6cbc-103">設定 Microsoft Defender for Office 365 中的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="d6cbc-104">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](office-365-atp.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="d6cbc-105">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="d6cbc-106">安全連結是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一項功能，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="d6cbc-107">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="d6cbc-108">沒有內建或預設的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="d6cbc-109">若要取得 URLs 的安全連結掃描，您必須建立一個或多個安全連結原則，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="d6cbc-110">您可以在安全連結原則 **以外** 的安全連結保護中，設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-110">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="d6cbc-111">如需相關指示，請參閱 [在 Microsoft Defender For Office 365 中設定安全連結的通用設定](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-111">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="d6cbc-112">您可以使用 Exchange Online 中的信箱，設定安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中的安全連結原則;獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但搭配 Microsoft Defender for Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-112">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="d6cbc-113">安全連結原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-113">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="d6cbc-114">**安全連結原則**：開啟安全連結保護，開啟即時 URL 掃描，指定在傳遞郵件之前是否等候即時掃描，請開啟 [內部郵件的掃描]，指定是否要在 URLs 追蹤使用者按一下，並指定是否允許使用者按一下原始 URL 的 trough。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-114">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="d6cbc-115">**安全連結規則**：指定原則套用至) 的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-115">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="d6cbc-116">當您在安全性 & 合規性中心管理安全連結原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-116">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d6cbc-117">當您建立安全連結原則時，實際上是建立安全連結規則和關聯的安全連結原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-117">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d6cbc-118">當您修改安全連結原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-118">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="d6cbc-119">所有其他設定都會修改相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-119">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="d6cbc-120">當您移除安全連結原則時，會移除安全連結規則和相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-120">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="d6cbc-121">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-121">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d6cbc-122">如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-122">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d6cbc-123">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d6cbc-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d6cbc-124">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d6cbc-125">若要直接移至 [ **安全連結** ] 頁面，請使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="d6cbc-126">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d6cbc-127">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d6cbc-128">您必須先獲指派安全性與合規性中心的權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d6cbc-129">若要建立、修改及刪除安全連結原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d6cbc-130">若要對安全連結原則進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d6cbc-131">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d6cbc-132">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-132">**Notes**:</span></span>

  - <span data-ttu-id="d6cbc-133">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d6cbc-134">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="d6cbc-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="d6cbc-136">如需安全連結原則的建議設定，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="d6cbc-137">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="d6cbc-138">[新功能不斷新增至 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="d6cbc-139">新增新功能時，您可能需要調整現有的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="d6cbc-140">使用安全性 & 規範中心建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="d6cbc-141">在安全性 & 合規性中心建立自訂安全連結原則，會同時使用相同的名稱建立安全連結規則及相關聯的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d6cbc-142">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-143">在 [ **安全連結** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="d6cbc-144">[ **新增安全連結原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="d6cbc-145">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d6cbc-146">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d6cbc-147">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d6cbc-148">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d6cbc-149">在顯示的 [ **設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d6cbc-150">**在郵件中選取未知可能惡意 URLs 的動作**：選取 [ **開啟** ]，可對電子郵件中的連結啟用安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="d6cbc-151">**選取 Microsoft 小組中未知或可能惡意的 URLs 的動作**：選擇 [ **開啟** ]，可對小組中的連結啟用安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="d6cbc-152">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此設定可在電子郵件訊息中啟用連結的即時掃描。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="d6cbc-153">**等候 URL 掃描完成後，才能傳遞郵件**：選取此設定可等到即時 URL 掃描完成之後，才會傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="d6cbc-154">套用 **安全連結至組織內傳送的電子郵件**：選取此設定可將安全連結原則套用至內部寄件者和內部收件者之間的郵件。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="d6cbc-155">**請勿追蹤使用者點擊：請** 將此設定保留為未選取狀態，以啟用追蹤使用者按一下電子郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="d6cbc-156">**不允許使用者依序按一下原始 url**：選取此設定可在 [警告頁面](atp-safe-links.md#warning-pages-from-safe-links)中，禁止使用者按一下原始 url。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="d6cbc-157">**請勿重新寫入下列 URLs**：允許存取以安全連結封鎖的指定 URLs。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="d6cbc-158">在方塊中，輸入您想要的 URL 或值，然後按一下</span><span class="sxs-lookup"><span data-stu-id="d6cbc-158">In the box, type the URL or value that you want, and then click</span></span> ![新增按鈕圖示](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="d6cbc-160">.</span><span class="sxs-lookup"><span data-stu-id="d6cbc-160">.</span></span>

     <span data-ttu-id="d6cbc-161">若要移除現有的專案，請選取該專案，然後按一下</span><span class="sxs-lookup"><span data-stu-id="d6cbc-161">To remove an existing entry, select it and then click</span></span> ![刪除按鈕圖示](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="d6cbc-163">.</span><span class="sxs-lookup"><span data-stu-id="d6cbc-163">.</span></span>

     <span data-ttu-id="d6cbc-164">如需輸入語法，請參閱「 [不要重新寫入下列 URLs 的輸入語法」清單](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="d6cbc-165">如需這些設定的詳細資訊，請參閱 Microsoft 小組的電子郵件訊息和[安全連結設定](atp-safe-links.md#safe-links-settings-for-microsoft-teams)[的安全連結設定](atp-safe-links.md#safe-links-settings-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="d6cbc-166">如需標準和嚴格原則設定的建議值，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="d6cbc-167">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d6cbc-168">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d6cbc-169">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d6cbc-170">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d6cbc-171">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d6cbc-172">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-172">Click **Add a condition**.</span></span> <span data-ttu-id="d6cbc-173">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d6cbc-174">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d6cbc-175">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d6cbc-176">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d6cbc-177">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d6cbc-178">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d6cbc-179">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d6cbc-180">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d6cbc-181">若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d6cbc-182">若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d6cbc-183">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d6cbc-184">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d6cbc-185">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d6cbc-186">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d6cbc-187">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d6cbc-188">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d6cbc-189">完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="d6cbc-190">使用安全性 & 規範中心來查看安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="d6cbc-191">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-192">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="d6cbc-193">「即時」顯示原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="d6cbc-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="d6cbc-194">使用安全性 & 規範中心來修改安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="d6cbc-195">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-196">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d6cbc-197">在 [原則詳細資料] 顯示的 [飛出] 中，按一下 [ **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="d6cbc-198">[飛出] 中的可用設定與 [ [使用安全性 & 規範中心] 建立安全連結原則](#use-the-security--compliance-center-to-create-safe-links-policies) 一節中所述。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="d6cbc-199">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="d6cbc-200">啟用或停用安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="d6cbc-201">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-202">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d6cbc-203">將切換開關向左移動以停用原則：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-203">Move the toggle to the left to disable the policy:</span></span> ![關閉原則](../../media/scc-toggle-off.png)<span data-ttu-id="d6cbc-205">.</span><span class="sxs-lookup"><span data-stu-id="d6cbc-205">.</span></span>

   - <span data-ttu-id="d6cbc-206">將切換開關向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-206">Move the toggle to the right to enable the policy:</span></span> ![開啟原則](../../media/scc-toggle-on.png)<span data-ttu-id="d6cbc-208">.</span><span class="sxs-lookup"><span data-stu-id="d6cbc-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="d6cbc-209">設定安全連結原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="d6cbc-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="d6cbc-210">根據預設，安全連結原則的優先順序會根據在 (較舊的原則中所建立的順序，優先順序低於舊版的原則) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d6cbc-211">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d6cbc-212">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d6cbc-213">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d6cbc-214">安全連結原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="d6cbc-215">**附注**：在 [安全性 & 規範中心] 中，您只能在建立安全連結原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="d6cbc-216">在 PowerShell 中，您可以在建立安全連結規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d6cbc-217">若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序] 數字)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d6cbc-218">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-219">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d6cbc-220">在顯示的 [原則詳細資料] 中，按一下 [可用優先順序] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="d6cbc-221">**優先順序** 值為 **0** 的安全連結原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d6cbc-222">具有最低 **優先順序** 值的安全連結原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d6cbc-223">如果您有三個或更多的安全連結原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d6cbc-224">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d6cbc-225">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="d6cbc-226">使用安全性 & 規範中心移除安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="d6cbc-227">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d6cbc-228">在 [ **安全連結** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d6cbc-229">在顯示的 [原則詳細資料] 中，按一下 [ **刪除原則**]，然後在出現的警告對話方塊中按一下 [ **是]** 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="d6cbc-230">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="d6cbc-231">如先前所述，安全連結原則包含安全連結原則和安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="d6cbc-232">在 PowerShell 中，安全連結原則與安全連結規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="d6cbc-233">您可以使用 **\* -SafeLinksPolicy** Cmdlet 來管理安全連結原則，也可以使用 **\* -SafeLinksRule** Cmdlet 來管理安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="d6cbc-234">在 PowerShell 中，您必須先建立安全連結原則，然後建立安全連結規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d6cbc-235">在 PowerShell 中，您可以分別修改 [安全連結原則] 和 [安全連結] 規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="d6cbc-236">當您移除 PowerShell 的安全連結原則時，不會自動移除對應的安全連結規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="d6cbc-237">使用 PowerShell 建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="d6cbc-238">在 PowerShell 中建立安全連結原則的過程包括兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d6cbc-239">建立安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="d6cbc-240">建立安全連結規則，以指定套用規則的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="d6cbc-241">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-241">**Notes**:</span></span>

- <span data-ttu-id="d6cbc-242">您可以建立新的安全連結規則，並將現有的未關聯的安全連結原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="d6cbc-243">安全連結規則無法與一個以上的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="d6cbc-244">您可以在 [安全性 & 規範中心] PowerShell 中的新安全連結原則上設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d6cbc-245">_在_ `$false` **New-SafeLinksRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="d6cbc-246">在 _\<Number\>_ **New-SafeLinksRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="d6cbc-247">您在 PowerShell 中建立的新安全連結原則不會顯示在安全性 & 規範中心，除非您將原則指派至安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="d6cbc-248">步驟1：使用 PowerShell 建立安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="d6cbc-249">若要建立安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="d6cbc-250">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-250">**Notes**:</span></span>

- <span data-ttu-id="d6cbc-251">如需 _DoNotRewriteUrls_ 參數所使用之專案語法的詳細資訊，請參閱 [[不要重新寫入下列 URLs] 清單中的輸入語法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="d6cbc-252">如需使用 **Set-SafeLinksPolicy** Cmdlet 修改現有的安全連結原則時可用於 _DoNotRewriteUrls_ 參數的其他語法，請參閱本文稍後的 [使用 PowerShell 修改安全連結原則](#use-powershell-to-modify-safe-links-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="d6cbc-253">此範例會建立名為 Contoso 的安全連結原則，並提供下列值：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="d6cbc-254">開啟電子郵件訊息中的 URL 掃描和重新寫入。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="d6cbc-255">開啟小組中的 URL 掃描 (點擊 [只供預覽]) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="d6cbc-256">開啟已按一下的即時掃描 URLs，包括指向檔案的按一下連結。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="d6cbc-257">等候 URL 掃描完成後，才能傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="d6cbc-258">開啟內部郵件的 URL 掃描及重新寫入。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="d6cbc-259">追蹤與安全連結保護 (相關的使用者按一下。我們不會使用 _DoNotTrackUserClicks_ 參數，而預設值則是 $false，這表示會追蹤) 的使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="d6cbc-260">不允許使用者依序按一下原始 URL。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="d6cbc-261">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="d6cbc-262">步驟2：使用 PowerShell 建立安全連結規則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="d6cbc-263">若要建立安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="d6cbc-264">此範例會建立名為 Contoso 的安全連結規則，且具有下列條件：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="d6cbc-265">此規則會與名為 Contoso All 的安全連結原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="d6cbc-266">此規則會套用至 contoso.com 網域中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="d6cbc-267">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="d6cbc-268"> (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="d6cbc-269">如需詳細的語法及參數資訊，請參閱 [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="d6cbc-270">使用 PowerShell 來查看安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="d6cbc-271">若要查看現有的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d6cbc-272">本範例會傳回所有安全連結原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="d6cbc-273">此範例會傳回名為 Contoso 主管的安全連結原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="d6cbc-274">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="d6cbc-275">使用 PowerShell 來查看安全連結規則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="d6cbc-276">若要查看現有的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d6cbc-277">本範例會傳回所有安全連結規則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="d6cbc-278">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="d6cbc-279">此範例會傳回名為 Contoso 主管的安全連結規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="d6cbc-280">如需詳細的語法及參數資訊，請參閱 [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="d6cbc-281">使用 PowerShell 修改安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="d6cbc-282">您無法在 PowerShell 中重新命名安全連結原則 (**Set-SafeLinksPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d6cbc-283">當您在安全性 & 合規性中心重新命名安全連結原則時，您只會重新命名安全連結 _規則_。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="d6cbc-284">在 PowerShell 中修改安全連結原則的唯一進一步考慮，就是 (「[不要重新寫入下列 URLs」清單](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) 的 _DoNotRewriteUrls_ 參數可用語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="d6cbc-285">若要新增將取代任何現有專案的值，請使用下列語法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="d6cbc-286">若要新增或移除值，而不影響其他現有的專案，請使用下列語法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="d6cbc-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="d6cbc-287">否則，當您建立安全連結原則時，可以使用相同的設定，如本文稍早的 [步驟1：使用 PowerShell 建立安全連結原則](#step-1-use-powershell-to-create-a-safe-links-policy) 一節所述。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="d6cbc-288">若要修改安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d6cbc-289">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="d6cbc-290">使用 PowerShell 修改安全連結規則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="d6cbc-291">當您在 PowerShell 中修改安全連結規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d6cbc-292">若要啟用或停用現有的安全連結規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="d6cbc-293">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全連結規則](#step-2-use-powershell-to-create-a-safe-links-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="d6cbc-294">若要修改安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d6cbc-295">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="d6cbc-296">使用 PowerShell 來啟用或停用安全連結規則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="d6cbc-297">啟用或停用 PowerShell 中的安全連結規則可啟用或停用安全連結規則和指派的安全連結原則)  (的整體安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="d6cbc-298">若要啟用或停用 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="d6cbc-299">本範例會停用名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d6cbc-300">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d6cbc-301">如需詳細的語法及參數資訊，請參閱 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="d6cbc-302">使用 PowerShell 設定安全連結規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="d6cbc-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="d6cbc-303">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d6cbc-304">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d6cbc-305">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d6cbc-306">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d6cbc-307">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d6cbc-308">若要設定 PowerShell 中安全連結規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d6cbc-309">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-309">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d6cbc-310">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-310">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d6cbc-311">**附注**：若要在建立新規則時設定其優先順序，請改為在 **New-SafeLinksRule** Cmdlet 上使用 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="d6cbc-312">如需詳細的語法及參數資訊，請參閱 [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="d6cbc-313">使用 PowerShell 移除安全連結原則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="d6cbc-314">當您使用 PowerShell 來移除安全連結原則時，並不會移除對應的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="d6cbc-315">若要移除 PowerShell 中的安全連結原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d6cbc-316">此範例會移除名為「行銷部門」的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d6cbc-317">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="d6cbc-318">使用 PowerShell 移除安全連結規則</span><span class="sxs-lookup"><span data-stu-id="d6cbc-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="d6cbc-319">當您使用 PowerShell 來移除安全連結規則時，並不會移除對應的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="d6cbc-320">若要移除 PowerShell 中的安全連結規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="d6cbc-321">此範例會移除名為「行銷部門」的安全連結規則。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d6cbc-322">如需詳細的語法及參數資訊，請參閱 [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="d6cbc-323">若要確認安全連結正在掃描郵件，請檢查可用的 Microsoft Defender for Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="d6cbc-324">如需詳細資訊，請參閱 [View For Office 365 的 Defender 報告](view-reports-for-atp.md) 和 [使用 Explorer In Security & 合規性中心](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d6cbc-325">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d6cbc-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="d6cbc-326">若要確認您是否已成功建立、修改或移除安全連結原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="d6cbc-327">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="d6cbc-328">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d6cbc-329">若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d6cbc-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="d6cbc-330">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="d6cbc-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
