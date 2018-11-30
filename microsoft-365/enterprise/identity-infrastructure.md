---
title: 第 2 階段：身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版身分識別基礎結構的部署步驟。
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866524"
---
# <a name="phase-2-identity"></a><span data-ttu-id="f6d31-103">第 2 階段：身分識別</span><span class="sxs-lookup"><span data-stu-id="f6d31-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="f6d31-104">在 Microsoft 365 企業版中，妥善的規劃與執行的身分識別基礎結構造就了強大的安全性，利用已驗證的使用者和裝置來存取生產力的工作負載及其資料。</span><span class="sxs-lookup"><span data-stu-id="f6d31-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="f6d31-105">如果您已部署身分識別基礎結構，請參閱[身分識別允出準則](identity-exit-criteria.md)，確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="f6d31-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="f6d31-106">規劃及部署 Microsoft 365 企業版的身分識別基礎結構</span><span class="sxs-lookup"><span data-stu-id="f6d31-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="f6d31-p101">使用下列步驟在雲端規劃及部署新的身分識別基礎結構。您也可以使用這些步驟讓現有的內部部署或混合式身分識別基礎結構能搭配使用 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="f6d31-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f6d31-109">規劃使用者與群組</span><span class="sxs-lookup"><span data-stu-id="f6d31-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="f6d31-110">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="f6d31-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="f6d31-111">設定隨選全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f6d31-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="f6d31-112">簡化密碼重設</span><span class="sxs-lookup"><span data-stu-id="f6d31-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="f6d31-113">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="f6d31-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="f6d31-114">防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="f6d31-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="f6d31-115">同步處理目錄</span><span class="sxs-lookup"><span data-stu-id="f6d31-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="f6d31-116">監控同步處理健康情況</span><span class="sxs-lookup"><span data-stu-id="f6d31-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="f6d31-117">簡化密碼更新</span><span class="sxs-lookup"><span data-stu-id="f6d31-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="f6d31-118">簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="f6d31-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="f6d31-119">自訂 Office 365 登入頁面</span><span class="sxs-lookup"><span data-stu-id="f6d31-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="f6d31-120">設定自動授權</span><span class="sxs-lookup"><span data-stu-id="f6d31-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="f6d31-121">監控租用戶和登入活動</span><span class="sxs-lookup"><span data-stu-id="f6d31-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="f6d31-122">允許使用者建立及管理自己的群組</span><span class="sxs-lookup"><span data-stu-id="f6d31-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="f6d31-123">設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="f6d31-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="f6d31-124">完成這些步驟之後，請移至此階段的[允出準則](identity-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="f6d31-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="f6d31-125">身分識別與裝置存取建議</span><span class="sxs-lookup"><span data-stu-id="f6d31-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="f6d31-p102">Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。針對身分識別，使用下列文章中的建議和設定以及本階段的步驟：</span><span class="sxs-lookup"><span data-stu-id="f6d31-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="f6d31-128">必要條件</span><span class="sxs-lookup"><span data-stu-id="f6d31-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="f6d31-129">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="f6d31-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="f6d31-130">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="f6d31-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f6d31-131">深入了解 Microsoft 的 IT 專業人員如何使用以下資源，規劃及部署 Microsoft 365 企業版的身分識別功能：</span><span class="sxs-lookup"><span data-stu-id="f6d31-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="f6d31-132">在 Microsoft 管理使用者身分識別並且保護存取權</span><span class="sxs-lookup"><span data-stu-id="f6d31-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="f6d31-133">針對提升權限的存取使用 Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="f6d31-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="f6d31-134">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="f6d31-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f6d31-135">請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何為 Microsoft 365 雲端服務[部署混合式身分識別基礎結構](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d31-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="f6d31-136">下一步</span><span class="sxs-lookup"><span data-stu-id="f6d31-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f6d31-137">規劃使用者與群組</span><span class="sxs-lookup"><span data-stu-id="f6d31-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
