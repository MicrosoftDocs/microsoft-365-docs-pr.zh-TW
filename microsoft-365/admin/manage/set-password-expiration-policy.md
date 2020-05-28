---
title: 設定組織的密碼到期原則
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: '了解如何在 Microsoft 365 系統管理中心設定組織的密碼到期原則。 '
ms.openlocfilehash: a4d5f5240a6d4cca686b4809d05970b5e18b897f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399575"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="1e3f2-103">設定組織的密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="1e3f2-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e3f2-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-104">The admin center is changing.</span></span> <span data-ttu-id="1e3f2-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1e3f2-106">本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="1e3f2-107">如果您是使用者，則無權將密碼設為永不到期。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="1e3f2-108">請要求貴公司或學校的技術支援人員，為您執行本文所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="1e3f2-109">身為系統管理員，您可以將使用者密碼設為在指定天數後過期，或將密碼設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="1e3f2-110">根據預設，密碼會設定為在 90 天內過期。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="1e3f2-111">最新研究強烈指出強制密碼變更的弊大於利。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="1e3f2-112">它們會讓使用者選擇較弱的密碼、重複使用密碼或以容易被駭客猜測到的方式更新舊密碼。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="1e3f2-113">如果將密碼設定為永不到期，建議您啟用[多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="1e3f2-114">如果您要將使用者密碼設定在指定的時間量後到期，請遵循下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1e3f2-115">只有[全域系統管理員](../add-users/about-admin-roles.md)才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="1e3f2-116">在系統管理中心中，移至 [設定]\*\*\*\* \> [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="1e3f2-117">移至<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全性與隱私權</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="1e3f2-118">如果您不是全域系統管理員，就看不到 [安全性和隱私權] 選項。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="1e3f2-119">選取 [密碼到期原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="1e3f2-120">如果您不希望使用者必須變更密碼，請選取 [將使用者密碼設定為在幾天後到期]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="1e3f2-121">輸入密碼應到期的頻率。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-121">Type how often passwords should expire.</span></span> <span data-ttu-id="1e3f2-122">選擇介於 14 到 730 之間的天數。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="1e3f2-123">在第二個方塊中，輸入使用者何時應收到其密碼到期的通知，然後選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="1e3f2-124">Choose a number of days from 1 to 30.</span><span class="sxs-lookup"><span data-stu-id="1e3f2-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="1e3f2-125">使用者的密碼過期時，會收到通知 (顯示在其螢幕的右下角)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="1e3f2-126">關於密碼到期功能，您應知道的重要事項</span><span class="sxs-lookup"><span data-stu-id="1e3f2-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="1e3f2-127">有關這項功能截至 2018 年 1 月的運作情形，這裡是您需要了解的一些事項：</span><span class="sxs-lookup"><span data-stu-id="1e3f2-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="1e3f2-p107">在快取中的密碼過期之前，不會強制要求只使用 Outlook App 的使用者重設其 Microsoft 365 密碼。這可能會在實際到期日之後的數天發生。針對此問題，目前沒有系統管理員層級的因應措施。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="1e3f2-p108">使用者不會收到其密碼即將在 X 天後過期的電子郵件通知。您想要這項功能嗎？ **[在這裡投票！](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="1e3f2-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="1e3f2-134">避免再次使用上次的密碼</span><span class="sxs-lookup"><span data-stu-id="1e3f2-134">Prevent last password from being used again</span></span>

<span data-ttu-id="1e3f2-135">如果要避免使用者回收舊密碼，您可以在 Azure AD 中執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-135">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="1e3f2-136">請參閱[強制密碼歷程記錄](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-136">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="1e3f2-137">此外，如果某位員工使用行動裝置來存取 Microsoft 365，您可以將其清除，以確保不會從該位置儲存並回收密碼。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-137">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="1e3f2-138">若要進一步了解，請參閱[抹除及封鎖離職員工的行動裝置](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-138">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="1e3f2-139">將內部部署 Active Directory 的使用者密碼雜湊同步處理到 Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="1e3f2-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="1e3f2-140">本文用於為僅限雲端使用者 (Azure AD) 設定到期原則。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="1e3f2-141">不適用於使用密碼雜湊同步處理、傳遞驗證或內部部署同盟 (例如 ADFS) 的混合式身分識別使用者。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="1e3f2-142">若要了解如何將使用者密碼雜湊從內部部署 AD 同步處理到 Azure AD，請參閱[使用 Azure AD Connect 同步處理實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="1e3f2-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
