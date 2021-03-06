---
title: 保護您的組織免受網頁威脅
description: 深入瞭解 Microsoft Defender for Endpoint 中的 web 保護，以及它如何保護您的組織。
keywords: 網頁防護，網頁威脅防護，網頁流覽，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688942"
---
# <a name="protect-your-organization-against-web-threats"></a>保護您的組織免受網頁威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 威脅防護是用於端點之 [web 保護](web-protection-overview.md) 的一部分。 它會使用 [網路保護](network-protection.md) 來保護您的裝置免受網頁威脅。 透過與 Microsoft Edge 和流行的協力廠商瀏覽器（如 Chrome 和 Firefox）整合，web 威脅防護會停止網頁 proxy 以外的網頁威脅，並在使用者離開或內部部署時，保護裝置。 Web 威脅防護會停止存取網路釣魚網站、惡意程式碼向量、exploit 網站、不信任或低信譽網站，以及您在 [自訂指示器清單](manage-indicators.md)中封鎖的網站。

>[!Note]
>裝置接收新的自訂指示器時，最多可能需要一小時。

## <a name="prerequisites"></a>必要條件
Web 保護使用網路保護，在 Microsoft Edge 和協力廠商網頁瀏覽器上提供 web 流覽安全性。

開啟裝置上的網路保護：
- 在 [ **Web & 網路保護** ] 底下編輯端點的「安全性基準」，以在部署或重新部署之前啟用網路保護。 [瞭解如何檢查和指派用於端點安全性基準的 Defender](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- 使用 Intune 裝置設定、SCCM、群組原則或 MDM 解決方案開啟網路保護。 [進一步閱讀啟用網路保護的資訊](enable-network-protection.md)  

>[!Note]
>若您將網路保護設定為 **僅供審核**，封鎖將無法使用。 此外，您也可以偵測和記錄只在 Microsoft Edge 上存取惡意和有害網站的嘗試。

## <a name="related-topics"></a>相關主題

- [Web 保護概觀](web-protection-overview.md)
- [網頁威脅防護](web-threat-protection.md)
- [監視 Web 安全性](web-protection-monitoring.md)
- [回應 Web 威脅](web-protection-response.md)
- [網路保護](network-protection.md)
