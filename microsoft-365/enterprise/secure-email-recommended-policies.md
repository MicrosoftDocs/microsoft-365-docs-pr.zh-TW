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
ms.openlocfilehash: dd1504ac11f0e2eefa56572af24de14b5f87830e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866129"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="3a63d-103">保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="3a63d-103">Policy recommendations for securing email</span></span>
<span data-ttu-id="3a63d-p101">本文說明如何實作的建議的身分識別和保護組織的電子郵件和現代驗證與條件式存取支援的電子郵件用戶端裝置存取原則。這份指導是以為基礎的[一般身分識別與裝置存取的原則](identity-access-policies.md)與也包含一些其他的建議。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p101">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support Modern Authentication and Conditional Access. This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>


<span data-ttu-id="3a63d-p102">這些建議根據三種不同的層的安全性和保護可以套用根據您的需要的層次：**基準**、**機密**、 和**高度規範**。您可以深入了解這些安全性各層與建議的用戶端作業系統、 參照中的[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)這些建議。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p102">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**. You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="3a63d-p103">這些建議需要使用者使用摩登的電子郵件用戶端，包括 Outlook for iOS 及 Android 行動裝置上。IOS 及 Android 的 outlook for Office 365 的最佳功能提供支援。這些行動 Outlook 應用程式也會以支援行動裝置的功能使用並與其他 Microsoft cloud 安全性功能搭配使用的安全性架構。如需詳細資訊，請參閱[Outlook iOS 及 Android 的常見問題集](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p103">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices. Outlook for iOS and Android provide support for the best features of Office 365. These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities. For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="3a63d-112">更新加入電子郵件的一般原則</span><span class="sxs-lookup"><span data-stu-id="3a63d-112">Updating common policies to include email</span></span>
<span data-ttu-id="3a63d-p104">下圖說明常見的身分識別和裝置存取的原則會指出哪些原則需要更新來保護電子郵件。請注意的 Exchange Online 封鎖 ActiveSync 用戶端的新規則。這會強制 Outlook 使用行動裝置。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p104">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email. Note the addition of a new rule for Exchange Online to block ActiveSync clients. This forces the use of Outlook mobile.</span></span>

![保護電子郵件的原則更新的摘要](../images/identity-access-ruleset-mail.png)

<span data-ttu-id="3a63d-p105">如果在 Exchange Online 與 Outlook 中包含的原則範圍時您設定這些，您只需要建立新的原則來封鎖 ActiveSync 用戶端。請檢閱下表所列的原則並其中一個建議新增的項目，或確認這些是已包含在內。[常見的身分識別與裝置存取原則](identity-access-policies.md)文章中的關聯的設定指示每一個規則連結。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p105">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients. Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included. Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span> 

|<span data-ttu-id="3a63d-120">保護層級</span><span class="sxs-lookup"><span data-stu-id="3a63d-120">Protection level</span></span>|<span data-ttu-id="3a63d-121">Policies</span><span class="sxs-lookup"><span data-stu-id="3a63d-121">Policies</span></span>|<span data-ttu-id="3a63d-122">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3a63d-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="3a63d-123">**基準**</span><span class="sxs-lookup"><span data-stu-id="3a63d-123">**Baseline**</span></span>|[<span data-ttu-id="3a63d-124">登入風險為*medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="3a63d-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3a63d-125">Exchange Online 中包含的雲端應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="3a63d-125">Include Exchange Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="3a63d-126">不支援經過驗證的封鎖用戶端</span><span class="sxs-lookup"><span data-stu-id="3a63d-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="3a63d-127">Exchange Online 中包含的雲端應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="3a63d-127">Include Exchange Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="3a63d-128">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="3a63d-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="3a63d-p106">請務必 Outlook 隨附的應用程式清單中。請務必更新每個平台 (iOS、 Android、 Windows) 的原則。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p106">Be sure Outlook is included in the list of apps. Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="3a63d-131">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="3a63d-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="3a63d-132">Exchange Online 中包含的雲端應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="3a63d-132">Include Exchange Online in the list of cloud apps.</span></span>|
|        |[<span data-ttu-id="3a63d-133">需要相容的 Pc</span><span class="sxs-lookup"><span data-stu-id="3a63d-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="3a63d-134">Exchange Online 中包含的雲端應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="3a63d-134">Include Exchange Online in list of cloud apps.</span></span>|
|        |[<span data-ttu-id="3a63d-135">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="3a63d-135">Block ActiveSync clients</span></span>](#block-activesync)|<span data-ttu-id="3a63d-136">新增此新原則。</span><span class="sxs-lookup"><span data-stu-id="3a63d-136">Add this new policy.</span></span> 
|<span data-ttu-id="3a63d-137">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="3a63d-137">**Sensitive**</span></span>|[<span data-ttu-id="3a63d-138">登入風險為*低*、 *medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="3a63d-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="3a63d-139">Exchange Online 中包含的雲端應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="3a63d-139">Include Exchange Online in the assignments of cloud apps.</span></span>|
|         |[<span data-ttu-id="3a63d-140">需要相容的 Pc*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="3a63d-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="3a63d-141">Exchange Online 中包含的雲端應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="3a63d-141">Include Exchange Online in the list of cloud apps.</span></span>|
|<span data-ttu-id="3a63d-142">**高管制**</span><span class="sxs-lookup"><span data-stu-id="3a63d-142">**Highly regulated**</span></span>|[<span data-ttu-id="3a63d-143">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="3a63d-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3a63d-144">包含 Exchange Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="3a63d-144">Include Exchange Online in the assignments of cloud apps</span></span> |

## <a name="block-activesync-clients"></a><span data-ttu-id="3a63d-145">封鎖 ActiveSync 用戶端</span><span class="sxs-lookup"><span data-stu-id="3a63d-145">Block ActiveSync clients</span></span>
<span data-ttu-id="3a63d-p107">此原則可禁止 ActiveSync 用戶端略過其他條件式存取規則。規則設定僅適用於 ActiveSync 用戶端。選取 [**需要核准用戶端應用程式**，此原則會封鎖 ActiveSync 用戶端。若要設定此原則：</span><span class="sxs-lookup"><span data-stu-id="3a63d-p107">This policy prevents ActiveSync clients from bypassing other conditional access rules. The rule configuration applies only to ActiveSync clients. By selecting **Require approved client app**, this policy blocks ActiveSync clients. To configure this policy:</span></span>

1. <span data-ttu-id="3a63d-p108">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p108">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="3a63d-152">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="3a63d-153">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="3a63d-154">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="3a63d-155">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="3a63d-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="3a63d-156">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="3a63d-p109">選擇 [**選取應用程式**中，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p109">Choose **Select apps**, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>
8. <span data-ttu-id="3a63d-159">選擇 [**條件**]，然後選擇 [**用戶端應用程式**。</span><span class="sxs-lookup"><span data-stu-id="3a63d-159">Choose **Conditions**, and then choose **Client apps**.</span></span>
9. <span data-ttu-id="3a63d-p110">針對**設定**] 中選取 **[是]**。檢查只有下列項目：**行動應用程式和桌面用戶端**與**Exchange ActiveSync 用戶端**。按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p110">For **Configure**, select **Yes**. Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**. Click **Done**.</span></span>

10. <span data-ttu-id="3a63d-163">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="3a63d-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="3a63d-p111">選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。 多個控制項，選取 [**需要在選定的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p111">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="3a63d-166">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a63d-166">Click **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="3a63d-167">安裝 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="3a63d-167">Setup Office 365 message encryption</span></span>
<span data-ttu-id="3a63d-p112">新的 Office 365 郵件加密 (OME) 功能運用在 Azure 資訊保護的保護功能，您的組織可以輕鬆地共用受保護的電子郵件與任何裝置上的任何人。使用者可以傳送及接收與其他 Office 365 組織以及非 Office 365 客戶使用 Outlook.com、 Gmail，以及其他電子郵件服務受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="3a63d-p112">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="3a63d-170">如需詳細資訊，請參閱 ＜ [Set up Office 365 郵件加密的新功能](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)。</span><span class="sxs-lookup"><span data-stu-id="3a63d-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span> 

<!---
This article describes recommended policies to help you secure organizational email and email clients that support Modern Authentication and Conditional Access. These recommendations are in addition to the [common identity and access policy recommendations](identity-access-policies.md).

The following recommendations are based on three different layers of security and protection for your email that can be applied based on the granularity of your needs:

- **Baseline**: Microsoft recommends you establish a minimum standard for protecting data, as well as the identities and devices that access your data. Microsoft provides strong default protection that meets the needs of many organizations. Some organizations require additional capabilities to meet their baseline requirements.
- **Sensitive**: Some customers have a subset of data that must be protected at higher levels. You can apply increased protection to specific data sets in your Office 365 environment. Microsoft recommends protecting identities and devices that access sensitive data with comparable levels of security. 
- **Highly regulated**: Some organizations may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

See the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md) topic for more details.

> [!IMPORTANT]
> All security groups created as part of these recommendations must be created with Office features enabled. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.
>
>![Office features enabled for security groups](./media/security-group.png)
>

## Baseline
To create a new conditional access policy: 

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **Azure Active Directory** from the left menu.

3. Under the **Security** section, choose **Conditional access**.

4. Choose **New policy** as shown in the screen-shot below:

![Baseline CA policy](./media/secure-email/CA-EXO-policy-1.png)

The following tables describe the appropriate settings necessary to express the policies required for each level of protection.

### Medium and above risk requires MFA

The following tables describes the conditional access policy settings to implement for this policy.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users.|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||
|Conditions|Configured|Yes|Configure specific to your environment and needs|
|Sign-in risk|Risk level|High, medium|Check both|

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require compliant devices|False||
||Require domain joined devices|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device

To create a conditional access policy for Exchange Online:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **Azure Active Directory** from the left menu.

3. Under the **Security** section, choose **Conditional access**.

4. Choose **New policy**.

5. Enter a policy name, then choose the **Users and groups** you want to apply the policy for.

6. Choose **Cloud apps**.

7. Choose **Select apps**, select **Office 365 Exchange Online** from the **Cloud apps** list, click on **Select**. Once the **Office 365 Exchange Online** app is selected, click **Done**.

8. Choose **Grant** from the **Access controls** section.

9. Choose **Grant access**, select both **Require device to be marked as compliant** and **Require domain joined (Hybrid Azure AD)**, then choose **Select**.

10. Click **Create** to create the Exchange Online conditional access policy.

    > [!NOTE]
    > Beginning with Intune on Azure, you have to create all conditional access policies in the Azure Active Directory workload. Intune provides a link to Azure AD conditional access policies workload from its portal  for convenience.

    > [!IMPORTANT]
    > If you need assistance on migrating conditional access policies previously created in the Intune classic portal to the Intune on Azure portal, see the [reassign conditional access policies from Intune classic portal to the Azure portal](https://docs.microsoft.com/intune/conditional-access-intune-reassign) topic. 

### App-based conditional access for Exchange Online

You can add one more security layer by setting up an app-based conditional access policy for Exchange Online in the Intune on Azure portal. When you apply an app-based conditional access for Exchange Online you require users to use a specific app (E.g. Microsoft Outlook app) to access corporate e-mail.

To add an app-based conditional access policy:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **More services** from the left menu, then type: "**Intune**".

3. Choose **Intune App Protection**.

4. On the **Intune mobile application management** blade choose **All Settings**.

5. Choose **Exchange Online** under the **Conditional access** section.

6. Select **Allow apps that support Intune app policies**, then choose the app (E.g. Microsoft Outlook).

7. Choose **Restricted user groups**, click **Select groups**, select the user or group you want to apply the policy for, then click **Select**.

## Sensitive

### Low and above risk requires MFA
The following tables describes the conditional access policy settings to implement for low- and above-risk policies.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||
|Conditions|Configured|Yes|Configure specific to your environment and needs|
|Sign-in risk|Configured|Yes|Configure specific to your environment and needs|
||Risk level|Low, medium, high|Check all three|

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
||Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require compliant devices|False||
||Require domain joined device|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device
(See baseline instructions)

### App-based conditional access for Exchange online

(See baseline instructions)

#### Apply to

Once the pilot project has been completed, these policies should be applied to users in your organization who require access to email considered sensitive.

## Highly regulated
### MFA required

The following tables describes the conditional access policy settings to implement for the highly regulated policy.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require complaint devices|False|Check|
||Require domain joined device|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device
(See baseline instructions)
### App-based conditional access for Exchange online
(See baseline instructions)
#### Apply to
Once the pilot project has been completed, these policies should be applied to users in your organization who require access to email considered highly regulated.

### High risk users policy
To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.

Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users|Include|All users|Selected|
||Exclude|None||
|Conditions|User risk|High|Selected|

**Controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
||Access|Allow access|True|Selected|
||Access|Require password change|True|Check|

**Review:** not applicable

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

## Additional configurations
In addition to the above policies, you must configure the following Mobile Application and Device Management settings discussed in this section.

### Intune mobile application management

To ensure email is protected by the policy recommendations stated earlier for each security and data protection tier, you must create Intune app protection policies from within the Azure portal.

To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune App Protection > App policy**.

Add a new policy (+Add) as shown in the following screen shot:

![Intune mobile application management](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android.
>

The following tables describe the recommended Intune app protection policy settings:

**General**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Email|Name|Secure email policy for Android|Enter a policy name|
||Description||Enter text that describes the policy|
||Platform|Android|There are slight differences in the app protection policy options between iOS and Android; this policy is specifically for Android|

**Apps**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Applications|Apps|Outlook|Selected (list)|

**Settings**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Data relocation|Prevent Android backup|Yes|On iOS this will specifically call out iTunes and iCloud|
|||Allow app to transfer data to other apps|Policy managed apps||
||Allow app to receive data to other apps|Policy managed apps||
||Prevent "Save As"|Yes||
||Restrict cut, copy, and paste with other apps|Policy managed apps||
||Restrict web content to display in the managed browser|No||
||Encrypt app data|Yes|On iOS select option: When device is locked|
||Disable contacts sync|No||
|Access|Require PIN for access|Yes||
||Number of attempts before PIN reset|3||
||Allow simple PIN|No||
||PIN length|6||
||Allow fingerprint instead of PIN|Yes||
||Require Corporate credentials for access|No||
||Block managed apps from running on jailbroken or rooted devices|Yes||
||Recheck the access requirement after (minutes)|30||
||Offline grace period|720||
||Offline interval (days) before app data is wiped|90||
||Block screen capture and Android assistant|No|On iOS this is not an available option|

When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.

- See [how to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies) for more details.

### Intune mobile device management
You create the following device configuration profiles and device compliance policies by logging into the [Intune on Azure portal](https://portal.azure.com) with your Intune credentials.

#### iOS email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (iOS) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host (#)|Outlook.office365.com||
||Account Name (#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
||Use S/MIME|False||
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Use SSL|True|Check|
||Allow messages to be moved to other email accounts|False||
||Allow email to be sent from third party applications|True||
||Synchronize recently used email addresses|True|Check|

#### Android email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (Android) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host (#)| Outlook.office365.com|
||Account Name (#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
||Use S/MIME|False||
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Sync schedule|Not configured|Selected – Drop down|
||Use SSL|True|Check|
||Content type to synchronize|||
||Email|True|Check (locked)|
||Contacts|True|Check|
||Calenadr|True|Check|
||Tasks|True|Check|
||Notes|True|Check|

#### Android for work email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (Android for Work) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host(#)| Outlook.office365.com|
||Account Name(#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Use SSL|True|Check|

#### Device compliance policy
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device compliance policies at **Device compliance > Policies > Create Policy > Platform (iOS, Android or others) > Settings**.

**System security**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Password|Require a password to unlock mobile devices (...)|Yes|Selected – Drop down|
||Allow simple passwords (...)|No|Selected – Drop down|
||Minimum password length (...)|6|Selected – List|
|Advanced password settings|All|Not configured||
|Encryption|Require encryption on mobile device (...)|Yes|Selected – Drop down|
|Email profiles|Email account must be managed by Intune (iOS 8.0+)|Yes| Selected  – Drop down|
||Select (#)||Must select Email Configuration Policy for iOS: iOS Email Policy (see configuration policies above)|

**Device health**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Windows decide health attestation|Require devices to be reported as healthy (Windows 10 Desktop and Mobile and later)|Yes||
|Device security settings|All|Not configured||
|Device threat protection|All|Not configured||
|Jailbreak|Device must not be jailbroken or rooted (iOS 8.0+, Android 4.0+)|Yes||

**Device properties**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Operating system version|All|Not configured||

For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).

## Remediating medium or high risk access events
If a user reports that they are now expected to perform MFA when this was previously not required, support can review their status from a risk perspective.  

Users within the organization with a Global Administrator or Security Administrator role can use Azure AD Identity Protection to review the risky events that contributed to the calculated risk score. If they identify some events that were flagged as suspicious, but are confirmed to be valid (such as a login from an unfamiliar location when an employee is on vacation), the administrator can resolve the event so it no longer contributes to the risk score.
--->

## <a name="next-steps"></a><span data-ttu-id="3a63d-171">接下來的步驟</span><span class="sxs-lookup"><span data-stu-id="3a63d-171">Next steps</span></span>

[<span data-ttu-id="3a63d-172">了解保護 SharePoint 網站和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="3a63d-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
