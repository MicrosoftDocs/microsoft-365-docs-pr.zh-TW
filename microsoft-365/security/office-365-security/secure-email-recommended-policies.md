---
title: 安全電子郵件建議原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述如何套用電子郵件原則和設定之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 653b16b7b3f6637440e3740830ffe9f9a51c6dd8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166504"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="20975-103">保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="20975-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="20975-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="20975-104">**Applies to**</span></span>
- [<span data-ttu-id="20975-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="20975-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="20975-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="20975-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)


<span data-ttu-id="20975-107">本文說明如何執行建議的身分識別和裝置存取原則，以保護支援新式驗證和條件式存取的組織電子郵件和電子郵件客戶程式。</span><span class="sxs-lookup"><span data-stu-id="20975-107">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="20975-108">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md) 為基礎，也包含一些額外的建議。</span><span class="sxs-lookup"><span data-stu-id="20975-108">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="20975-109">這些建議是以三種不同的安全性和保護層級為基礎，可以根據您的需求細微性來套用： **基準**、 **機密** 和 **高管制**。</span><span class="sxs-lookup"><span data-stu-id="20975-109">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="20975-110">您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="20975-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="20975-111">這些建議要求您的使用者使用現代電子郵件客戶程式，包括行動裝置上的 Outlook iOS 和 Android。</span><span class="sxs-lookup"><span data-stu-id="20975-111">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="20975-112">適用于 iOS 和 Android 的 Outlook 提供 Office 365 的最佳功能支援。</span><span class="sxs-lookup"><span data-stu-id="20975-112">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="20975-113">這些行動性 Outlook 應用程式也會使用支援行動使用的安全性功能，以及與其他 Microsoft cloud 安全性功能共同運作。</span><span class="sxs-lookup"><span data-stu-id="20975-113">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="20975-114">如需詳細資訊，請參閱 [Outlook for iOS 和 ANDROID 常見問題](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="20975-114">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="20975-115">更新常見原則以包含電子郵件</span><span class="sxs-lookup"><span data-stu-id="20975-115">Update common policies to include email</span></span>

<span data-ttu-id="20975-116">為了保護電子郵件，下列圖表說明從通用身分識別和裝置存取原則更新哪些原則。</span><span class="sxs-lookup"><span data-stu-id="20975-116">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="20975-117">[![保護對小組及其相依服務之存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="20975-117">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="20975-118">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="20975-118">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="20975-119">請注意，新增 Exchange Online 的新原則，以封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="20975-119">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="20975-120">這會強制使用 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="20975-120">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="20975-121">當您設定 Exchange Online 和 Outlook 時，如果您已在設定原則的範圍內包含 Exchange Online 和 Outlook，您只需要建立新原則來封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="20975-121">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="20975-122">請查看下表所列的原則，並進行建議的新增，或確認是否已包含這些原則。</span><span class="sxs-lookup"><span data-stu-id="20975-122">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="20975-123">每個原則都連結至 [共同身分識別和裝置存取原則](identity-access-policies.md)中相關的設定指示。</span><span class="sxs-lookup"><span data-stu-id="20975-123">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="20975-124">保護層級</span><span class="sxs-lookup"><span data-stu-id="20975-124">Protection level</span></span>|<span data-ttu-id="20975-125">原則</span><span class="sxs-lookup"><span data-stu-id="20975-125">Policies</span></span>|<span data-ttu-id="20975-126">其他資訊</span><span class="sxs-lookup"><span data-stu-id="20975-126">More information</span></span>|
|---|---|---|
|<span data-ttu-id="20975-127">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="20975-127">**Baseline**</span></span>|[<span data-ttu-id="20975-128">當登入風險為 *中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="20975-128">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="20975-129">在雲應用程式的指派中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-129">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="20975-130">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="20975-130">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="20975-131">在雲應用程式的指派中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-131">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="20975-132">套用應用程式資料保護原則</span><span class="sxs-lookup"><span data-stu-id="20975-132">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="20975-133">請確定 Outlook 已包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="20975-133">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="20975-134">請務必更新每個平臺 (iOS、Android、Windows) 的原則</span><span class="sxs-lookup"><span data-stu-id="20975-134">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="20975-135">需要核准的應用程式和應用程式保護</span><span class="sxs-lookup"><span data-stu-id="20975-135">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="20975-136">在雲端應用程式清單中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-136">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="20975-137">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="20975-137">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="20975-138">在雲端 app 清單中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-138">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="20975-139">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="20975-139">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="20975-140">新增此新原則</span><span class="sxs-lookup"><span data-stu-id="20975-140">Add this new policy</span></span>|
|<span data-ttu-id="20975-141">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="20975-141">**Sensitive**</span></span>|[<span data-ttu-id="20975-142">當登入風險為 *低*、*中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="20975-142">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="20975-143">在雲應用程式的指派中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-143">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="20975-144">需要相容 *的電腦和* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="20975-144">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="20975-145">在雲端應用程式清單中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-145">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="20975-146">**高管制**</span><span class="sxs-lookup"><span data-stu-id="20975-146">**Highly regulated**</span></span>|[<span data-ttu-id="20975-147">*永遠* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="20975-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="20975-148">在雲應用程式的指派中包含 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-148">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="20975-149">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="20975-149">Block ActiveSync clients</span></span>

<span data-ttu-id="20975-150">這個原則可防止 ActiveSync 用戶端略過其他條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="20975-150">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="20975-151">原則設定只適用于 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="20975-151">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="20975-152">選取 [ **[要求應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**]，此原則會封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="20975-152">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="20975-153">若要瞭解如何建立此原則的詳細資料，請參閱 [使用條件式存取之 cloud app access 的應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="20975-153">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="20975-154">在第 [365 1 種情形](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)中，請遵循「步驟2：使用 Exchange Online 設定 Azure AD 條件式存取原則 ACTIVESYNC (EAS) 」，以防止 exchange ActiveSync 用戶端利用基本驗證連線至 Exchange Online，以防止 exchange 用戶端使用基本驗證。</span><span class="sxs-lookup"><span data-stu-id="20975-154">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="20975-155">您也可以使用驗證原則 [停用基本身份](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)驗證，以強制所有用戶端存取要求使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="20975-155">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="20975-156">從網頁上的 Outlook 限制存取 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20975-156">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="20975-157">您可以在 umnanaged 裝置上限制使用者從 Outlook 網頁版下載附件的能力。</span><span class="sxs-lookup"><span data-stu-id="20975-157">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="20975-158">這些裝置上的使用者可以使用 Office Online 來查看及編輯這些檔案，而不需要在裝置上洩漏及儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="20975-158">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="20975-159">您也可以封鎖使用者在未受管理的裝置上看到附件。</span><span class="sxs-lookup"><span data-stu-id="20975-159">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="20975-160">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="20975-160">Here are the steps:</span></span>

1. <span data-ttu-id="20975-161">[連接至 Exchange Online 遠端 PowerShell 會話](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="20975-161">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="20975-162">如果您還沒有 OWA 信箱原則，請使用 [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) Cmdlet 建立一個。</span><span class="sxs-lookup"><span data-stu-id="20975-162">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="20975-163">如果您想要允許查看附件，但無法下載，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="20975-163">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="20975-164">如果您想要封鎖附件，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="20975-164">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="20975-165">在 Azure 入口網站中，使用下列設定來建立新的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="20975-165">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="20975-166">**工作分派** \>**使用者和群組**：選取適當的使用者和群組以加入及排除。</span><span class="sxs-lookup"><span data-stu-id="20975-166">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="20975-167">**工作分派** \>**雲端應用程式或動作** \>**雲端應用程式** \>**包含** \>**選取應用程式**：選取 **Office 365 Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="20975-167">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="20975-168">**存取控制** \>**會話**：選取 [**使用 app 強制限制**]</span><span class="sxs-lookup"><span data-stu-id="20975-168">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="20975-169">需要 iOS 和 Android 裝置必須使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="20975-169">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="20975-170">為了確保 iOS 和 Android 裝置的使用者只能使用 Outlook for iOS 和 Android 來存取工作或學校內容，您需要針對那些潛在使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="20975-170">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="20975-171">若要 [使用 iOS 和 Android 的 Outlook 來管理通訊共同存取]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)，請參閱設定此原則的步驟。</span><span class="sxs-lookup"><span data-stu-id="20975-171">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="20975-172">設定郵件加密</span><span class="sxs-lookup"><span data-stu-id="20975-172">Set up message encryption</span></span>

<span data-ttu-id="20975-173">使用新的 Office 365 郵件加密 (OME) 功能，利用 Azure 資訊保護中的保護功能，您的組織可以輕鬆地與任何設備上的任何人共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="20975-173">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="20975-174">使用者可以使用 Outlook.com、Gmail 及其他電子郵件服務，傳送及接收與其他 Microsoft 365 組織及非客戶的受保護郵件。</span><span class="sxs-lookup"><span data-stu-id="20975-174">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="20975-175">如需詳細資訊，請參閱 [設定新的 Office 365 郵件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="20975-175">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="20975-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="20975-176">Next steps</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="20975-178">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="20975-178">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="20975-179">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20975-179">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="20975-180">SharePoint</span><span class="sxs-lookup"><span data-stu-id="20975-180">SharePoint</span></span>](sharepoint-file-access-policies.md)
