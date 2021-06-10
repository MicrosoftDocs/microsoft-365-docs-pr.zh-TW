---
title: Windows 10 裝置的上線工具及方法
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 板載 Windows 10 裝置，使其可將感應器資料傳送至 Microsoft 365 規範解決方案
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917849"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="d3074-103">Windows 10 裝置的上線工具及方法</span><span class="sxs-lookup"><span data-stu-id="d3074-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="d3074-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d3074-104">**Applies to:**</span></span>
- [<span data-ttu-id="d3074-105">Microsoft 365端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="d3074-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="d3074-106">您組織中的裝置必須設定，才能讓 Microsoft 365 端點資料遺失防護服務可以從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="d3074-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="d3074-107">您可以使用各種方法和部署工具來設定組織中的裝置。</span><span class="sxs-lookup"><span data-stu-id="d3074-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="d3074-108">下列為支援的部署工具及方法：</span><span class="sxs-lookup"><span data-stu-id="d3074-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="d3074-109">群組原則</span><span class="sxs-lookup"><span data-stu-id="d3074-109">group policy</span></span>
- <span data-ttu-id="d3074-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d3074-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="d3074-111">行動裝置管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="d3074-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="d3074-112">本機腳本</span><span class="sxs-lookup"><span data-stu-id="d3074-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d3074-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="d3074-113">In this section</span></span>
<span data-ttu-id="d3074-114">主題</span><span class="sxs-lookup"><span data-stu-id="d3074-114">Topic</span></span> | <span data-ttu-id="d3074-115">描述</span><span class="sxs-lookup"><span data-stu-id="d3074-115">Description</span></span>
:---|:---
[<span data-ttu-id="d3074-116">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="d3074-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="d3074-117">使用群組原則在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="d3074-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="d3074-118">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="d3074-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="d3074-119">您可以使用 Microsoft Endpoint Configuration Manager (目前的分支) 版本1606或 Microsoft Endpoint Configuration Manager (目前的分支) 版本1602或更早版本，以在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="d3074-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="d3074-120">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="d3074-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="d3074-121">使用行動裝置管理工具或 Microsoft Intune，在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="d3074-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="d3074-122">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="d3074-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="d3074-123">瞭解如何使用本機腳本，在端點上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="d3074-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="d3074-124">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="d3074-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="d3074-125">瞭解如何使用 configuration 套件來設定 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="d3074-125">Learn how to use the configuration package to configure VDI devices.</span></span>