---
title: 連線到 Office 365 服務的網路裝置的計劃
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 摘要：說明用來連線至 Office 365 之網路容量、WAN 加速器及負載平衡裝置的考慮。
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927497"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>連線到 Office 365 服務的網路裝置的計劃

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*
  
有些網路硬體可能會限制支援的並行會話數目。 對於擁有超過2000使用者的組織，建議他們監視其網路裝置，以確保它們能夠處理其他 Office 365 服務流量。 簡易網路管理通訊協定 (SNMP) 監視軟體可協助您執行這項作業。

本文是 [Office 365 的網路規劃與效能調整](./network-planning-and-performance.md)的一部分。

內部部署外寄網際網路 proxy 設定也會影響用戶端應用程式的 Office 365 服務連線能力。 您也必須設定網路 proxy 裝置，以允許 Microsoft cloud services URLs 和應用程式的連線。 每個組織都不同。 若要瞭解 Microsoft 如何管理此程式以及我們提供的頻寬量，請 [閱讀案例分析](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)。
  
下列商務用 Skype 說明文章具有商務用 Skype 設定的詳細資訊：
  
- [疑難排解系統管理員的商務用 Skype Online 登入錯誤](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [您無法連線至商務用 Skype，或某些功能無法運作，因為內部部署防火牆會封鎖連線](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> 雖然這些設定中有許多是商務用 Skype，但網路設定的一般指導也適用于所有 Office 365 服務。
  
## <a name="determining-network-capacity"></a>決定網路容量

連接上的每個網路裝置都有其容量限制。 這些裝置包含用戶端和伺服器網路介面卡、路由器、交換器，以及與其互連的中樞。 足夠的網路容量表示沒有任何飽和。 監視網路活動非常重要，以協助確保所有網路裝置上的實際負載小於其容量上限。 網路容量會影響 proxy 裝置效能。
  
在大多數情況下，網際網路連線頻寬會設定流量的數量限制。 峰值流量峰值的效能可能是由於過度使用網際網路連結所造成。 這種情況也適用于分公司的分支機搆，在此案例中，分支機搆 proxy 伺服器電腦會透過慢速廣域網路 (WAN) 連結連線到分支總部的 proxy 裝置。
  
若要測試網路容量，請在 proxy 網路介面上監視網路活動。 如果是任何網路介面的最大頻寬超過75%，請考慮增加不充分之網路基礎結構的頻寬。 或者，請考慮使用高級功能（例如 HTTP 壓縮）。
  
## <a name="wan-accelerators"></a>WAN 加速器

如果您的組織使用廣域網路絡 (WAN) 加速 proxy 裝置，當您存取 Office 365 服務時，可能會發生問題。 您可能需要優化網路裝置或裝置，以確保您的使用者在存取 Office 365 時有一致的經驗。 例如，Office 365 服務會加密某些 Office 365 內容和 TCP 標頭。 您的裝置可能無法處理這類流量。
  
如需 [使用 WAN 優化控制器或流量/檢查裝置與 Office 365 的支援聲明，請](https://support.microsoft.com/kb/2690045)參閱。
  
## <a name="hardware-and-software-load-balancing-devices"></a>硬體與軟體負載平衡裝置

您的組織必須使用硬體負載平衡器 (HLB) 或網路負載平衡 (NLB) 解決方案，將要求散佈至 Active Directory Federation Services (AD FS) 伺服器和（或） Exchange 混合伺服器。 負載平衡裝置可控制內部部署伺服器的網路流量。 這些伺服器對於協助確保單一登入與 Exchange 混合式部署的可用性非常重要。
  
我們提供 Windows Server 內建的軟體型 NLB 解決方案。 Office 365 支援此解決方案，以達到負載平衡。
  
## <a name="firewalls-and-proxies"></a>防火牆和代理

如需設定防火牆和代理伺服器以連線至 Office 365 的詳細資訊，請參閱 [管理 office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)、 [評估 Office 365 網路](assessing-network-connectivity.md)連線，以及 [office 365 端點常見問題](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) 以深入瞭解裝置和電路選項。
  
## <a name="see-also"></a>另請參閱

[Office 365 服務的安裝指南](setup-guides-for-microsoft-365.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)