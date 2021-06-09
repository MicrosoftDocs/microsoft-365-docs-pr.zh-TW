---
title: Contoso Corporation 的概覽
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 公司的業務及其全球辦公室的分層架構。
ms.openlocfilehash: b0c00ed5657d914851f28278a2f4cf80660b53b0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754265"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation 的概覽

Contoso Corporation 是其總部在巴黎的跨國企業。 公司是含100000以上產品的製造業、sales 和 support 組織。

## <a name="contoso-around-the-world"></a>世界各地的 Contoso

圖1顯示巴黎和地區性 hub 中的總部辦公室和各大陸的衛星辦公室。

![世界各地的 Contoso 辦事處](../media/contoso-overview/contoso-overview-fig1.png)

**圖1：世界各地的 Contoso 辦事處**
 
Contoso 有三個層級：

- Headquarters

  Contoso 總部是巴黎 outskirts 的公司校園，具有數十個大樓，以供管理、工程及製造設施使用。 所有 Contoso 資料中心及其網際網路目前狀態皆位於巴黎總部。

  總部共有 25,000 名員工。

- 地區中心

  Hub 分公司使用60的銷售及支援人員，為全球的特定地區提供服務。 每個區域中樞都透過高頻寬 WAN 連結連線至巴黎總部。

  地區中心的平均人數為2000工作者。

- 衛星辦公室

  衛星辦公室包含80% 的銷售和支援人員。 它們為 Contoso 客戶在重要城市或 subregions 中提供現場顯示狀態。 每個衛星辦公室都透過高頻寬的 WAN 連結連線至區域中樞。

  衛星辦公室的平均為250工作者。

大約25% 的 Contoso 工作力是僅限行動裝置。 地區中樞和衛星辦公室的工作人數會高出的百分比。 針對僅限行動工作者提供更好的支援是 Contoso 的重要業務目標。

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>Microsoft 365 企業版的設計考慮

Contoso IT 架構師發現下列為企業版部署 Microsoft 365 的設計需求因素：

- 多個地理位置與其須遵守的當地法規及規範
- 在總部辦公室和地區性應用程式伺服器中，主控內部企業營運應用程式的中央內部網路資料中心
- 現有的 Microsoft Endpoint Configuration Manager 基礎架構
- 混合執行 Windows、Mac 和 Linux 的用戶端計算裝置
- 混合的個人及公司行動裝置，包括 iOS (iPhone 和 iPad)、Android 智慧型手機及平板電腦
- 為數眾多的遠端和行動工作者
- 為數眾多的事業夥伴
- 大量客戶和其他機密個人資訊以管理和保護
- 數量龐大的高價值產品設計規格智慧財產及製造交易秘密

## <a name="next-step"></a>下一步

深入瞭解 Contoso Corporation 的[內部部署 IT 基礎結構](contoso-infra-needs.md)，以及公司的 Microsoft 365 如何以企業的方式來解決公司的業務需求。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
