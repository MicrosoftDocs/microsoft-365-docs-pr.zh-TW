---
title: 步驟 4：設定安全的使用者驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定使用者帳戶的多重要素驗證。
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981844"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="0749c-103">步驟 4：設定安全的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="0749c-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="0749c-104">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="0749c-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="0749c-105">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0749c-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0749c-p101">在本步驟中，您將設定多重要素驗證 (MFA)，以將第二層安全性新增至使用者登入和交易。在使用者已正確地輸入密碼後，MFA 需要額外的驗證方法。少了 MFA，密碼是唯一的驗證方式。密碼的問題是攻擊者容易猜測許多密碼或在不知情的情況下與未受信任的對象共用密碼。</span><span class="sxs-lookup"><span data-stu-id="0749c-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="0749c-110">透過 MFA，第二層安全性可以是：</span><span class="sxs-lookup"><span data-stu-id="0749c-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="0749c-111">不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="0749c-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="0749c-112">生物識別屬性 (例如指紋)。</span><span class="sxs-lookup"><span data-stu-id="0749c-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="0749c-113">您將啟用 MFA 並使用[條件式存取原則](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)來設定次要驗證方法，這會允許您使用 Azure Active Directory (Azure AD) 群組來將 MFA 向指定的一組使用者 (例如試驗使用者、地理位置或部門) 推出。</span><span class="sxs-lookup"><span data-stu-id="0749c-113">You'll enable MFA and configure the secondary authentication method with [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="0749c-114">請務必讓使用者知道即將啟用 MFA，使得他們了解需求 (例如強制使用智慧型手機登入) 並能順利登入。</span><span class="sxs-lookup"><span data-stu-id="0749c-114">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="0749c-115">如需詳細資訊，請參閱[規劃多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="0749c-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="0749c-p103">在部分應用程式中 (例如 Microsoft Office 2010 或更舊版本和 Apple Mail) 您無法使用 MFA。若要使用這些應用程式，您將需要使用「應用程式密碼」取代您的傳統密碼。應用程式密碼允許應用程式略過 MFA 並繼續執行。若需應用程式密碼的更多資訊，請參閱[建立 Office 365 的應用程式密碼](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="0749c-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="0749c-121">測試實驗室指南：多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="0749c-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="0749c-122">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="0749c-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="0749c-123">防止不正確的密碼</span><span class="sxs-lookup"><span data-stu-id="0749c-123">Prevent bad passwords</span></span>

<span data-ttu-id="0749c-124">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0749c-124">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0749c-125">若要防止使用者建立容易猜測的密碼，請使用 Azure AD 密碼保護，此功能會同時使用全域禁止密碼清單和您指定的選用自訂禁止密碼清單。</span><span class="sxs-lookup"><span data-stu-id="0749c-125">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="0749c-126">例如，您可以指定組織的特定字詞，例如：</span><span class="sxs-lookup"><span data-stu-id="0749c-126">For example, you can specify terms that are specific to your organization, such as"</span></span>

- <span data-ttu-id="0749c-127">品牌名稱</span><span class="sxs-lookup"><span data-stu-id="0749c-127">Brand names</span></span>
- <span data-ttu-id="0749c-128">產品名稱</span><span class="sxs-lookup"><span data-stu-id="0749c-128">Product names</span></span>
- <span data-ttu-id="0749c-129">位置 (例如公司總部)</span><span class="sxs-lookup"><span data-stu-id="0749c-129">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="0749c-130">公司的特定內部條款</span><span class="sxs-lookup"><span data-stu-id="0749c-130">Company-specific internal terms</span></span>
- <span data-ttu-id="0749c-131">具有特定公司意義的縮寫。</span><span class="sxs-lookup"><span data-stu-id="0749c-131">Abbreviations that have specific company meaning.</span></span>

<span data-ttu-id="0749c-132">您可以在[雲端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[內部部署 Active Directory 網域服務 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 中禁止使用不良密碼。</span><span class="sxs-lookup"><span data-stu-id="0749c-132">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="0749c-133">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-password-prot)。</span><span class="sxs-lookup"><span data-stu-id="0749c-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="0749c-134">防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="0749c-134">Protect against credential compromise</span></span>

<span data-ttu-id="0749c-135">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0749c-135">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0749c-136">在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。</span><span class="sxs-lookup"><span data-stu-id="0749c-136">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="0749c-137">Azure AD Identity Protection 提供許多方法，協助防止攻擊者透過您的帳戶和群組而入侵，以及協助保護您最寶貴的資料。</span><span class="sxs-lookup"><span data-stu-id="0749c-137">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="0749c-138">使用 Azure AD Identity Protection，您可以：</span><span class="sxs-lookup"><span data-stu-id="0749c-138">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="0749c-139">判斷並處理組織身分識別中潛在的弱點</span><span class="sxs-lookup"><span data-stu-id="0749c-139">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="0749c-140">Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。</span><span class="sxs-lookup"><span data-stu-id="0749c-140">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="0749c-141">Azure AD Identity Protection 可使用此資料來產生報告和警示，協助您評估問題及採取行動。</span><span class="sxs-lookup"><span data-stu-id="0749c-141">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="0749c-142">偵測與組織身分識別相關的可疑活動，並自動進行回應處理</span><span class="sxs-lookup"><span data-stu-id="0749c-142">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="0749c-143">您可以設定以風險為基礎的原則，當達到指定風險層級時自動回應偵測到的問題。</span><span class="sxs-lookup"><span data-stu-id="0749c-143">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="0749c-144">除了由 Azure AD 和 Microsoft Intune 提供的其他條件式存取控制項之外，這些原則還可以自動封鎖存取權，或採取更正動作，包括密碼重設以及對後續登入要求多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="0749c-144">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="0749c-145">調查可疑事件，並使用系統管理動作加以解決</span><span class="sxs-lookup"><span data-stu-id="0749c-145">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="0749c-p108">您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。</span><span class="sxs-lookup"><span data-stu-id="0749c-p108">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="0749c-148">請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="0749c-148">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="0749c-149">請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="0749c-149">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="0749c-150">此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：</span><span class="sxs-lookup"><span data-stu-id="0749c-150">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="0749c-151">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="0749c-151">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="0749c-152">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="0749c-152">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="0749c-153">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="0749c-153">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="0749c-155">測試實驗室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="0749c-155">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="0749c-156">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="0749c-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="0749c-157">監控租用戶和登入活動</span><span class="sxs-lookup"><span data-stu-id="0749c-157">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="0749c-158">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0749c-158">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0749c-p109">在此步驟中，您將會使用 Azure AD 報告檢視稽核記錄和登入活動。兩種類型的報告皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="0749c-p109">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="0749c-p110">**稽核記錄活動報告**會報告 Azure AD 租用戶中執行的每項工作歷程記錄。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="0749c-p110">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="0749c-163">哪個人員已將某人新增至系統管理群組？</span><span class="sxs-lookup"><span data-stu-id="0749c-163">Who added someone to an admin group?</span></span>
- <span data-ttu-id="0749c-164">哪個使用者正在登入特定的應用程式？</span><span class="sxs-lookup"><span data-stu-id="0749c-164">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="0749c-165">密碼重設的發生次數？</span><span class="sxs-lookup"><span data-stu-id="0749c-165">How many password resets are happening?</span></span>

<span data-ttu-id="0749c-p111">**登入活動報告**會報告哪個人員執行稽核記錄報告所報告的工作。這份報告會回答如以下的問題：</span><span class="sxs-lookup"><span data-stu-id="0749c-p111">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="0749c-168">針對調查中的特定使用者，他們的登入模式是什麼？</span><span class="sxs-lookup"><span data-stu-id="0749c-168">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="0749c-169">一天、週或月的登入活動量為何？</span><span class="sxs-lookup"><span data-stu-id="0749c-169">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="0749c-170">這些登入嘗試不成功的次數有多少，且是針對哪一個帳戶？</span><span class="sxs-lookup"><span data-stu-id="0749c-170">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="0749c-171">如需報告以及如何存取他們的詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="0749c-171">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="0749c-172">在此步驟的結果中，您將了解這些報告以及如何使用這些報告來深入了解用於規劃與安全性目的之 Azure AD 事件與活動。</span><span class="sxs-lookup"><span data-stu-id="0749c-172">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="0749c-173">下一步</span><span class="sxs-lookup"><span data-stu-id="0749c-173">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="0749c-174">簡化使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="0749c-174">Simplify access for users</span></span>](identity-password-reset.md) |

