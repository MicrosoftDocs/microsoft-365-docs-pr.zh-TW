---
title: 身分識別與裝置存取 - 您的 Microsoft 365 測試環境中僅限雲端的先決條件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境，以使用僅限雲端驗證的先決條件測試身分識別與裝置存取。
ms.openlocfilehash: 94d3f5cdff7c8515ab775ae8070b74dd9b80df0f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153779"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="8de11-103">身分識別與裝置存取 - 您的 Microsoft 365 測試環境中僅限雲端的先決條件</span><span class="sxs-lookup"><span data-stu-id="8de11-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="8de11-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="8de11-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8de11-105">[身分識別與裝置存取組態](microsoft-365-policies-configurations.md)是一組組態和條件式存取原則，用來保護對與 Azure Active Directory (Azure AD) 整合之所有服務的存取，包括 Microsoft 365 企業版中的 Office 365 和 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="8de11-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and Conditional Access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="8de11-106">本文說明如何設定符合[僅限雲端先決條件組態](identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的 Microsoft 365 測試環境。</span><span class="sxs-lookup"><span data-stu-id="8de11-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="8de11-107">設定此測試環境有七個階段：</span><span class="sxs-lookup"><span data-stu-id="8de11-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="8de11-108">建立輕量型測試環境</span><span class="sxs-lookup"><span data-stu-id="8de11-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="8de11-109">設定具名位置</span><span class="sxs-lookup"><span data-stu-id="8de11-109">Configure named locations</span></span>
3.  <span data-ttu-id="8de11-110">設定密碼回寫</span><span class="sxs-lookup"><span data-stu-id="8de11-110">Configure password writeback</span></span>
4.  <span data-ttu-id="8de11-111">啟用自助式密碼重設</span><span class="sxs-lookup"><span data-stu-id="8de11-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="8de11-112">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8de11-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="8de11-113">啟用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="8de11-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="8de11-114">為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="8de11-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="8de11-115">階段 1：建立輕量型 Microsoft 365 測試環境</span><span class="sxs-lookup"><span data-stu-id="8de11-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="8de11-116">遵循[輕量型組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="8de11-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="8de11-117">以下是所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="8de11-117">Here is the resulting configuration.</span></span>

![輕量型 Microsoft 365 企業版測試環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="8de11-119">階段 2：設定具名位置</span><span class="sxs-lookup"><span data-stu-id="8de11-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="8de11-120">首先，判斷組織使用的公用 IP 位址或位址範圍。</span><span class="sxs-lookup"><span data-stu-id="8de11-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="8de11-121">接下來，遵循[在 Azure Active Directory 中設定具名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的指示，新增位址或位址範圍做為具名位置。</span><span class="sxs-lookup"><span data-stu-id="8de11-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="8de11-122">階段 3：設定密碼回寫</span><span class="sxs-lookup"><span data-stu-id="8de11-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="8de11-123">遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8de11-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="8de11-124">階段 4：設定自助式密碼重設</span><span class="sxs-lookup"><span data-stu-id="8de11-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="8de11-125">遵循[測試實驗室指南密碼重設階段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8de11-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="8de11-126">為特定 Azure AD 群組中的帳戶啟用重設密碼時，請將下列帳戶新增至**重設密碼**群組：</span><span class="sxs-lookup"><span data-stu-id="8de11-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="8de11-127">使用者 2</span><span class="sxs-lookup"><span data-stu-id="8de11-127">User 2</span></span>
- <span data-ttu-id="8de11-128">使用者 3</span><span class="sxs-lookup"><span data-stu-id="8de11-128">User 3</span></span>
- <span data-ttu-id="8de11-129">使用者 4</span><span class="sxs-lookup"><span data-stu-id="8de11-129">User 4</span></span>
- <span data-ttu-id="8de11-130">使用者 5</span><span class="sxs-lookup"><span data-stu-id="8de11-130">User 5</span></span>

<span data-ttu-id="8de11-131">僅對使用者 2 帳戶測試密碼重設。</span><span class="sxs-lookup"><span data-stu-id="8de11-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="8de11-132">階段 5：設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8de11-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="8de11-133">針對下列使用者帳戶，遵循[測試實驗室指南多重要素驗證階段 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 中的指示：</span><span class="sxs-lookup"><span data-stu-id="8de11-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="8de11-134">使用者 2</span><span class="sxs-lookup"><span data-stu-id="8de11-134">User 2</span></span>
- <span data-ttu-id="8de11-135">使用者 3</span><span class="sxs-lookup"><span data-stu-id="8de11-135">User 3</span></span>
- <span data-ttu-id="8de11-136">使用者 4</span><span class="sxs-lookup"><span data-stu-id="8de11-136">User 4</span></span>
- <span data-ttu-id="8de11-137">使用者 5</span><span class="sxs-lookup"><span data-stu-id="8de11-137">User 5</span></span>

<span data-ttu-id="8de11-138">僅針對使用者 2 帳戶測試多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8de11-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="8de11-139">階段 6：啟用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="8de11-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="8de11-140">遵循[測試實驗室指南 Azure AD Identity Protection 階段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8de11-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="8de11-141">階段 7：為 Exchange Online 和商務用 Skype Online 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="8de11-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="8de11-142">若為 Exchange Online，請遵循[這些指示](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)。</span><span class="sxs-lookup"><span data-stu-id="8de11-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="8de11-143">若為商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="8de11-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="8de11-144">連線到[商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8de11-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="8de11-145">執行此命令。</span><span class="sxs-lookup"><span data-stu-id="8de11-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="8de11-146">使用此命令以確認變更是否成功。</span><span class="sxs-lookup"><span data-stu-id="8de11-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="8de11-147">結果會是符合[僅限雲端先決條件組態](identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的測試環境。</span><span class="sxs-lookup"><span data-stu-id="8de11-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="8de11-148">下一步</span><span class="sxs-lookup"><span data-stu-id="8de11-148">Next step</span></span>

<span data-ttu-id="8de11-149">使用[一般身分識別與裝置存取原則](identity-access-policies.md)來設定根據先決條件建置的原則，並保護身分識別與裝置。</span><span class="sxs-lookup"><span data-stu-id="8de11-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8de11-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="8de11-150">See also</span></span>

[<span data-ttu-id="8de11-151">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8de11-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="8de11-152">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="8de11-152">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8de11-153">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8de11-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8de11-154">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="8de11-154">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8de11-155">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="8de11-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
