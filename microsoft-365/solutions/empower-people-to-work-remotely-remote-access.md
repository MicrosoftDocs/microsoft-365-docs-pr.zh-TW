---
title: 步驟 2： 可遠端存取內部部署應用程式和服務
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/27/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 請確保您的遠端工作者能夠存取內部部署資源，同時將 Microsoft 365 雲端服務的存取最佳化。
ms.openlocfilehash: 199dc6aa33134cfa0f9ac311d037a934c12ba3b9
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844975"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>步驟 2： 可遠端存取內部部署應用程式和服務

如果貴組織使用遠端存取 VPN 解決方案 (通常 VPN 伺服器安裝在網路的邊緣，而 VPN 用戶端則安裝在使用者的裝置上)，您的使用者就可以使用遠端存取 VPN 連線存取內部部署應用程式和伺服器。 但您可能需要將 Microsoft 365 雲端服務的流量最佳化。

如果您的使用者沒有使用 VPN 解決方案，您可以使用 Azure Active Directory (Azure AD) 應用程式 Proxy 和 Azure 點對站台 (P2S) VPN 提供存取權，端視您所有的應用程式是否為 Web 架構而定。

有三種主要設定：

1. 您已經在使用遠端存取 VPN 解決方案。
2. 您沒有使用遠端存取 VPN 解決方案、您有混合式身分識別，而且您只需要遠端存取內部部署的 Web 架構應用程式。
3. 您沒有使用遠端存取 VPN 解決方案、您需要存取內部部署應用程式，而且其中部分應用程式並非 Web 架構。

請參閱此流程圖，了解本文所述的遠端存取設定選項。

![遠端存取設定流程圖](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

使用遠端存取連線時，您也可以使用[遠端桌面](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)，將您的使用者連線到內部部署電腦。 例如，遠端工作者可以從 Windows、iOS 或 Android 裝置，使用遠端桌面連線到其辦公室中的電腦。 從遠端連線之後，他們就可以像坐在電腦前面一樣使用電腦。

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>針對 Microsoft 365 雲端服務，將遠端存取 VPN 用戶端的效能最佳化

如果您的遠端工作者使用傳統的 VPN 用戶端取得貴組織網路的遠端存取權，請確認 VPN 用戶端支援分割通道。

如果沒有分割通道，您所有的遠端工作流量都會透過 VPN 連線傳送，其中必須先將流量轉送給貴組織的邊緣裝置、進行處理，然後透過網際網路傳送。

![來自 VPN 用戶端的網路流量 (不含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Microsoft 365 流量必須透過貴組織進行間接路由，這可能是從距離 VPN 用戶端實體位置很遠的位置轉送到 Microsoft 網路進入點。 這種間接路徑可增加網路流量的延遲，並降低整體效能。 

您可以利用分割通道設定 VPN 用戶端，以排除透過 VPN 連線傳送到組織網路的特定類型流量。

若要將 Microsoft 365 雲端資源的存取最佳化，請設定分割通道 VPN 用戶端，排除透過 VPN 連線到**最佳化**類別 Microsoft 365 端點的流量。 如需詳細資訊，請參閱 [Office 365 端點類別](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) (部分機器翻譯)。 請參閱[這裡](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)的最佳化類別端點清單。

![來自 VPN 用戶端的網路流量 (含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

如此可讓 VPN 用戶端直接透過網際網路傳送和接收重要的 Microsoft 365 雲端服務流量，並透過最接近的進入點到 Microsoft 網路。

如需詳細資訊和指導方針，請參閱[使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)。

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>當您的所有應用程式都為 Web 應用程式且您擁有混合式身分識別時，部署遠端存取

如果您的遠端工作者並未使用傳統的 VPN 用戶端，且您的內部部署使用者帳戶和群組已與 Azure AD 同步處理，則您可以使用 Azure AD 應用程式 Proxy，為內部網路伺服器上託管的 Web 架構應用程式，提供安全的遠端存取。 Web 架構應用程式包括 SharePoint 網站、Outlook Web Access 伺服器或其他任何 Web 架構企業營運應用程式。 

以下是 Azure AD 應用程式 Proxy 的元件。

![Azure AD 應用程式 Proxy 的元件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

如需詳細資訊，請參閱 [Azure AD 應用程式 Proxy 概觀](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)，以及[使用 Azure AD 應用程式 Proxy 的第 3 部分影片](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security) (英文)。

>[!Note]
>Azure AD 應用程式 Proxy 未包含在 Microsoft 365 訂閱中。 您必須購買單獨的 Azure 訂閱才能使用。
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>並非所有應用程式都是 Web 應用程式時，部署遠端存取

如果您的遠端工作者並未使用傳統的 VPN 用戶端，且您的任何應用程式都不是 Web 架構，則您可以使用 Azure 點對站台 (P2S) VPN。

P2S VPN 連線會透過 Azure 虛擬網路，建立遠端工作者裝置到貴組織網路的安全連線。 

![Azure P2S VPN 的元件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

如需詳細資訊，請參閱這個 [P2S VPN 概觀](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about) (部分機器翻譯)。

>[!Note]
>Azure P2S VPN 不包含在 Microsoft 365 訂閱中。 您必須購買單獨的 Azure 訂閱才能使用。
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>部署 Windows 虛擬桌面，以便為使用個人裝置的遠端工作者提供遠端存取 

為支援只能使用其個人和非受管理裝置的遠端工作者，請使用 Azure 中的 Windows 虛擬桌面建立並配置虛擬桌面，讓您的使用者可以在家使用。 虛擬化的電腦可以充當連線至貴組織網路的電腦使用。

![Azure Windows 虛擬桌面元件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

如需詳細資訊，請參閱： 

- [Windows 虛擬桌面的概觀](https://docs.microsoft.com/azure/virtual-desktop/overview)。
- [讓遠端工作者使用 Windows 虛擬桌面的第 2 部分影片](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity) (英文)。

>[!Note]
>Windows 虛擬桌面不包含在 Microsoft 365 訂閱中。 您必須購買單獨的 Azure 訂閱才能使用。
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a>使用遠端桌面服務閘道保護您的遠端桌面服務連線

如果您使用遠端桌面服務 (RDS) 來允許員工連線到內部部署網路上的 Windows 電腦，您應在邊緣網路中使用 Microsoft 遠端桌面服務閘道。 該閘道會使用安全通訊端層 (SSL) 加密通訊，並防止直接將主控 RDS 的系統暴露到網際網路上。

![使用遠端桌面服務閘道的遠端桌面服務連線](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

如需詳細資訊，請參閱[這篇文章](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/)。

## <a name="admin-technical-resources-for-remote-access"></a>適用於遠端存取的系統管理技術資源

- [如何快速優化遠端員工的 Office 365 流量，並降低基礎結構負載](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571) (英文)
- [使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a>步驟 2 的結果

為您的遠端工作者部署遠端存取解決方案之後：

| 遠端存取設定 | 結果 |
|:-------|:-----|
| 遠端存取 VPN 解決方案已就緒 | 您已經針對分割通道以及 Microsoft 365 端點的最佳化類別，設定您的遠端存取 VPN 用戶端。 |
| 沒有遠端存取 VPN 解決方案，而且您只需要遠端存取內部部署的 Web 架構應用程式 | 您已經設定 Azure 應用程式 Proxy。 |
| 沒有遠端存取 VPN 解決方案、您需要存取內部部署應用程式，而且其中部分應用程式並非 Web 架構 | 您已經設定 Azure P2S VPN。 |
| 遠端工作者正在家中使用其個人裝置 | 您已經設定 Windows 虛擬桌面。 |
| 遠端工作者正在使用 RDS 連線到內部部署系統 | 您已在邊緣網路中部署遠端桌面服務閘道。 |
|||

## <a name="next-step"></a>下一步

繼續進行[步驟 3](empower-people-to-work-remotely-security-compliance.md) 部署 Microsoft 365 安全性與合規性服務，以保護您的應用程式、資料和裝置。
