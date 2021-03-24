---
title: 身分識別與裝置存取 - 您的 Microsoft 365 測試環境中僅限雲端的先決條件
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
description: 建立 Microsoft 365 環境，以使用僅限雲端驗證的先決條件測試身分識別與裝置存取。
ms.openlocfilehash: 537718eb0efcffc296162a4458158efcbdad9986
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051541"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="5c449-103">身分識別與裝置存取 - 您的 Microsoft 365 測試環境中僅限雲端的先決條件</span><span class="sxs-lookup"><span data-stu-id="5c449-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="5c449-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="5c449-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5c449-105">身分[識別與裝置存取](../security/defender-365-security/microsoft-365-policies-configurations.md)設定是一組建議的設定和條件式存取原則，可保護對與 Azure Active Directory (azure AD) 整合的所有服務的存取。</span><span class="sxs-lookup"><span data-stu-id="5c449-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="5c449-106">本文說明如何設定符合[僅限雲端先決條件組態](../security/defender-365-security/identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的 Microsoft 365 測試環境。</span><span class="sxs-lookup"><span data-stu-id="5c449-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="5c449-107">設定此測試環境有八個階段：</span><span class="sxs-lookup"><span data-stu-id="5c449-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="5c449-108">建立輕量型測試環境</span><span class="sxs-lookup"><span data-stu-id="5c449-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="5c449-109">設定具名位置</span><span class="sxs-lookup"><span data-stu-id="5c449-109">Configure named locations</span></span>
3. <span data-ttu-id="5c449-110">設定自助式密碼重設</span><span class="sxs-lookup"><span data-stu-id="5c449-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="5c449-111">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="5c449-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="5c449-112">啟用加入網域之 Windows 電腦的自動裝置註冊</span><span class="sxs-lookup"><span data-stu-id="5c449-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="5c449-113">設定 Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="5c449-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="5c449-114">啟用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5c449-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="5c449-115">為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="5c449-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="5c449-116">階段 1：建立輕量型 Microsoft 365 測試環境</span><span class="sxs-lookup"><span data-stu-id="5c449-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="5c449-117">遵循[輕量型組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="5c449-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="5c449-118">以下是所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="5c449-118">Here is the resulting configuration.</span></span>

![輕量型 Microsoft 365 企業版測試環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="5c449-120">階段 2：設定具名位置</span><span class="sxs-lookup"><span data-stu-id="5c449-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="5c449-121">首先，判斷組織使用的公用 IP 位址或位址範圍。</span><span class="sxs-lookup"><span data-stu-id="5c449-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="5c449-122">接下來，遵循[在 Azure Active Directory 中設定具名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的指示，新增位址或位址範圍做為具名位置。</span><span class="sxs-lookup"><span data-stu-id="5c449-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="5c449-123">階段3：設定自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="5c449-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="5c449-124">遵循[測試實驗室指南密碼重設階段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5c449-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="5c449-125">為特定 Azure AD 群組中的帳戶啟用重設密碼時，請將下列帳戶新增至 **重設密碼** 群組：</span><span class="sxs-lookup"><span data-stu-id="5c449-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="5c449-126">使用者 2</span><span class="sxs-lookup"><span data-stu-id="5c449-126">User 2</span></span>
- <span data-ttu-id="5c449-127">使用者 3</span><span class="sxs-lookup"><span data-stu-id="5c449-127">User 3</span></span>
- <span data-ttu-id="5c449-128">使用者 4</span><span class="sxs-lookup"><span data-stu-id="5c449-128">User 4</span></span>
- <span data-ttu-id="5c449-129">使用者 5</span><span class="sxs-lookup"><span data-stu-id="5c449-129">User 5</span></span>

<span data-ttu-id="5c449-130">僅對使用者 2 帳戶測試密碼重設。</span><span class="sxs-lookup"><span data-stu-id="5c449-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="5c449-131">階段4：設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="5c449-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="5c449-132">針對下列使用者帳戶，遵循[測試實驗室指南多重要素驗證階段 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 中的指示：</span><span class="sxs-lookup"><span data-stu-id="5c449-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="5c449-133">使用者 2</span><span class="sxs-lookup"><span data-stu-id="5c449-133">User 2</span></span>
- <span data-ttu-id="5c449-134">使用者 3</span><span class="sxs-lookup"><span data-stu-id="5c449-134">User 3</span></span>
- <span data-ttu-id="5c449-135">使用者 4</span><span class="sxs-lookup"><span data-stu-id="5c449-135">User 4</span></span>
- <span data-ttu-id="5c449-136">使用者 5</span><span class="sxs-lookup"><span data-stu-id="5c449-136">User 5</span></span>

<span data-ttu-id="5c449-137">僅針對使用者 2 帳戶測試多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="5c449-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="5c449-138">階段5：啟用加入網域的 Windows 電腦的自動裝置註冊</span><span class="sxs-lookup"><span data-stu-id="5c449-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="5c449-139">遵循 [下列指示](/azure/active-directory/devices/hybrid-azuread-join-plan) ，啟用已加入網域之 Windows 電腦的自動裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="5c449-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="5c449-140">階段6：設定 Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="5c449-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="5c449-141">請遵循 [這些指示](/azure/active-directory/authentication/concept-password-ban-bad) 來封鎖已知的弱密碼及其變種。</span><span class="sxs-lookup"><span data-stu-id="5c449-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="5c449-142">階段 7：啟用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5c449-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="5c449-143">遵循[測試實驗室指南 Azure AD Identity Protection 階段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5c449-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="5c449-144">階段 8：為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="5c449-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="5c449-145">若為 Exchange Online，請遵循[這些指示](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)。</span><span class="sxs-lookup"><span data-stu-id="5c449-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="5c449-146">若為商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="5c449-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="5c449-147">連線到[商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5c449-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="5c449-148">執行此命令。</span><span class="sxs-lookup"><span data-stu-id="5c449-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="5c449-149">使用此命令以確認變更是否成功。</span><span class="sxs-lookup"><span data-stu-id="5c449-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="5c449-150">結果是一種測試環境，可滿足身分識別與裝置存取之 [僅雲端](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) 必要條件設定的需求。</span><span class="sxs-lookup"><span data-stu-id="5c449-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5c449-151">下一步</span><span class="sxs-lookup"><span data-stu-id="5c449-151">Next step</span></span>

<span data-ttu-id="5c449-152">使用[一般身分識別與裝置存取原則](../security/defender-365-security/identity-access-policies.md)來設定根據先決條件建置的原則，並保護身分識別與裝置。</span><span class="sxs-lookup"><span data-stu-id="5c449-152">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c449-153">請參閱</span><span class="sxs-lookup"><span data-stu-id="5c449-153">See also</span></span>

[<span data-ttu-id="5c449-154">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="5c449-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5c449-155">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="5c449-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5c449-156">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="5c449-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5c449-157">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="5c449-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5c449-158">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="5c449-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
