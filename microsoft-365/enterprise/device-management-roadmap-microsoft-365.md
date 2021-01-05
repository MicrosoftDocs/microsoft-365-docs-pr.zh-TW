---
title: Microsoft 365 的裝置管理藍圖
keywords: Microsoft 365，Microsoft 365 for enterprise，Microsoft 365 檔，行動裝置管理，Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: 設定 Microsoft 365 裝置管理的藍圖。
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749536"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="69217-104">Microsoft 365 的裝置管理藍圖</span><span class="sxs-lookup"><span data-stu-id="69217-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="69217-105">Microsoft 365 for enterprise 包含的功能可協助您管理組織內的裝置及其應用程式。</span><span class="sxs-lookup"><span data-stu-id="69217-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="69217-106">管理行動裝置可協助您保護和保護組織的資源。</span><span class="sxs-lookup"><span data-stu-id="69217-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="69217-107">裝置管理有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="69217-107">There are two options for device management:</span></span>

- [<span data-ttu-id="69217-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="69217-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="69217-109">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="69217-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="69217-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="69217-110">Microsoft Intune</span></span>

<span data-ttu-id="69217-111">您可以使用 Microsoft Intune，利用行動裝置管理或行動應用程式管理來管理組織的存取權。</span><span class="sxs-lookup"><span data-stu-id="69217-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="69217-112">行動裝置管理是使用者在 Intune 中「註冊」其裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="69217-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="69217-113">裝置註冊後，即為受管理的裝置;因此，它可以接收您組織的原則、規則和設定。</span><span class="sxs-lookup"><span data-stu-id="69217-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="69217-114">例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。</span><span class="sxs-lookup"><span data-stu-id="69217-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="69217-115">具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您組織的原則進行管理。</span><span class="sxs-lookup"><span data-stu-id="69217-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="69217-116">不過，您仍然需要保護組織的資源和資料。</span><span class="sxs-lookup"><span data-stu-id="69217-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="69217-117">在此案例中，您可以使用行動應用程式管理來保護您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="69217-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="69217-118">例如，您可以使用行動應用程式管理原則，此原則要求使用者在存取裝置上的 SharePoint 線上時輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="69217-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="69217-119">您也會決定要如何管理個人裝置和組織所擁有的裝置。</span><span class="sxs-lookup"><span data-stu-id="69217-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="69217-120">您可能想要視裝置的用途而異。</span><span class="sxs-lookup"><span data-stu-id="69217-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="69217-121">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="69217-121">Basic Mobility and Security</span></span>

<span data-ttu-id="69217-122">這是 Microsoft 365 內建的，可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="69217-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="69217-123">您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。</span><span class="sxs-lookup"><span data-stu-id="69217-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="69217-124">選擇兩個選項</span><span class="sxs-lookup"><span data-stu-id="69217-124">Choose between the two options</span></span>

<span data-ttu-id="69217-125">為了協助您更進一步評估最適合您的裝置管理選項，請參閱 [Choose Basic 行動性安全性與 Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)。</span><span class="sxs-lookup"><span data-stu-id="69217-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="69217-126">根據您的評估，使用下列專案開始管理您的裝置：</span><span class="sxs-lookup"><span data-stu-id="69217-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="69217-127">Intune</span><span class="sxs-lookup"><span data-stu-id="69217-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="69217-128">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="69217-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="69217-129">身分識別與裝置存取建議</span><span class="sxs-lookup"><span data-stu-id="69217-129">Identity and device access recommendations</span></span>

<span data-ttu-id="69217-130">Microsoft 會針對[身分識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。</span><span class="sxs-lookup"><span data-stu-id="69217-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="69217-131">如需裝置存取，請使用下列文章中的建議和設定：</span><span class="sxs-lookup"><span data-stu-id="69217-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="69217-132">必要條件</span><span class="sxs-lookup"><span data-stu-id="69217-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="69217-133">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="69217-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="69217-134">Contoso 如何對 Microsoft 365 進行裝置管理</span><span class="sxs-lookup"><span data-stu-id="69217-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="69217-135">如需虛構但具有代表性的多國公司如何使用 Microsoft 365 雲端服務部署行動裝置管理基礎結構的資訊，請參閱 [mobile device management For Contoso](contoso-mdm.md)。</span><span class="sxs-lookup"><span data-stu-id="69217-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
