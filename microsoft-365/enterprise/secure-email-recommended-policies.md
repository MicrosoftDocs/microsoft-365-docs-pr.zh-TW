---
title: 安全電子郵件建議原則原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何套用電子郵件原則和設定之 Microsoft 建議的原則。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 78defc7ad5da788ae49195f6c0027f3639d50f3e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291111"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="11efe-103">保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="11efe-103">Policy recommendations for securing email</span></span>
<span data-ttu-id="11efe-104">本文說明如何實作建議身分識別與裝置存取原則，以保護組織的電子郵件和支援新式驗證和條件式存取的電子郵件用戶端。</span><span class="sxs-lookup"><span data-stu-id="11efe-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="11efe-105">這份指導的[常見身分識別與裝置存取原則](identity-access-policies.md)為基礎，同時還包括一些其他強化建議。</span><span class="sxs-lookup"><span data-stu-id="11efe-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>


<span data-ttu-id="11efe-106">這些建議根據三個不同的層級的安全性和保護功能可以套用根據您所需要的精確度：**基礎**、**機密**和**高管制**。</span><span class="sxs-lookup"><span data-stu-id="11efe-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="11efe-107">您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="11efe-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="11efe-108">這些建議需要讓使用者使用新式的電子郵件用戶端，包括 Outlook for iOS 和 Android 行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="11efe-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="11efe-109">Outlook for iOS 和 Android 的 Office 365 的最佳功能提供支援。</span><span class="sxs-lookup"><span data-stu-id="11efe-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="11efe-110">這些行動的 Outlook 應用程式也會架構與安全性功能，可支援行動裝置使用和配合其他 Microsoft 雲端安全性功能。</span><span class="sxs-lookup"><span data-stu-id="11efe-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="11efe-111">如需詳細資訊，請參閱 < <b0>Outlook for iOS 和 Android 常見問題集</b0>。</span><span class="sxs-lookup"><span data-stu-id="11efe-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="11efe-112">更新加入電子郵件的一般原則</span><span class="sxs-lookup"><span data-stu-id="11efe-112">Updating common policies to include email</span></span>
<span data-ttu-id="11efe-113">下圖說明常見的身分識別與裝置存取原則，並指出哪些原則需要進行更新，以保護電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11efe-113">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email.</span></span> <span data-ttu-id="11efe-114">請注意額外的 Exchange Online，以封鎖 ActiveSync 用戶端的新規則。</span><span class="sxs-lookup"><span data-stu-id="11efe-114">Note the addition of a new rule for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="11efe-115">這會強制使用 Outlook 行動裝置。</span><span class="sxs-lookup"><span data-stu-id="11efe-115">This forces the use of Outlook mobile.</span></span>

![保護電子郵件的原則更新的摘要](../images/identity-access-ruleset-mail.png)

<span data-ttu-id="11efe-117">如果您的原則範圍中包含 Exchange Online 和 Outlook，您設定它們，您只需要建立新的原則，以封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="11efe-117">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="11efe-118">檢閱下列表格所列出的原則與下列一項將建議新增的項目，或確認這些已加入。</span><span class="sxs-lookup"><span data-stu-id="11efe-118">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="11efe-119">每個規則會連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)> 一文中的關聯的設定指示。</span><span class="sxs-lookup"><span data-stu-id="11efe-119">Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span> 

|<span data-ttu-id="11efe-120">保護層級</span><span class="sxs-lookup"><span data-stu-id="11efe-120">Protection level</span></span>|<span data-ttu-id="11efe-121">原則</span><span class="sxs-lookup"><span data-stu-id="11efe-121">Policies</span></span>|<span data-ttu-id="11efe-122">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="11efe-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="11efe-123">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="11efe-123">**Baseline**</span></span>|<span data-ttu-id="11efe-124">[登入風險*中*] 或 [*高*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="11efe-124">[Require MFA when sign-in risk is *medium* or *high*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span>|<span data-ttu-id="11efe-125">包含 Exchange Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="11efe-125">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="11efe-126">封鎖用戶端不支援新式驗證</span><span class="sxs-lookup"><span data-stu-id="11efe-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="11efe-127">包含 Exchange Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="11efe-127">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="11efe-128">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="11efe-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="11efe-129">請務必 Outlook 隨附的應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="11efe-129">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="11efe-130">請務必更新每個平台 (iOS、 Android、 Windows) 的原則</span><span class="sxs-lookup"><span data-stu-id="11efe-130">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="11efe-131">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="11efe-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="11efe-132">雲端應用程式的清單中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="11efe-132">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="11efe-133">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="11efe-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="11efe-134">包含 Exchange Online 中的雲端應用程式清單</span><span class="sxs-lookup"><span data-stu-id="11efe-134">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="11efe-135">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="11efe-135">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="11efe-136">新增這個新的原則</span><span class="sxs-lookup"><span data-stu-id="11efe-136">Add this new policy</span></span>| 
|<span data-ttu-id="11efe-137">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="11efe-137">**Sensitive**</span></span>|[<span data-ttu-id="11efe-138">*低*、*中*或*高*登入風險時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="11efe-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="11efe-139">包含 Exchange Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="11efe-139">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="11efe-140">需要相容電腦*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="11efe-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="11efe-141">雲端應用程式的清單中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="11efe-141">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="11efe-142">**高管制**</span><span class="sxs-lookup"><span data-stu-id="11efe-142">**Highly regulated**</span></span>|[<span data-ttu-id="11efe-143">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="11efe-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="11efe-144">包含 Exchange Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="11efe-144">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="11efe-145">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="11efe-145">Block ActiveSync clients</span></span>
<span data-ttu-id="11efe-146">此原則可防止 ActiveSync 用戶端略過其他條件式存取規則。</span><span class="sxs-lookup"><span data-stu-id="11efe-146">This policy prevents ActiveSync clients from bypassing other conditional access rules.</span></span> <span data-ttu-id="11efe-147">規則設定僅適用於 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="11efe-147">The rule configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="11efe-148">藉由選取**需要核准用戶端應用程式**，此原則會封鎖 ActiveSync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="11efe-148">By selecting **Require approved client app**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="11efe-149">若要設定此原則：</span><span class="sxs-lookup"><span data-stu-id="11efe-149">To configure this policy:</span></span>

1. <span data-ttu-id="11efe-150">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="11efe-150">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="11efe-151">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="11efe-151">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="11efe-152">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="11efe-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="11efe-153">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="11efe-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="11efe-154">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="11efe-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="11efe-155">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="11efe-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="11efe-156">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="11efe-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="11efe-157">選擇 [**選取應用程式**中，選取 [ **Office 365 Exchange Online**。</span><span class="sxs-lookup"><span data-stu-id="11efe-157">Choose **Select apps**, select **Office 365 Exchange Online**.</span></span> <span data-ttu-id="11efe-158">選擇 [**選取**和**完成**]。</span><span class="sxs-lookup"><span data-stu-id="11efe-158">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="11efe-159">選擇 [**條件**]，然後選擇 [**用戶端應用程式**。</span><span class="sxs-lookup"><span data-stu-id="11efe-159">Choose **Conditions**, and then choose **Client apps**.</span></span>

9. <span data-ttu-id="11efe-160">如**設定**中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="11efe-160">For **Configure**, select **Yes**.</span></span> <span data-ttu-id="11efe-161">檢查只有下列項目：**桌面用戶端和行動應用程式**和**Exchange ActiveSync 用戶端**。</span><span class="sxs-lookup"><span data-stu-id="11efe-161">Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**.</span></span> <span data-ttu-id="11efe-162">選擇 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="11efe-162">Choose **Done**.</span></span>

10. <span data-ttu-id="11efe-163">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="11efe-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="11efe-164">選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。</span><span class="sxs-lookup"><span data-stu-id="11efe-164">Choose **Grant access**, select **Require approved client app**.</span></span>  <span data-ttu-id="11efe-165">對於多個控制項，請選取 [**需要選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="11efe-165">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="11efe-166">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="11efe-166">Choose **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="11efe-167">設定 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="11efe-167">Setup Office 365 message encryption</span></span>
<span data-ttu-id="11efe-168">與新的 Office 365 郵件加密 (OME) 功能，利用 Azure 資訊保護中的保護功能，您的組織可以輕鬆地共用受保護的電子郵件與任何裝置上的任何人。</span><span class="sxs-lookup"><span data-stu-id="11efe-168">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="11efe-169">使用者可以傳送和接收受保護的郵件與其他 Office 365 組織，以及使用 Outlook.com、 Gmail，以及其他電子郵件服務的非 Office 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="11efe-169">Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="11efe-170">如需詳細資訊，請參閱 <<c0>設定新的 Office 365 郵件加密功能。</span><span class="sxs-lookup"><span data-stu-id="11efe-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span> 



## <a name="next-steps"></a><span data-ttu-id="11efe-171">後續步驟</span><span class="sxs-lookup"><span data-stu-id="11efe-171">Next steps</span></span>

[<span data-ttu-id="11efe-172">了解保護 SharePoint 網站和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="11efe-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
