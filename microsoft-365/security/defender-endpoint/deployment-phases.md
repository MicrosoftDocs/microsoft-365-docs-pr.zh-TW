---
title: 部署階段
description: 瞭解如何在服務中準備、設定和上架端點來部署 Microsoft Defender for Endpoint
keywords: deploy，prepare，setup，板載，階段，部署，部署，採用，設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165162"
---
# <a name="deployment-phases"></a>部署階段

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

瞭解如何部署 Microsoft Defender for Endpoint，使您的企業能夠利用預防性防護、入侵後偵測、自動調查和回應。 


本指南可協助您在不同的專案關係人上運作，以系統方式準備您的環境，然後以系統方式從評估移至有意義的試驗，以進行完整部署。

每一節都對應此方案中的個別文章。

![包含資料表詳細資料的部署階段映射](images/deployment-guide-phases.png)


![部署階段摘要： prepare、setup、板載](images/phase-diagrams/deployment-phases.png)

|階段 | 描述 | 
|:-------|:-----|
| [階段 1：準備](prepare-deployment.md)| 深入瞭解部署 Defender （如專案關係人核准、環境考慮、存取權及功能採用順序）時，您需要考慮的事項。 
| [階段 2：設定](production-deployment.md)|  取得您必須採取之初始步驟的指導方針，讓您可以存取入口網站，例如驗證授權、完成安裝精靈及網路設定。 
| [第 3 階段：導入](onboarding.md) | 瞭解如何使用部署環、根據端點類型所支援的內架工具，以及設定可用的功能。 


當您完成本指南後，您將會使用正確的存取權限進行安裝，而您的端點將會架並報告感應器資料給服務，而下一代保護和攻擊面降低等功能將會就地實施。



不論 [規劃部署](deployment-strategy.md) 指導中所選擇的環境架構和部署方法為何，本指南都將為您提供上架端點的支援。 








## <a name="key-capabilities"></a>主要功能

雖然 Microsoft Defender for Endpoint 提供許多功能，但此部署指南的主要目的是讓您開始使用上架裝置。 除了上架之外，本指南也可讓您開始使用下列功能。



功能 | 描述 
:---|:---
端點偵測及回應 | 端點偵測和回應功能可就地偵測、調查和回應入侵嘗試和主動違例。
新一代保護 | 若要進一步鞏固網路的安全性周邊，Microsoft Defender for Endpoint 會使用下一代保護，以捕捉所有類型的新威脅。
攻擊面縮小 |  在堆疊中提供第一項防護。 透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。

所有這些功能均可供 Microsoft Defender for Endpoint 授權擁有者使用。 如需詳細資訊，請參閱 [授權要求](minimum-requirements.md#licensing-requirements)。

## <a name="scope"></a>範圍

### <a name="in-scope"></a>在範圍內

-   使用 Microsoft 端點管理員和 Microsoft 端點管理員上架端點至服務和設定功能

-   啟用 (EDR) 功能的 Defender endpoint endpoint 偵測和回應

-   啟用適用于 Endpoint endpoint protection 平臺的 Defender (EPP) 功能

    -   新一代保護

    -   攻擊面縮小


### <a name="out-of-scope"></a>超出範圍

下列專案不在本部署指南的範圍內：

-   設定可能與 Defender for Endpoint 整合的協力廠商解決方案

-   實際執行環境中的滲透測試




## <a name="see-also"></a>另請參閱
- [階段 1：準備](prepare-deployment.md)
- [階段 2：設定](production-deployment.md)
- [第 3 階段：導入](onboarding.md)
- [規劃部署](deployment-strategy.md)