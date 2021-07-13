---
title: 從 Office 365 E3 遷移至 Microsoft 365 商務版
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: 如果您有 Office 365 E3 訂閱，但沒有超過300名員工，請考慮切換至 Microsoft 365 商務進階版。
ms.openlocfilehash: c1b4da07b3bf28cce1a48424ab45cde6ea54d367
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394164"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="13a8e-103">從 Office 365 E3 遷移至 Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="13a8e-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="13a8e-104">Microsoft 365 商務進階版具有您的小型企業所需的一切，結合了最佳的雲端架構應用程式與簡單的裝置管理和安全性。</span><span class="sxs-lookup"><span data-stu-id="13a8e-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="13a8e-105">如果您目前已有 Office 365 E3 訂閱，但沒有超過300名員工，請考慮切換至 Microsoft 365 商務進階版以新增安全性功能。</span><span class="sxs-lookup"><span data-stu-id="13a8e-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="13a8e-106">遷移非常簡單：先切換授權，您的目前訂閱中的所有資料和使用者資訊仍會維護。</span><span class="sxs-lookup"><span data-stu-id="13a8e-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="13a8e-107">遷移之後，您必須設定 Microsoft 365 商務進階版中新增的功能。</span><span class="sxs-lookup"><span data-stu-id="13a8e-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="13a8e-108">Office 365 E3 和 Microsoft 365 商務進階版之間的差異</span><span class="sxs-lookup"><span data-stu-id="13a8e-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="13a8e-109">下表顯示 Microsoft 365 商務進階版和 Office 365 E3 之間的差異。</span><span class="sxs-lookup"><span data-stu-id="13a8e-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="13a8e-110">功能</span><span class="sxs-lookup"><span data-stu-id="13a8e-110">Feature</span></span>    | <span data-ttu-id="13a8e-111">Microsoft 365 商務進階版中的支援</span><span class="sxs-lookup"><span data-stu-id="13a8e-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="13a8e-112">Office 365 E3 中的支援</span><span class="sxs-lookup"><span data-stu-id="13a8e-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="13a8e-113">**內部部署**</span><span class="sxs-lookup"><span data-stu-id="13a8e-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="13a8e-114">Office 應用程式<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13a8e-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="13a8e-115">Microsoft 365 Apps 商務版</span><span class="sxs-lookup"><span data-stu-id="13a8e-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="13a8e-116">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="13a8e-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="13a8e-117">**雲端生產力應用程式**</span><span class="sxs-lookup"><span data-stu-id="13a8e-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="13a8e-118">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="13a8e-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="13a8e-119">每個信箱 50 GB 儲存量限制，而不限 Exchange Online 封存</span><span class="sxs-lookup"><span data-stu-id="13a8e-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="13a8e-120">每個信箱 100 GB 儲存量限制，而不限 Exchange Online 封存</span><span class="sxs-lookup"><span data-stu-id="13a8e-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="13a8e-121">Teams</span><span class="sxs-lookup"><span data-stu-id="13a8e-121">Teams</span></span>    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="13a8e-124">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="13a8e-124">OneDrive for Business</span></span>    | <span data-ttu-id="13a8e-125">每個使用者 1 TB 的儲存空間限制</span><span class="sxs-lookup"><span data-stu-id="13a8e-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="13a8e-126">無限制</span><span class="sxs-lookup"><span data-stu-id="13a8e-126">Unlimited</span></span> | 
| <span data-ttu-id="13a8e-127">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="13a8e-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="13a8e-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="13a8e-130">StaffHub</span></span>    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="13a8e-133">**威脅防護**</span><span class="sxs-lookup"><span data-stu-id="13a8e-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="13a8e-134">適用於 Office 365 的 Defender 方案 1</span><span class="sxs-lookup"><span data-stu-id="13a8e-134">Defender for Office 365 Plan 1</span></span> | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | <span data-ttu-id="13a8e-136">不包含，但可以新增于</span><span class="sxs-lookup"><span data-stu-id="13a8e-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="13a8e-137">**身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="13a8e-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="13a8e-138">混合式 Azure Active Directory 的自助密碼重設 (Azure ad) 帳戶，azure ad 多重要素驗證 (MFA) ，條件式存取，針對內部部署身分識別的密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="13a8e-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    |  |
| <span data-ttu-id="13a8e-140">**裝置和應用程式管理**</span><span class="sxs-lookup"><span data-stu-id="13a8e-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="13a8e-141">Microsoft Intune，Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="13a8e-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    |  |
| <span data-ttu-id="13a8e-143">共用電腦啟用</span><span class="sxs-lookup"><span data-stu-id="13a8e-143">Shared computer activation</span></span>|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="13a8e-146">從 Win 7/8.1 Pro 授權 Windows 10 專業版的升級許可權</span><span class="sxs-lookup"><span data-stu-id="13a8e-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    ||
| <span data-ttu-id="13a8e-148">**資訊保護**</span><span class="sxs-lookup"><span data-stu-id="13a8e-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="13a8e-149">Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="13a8e-149">Office 365 Data Loss Prevention</span></span>|    ![包含 Microsoft 365 商務進階版](../media/check-mark.png)|![包含 Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="13a8e-152">Azure 資訊保護方案1，BitLocker 強制執行</span><span class="sxs-lookup"><span data-stu-id="13a8e-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![包含 Microsoft 365 商務進階版](../media/check-mark.png)||
|<span data-ttu-id="13a8e-154">Azure 資訊保護方案1，敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="13a8e-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![包含 Microsoft 365 商務進階版](../media/check-mark.png)||
|<span data-ttu-id="13a8e-156">**用戶端存取許可證 (CAL 許可權)**</span><span class="sxs-lookup"><span data-stu-id="13a8e-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="13a8e-157">EnterpriseCAL 套件 (Exchange、SharePoint、Skype) </span><span class="sxs-lookup"><span data-stu-id="13a8e-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![包含 Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="13a8e-159"><sup>1</sup> Office 應用程式的 Microsoft 365 商務進階版版本不包括透過群組原則、應用程式遙測、更新控制項、試算表比較和查詢或商務智慧的大量啟用。</span><span class="sxs-lookup"><span data-stu-id="13a8e-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="13a8e-160">移轉</span><span class="sxs-lookup"><span data-stu-id="13a8e-160">Migration</span></span>

<span data-ttu-id="13a8e-161">若要 Microsoft 365 商務進階版將您的訂閱遷移，請參閱[手動變更計畫](../commerce/subscriptions/change-plans-manually.md)，以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="13a8e-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="13a8e-162">您也可以[自動升級所有人](../commerce/subscriptions/upgrade-to-different-plan.md)，或與合作夥伴合作，將 E3 訂閱和授權移至 Microsoft 365 商務進階版訂閱。</span><span class="sxs-lookup"><span data-stu-id="13a8e-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="13a8e-163">下列各節說明您需要做的變更（若有的話），以及遷移後可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="13a8e-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="13a8e-164">Office 365 E3 訂閱設定和資料</span><span class="sxs-lookup"><span data-stu-id="13a8e-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="13a8e-165">您不需要在遷移之前對目前的訂閱或資料做任何變更，包括：</span><span class="sxs-lookup"><span data-stu-id="13a8e-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="13a8e-166">訂閱設定，例如 DNS 記錄和功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="13a8e-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="13a8e-167">使用者和群群組帳戶及驗證設定，例如多重因素驗證或條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="13a8e-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="13a8e-168">生產力服務設定及其資料，例如 Teams、Exchange Online 信箱、SharePoint 線上網站、商務用 OneDrive 資料夾及 OneNote 筆記本。</span><span class="sxs-lookup"><span data-stu-id="13a8e-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="13a8e-169">Office 應用程式會自動縮放。</span><span class="sxs-lookup"><span data-stu-id="13a8e-169">Office applications will scale automatically.</span></span> <span data-ttu-id="13a8e-170">Office 365 新式授權會每72小時檢查一次使用者的授權指派，並將 Office 應用程式轉換成符合使用者訂閱的版本。</span><span class="sxs-lookup"><span data-stu-id="13a8e-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="13a8e-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="13a8e-171">Windows 10</span></span>

<span data-ttu-id="13a8e-172">如果您的 Windows 尚未 Windows Pro 建立者更新，請[將其升級為 Windows Pro 創意者更新](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="13a8e-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="13a8e-173">設定保護使用者裝置及檔的原則</span><span class="sxs-lookup"><span data-stu-id="13a8e-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="13a8e-174">如果您設定 Office 365 MDM 原則和裝置，這些裝置將會列在 Microsoft 365 系統管理中心的 [**裝置**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="13a8e-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="13a8e-175">您設定的任何原則都會顯示在 [Intune 入口網站](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)的經典原則清單中。</span><span class="sxs-lookup"><span data-stu-id="13a8e-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="13a8e-176">指派授權給 Microsoft 365 商務進階版之後，您可以開始保護使用者的裝置和檔案。</span><span class="sxs-lookup"><span data-stu-id="13a8e-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="13a8e-177">如果您已將組織中的每個人升級為 Microsoft 365 商務進階版，您會在首頁上看到安裝精靈，並且可以遵循[安裝精靈的設定 Microsoft 365 商務進階版中](set-up.md)的步驟，以保護檔案和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="13a8e-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="13a8e-178">您也可以在 [裝置] 頁面上完成這些步驟：</span><span class="sxs-lookup"><span data-stu-id="13a8e-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="13a8e-179">在系統管理中心的左側導覽中，移至 [ **裝置** \> **原則**]。</span><span class="sxs-lookup"><span data-stu-id="13a8e-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="13a8e-180">在 [ **裝置原則** ] 頁面上，選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="13a8e-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="13a8e-181">在 [ **新增原則** ] 窗格中，將原則命名為 [名稱]，然後從下拉式清單中選擇 **原則類型** 。</span><span class="sxs-lookup"><span data-stu-id="13a8e-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="13a8e-182">您可以設定應用程式原則來保護 Android 和 iPhone 裝置上的檔案，以及 Windows 10，也可以為擁有 Windows 10 裝置的公司設定裝置配置原則。</span><span class="sxs-lookup"><span data-stu-id="13a8e-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="13a8e-183">如需詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="13a8e-183">See the following links for details:</span></span>

  - [<span data-ttu-id="13a8e-184">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="13a8e-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="13a8e-185">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="13a8e-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="13a8e-186">設定 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="13a8e-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="13a8e-187">一旦您設定原則，您和您的員工便可以設定裝置：</span><span class="sxs-lookup"><span data-stu-id="13a8e-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="13a8e-188">如需 Windows 裝置的步驟，請參閱[設定 Microsoft 365 商務進階版使用者 Windows 裝置](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="13a8e-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="13a8e-189">如需 Android 手機和 iphone 的步驟，請參閱[為 Microsoft 365 商務進階版使用者設定行動裝置](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="13a8e-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="13a8e-190">信箱大小</span><span class="sxs-lookup"><span data-stu-id="13a8e-190">Mailbox Size</span></span>

<span data-ttu-id="13a8e-191">Microsoft 365 商務進階版在使用 Exchange Online 方案1時，其使用的儲存量限制為 50 GB。</span><span class="sxs-lookup"><span data-stu-id="13a8e-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="13a8e-192">在遷移至 Microsoft 365 商務進階版時，如果您的任何使用者超過 50 GB 的信箱儲存空間，建議您指派此使用者 Exchange Online 計畫2並移除 Exchange Online 方案1，因為這兩者都不可行。</span><span class="sxs-lookup"><span data-stu-id="13a8e-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="13a8e-193">威脅防護</span><span class="sxs-lookup"><span data-stu-id="13a8e-193">Threat protection</span></span>

<span data-ttu-id="13a8e-194">在遷移至 Microsoft 365 商務進階版後，您就能使用 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="13a8e-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="13a8e-195">如需概述，請參閱[Microsoft Defender Office 365](../security/office-365-security/defender-for-office-365.md) 。</span><span class="sxs-lookup"><span data-stu-id="13a8e-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="13a8e-196">若要設定，請參閱[設定保管庫連結](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，[設定保管庫附件](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，並[在 Office 365 中設定 Defender 的反網路釣魚](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)。</span><span class="sxs-lookup"><span data-stu-id="13a8e-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="13a8e-197">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="13a8e-197">Sensitivity labels</span></span>

<span data-ttu-id="13a8e-198">若要開始使用敏感度標籤，請參閱 [敏感度標籤](../compliance/sensitivity-labels.md) 和 [建立及管理敏感度標籤](../business-video/create-sensitivity-labels.md) 影片。</span><span class="sxs-lookup"><span data-stu-id="13a8e-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="13a8e-199">相關內容</span><span class="sxs-lookup"><span data-stu-id="13a8e-199">Related content</span></span>

<span data-ttu-id="13a8e-200">[手動變更方案](../commerce/subscriptions/change-plans-manually.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="13a8e-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="13a8e-201">[升級 Windows 裝置以 Windows 10 專業版](upgrade-to-windows-pro-creators-update.md) (影片) </span><span class="sxs-lookup"><span data-stu-id="13a8e-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="13a8e-202">[設定 Android 或 iOS 裝置的應用程式保護設定](app-protection-settings-for-android-and-ios.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="13a8e-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="13a8e-203">[設定或編輯 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="13a8e-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="13a8e-204">[]</span><span class="sxs-lookup"><span data-stu-id="13a8e-204">[]</span></span>

