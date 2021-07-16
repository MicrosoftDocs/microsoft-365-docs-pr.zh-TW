---
title: 查看 Microsoft Defender 的端點架構需求和重要概念
description: 在 Microsoft 365 Defender 中，Microsoft Defender for Endpoint 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457817"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>查看 Microsoft Defender 的端點架構需求和重要概念

**適用于：** Microsoft 365 Defender

本文將引導您在設定 Microsoft Defender for Endpoint 環境評估的過程中。

如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-endpoint-overview.md)。

啟用 Microsoft Defender for Endpoint 之前，請確定您瞭解架構，並且可以符合需求。

## <a name="understand-the-architecture"></a>了解架構

下圖說明用於端點架構和整合的 Microsoft Defender。 

![將 Microsoft defender for Office 新增至 Defender 評估環境的步驟](../../media/defender/m365-defender-endpoint-architecture.png)

下表說明圖例。

撥出 | 說明
:---|:---|
1 | 透過其中一個支援的管理工具來 boarded 裝置。 
2  | Boarded 裝置會提供 Microsoft Defender for Endpoint 信號資料，並加以回應。
3  | 受管理的裝置會在 Azure Active Directory 中加入和/或註冊。
4  | 加入網域的 Windows 10 裝置會使用 Azure Active Directory 連線同步處理至 Azure Active Directory。
5  | Microsoft Defender for Endpoint 警示、調查和回應是在 Microsoft 365 Defender 中管理。

## <a name="understand-key-concepts"></a>瞭解重要概念

下清單格識別重要概念，在評估、設定及部署 Microsoft Defender for Endpoint 時，重要概念非常重要： 

概念 | 描述 | 其他資訊
:---|:---|:---|
管理入口網站 | Microsoft 365 Defender 入口網站，以監視及協助回應潛在的持續威脅活動或資料違例的警示。 | [Microsoft Defender for Endpoint 入口網站概述](/defender-endpoint/portal-overview)
攻擊面減少 | 將您的組織容易遭受 cyberthreats 和攻擊的位置降到最低，協助減少攻擊面。 | [攻擊面縮小概觀](/defender-endpoint/overview-attack-surface-reduction)
端點偵測和回應 | 端點偵測和回應功能提供接近即時及可行動的高級攻擊偵測。 | [端點偵測和回應功能的概覽](/defender-endpoint/overview-endpoint-detection-response)
行為封鎖和包容 | 行為封鎖和包容功能可在威脅已開始執行時，根據其行為和程式樹，協助識別及停止威脅。 | [行為封鎖和包含專案](/defender-endpoint/behavioral-blocking-containment)
自動化調查和回應 | 自動調查使用各種檢查演算法，取決於安全分析員所使用的處理常式，並設計用來檢查提醒並立即採取動作來解決違規行為。 | [使用自動調查以調查和修正威脅](/defender-endpoint/automated-investigations)
進階搜捕 | 「高級搜尋」是查詢型威脅搜尋工具，可讓您探索最多30天的原始資料，使您能夠主動檢查網路中的事件，以找出威脅指示器和實體。 | [高級搜尋一覽](/defender-endpoint/advanced-hunting-overview)
威脅分析 | 威脅分析是一組來自專家 Microsoft 安全性研究人員的報表，涵蓋最相關的威脅。 | [追蹤並回應新興威脅](/defender-endpoint/threat-analytics)


如需 Microsoft Defender for Endpoint 隨附之功能的詳細資訊，請參閱 [什麼是 Microsoft defender For endpoint](/defender-endpoint/microsoft-defender-endpoint)。

## <a name="siem-integration"></a>SIEM 整合

您可以整合 Microsoft Defender for Endpoint with Azure Sentinel，以更全面地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。 

Microsoft Defender for Endpoint 也可以整合到其他安全性資訊和事件管理 (SIEM) 解決方案。 如需詳細資訊，請參閱 [ENABLE SIEM integration In Microsoft Defender For Endpoint](/defender-endpoint/enable-siem-integration)。


## <a name="next-steps"></a>後續步驟
[啟用評估](eval-defender-endpoint-enable-eval.md)

回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述