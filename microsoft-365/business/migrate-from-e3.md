---
title: 從 Office 365 E3 移轉至 Microsoft 365 商務版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: 了解如何將業務移至 Microsoft 365 商務版中，從 Office 365 E3。
ms.openlocfilehash: b86a163792aa71f0bca115ab918e0800acc0427d
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409678"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="877a3-103">從 Office 365 E3 移轉至 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="877a3-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="877a3-104">Microsoft 365 商務版具有您需要為您的小型企業，簡單的裝置管理與安全性結合最佳-雲端生產力應用程式的所有項目。</span><span class="sxs-lookup"><span data-stu-id="877a3-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="877a3-105">如果您目前有 Office 365 E3 訂閱，但沒有超過 300 個員工，請考慮新增的安全性功能切換至 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="877a3-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="877a3-106">移轉很簡單： 第一次切換授權和維護您目前訂閱中的所有資料和使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="877a3-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="877a3-107">移轉之後，您需要設定 Microsoft 365 商務版中加入的功能。</span><span class="sxs-lookup"><span data-stu-id="877a3-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="877a3-108">Office 365 E3 和 Microsoft 365 商務版之間的差異</span><span class="sxs-lookup"><span data-stu-id="877a3-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="877a3-109">此表說明 Microsoft 365 商務版和 Office 365 E3 之間的差異。</span><span class="sxs-lookup"><span data-stu-id="877a3-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="877a3-110">功能</span><span class="sxs-lookup"><span data-stu-id="877a3-110">Feature</span></span>    | <span data-ttu-id="877a3-111">支援在 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="877a3-111">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="877a3-112">支援 office 365 E3</span><span class="sxs-lookup"><span data-stu-id="877a3-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="877a3-113">**內部部署**</span><span class="sxs-lookup"><span data-stu-id="877a3-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="877a3-114">Office 應用程式<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="877a3-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="877a3-115">Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="877a3-115">Office 365 Business</span></span>    | <span data-ttu-id="877a3-116">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="877a3-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="877a3-117">**雲端生產力應用程式**</span><span class="sxs-lookup"><span data-stu-id="877a3-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="877a3-118">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="877a3-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="877a3-119">每個信箱和 unlimited Exchange Online Archiving 50 GB 儲存空間限制</span><span class="sxs-lookup"><span data-stu-id="877a3-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="877a3-120">每個信箱並無限制 Exchange Online 封存的 100 GB 儲存空間上限</span><span class="sxs-lookup"><span data-stu-id="877a3-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="877a3-121">Teams</span><span class="sxs-lookup"><span data-stu-id="877a3-121">Teams</span></span>    | ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | ![隨附於 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="877a3-124">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="877a3-124">OneDrive for Business</span></span>    | <span data-ttu-id="877a3-125">每個使用者 1 TB 的儲存量限制</span><span class="sxs-lookup"><span data-stu-id="877a3-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="877a3-126">無限制</span><span class="sxs-lookup"><span data-stu-id="877a3-126">Unlimited</span></span> | 
| <span data-ttu-id="877a3-127">Yammer，SharePoint Online，規劃中，資料流</span><span class="sxs-lookup"><span data-stu-id="877a3-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | ![隨附於 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="877a3-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="877a3-130">StaffHub</span></span>    | ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | ![隨附於 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="877a3-133">Outlook Customer Manager、 MileIQ</span><span class="sxs-lookup"><span data-stu-id="877a3-133">Outlook Customer Manager, MileIQ</span></span>    | ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | | 
| <span data-ttu-id="877a3-135">**威脅防護**</span><span class="sxs-lookup"><span data-stu-id="877a3-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="877a3-136">Office 365 進階的威脅防護 (ATP) 計劃 1</span><span class="sxs-lookup"><span data-stu-id="877a3-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | <span data-ttu-id="877a3-138">不包含在內，但是可以加上</span><span class="sxs-lookup"><span data-stu-id="877a3-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="877a3-139">**身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="877a3-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="877a3-140">自助密碼重設為混合式 Azure Active Directory (Azure AD) 帳戶，Azure 多重要素驗證 (MFA)、 條件式存取，適用於內部部署身分識別的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="877a3-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    |  | 
| <span data-ttu-id="877a3-142">**裝置和應用程式管理**</span><span class="sxs-lookup"><span data-stu-id="877a3-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="877a3-143">Microsoft Intune、 Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="877a3-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    |  |
| <span data-ttu-id="877a3-145">共用電腦啟用</span><span class="sxs-lookup"><span data-stu-id="877a3-145">Shared computer activation</span></span>|     ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    | ![隨附於 Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="877a3-148">升級到 Windows 10 專業版的權限，從 Win 7/8.1 專業版的授權</span><span class="sxs-lookup"><span data-stu-id="877a3-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![隨附於 Microsoft 365 商務版](../media/check-mark.png)    || 
| <span data-ttu-id="877a3-150">**資訊保護**</span><span class="sxs-lookup"><span data-stu-id="877a3-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="877a3-151">Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="877a3-151">Office 365 Data Loss Prevention</span></span>|    ![隨附於 Microsoft 365 商務版](../media/check-mark.png)|![隨附於 Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="877a3-154">Azure 資訊保護方案 1，Bitlocker 強制執行</span><span class="sxs-lookup"><span data-stu-id="877a3-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![隨附於 Microsoft 365 商務版](../media/check-mark.png)||
|<span data-ttu-id="877a3-156">Azure 資訊保護方案 1，敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="877a3-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![隨附於 Microsoft 365 商務版](../media/check-mark.png)||
|<span data-ttu-id="877a3-158">**用戶端存取使用權 （CAL 權限）**</span><span class="sxs-lookup"><span data-stu-id="877a3-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="877a3-159">企業 CAL 套件 (Exchange、 SharePoint、 Skype)</span><span class="sxs-lookup"><span data-stu-id="877a3-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![隨附於 Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="877a3-161"><sup>1</sup> Microsoft 365 商務版版本的 Office 應用程式不會包含大量啟用透過群組原則中，應用程式遙測，更新控制項、 試算表比較和查詢，或商務智慧。</span><span class="sxs-lookup"><span data-stu-id="877a3-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="877a3-162">移轉</span><span class="sxs-lookup"><span data-stu-id="877a3-162">Migration</span></span>

<span data-ttu-id="877a3-163">若要移轉您的訂閱，請參閱[手動變更計劃](../commerce/subscriptions/change-plans-manually.md)指示如果您想要將少數使用者移至 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="877a3-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="877a3-164">您也可以[自動升級所有人](../commerce/subscriptions/upgrade-to-different-plan.md)，或與合作夥伴移到 Microsoft 365 商務版訂閱版 E3 訂閱和授權工作。</span><span class="sxs-lookup"><span data-stu-id="877a3-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="877a3-165">下列各節說明您需要進行，如果有的話，所做的變更，您可以在移轉後執行的動作。</span><span class="sxs-lookup"><span data-stu-id="877a3-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="877a3-166">Office 365 E3 訂閱設定與資料</span><span class="sxs-lookup"><span data-stu-id="877a3-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="877a3-167">您不需要執行任何您目前訂閱或變更資料移轉之前，其中包含：</span><span class="sxs-lookup"><span data-stu-id="877a3-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="877a3-168">訂閱設定，例如 DNS 記錄及網域名稱。</span><span class="sxs-lookup"><span data-stu-id="877a3-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="877a3-169">使用者和群組帳戶和驗證設定，例如多因素驗證] 或 [條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="877a3-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="877a3-170">生產力服務設定和其資料，例如 Exchange Online 信箱、 SharePoint Online 網站的小組 OneDrive for Business 資料夾及 OneNote 筆記本。</span><span class="sxs-lookup"><span data-stu-id="877a3-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="877a3-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="877a3-171">Windows 10</span></span>

<span data-ttu-id="877a3-172">如果您的 Windows 已經不在 Windows Pro Creator 更新，[升級到 Windows 專業人員的 Creators Update](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="877a3-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="877a3-173">設定原則來保護使用者裝置和檔案</span><span class="sxs-lookup"><span data-stu-id="877a3-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="877a3-174">如果您設定 Office 365 MDM 原則和裝置，那些裝置將會列在 [**裝置**] 頁面上，在 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="877a3-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="877a3-175">[Intune 入口網站](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)中的傳統原則清單中，會顯示您所設定的任何原則。</span><span class="sxs-lookup"><span data-stu-id="877a3-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="877a3-176">您已指派授權給 Microsoft 365 商務版之後，您可以開始保護使用者的裝置和檔案。</span><span class="sxs-lookup"><span data-stu-id="877a3-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="877a3-177">如果您升級所有人組織 Microsoft 365 商務版中，您會看到安裝精靈] 在 [首頁] 頁面，並可以依照[設定安裝程式精靈] 中的 Microsoft 365 商務版](set-up.md)來保護檔案和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="877a3-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="877a3-178">您也可以完成下列步驟，在 [裝置] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="877a3-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="877a3-179">在系統管理中心中，在左側導覽中，移至 [**裝置** \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="877a3-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="877a3-180">在 [**裝置原則**] 頁面上，選擇 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="877a3-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="877a3-181">在 [**新增原則**] 窗格中輸入原則的名稱，，然後從下拉式清單中選擇 [**原則類型**。</span><span class="sxs-lookup"><span data-stu-id="877a3-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="877a3-182">您可以設定應用程式原則保護 Android 和 iPhone 裝置以及 Windows 10 上的檔案，您可以設定公司擁有 Windows 10 裝置的裝置設定原則。</span><span class="sxs-lookup"><span data-stu-id="877a3-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="877a3-183">請參閱下列連結，如需詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="877a3-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="877a3-184">設定 Android 或 iOS 裝置的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="877a3-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="877a3-185">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="877a3-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="877a3-186">設定適用於 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="877a3-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="877a3-187">一旦您設定原則時，您和您的員工可以設定裝置：</span><span class="sxs-lookup"><span data-stu-id="877a3-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="877a3-188">如需 Windows 裝置步驟，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="877a3-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="877a3-189">如需 Android 手機和 Iphone 步驟，請參閱[為 Microsoft 365 商務版使用者的行動裝置上設定](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="877a3-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="877a3-190">威脅防護</span><span class="sxs-lookup"><span data-stu-id="877a3-190">Threat protection</span></span>

<span data-ttu-id="877a3-191">移轉至 Microsoft 365 商務版之後，您有 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="877a3-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="877a3-192">如需概觀，請參閱[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 。</span><span class="sxs-lookup"><span data-stu-id="877a3-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="877a3-193">若要設定，請參閱[設定 ATP 安全連結](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)、[設定 ATP 安全附件](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)和[設定 ATP 防網路釣魚](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)。</span><span class="sxs-lookup"><span data-stu-id="877a3-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="877a3-194">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="877a3-194">Sensitivity labels</span></span>

<span data-ttu-id="877a3-195">若要開始使用敏感度標籤，請參閱[Overview of 敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)[建立及管理敏感度標籤](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)視訊。</span><span class="sxs-lookup"><span data-stu-id="877a3-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
