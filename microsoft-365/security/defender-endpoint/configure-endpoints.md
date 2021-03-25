---
title: Windows 10 裝置的上線工具及方法
description: 板載 Windows 10 裝置，讓他們可以將感應器資料傳送至 Microsoft Defender ATP 感應器
keywords: 板載 Windows 10 裝置、群組原則、端點 configuration manager、行動裝置管理、本機腳本、gp、sccm、mdm、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165534"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="cf589-104">Windows 10 裝置的上線工具及方法</span><span class="sxs-lookup"><span data-stu-id="cf589-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf589-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cf589-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf589-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cf589-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf589-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf589-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="cf589-108">Microsoft 365 端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="cf589-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="cf589-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cf589-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf589-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cf589-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="cf589-111">您組織中的裝置必須設定，讓 Endpoint service 的 Defender 才能從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="cf589-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="cf589-112">您可以使用各種方法和部署工具來設定組織中的裝置。</span><span class="sxs-lookup"><span data-stu-id="cf589-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="cf589-113">下列為支援的部署工具及方法：</span><span class="sxs-lookup"><span data-stu-id="cf589-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="cf589-114">群組原則</span><span class="sxs-lookup"><span data-stu-id="cf589-114">Group Policy</span></span>
- <span data-ttu-id="cf589-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cf589-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="cf589-116">行動裝置管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="cf589-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="cf589-117">本機腳本</span><span class="sxs-lookup"><span data-stu-id="cf589-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cf589-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="cf589-118">In this section</span></span>
<span data-ttu-id="cf589-119">主題</span><span class="sxs-lookup"><span data-stu-id="cf589-119">Topic</span></span> | <span data-ttu-id="cf589-120">描述</span><span class="sxs-lookup"><span data-stu-id="cf589-120">Description</span></span>
:---|:---
[<span data-ttu-id="cf589-121">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="cf589-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="cf589-122">使用群組原則在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="cf589-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="cf589-123">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="cf589-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="cf589-124">您可以使用 Microsoft 端點管理員 (目前的分支) 版本1606或 Microsoft 端點管理員 (目前的分支) 版本1602或更早版本，以在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="cf589-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="cf589-125">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="cf589-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="cf589-126">使用行動裝置管理工具或 Microsoft Intune 在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="cf589-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="cf589-127">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="cf589-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="cf589-128">瞭解如何使用本機腳本，在端點上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="cf589-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="cf589-129">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="cf589-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="cf589-130">瞭解如何使用 configuration 套件來設定 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="cf589-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="cf589-131">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cf589-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf589-132">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cf589-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
