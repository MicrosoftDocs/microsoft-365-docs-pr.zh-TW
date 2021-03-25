---
title: 設定適用于 Android 功能的 Microsoft Defender ATP
description: 說明如何設定適用于 Android 的 Microsoft Defender ATP
keywords: microsoft、defender、atp、android、configuration
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163444"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>為 Android 功能設定 Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>使用適用于 Android 的 Defender for Endpoint 的條件式存取  
適用于 Android 的 microsoft Defender Endpoint 及 Microsoft Intune 和 Azure Active Directory 可根據裝置風險層級強制實施裝置合規性和條件式存取原則。 Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。

如需如何設定適用于 Android 和條件式存取的 Defender 端點的詳細資訊，請參閱 [Defender For Endpoint And Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。

## <a name="configure-custom-indicators"></a>設定自訂指示器  

> [!NOTE]
> 適用于 Android 的 Defender 僅支援為 IP 位址和 URLs/網域建立自訂指示器。

適用于 Android 的 Defender，可讓系統管理員設定自訂指示器，以支援 Android 裝置。 如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](manage-indicators.md)。

## <a name="configure-web-protection"></a>設定 web 保護
適用于 Android 的 Defender Endpoint 允許 IT 管理員設定 web 保護功能。 這項功能可在 Microsoft 端點管理員系統管理中心內使用。

> [!NOTE]
> 適用于 Android 的 Defender for Android 會使用 VPN，以便提供 Web 保護功能。 這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。 如需詳細資訊，請參閱 [在執行 Android 的裝置上設定 web 保護](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="related-topics"></a>相關主題
- [適用于 Android 的 Microsoft Defender 端點簡介](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 部署適用于 Android 的 Microsoft Defender 端點](android-intune.md)
