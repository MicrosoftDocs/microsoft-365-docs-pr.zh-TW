---
title: 步驟 12：設定自動授權
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
description: 了解並設定 Azure AD 群組之以群組為基礎的授權。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866101"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="a4087-103">步驟 12：設定自動授權</span><span class="sxs-lookup"><span data-stu-id="a4087-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="a4087-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a4087-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="a4087-p101">在此步驟中，您會在 Azure AD 中設定安全性群組，以自動將授權從一組訂閱中指派給該群組的所有成員。這稱為*以群組為基礎的授權*。若使用者帳戶已新增至該群組或從其中移除，該群組訂閱的授權將會自動從使用者帳戶指派或移除。</span><span class="sxs-lookup"><span data-stu-id="a4087-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="a4087-108">針對 Microsoft 365 企業版，您將會設定 Azure AD 安全性群組來指派這些授權：</span><span class="sxs-lookup"><span data-stu-id="a4087-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="a4087-109">Office 365 企業版 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a4087-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="a4087-110">Enterprise Mobility + Security (EMS) E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a4087-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="a4087-p102">使用您在步驟 2 中找出的群組，尋找包含帳戶清單的群組，其中該群組中的所有使用者必須同時擁有 Office 365 和 EMS 授權。請確定您擁有有足夠的授權可供所有群組成員使用。如果您的授權已用完，在授權可供使用前將不會指派新使用者。</span><span class="sxs-lookup"><span data-stu-id="a4087-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="a4087-114">您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定*以群組為基礎的授權*。</span><span class="sxs-lookup"><span data-stu-id="a4087-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="a4087-115">查看 [Azure Active Directory 中以群組為基礎之授權基本概念](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a4087-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="a4087-116">請參閱「[為 Azure 安全性群組設定以群組為基礎之授權的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」。</span><span class="sxs-lookup"><span data-stu-id="a4087-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="a4087-117">此步驟的結果如下：</span><span class="sxs-lookup"><span data-stu-id="a4087-117">The results of this step are:</span></span>

- <span data-ttu-id="a4087-118">您已識別出哪些安全性群組適用於以群組為基礎的授權。</span><span class="sxs-lookup"><span data-stu-id="a4087-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="a4087-119">您已為以群組為基礎的授權設定這些群組。</span><span class="sxs-lookup"><span data-stu-id="a4087-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a4087-121">測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="a4087-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a4087-122">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-group-license)。</span><span class="sxs-lookup"><span data-stu-id="a4087-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a4087-123">下一步</span><span class="sxs-lookup"><span data-stu-id="a4087-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="a4087-124">監控租用戶和登入活動</span><span class="sxs-lookup"><span data-stu-id="a4087-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

