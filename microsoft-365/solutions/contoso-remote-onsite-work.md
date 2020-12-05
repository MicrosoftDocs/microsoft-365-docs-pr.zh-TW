---
title: Contoso 的 COVID-19 回應，並支援遠端和現場工作
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
description: 瞭解 Contoso Corporation 如何回應 COVID-19 pandemic，並將其軟體安裝和更新基礎結構用於遠端和現場工作。
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580670"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Contoso 的 COVID-19 回應，並支援遠端和現場工作

Contoso 永遠支援其遠端工作者，該員工是透過巴黎總部的中央 VPN 伺服器來存取內部部署資源。 Contoso 已頒佈所有的遠端工作者為受管理的膝上型電腦。 內部部署工作者會混合使用桌上型電腦和可擕式電腦。

## <a name="contosos-response-to-covid-19"></a>Contoso 對 COVID-19 的回應

使用 COVID-19 pandemic 的 onset，就會突然，但所有重要工作者都是遠端工作者。 Contoso 通過將其員工轉變為在家中運作，並使用 Microsoft 365 雲端服務，透過遠端存取來執行主要活動，以作出回應。

Contoso 擁有位於巴黎總部辦公室的遠端存取 VPN 伺服器，可支援25% 的遠端員工，但快速移動以擴充其遠端存取能力，以支援其工作力的90%。 Contoso 在每個衛星辦公室中部署遠端存取 VPN 伺服器，讓遠端工作者使用地區 close 進入點來存取 Contoso 內部網路。

Contoso 也會更新安裝在膝上型電腦、平板電腦及智慧型電話上分割通道的 VPN 用戶端設定，讓 Office 365 端點的最佳流量已略過 VPN 連線，並且直接透過網際網路傳送。 如需詳細資訊，請參閱 [使用 VPN 分割隧道為遠端使用者優化 Office 365](../enterprise/microsoft-365-vpn-split-tunnel.md)連線。

以下是安裝于巴黎總部及每個衛星辦公室中的 VPN 裝置所產生的設定。 

![Contoso 的 VPN 基礎結構](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

安裝了 VPN 用戶端的遠端工作者會使用 DNS 來尋找地區最接近的 office，並連接到此處安裝的 VPN 裝置。 透過分割隧道，對 Microsoft 365 的流量會將 [優化端點] 直接傳送至地區最接近的 Microsoft 365 網路位置。 其他所有流量都會透過 VPN 連線傳送至 VPN 裝置。

## <a name="contosos-support-for-remote-and-onsite-work"></a>Contoso 對遠端和現場工作的支援

在地區鎖定期間，為了支援大多數的遠端工作者所做的初步變更之後，Contoso 所做的基礎結構變更可支援遠端和現場工作，而工作者可能是：

- Always remote。
- 永遠在現場。
- 現場和遠端的組合。

Microsoft 365 身分識別、安全性和符合性功能是針對零信任而設計，不論使用者及其裝置的位置為何，都能運作。 如需詳細資訊，請參閱 [零信任](https://www.microsoft.com/security/business/zero-trust)。

不過，管理軟體的新安裝和更新取決於裝置的位置，因為安裝的軟體可能來自內部部署或網際網路來源。 Contoso IT 架構設計其新安裝和更新基礎結構，而不是以設備的位置，而是根據工作者的位置。

其指定了兩種裝置類型：專用的內部部署和漫遊。

### <a name="dedicated-on-premises"></a>專用的內部部署

專用的內部部署裝置是一部桌面或伺服器電腦，永遠不會離開 Contoso 內部網路，也不會安裝 VPN 用戶端。 這些內部部署裝置繼續使用 Microsoft 端點設定管理員和其發佈點來安裝及更新 Windows 10、Microsoft 365 應用程式的企業版和 Edge browser。

### <a name="roaming"></a>漫遊

漫遊裝置可以留下 Contoso 內部網路，並包含發給許多 office 工作者的膝上型電腦，以及所有遠端工作者及其他組織所擁有的裝置，例如已安裝 Contoso VPN 用戶端的智慧型電話和平板電腦。 

因為這些裝置可在任何時間連接至網際網路，所以他們會使用 Intune 或其他雲端式服務來安裝及更新 Windows 10、Microsoft 365 應用程式的企業版和 Edge。 它們不使用現有的內部部署 Configuration Manager 發佈點。

這表示漫遊裝置的部分安裝和更新會在 internet 內部部署並聯機至內部網路時進行。 但是，Contoso IT 架構師決定簡易性設定比對網際網路內部網路頻寬的優化更為重要，尤其是當大多數的遠端工作者很少連接至內部網路時。

以下是所產生的基礎結構。

![Contoso 的安裝和更新基礎結構](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

安裝和更新行為是透過讓裝置的電腦帳戶成為其中一個群組的成員來決定：

- OnPremDevices

  裝置上的 Configuration Manager 用戶端使用發佈點來進行安裝和更新。

- RoamingDevices

  Intune 和裝置上的其他設定指定使用 Microsoft 365 網路進行安裝和更新。

## <a name="new-onboarding-process"></a>新的上架過程

針對新的工作人員或資料中心內新伺服器發佈的新專屬內部部署裝置，當工作者登入時，會根據 OnPremDevices 群組中裝置的成員資格，針對 Windows 10、Microsoft 365 應用程式（適用于企業）和 Edge 安裝最新的更新，並安裝內部部署 Configuration Manager 發佈點的最新更新。 完成時，專用的內部部署裝置可供使用，並使用這些發佈點進行持續更新。

針對發佈到新工作者的新遠端裝置，當工作者登入時，裝置會根據其在 RoamingDevices 群組中的成員資格，聯繫 Intune 雲端服務和其他服務，以及安裝最新的更新，以供 Windows 10、Microsoft 365 應用程式的企業版及 Edge 使用。 完成後，遠端裝置即可供使用，並使用已安裝的 VPN 用戶端來存取內部部署資源和 Microsoft 365 網路，以進行持續更新。

## <a name="next-step"></a>下一步

在您的組織中提供[遠端工作者](empower-people-to-work-remotely.md)。
