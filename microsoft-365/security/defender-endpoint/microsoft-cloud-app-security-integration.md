---
title: Microsoft Cloud App Security 整合概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 會透過轉送所有雲端 app 網路活動，與 Cloud App 安全性整合。
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
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185596"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Defender for Endpoint 中的 Microsoft Cloud App Security 簡介

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) 是一種全面的解決方案，可讓您控制和限制雲端應用程式的存取，同時也會在雲端儲存的資料上強制執行規范的需求。 如需詳細資訊，請參閱 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

>[!NOTE]
>在執行 Windows 10 版本1809或更新版本的裝置上，使用 [企業行動](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 裝置和安全性的 E5 授權可取得此功能。

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint 和 Cloud App Security 整合 

雲端應用程式安全性探索依賴從企業防火牆和 proxy 伺服器轉寄的雲端流量記錄。 Microsoft Defender for Endpoint 會透過收集和轉寄所有雲端應用程式網路活動，以與雲端 App 安全性整合，以提供 Cloud app 使用狀況的無與倫比的洞察力。 監視功能是內置於裝置中，可提供完整的網路活動範圍。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


整合針對現有的雲端應用程式安全性探索提供下列重大改進： 

- 隨處可用-因為網路活動是直接從端點收集，所以不論是在公司網路上，還是在公司網路上，只要該裝置不再是透過企業防火牆或 proxy 伺服器路由傳送的流量，便可使用。 

- 可在盒外運作，不需要設定將雲端流量記錄送出至 Cloud App 安全性需要防火牆和 proxy 伺服器設定。 使用 Defender for Endpoint 和 Cloud App Security 整合，不需要進行任何設定。 只要在 Microsoft Defender 安全性中心設定中切換，您就可以繼續。 

- 裝置內容-Cloud 流量記錄檔缺乏裝置內容。 Defender for Endpoint network activity 會以裝置內容來報告 (哪些裝置存取雲端 app) ，因此您可以完全瞭解 (裝置) 網路活動的位置，以及 (使用者) 執行它的情況。 

如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>相關主題

- [設定 Microsoft Cloud App Security 整合](microsoft-cloud-app-security-config.md)
