---
title: 在 Android 上設定適用於端點的 Microsoft Defender 功能
description: 說明如何在 Android 上設定 Microsoft Defender for Endpoint
keywords: microsoft、defender、Microsoft Defender for Endpoint、mde、android、configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841335"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="99678-104">設定 Android 功能上的 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99678-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99678-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="99678-105">**Applies to:**</span></span>
- [<span data-ttu-id="99678-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="99678-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99678-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99678-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="99678-108">在 Android 上使用 Defender for Endpoint 進行條件式存取</span><span class="sxs-lookup"><span data-stu-id="99678-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="99678-109">Android 上的 Microsoft Defender for Endpoint 和 Microsoft Intune 和 Azure Active Directory 可根據裝置風險層級強制實施裝置合規性和條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="99678-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="99678-110">Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。</span><span class="sxs-lookup"><span data-stu-id="99678-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="99678-111">如需如何在 Android 和條件式存取上為端點設定 Defender 的詳細資訊，請參閱 [適用于 endpoint 和 Intune 的 defender](/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="99678-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="99678-112">設定自訂指示器</span><span class="sxs-lookup"><span data-stu-id="99678-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="99678-113">Android 上的 Defender for Endpoint 只支援為 IP 位址和 URLs/網域建立自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="99678-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="99678-114">Android 上的 Defender for Android 可讓系統管理員設定自訂指示器，以同時支援 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="99678-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="99678-115">如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="99678-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="99678-116">設定 web 保護</span><span class="sxs-lookup"><span data-stu-id="99678-116">Configure web protection</span></span>
<span data-ttu-id="99678-117">Android 上的 Defender for Android 可讓 IT 管理員設定 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="99678-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="99678-118">這項功能可在 Microsoft 端點管理員系統管理中心內取得。</span><span class="sxs-lookup"><span data-stu-id="99678-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="99678-119">Android 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="99678-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="99678-120">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="99678-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="99678-121">如需詳細資訊，請參閱 [在執行 Android 的裝置上設定 web 保護](/mem/intune/protect/advanced-threat-protection-manage-android)。</span><span class="sxs-lookup"><span data-stu-id="99678-121">For more information, see [Configure web protection on devices that run Android](/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="99678-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="99678-122">Related topics</span></span>
- [<span data-ttu-id="99678-123">Android 上適用於端點的 Microsoft Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="99678-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="99678-124">在 Android 上使用 Microsoft Intune 部署適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="99678-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
