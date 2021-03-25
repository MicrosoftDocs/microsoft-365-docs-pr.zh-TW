---
title: 針對 Office 365 的 Defender 中的安全連結設定設定全域設定
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
description: 系統管理員可以瞭解如何查看和設定全域設定 (「封鎖下列 URLs」清單和 Office 365 應用程式的保護) ，以取得 Microsoft Defender for Office 365 中的安全連結。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203420"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="237fe-103">設定 Microsoft Defender for Office 365 中安全連結的全域設定</span><span class="sxs-lookup"><span data-stu-id="237fe-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="237fe-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="237fe-104">**Applies to**</span></span>
- [<span data-ttu-id="237fe-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="237fe-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="237fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="237fe-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="237fe-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="237fe-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="237fe-108">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="237fe-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="237fe-109">安全連結是 [Microsoft Defender For Office 365](defender-for-office-365.md) 中的一項功能，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結。</span><span class="sxs-lookup"><span data-stu-id="237fe-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="237fe-110">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全連結](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="237fe-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="237fe-111">您可以在安全連結原則中設定大多數的安全連結設定。</span><span class="sxs-lookup"><span data-stu-id="237fe-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="237fe-112">如需相關指示，請參閱 [設定 Microsoft Defender For Office 365 中的安全連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="237fe-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="237fe-113">不過，安全連結也會使用適用于所有作用中安全連結原則中所包含之所有使用者的全域設定。</span><span class="sxs-lookup"><span data-stu-id="237fe-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="237fe-114">下列全域設定區域：</span><span class="sxs-lookup"><span data-stu-id="237fe-114">These global settings area:</span></span>

- <span data-ttu-id="237fe-115">**封鎖下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="237fe-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="237fe-116">如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單。](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="237fe-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="237fe-117">Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="237fe-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="237fe-118">如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="237fe-118">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="237fe-119">您可以使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中設定全域安全連結設定，以取得適用的 Microsoft 365 組織。獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但搭配 Microsoft Defender for Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="237fe-120">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="237fe-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="237fe-121">安全連結的全域設定所提供的功能僅適用于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="237fe-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="237fe-122">沒有內建或預設的安全連結原則，因此您必須建立至少一個安全連結原則，這些全域設定才會作用。</span><span class="sxs-lookup"><span data-stu-id="237fe-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="237fe-123">如需相關指示，請參閱 [設定 Microsoft Defender For Office 365 中的安全連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="237fe-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="237fe-124">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="237fe-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="237fe-125">若要直接移至 [ **安全連結** ] 頁面，請使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="237fe-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="237fe-126">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="237fe-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="237fe-127">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="237fe-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="237fe-128">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="237fe-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="237fe-129">若要設定安全連結的全域設定，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="237fe-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="237fe-130">若要對安全連結的全域設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="237fe-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="237fe-131">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="237fe-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="237fe-132">**附註**：</span><span class="sxs-lookup"><span data-stu-id="237fe-132">**Notes**:</span></span>

  - <span data-ttu-id="237fe-133">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="237fe-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="237fe-134">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="237fe-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="237fe-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="237fe-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="237fe-136">如需安全連結之全域設定的建議值，請參閱 [安全連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="237fe-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="237fe-137">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="237fe-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="237fe-138">[新功能不斷新增至 Microsoft Defender For Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="237fe-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="237fe-139">新增新功能時，您可能需要調整現有的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="237fe-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="237fe-140">在安全性 & 規範中心設定「阻止下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="237fe-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="237fe-141">**Block 下列 URLs** 清單會識別在支援的應用程式中，安全連結掃描時，應攔截的連結。</span><span class="sxs-lookup"><span data-stu-id="237fe-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="237fe-142">如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單](safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="237fe-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="237fe-143">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="237fe-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="237fe-144">在 **您的組織的安全連結原則** 中，會出現 [飛出]，請移至 [ **封鎖下列 URLs] 方塊** 。</span><span class="sxs-lookup"><span data-stu-id="237fe-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="237fe-145">設定一或多個專案，如 ["封鎖下列 URLs 的專案語法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述] 清單。</span><span class="sxs-lookup"><span data-stu-id="237fe-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="237fe-146">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="237fe-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="237fe-147">設定 PowerShell 中的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="237fe-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="237fe-148">如需輸入語法的詳細資訊，請參閱「 [封鎖下列 URLs 的輸入語法」清單](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="237fe-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="237fe-149">您可以使用 **AtpPolicyForO365** Cmdlet 來查看 _BlockURLs_ 屬性中的現有專案。</span><span class="sxs-lookup"><span data-stu-id="237fe-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="237fe-150">若要新增將取代任何現有專案的值，請在 Exchange Online 中使用下列語法 PowerShell 或 Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="237fe-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="237fe-151">本範例會將下列專案新增至清單：</span><span class="sxs-lookup"><span data-stu-id="237fe-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="237fe-152">封鎖 fabrikam.com 的網域、子域及路徑。</span><span class="sxs-lookup"><span data-stu-id="237fe-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="237fe-153">封鎖子域調查，但不封鎖 tailspintoys.com 中的父網域或其他子域</span><span class="sxs-lookup"><span data-stu-id="237fe-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="237fe-154">若要新增或移除值，而不影響其他現有的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="237fe-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="237fe-155">本範例會為 adatum.com 新增新的專案，並移除 fabrikam.com 的專案。</span><span class="sxs-lookup"><span data-stu-id="237fe-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="237fe-156">在安全性 & 規範中心內設定 Office 365 應用程式的安全連結保護</span><span class="sxs-lookup"><span data-stu-id="237fe-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="237fe-157">Office 365 應用程式的安全連結保護適用于支援的 Office desktop、行動裝置和 web 應用程式中的檔。</span><span class="sxs-lookup"><span data-stu-id="237fe-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="237fe-158">如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="237fe-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="237fe-159">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="237fe-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="237fe-160">在已出現之 **組織的安全連結原則** 中，在 [ **電子郵件以外的內容設定** ] 區段中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="237fe-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="237fe-161">**Office 365 應用程式**：驗證切換是否為支援的 office 365 應用程式的安全連結：開啟開啟 ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="237fe-162">**當使用者按一下安全連結時，請勿追蹤**：在支援的 Office 365 應用程式中，將切換移至左側以追蹤與封鎖的 URLs 相關的使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="237fe-163">**不要讓使用者點擊 [安全連結] 原始 URL**：確認切換是向右，以防止使用者在支援的 Office 365 應用程式中按一下原始的封鎖 URL： ![ 開啟 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="237fe-164">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="237fe-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="237fe-165">在 PowerShell 中設定 Office 365 應用程式的安全連結保護</span><span class="sxs-lookup"><span data-stu-id="237fe-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="237fe-166">如果您不想使用 PowerShell 來設定 Office 365 應用程式的安全連結保護，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="237fe-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="237fe-167">此範例會針對 Office 365 應用程式中的安全連結保護設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="237fe-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="237fe-168">Office 365 應用程式的安全連結已開啟 (我們不會使用 _EnableSafeLinksForO365Clients_ 參數，預設值是 $true) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="237fe-169">追蹤支援的 Office 365 應用程式中的封鎖 URLs 相關的使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="237fe-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="237fe-170">在支援的 Office 365 應用程式中，不允許使用者點擊至原始的封鎖 URL (我們不會使用 _AllowClickThrough_ 參數，預設值是 $false) 。</span><span class="sxs-lookup"><span data-stu-id="237fe-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="237fe-171">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="237fe-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="237fe-172">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="237fe-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="237fe-173">若要確認您是否已成功設定安全連結的全域設定 (**封鎖下列 URLs** 清單和 Office 365 app protection 設定) ，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="237fe-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="237fe-174">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，按一下 [ **通用設定**]，然後確認 [飛出] 中顯示的設定。</span><span class="sxs-lookup"><span data-stu-id="237fe-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="237fe-175">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="237fe-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="237fe-176">如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="237fe-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>