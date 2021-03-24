---
title: Web 保護
description: 深入瞭解 Microsoft Defender ATP 中的 web 保護，以及它如何保護您的組織
keywords: web 保護、網頁威脅防護、網頁流覽、安全性、網路釣魚、惡意程式碼、利用方式、網站、網路保護、Edge、Internet Explorer、Chrome、Firefox、網頁瀏覽器、惡意網站
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: efddd646af609200708c5fd6d2e8b27211bd7021
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058108"
---
# <a name="web-protection"></a>Web 保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Microsoft Defender for Endpoint 中的 Web 保護是由 [web 威脅防護](web-threat-protection.md) 和 [web 內容篩選](web-content-filtering.md)所組成的功能。 Web 保護功能可讓您保護裝置免受網頁威脅，並協助您控制不想要的內容。 您可以在 Microsoft Defender Security Center 中尋找 Web 保護報告，以 **> web 保護的報表**。

![所有 web 保護卡的影像](images/web-protection.png)

## <a name="web-threat-protection"></a>網頁威脅防護

組成網頁威脅防護的卡片是一段時間和 **網頁威脅摘要** 中的 **web 威脅** 偵測。

網頁威脅防護包括：
- 深入瞭解影響組織的 web 威脅
- 透過透過網路相關之威脅活動的功能和 URLs 及可存取這些 URLs 裝置的綜合設定檔，調查功能
- 一組完整的安全性功能，可追蹤對惡意及有害網站的一般存取趨勢

## <a name="web-content-filtering"></a>Web 內容篩選

組成 web 內容篩選的卡片是依類別、**網頁內容篩選摘要** 及 **網頁活動摘要** 的 **web 活動**。

Web 內容篩選包括：
- 使用者無法存取封鎖類別中的網站，不論他們流覽內部部署或離開
- 您可以使用[Microsoft Defender For Endpoint role 的存取控制設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)中所定義的裝置群組，輕鬆地將不同的原則部署至不同的使用者群組
- 您可以在相同的中央位置存取 web 報表，並透過實際區塊和 web 使用狀況進行查看

## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
[網頁威脅防護](web-threat-protection.md) | 停止存取網路釣魚網站、惡意程式碼向量、exploit 網站、不信任或低信譽網站，以及您已封鎖的網站。
[Web 內容篩選](web-content-filtering.md) | 根據網站的內容類別別，追蹤和控制網站的存取權。
