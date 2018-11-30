---
title: 步驟 10：簡化使用者登入
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定 Azure AD 無縫單一登入 (無縫 SSO)。
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866662"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="d808a-103">步驟 10：簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="d808a-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="d808a-104">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="d808a-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d808a-p101">在本步驟中，您將會設定 Azure Active Directory 無縫單一登入 (Azure AD 無縫 SSO)，讓使用者可登入使用 Azure AD 使用者帳戶的服務，而不需要輸入密碼，以及在許多情況下不需輸入使用者名稱。這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。</span><span class="sxs-lookup"><span data-stu-id="d808a-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="d808a-107">您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。</span><span class="sxs-lookup"><span data-stu-id="d808a-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="d808a-108">請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="d808a-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d808a-110">測試實驗室指南：Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="d808a-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d808a-111">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-sso)。</span><span class="sxs-lookup"><span data-stu-id="d808a-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d808a-112">下一步</span><span class="sxs-lookup"><span data-stu-id="d808a-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="d808a-113">自訂 Office 365 登入頁面</span><span class="sxs-lookup"><span data-stu-id="d808a-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

