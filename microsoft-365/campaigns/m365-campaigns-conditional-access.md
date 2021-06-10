---
title: 開啟安全性預設值
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解安全性預設如何協助您提供預先設定的安全性設定，以保護您的組織免受身分識別相關的攻擊。
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398288"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="96cdf-103">開啟安全性預設值</span><span class="sxs-lookup"><span data-stu-id="96cdf-103">Turn on security defaults</span></span>

<span data-ttu-id="96cdf-104">安全性預設值可提供 Microsoft 代表組織所管理的預先設定安全性設定，協助保護您的組織免受身分識別相關的攻擊。</span><span class="sxs-lookup"><span data-stu-id="96cdf-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="96cdf-105">這些設定包括針對所有系統管理員和使用者帳戶啟用多重要素驗證 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="96cdf-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="96cdf-106">對大多數的組織而言，安全性預設值提供好的額外登入安全性。</span><span class="sxs-lookup"><span data-stu-id="96cdf-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="96cdf-107">如需安全性預設值及其強制原則的詳細資訊，請參閱 [安全性預設值為何？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="96cdf-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="96cdf-108">如果您的訂閱是在10月22日2019（或後）完成，則會自動啟用安全性預設值，您 &mdash; 應該檢查您的設定以確認。</span><span class="sxs-lookup"><span data-stu-id="96cdf-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="96cdf-109">若要在 Azure Active Directory (Azure AD) 中啟用安全性預設值，或查看是否已啟用這些預設值：</span><span class="sxs-lookup"><span data-stu-id="96cdf-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="96cdf-110">使用全域系統管理員認證登入<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="96cdf-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="96cdf-111">在左窗格中，選取 [**全部顯示]，** 然後在 [系統 **管理中心**] 底下，選取 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="96cdf-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="96cdf-112">在 **Azure Active Directory 系統管理中心** 的左窗格中，選取 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="96cdf-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="96cdf-113">從儀表板的左側功能表中，選取 [ **管理** ] 區段中的 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="96cdf-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Azure Active Directory 系統管理中心的螢幕擷取畫面，顯示內容功能表項目目的位置。":::

5. <span data-ttu-id="96cdf-115">在 [ **屬性** ] 頁面的底部，選取 [ **管理安全性預設值**]。</span><span class="sxs-lookup"><span data-stu-id="96cdf-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="96cdf-116">在右窗格中，您將會看到 [ **啟用安全性預設值** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="96cdf-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="96cdf-117">如果選取 **[是]** ，則安全性預設值已啟用，不需要進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="96cdf-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="96cdf-118">如果目前未啟用安全性預設值，請選取 **[是]** 加以啟用，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="96cdf-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="96cdf-119">如果您已使用條件式存取原則，則必須在使用安全性預設值之前將其關閉。</span><span class="sxs-lookup"><span data-stu-id="96cdf-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="96cdf-120">您可以使用安全性預設值或條件式存取原則，但不能同時使用這兩種原則。</span><span class="sxs-lookup"><span data-stu-id="96cdf-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="96cdf-121">考慮使用條件式存取</span><span class="sxs-lookup"><span data-stu-id="96cdf-121">Consider using Conditional Access</span></span>

<span data-ttu-id="96cdf-122">如果您的組織有複雜的安全性需求，或需要更細微地控制安全性原則，則應該考慮使用條件式存取，而不是安全性預設值，以取得類似或更高的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="96cdf-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="96cdf-123">條件式存取可讓您建立及定義回應登入事件並在使用者獲准存取應用程式或服務之前要求其他動作的原則。</span><span class="sxs-lookup"><span data-stu-id="96cdf-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="96cdf-124">條件式存取原則可以細微且特定，可讓使用者在任何時刻和何地都能獲得生產力，但同時也會保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="96cdf-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="96cdf-125">安全性預設值可供所有客戶使用，而條件式存取需要授權執行下列其中一個計畫：</span><span class="sxs-lookup"><span data-stu-id="96cdf-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="96cdf-126">Azure Active Directory 進階版 P1 或 P2</span><span class="sxs-lookup"><span data-stu-id="96cdf-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="96cdf-127">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="96cdf-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="96cdf-128">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="96cdf-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="96cdf-129">Enterprise行動 & 安全性 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="96cdf-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="96cdf-130">如果您想要使用條件式存取來設定與安全性預設啟用的原則同等的原則，請參閱下列逐步指南：</span><span class="sxs-lookup"><span data-stu-id="96cdf-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="96cdf-131">要求系統管理員使用 MFA</span><span class="sxs-lookup"><span data-stu-id="96cdf-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="96cdf-132">Azure 管理需要 MFA</span><span class="sxs-lookup"><span data-stu-id="96cdf-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="96cdf-133">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="96cdf-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="96cdf-134">要求所有使用者使用 MFA</span><span class="sxs-lookup"><span data-stu-id="96cdf-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="96cdf-135">[需要 azure ad MFA 註冊](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)-需要 azure ad 身分識別保護，也就是 Azure Active Directory 進階版 P2 的一部分</span><span class="sxs-lookup"><span data-stu-id="96cdf-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="96cdf-136">若要深入瞭解條件式存取，請參閱 [什麼是條件式存取？](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="96cdf-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="96cdf-137">如需建立條件式存取原則的詳細資訊，請參閱 [建立條件式存取原則](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。</span><span class="sxs-lookup"><span data-stu-id="96cdf-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="96cdf-138">如果您有提供條件式存取的計畫或授權，但尚未建立任何條件式存取原則，您可以使用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="96cdf-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="96cdf-139">不過，您必須先關閉安全性預設值，才能使用條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="96cdf-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
