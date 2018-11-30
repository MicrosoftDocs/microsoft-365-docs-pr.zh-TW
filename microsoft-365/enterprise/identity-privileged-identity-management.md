---
title: 步驟 3：設定隨選全域管理員
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定 Azure AD Privileged Identity Management。
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866310"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="3e7d9-103">步驟 3：設定隨選全域管理員</span><span class="sxs-lookup"><span data-stu-id="3e7d9-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="3e7d9-104">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="3e7d9-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="3e7d9-p101">在此步驟中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少全域系統管理員帳戶容易受到惡意使用者攻擊的時間。PIM 可在需要時提供隨需、即時的全域系統管理員角色指派。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="3e7d9-p102">全域系統管理員帳戶不再是永久管理員，而是變為合格的管理員。全域系統管理員角色在有人需要它之前為無作用狀態。您需要完成啟動程序，在一段特定時間內將全域系統管理員角色新增到全域系統管理員帳戶。時間到期後，PIM 會從全域系統管理員帳戶中移除此全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="3e7d9-p103">Microsoft 365 企業版 E5 隨附 Azure Active Directory Premium P2，而 P2 便有 PIM 功能。或者，您可以為您的全域系統管理員帳戶購買單獨的 Azure Active Directory Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="3e7d9-113">若要為 Azure AD 租用戶和全域系統管理員帳戶啟用 Azure PIM，請參閱[什麼是 Azure AD Privileged Identity Management？](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="3e7d9-114">若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="3e7d9-115">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="3e7d9-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3e7d9-116">下一步</span><span class="sxs-lookup"><span data-stu-id="3e7d9-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="3e7d9-117">簡化密碼重設</span><span class="sxs-lookup"><span data-stu-id="3e7d9-117">Simplify password resets</span></span>](identity-password-reset.md) |

