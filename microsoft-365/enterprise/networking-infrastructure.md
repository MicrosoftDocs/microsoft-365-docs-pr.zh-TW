---
title: 階段 1：Microsoft 365 企業版的網路基礎結構
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版網路基礎結構的部署步驟。
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982794"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>階段 1：Microsoft 365 企業版的網路基礎結構

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 企業版包括 Office 365、Microsoft Intune 和許多 Microsoft Azure 的身分識別和安全性服務。 這些所有雲端服務都依賴透過網際網路或專用線路從用戶端裝置連線的安全性、效能及可靠性。 為了裝載這些服務並且讓世界各地的客戶使用，Microsoft 設計了強調效能和整合的網路基礎結構。 

在這個階段，您會逐步探討對 Microsoft 365 企業版雲端服務建立更具效能的連線之關鍵考量。如需概觀，請參閱 [Office 365 網路原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

>[!Note]
>如果您已部署網路基礎結構，請參閱此階段的[允出準則](networking-exit-criteria.md)，確保其符合 Microsoft 365 企業版的必要與選用條件。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>規劃及部署 Microsoft 365 企業版的網路基礎結構 

使用下列步驟為 Microsoft 365 企業版的需求和功能建立您的網路基礎結構。

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[準備用於 Microsoft 365 的網路](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[設定每個辦公室的當地網際網路連線](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[避免網路 hairpin](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[設定流量旁路](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[最佳化用戶端和 Office 365 服務效能](networking-optimize-tcp-performance.md)|


完成這些步驟之後，請移至此階段的[允出準則](networking-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

一窺 Microsoft IT 內部，並了解公司如何[針對雲端服務最佳化 Microsoft 網路](https://www.microsoft.com/zh-TW/itshowcase/deploying-and-managing-microsoft-365#primaryR4)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

看看 Contoso Corporation (虛構但具代表性的跨國企業) 如何為 Microsoft 365 雲端服務[最佳化其網路裝置和網際網路連線](contoso-networking.md)。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>後續步驟

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[準備用於 Microsoft 365 的網路](networking-provide-bandwidth-cloud-services.md)|

