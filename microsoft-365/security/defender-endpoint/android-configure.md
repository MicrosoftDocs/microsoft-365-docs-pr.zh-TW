---
title: 設定 Android 版適用於端點的 Microsoft Defender 功能
description: 說明如何為 Android 設定 Microsoft Defender for Endpoint
keywords: microsoft、defender、atp、mde、android、configuration
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
ms.openlocfilehash: c395aafc8a468cfdeaea973ab02421212870192a
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587212"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="2f90f-104">為 Android 功能設定 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f90f-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f90f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f90f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f90f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f90f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f90f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f90f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="2f90f-108">使用適用于 Android 的 Defender for Endpoint 的條件式存取</span><span class="sxs-lookup"><span data-stu-id="2f90f-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="2f90f-109">適用于 Android 的 microsoft Defender Endpoint 及 Microsoft Intune 和 Azure Active Directory 可根據裝置風險層級強制實施裝置合規性和條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="2f90f-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="2f90f-110">Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。</span><span class="sxs-lookup"><span data-stu-id="2f90f-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="2f90f-111">如需如何設定適用于 Android 和條件式存取的 Defender 端點的詳細資訊，請參閱 [Defender For Endpoint And Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="2f90f-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="2f90f-112">設定自訂指示器</span><span class="sxs-lookup"><span data-stu-id="2f90f-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="2f90f-113">適用于 Android 的 Defender 僅支援為 IP 位址和 URLs/網域建立自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="2f90f-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="2f90f-114">適用于 Android 的 Defender，可讓系統管理員設定自訂指示器，以支援 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="2f90f-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="2f90f-115">如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="2f90f-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="2f90f-116">設定 web 保護</span><span class="sxs-lookup"><span data-stu-id="2f90f-116">Configure web protection</span></span>
<span data-ttu-id="2f90f-117">適用于 Android 的 Defender Endpoint 允許 IT 管理員設定 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="2f90f-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="2f90f-118">這項功能可在 Microsoft 端點管理員系統管理中心內使用。</span><span class="sxs-lookup"><span data-stu-id="2f90f-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="2f90f-119">適用于 Android 的 Defender for Android 會使用 VPN，以便提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="2f90f-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="2f90f-120">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="2f90f-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="2f90f-121">如需詳細資訊，請參閱 [在執行 Android 的裝置上設定 web 保護](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。</span><span class="sxs-lookup"><span data-stu-id="2f90f-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f90f-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f90f-122">Related topics</span></span>
- [<span data-ttu-id="2f90f-123">Android 版適用於端點的 Microsoft Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="2f90f-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="2f90f-124">使用 Microsoft Intune 部署 Android 版適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f90f-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)