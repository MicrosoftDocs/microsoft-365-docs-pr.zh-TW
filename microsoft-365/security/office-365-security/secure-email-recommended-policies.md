---
title: 安全的電子郵件建議政策 - 適用于企業的 Microsoft 365 |Microsoft Docs
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
ms.openlocfilehash: f3654762bf4d4c28a82b1e93829094b9e0386a60
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926519"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="b526d-103">保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="b526d-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="b526d-104">本文說明如何執行建議的身分識別與裝置存取策略，以保護支援新式驗證與條件式存取的組織電子郵件和電子郵件客戶客戶。</span><span class="sxs-lookup"><span data-stu-id="b526d-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="b526d-105">此指引以一 [般身分識別與裝置存取策略為](identity-access-policies.md) 根據，並包含一些額外的建議。</span><span class="sxs-lookup"><span data-stu-id="b526d-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="b526d-106">這些建議是以三種不同的安全性和保護層級為基礎，可以根據您的需求細微度來加以運用：比較基準、機密以及 **高度規範**。  </span><span class="sxs-lookup"><span data-stu-id="b526d-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="b526d-107">您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="b526d-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="b526d-108">這些建議會要求您的使用者使用新式電子郵件用戶端，包括行動裝置上的 iOS 版 Outlook 和 Android 版 Outlook。</span><span class="sxs-lookup"><span data-stu-id="b526d-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="b526d-109">iOS 和 Android 版 Outlook 支援 Office 365 的最佳功能。</span><span class="sxs-lookup"><span data-stu-id="b526d-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="b526d-110">這些行動版 Outlook App 也採用安全性功能進行架構，可支援行動用途並與其他 Microsoft 雲端安全性功能共同作業。</span><span class="sxs-lookup"><span data-stu-id="b526d-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="b526d-111">詳細資訊請參閱 iOS 版 Outlook 和 [Android 版 Outlook 的常見問題](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="b526d-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="b526d-112">更新一般策略以包含電子郵件</span><span class="sxs-lookup"><span data-stu-id="b526d-112">Update common policies to include email</span></span>

<span data-ttu-id="b526d-113">若要保護電子郵件，下圖說明要從一般身分識別與裝置存取策略更新哪些策略。</span><span class="sxs-lookup"><span data-stu-id="b526d-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="b526d-114">[![用於保護 Teams 存取權及其從屬服務之策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="b526d-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="b526d-115">查看此影像的較大版本</span><span class="sxs-lookup"><span data-stu-id="b526d-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="b526d-116">請注意，Exchange Online 新增了封鎖 ActiveSync 用戶端的新策略。</span><span class="sxs-lookup"><span data-stu-id="b526d-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="b526d-117">這會強制使用 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="b526d-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="b526d-118">如果您在設定 Exchange Online 和 Outlook 時將 Exchange Online 和 Outlook 納入其中，您只需要建立新策略來封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b526d-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="b526d-119">請審查下表中列出的政策，並新增建議專案，或確認其中已包含這些。</span><span class="sxs-lookup"><span data-stu-id="b526d-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="b526d-120">每個策略會連結至一般身分識別與 [裝置存取策略中關聯的組組指示](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b526d-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="b526d-121">保護層級</span><span class="sxs-lookup"><span data-stu-id="b526d-121">Protection level</span></span>|<span data-ttu-id="b526d-122">原則</span><span class="sxs-lookup"><span data-stu-id="b526d-122">Policies</span></span>|<span data-ttu-id="b526d-123">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="b526d-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="b526d-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="b526d-124">**Baseline**</span></span>|[<span data-ttu-id="b526d-125">當登錄風險中或高 *時需要* MFA</span><span class="sxs-lookup"><span data-stu-id="b526d-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b526d-126">在指派雲端 App 中納入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b526d-126">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="b526d-127">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="b526d-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="b526d-128">在指派雲端 App 中納入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b526d-128">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="b526d-129">Apply APP 資料保護原則</span><span class="sxs-lookup"><span data-stu-id="b526d-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="b526d-130">請確定 Outlook 已包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="b526d-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="b526d-131">請務必針對 iOS、Android、Windows (每個平臺更新) </span><span class="sxs-lookup"><span data-stu-id="b526d-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="b526d-132">需要核准的應用程式和 APP 保護</span><span class="sxs-lookup"><span data-stu-id="b526d-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="b526d-133">將 Exchange Online 納入雲端應用程式清單</span><span class="sxs-lookup"><span data-stu-id="b526d-133">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="b526d-134">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="b526d-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="b526d-135">將 Exchange Online 納入雲端應用程式清單</span><span class="sxs-lookup"><span data-stu-id="b526d-135">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="b526d-136">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="b526d-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="b526d-137">新增此新政策</span><span class="sxs-lookup"><span data-stu-id="b526d-137">Add this new policy</span></span>|
|<span data-ttu-id="b526d-138">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="b526d-138">**Sensitive**</span></span>|[<span data-ttu-id="b526d-139">在低、中或高登錄風險時需要MFA </span><span class="sxs-lookup"><span data-stu-id="b526d-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b526d-140">在指派雲端 App 中納入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b526d-140">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="b526d-141">需要符合規範的 PC *及* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="b526d-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="b526d-142">將 Exchange Online 納入雲端應用程式清單</span><span class="sxs-lookup"><span data-stu-id="b526d-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="b526d-143">**高管制**</span><span class="sxs-lookup"><span data-stu-id="b526d-143">**Highly regulated**</span></span>|[<span data-ttu-id="b526d-144">*一* 直需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b526d-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b526d-145">在指派雲端 App 中納入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b526d-145">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="b526d-146">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="b526d-146">Block ActiveSync clients</span></span>

<span data-ttu-id="b526d-147">此策略可防止 ActiveSync 用戶端忽略其他條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="b526d-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="b526d-148">原則群組原則只會適用于 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b526d-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="b526d-149">選取需要 **[App 保護原則，](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 此策略會區塊 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b526d-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="b526d-150">您可以在使用條件式存取進行雲端 App 存取的需要 App 保護原則中，找到建立 [此策略的詳細資訊](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="b526d-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="b526d-151">請遵循「步驟 2：使用 ActiveSync (EAS) 設定 Exchange Online 的 Azure AD 條件式存取策略」：Office [365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)App 需要具有 App 保護原則核准的 App，以避免使用基本驗證的 Exchange ActiveSync 用戶端無法連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b526d-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="b526d-152">您也可以使用驗證策略來停用基本 [驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)，強制所有用戶端存取要求使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="b526d-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="b526d-153">限制從 Outlook 網頁版存取 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b526d-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="b526d-154">您可以限制使用者在裝置上從 Outlook 網頁版本下載附件的能力。</span><span class="sxs-lookup"><span data-stu-id="b526d-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="b526d-155">這些裝置上的使用者可以使用 Office Online 來查看和編輯這些檔案，而不必將檔案洩漏到裝置上並儲存。</span><span class="sxs-lookup"><span data-stu-id="b526d-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="b526d-156">您也可以封鎖使用者在未受到管理裝置上看到附件。</span><span class="sxs-lookup"><span data-stu-id="b526d-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="b526d-157">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="b526d-157">Here are the steps:</span></span>

1. <span data-ttu-id="b526d-158">[連線到 Exchange Online 遠端 PowerShell 會話](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b526d-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="b526d-159">如果您還沒有 OWA 信箱策略，請用 [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) Cmdlet 建立一個。</span><span class="sxs-lookup"><span data-stu-id="b526d-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="b526d-160">如果您想要允許檢視附件但不允許下載，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="b526d-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="b526d-161">如果您想要封鎖附件，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="b526d-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="b526d-162">在 Azure 入口網站中，使用這些設定來建立一個新的條件式存取政策：</span><span class="sxs-lookup"><span data-stu-id="b526d-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="b526d-163">**作業** \>**使用者和群組**：選取要包含和排除的適當使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="b526d-163">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="b526d-164">**作業** \>**雲端 App 或動作** \>**雲端應用程式** \>**包含** \>**選取應用程式**：選取 **Office 365 Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="b526d-164">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="b526d-165">**存取控制** \>**會話**：選取 **使用應用程式強制限制**</span><span class="sxs-lookup"><span data-stu-id="b526d-165">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="b526d-166">要求 iOS 和 Android 裝置必須使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="b526d-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="b526d-167">若要確保 iOS 和 Android 裝置的使用者只能使用 iOS 和 Android 版 Outlook 存取公司或學校內容，您需要一個會檢查這些潛在使用者的條件式存取政策。</span><span class="sxs-lookup"><span data-stu-id="b526d-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="b526d-168">請參閱使用 iOS 和 Android 版 Outlook 在管理郵件共同處理存取中設定 [此策略的步驟]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="b526d-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="b526d-169">設定郵件加密</span><span class="sxs-lookup"><span data-stu-id="b526d-169">Set up message encryption</span></span>

<span data-ttu-id="b526d-170">有了新的 Office 365 郵件加密 (OME) 功能，利用 Azure 資訊保護中的保護功能，貴組織就可以輕鬆地與任何裝置上的任何人共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b526d-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="b526d-171">使用者可以與其他 Microsoft 365 組織以及使用 Outlook.com、Gmail 和其他電子郵件服務的非客戶一起傳送及接收受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="b526d-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="b526d-172">詳細資訊請參閱設定新的 [Office 365 郵件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="b526d-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b526d-173">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b526d-173">Next steps</span></span>

![步驟 4：Microsoft 365 雲端應用程式政策](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="b526d-175">設定條件式存取策略：</span><span class="sxs-lookup"><span data-stu-id="b526d-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="b526d-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b526d-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="b526d-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b526d-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
