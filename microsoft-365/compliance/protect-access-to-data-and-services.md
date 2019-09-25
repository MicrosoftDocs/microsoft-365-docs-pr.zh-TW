---
title: 保護使用者和裝置存取權
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
description: 用于保护对 O365 数据和服务的访问的登录页
ms.openlocfilehash: 9fc1691e7e36f994b5d0b8a6a9735fe8ccd8735a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077822"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="2a7a6-103">保護使用者和裝置存取權</span><span class="sxs-lookup"><span data-stu-id="2a7a6-103">Protect user and device access</span></span>

<span data-ttu-id="2a7a6-104">保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-104">Protecting access to your Office 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="2a7a6-105">相同的保护可以应用于环境中的其他 SaaS 应用程序，甚至适用于使用 Azure 活动目录应用程序代理发布的本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="2a7a6-106">第 1 步：审查建议</span><span class="sxs-lookup"><span data-stu-id="2a7a6-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="2a7a6-107">推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="2a7a6-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="2a7a6-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="2a7a6-109">第 2 步：保护管理员帐户和访问权限</span><span class="sxs-lookup"><span data-stu-id="2a7a6-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="2a7a6-110">用于管理 Office 365 环境的管理帐户包括提升的权限。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="2a7a6-111">这些是黑客和网络攻击者的宝贵目标。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="2a7a6-112">首先，仅使用管理员帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="2a7a6-113">管理员应具有用于常规、非管理用途的单独用户帐户，并且仅在必要时使用其管理帐户来完成与其作业功能关联的任务。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="2a7a6-114">通过多重身份验证和条件访问保护管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="2a7a6-115">有关详细信息，请参阅[保护管理员帐户](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="2a7a6-116">接下来，在 Office 365 中配置特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="2a7a6-117">特权访问管理允许对 Office 365 中的特权管理任务进行精细访问控制。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="2a7a6-118">它可以帮助保护您的组织免受可能使用现有特权管理员帐户的违规事件，这些帐户具有对敏感数据的长期访问权限或对关键配置设置的访问。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="2a7a6-119">特权访问管理概述</span><span class="sxs-lookup"><span data-stu-id="2a7a6-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="2a7a6-120">設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="2a7a6-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="2a7a6-121">另一个首要建议是使用专门为管理工作配置的工作站。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="2a7a6-122">这些是仅用于管理任务的专用设备。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="2a7a6-123">请参阅[保护特权访问](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="2a7a6-124">最后，您可以通过在租户中创建两个或多个紧急访问帐户来减轻意外缺乏管理访问权限的影响。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="2a7a6-125">请参阅[在 Azure AD 中管理紧急访问帐户。](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="2a7a6-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="2a7a6-126">步骤 3：配置建议的标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="2a7a6-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="2a7a6-127">多重身份验证 （MFA） 和条件访问策略是缓解帐户受损和未经授权的访问的强大工具。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="2a7a6-128">我们建议实现一组一起测试的策略。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="2a7a6-129">有关详细信息（包括部署步骤），请参阅[标识和设备访问配置](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="2a7a6-130">这些策略实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="2a7a6-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="2a7a6-131">木因身份验证</span><span class="sxs-lookup"><span data-stu-id="2a7a6-131">Mult-factor authentication</span></span>
- <span data-ttu-id="2a7a6-132">條件式存取</span><span class="sxs-lookup"><span data-stu-id="2a7a6-132">Conditional access</span></span>
- <span data-ttu-id="2a7a6-133">Intune 应用保护（设备的应用和数据保护）</span><span class="sxs-lookup"><span data-stu-id="2a7a6-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="2a7a6-134">Intune 设备合规性</span><span class="sxs-lookup"><span data-stu-id="2a7a6-134">Intune device compliance</span></span>
- <span data-ttu-id="2a7a6-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2a7a6-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="2a7a6-136">实现 Intune 设备合规性需要设备注册。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="2a7a6-137">通过管理设备，在允许设备访问环境中的资源之前，确保设备是正常运行和合规的。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="2a7a6-138">请参阅[在 Intune 中注册设备进行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="2a7a6-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="2a7a6-139">步骤 4：配置 SharePoint 设备访问策略</span><span class="sxs-lookup"><span data-stu-id="2a7a6-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="2a7a6-140">Microsoft 建议您使用设备访问控制保护具有敏感且高度监管内容的 SharePoint 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="2a7a6-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="2a7a6-141">有关详细信息，请参阅保护[SharePoint 网站和文件的策略建议。](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)</span><span class="sxs-lookup"><span data-stu-id="2a7a6-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

