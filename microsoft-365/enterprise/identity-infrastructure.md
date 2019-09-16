---
title: 第 2 階段：身分識別
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
description: Microsoft 365 企業版身分識別基礎結構的部署步驟。
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981946"
---
# <a name="phase-2-identity"></a><span data-ttu-id="40f31-103">第 2 階段：身分識別</span><span class="sxs-lookup"><span data-stu-id="40f31-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="40f31-104">在 Microsoft 365 企業版中，妥善的規劃與執行的身分識別基礎結構造就了強大的安全性，利用已驗證的使用者和裝置來存取生產力的工作負載及其資料。</span><span class="sxs-lookup"><span data-stu-id="40f31-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="40f31-105">請觀看這段影片，以大略了解身分識別模型和 Microsoft 365 企業版的驗證。</span><span class="sxs-lookup"><span data-stu-id="40f31-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="40f31-106">如果您已部署身分識別基礎結構，請參閱[身分識別允出準則](identity-exit-criteria.md)，確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="40f31-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="40f31-107">如需每個 Microsoft 365 企業版方案的身分識別功能、Azure Active Directory (Azure AD) 的角色、內部部署和雲端式元件，以及最常見的驗證組態，請參閱[身分識別基礎結構海報](media/identity-infrastructure/M365E-ID-Infra.pdf)。</span><span class="sxs-lookup"><span data-stu-id="40f31-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="40f31-108">[![身分識別基礎結構海報](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="40f31-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="40f31-109">這份雙頁海報可讓您快速了解有關 Microsoft 365 企業版的身分識別概念和組態。</span><span class="sxs-lookup"><span data-stu-id="40f31-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="40f31-110">您也可以[下載此海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="40f31-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="40f31-111">規劃及部署 Microsoft 365 企業版的身分識別基礎結構</span><span class="sxs-lookup"><span data-stu-id="40f31-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="40f31-p101">使用下列步驟在雲端規劃及部署新的身分識別基礎結構。您也可以使用這些步驟讓現有的內部部署或混合式身分識別基礎結構能搭配使用 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="40f31-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="40f31-114">規劃使用者與群組</span><span class="sxs-lookup"><span data-stu-id="40f31-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="40f31-115">保護您的特殊權限身分識別</span><span class="sxs-lookup"><span data-stu-id="40f31-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="40f31-116">設定混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="40f31-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="40f31-117">設定安全的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="40f31-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="40f31-118">簡化使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="40f31-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="40f31-119">使用群組更輕鬆地進行管理</span><span class="sxs-lookup"><span data-stu-id="40f31-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="40f31-120">設定身分識別治理</span><span class="sxs-lookup"><span data-stu-id="40f31-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="40f31-121">完成這些步驟之後，請移至此階段的[允出準則](identity-exit-criteria.md)，以確定您符合 Microsoft 365 企業版身分識別的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="40f31-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="40f31-122">身分識別與裝置存取建議</span><span class="sxs-lookup"><span data-stu-id="40f31-122">Identity and device access recommendations</span></span>

<span data-ttu-id="40f31-p102">Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。針對身分識別，使用下列文章中的建議和設定以及本階段的步驟：</span><span class="sxs-lookup"><span data-stu-id="40f31-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="40f31-125">必要條件</span><span class="sxs-lookup"><span data-stu-id="40f31-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="40f31-126">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="40f31-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="40f31-127">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="40f31-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="40f31-128">了解 Microsoft 的 IT 專家如何使用[管理身分識別和保護存取](https://www.microsoft.com/zh-TW/itshowcase/deploying-and-managing-microsoft-365#primaryR5)。</span><span class="sxs-lookup"><span data-stu-id="40f31-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/zh-TW/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="40f31-129">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="40f31-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="40f31-130">請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何為 Microsoft 365 雲端服務[部署混合式身分識別基礎結構](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="40f31-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="40f31-131">下一步</span><span class="sxs-lookup"><span data-stu-id="40f31-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="40f31-132">規劃使用者與群組</span><span class="sxs-lookup"><span data-stu-id="40f31-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
