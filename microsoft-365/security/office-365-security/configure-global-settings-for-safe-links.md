---
title: 設定 Office 365 ATP 中安全連結設定的全域設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何查看和設定全域設定 (「封鎖下列 URLs」清單和 Office 365 app 的保護）) 以取得 Office 365 高級威脅防護 (ATP) 的安全連結。
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328504"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="82790-103">針對 Office 365 ATP 中的安全連結設定全域設定</span><span class="sxs-lookup"><span data-stu-id="82790-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="82790-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="82790-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="82790-105">如果您是尋找 Outlook 中 Safelinks 相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="82790-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="82790-106">安全連結是 [Office 365 的「高級威脅防護 ](office-365-atp.md) 」中的功能 (ATP) ，可在郵件流程中提供輸入電子郵件的 URL 掃描，並在電子郵件和其他位置中，按一下驗證 URLs 和連結的時間。</span><span class="sxs-lookup"><span data-stu-id="82790-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="82790-107">如需詳細資訊，請參閱 [Office 365 ATP 中的安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="82790-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="82790-108">您可以在安全連結原則中設定大多數的安全連結設定。</span><span class="sxs-lookup"><span data-stu-id="82790-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="82790-109">如需相關指示，請參閱 [設定 Office 365 ATP 中的安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="82790-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="82790-110">不過，安全連結也會使用適用于所有作用中安全連結原則中所包含之所有使用者的全域設定。</span><span class="sxs-lookup"><span data-stu-id="82790-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="82790-111">下列全域設定區域：</span><span class="sxs-lookup"><span data-stu-id="82790-111">These global settings area:</span></span>

- <span data-ttu-id="82790-112">**封鎖下列 URLs**清單。</span><span class="sxs-lookup"><span data-stu-id="82790-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="82790-113">如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單。](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="82790-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="82790-114">Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="82790-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="82790-115">如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="82790-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="82790-116">您可以使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中設定全域安全連結設定，以取得適用的 Microsoft 365 組織。獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但使用 Office 365 ATP 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="82790-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="82790-117">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="82790-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="82790-118">安全連結的全域設定所提供的功能僅適用于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="82790-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="82790-119">沒有內建或預設的安全連結原則，因此您必須建立至少一個安全連結原則，這些全域設定才會作用。</span><span class="sxs-lookup"><span data-stu-id="82790-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="82790-120">如需相關指示，請參閱 [設定 Office 365 ATP 中的安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="82790-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="82790-121">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="82790-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="82790-122">若要直接移至 [ **ATP 安全連結** ] 頁面，請使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="82790-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="82790-123">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="82790-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="82790-124">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="82790-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="82790-125">若要查看及設定安全連結的全域設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="82790-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="82790-126">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="82790-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="82790-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**組織管理**。</span><span class="sxs-lookup"><span data-stu-id="82790-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="82790-128">如需安全連結之全域設定的建議值，請參閱 [安全連結設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="82790-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="82790-129">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="82790-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="82790-130">[我們會持續將新功能新增至 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="82790-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="82790-131">新增新功能時，您可能需要調整現有的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="82790-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="82790-132">在安全性 & 規範中心設定「阻止下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="82790-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="82790-133">**Block 下列 URLs**清單會識別在支援的應用程式中，安全連結掃描時，應攔截的連結。</span><span class="sxs-lookup"><span data-stu-id="82790-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="82790-134">如需詳細資訊，請參閱 [安全連結的「封鎖下列 URLs」清單](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="82790-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="82790-135">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="82790-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="82790-136">在 **您的組織的安全連結原則** 中，會出現 [飛出]，請移至 [ **封鎖下列 URLs] 方塊** 。</span><span class="sxs-lookup"><span data-stu-id="82790-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="82790-137">設定一或多個專案，如 ["封鎖下列 URLs 的專案語法](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述] 清單。</span><span class="sxs-lookup"><span data-stu-id="82790-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="82790-138">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82790-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="82790-139">設定 PowerShell 中的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="82790-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="82790-140">如需輸入語法的詳細資訊，請參閱「 [封鎖下列 URLs 的輸入語法」清單](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="82790-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="82790-141">您可以使用 **AtpPolicyForO365** Cmdlet 來查看 _BlockURLs_ 屬性中的現有專案。</span><span class="sxs-lookup"><span data-stu-id="82790-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="82790-142">若要新增將取代任何現有專案的值，請在 Exchange Online 中使用下列語法 PowerShell 或 Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82790-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="82790-143">本範例會將下列專案新增至清單：</span><span class="sxs-lookup"><span data-stu-id="82790-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="82790-144">封鎖 fabrikam.com 的網域、子域及路徑。</span><span class="sxs-lookup"><span data-stu-id="82790-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="82790-145">封鎖子域調查，但不封鎖 tailspintoys.com 中的父網域或其他子域</span><span class="sxs-lookup"><span data-stu-id="82790-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="82790-146">若要新增或移除值，而不影響其他現有的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="82790-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="82790-147">本範例會為 adatum.com 新增新的專案，並移除 fabrikam.com 的專案。</span><span class="sxs-lookup"><span data-stu-id="82790-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="82790-148">在安全性 & 規範中心內設定 Office 365 應用程式的安全連結保護</span><span class="sxs-lookup"><span data-stu-id="82790-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="82790-149">Office 365 應用程式的安全連結保護適用于支援的 Office desktop、行動裝置和 web 應用程式中的檔。</span><span class="sxs-lookup"><span data-stu-id="82790-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="82790-150">如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="82790-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="82790-151">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="82790-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="82790-152">在已出現之 **組織的安全連結原則** 中，在 [ **電子郵件以外的內容設定** ] 區段中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="82790-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="82790-153">**Office 365 應用程式**：驗證切換是否為支援的 office 365 應用程式的安全連結：開啟開啟 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="82790-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="82790-154">**當使用者按一下安全連結時，請勿追蹤**：在支援的 Office 365 應用程式中，將切換移至左側以追蹤與封鎖的 URLs 相關的使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="82790-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="82790-155">**不要讓使用者點擊 [安全連結] 原始 URL**：確認切換是向右，以防止使用者在支援的 Office 365 應用程式中按一下原始的封鎖 URL： ![ 開啟 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="82790-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="82790-156">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82790-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="82790-157">在 PowerShell 中設定 Office 365 應用程式的安全連結保護</span><span class="sxs-lookup"><span data-stu-id="82790-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="82790-158">如果您不想使用 PowerShell 來設定 Office 365 應用程式的安全連結保護，請在 Exchange Online PowerShell 或 Exchange Online Protection 中使用下列語法 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82790-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="82790-159">此範例會針對 Office 365 應用程式中的安全連結保護設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="82790-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="82790-160">Office 365 應用程式的安全連結已開啟 (我們不會使用 _EnableSafeLinksForO365Clients_ 參數，預設值是 $true) 。</span><span class="sxs-lookup"><span data-stu-id="82790-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="82790-161">追蹤支援的 Office 365 應用程式中的封鎖 URLs 相關的使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="82790-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="82790-162">在支援的 Office 365 應用程式中，不允許使用者點擊至原始的封鎖 URL (我們不會使用 _AllowClickThrough_ 參數，預設值是 $false) 。</span><span class="sxs-lookup"><span data-stu-id="82790-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="82790-163">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="82790-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="82790-164">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="82790-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="82790-165">若要確認您是否已成功設定安全連結的全域設定 (**封鎖下列 URLs** 清單和 Office 365 app protection 設定) ，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="82790-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="82790-166">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，按一下 [ **通用設定**]，然後確認 [飛出] 中顯示的設定。</span><span class="sxs-lookup"><span data-stu-id="82790-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="82790-167">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="82790-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="82790-168">如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="82790-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>