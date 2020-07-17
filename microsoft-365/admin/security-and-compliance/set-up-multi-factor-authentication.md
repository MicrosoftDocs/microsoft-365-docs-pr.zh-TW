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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083535"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="bd555-103">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="bd555-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="bd555-104">根據您對[多重因素驗證 (MFA) 及其在 Microsoft 365 中支援](multi-factor-authentication-microsoft-365.md)的了解，是時候進行設定並將其階段推出至您的組織了。</span><span class="sxs-lookup"><span data-stu-id="bd555-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="bd555-105">開始之前，請先判斷這些特殊條件是否適用於您，並採取適當的動作：</span><span class="sxs-lookup"><span data-stu-id="bd555-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="bd555-106">如果您在 Windows 裝置上安裝有 Office 2013 用戶端，請[啟用新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="bd555-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="bd555-107">如果您使用 Active Directory 同盟服務 (AD FS) 搭配協力廠商目錄服務，請設定 Azure MFA 伺服器。</span><span class="sxs-lookup"><span data-stu-id="bd555-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="bd555-108">如需詳細資訊，請參閱 [Azure 多重因素驗證和協力廠商 VPN 解決方案搭配的進階腳本](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="bd555-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="bd555-109">將會在需要時向所有其他使用者要求執行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="bd555-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="bd555-110">如需詳細資料，請造訪[雙因素驗證方法和設定](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)。</span><span class="sxs-lookup"><span data-stu-id="bd555-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="bd555-111">步驟 1 ：決定要求您使用者使用 MFA 的方法</span><span class="sxs-lookup"><span data-stu-id="bd555-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="bd555-112">您必須是全域系統管理員才能設定或修改 MFA。</span><span class="sxs-lookup"><span data-stu-id="bd555-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="bd555-113">有三種方法可以要求您的使用者使用 MFA 登入。如需詳細資料，請參閱 [Microsoft 365 中的 MFA 支援](multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bd555-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="bd555-114">安全性預設值 (建議給小型企業使用)</span><span class="sxs-lookup"><span data-stu-id="bd555-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="bd555-115">如果您在 2019 年10 月 21 日之後購買訂閱或試用版，且未預期情況下提示您進行 MFA，則將自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="bd555-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="bd555-116">每一個新 Microsoft 365 訂閱都會自動開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="bd555-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="bd555-117">這表示每位使用者都必須設定 MFA，並在其行動裝置上安裝 Microsoft Authenticator 應用程式。</span><span class="sxs-lookup"><span data-stu-id="bd555-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="bd555-118">所有使用者都必須使用 Microsoft Authenticator 應用程式做為其額外驗證方法，且舊版驗證會被封鎖。</span><span class="sxs-lookup"><span data-stu-id="bd555-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="bd555-119">條件式存取原則 (建議用於企業) </span><span class="sxs-lookup"><span data-stu-id="bd555-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="bd555-120">使用者要在 MFA 註冊過程中選擇其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="bd555-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="bd555-121">依每一使用者帳戶 (不建議使用) </span><span class="sxs-lookup"><span data-stu-id="bd555-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="bd555-122">使用者要在 MFA 註冊過程中選擇其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="bd555-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="bd555-123">步驟 2：</span><span class="sxs-lookup"><span data-stu-id="bd555-123">Step 2.</span></span> <span data-ttu-id="bd555-124">對您的試驗使用者測試 MFA</span><span class="sxs-lookup"><span data-stu-id="bd555-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="bd555-125">如果您使用的是條件式存取原則或依每位使用者 MFA (不建議使用)，請選取您企業或組織中的試驗使用者來測試 MFA 註冊和登入。例如：</span><span class="sxs-lookup"><span data-stu-id="bd555-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="bd555-126">若要設定條件式存取原則，請建立試驗使用者群組，以及要求將 MFA 用於群組成員和所有應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="bd555-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="bd555-127">然後，將您的試驗使用者帳戶新增至群組中。</span><span class="sxs-lookup"><span data-stu-id="bd555-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="bd555-128">針對依每一名使用者 MFA，請一次為一名試驗使用者的使用者帳戶啟用 MFA。</span><span class="sxs-lookup"><span data-stu-id="bd555-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="bd555-129">與您的試驗使用者共同解決問題，以準備好順暢階段推出給對組織。</span><span class="sxs-lookup"><span data-stu-id="bd555-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="bd555-130">步驟 3：</span><span class="sxs-lookup"><span data-stu-id="bd555-130">Step 3.</span></span> <span data-ttu-id="bd555-131">通知組織 MFA 即將來臨</span><span class="sxs-lookup"><span data-stu-id="bd555-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="bd555-132">您可以使用電子郵件通知、走道海報、小組會議或正式訓練，以確保員工了解：</span><span class="sxs-lookup"><span data-stu-id="bd555-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="bd555-133">為什麼需要 MFA 才能登入</span><span class="sxs-lookup"><span data-stu-id="bd555-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="bd555-134">如何註冊以取得其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="bd555-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="bd555-135">註冊之後如何登入</span><span class="sxs-lookup"><span data-stu-id="bd555-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="bd555-136">如何變更其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="bd555-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="bd555-137">如何處理新智慧型手機等狀況</span><span class="sxs-lookup"><span data-stu-id="bd555-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="bd555-138">最重要的是，請確認您的員工了解***何時將要實施 MFA 需求***，以免使其措手不及。</span><span class="sxs-lookup"><span data-stu-id="bd555-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="bd555-139">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="bd555-139">Step 4.</span></span> <span data-ttu-id="bd555-140">向貴組織或使用者階段推出 MFA 需求</span><span class="sxs-lookup"><span data-stu-id="bd555-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="bd555-141">根據您所選擇的 MFA 需求方法，將 MFA 驗證階段推出至試驗測試人員以外的員工。</span><span class="sxs-lookup"><span data-stu-id="bd555-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="bd555-142">安全性預設</span><span class="sxs-lookup"><span data-stu-id="bd555-142">Security defaults</span></span>

<span data-ttu-id="bd555-143">您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性**窗格中，啟用或停用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="bd555-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="bd555-144">使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bd555-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="bd555-145">移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="bd555-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="bd555-146">在頁面底部，選取 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd555-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="bd555-147">選擇 [是]\*\*\*\* 可啟用安全性預設，以及 [否]\*\*\*\* 可停用安全性預設，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd555-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="bd555-148">如果您一直是使用[基準條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，以下是移轉為使用安全性預設值的方法。</span><span class="sxs-lookup"><span data-stu-id="bd555-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="bd555-149">移至 [條件式存取原則][](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 頁面。</span><span class="sxs-lookup"><span data-stu-id="bd555-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="bd555-150">選擇每個**開啟**的基準原則，並將**啟用原則**設定為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="bd555-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="bd555-151">移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="bd555-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="bd555-152">在頁面底部，選取 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd555-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="bd555-153">選擇 [是]\*\*\*\* 可啟用安全性預設，以及 [否]\*\*\*\* 可停用安全性預設，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd555-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="bd555-154">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="bd555-154">Conditional Access policies</span></span>

<span data-ttu-id="bd555-155">建立、設定及啟用適當的原則，以納入需要進行 MFA 登入的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="bd555-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="bd555-156">依每一使用者 MFA (不建議使用) </span><span class="sxs-lookup"><span data-stu-id="bd555-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="bd555-157">針對您的階段推出，為使用者帳戶啟用 MFA 功能。</span><span class="sxs-lookup"><span data-stu-id="bd555-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="bd555-158">支援您的員工</span><span class="sxs-lookup"><span data-stu-id="bd555-158">Supporting your employees</span></span>

<span data-ttu-id="bd555-159">當員工註冊並開始使用 MFA 登入時，請確認您的 IT 專家、IT 部門或服務支援人員能迅速回答問題並解決問題。</span><span class="sxs-lookup"><span data-stu-id="bd555-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="bd555-160">請參閱這篇文章，以取得有關[如何疑難排解 MFA 登入的資訊](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)。</span><span class="sxs-lookup"><span data-stu-id="bd555-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


