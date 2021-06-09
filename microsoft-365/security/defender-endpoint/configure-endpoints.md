---
title: Windows 10 裝置的上線工具及方法
description: 板載 Windows 10 裝置，使其可將感應器資料傳送至 Microsoft Defender for Endpoint 感應器
keywords: 板載 Windows 10 裝置，群組原則，端點設定管理員，行動裝置管理，本機腳本，gp，sccm，mdm，intune
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892826"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="48686-104">Windows 10 裝置的上線工具及方法</span><span class="sxs-lookup"><span data-stu-id="48686-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48686-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="48686-105">**Applies to:**</span></span>
- [<span data-ttu-id="48686-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="48686-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48686-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48686-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="48686-108">Microsoft 365端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="48686-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="48686-109">Microsoft 365有問必答風險管理</span><span class="sxs-lookup"><span data-stu-id="48686-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="48686-110">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="48686-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48686-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="48686-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="48686-112">您組織中的裝置必須設定，讓 Endpoint service 的 Defender 才能從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="48686-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="48686-113">您可以使用各種方法和部署工具來設定組織中的裝置。</span><span class="sxs-lookup"><span data-stu-id="48686-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="48686-114">下列為支援的部署工具及方法：</span><span class="sxs-lookup"><span data-stu-id="48686-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="48686-115">群組原則</span><span class="sxs-lookup"><span data-stu-id="48686-115">Group Policy</span></span>
- <span data-ttu-id="48686-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="48686-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="48686-117">行動裝置管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="48686-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="48686-118">本機腳本</span><span class="sxs-lookup"><span data-stu-id="48686-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="48686-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="48686-119">In this section</span></span>
<span data-ttu-id="48686-120">主題</span><span class="sxs-lookup"><span data-stu-id="48686-120">Topic</span></span> | <span data-ttu-id="48686-121">描述</span><span class="sxs-lookup"><span data-stu-id="48686-121">Description</span></span>
:---|:---
[<span data-ttu-id="48686-122">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="48686-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="48686-123">使用群組原則在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="48686-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="48686-124">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="48686-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="48686-125">您可以使用 Microsoft 端點管理員 (目前的分支) 版本1606或 Microsoft 端點管理員 (目前的分支) 版本1602或更早版本，以在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="48686-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="48686-126">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="48686-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="48686-127">使用行動裝置管理工具或 Microsoft Intune，在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="48686-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="48686-128">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="48686-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="48686-129">瞭解如何使用本機腳本，在端點上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="48686-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="48686-130">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="48686-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="48686-131">瞭解如何使用 configuration 套件來設定 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="48686-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="48686-132">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="48686-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48686-133">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="48686-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
