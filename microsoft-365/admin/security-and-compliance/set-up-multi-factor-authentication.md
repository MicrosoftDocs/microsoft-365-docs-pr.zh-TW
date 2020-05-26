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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 瞭解如何為您的組織設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: ca1a8bd47e2fa5bbd7b7aed396debefaad10ea5e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351712"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a1494-103">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="a1494-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="a1494-104">根據您對[Microsoft 365 中的多重要素驗證（MFA）和支援](multi-factor-authentication-microsoft-365.md)的瞭解，您可以將它設定好，並將其部署至您的組織。</span><span class="sxs-lookup"><span data-stu-id="a1494-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="a1494-105">開始之前，請先確定這些特殊條件是否適用于您並採取適當的動作：</span><span class="sxs-lookup"><span data-stu-id="a1494-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="a1494-106">如果您有 Windows 裝置上的 Office 2013 用戶端，請[啟用新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="a1494-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="a1494-107">如果您有使用 Active Directory Federation Services （AD FS）的協力廠商目錄服務，請設定 Azure MFA 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1494-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="a1494-108">如需詳細資訊，請參閱[使用 Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="a1494-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="a1494-109">步驟1：決定要求使用者使用 MFA 的方法</span><span class="sxs-lookup"><span data-stu-id="a1494-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="a1494-110">有三種方式可要求使用者使用 MFA 進行登入。如需詳細資訊，請參閱[Microsoft 365 中的 MFA 支援](multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a1494-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="a1494-111">安全性預設值（適用于小型企業的建議）</span><span class="sxs-lookup"><span data-stu-id="a1494-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="a1494-112">如果您在2019年10月21日之後購買訂閱或試用版，且意外提示您進行 MFA，[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)會自動為您的訂閱啟用。</span><span class="sxs-lookup"><span data-stu-id="a1494-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="a1494-113">每個新的 Microsoft 365 訂閱都會自動開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="a1494-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="a1494-114">這表示每位使用者都必須在其行動裝置上設定 MFA，並安裝 Microsoft 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="a1494-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="a1494-115">所有使用者都必須使用 Microsoft 驗證應用程式作為其他驗證方法，而且會封鎖舊版驗證。</span><span class="sxs-lookup"><span data-stu-id="a1494-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="a1494-116">條件式存取原則（建議企業使用）</span><span class="sxs-lookup"><span data-stu-id="a1494-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="a1494-117">使用者在 MFA 登記期間選擇其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="a1494-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="a1494-118">每個使用者帳戶（不建議）</span><span class="sxs-lookup"><span data-stu-id="a1494-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="a1494-119">使用者在 MFA 登記期間選擇其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="a1494-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="a1494-120">步驟 2：</span><span class="sxs-lookup"><span data-stu-id="a1494-120">Step 2.</span></span> <span data-ttu-id="a1494-121">在試驗使用者上測試 MFA</span><span class="sxs-lookup"><span data-stu-id="a1494-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="a1494-122">如果您使用的是條件式存取原則或個別使用者 MFA （不建議使用），請在您的公司或組織中選取試驗使用者，以測試 MFA 註冊和登入。例如：</span><span class="sxs-lookup"><span data-stu-id="a1494-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="a1494-123">針對條件式存取原則，建立試驗使用者群組和需要 MFA 做為群組成員及所有應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="a1494-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="a1494-124">然後，將試驗使用者的帳戶新增至群組。</span><span class="sxs-lookup"><span data-stu-id="a1494-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="a1494-125">針對每一使用者 MFA，一次可對您的試驗使用者的使用者帳戶啟用 MFA。</span><span class="sxs-lookup"><span data-stu-id="a1494-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="a1494-126">請與您的試驗使用者合作，以解決問題，以準備您的組織的順利推出。</span><span class="sxs-lookup"><span data-stu-id="a1494-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="a1494-127">步驟 3：</span><span class="sxs-lookup"><span data-stu-id="a1494-127">Step 3.</span></span> <span data-ttu-id="a1494-128">通知組織即將推出 MFA</span><span class="sxs-lookup"><span data-stu-id="a1494-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="a1494-129">使用電子郵件通知、hallway 海報、小組會議或正式訓練，以確保您的員工瞭解：</span><span class="sxs-lookup"><span data-stu-id="a1494-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="a1494-130">為何登入需要 MFA</span><span class="sxs-lookup"><span data-stu-id="a1494-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="a1494-131">如何註冊以進行其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="a1494-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="a1494-132">註冊後如何登入</span><span class="sxs-lookup"><span data-stu-id="a1494-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="a1494-133">如何變更其其他驗證方法</span><span class="sxs-lookup"><span data-stu-id="a1494-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="a1494-134">如何處理類似于新智慧型電話的情況</span><span class="sxs-lookup"><span data-stu-id="a1494-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="a1494-135">最重要的是，請確定您***的員工瞭解何時要強制執行 MFA 需求***，使其不會令人感到驚訝。</span><span class="sxs-lookup"><span data-stu-id="a1494-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="a1494-136">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="a1494-136">Step 4.</span></span> <span data-ttu-id="a1494-137">向您的組織或使用者推出 MFA 需求</span><span class="sxs-lookup"><span data-stu-id="a1494-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="a1494-138">根據您所選擇的 MFA 需求方法，將 MFA 驗證向外推行您的試驗測試人員之外的員工。</span><span class="sxs-lookup"><span data-stu-id="a1494-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="a1494-139">安全性預設</span><span class="sxs-lookup"><span data-stu-id="a1494-139">Security defaults</span></span>

<span data-ttu-id="a1494-140">您可以在 Azure 入口網站中，從 Azure Active Directory （Azure AD）的**屬性**窗格中啟用或停用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="a1494-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="a1494-141">使用全域系統管理員認證登入[Microsoft 365 admin center](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="a1494-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="a1494-142">移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="a1494-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="a1494-143">在頁面底部，選擇 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1494-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="a1494-144">選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a1494-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="a1494-145">如果您已使用[基準條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，以下是您移至使用安全性預設值的方式。</span><span class="sxs-lookup"><span data-stu-id="a1494-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="a1494-146">移至 [[條件式存取原則] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="a1494-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="a1494-147">選擇 [**開啟**的每一個基準原則]，並將 [**啟用原則**] 設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a1494-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="a1494-148">移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="a1494-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="a1494-149">在頁面底部，選擇 [管理安全性預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1494-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="a1494-150">選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a1494-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="a1494-151">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="a1494-151">Conditional Access policies</span></span>

<span data-ttu-id="a1494-152">建立、設定及啟用適當的原則，其中包括需要 MFA 進行 MFA 的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="a1494-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="a1494-153">每一使用者 MFA （不建議）</span><span class="sxs-lookup"><span data-stu-id="a1494-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="a1494-154">針對與您的部署對應的 MFA 啟用使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1494-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="a1494-155">支援您的員工</span><span class="sxs-lookup"><span data-stu-id="a1494-155">Supporting your employees</span></span>

<span data-ttu-id="a1494-156">當您的員工註冊並開始以 MFA 登入時，請確定您的 IT 專家、IT 部門或服務台可以快速解答問題並解決問題。</span><span class="sxs-lookup"><span data-stu-id="a1494-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="a1494-157">如需[疑難排解 MFA 登入的相關資訊](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)，請參閱本文。</span><span class="sxs-lookup"><span data-stu-id="a1494-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


