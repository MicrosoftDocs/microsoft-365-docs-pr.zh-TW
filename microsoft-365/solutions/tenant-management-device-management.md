---
title: 步驟 5： 適用于企業承租人的 Microsoft 365 裝置和應用程式管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 為 Microsoft 365 承租人的裝置和應用程式管理部署正確的選項。
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050991"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e4cd7-104">步驟 5.</span><span class="sxs-lookup"><span data-stu-id="e4cd7-104">Step 5.</span></span> <span data-ttu-id="e4cd7-105">適用于企業承租人的 Microsoft 365 裝置和應用程式管理</span><span class="sxs-lookup"><span data-stu-id="e4cd7-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e4cd7-106">Microsoft 365 for enterprise 包含一些功能，可協助您管理裝置，並在組織內使用行動裝置管理 (MDM) 和行動應用程式管理 (MAM) 來管理裝置及使用這些裝置上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="e4cd7-107">您可以管理 iOS、Android、macOS 和 Windows 裝置，以保護您組織的資源（包括您的資料）的存取。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="e4cd7-108">例如，您可以防止將電子郵件傳送給組織外部的人員，或從工作者個人裝置上的個人資料隔離組織資料。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="e4cd7-109">以下是使用者、其裝置的驗證和管理，以及其使用本機和雲端生產力應用程式（如 Microsoft 團隊）的範例。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![使用者、裝置及應用程式的驗證與管理](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="e4cd7-111">為了協助您保護組織的資源，Microsoft 365 for enterprise 包含協助管理裝置及其存取應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="e4cd7-112">裝置管理有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="e4cd7-112">There are two options for device management:</span></span>

- <span data-ttu-id="e4cd7-113">Microsoft Intune，是企業的綜合裝置和應用程式管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="e4cd7-114">基本行動性和安全性，這是包括所有 Microsoft 365 產品的 Intune 服務的子集，用來管理組織中的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="e4cd7-115">如需詳細資訊，請參閱 [基本行動性和安全性的功能](../admin/basic-mobility-security/capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="e4cd7-116">如果您有 Microsoft 365 E3 或 E5，您應該使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="e4cd7-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e4cd7-117">Microsoft Intune</span></span>

<span data-ttu-id="e4cd7-118">您可以使用 [Microsoft Intune](/mem/intune/fundamentals/planning-guide) 管理使用 MDM 或 MAM 對您組織的存取。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="e4cd7-119">MDM 是使用者在 Intune 中「註冊」其裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="e4cd7-120">裝置註冊後，它就是受管理的裝置，而且可以接收您組織的原則、規則和設定。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="e4cd7-121">例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="e4cd7-122">具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您組織的原則進行管理。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="e4cd7-123">不過，您仍然需要保護組織的資源和資料。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="e4cd7-124">在此案例中，您可以使用 MAM 來保護您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="e4cd7-125">例如，您可以使用需要使用者在存取裝置上的 SharePoint 時輸入 PIN 碼的 MAM 原則。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="e4cd7-126">您也會決定要如何管理個人裝置和組織所擁有的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="e4cd7-127">您可能想要視裝置的用途而異。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="e4cd7-128">身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="e4cd7-128">Identity and device access configurations</span></span>

<span data-ttu-id="e4cd7-129">Microsoft 提供一組身分 [識別與裝置存取](../security/defender-365-security/microsoft-365-policies-configurations.md) 設定，以確保安全且生產力的工作力。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-129">Microsoft provides a set of configurations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="e4cd7-130">這些設定包括使用：</span><span class="sxs-lookup"><span data-stu-id="e4cd7-130">These configurations include the use of:</span></span>

- <span data-ttu-id="e4cd7-131">Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="e4cd7-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="e4cd7-132">Microsoft Intune 裝置合規性和應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="e4cd7-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="e4cd7-133">Azure AD 身分識別保護使用者風險原則</span><span class="sxs-lookup"><span data-stu-id="e4cd7-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="e4cd7-134">其他 cloud 應用程式的原則</span><span class="sxs-lookup"><span data-stu-id="e4cd7-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="e4cd7-135">以下是應用這些設定和原則的範例，以驗證及限制使用者、其裝置，以及其使用本機和雲端生產力應用程式（如 Microsoft 團隊）。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![身分識別與裝置存取設定，以瞭解使用者的需求和限制、裝置及其應用程式的使用](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="e4cd7-137">如需裝置存取和應用程式管理，請使用下列文章中的設定：</span><span class="sxs-lookup"><span data-stu-id="e4cd7-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="e4cd7-138">必要條件</span><span class="sxs-lookup"><span data-stu-id="e4cd7-138">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="e4cd7-139">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="e4cd7-139">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="e4cd7-140">步驟 5 的結果</span><span class="sxs-lookup"><span data-stu-id="e4cd7-140">Results of Step 5</span></span>

<span data-ttu-id="e4cd7-141">針對 Microsoft 365 租使用者的裝置和應用程式管理，您已決定 Intune 設定和原則，以驗證及限制使用者、其裝置，以及其使用本機和 cloud 生產工具的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="e4cd7-142">以下是具有 Intune 裝置和應用程式管理的承租人範例，新的元素會反白顯示。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![包含 Intune 裝置和應用程式管理的承租人範例](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="e4cd7-144">在此圖中，租使用者有：</span><span class="sxs-lookup"><span data-stu-id="e4cd7-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="e4cd7-145">在 Intune 中註冊的組織擁有的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="e4cd7-146">已登記和個人裝置的 Intune 裝置和應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="e4cd7-147">裝置和應用程式管理的持續維護</span><span class="sxs-lookup"><span data-stu-id="e4cd7-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="e4cd7-148">您可能需要進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e4cd7-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="e4cd7-149">管理裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-149">Manage device enrollment.</span></span>
- <span data-ttu-id="e4cd7-150">修改其他應用程式、裝置及安全性需求的設定和原則。</span><span class="sxs-lookup"><span data-stu-id="e4cd7-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>