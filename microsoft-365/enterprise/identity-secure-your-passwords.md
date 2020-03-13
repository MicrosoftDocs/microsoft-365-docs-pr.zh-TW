---
title: 步驟2：保護您的密碼
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 您必須在組織中強化且易於管理您的密碼。
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544052"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="6af42-103">步驟 2：保護您的密碼</span><span class="sxs-lookup"><span data-stu-id="6af42-103">Step 2: Secure your passwords</span></span>

![第 2 階段 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="6af42-105">防止不正確的密碼</span><span class="sxs-lookup"><span data-stu-id="6af42-105">Prevent bad passwords</span></span>

<span data-ttu-id="6af42-106">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6af42-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="6af42-107">您所有的使用者都應使用 [Microsoft 密碼指導方針](https://www.microsoft.com/research/publication/password-guidance/)來建立使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="6af42-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="6af42-108">若要防止使用者建立容易猜測的密碼，請使用 Azure AD 密碼保護，此功能會同時使用全域禁止密碼清單和您指定的選用自訂禁止密碼清單。</span><span class="sxs-lookup"><span data-stu-id="6af42-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="6af42-109">例如，您可以指定組織的特定字詞，例如：</span><span class="sxs-lookup"><span data-stu-id="6af42-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="6af42-110">品牌名稱</span><span class="sxs-lookup"><span data-stu-id="6af42-110">Brand names</span></span>
- <span data-ttu-id="6af42-111">產品名稱</span><span class="sxs-lookup"><span data-stu-id="6af42-111">Product names</span></span>
- <span data-ttu-id="6af42-112">位置 (例如公司總部)</span><span class="sxs-lookup"><span data-stu-id="6af42-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="6af42-113">公司的特定內部條款</span><span class="sxs-lookup"><span data-stu-id="6af42-113">Company-specific internal terms</span></span>
- <span data-ttu-id="6af42-114">具有特定公司意義的縮寫</span><span class="sxs-lookup"><span data-stu-id="6af42-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="6af42-115">您可以在[雲端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[內部部署 Active Directory 網域服務 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 中禁止使用不正確的密碼。</span><span class="sxs-lookup"><span data-stu-id="6af42-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="6af42-116">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-password-prot)。</span><span class="sxs-lookup"><span data-stu-id="6af42-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="6af42-117">簡化密碼重設</span><span class="sxs-lookup"><span data-stu-id="6af42-117">Simplify password resets</span></span>

<span data-ttu-id="6af42-118">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6af42-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="6af42-119">在這一節中，您會啟用自助密碼重設 (SSPR)，允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="6af42-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="6af42-120">您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。</span><span class="sxs-lookup"><span data-stu-id="6af42-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="6af42-121">您必須先啟用密碼回寫，才可以部署密碼重設。</span><span class="sxs-lookup"><span data-stu-id="6af42-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="6af42-122">請參閱[推出密碼重設的指示](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="6af42-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6af42-124">測試實驗室指南：密碼重設</span><span class="sxs-lookup"><span data-stu-id="6af42-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="6af42-125">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-reset)。</span><span class="sxs-lookup"><span data-stu-id="6af42-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="6af42-126">簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="6af42-126">Simplify user sign-in</span></span>

<span data-ttu-id="6af42-127">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6af42-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6af42-128">在這一節中，您將會設定 Azure Active Directory 無縫單一登入 (Azure AD 無縫 SSO)，搭配密碼雜湊同步 (PHS)和傳遞驗證 (PTA) 使用，以便使用者可登入使用 Azure AD 使用者帳戶的服務，而不需要輸入密碼，以及在許多情況下不需輸入使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="6af42-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="6af42-129">這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。</span><span class="sxs-lookup"><span data-stu-id="6af42-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="6af42-130">您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。</span><span class="sxs-lookup"><span data-stu-id="6af42-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="6af42-131">請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="6af42-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6af42-133">測試實驗室指南：Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="6af42-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="6af42-134">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-sso)。</span><span class="sxs-lookup"><span data-stu-id="6af42-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="6af42-135">自訂 Office 365 登入頁面</span><span class="sxs-lookup"><span data-stu-id="6af42-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="6af42-136">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6af42-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6af42-137">在這一節中，您將會新增公司的名稱、標誌和其他辨識項目，藉此協助使用者辨識組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="6af42-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="6af42-138">使用 Microsoft 365 企業版，您可以自訂登入和存取面板頁面的外觀，讓頁面中出現公司的標誌、色彩配置和自訂的使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="6af42-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="6af42-139">如需詳細資訊，請參閱[將公司商標新增至 Office 365 登入頁面](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。</span><span class="sxs-lookup"><span data-stu-id="6af42-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="6af42-140">如需設定的指示，請參閱[將公司商標新增至登入和存取面板頁面](https://aka.ms/aadpaddbranding)。</span><span class="sxs-lookup"><span data-stu-id="6af42-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="6af42-141">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-custom-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="6af42-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="6af42-142">下一步</span><span class="sxs-lookup"><span data-stu-id="6af42-142">Next step</span></span>

|||
|:-------|:-----|
|![步驟 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="6af42-144">保護和管理您的使用者登入</span><span class="sxs-lookup"><span data-stu-id="6af42-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
