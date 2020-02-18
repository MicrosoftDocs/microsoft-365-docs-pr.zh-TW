---
title: 步驟 5：最佳化用戶端和 Office 365 服務效能
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 設定 TCP 設定與 Office 365 服務以獲得更佳效能。
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066539"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>步驟 5：最佳化用戶端和 Office 365 服務效能

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![階段 1 - 網路](../media/deploy-foundation-infrastructure/networking_icon-small.png)

您可以透過微調傳輸控制通訊協定 (TCP) 在用戶端裝置與 Office 365 服務間的運作方式來增加效能。

針對用戶端裝置，您可以變更用戶端裝置上的下列 TCP 設定以最佳化 TCP 效能：

- [TCP 視窗縮放](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/)，因此用戶端裝置可以傳送更多資料，再要求通知
- [TCP 閒置時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/)，因此用戶端裝置可以更有效率地處理開啟的連線
- [TCP 最大區段大小](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/)，所以用戶端裝置可以傳送封包中資料的最大區塊
- [TCP 選擇性通知](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/)，因此用戶端裝置可以更有效率地認知接收資料

針對 Office 365 服務，請參閱這些額外的資源以最佳化效能：

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App for Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step5)。

## <a name="next-step"></a>下一步

[網路基礎結構允出準則](networking-exit-criteria.md)
