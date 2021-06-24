---
title: 設定保管庫的 Defender 中的連結設定全域設定 Office 365
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何查看和設定全域設定 (「封鎖下列 URLs」清單和保護 Office 365 應用程式) ，以保管庫的 Microsoft Defender 連結。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46bafd89400dfa551641c055f6f0e208c0ecd49f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108040"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bb7d3-103">針對 Office 365 設定 Microsoft Defender 中保管庫連結的全域設定</span><span class="sxs-lookup"><span data-stu-id="bb7d3-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bb7d3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="bb7d3-104">**Applies to**</span></span>
- [<span data-ttu-id="bb7d3-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="bb7d3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bb7d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb7d3-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="bb7d3-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="bb7d3-108">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱[Advanced Outlook .com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bb7d3-109">保管庫連結是[Microsoft Defender](defender-for-office-365.md)中的功能 Office 365，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結的時間。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="bb7d3-110">如需詳細資訊，請參閱[保管庫 Office 365 的 Microsoft Defender 連結](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="bb7d3-111">您可以設定保管庫連結原則中的大部分保管庫連結設定。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="bb7d3-112">如需相關指示，請參閱[在 Microsoft Defender for Office 365 中設定保管庫連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="bb7d3-113">不過，保管庫連結也會使用您在保管庫連結原則本身之外設定的下列全域設定：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="bb7d3-114">**封鎖下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="bb7d3-115">此設定會套用至所有作用中保管庫連結原則中包含的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="bb7d3-116">如需詳細資訊，請參閱[保管庫連結的「封鎖下列 URLs」清單。](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="bb7d3-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="bb7d3-117">保管庫Office 365 應用程式的連結保護。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="bb7d3-118">這些設定會套用至組織中所有授權使用 Office 365 的使用者，不論使用者是否包含在 active 保管庫連結原則中。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="bb7d3-119">如需詳細資訊，請參閱[保管庫連結設定 Office 365 應用程式](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="bb7d3-120">您可以設定 Microsoft 365 Defender 入口網站中的全域保管庫連結設定或 PowerShell (Exchange Online PowerShell，以供具有 Microsoft 365 信箱的合格 Exchange Online 組織使用。組織的獨立 EOP PowerShell，但沒有 Exchange Online 信箱，但使用 Microsoft Defender Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-120">You can configure the global Safe Links settings in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bb7d3-121">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="bb7d3-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bb7d3-122">沒有內建或預設的保管庫連結原則，因此您必須至少建立一個保管庫連結原則，才能讓 **封鎖下列 URLs** 清單成為作用中。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="bb7d3-123">如需相關指示，請參閱[在 Microsoft Defender for Office 365 中設定保管庫連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="bb7d3-124">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-124">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="bb7d3-125">若要直接移至 [**保管庫連結**] 頁面，請使用 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="bb7d3-126">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bb7d3-127">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bb7d3-128">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bb7d3-129">若要設定保管庫連結的全域設定，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bb7d3-130">若要針對保管庫連結的全域設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bb7d3-131">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="bb7d3-132">**附註**：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-132">**Notes**:</span></span>

  - <span data-ttu-id="bb7d3-133">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bb7d3-134">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="bb7d3-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="bb7d3-136">如需保管庫連結之全域設定的建議值，請參閱[保管庫連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="bb7d3-137">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="bb7d3-138">[新功能會連續新增至 Microsoft Defender 以供 Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="bb7d3-139">新增新功能時，您可能需要調整現有的保管庫連結原則。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="bb7d3-140">設定 Microsoft 365 Defender 入口網站中的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="bb7d3-140">Configure the "Block the following URLs" list in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="bb7d3-141">**Block 下列 URLs** 清單會識別在支援的應用程式中保管庫連結掃描時，應攔截的連結。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="bb7d3-142">如需詳細資訊，請參閱[保管庫連結的「封鎖下列 URLs」清單](safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="bb7d3-143">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="bb7d3-144">在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="bb7d3-145">在組織的 [**保管庫連結] 原則** 中，請移出顯示的 [**封鎖下列 URLs] 方塊**。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="bb7d3-146">設定一或多個專案，如 ["封鎖下列 URLs 的專案語法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述] 清單。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="bb7d3-147">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="bb7d3-148">設定 PowerShell 中的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="bb7d3-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="bb7d3-149">如需輸入語法的詳細資訊，請參閱「 [封鎖下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="bb7d3-150">您可以使用 **AtpPolicyForO365** Cmdlet 來查看 _BlockURLs_ 屬性中的現有專案。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="bb7d3-151">若要新增將取代任何現有專案的值，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb7d3-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="bb7d3-152">本範例會將下列專案新增至清單：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="bb7d3-153">封鎖 fabrikam.com 的網域、子域及路徑。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="bb7d3-154">封鎖子域調查，但不封鎖 tailspintoys.com 中的父網域或其他子域</span><span class="sxs-lookup"><span data-stu-id="bb7d3-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="bb7d3-155">若要新增或移除值，而不影響其他現有的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="bb7d3-156">本範例會為 adatum.com 新增新的專案，並移除 fabrikam.com 的專案。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="bb7d3-157">在 Microsoft 365 Defender 入口網站中設定 Office 365 應用程式的保管庫連結保護</span><span class="sxs-lookup"><span data-stu-id="bb7d3-157">Configure Safe Links protection for Office 365 apps in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="bb7d3-158">保管庫Office 365 應用程式的連結保護適用于支援的 Office 桌面、行動裝置及 web 應用程式中的檔。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="bb7d3-159">如需詳細資訊，請參閱[保管庫連結設定 Office 365 應用程式](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="bb7d3-160">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **原則**] \> **保管庫連結**。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-160">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="bb7d3-161">在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="bb7d3-162">在所出現的 **組織保管庫連結原則** 中，設定設定中的下列設定，這些設定 **適用于 [支援的 Office 365 應用程式**] 區段中的內容：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="bb7d3-163">**使用 Office 365 應用程式中的保管庫連結**：確認是否要啟用支援 Office 365 應用程式的保管庫連結： ![ 開啟切換 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="bb7d3-164">**當使用者在 Office 365 應用程式中按下受保護的連結時，請勿追蹤**：將切換移至左側以追蹤與受支援 Office 365 應用程式中封鎖 URLs 相關的使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="bb7d3-165">**請勿讓使用者在 Office 365 應用程式中，按原始 URL**：確認切換是向右，以防止使用者在支援的 Office 365 應用程式中按一下原始的封鎖 url：開啟開啟] ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="bb7d3-166">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="bb7d3-167">在 PowerShell 中設定 Office 365 應用程式的保管庫連結保護</span><span class="sxs-lookup"><span data-stu-id="bb7d3-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="bb7d3-168">如果您不想使用 PowerShell 來設定 Office 365 應用程式保管庫連結保護，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb7d3-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="bb7d3-169">此範例會針對 Office 365 應用程式中的保管庫連結保護設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="bb7d3-170">保管庫Office 365 應用程式的連結已開啟 (不是使用 _EnableSafeLinksForO365Clients_ 參數，而預設值為 $true) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="bb7d3-171">會追蹤支援的 Office 365 應用程式中，與封鎖 URLs 相關的使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="bb7d3-172">在支援的 Office 365 應用程式中，不允許使用者點擊至原始的封鎖 URL (我們不會使用 _AllowClickThrough_ 參數，預設值會 $false) 。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="bb7d3-173">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bb7d3-174">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="bb7d3-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="bb7d3-175">若要確認您已成功設定保管庫連結的全域設定 (**區塊下列 URLs** 清單和 Office 365 應用程式保護設定) ，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="bb7d3-176">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **原則**] 區段 \> **保管庫連結** \> 按一下 [**通用設定**]，然後確認 [飛出] 中顯示的設定。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-176">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="bb7d3-177">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="bb7d3-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="bb7d3-178">如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="bb7d3-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
