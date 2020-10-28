---
title: 'Windows 10 裝置的上架工具和方法 (預覽) '
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
description: 板載 Windows 10 裝置，讓他們可以將感應器資料傳送至 Microsoft 365 合規性解決方案
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769640"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="0129d-103">Windows 10 裝置的上架工具和方法 (預覽) </span><span class="sxs-lookup"><span data-stu-id="0129d-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="0129d-104">適用於： </span><span class="sxs-lookup"><span data-stu-id="0129d-104">**Applies to:**</span></span>
- [<span data-ttu-id="0129d-105">Microsoft 365 端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="0129d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="0129d-106">您組織中的裝置必須設定，Microsoft 365 端點資料遺失防護服務才能從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="0129d-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="0129d-107">您可以使用各種方法和部署工具來設定組織中的裝置。</span><span class="sxs-lookup"><span data-stu-id="0129d-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="0129d-108">下列為支援的部署工具及方法：</span><span class="sxs-lookup"><span data-stu-id="0129d-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="0129d-109">群組原則</span><span class="sxs-lookup"><span data-stu-id="0129d-109">group policy</span></span>
- <span data-ttu-id="0129d-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0129d-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0129d-111">行動裝置管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="0129d-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="0129d-112">本機腳本</span><span class="sxs-lookup"><span data-stu-id="0129d-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0129d-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="0129d-113">In this section</span></span>
<span data-ttu-id="0129d-114">主題</span><span class="sxs-lookup"><span data-stu-id="0129d-114">Topic</span></span> | <span data-ttu-id="0129d-115">描述</span><span class="sxs-lookup"><span data-stu-id="0129d-115">Description</span></span>
:---|:---
[<span data-ttu-id="0129d-116">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0129d-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="0129d-117">使用群組原則在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="0129d-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0129d-118">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="0129d-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="0129d-119">您可以使用 Microsoft 端點 Configuration Manager (目前的分支) 版本1606或 Microsoft 端點 Configuration Manager (電流分支) 版本1602或更早版本，以在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="0129d-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0129d-120">使用行動裝置管理工具的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0129d-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="0129d-121">使用行動裝置管理工具或 Microsoft Intune 在裝置上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="0129d-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="0129d-122">使用本機腳本的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0129d-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="0129d-123">瞭解如何使用本機腳本，在端點上部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="0129d-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="0129d-124">板載非持久性虛擬桌面基礎結構 (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="0129d-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="0129d-125">瞭解如何使用 configuration 套件來設定 VDI 裝置。</span><span class="sxs-lookup"><span data-stu-id="0129d-125">Learn how to use the configuration package to configure VDI devices.</span></span>
