---
title: 身分識別與裝置存取 - 您的 Microsoft 365 測試環境中傳遞驗證的先決條件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境，以使用傳遞驗證的先決條件測試身分識別與裝置存取。
ms.openlocfilehash: f257b85672a1a1b27f600d145b1f9f3296b21980
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199846"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="cad1d-103">身分識別與裝置存取 - 您的 Microsoft 365 測試環境中傳遞驗證的先決條件</span><span class="sxs-lookup"><span data-stu-id="cad1d-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="cad1d-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="cad1d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cad1d-105">身分[識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定是一組設定和條件式存取原則，可保護所有與 Azure Active Directory (azure AD) 整合的 365 Microsoft 企業版服務的存取。</span><span class="sxs-lookup"><span data-stu-id="cad1d-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="cad1d-106">本文說明如何設定符合[傳遞驗證先決條件組態](../security/office-365-security/identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的 Microsoft 365 測試環境。</span><span class="sxs-lookup"><span data-stu-id="cad1d-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="cad1d-107">設定此測試環境有10個階段：</span><span class="sxs-lookup"><span data-stu-id="cad1d-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="cad1d-108">使用傳遞驗證 Microsoft 365 測試環境建立模擬企業</span><span class="sxs-lookup"><span data-stu-id="cad1d-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="cad1d-109">設定 Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="cad1d-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="cad1d-110">設定具名位置</span><span class="sxs-lookup"><span data-stu-id="cad1d-110">Configure named locations</span></span>
4. <span data-ttu-id="cad1d-111">設定密碼回寫</span><span class="sxs-lookup"><span data-stu-id="cad1d-111">Configure password writeback</span></span>
5. <span data-ttu-id="cad1d-112">設定自助式密碼重設</span><span class="sxs-lookup"><span data-stu-id="cad1d-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="cad1d-113">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="cad1d-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="cad1d-114">啟用加入網域之 Windows 電腦的自動裝置註冊</span><span class="sxs-lookup"><span data-stu-id="cad1d-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="cad1d-115">設定 Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="cad1d-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="cad1d-116">啟用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="cad1d-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="cad1d-117">為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="cad1d-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="cad1d-118">階段 1：使用傳遞驗證 Microsoft 365 測試環境建立模擬企業</span><span class="sxs-lookup"><span data-stu-id="cad1d-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="cad1d-119">遵循[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="cad1d-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="cad1d-120">以下是所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="cad1d-120">Here is the resulting configuration.</span></span>

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="cad1d-122">階段 2：設定 Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="cad1d-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="cad1d-123">遵循[測試實驗室指南 Azure AD 無縫單一登入階段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="cad1d-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="cad1d-124">階段 3：設定具名位置</span><span class="sxs-lookup"><span data-stu-id="cad1d-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="cad1d-125">首先，判斷組織使用的公用 IP 位址或位址範圍。</span><span class="sxs-lookup"><span data-stu-id="cad1d-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="cad1d-126">接下來，遵循[在 Azure Active Directory 中設定具名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的指示，新增位址或位址範圍做為具名位置。</span><span class="sxs-lookup"><span data-stu-id="cad1d-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="cad1d-127">階段 4：設定密碼回寫</span><span class="sxs-lookup"><span data-stu-id="cad1d-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="cad1d-128">遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="cad1d-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="cad1d-129">階段 5：啟用自助式密碼重設</span><span class="sxs-lookup"><span data-stu-id="cad1d-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="cad1d-130">遵循[測試實驗室指南密碼重設階段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="cad1d-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="cad1d-131">為特定 Azure AD 群組中的帳戶啟用重設密碼時，請將下列帳戶新增至 **重設密碼** 群組：</span><span class="sxs-lookup"><span data-stu-id="cad1d-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="cad1d-132">使用者 2</span><span class="sxs-lookup"><span data-stu-id="cad1d-132">User 2</span></span>
- <span data-ttu-id="cad1d-133">使用者 3</span><span class="sxs-lookup"><span data-stu-id="cad1d-133">User 3</span></span>
- <span data-ttu-id="cad1d-134">使用者 4</span><span class="sxs-lookup"><span data-stu-id="cad1d-134">User 4</span></span>
- <span data-ttu-id="cad1d-135">使用者 5</span><span class="sxs-lookup"><span data-stu-id="cad1d-135">User 5</span></span>

<span data-ttu-id="cad1d-136">僅對使用者 2 帳戶測試密碼重設。</span><span class="sxs-lookup"><span data-stu-id="cad1d-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="cad1d-137">階段 6：設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="cad1d-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="cad1d-138">針對下列使用者帳戶，遵循[測試實驗室指南多重要素驗證階段 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 中的指示：</span><span class="sxs-lookup"><span data-stu-id="cad1d-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="cad1d-139">使用者 2</span><span class="sxs-lookup"><span data-stu-id="cad1d-139">User 2</span></span>
- <span data-ttu-id="cad1d-140">使用者 3</span><span class="sxs-lookup"><span data-stu-id="cad1d-140">User 3</span></span>
- <span data-ttu-id="cad1d-141">使用者 4</span><span class="sxs-lookup"><span data-stu-id="cad1d-141">User 4</span></span>
- <span data-ttu-id="cad1d-142">使用者 5</span><span class="sxs-lookup"><span data-stu-id="cad1d-142">User 5</span></span>

<span data-ttu-id="cad1d-143">僅針對使用者 2 帳戶測試多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="cad1d-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="cad1d-144">階段7：啟用加入網域的 Windows 電腦的自動裝置註冊</span><span class="sxs-lookup"><span data-stu-id="cad1d-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="cad1d-145">遵循 [下列指示](/azure/active-directory/devices/hybrid-azuread-join-plan) ，啟用已加入網域之 Windows 電腦的自動裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="cad1d-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="cad1d-146">階段8：設定 Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="cad1d-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="cad1d-147">請遵循 [這些指示](/azure/active-directory/authentication/concept-password-ban-bad) 來封鎖已知的弱密碼及其變種。</span><span class="sxs-lookup"><span data-stu-id="cad1d-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="cad1d-148">階段9：啟用 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="cad1d-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="cad1d-149">遵循[測試實驗室指南 Azure AD Identity Protection 階段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="cad1d-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="cad1d-150">階段10：為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="cad1d-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="cad1d-151">若為 Exchange Online，請遵循[這些指示](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)。</span><span class="sxs-lookup"><span data-stu-id="cad1d-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="cad1d-152">若為商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="cad1d-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="cad1d-153">連線到[商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cad1d-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="cad1d-154">執行此命令。</span><span class="sxs-lookup"><span data-stu-id="cad1d-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="cad1d-155">使用此命令以確認變更是否成功。</span><span class="sxs-lookup"><span data-stu-id="cad1d-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="cad1d-156">結果會是符合[傳遞驗證先決條件組態](../security/office-365-security/identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的測試環境。</span><span class="sxs-lookup"><span data-stu-id="cad1d-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cad1d-157">下一步</span><span class="sxs-lookup"><span data-stu-id="cad1d-157">Next step</span></span>

<span data-ttu-id="cad1d-158">使用[一般身分識別與裝置存取原則](../security/office-365-security/identity-access-policies.md)來設定根據先決條件建置的原則，並保護身分識別與裝置。</span><span class="sxs-lookup"><span data-stu-id="cad1d-158">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="cad1d-159">請參閱</span><span class="sxs-lookup"><span data-stu-id="cad1d-159">See also</span></span>

[<span data-ttu-id="cad1d-160">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="cad1d-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="cad1d-161">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="cad1d-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="cad1d-162">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="cad1d-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cad1d-163">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="cad1d-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cad1d-164">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="cad1d-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
