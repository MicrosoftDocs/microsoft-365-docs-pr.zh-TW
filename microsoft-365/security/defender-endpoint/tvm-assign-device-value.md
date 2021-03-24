---
title: 指派裝置價值-威脅和弱點管理
description: 瞭解如何對裝置指派低、標準或高值，以協助您區分資產優先順序。
keywords: microsoft defender atp device value，威脅和弱點管理裝置值，高價值裝置，裝置價值暴露分數
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be578158e18d55bb25d450749c3fb4373854456b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059260"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="3f21a-104">指派裝置價值-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="3f21a-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f21a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3f21a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3f21a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3f21a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3f21a-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="3f21a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3f21a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f21a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3f21a-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3f21a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f21a-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3f21a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3f21a-111">定義裝置的值可協助您區分資產優先順序。</span><span class="sxs-lookup"><span data-stu-id="3f21a-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="3f21a-112">裝置值用於將個別資產的風險 appetite 納入威脅和弱點管理洩密評分計算中。</span><span class="sxs-lookup"><span data-stu-id="3f21a-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="3f21a-113">指派為 "高值" 的裝置會獲得更多權重。</span><span class="sxs-lookup"><span data-stu-id="3f21a-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="3f21a-114">您也可以使用 [ [設定裝置值] API](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="3f21a-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="3f21a-115">裝置值選項：</span><span class="sxs-lookup"><span data-stu-id="3f21a-115">Device value options:</span></span>

- <span data-ttu-id="3f21a-116">低</span><span class="sxs-lookup"><span data-stu-id="3f21a-116">Low</span></span>
- <span data-ttu-id="3f21a-117">一般 (預設值)</span><span class="sxs-lookup"><span data-stu-id="3f21a-117">Normal (Default)</span></span>
- <span data-ttu-id="3f21a-118">高</span><span class="sxs-lookup"><span data-stu-id="3f21a-118">High</span></span>

<span data-ttu-id="3f21a-119">應指派高值之裝置的範例：</span><span class="sxs-lookup"><span data-stu-id="3f21a-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="3f21a-120">網域控制站、Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f21a-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="3f21a-121">網際網路對向裝置</span><span class="sxs-lookup"><span data-stu-id="3f21a-121">Internet facing devices</span></span>
- <span data-ttu-id="3f21a-122">VIP 裝置</span><span class="sxs-lookup"><span data-stu-id="3f21a-122">VIP devices</span></span>
- <span data-ttu-id="3f21a-123">主控內部/外部生產服務的裝置</span><span class="sxs-lookup"><span data-stu-id="3f21a-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="3f21a-124">選擇設備值</span><span class="sxs-lookup"><span data-stu-id="3f21a-124">Choose device value</span></span>

1. <span data-ttu-id="3f21a-125">流覽至任一裝置頁面，最簡單的地方是來自設備庫存。</span><span class="sxs-lookup"><span data-stu-id="3f21a-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="3f21a-126">從頁面頂端的 [動作] 欄旁邊的三個點選取 [ **裝置值** ]。</span><span class="sxs-lookup"><span data-stu-id="3f21a-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![裝置值 dropdown 的範例。](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="3f21a-128">快顯視窗會顯示目前的裝置值及其意義。</span><span class="sxs-lookup"><span data-stu-id="3f21a-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="3f21a-129">請複查裝置的值，並選擇最適合您的裝置的值。</span><span class="sxs-lookup"><span data-stu-id="3f21a-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="3f21a-130">![裝置值浮出的範例。](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="3f21a-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="3f21a-131">裝置價值如何影響曝光分數</span><span class="sxs-lookup"><span data-stu-id="3f21a-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="3f21a-132">曝光得分是所有裝置的加權平均。</span><span class="sxs-lookup"><span data-stu-id="3f21a-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="3f21a-133">如果您有裝置群組，也可以依設備群組篩選排名。</span><span class="sxs-lookup"><span data-stu-id="3f21a-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="3f21a-134">一般裝置的重量為1</span><span class="sxs-lookup"><span data-stu-id="3f21a-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="3f21a-135">低價值裝置的重量為0.75</span><span class="sxs-lookup"><span data-stu-id="3f21a-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="3f21a-136">高值裝置的重量為 NumberOfAssets/10。</span><span class="sxs-lookup"><span data-stu-id="3f21a-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="3f21a-137">如果您有100裝置，則每個高值裝置的重量為 10 (100/10) </span><span class="sxs-lookup"><span data-stu-id="3f21a-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f21a-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="3f21a-138">Related topics</span></span>

- [<span data-ttu-id="3f21a-139">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="3f21a-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3f21a-140">披露分數</span><span class="sxs-lookup"><span data-stu-id="3f21a-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="3f21a-141">API</span><span class="sxs-lookup"><span data-stu-id="3f21a-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)