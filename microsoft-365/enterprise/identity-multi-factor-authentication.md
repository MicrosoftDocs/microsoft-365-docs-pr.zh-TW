---
title: 步驟 4：設定安全的使用者驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定使用者帳戶的多重要素驗證。
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072083"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="85d0c-103">步驟 4：設定安全的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="85d0c-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="85d0c-104">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="85d0c-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="85d0c-105">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="85d0c-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="85d0c-p101">在本步驟中，您將設定多重要素驗證 (MFA)，以將第二層安全性新增至使用者登入和交易。在使用者已正確地輸入密碼後，MFA 需要額外的驗證方法。少了 MFA，密碼是唯一的驗證方式。密碼的問題是攻擊者容易猜測許多密碼或在不知情的情況下與未受信任的對象共用密碼。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="85d0c-110">透過 MFA，第二層安全性可以是：</span><span class="sxs-lookup"><span data-stu-id="85d0c-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="85d0c-111">不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="85d0c-112">生物識別屬性 (例如指紋)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="85d0c-p102">您將啟用 MFA，並以每個使用者帳戶為基礎設定次要驗證方法。請務必讓使用者知道 MFA 已啟用，他們就了解要求 (例如強制使用智慧型手機登入) 並能順利登入。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="85d0c-115">如需詳細資訊，請參閱[規劃多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="85d0c-p103">在部分應用程式中 (例如 Microsoft Office 2010 或更舊版本和 Apple Mail) 您無法使用 MFA。若要使用這些應用程式，您將需要使用「應用程式密碼」取代您的傳統密碼。應用程式密碼允許應用程式略過 MFA 並繼續執行。若需應用程式密碼的更多資訊，請參閱[建立 Office 365 的應用程式密碼](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="85d0c-121">測試實驗室指南：多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="85d0c-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="85d0c-122">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="85d0c-123">防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="85d0c-123">Protect against credential compromise</span></span>

<span data-ttu-id="85d0c-124">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="85d0c-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="85d0c-125">在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。</span><span class="sxs-lookup"><span data-stu-id="85d0c-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="85d0c-126">Azure AD Identity Protection 提供許多方法，協助防止攻擊者透過您的帳戶和群組而入侵，以及協助保護您最寶貴的資料。</span><span class="sxs-lookup"><span data-stu-id="85d0c-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="85d0c-127">使用 Azure AD Identity Protection，您可以：</span><span class="sxs-lookup"><span data-stu-id="85d0c-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="85d0c-128">判斷並處理組織身分識別中潛在的弱點</span><span class="sxs-lookup"><span data-stu-id="85d0c-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="85d0c-p105">Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。Identity Protection 可使用此資料產生報告和警訊，協助您評估問題及採取行動。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="85d0c-131">偵測與組織身分識別相關的可疑活動，並自動進行回應處理</span><span class="sxs-lookup"><span data-stu-id="85d0c-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="85d0c-p106">您可以設定風險原則，在達到指定的風險層級時，會自動回應偵測到的問題。由 Azure Active Directory 和 Enterprise Mobility + Security (EMS) 提供的這些原則，以及其他條件式存取控制，可自動封鎖存取或採取修正動作，包括密碼重設和要求後續登入的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="85d0c-134">調查可疑事件，並使用系統管理動作加以解決</span><span class="sxs-lookup"><span data-stu-id="85d0c-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="85d0c-p107">您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="85d0c-137">請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="85d0c-138">請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="85d0c-139">此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：</span><span class="sxs-lookup"><span data-stu-id="85d0c-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="85d0c-140">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="85d0c-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="85d0c-141">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="85d0c-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="85d0c-142">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="85d0c-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="85d0c-144">測試實驗室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="85d0c-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="85d0c-145">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="85d0c-146">監控租用戶和登入活動</span><span class="sxs-lookup"><span data-stu-id="85d0c-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="85d0c-147">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="85d0c-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="85d0c-p108">在此步驟中，您將會使用 Azure AD 報告檢視稽核記錄和登入活動。兩種類型的報告皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="85d0c-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="85d0c-p109">**稽核記錄活動報告**會報告 Azure AD 租用戶中執行的每項工作歷程記錄。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="85d0c-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="85d0c-152">哪個人員已將某人新增至系統管理群組？</span><span class="sxs-lookup"><span data-stu-id="85d0c-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="85d0c-153">哪個使用者正在登入特定的應用程式？</span><span class="sxs-lookup"><span data-stu-id="85d0c-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="85d0c-154">密碼重設的發生次數？</span><span class="sxs-lookup"><span data-stu-id="85d0c-154">How many password resets are happening?</span></span>

<span data-ttu-id="85d0c-p110">**登入活動報告**會報告哪個人員執行稽核記錄報告所報告的工作。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="85d0c-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="85d0c-157">針對調查中的特定使用者，他們的登入模式是什麼？</span><span class="sxs-lookup"><span data-stu-id="85d0c-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="85d0c-158">一天、週或月的登入活動量為何？</span><span class="sxs-lookup"><span data-stu-id="85d0c-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="85d0c-159">這些登入嘗試不成功的次數有多少，且是針對哪一個帳戶？</span><span class="sxs-lookup"><span data-stu-id="85d0c-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="85d0c-160">如需報告以及如何存取他們的詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="85d0c-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="85d0c-161">在此步驟的結果中，您將了解這些報告以及如何使用這些報告來深入了解用於規劃與安全性目的之 Azure AD 事件與活動。</span><span class="sxs-lookup"><span data-stu-id="85d0c-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="85d0c-162">下一步</span><span class="sxs-lookup"><span data-stu-id="85d0c-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="85d0c-163">簡化使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="85d0c-163">Simplify access for users</span></span>](identity-password-reset.md) |

