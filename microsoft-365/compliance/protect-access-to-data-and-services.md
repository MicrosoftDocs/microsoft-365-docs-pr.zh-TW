---
title: 保護使用者和裝置存取權
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用於保護 Microsoft 365 資料和服務存取權的登陸頁面
ms.openlocfilehash: 4d09ee0aa0ef36222ae0d238b0e7a44ee23994d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632208"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="166c5-103">保護使用者和裝置存取權</span><span class="sxs-lookup"><span data-stu-id="166c5-103">Protect user and device access</span></span>

<span data-ttu-id="166c5-104">保護您的 Microsoft 365 資料和服務存取權，對於防禦 cyberattacks 及防止資料遺失而言很重要。</span><span class="sxs-lookup"><span data-stu-id="166c5-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="166c5-105">相同的保護可以套用至您環境中的其他 SaaS 應用程式，甚至適用于使用 Azure Active Directory 應用程式 Proxy 發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="166c5-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="166c5-106">步驟1：複查建議</span><span class="sxs-lookup"><span data-stu-id="166c5-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="166c5-107">推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="166c5-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="166c5-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="166c5-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="166c5-109">步驟2：保護系統管理員帳戶和存取</span><span class="sxs-lookup"><span data-stu-id="166c5-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="166c5-110">您用來管理 Microsoft 365 環境的管理帳戶包含較高的許可權。</span><span class="sxs-lookup"><span data-stu-id="166c5-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="166c5-111">這些是駭客和 cyberattackers 的有用目標。</span><span class="sxs-lookup"><span data-stu-id="166c5-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="166c5-112">僅使用管理員帳戶來開始。</span><span class="sxs-lookup"><span data-stu-id="166c5-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="166c5-113">系統管理員應該要有個別的使用者帳戶，以進行一般的非系統管理，而且只有在必要時才使用系統管理帳戶，才可完成與工作職能相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="166c5-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="166c5-114">使用多重要素驗證和條件式存取來保護您的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="166c5-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="166c5-115">如需詳細資訊，請參閱[保護系統管理員帳戶](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="166c5-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="166c5-116">接下來，在 Office 365 中設定特殊許可權存取管理。</span><span class="sxs-lookup"><span data-stu-id="166c5-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="166c5-117">「特權存取管理」可讓您透過 Office 365 中的版權管理工作進行精細存取控制。</span><span class="sxs-lookup"><span data-stu-id="166c5-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="166c5-118">它可以協助保護您的組織不會因可能使用現有的許可權系統管理員帳戶存取機密資料或存取重要的設定設定而遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="166c5-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="166c5-119">特殊許可權存取管理的概述</span><span class="sxs-lookup"><span data-stu-id="166c5-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="166c5-120">設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="166c5-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="166c5-121">另一個主要建議是使用專門設定管理工作的工作站。</span><span class="sxs-lookup"><span data-stu-id="166c5-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="166c5-122">這些是僅供管理工作使用的專用裝置。</span><span class="sxs-lookup"><span data-stu-id="166c5-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="166c5-123">請參閱[保護特殊許可權存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="166c5-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="166c5-124">最後，您可以在您的租使用者中建立兩個或多個緊急存取帳戶，以減輕意外缺乏管理存取的影響。</span><span class="sxs-lookup"><span data-stu-id="166c5-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="166c5-125">請參閱[管理 AZURE AD 中的緊急存取帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="166c5-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="166c5-126">步驟3：設定建議的身分識別和裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="166c5-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="166c5-127">多重要素驗證（MFA）和條件式存取原則都是強大的工具，可減少遭到損害的帳戶和未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="166c5-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="166c5-128">建議您實施一組已一起測試的原則。</span><span class="sxs-lookup"><span data-stu-id="166c5-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="166c5-129">如需詳細資訊，包括部署步驟，請參閱[Identity and device access](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)設定。</span><span class="sxs-lookup"><span data-stu-id="166c5-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="166c5-130">這些原則會執行下列功能：</span><span class="sxs-lookup"><span data-stu-id="166c5-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="166c5-131">單行因素驗證</span><span class="sxs-lookup"><span data-stu-id="166c5-131">Mult-factor authentication</span></span>
- <span data-ttu-id="166c5-132">條件式存取</span><span class="sxs-lookup"><span data-stu-id="166c5-132">Conditional access</span></span>
- <span data-ttu-id="166c5-133">Intune 應用程式保護（裝置的應用程式和資料保護）</span><span class="sxs-lookup"><span data-stu-id="166c5-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="166c5-134">Intune 裝置合規性</span><span class="sxs-lookup"><span data-stu-id="166c5-134">Intune device compliance</span></span>
- <span data-ttu-id="166c5-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="166c5-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="166c5-136">實施 Intune 裝置合規性需要裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="166c5-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="166c5-137">管理裝置可讓您在允許存取您環境中的資源之前，確定這些裝置的健康和相容性。</span><span class="sxs-lookup"><span data-stu-id="166c5-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="166c5-138">請參閱[在 Intune 中註冊裝置以進行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="166c5-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="166c5-139">步驟4：設定 SharePoint 裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="166c5-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="166c5-140">Microsoft 建議您使用裝置存取控制，以機密和高管制內容來保護 SharePoint 網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="166c5-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="166c5-141">如需詳細資訊，請參閱[保護 SharePoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="166c5-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

