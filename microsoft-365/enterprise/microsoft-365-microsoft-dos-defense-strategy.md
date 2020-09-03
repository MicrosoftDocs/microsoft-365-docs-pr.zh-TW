---
title: Microsoft 365 拒絕服務防護策略
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您可以找到針對拒絕服務 (DoS) 攻擊的 Microsoft 防護策略的概述。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3fc436dfe8a63575c8bbeefeed0653c329780247
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332277"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Microsoft 365 拒絕服務防護策略

針對以網路為基礎的拒絕服務 (DoS) 攻擊的 Microsoft 策略，是由於我們的規模和全域空間的不同而有獨特的。 這項規模可讓 Microsoft 利用策略及技術，而不是組織、提供者或客戶組織可以比對。 DoS 策略的基石是我們的全球平臺。 Microsoft 與網際網路提供者、對等提供者 (公開和私營) ，以及世界各地的私營公司。 這為 Microsoft 提供大量的網際網路服務，讓 Microsoft 能夠吸收跨越大型 surface 區域的攻擊。

在此獨特的情況下，Microsoft 會使用不同于大型企業所使用的偵測和緩解處理常式。 策略是以透過許多網路邊緣的偵測和全域分散式緩解的方式來隔離。 許多企業使用協力廠商解決方案來偵測並減輕 edge 的攻擊。 隨著 Microsoft 的 edge 容量增加，它會明確針對個別或特定邊界的任何攻擊，都是很低的意義。 由於這項獨特的設定，Microsoft 會以偵測和緩解元件為依據。 Microsoft 部署多層偵測系統，以偵測其飽和點較接近的攻擊，同時維持 edge 的全域緩解。 此策略可確保我們可以處理多個同時進行的攻擊。

Microsoft 對 DoS 攻擊所採用的最有效且低成本的防禦措施之一，是減少服務攻擊面。 不需要的流量會在網路 edge 中斷，而不會分析、處理及清理資料內聯。

在使用公用網路的介面上，Microsoft 會針對防火牆、網路位址轉譯和 IP 篩選功能使用特殊用途的安全性裝置。 Microsoft 也會使用全域同等成本的多重路徑 (ECMP) 路由。 全域 ECMP 路由是一個網路架構，可確保有多個通用路徑可以到達服務。 透過這些多重路徑，針對服務的攻擊會限制在發起攻擊的地區。 其他地區應該會受到這項攻擊的影響，因為使用者會使用其他路徑來到達這些地區的服務。 Microsoft 也已開發內部 DoS 的關聯性和偵測系統，使用流程資料、效能度量及其他資訊。 這是 Microsoft Azure 中的超大型雲端服務，可分析從 Microsoft 網路和服務上的各點收集的資料。 跨工作負載 DoS 事件回應小組識別各小組的角色與責任、升級的準則，以及用來吸引各小組和事件處理的通訊協定。 這些解決方案提供網路型防護，以防範 DoS 攻擊。

最後，以雲端架構為基礎的工作負載會根據其通訊協定和頻寬使用方式來設定優化的門限，以唯一保護該工作負載。
