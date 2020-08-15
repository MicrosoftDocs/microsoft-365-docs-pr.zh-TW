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
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688486"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="6743f-104">Microsoft 365 的裝置管理藍圖</span><span class="sxs-lookup"><span data-stu-id="6743f-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="6743f-105">Microsoft 365 for enterprise 包含的功能可協助您管理組織內的裝置及其應用程式。</span><span class="sxs-lookup"><span data-stu-id="6743f-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="6743f-106">管理行動裝置可協助您保護和保護組織的資源。</span><span class="sxs-lookup"><span data-stu-id="6743f-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="6743f-107">裝置管理有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="6743f-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="6743f-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6743f-108">Microsoft Intune</span></span>

<span data-ttu-id="6743f-109">Intune 可讓您使用行動裝置管理 (MDM) 或行動應用程式管理 (MAM) ，以管理對組織存取的選項。</span><span class="sxs-lookup"><span data-stu-id="6743f-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="6743f-110">MDM 是使用者在 Intune 中「註冊」其裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="6743f-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="6743f-111">註冊後，他們就是受管理的裝置，而且可以接收組織使用的任何原則、規則和設定。</span><span class="sxs-lookup"><span data-stu-id="6743f-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="6743f-112">例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。</span><span class="sxs-lookup"><span data-stu-id="6743f-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="6743f-113">具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您的原則進行管理。</span><span class="sxs-lookup"><span data-stu-id="6743f-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="6743f-114">不過，您仍然需要保護組織的資源和資料。</span><span class="sxs-lookup"><span data-stu-id="6743f-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="6743f-115">在此案例中，您可以使用 MAM 來保護您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6743f-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="6743f-116">例如，您可以使用需要使用者在存取裝置上的 SharePoint 時輸入 PIN 碼的 MAM 原則。</span><span class="sxs-lookup"><span data-stu-id="6743f-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="6743f-117">您也會決定要如何管理個人或組織所擁有的裝置。</span><span class="sxs-lookup"><span data-stu-id="6743f-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="6743f-118">您可能想要視裝置的用途而異。</span><span class="sxs-lookup"><span data-stu-id="6743f-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="6743f-119">從 [這裡](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)開始。</span><span class="sxs-lookup"><span data-stu-id="6743f-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="6743f-120">基本行動性和安全性</span><span class="sxs-lookup"><span data-stu-id="6743f-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="6743f-121">這是 Microsoft 365 內建的，可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="6743f-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="6743f-122">您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。</span><span class="sxs-lookup"><span data-stu-id="6743f-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="6743f-123">從 [這裡](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)開始。</span><span class="sxs-lookup"><span data-stu-id="6743f-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="6743f-124">身分識別與裝置存取建議</span><span class="sxs-lookup"><span data-stu-id="6743f-124">Identity and device access recommendations</span></span>

<span data-ttu-id="6743f-125">Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。</span><span class="sxs-lookup"><span data-stu-id="6743f-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="6743f-126">針對裝置存取，請使用下列文章中的建議和設定，以及此階段中的步驟：</span><span class="sxs-lookup"><span data-stu-id="6743f-126">For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="6743f-127">必要條件</span><span class="sxs-lookup"><span data-stu-id="6743f-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="6743f-128">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="6743f-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a><span data-ttu-id="6743f-129">Microsoft 如何對 Microsoft 365 進行裝置管理</span><span class="sxs-lookup"><span data-stu-id="6743f-129">How Microsoft does device management for Microsoft 365</span></span>

<span data-ttu-id="6743f-130">深入瞭解 Microsoft 的 IT 專家如何 [使用 EMS 管理裝置](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)。</span><span class="sxs-lookup"><span data-stu-id="6743f-130">Learn how IT experts at Microsoft [manage devices with EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).</span></span>

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="6743f-131">Contoso 如何對 Microsoft 365 進行裝置管理</span><span class="sxs-lookup"><span data-stu-id="6743f-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="6743f-132">請參閱 Contoso Corporation （虛構但有代表性的跨國企業）如何使用 Microsoft 365 雲端服務 [部署行動裝置管理基礎結構](contoso-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="6743f-132">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)
