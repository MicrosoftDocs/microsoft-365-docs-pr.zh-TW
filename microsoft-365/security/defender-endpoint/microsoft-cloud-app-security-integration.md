---
title: Microsoft Cloud App Security 整合概觀
ms.reviewer: ''
description: Microsoft Defender for Endpoint 會透過轉送所有雲端 App 網路活動，與雲端 App 安全性整合。
keywords: 雲端，應用程式，網路，可視性，使用
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844739"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>在 Defender for Endpoint 中 Microsoft Cloud App Security 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (雲端 App 安全性) 是一種全面的解決方案，可讓您控制和限制雲端應用程式的存取，同時也會在雲端中儲存的資料上強制執行規范的需求。 如需詳細資訊，請參閱[雲端 App 安全性](/cloud-app-security/what-is-cloud-app-security)。

>[!NOTE]
>您可以在執行 Windows 10 版本1809或更新版本的裝置上，使用[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) E5 授權的此功能。

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for 端點和雲端 App 安全性整合 

雲端 App 安全性探索取決於雲端流量記錄會從企業防火牆和 proxy 伺服器轉寄給它。 Microsoft Defender for Endpoint 會收集及轉送所有雲端應用程式網路活動，以整合與雲端 App 安全性，提供雲端應用程式使用狀況的無與倫比的洞察力。 監視功能是內置於裝置中，可提供完整的網路活動範圍。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


整合針對現有的雲端 App 安全性探索提供下列主要改進： 

- 隨處可用-因為網路活動是直接從端點收集，所以不論是在公司網路上，還是在公司網路上，只要該裝置不再是透過企業防火牆或 proxy 伺服器路由傳送的流量，便可使用。 

- 可在盒外運作，不需要將雲端流量記錄轉送至雲端 App 安全性需要防火牆和 proxy 伺服器設定。 使用 Defender for Endpoint 和雲端 App 安全性整合時，不需要進行任何設定。 只要在 Microsoft Defender 資訊安全中心設定中切換，您就可以繼續。 

- 裝置內容-Cloud 流量記錄檔缺乏裝置內容。 Defender for Endpoint network activity 會以裝置內容來報告 (哪些裝置存取雲端 app) ，因此您可以完全瞭解 (裝置) 網路活動的位置，以及 (使用者) 執行它的情況。 

如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>相關主題

- [設定 Microsoft Cloud App Security 整合](microsoft-cloud-app-security-config.md)
