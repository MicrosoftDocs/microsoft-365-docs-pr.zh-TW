---
title: 步驟 5：設定多重要素驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定使用者帳戶的多重要素驗證。
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866603"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="5f7b6-103">步驟 5：設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="5f7b6-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="5f7b6-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5f7b6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5f7b6-p101">在本步驟中，您將設定多重要素驗證 (MFA)，以將第二層安全性新增至使用者登入和交易。在使用者已正確地輸入密碼後，MFA 需要額外的驗證方法。少了 MFA，密碼是唯一的驗證方式。密碼的問題是攻擊者容易猜測許多密碼或在不知情的情況下與未受信任的對象共用密碼。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="5f7b6-109">透過 MFA，第二層安全性可以是：</span><span class="sxs-lookup"><span data-stu-id="5f7b6-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="5f7b6-110">不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="5f7b6-111">生物識別屬性 (例如指紋)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="5f7b6-p102">您將啟用 MFA，並以每個使用者帳戶為基礎設定次要驗證方法。請務必讓使用者知道 MFA 已啟用，他們就了解要求 (例如強制使用智慧型手機登入) 並能順利登入。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="5f7b6-114">如需更多資訊，請參閱 [Office 365 部署的多重要素驗證方案](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="5f7b6-115">若要設定多重要素驗證，[設定 Office 365 使用者的多重要素驗證](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="5f7b6-p103">您可以要求含條件式存取原則的 MFA。例如，您可以設定在決定驗證為中或高風險時需要 MFA 的原則。如需詳細資訊，請參閱[常見的身分識別與裝置存取原則](identity-access-policies.md#require-mfa-based-on-sign-in-risk)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="5f7b6-p104">在部分應用程式中 (例如 Microsoft Office 2010 或更舊版本和 Apple Mail) 您無法使用 MFA。若要使用這些應用程式，您將需要使用「應用程式密碼」取代您的傳統密碼。應用程式密碼允許應用程式略過 MFA 並繼續執行。若需應用程式密碼的更多資訊，請參閱[建立 Office 365 的應用程式密碼](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5f7b6-124">測試實驗室指南：多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="5f7b6-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5f7b6-125">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="5f7b6-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5f7b6-126">下一步</span><span class="sxs-lookup"><span data-stu-id="5f7b6-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="5f7b6-127">防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="5f7b6-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

