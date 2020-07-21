---
title: 為使用者設定多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何為您的組織設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 34133f4204c1ee305b0a249a0ff8e0e9edaf5599
ms.sourcegitcommit: e891c7c25f351f10f250af3f483f68594976ddc9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153674"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="37452-103">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="37452-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="37452-104">根據您對[多重因素驗證 (MFA) 及其在 Microsoft 365 中支援](multi-factor-authentication-microsoft-365.md)的了解，是時候進行設定並將其階段推出至您的組織了。</span><span class="sxs-lookup"><span data-stu-id="37452-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37452-105">如果您在 2019 年10 月 21 日之後購買訂閱或試用版，且在您登入時，提示您進行 MFA，則將自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="37452-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="37452-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="37452-106">Before you begin</span></span>

- <span data-ttu-id="37452-107">您必須是全域系統管理員才能管理 MFA。</span><span class="sxs-lookup"><span data-stu-id="37452-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="37452-108">如需詳細資訊，請參閱[系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="37452-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="37452-109">如果您已開啟舊版每人 MFA，請 [關閉舊版每人 MFA](#turn-off-legacy-per-person-mfa)。</span><span class="sxs-lookup"><span data-stu-id="37452-109">If you have legacy per person MFA turned on, [Turn off legacy per person MFA](#turn-off-legacy-per-person-mfa).</span></span>
- <span data-ttu-id="37452-110">如果您在 Windows 裝置上安裝有 Office 2013 用戶端，請[開啟 Office 2013 用戶端新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="37452-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="37452-111">進階版: 如果您使用 Active Directory 同盟服務 (AD FS) 搭配協力廠商目錄服務，請設定 Azure MFA 伺服器。</span><span class="sxs-lookup"><span data-stu-id="37452-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="37452-112">如需詳細資訊，請參閱 [Azure 多重因素驗證和協力廠商 VPN 解決方案搭配的進階腳本](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="37452-112">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="37452-113">開啟或關閉安全性預設值</span><span class="sxs-lookup"><span data-stu-id="37452-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="37452-114">大部分的組織，安全性預設值皆提供有良好的額外登入安全性。</span><span class="sxs-lookup"><span data-stu-id="37452-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="37452-115">如需詳細資訊，請參閱[什麼是安全性預設？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="37452-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="37452-116">如果您新訂閱，則系統可能會自動為您開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="37452-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="37452-117">您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性**窗格中，啟用或停用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="37452-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="37452-118">使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="37452-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="37452-119">在左側導覽中，請選擇 **[顯示所有]**，然後在 **[系統管理中心]** 底下，選擇 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="37452-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="37452-120">在 **[Azure Active Directory 系統管理中心]** 選擇 **[Azure Active Directory** > **屬性]**。</span><span class="sxs-lookup"><span data-stu-id="37452-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** > **Properties**.</span></span>
3.  <span data-ttu-id="37452-121">在頁面底部，選取 **[管理安全性預設]**。</span><span class="sxs-lookup"><span data-stu-id="37452-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="37452-122">選擇 **[是]** 以啟用安全性預設，或 **[否]** 以停用安全性預設，然後選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="37452-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="37452-123">如果您使用的是[基準條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，則會在您移往使用安全性預設之前，提示您將之關閉。</span><span class="sxs-lookup"><span data-stu-id="37452-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1.  <span data-ttu-id="37452-124">移至 [條件式存取原則][](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 頁面。</span><span class="sxs-lookup"><span data-stu-id="37452-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="37452-125">選擇每個**開啟**的基準原則，並將**啟用原則**設定為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="37452-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="37452-126">移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="37452-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="37452-127">在頁面底部，選取 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37452-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="37452-128">選擇 [是]\*\*\*\* 可啟用安全性預設，以及 [否]\*\*\*\* 可停用安全性預設，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37452-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="37452-129">使用 [條件式存取] 原則</span><span class="sxs-lookup"><span data-stu-id="37452-129">Use Conditional Access policies</span></span>

<span data-ttu-id="37452-130">如果貴組織有更仔細的登入安全需求，[條件式存取] 原則可讓您有更多控制權。</span><span class="sxs-lookup"><span data-stu-id="37452-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="37452-131">[條件式存取] 允許您建立並定義原則条件，在使用人被授權對應用程式或服務的存取之前反應登入事件和請求附加操作。</span><span class="sxs-lookup"><span data-stu-id="37452-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37452-132">在啟用條件式存取原則之前，請關閉 [每人 MFA] 和 [安全性預設]。</span><span class="sxs-lookup"><span data-stu-id="37452-132">Turn off both per person MFA and Security defaults before you enable Conditional Access policies.</span></span> 

<span data-ttu-id="37452-133">購買 Azure AD Premium P1 的客戶或含此授權的授權（例如 Microsoft 365 商務版 Premium）和 Microsoft 365 E3 皆可使用條件式存取。</span><span class="sxs-lookup"><span data-stu-id="37452-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="37452-134">如需詳細資訊，請參閱[建立 [條件式存取] 原則](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)。</span><span class="sxs-lookup"><span data-stu-id="37452-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="37452-135">透過 Azure AD Premium P2 授權或含此授權的授權（例如 Microsoft 365 E5）可使用風險型條件式存取。</span><span class="sxs-lookup"><span data-stu-id="37452-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licences that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="37452-136">如需詳細資訊，請參閱 [風險型 [條件式存取]](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。</span><span class="sxs-lookup"><span data-stu-id="37452-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="37452-137">如需有關 Azure AD P1 和 P2 的詳細資訊，請參閱 [Azure Active Directory 定價](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="37452-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="37452-138">為您的組織開啟 [新式] 驗證。</span><span class="sxs-lookup"><span data-stu-id="37452-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="37452-139">對於大多數訂閱而言，[新式] 驗證會自動開啟，但如果您是在很久以前購買訂閱的話，則可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="37452-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="37452-140">這必須在 MFA 以 Office 應用程式正常運作之前開啟。</span><span class="sxs-lookup"><span data-stu-id="37452-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="37452-141">在 Microsoft 365 系統管理中心的左側導覽中，選擇 **[設定]** > \*\* [組織設定]\*\*。</span><span class="sxs-lookup"><span data-stu-id="37452-141">In the Microsoft 365 admin center, in the left nav choose **Settings** > **Org settings**.</span></span>
1. <span data-ttu-id="37452-142">在 **[服務]** 索引標籤底下，選擇 **[新式驗證]**，然後在 **[新式驗證]** 窗格中，確保 **[啟用新式驗證]** 已選取。</span><span class="sxs-lookup"><span data-stu-id="37452-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="37452-143">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="37452-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-person-mfa"></a><span data-ttu-id="37452-144">關閉舊版的每人 MFA</span><span class="sxs-lookup"><span data-stu-id="37452-144">Turn off legacy per person MFA</span></span>

<span data-ttu-id="37452-145">如果您先前已開啟每人 MFA，您必須先將它關閉才能啟用安全性預設。</span><span class="sxs-lookup"><span data-stu-id="37452-145">If you have previously turned on per person MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="37452-146">在 Microsoft 365 系統管理中心的左側導覽中，選擇 **[使用者]** > \*\* [使用中的使用者]\*\*。</span><span class="sxs-lookup"><span data-stu-id="37452-146">In the Microsoft 365 admin center, in the left nav choose **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="37452-147">在 **[使用中的使用者]** 頁面中，選擇 **[多重要素驗證]**。</span><span class="sxs-lookup"><span data-stu-id="37452-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="37452-148">在多重要素驗證頁面上，選取每個使用者並將其 [多重要素驗證] 狀態設為 **停用**。</span><span class="sxs-lookup"><span data-stu-id="37452-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37452-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="37452-149">Next steps</span></span>

- [<span data-ttu-id="37452-150">如何註冊以取得其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="37452-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="37452-151">註冊之後如何登入</span><span class="sxs-lookup"><span data-stu-id="37452-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="37452-152">如何變更其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="37452-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="37452-153">如何處理新智慧型手機等狀況</span><span class="sxs-lookup"><span data-stu-id="37452-153">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)
- [<span data-ttu-id="37452-154">疑難排解 MFA 登入</span><span class="sxs-lookup"><span data-stu-id="37452-154">Troubleshoot MFA sign-ins</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)




