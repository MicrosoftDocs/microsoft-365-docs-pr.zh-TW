---
title: Contoso 公司概觀
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 公司的業務及其全球辦公室的分層架構。
ms.openlocfilehash: 856363881c749b06a530dc7cc4f0eb82dc155054
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068292"
---
# <a name="overview-of-the-contoso-corporation"></a>Contoso 公司概觀

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

Contoso 公司是一家跨國企業，總部設於法國巴黎。它是一家集製造、銷售與支援的集團，旗下商品超過 100,000 種。

## <a name="contoso-around-the-world"></a>世界各地的 Contoso

圖 1 顯示在巴黎的總部和其他跨洲的地區中心及衛星辦公室。

![世界各地的 Contoso 辦公室](../media/contoso-overview/contoso-overview-fig1.png)

**圖 1：世界各地的 Contoso 辦公室**
 
Contoso 辦公室皆依照下列三層式架構設計。

- 總部

  Contoso 公司總部是個位於巴黎郊區的大型園區，園區中有多座建築物做為行政、工程和生產設施之用。所有 Contoso 的資料中心及其網際網路呈現設施均位於巴黎總部。

  總部共有 25,000 名員工。

- 地區中心

  地區中心辦公室主要服務全球特定區域 60% 的銷售和支援人員。每個地區中心均透過高頻寬 WAN 連結連線至巴黎總部。

  每個地區中心平均有 2,000 名員工。

- 衛星辦公室

  衛星辦公室容納 80% 的銷售與支援人員，負責為主要城市或分區的 Contoso 客戶提供現場服務，每個衛星辦公室均透過高頻寬 WAN 連結連線至地區中心。

  每個衛星辦公室平均有 250 名員工。

25% 的 Contoso 員工屬於行動工作者，當中又以地區中心和衛星辦公室的行動工作者人數佔較高的百分比。為行動工作者提供較完善的支援是 Contoso 的一項重要業務目標。 

## <a name="design-considerations-for-microsoft-365-enterprise"></a>Microsoft 365 企業版的設計考量

Contoso 的 IT 架構識別在部署 Microsoft 365 企業版時的以下設計需求和考量： 

- 多個地理位置與其須遵守的當地法規及規範
- 在總部辦公室的中央內部資料中心和地區應用程式伺服器中，裝載內部業務應用程式
- 現有的 Microsoft Endpoint Configuration Manager 基礎架構
- 混合的用戶端電腦裝置，包括 Windows、Mac 和 Linux
- 混合的個人及公司行動裝置，包括 iOS (iPhone 和 iPad)、Android 智慧型手機及平板電腦
- 為數眾多的遠端和行動工作者
- 為數眾多的事業夥伴
- 數量龐大的客戶及個人識別資訊
- 數量龐大的高價值產品設計規格智慧財產及製造交易秘密

## <a name="next-step"></a>下一步

[深入了解](contoso-infra-needs.md) Contoso 公司的內部部署 IT 基礎架構，以及 Microsoft 365 企業版如何解決其業務需求。

## <a name="see-also"></a>請參閱

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)



