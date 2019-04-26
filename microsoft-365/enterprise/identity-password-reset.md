---
title: 步驟 5：簡化使用者的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定 Azure AD 的自助密碼重設 (SSPR)。
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287050"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="b2b94-103">步驟 5：簡化使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="b2b94-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="b2b94-104">簡化密碼更新</span><span class="sxs-lookup"><span data-stu-id="b2b94-104">Simplify password updates</span></span>

<span data-ttu-id="b2b94-105">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b2b94-105">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b2b94-106">在這一節中，您會允許使用者透過 Azure Active Directory (Azure AD) 重設其密碼，然後複製到本機 Active Directory 網域服務 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="b2b94-107">這個程序也稱為密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="b2b94-107">This process is known as password writeback.</span></span> <span data-ttu-id="b2b94-108">使用密碼回寫，使用者不需要透過使用者帳戶與其屬性儲存在其中的內部部署 Active Directory Domain Services (AD DS) 來更新其密碼。</span><span class="sxs-lookup"><span data-stu-id="b2b94-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="b2b94-109">對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。</span><span class="sxs-lookup"><span data-stu-id="b2b94-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="b2b94-110">為了充分利用 Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="b2b94-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="b2b94-111">如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="b2b94-p102">升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b2b94-115">測試實驗室指南：密碼回寫</span><span class="sxs-lookup"><span data-stu-id="b2b94-115">Test Lab Guide: Password reset</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b2b94-116">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="b2b94-117">簡化密碼重設</span><span class="sxs-lookup"><span data-stu-id="b2b94-117">Simplify password resets</span></span>

<span data-ttu-id="b2b94-118">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b2b94-118">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b2b94-119">在這一節中，您會啟用自助密碼重設 (SSPR)，允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="b2b94-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="b2b94-120">您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。</span><span class="sxs-lookup"><span data-stu-id="b2b94-120">In this step, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts. To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="b2b94-121">您必須先啟用密碼回寫，才可以部署密碼重設。</span><span class="sxs-lookup"><span data-stu-id="b2b94-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="b2b94-122">請參閱[推出密碼重設的指示](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-122">See the [instructions to enable password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b2b94-124">測試實驗室指南：密碼重設</span><span class="sxs-lookup"><span data-stu-id="b2b94-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b2b94-125">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-reset)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this step.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="b2b94-126">簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="b2b94-126">Simplify user sign-in</span></span>

<span data-ttu-id="b2b94-127">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b2b94-127">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b2b94-128">在這一節中，您將會設定 Azure Active Directory 無縫單一登入 (Azure AD 無縫 SSO)，讓使用者可登入使用 Azure AD 使用者帳戶的服務，而不需要輸入密碼，以及在許多情況下不需輸入使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b2b94-128">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span> <span data-ttu-id="b2b94-129">這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2b94-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="b2b94-130">您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。</span><span class="sxs-lookup"><span data-stu-id="b2b94-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="b2b94-131">請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b2b94-133">測試實驗室指南：Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="b2b94-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b2b94-134">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-sso)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="b2b94-135">自訂 Office 365 登入頁面</span><span class="sxs-lookup"><span data-stu-id="b2b94-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="b2b94-136">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b2b94-136">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b2b94-137">在這一節中，您將會新增公司的名稱、標誌和其他辨識項目，藉此協助使用者辨識組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="b2b94-137">In this step, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="b2b94-138">使用 Microsoft 365 企業版，您可以自訂登入和存取面板頁面的外觀，讓頁面中出現公司的標誌、色彩配置和自訂的使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="b2b94-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="b2b94-139">自訂之前\*\*，當使用者嘗試從裝置登入時，會看見類似下列範例的 Office 365 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="b2b94-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![自訂之前的 Office 365 登入頁面範例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="b2b94-141">自訂之後\*\*，同一位 Contoso 公司使用者會看到以下頁面。</span><span class="sxs-lookup"><span data-stu-id="b2b94-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![自訂之後的 Office 365 登入頁面範例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="b2b94-143">如需詳細資訊，請參閱[將公司商標新增至 Office 365 登入頁面](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="b2b94-144">如需設定的指示，請參閱[將公司商標新增至登入和存取面板頁面](http://aka.ms/aadpaddbranding)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="b2b94-145">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-custom-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="b2b94-146">下一步</span><span class="sxs-lookup"><span data-stu-id="b2b94-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="b2b94-147">使用群組更輕鬆地進行管理</span><span class="sxs-lookup"><span data-stu-id="b2b94-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


