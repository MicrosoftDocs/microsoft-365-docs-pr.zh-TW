---
title: 保護商務用 Microsoft 365 方案的十大方式
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: '保護您的商務電子郵件和網路威脅中的資料，包括勒索軟體、網路釣魚和惡意附件。 '
ms.openlocfilehash: c78e65e9a466fe8b95e83fa1791dd8f09fa0c541
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948733"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a><span data-ttu-id="673c0-103">保護商務用 Microsoft 365 方案的十大方式</span><span class="sxs-lookup"><span data-stu-id="673c0-103">Top 10 ways to secure Microsoft 365 for business plans</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="673c0-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="673c0-104">The admin center is changing.</span></span> <span data-ttu-id="673c0-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="673c0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="673c0-106">如果您是使用 Microsoft 商務方案之一的小型或中型組織，且您的組織類型是由網路罪犯和駭客的目標所組成，請使用本文中的指導方針增加組織的安全性。</span><span class="sxs-lookup"><span data-stu-id="673c0-106">If you are a small or medium-size organization using one of Microsoft's business plans and your type of organization is targeted by cyber criminals and hackers, use the guidance in this article to increase the security of your organization.</span></span> <span data-ttu-id="673c0-107">本指南可協助您的組織達成 Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/p/?linkid=2015598)中所述的目標。</span><span class="sxs-lookup"><span data-stu-id="673c0-107">This guidance helps your organization achieve the goals described in the Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/p/?linkid=2015598).</span></span>

<span data-ttu-id="673c0-108">Microsoft 建議您完成下清單格中所列的工作，以套用至您的服務方案。</span><span class="sxs-lookup"><span data-stu-id="673c0-108">Microsoft recommends that you complete the tasks listed in the following table that apply to your service plan.</span></span>

||<span data-ttu-id="673c0-109">工作</span><span class="sxs-lookup"><span data-stu-id="673c0-109">Task</span></span>|<span data-ttu-id="673c0-110">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="673c0-110">Microsoft 365 Business Standard</span></span>|<span data-ttu-id="673c0-111">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="673c0-111">Microsoft 365 Business Premium</span></span>|
|---|---|---|---|
|<span data-ttu-id="673c0-112">1 </span><span class="sxs-lookup"><span data-stu-id="673c0-112">1</span></span>|[<span data-ttu-id="673c0-113">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="673c0-113">Set up multi-factor authentication</span></span>](secure-your-business-data.md#setup)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-116">2 </span><span class="sxs-lookup"><span data-stu-id="673c0-116">2</span></span>|[<span data-ttu-id="673c0-117">訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="673c0-117">Train your users</span></span>](secure-your-business-data.md#train)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-120">3 </span><span class="sxs-lookup"><span data-stu-id="673c0-120">3</span></span>|[<span data-ttu-id="673c0-121">使用專用的系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="673c0-121">Use dedicated admin accounts</span></span>](secure-your-business-data.md#admin)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-124">4 </span><span class="sxs-lookup"><span data-stu-id="673c0-124">4</span></span>|[<span data-ttu-id="673c0-125">提升郵件中惡意程式碼的保護層級</span><span class="sxs-lookup"><span data-stu-id="673c0-125">Raise the level of protection against malware in mail</span></span>](secure-your-business-data.md#malware)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-128">5 </span><span class="sxs-lookup"><span data-stu-id="673c0-128">5</span></span>|[<span data-ttu-id="673c0-129">防範勒索軟體</span><span class="sxs-lookup"><span data-stu-id="673c0-129">Protect against ransomware</span></span>](secure-your-business-data.md#ransomware)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-132">6 </span><span class="sxs-lookup"><span data-stu-id="673c0-132">6</span></span>|[<span data-ttu-id="673c0-133">停止電子郵件的自動轉寄功能</span><span class="sxs-lookup"><span data-stu-id="673c0-133">Stop auto-forwarding for email</span></span>](secure-your-business-data.md#forwarding)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-136">7 </span><span class="sxs-lookup"><span data-stu-id="673c0-136">7</span></span>|[<span data-ttu-id="673c0-137">使用 Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="673c0-137">Use Office Message Encryption</span></span>](secure-your-business-data.md#encryption)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-139">8 </span><span class="sxs-lookup"><span data-stu-id="673c0-139">8</span></span>|[<span data-ttu-id="673c0-140">保護您的電子郵件免受網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="673c0-140">Protect your email from phishing attacks</span></span>](secure-your-business-data.md#phishing)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-142">9 </span><span class="sxs-lookup"><span data-stu-id="673c0-142">9</span></span>|[<span data-ttu-id="673c0-143">使用 ATP 安全附件防護惡意附件和檔案</span><span class="sxs-lookup"><span data-stu-id="673c0-143">Protect against malicious attachments and files with ATP Safe Attachments</span></span>](secure-your-business-data.md#atp)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|<span data-ttu-id="673c0-145">10 </span><span class="sxs-lookup"><span data-stu-id="673c0-145">10</span></span>|[<span data-ttu-id="673c0-146">使用 ATP 安全連結防禦網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="673c0-146">Protect against phishing attacks with ATP Safe Links</span></span>](secure-your-business-data.md#phishingatp)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

<span data-ttu-id="673c0-148">開始之前，請先在 Microsoft 365 安全性中心檢查您的 [microsoft 365 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 。</span><span class="sxs-lookup"><span data-stu-id="673c0-148">Before you begin, check your [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) in the Microsoft 365 security center.</span></span> <span data-ttu-id="673c0-149">您可以從集中式儀表板，監視及提高 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="673c0-149">From a centralized dashboard, you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span> <span data-ttu-id="673c0-150">您可以在設定建議的安全性功能、執行安全性相關工作 (例如查看報告) 或使用協力廠商應用程式或軟體解決建議等方面提供積分。</span><span class="sxs-lookup"><span data-stu-id="673c0-150">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing recommendations with a third-party application or software.</span></span> <span data-ttu-id="673c0-151">透過更深入的見解和更深入的 Microsoft 產品和服務集合，您可以自信地報告組織的安全性健康情況。</span><span class="sxs-lookup"><span data-stu-id="673c0-151">With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting about your organization's security health.</span></span>

![Microsoft 安全分數的螢幕擷取畫面](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a><span data-ttu-id="673c0-153">1：設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="673c0-153">1: Set up multi-factor authentication</span></span>
<span data-ttu-id="673c0-154"><a name="setup"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-154"><a name="setup"> </a></span></span>

<span data-ttu-id="673c0-155">使用多重要素驗證是增加組織安全性的最簡單且最有效的方式之一。</span><span class="sxs-lookup"><span data-stu-id="673c0-155">Using multi-factor authentication is one of the easiest and most effective ways to increase the security of your organization.</span></span> <span data-ttu-id="673c0-156">它會比您登入時更輕鬆-當您登入時，多重要素驗證表示您會輸入您的電話中的程式碼，以取得 Microsoft 365 的存取權。</span><span class="sxs-lookup"><span data-stu-id="673c0-156">It's easier than it sounds - when you log in, multi-factor authentication means you'll type a code from your phone to get access to Microsoft 365.</span></span> <span data-ttu-id="673c0-157">這可防止駭客在知道密碼的情況時採取行動。</span><span class="sxs-lookup"><span data-stu-id="673c0-157">This can prevent hackers from taking over if they know your password.</span></span> <span data-ttu-id="673c0-158">多重要素驗證也稱為雙步驟驗證。</span><span class="sxs-lookup"><span data-stu-id="673c0-158">Multi-factor authentication is also called 2-step verification.</span></span> <span data-ttu-id="673c0-159">個人可以輕鬆地將兩步驟驗證新增至大多數帳戶，例如，加入其 Google 或 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="673c0-159">Individuals can add 2-step verification to most accounts easily, for example, to their Google or Microsoft accounts.</span></span> <span data-ttu-id="673c0-160">以下說明如何 [將兩步驟驗證新增至您的個人 Microsoft 帳戶](https://go.microsoft.com/fwlink/p/?linkid=2016403)。</span><span class="sxs-lookup"><span data-stu-id="673c0-160">Here's how to [add two-step verification to your personal Microsoft account](https://go.microsoft.com/fwlink/p/?linkid=2016403).</span></span>

<span data-ttu-id="673c0-161">針對使用 Microsoft 365 的企業，新增設定，以要求使用者使用多重要素驗證來登入。</span><span class="sxs-lookup"><span data-stu-id="673c0-161">For businesses using Microsoft 365, add a setting that requires your users to log in using multi-factor authentication.</span></span> <span data-ttu-id="673c0-162">當您進行此項變更時，系統會提示使用者在下一次登入時設定其電話進行兩個要素驗證。</span><span class="sxs-lookup"><span data-stu-id="673c0-162">When you make this change, users will be prompted to set up their phone for two-factor authentication next time they log in.</span></span>
<span data-ttu-id="673c0-163">若要查看如何設定 MFA 的訓練影片和使用者完成設定的方式，請參閱 [設定 mfa](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) 和 [使用者設定](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)。</span><span class="sxs-lookup"><span data-stu-id="673c0-163">To see a training video for how to set up MFA and how users complete the set up, see [set up MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) and [user set up](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225).</span></span>

<span data-ttu-id="673c0-164">若要設定多重要素驗證，請開啟安全性預設值：</span><span class="sxs-lookup"><span data-stu-id="673c0-164">To set up multi-factor authentication, you turn on Security defaults:</span></span>

<span data-ttu-id="673c0-165">大部分的組織，安全性預設值皆提供有良好的額外登入安全性。</span><span class="sxs-lookup"><span data-stu-id="673c0-165">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="673c0-166">如需詳細資訊，請參閱[什麼是安全性預設？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="673c0-166">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="673c0-167">如果您新訂閱，則系統可能會自動為您開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="673c0-167">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="673c0-168">您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性**窗格中，啟用或停用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="673c0-168">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="673c0-169">使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="673c0-169">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="673c0-170">在左側導覽中，請選擇 **[顯示所有]**，然後在 **[系統管理中心]** 底下，選擇 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-170">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="673c0-171">在 **[Azure Active Directory 系統管理中心]** 選擇 **[Azure Active Directory** > **屬性]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-171">In the **Azure Active Directory admin center** choose **Azure Active Directory** > **Properties**.</span></span>
4. <span data-ttu-id="673c0-172">在頁面底部，選取 **[管理安全性預設]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-172">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="673c0-173">選擇 **[是]** 以啟用安全性預設，或 **[否]** 以停用安全性預設，然後選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-173">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="673c0-174">為組織設定多重要素驗證之後，您的使用者必須在其裝置上設定雙步驟驗證。</span><span class="sxs-lookup"><span data-stu-id="673c0-174">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="673c0-175">如需詳細資訊，請參閱 [設定 Microsoft 365 的2步驟驗證](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="673c0-175">For more information, see [Set up 2-step verification for Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="673c0-176">如需完整詳細資料和完整建議，請參閱 [設定使用者的多重要素驗證](set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="673c0-176">For full details and complete recommendations, see [Set up multi-factor authentication for users](set-up-multi-factor-authentication.md).</span></span>

## <a name="2-train-your-users"></a><span data-ttu-id="673c0-177">2：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="673c0-177">2: Train your users</span></span>
<span data-ttu-id="673c0-178"><a name="train"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-178"><a name="train"> </a></span></span>

<span data-ttu-id="673c0-179">Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/p/?linkid=2015598) 提供好的指導方針，可為組織內的安全性感知建立強大的文化，包括訓練使用者來識別網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="673c0-179">The Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/p/?linkid=2015598) provides excellent guidance on establishing a strong culture of security awareness within your organization, including training users to identify phishing attacks.</span></span>

<span data-ttu-id="673c0-180">除了這項指導之外，Microsoft 也建議您的使用者採取本文所述的動作： [保護您的帳戶和裝置免受駭客和惡意](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)代碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="673c0-180">In addition to this guidance, Microsoft recommends that your users take the actions described in this article: [Protect your account and devices from hackers and malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6).</span></span> <span data-ttu-id="673c0-181">這些動作包括：</span><span class="sxs-lookup"><span data-stu-id="673c0-181">These actions include:</span></span>

- <span data-ttu-id="673c0-182">使用強式密碼</span><span class="sxs-lookup"><span data-stu-id="673c0-182">Using strong passwords</span></span>

- <span data-ttu-id="673c0-183">保護裝置</span><span class="sxs-lookup"><span data-stu-id="673c0-183">Protecting devices</span></span>

- <span data-ttu-id="673c0-184">啟用 Windows 10 和 Mac 電腦上的安全性功能</span><span class="sxs-lookup"><span data-stu-id="673c0-184">Enabling security features on Windows 10 and Mac PCs</span></span>

<span data-ttu-id="673c0-185">Microsoft 也建議您採取下列文章中建議的動作來保護其個人電子郵件帳戶：</span><span class="sxs-lookup"><span data-stu-id="673c0-185">Microsoft also recommends that users protect their personal email accounts by taking the actions recommended in the following articles:</span></span>

- [<span data-ttu-id="673c0-186">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="673c0-186">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [<span data-ttu-id="673c0-187">使用2步驟驗證保護您的 Gmail 帳戶</span><span class="sxs-lookup"><span data-stu-id="673c0-187">Protect your Gmail account with 2-step verification</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a><span data-ttu-id="673c0-188">3：使用專用的系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="673c0-188">3: Use dedicated admin accounts</span></span>
<span data-ttu-id="673c0-189"><a name="admin"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-189"><a name="admin"> </a></span></span>

<span data-ttu-id="673c0-190">您用來管理 Microsoft 365 環境的管理帳戶包含較高的許可權。</span><span class="sxs-lookup"><span data-stu-id="673c0-190">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="673c0-191">這些是駭客和網路罪犯的有用目標。</span><span class="sxs-lookup"><span data-stu-id="673c0-191">These are valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="673c0-192">僅使用系統管理帳戶進行管理。</span><span class="sxs-lookup"><span data-stu-id="673c0-192">Use admin accounts only for administration.</span></span> <span data-ttu-id="673c0-193">系統管理員應該要有個別的使用者帳戶，以進行一般的非系統管理，而且只有在必要時才使用系統管理帳戶，才可完成與工作職能相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="673c0-193">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span> <span data-ttu-id="673c0-194">其他建議：</span><span class="sxs-lookup"><span data-stu-id="673c0-194">Additional recommendations:</span></span>

- <span data-ttu-id="673c0-195">請確定系統管理員帳戶也設定進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="673c0-195">Be sure admin accounts are also set up for multi-factor authentication.</span></span>

- <span data-ttu-id="673c0-196">使用系統管理員帳戶之前，請先關閉所有不相關的瀏覽器會話和應用程式（包括個人電子郵件帳戶）。</span><span class="sxs-lookup"><span data-stu-id="673c0-196">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span>

- <span data-ttu-id="673c0-197">完成系統管理工作之後，請務必登出瀏覽器會話。</span><span class="sxs-lookup"><span data-stu-id="673c0-197">After completing admin tasks, be sure to log out of the browser session.</span></span>

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="673c0-198">4：提升郵件中惡意程式碼的保護層級</span><span class="sxs-lookup"><span data-stu-id="673c0-198">4: Raise the level of protection against malware in mail</span></span>
<span data-ttu-id="673c0-199"><a name="malware"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-199"><a name="malware"> </a></span></span>

<span data-ttu-id="673c0-200">您的 Microsoft 365 環境包括防範惡意程式碼，但是您可以使用常見於惡意程式碼的檔案類型來封鎖附件，以提升這種保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-200">Your Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="673c0-201">若要在電子郵件中增加惡意程式碼保護，請觀看 [簡短的訓練影片](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="673c0-201">To bump up malware protection in email, view a [short training video](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0), or complete the following steps:</span></span>

1. <span data-ttu-id="673c0-202">移至 <https://protection.office.com> 並以您的系統管理員帳號憑證登入。</span><span class="sxs-lookup"><span data-stu-id="673c0-202">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="673c0-203">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**] \> **Anti-Malware**。</span><span class="sxs-lookup"><span data-stu-id="673c0-203">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="673c0-204">按兩下預設原則，以編輯此全公司原則。</span><span class="sxs-lookup"><span data-stu-id="673c0-204">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="673c0-205">選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="673c0-205">Select **Settings**.</span></span>

5. <span data-ttu-id="673c0-206">在 [ **一般附件類型篩選**] 底下，選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-206">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="673c0-207">封鎖的檔案類型會列在此控制項底下的視窗中。</span><span class="sxs-lookup"><span data-stu-id="673c0-207">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="673c0-208">您可以稍後新增或刪除檔案類型（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="673c0-208">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="673c0-209">選取 [ **儲存]。**</span><span class="sxs-lookup"><span data-stu-id="673c0-209">Select **Save.**</span></span>

<span data-ttu-id="673c0-210">如需詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="673c0-210">For more information, see [Anti-malware protection in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).</span></span>

## <a name="5-protect-against-ransomware"></a><span data-ttu-id="673c0-211">5：防禦勒索軟體</span><span class="sxs-lookup"><span data-stu-id="673c0-211">5: Protect against ransomware</span></span>
<span data-ttu-id="673c0-212"><a name="ransomware"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-212"><a name="ransomware"> </a></span></span>

<span data-ttu-id="673c0-213">勒索軟體會以加密檔案或鎖定電腦畫面限制存取資料。</span><span class="sxs-lookup"><span data-stu-id="673c0-213">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="673c0-214">然後，它會詢問 "ransom" （通常是在 exchange 中的 cryptocurrencies 如 Bitcoin），以從受害者 extort 金錢，以供 exchange 存取資料。</span><span class="sxs-lookup"><span data-stu-id="673c0-214">It then attempts to extort money from victims by asking for "ransom," usually in form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="673c0-215">您可以建立一或多個郵件流程規則來封鎖勒索軟體常用的副檔名，或警告使用電子郵件接收這些附件的使用者，以防禦勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="673c0-215">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware, or to warn users who receive these attachments in email.</span></span> <span data-ttu-id="673c0-216">最好的起點是建立兩個規則：</span><span class="sxs-lookup"><span data-stu-id="673c0-216">A good starting point is to create two rules:</span></span>

- <span data-ttu-id="673c0-217">在開啟包含宏的 Office 檔案附件之前警告使用者。</span><span class="sxs-lookup"><span data-stu-id="673c0-217">Warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="673c0-218">勒索軟體可以隱藏在宏內，因此我們會警告使用者不要從他們不知道的人開啟這些檔案。</span><span class="sxs-lookup"><span data-stu-id="673c0-218">Ransomware can be hidden inside macros, so we'll warn users to not open these files from people they do not know.</span></span>

- <span data-ttu-id="673c0-219">封鎖可能包含勒索代碼或其他惡意程式碼的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="673c0-219">Block file types that could contain ransomware or other malicious code.</span></span> <span data-ttu-id="673c0-220">我們將從下表中列出的可執行檔 (的一般清單開始，) 。</span><span class="sxs-lookup"><span data-stu-id="673c0-220">We'll start with a common list of executables (listed in the table below).</span></span> <span data-ttu-id="673c0-221">如果您的組織使用任何這些可執行類型，而您想要以電子郵件傳送這些可執行檔案類型，請將它們新增至上一個規則 (警告使用者) 。</span><span class="sxs-lookup"><span data-stu-id="673c0-221">If your organization uses any of these executable types and you expect these to be sent in email, add these to the previous rule (warn users).</span></span>

<span data-ttu-id="673c0-222">若要建立郵件傳輸規則、查看 [簡短的訓練影片](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="673c0-222">To create a mail transport rule, view a [short training video](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad), or complete the following steps:</span></span>

1. <span data-ttu-id="673c0-223">移至 [Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)。</span><span class="sxs-lookup"><span data-stu-id="673c0-223">Go to the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104).</span></span>

2. <span data-ttu-id="673c0-224">在 [ **郵件流程** ] 類別中，選取 [ **規則**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-224">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="673c0-225">選取 [] **+** ，然後 **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="673c0-225">Select **+**, and then **Create a new rule**.</span></span>

4. <span data-ttu-id="673c0-226">選取對話方塊底部的 [\* \* \* \*]，以查看完整的選項組。</span><span class="sxs-lookup"><span data-stu-id="673c0-226">Select \*\*\*\* at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="673c0-227">針對每個規則套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-227">Apply the settings in the following table for each rule.</span></span> <span data-ttu-id="673c0-228">除非您想要變更這些設定，否則請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="673c0-228">Leave the rest of the settings at the default, unless you want to change these.</span></span>

6. <span data-ttu-id="673c0-229">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="673c0-229">Select **Save**.</span></span>
    
| <span data-ttu-id="673c0-230">設定</span><span class="sxs-lookup"><span data-stu-id="673c0-230">Setting</span></span> | <span data-ttu-id="673c0-231">開啟 Office 檔案的附件之前警告使用者</span><span class="sxs-lookup"><span data-stu-id="673c0-231">Warn users before opening attachments of Office files</span></span> | <span data-ttu-id="673c0-232">封鎖可能包含勒索代碼或其他惡意程式碼的檔案類型</span><span class="sxs-lookup"><span data-stu-id="673c0-232">Block file types that could contain ransomware or other malicious code</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="673c0-233">姓名</span><span class="sxs-lookup"><span data-stu-id="673c0-233">Name</span></span>  <br/> |<span data-ttu-id="673c0-234">反內部的勒索軟體規則：警告使用者</span><span class="sxs-lookup"><span data-stu-id="673c0-234">Anti-ransomware rule: warn users</span></span>  <br/> |<span data-ttu-id="673c0-235">防勒索軟體規則：封鎖檔案類型</span><span class="sxs-lookup"><span data-stu-id="673c0-235">Anti-ransomware rule: block file types</span></span>  <br/> |
|<span data-ttu-id="673c0-236">將此規則套用至 if。</span><span class="sxs-lookup"><span data-stu-id="673c0-236">Apply this rule if .</span></span> <span data-ttu-id="673c0-237">.</span><span class="sxs-lookup"><span data-stu-id="673c0-237">.</span></span> <span data-ttu-id="673c0-238">.</span><span class="sxs-lookup"><span data-stu-id="673c0-238">.</span></span>  <br/> |<span data-ttu-id="673c0-239">任何附件。</span><span class="sxs-lookup"><span data-stu-id="673c0-239">Any attachment .</span></span> <span data-ttu-id="673c0-240">.</span><span class="sxs-lookup"><span data-stu-id="673c0-240">.</span></span> <span data-ttu-id="673c0-241">.</span><span class="sxs-lookup"><span data-stu-id="673c0-241">.</span></span> <span data-ttu-id="673c0-242">副檔名符合。</span><span class="sxs-lookup"><span data-stu-id="673c0-242">file extension matches .</span></span> <span data-ttu-id="673c0-243">.</span><span class="sxs-lookup"><span data-stu-id="673c0-243">.</span></span> <span data-ttu-id="673c0-244">.</span><span class="sxs-lookup"><span data-stu-id="673c0-244">.</span></span>  <br/> |<span data-ttu-id="673c0-245">任何附件。</span><span class="sxs-lookup"><span data-stu-id="673c0-245">Any attachment .</span></span> <span data-ttu-id="673c0-246">.</span><span class="sxs-lookup"><span data-stu-id="673c0-246">.</span></span> <span data-ttu-id="673c0-247">.</span><span class="sxs-lookup"><span data-stu-id="673c0-247">.</span></span> <span data-ttu-id="673c0-248">副檔名符合。</span><span class="sxs-lookup"><span data-stu-id="673c0-248">file extension matches .</span></span> <span data-ttu-id="673c0-249">.</span><span class="sxs-lookup"><span data-stu-id="673c0-249">.</span></span> <span data-ttu-id="673c0-250">.</span><span class="sxs-lookup"><span data-stu-id="673c0-250">.</span></span>  <br/> |
|<span data-ttu-id="673c0-251">指定字詞或片語</span><span class="sxs-lookup"><span data-stu-id="673c0-251">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="673c0-252">新增下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="673c0-252">Add these file types:</span></span>  <br/> <span data-ttu-id="673c0-253">.docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="673c0-253">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/> |<span data-ttu-id="673c0-254">新增下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="673c0-254">Add these file types:</span></span>  <br/> <span data-ttu-id="673c0-255">ade、adp、ani、bas，bat，chm，cmd，com，cpl，crt，.hlp，ht，的 hta，inf，ins，jse，mdb，mdb，mde，mdz，msc，msi，msp，.msp，.pcd，reg，.scr，sct，wsc，wsf，wsh，vbe，pif</span><span class="sxs-lookup"><span data-stu-id="673c0-255">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> |
|<span data-ttu-id="673c0-256">請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="673c0-256">Do the following .</span></span> <span data-ttu-id="673c0-257">.</span><span class="sxs-lookup"><span data-stu-id="673c0-257">.</span></span> <span data-ttu-id="673c0-258">.</span><span class="sxs-lookup"><span data-stu-id="673c0-258">.</span></span>  <br/> |<span data-ttu-id="673c0-259">前置免責聲明</span><span class="sxs-lookup"><span data-stu-id="673c0-259">Prepend a disclaimer</span></span>  <br/> |<span data-ttu-id="673c0-260">封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-260">Block the message .</span></span> <span data-ttu-id="673c0-261">.</span><span class="sxs-lookup"><span data-stu-id="673c0-261">.</span></span> <span data-ttu-id="673c0-262">.</span><span class="sxs-lookup"><span data-stu-id="673c0-262">.</span></span> <span data-ttu-id="673c0-263">拒絕郵件並包含說明</span><span class="sxs-lookup"><span data-stu-id="673c0-263">reject the message and include an explanation</span></span>  <br/> |
|<span data-ttu-id="673c0-264">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="673c0-264">Provide message text</span></span>  <br/> |<span data-ttu-id="673c0-265">除非您想要的話，否則請勿開啟這些類型的檔，因為檔案可能包含惡意程式碼，而且知道寄件者不會保證安全性。</span><span class="sxs-lookup"><span data-stu-id="673c0-265">Do not open these types of files—unless you were expecting them—because the files may contain malicious code and knowing the sender isn't a guarantee of safety.</span></span>  <br/> ||
   
> [!TIP]
> <span data-ttu-id="673c0-266">您也可以將您想要封鎖的檔案新增至 [步驟 4](#4-raise-the-level-of-protection-against-malware-in-mail)中的反惡意代碼清單。</span><span class="sxs-lookup"><span data-stu-id="673c0-266">You can also add the files you want to block to the Anti-malware list in [step 4](#4-raise-the-level-of-protection-against-malware-in-mail).</span></span>

<span data-ttu-id="673c0-267">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="673c0-267">For more information, see:</span></span>

- [<span data-ttu-id="673c0-268">勒索軟體：如何降低風險</span><span class="sxs-lookup"><span data-stu-id="673c0-268">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="673c0-269">還原您的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="673c0-269">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a><span data-ttu-id="673c0-270">6：停止自動轉送電子郵件</span><span class="sxs-lookup"><span data-stu-id="673c0-270">6: Stop auto-forwarding for email</span></span>
<span data-ttu-id="673c0-271"><a name="forwarding"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-271"><a name="forwarding"> </a></span></span>

<span data-ttu-id="673c0-272">取得使用者信箱存取權的駭客可以將信箱設定為自動轉寄電子郵件，以 exfiltrate 郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-272">Hackers who gain access to a user's mailbox can exfiltrate mail by configuring the mailbox to automatically forward email.</span></span> <span data-ttu-id="673c0-273">即使沒有使用者的認知，也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="673c0-273">This can happen even without the user's awareness.</span></span> <span data-ttu-id="673c0-274">您可以設定郵件流程規則，避免發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="673c0-274">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="673c0-275">若要建立郵件傳輸規則：</span><span class="sxs-lookup"><span data-stu-id="673c0-275">To create a mail transport rule:</span></span>

1. <span data-ttu-id="673c0-276">移至 [Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)。</span><span class="sxs-lookup"><span data-stu-id="673c0-276">Go to the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104).</span></span>

2. <span data-ttu-id="673c0-277">在 [ **郵件流程** ] 類別中，選取 [ **規則**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-277">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="673c0-278">選取 [] **+** ，然後 **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="673c0-278">Select **+**, and then **Create a new rule**.</span></span>

4. <span data-ttu-id="673c0-279">在對話方塊底部選取 [ **更多選項** ]，以查看完整的選項組。</span><span class="sxs-lookup"><span data-stu-id="673c0-279">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="673c0-280">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-280">Apply the settings in the following table.</span></span> <span data-ttu-id="673c0-281">除非您想要變更這些設定，否則請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="673c0-281">Leave the rest of the settings at the default, unless you want to change these.</span></span>

6. <span data-ttu-id="673c0-282">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="673c0-282">Select **Save**.</span></span>

|<span data-ttu-id="673c0-283">設定</span><span class="sxs-lookup"><span data-stu-id="673c0-283">Setting</span></span>|<span data-ttu-id="673c0-284">拒絕自動轉寄電子郵件至外部網域</span><span class="sxs-lookup"><span data-stu-id="673c0-284">Reject Auto-Forward emails to external domains</span></span>|
|---|---|
|<span data-ttu-id="673c0-285">姓名</span><span class="sxs-lookup"><span data-stu-id="673c0-285">Name</span></span>|<span data-ttu-id="673c0-286">禁止將電子郵件自動轉寄轉送至外部網域</span><span class="sxs-lookup"><span data-stu-id="673c0-286">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="673c0-287">將此規則套用至 if .。。</span><span class="sxs-lookup"><span data-stu-id="673c0-287">Apply this rule if ...</span></span>|<span data-ttu-id="673c0-288">寄件者。</span><span class="sxs-lookup"><span data-stu-id="673c0-288">The sender .</span></span> <span data-ttu-id="673c0-289">.</span><span class="sxs-lookup"><span data-stu-id="673c0-289">.</span></span> <span data-ttu-id="673c0-290">.</span><span class="sxs-lookup"><span data-stu-id="673c0-290">.</span></span> <span data-ttu-id="673c0-291">為外部/內部。</span><span class="sxs-lookup"><span data-stu-id="673c0-291">is external/internal .</span></span> <span data-ttu-id="673c0-292">.</span><span class="sxs-lookup"><span data-stu-id="673c0-292">.</span></span> <span data-ttu-id="673c0-293">.</span><span class="sxs-lookup"><span data-stu-id="673c0-293">.</span></span> <span data-ttu-id="673c0-294">組織內部</span><span class="sxs-lookup"><span data-stu-id="673c0-294">Inside the organization</span></span>|
|<span data-ttu-id="673c0-295">新增條件</span><span class="sxs-lookup"><span data-stu-id="673c0-295">Add condition</span></span>|<span data-ttu-id="673c0-296">收件者。</span><span class="sxs-lookup"><span data-stu-id="673c0-296">The recipient .</span></span> <span data-ttu-id="673c0-297">.</span><span class="sxs-lookup"><span data-stu-id="673c0-297">.</span></span> <span data-ttu-id="673c0-298">.</span><span class="sxs-lookup"><span data-stu-id="673c0-298">.</span></span> <span data-ttu-id="673c0-299">為外部/內部。</span><span class="sxs-lookup"><span data-stu-id="673c0-299">is external/internal .</span></span> <span data-ttu-id="673c0-300">.</span><span class="sxs-lookup"><span data-stu-id="673c0-300">.</span></span> <span data-ttu-id="673c0-301">.</span><span class="sxs-lookup"><span data-stu-id="673c0-301">.</span></span> <span data-ttu-id="673c0-302">組織外部</span><span class="sxs-lookup"><span data-stu-id="673c0-302">Outside the organization</span></span>|
|<span data-ttu-id="673c0-303">新增條件</span><span class="sxs-lookup"><span data-stu-id="673c0-303">Add condition</span></span>|<span data-ttu-id="673c0-304">郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="673c0-304">The message properties .</span></span> <span data-ttu-id="673c0-305">.</span><span class="sxs-lookup"><span data-stu-id="673c0-305">.</span></span> <span data-ttu-id="673c0-306">.</span><span class="sxs-lookup"><span data-stu-id="673c0-306">.</span></span> <span data-ttu-id="673c0-307">包含郵件類型。</span><span class="sxs-lookup"><span data-stu-id="673c0-307">include the message type .</span></span> <span data-ttu-id="673c0-308">.</span><span class="sxs-lookup"><span data-stu-id="673c0-308">.</span></span> <span data-ttu-id="673c0-309">.</span><span class="sxs-lookup"><span data-stu-id="673c0-309">.</span></span> <span data-ttu-id="673c0-310">自動轉寄</span><span class="sxs-lookup"><span data-stu-id="673c0-310">Auto-forward</span></span>|
|<span data-ttu-id="673c0-311">請執行下列動作 .。。</span><span class="sxs-lookup"><span data-stu-id="673c0-311">Do the following ...</span></span>|<span data-ttu-id="673c0-312">封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-312">Block the message .</span></span> <span data-ttu-id="673c0-313">.</span><span class="sxs-lookup"><span data-stu-id="673c0-313">.</span></span> <span data-ttu-id="673c0-314">.</span><span class="sxs-lookup"><span data-stu-id="673c0-314">.</span></span> <span data-ttu-id="673c0-315">拒絕郵件並包含說明。</span><span class="sxs-lookup"><span data-stu-id="673c0-315">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="673c0-316">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="673c0-316">Provide message text</span></span>|<span data-ttu-id="673c0-317">由於安全性原因，禁止此組織外部的電子郵件的自動轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-317">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="7-use-office-message-encryption"></a><span data-ttu-id="673c0-318">7：使用 Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="673c0-318">7: Use Office Message Encryption</span></span>
<span data-ttu-id="673c0-319"><a name="encryption"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-319"><a name="encryption"> </a></span></span>

<span data-ttu-id="673c0-320">Office 郵件加密隨附于 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="673c0-320">Office Message Encryption is included with Microsoft 365.</span></span> <span data-ttu-id="673c0-321">已設定好。</span><span class="sxs-lookup"><span data-stu-id="673c0-321">It's already set up.</span></span> <span data-ttu-id="673c0-322">透過 Office 郵件加密，您的組織可以在組織內部和外部的人員之間傳送和接收加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-322">With Office Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="673c0-323">Office 365 郵件加密可與 Outlook.com、Yahoo！、Gmail 及其他電子郵件服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="673c0-323">Office 365 Message Encryption works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="673c0-324">電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。</span><span class="sxs-lookup"><span data-stu-id="673c0-324">Email message encryption helps ensure that only intended recipients can view message content.</span></span>

<span data-ttu-id="673c0-325">在傳送郵件時，Office 郵件加密會提供兩個保護選項：</span><span class="sxs-lookup"><span data-stu-id="673c0-325">Office Message Encryption provides two protection options when sending mail:</span></span>

- <span data-ttu-id="673c0-326">請勿轉寄</span><span class="sxs-lookup"><span data-stu-id="673c0-326">Do not forward</span></span>

- <span data-ttu-id="673c0-327">加密</span><span class="sxs-lookup"><span data-stu-id="673c0-327">Encrypt</span></span>

<span data-ttu-id="673c0-328">您的組織可能已設定其他選項，可將標籤套用至電子郵件，例如機密。</span><span class="sxs-lookup"><span data-stu-id="673c0-328">Your organization might have configured additional options that apply a label to email, such as Confidential.</span></span>

### <a name="to-send-protected-email"></a><span data-ttu-id="673c0-329">傳送受保護的電子郵件</span><span class="sxs-lookup"><span data-stu-id="673c0-329">To send protected email</span></span>

<span data-ttu-id="673c0-330">在 [適用于電腦的 Outlook] 中，選取 [電子郵件] 中的 **選項** ，然後選擇 [ **許可權**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-330">In Outlook for PC, select **Options** in the email, and then choose **Permissions**.</span></span>

![Outlook 中的電子郵件加密](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

<span data-ttu-id="673c0-332">在 Outlook.com 中，選取電子郵件中的 [ **保護** ]。</span><span class="sxs-lookup"><span data-stu-id="673c0-332">In Outlook.com, select **Protect** in the email.</span></span> <span data-ttu-id="673c0-333">預設保護不會 **轉寄**。</span><span class="sxs-lookup"><span data-stu-id="673c0-333">The default protection is **Do not forward**.</span></span> <span data-ttu-id="673c0-334">若要將此設為加密，請選取 [ **變更許可權** \> **加密**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-334">To change this to encrypt, select **Change Permissions** \> **Encrypt**.</span></span>

![Outlook.com 中的電子郵件加密](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a><span data-ttu-id="673c0-336">若要接收加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="673c0-336">To receive encrypted email</span></span>

<span data-ttu-id="673c0-337">如果收件者有 Outlook 2013 或 Outlook 2016 和 Microsoft 電子郵件帳戶，他們會在讀取窗格中看到有關該專案限制許可權的警示。</span><span class="sxs-lookup"><span data-stu-id="673c0-337">If the recipient has Outlook 2013 or Outlook 2016 and a Microsoft email account, they'll see an alert about the item's restricted permissions in the Reading pane.</span></span> <span data-ttu-id="673c0-338">開啟郵件後，收件者可以像任何其他方式一樣查看郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-338">After opening the message, the recipient can view the message just like any other.</span></span>

<span data-ttu-id="673c0-339">如果收件者使用另一個電子郵件用戶端或電子郵件帳戶，例如 Gmail 或 Yahoo，他們會看到可讓他們登入電子郵件訊息或要求單一時間密碼以在網頁瀏覽器中查看郵件的連結。</span><span class="sxs-lookup"><span data-stu-id="673c0-339">If the recipient is using another email client or email account, such as Gmail or Yahoo, they'll see a link that lets them either sign in to read the email message or request a one-time passcode to view the message in a web browser.</span></span> <span data-ttu-id="673c0-340">如果使用者未收到電子郵件，請他們檢查其 [垃圾郵件] 或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="673c0-340">If users aren't receiving the email, have them check their Spam or Junk folder.</span></span>

<span data-ttu-id="673c0-341">如需詳細資訊，請參閱 [在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)。</span><span class="sxs-lookup"><span data-stu-id="673c0-341">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="8-protect-your-email-from-phishing-attacks"></a><span data-ttu-id="673c0-342">8. 保護您的電子郵件免受網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="673c0-342">8. Protect your email from phishing attacks</span></span>
<span data-ttu-id="673c0-343"><a name="phishing"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-343"><a name="phishing"> </a></span></span>

<span data-ttu-id="673c0-344">如果您已為 Microsoft 365 環境設定一或多個自訂網域，您可以設定目標的反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-344">If you've configured one or more custom domains for your Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="673c0-345">ATP 反網路釣魚保護，部分的 Office 365 高級威脅防護，可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="673c0-345">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="673c0-346">若尚未設定自訂網域，您不需要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="673c0-346">If you haven't configured a custom domain, you do not need to do this.</span></span>

<span data-ttu-id="673c0-347">建議您建立原則來保護您最重要的使用者和自訂網域，以開始使用這項保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-347">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

![建立 ATP 反網路釣魚原則](../../media/security-and-compliance-center.png)

<span data-ttu-id="673c0-349">若要建立 ATP 反網路釣魚原則，請觀看 [簡短的訓練影片](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="673c0-349">To create an ATP anti-phishing policy, view a [short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="673c0-350">移至<https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="673c0-350">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="673c0-351">在 [安全性 & 規範中心] 的左功能窗格中，選取 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-351">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, select **Policy**.</span></span>

3. <span data-ttu-id="673c0-352">在 [原則] 頁面上，選取 [ **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-352">On the Policy page, select **ATP anti-phishing**.</span></span>

4. <span data-ttu-id="673c0-353">在 [反網路釣魚] 頁面上，選取 [ **+ 建立**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-353">On the Anti-phishing page, select **+ Create**.</span></span> <span data-ttu-id="673c0-354">嚮導會啟動以逐步逐步定義您的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="673c0-354">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="673c0-355">請依照下表中的建議，指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-355">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="673c0-356">如需詳細資訊，請參閱 [瞭解 ATP 反網路釣魚原則選項](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) 。</span><span class="sxs-lookup"><span data-stu-id="673c0-356">See [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) for more details.</span></span>

6. <span data-ttu-id="673c0-357">檢查您的設定之後，請選取 [ **建立這個原則** ] 或 [ **儲存**] （視需要）。</span><span class="sxs-lookup"><span data-stu-id="673c0-357">After you have reviewed your settings, select **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="673c0-358">設定或選項</span><span class="sxs-lookup"><span data-stu-id="673c0-358">Setting or option</span></span>|<span data-ttu-id="673c0-359">建議的設定</span><span class="sxs-lookup"><span data-stu-id="673c0-359">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="673c0-360">姓名</span><span class="sxs-lookup"><span data-stu-id="673c0-360">Name</span></span>|<span data-ttu-id="673c0-361">網域和最有價值的活動人員</span><span class="sxs-lookup"><span data-stu-id="673c0-361">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="673c0-362">說明</span><span class="sxs-lookup"><span data-stu-id="673c0-362">Description</span></span>|<span data-ttu-id="673c0-363">確定最重要的人員和我們的網域未進行類比。</span><span class="sxs-lookup"><span data-stu-id="673c0-363">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="673c0-364">新增要保護的使用者</span><span class="sxs-lookup"><span data-stu-id="673c0-364">Add users to protect</span></span>|<span data-ttu-id="673c0-365">選取 **[+ 新增條件]，收件者是**。</span><span class="sxs-lookup"><span data-stu-id="673c0-365">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="673c0-366">輸入使用者名稱，或輸入候選人、活動管理員及其他重要員工成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="673c0-366">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="673c0-367">您最多可以新增20個要從類比中保護的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="673c0-367">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="673c0-368">新增要保護的網域</span><span class="sxs-lookup"><span data-stu-id="673c0-368">Add domains to protect</span></span>|<span data-ttu-id="673c0-369">選取 **[+ 新增條件]，收件者網域是**。</span><span class="sxs-lookup"><span data-stu-id="673c0-369">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="673c0-370">輸入您的 Microsoft 365 訂閱相關聯的自訂網域（如果您已定義的話）。</span><span class="sxs-lookup"><span data-stu-id="673c0-370">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="673c0-371">您可以輸入一個以上的網域。</span><span class="sxs-lookup"><span data-stu-id="673c0-371">You can enter more than one domain.</span></span>|
|<span data-ttu-id="673c0-372">選擇動作</span><span class="sxs-lookup"><span data-stu-id="673c0-372">Choose actions</span></span>|<span data-ttu-id="673c0-373">如果模仿的使用者傳送電子郵件：選取 [重新 **導向郵件至另一個電子郵件地址**]，然後輸入安全性管理員的電子郵件地址。例如，securityadmin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="673c0-373">If email is sent by an impersonated user: select **Redirect message to another email address**, and then type the email address of the security administrator; for example, securityadmin@contoso.com.</span></span> <br/> <span data-ttu-id="673c0-374">如果模仿的網域傳送電子郵件： [選取 **隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-374">If email is sent by an impersonated domain: select **Quarantine message**.</span></span>|
|<span data-ttu-id="673c0-375">信箱情報</span><span class="sxs-lookup"><span data-stu-id="673c0-375">Mailbox intelligence</span></span>|<span data-ttu-id="673c0-376">當您建立新的反網路釣魚原則時，系統會預設選取信箱情報。</span><span class="sxs-lookup"><span data-stu-id="673c0-376">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="673c0-377">請將此設定保留為 **[開啟]**，以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="673c0-377">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="673c0-378">新增受信任的寄件者與網域</span><span class="sxs-lookup"><span data-stu-id="673c0-378">Add trusted senders and domains</span></span>|<span data-ttu-id="673c0-379">在此範例中，請不要定義任何覆寫。</span><span class="sxs-lookup"><span data-stu-id="673c0-379">For this example, don't define any overrides.</span></span>|
|<span data-ttu-id="673c0-380">套用對象</span><span class="sxs-lookup"><span data-stu-id="673c0-380">Applied to</span></span>|<span data-ttu-id="673c0-381">請選取 **[收件者的網域是]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-381">Select **The recipient domain is**.</span></span> <span data-ttu-id="673c0-382">在 **[任一項]** 底下選取 **[選擇]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-382">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="673c0-383">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-383">Select **+ Add**.</span></span> <span data-ttu-id="673c0-384">選取功能變數名稱（例如，contoso.com，在清單中）旁的核取方塊，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-384">Select the check box next to the name of the domain, for example, contoso.com, in the list, and then select **Add**.</span></span> <span data-ttu-id="673c0-385">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="673c0-385">Select **Done**.</span></span>|
|

<span data-ttu-id="673c0-386">如需詳細資訊，請參閱 [設定 Office 365 ATP 反網路釣魚原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="673c0-386">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).</span></span>

## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="673c0-387">9：防禦具有 ATP 安全附件的惡意附件和檔案</span><span class="sxs-lookup"><span data-stu-id="673c0-387">9: Protect against malicious attachments and files with ATP Safe Attachments</span></span>
<span data-ttu-id="673c0-388"><a name="atp"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-388"><a name="atp"> </a></span></span>

<span data-ttu-id="673c0-389">人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。</span><span class="sxs-lookup"><span data-stu-id="673c0-389">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="673c0-390">只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。</span><span class="sxs-lookup"><span data-stu-id="673c0-390">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="673c0-391">Office 365 的高級威脅防護包括 ATP 安全附件保護，但預設不會開啟此保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-391">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="673c0-392">建議您建立新的規則，以開始使用這種保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-392">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="673c0-393">這項保護會延伸至 SharePoint、OneDrive 和 Microsoft 小組中的檔案。</span><span class="sxs-lookup"><span data-stu-id="673c0-393">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="673c0-394">若要建立 ATP 安全附件原則，請觀看 [簡短的訓練影片](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="673c0-394">To create an ATP safe attachment policy, view a [short training video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="673c0-395">移至 <https://protection.office.com> 並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="673c0-395">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="673c0-396">在 [安全性 & 規範中心] 的左功能窗格中，選取 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-396">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, select **Policy**.</span></span>

3. <span data-ttu-id="673c0-397">在 [原則] 頁面上，選取 [ **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-397">On the Policy page, select **ATP safe attachments**.</span></span>

4. <span data-ttu-id="673c0-398">在 [安全附件] 頁面上，選取 [ **開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP** ] 核取方塊，廣泛套用此保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-398">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="673c0-399">選取 **+** 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="673c0-399">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="673c0-400">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-400">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="673c0-401">檢查您的設定之後，請選取 [ **建立這個原則** ] 或 [ **儲存**] （視需要）。</span><span class="sxs-lookup"><span data-stu-id="673c0-401">After you have reviewed your settings, select **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="673c0-402">設定或選項</span><span class="sxs-lookup"><span data-stu-id="673c0-402">Setting or option</span></span>|<span data-ttu-id="673c0-403">建議的設定</span><span class="sxs-lookup"><span data-stu-id="673c0-403">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="673c0-404">姓名</span><span class="sxs-lookup"><span data-stu-id="673c0-404">Name</span></span>|<span data-ttu-id="673c0-405">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="673c0-405">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="673c0-406">說明</span><span class="sxs-lookup"><span data-stu-id="673c0-406">Description</span></span>|<span data-ttu-id="673c0-407">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="673c0-407">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="673c0-408">儲存附件未知的惡意程式碼回應</span><span class="sxs-lookup"><span data-stu-id="673c0-408">Save attachments unknown malware response</span></span>|<span data-ttu-id="673c0-409">Select **Block-封鎖目前和未來的電子郵件和附件偵測到的惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="673c0-409">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="673c0-410">在偵測時重新導向附件</span><span class="sxs-lookup"><span data-stu-id="673c0-410">Redirect attachment on detection</span></span>|<span data-ttu-id="673c0-411">啟用重新導向 (選取此方塊) </span><span class="sxs-lookup"><span data-stu-id="673c0-411">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="673c0-412">輸入用於隔離的系統管理員帳戶或信箱設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-412">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="673c0-413">若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。 (選取此方塊) 。</span><span class="sxs-lookup"><span data-stu-id="673c0-413">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="673c0-414">套用對象</span><span class="sxs-lookup"><span data-stu-id="673c0-414">Applied to</span></span>|<span data-ttu-id="673c0-415">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="673c0-415">The recipient domain is .</span></span> <span data-ttu-id="673c0-416">.</span><span class="sxs-lookup"><span data-stu-id="673c0-416">.</span></span> <span data-ttu-id="673c0-417">.</span><span class="sxs-lookup"><span data-stu-id="673c0-417">.</span></span> <span data-ttu-id="673c0-418">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="673c0-418">select your domain.</span></span>|
|

<span data-ttu-id="673c0-419">如需詳細資訊，請參閱 [設定 Office 365 ATP 反網路釣魚原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="673c0-419">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).</span></span>

## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="673c0-420">10：防禦具有 ATP 安全連結的網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="673c0-420">10: Protect against phishing attacks with ATP Safe Links</span></span>
<span data-ttu-id="673c0-421"><a name="phishingatp"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-421"><a name="phishingatp"> </a></span></span>

<span data-ttu-id="673c0-422">駭客有時候會在電子郵件或其他檔案的連結中隱藏惡意網站。</span><span class="sxs-lookup"><span data-stu-id="673c0-422">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="673c0-423">Office 365 ATP 安全連結 (ATP 安全連結) （Office 365 的部分高級威脅防護）可在電子郵件訊息和 Office 檔中，透過網頁位址的驗證， (URLs) 來協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="673c0-423">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="673c0-424">保護是透過 ATP 安全連結原則定義。</span><span class="sxs-lookup"><span data-stu-id="673c0-424">Protection is defined through ATP Safe Links policies.</span></span>

<span data-ttu-id="673c0-425">我們建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="673c0-425">We recommend that you do the following:</span></span>

- <span data-ttu-id="673c0-426">修改預設原則以提升保護。</span><span class="sxs-lookup"><span data-stu-id="673c0-426">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="673c0-427">新增針對您網域中所有收件者的新原則。</span><span class="sxs-lookup"><span data-stu-id="673c0-427">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="673c0-428">若要取得 ATP 安全連結，請觀看 [簡短的訓練影片](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="673c0-428">To get to ATP Safe Links, view a [short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="673c0-429">移至 <https://protection.office.com> 並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="673c0-429">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="673c0-430">在 [安全性 & 規範中心] 的左功能窗格中，選取 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-430">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, select **Policy**.</span></span>

3. <span data-ttu-id="673c0-431">在 [原則] 頁面上，選取 [ **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-431">On the Policy page, select **ATP Safe Links**.</span></span>

<span data-ttu-id="673c0-432">若要修改預設原則：</span><span class="sxs-lookup"><span data-stu-id="673c0-432">To modify the default policy:</span></span>

1. <span data-ttu-id="673c0-433">在 [安全連結] 頁面的 [ **適用于整個組織的原則**] 底下，按兩下 [ **預設** 原則]。</span><span class="sxs-lookup"><span data-stu-id="673c0-433">On the Safe links page, under **Policies that apply to the entire organization**, double-click the **Default** policy.</span></span>

2. <span data-ttu-id="673c0-434">在 [ **適用于 Office 365 的內容設定**] 底下，輸入要封鎖的 URL，例如 _example.com_，然後選取 **+** 。</span><span class="sxs-lookup"><span data-stu-id="673c0-434">Under **Settings that apply to content across Office 365**, enter a URL to be blocked, such as _example.com_, and select **+**.</span></span>

3. <span data-ttu-id="673c0-435">在 [ **電子郵件除外，套用至內容**] 底下，選取 [ **Office 365 應用程式**]， **當使用者按一下 [安全連結] 時請勿追蹤**，而且不要 **讓使用者按一下 [指向原始 URL 的安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="673c0-435">Under **Settings that apply to content except email**, select **Office 365 applications**, **Do not track when users click safe links**, and **Do not let users click through safe links to original URL**.</span></span>

4. <span data-ttu-id="673c0-436">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="673c0-436">Select **Save**.</span></span>

<span data-ttu-id="673c0-437">若要建立新的原則針對您網域中的所有收件者：</span><span class="sxs-lookup"><span data-stu-id="673c0-437">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="673c0-438">在 [安全連結] 頁面上，按一下 [套用 **至特定**收件者的原則] 底下的 [ **+** 建立新原則]。</span><span class="sxs-lookup"><span data-stu-id="673c0-438">On the Safe links page, under **Policies that apply to specific recipients**, select **+** to create a new policy.</span></span>

2. <span data-ttu-id="673c0-439">套用下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="673c0-439">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="673c0-440">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="673c0-440">Select **Save**.</span></span>

|<span data-ttu-id="673c0-441">設定或選項</span><span class="sxs-lookup"><span data-stu-id="673c0-441">Setting or option</span></span>|<span data-ttu-id="673c0-442">建議的設定</span><span class="sxs-lookup"><span data-stu-id="673c0-442">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="673c0-443">姓名</span><span class="sxs-lookup"><span data-stu-id="673c0-443">Name</span></span>|<span data-ttu-id="673c0-444">網域中所有收件者的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="673c0-444">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="673c0-445">選取郵件中未知可能惡意 URLs 的動作</span><span class="sxs-lookup"><span data-stu-id="673c0-445">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="673c0-446">選取 **[URLs 會在使用者按一下連結時，重新寫入並檢查已知惡意連結的清單**。</span><span class="sxs-lookup"><span data-stu-id="673c0-446">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="673c0-447">針對可疑的連結和指向檔案的連結套用即時 URL 掃描</span><span class="sxs-lookup"><span data-stu-id="673c0-447">Apply real-time URL scanning for suspicious links and links that point to files</span></span>|<span data-ttu-id="673c0-448">選取此方塊。</span><span class="sxs-lookup"><span data-stu-id="673c0-448">Select this box.</span></span>|
|<span data-ttu-id="673c0-449">套用對象</span><span class="sxs-lookup"><span data-stu-id="673c0-449">Applied to</span></span>|<span data-ttu-id="673c0-450">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="673c0-450">The recipient domain is .</span></span> <span data-ttu-id="673c0-451">.</span><span class="sxs-lookup"><span data-stu-id="673c0-451">.</span></span> <span data-ttu-id="673c0-452">.</span><span class="sxs-lookup"><span data-stu-id="673c0-452">.</span></span> <span data-ttu-id="673c0-453">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="673c0-453">select your domain.</span></span>|
|

<span data-ttu-id="673c0-454">如需詳細資訊，請參閱 [Office 365 ATP 中的安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="673c0-454">For more information, see [Safe Links in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).</span></span>
