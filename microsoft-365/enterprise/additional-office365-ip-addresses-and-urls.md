---
title: Office 365 IP 位址和 URL Web 服務中未包含的其他端點
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 摘要：新端點 Web 服務不包含特定案例的少量端點。
hideEdit: true
ms.openlocfilehash: 76bfc947460d4c513207c3a53b2f4536282c65e1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289148"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Office 365 IP 位址和 URL Web 服務中未包含的其他端點

某些網路端點之前已經發佈，而且尚未包含在 [Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)中。Web 服務範圍是從 Office 365 使用者到整個企業周邊網路之連線能力所需的網路端點。這目前未包含：

1. 從 Microsoft 資料中心到客戶網路可能需要的網路連線 (內送混合式伺服器網路流量)。
2. 從客戶網路上的伺服器到整個企業周邊的網路連線能力 (外寄伺服器網路流量)。
3. 使用者網路連線能力需求的另類案例。
4. DNS 解析連線能力需求 (以下未列出)。
5. Internet Explorer 或 Microsoft Edge 信任的網站。

除了 DNS 以外，對大多數客戶來說，這些全都是選用，除非您需要所述的特定案例。

<br>

****

|列|用途|目的地|類型|
|---|---|---|---|
|1 |PST 的[匯入服務](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)和檔案擷取|如需其他需求的資訊，請參閱[匯入服務](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)。|另類外寄範例|
|2 |[適用於 Office 365 的 Microsoft 支援及修復小幫手](https://diagnostics.office.com/#/)|<https://autodiscover.outlook.com> <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> <https://apibasic.diagnostics.office.com> <br> <https://autodiscover-s.outlook.com> <br> <https://cloudcheckenabler.azurewebsites.net> <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|外寄伺服器流量|
|3 |Azure AD Connect (含 SSO 選項) – WinRM 和遠端 PowerShell|客戶 STS 環境 (AD FS 伺服器和 AD FS Proxy) \| TCP 通訊埠 80 和 443|內送伺服器流量|
|4 |STS，例如 AD FS Proxy 伺服器 (僅適用於同盟客戶)|客戶 STS (例如 AD FS Proxy) \| 通訊埠 TCP 443 或 TCP 49443 (含 ClientTLS)|內送伺服器流量|
|5 |[Exchange Online 整合通訊/SBC 整合](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)|內部部署會話邊界控制器和 um.outlook.com 之間的雙向 \* 。|僅限外寄伺服器的流量|
|6 |信箱遷移。 當信箱遷移從內部部署[Exchange 混合](/exchange/exchange-deployment-assistant)式 Office 365 時，Office 365 會連線至您發佈的 Exchange Web 服務 (EWS) /Mailbox 複寫服務 (MRS) server。 如果您需要 Exchange Online 伺服器用以限制來自特定來源 IP 範圍之輸入連線的 NAT IP 位址，這些位址會列在「Exchange Online」服務區域底下的[Office 365 URL & IP 範圍](urls-and-ip-address-ranges.md)內。 <p> 請務必小心，以確保對發佈的 EWS 端點（如 OWA）的存取不會受到影響，因為可確保 MRS proxy 先解析為個別的 FQDN 和公用 IP 位址，再從特定來源 IP 範圍限制 TCP 443 連線。|客戶內部部署 EWS/MRS Proxy <br> TCP 通訊埠 443|內送伺服器流量|
|7 |[Exchange 混合式](/exchange/exchange-deployment-assistant)共存功能，例如空閒/忙碌共用。|客戶內部部署 Exchange 伺服器|內送伺服器流量|
|8 |[Exchange 混合式](/exchange/exchange-deployment-assistant) Proxy 驗證|客戶內部部署 STS|內送伺服器流量|
|9 |用來設定 [Exchange 混合式](/exchange/exchange-deployment-assistant)，使用 [Exchange 混合式組態精靈](/exchange/hybrid-configuration-wizard) <p> 附註：只有在設定 Exchange 混合式時，才需要這些端點|TCP 通訊埠 80 和 443 上的 domains.live.com，只有 Exchange 2010 SP3 混合式組態精靈才需要。 <p> GCC 高、DoD IP 位址：40.118.209.192/32；168.62.190.41/32 <p> 全球商業銀行 & GCC： \* store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net; <br> aka.ms/hybridwizard; <br> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;|僅限外寄伺服器的流量|
|10 |自動偵測服務用於 [Exchange 混合式](/exchange/exchange-deployment-assistant)案例，搭配 [iOS 版 Outlook 和 Android 的混合式新式驗證](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <p> `*.acompli.net` <br> `*.outlookmobile.com` <br> `*.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|客戶在 TCP 443 上內部部署 Exchange 伺服器|內送伺服器流量|
|11 |Exchange 混合式 Azure AD 驗證|msappproxy.net|僅限 TCP 輸出伺服器流量|
|12 |Office 2016 中的商務用 Skype 包含使用 UDP 通訊埠根據螢幕共用的視訊。Office 2013 及較舊版本中的商務用 Skype 用戶端在 TCP 通訊埠 443 上使用 RDP。|TCP 通訊埠 443 開放給 52.112.0.0/14|Office 2013 及較舊版本中的商務用 Skype 更舊用戶端版本|
|13 |商務用 Skype 混合式內部部署伺服器連線至商務用 Skype Online|13.107.64.0/18、52.112.0.0/14 <br> UDP 連接埠 50,000-59,999 <br> TCP 連接埠 50,000-59,999；5061|商務用 Skype 內部部署伺服器輸出連線|
|14 |具有內部部署混合式連線的 Cloud PSTN 要求開啟內部部署主機的網路連線。如需商務用 Skype Online 混合式設定的詳細資料，|請參閱[規劃商務用 Skype Server 和 Office 365 之間的混合式連線](/skypeforbusiness/hybrid/plan-hybrid-connectivity) (英文)|商務用 Skype 內部部署混合式輸入|
|8|**驗證與身分識別 FQDN** <p> FQDN `secure.aadcdn.microsoftonline-p.com` 必須在您用戶端的 Internet Explorer (IE) 或 Microsoft Edge 信任的網站區域中才能正常運作。||信任的網站|
|16 |**Microsoft Teams FQDN** <p> 如果您使用的是 Internet Explorer 或 Microsoft Edge，您需要啟用第一和第三方 Cookie，並將 Teams 的 FQDN 新增到您的 [信任的網站] 中。這是列 14 所列之跨套件 FQDN、CDN 和遙測之外的項目。如需詳細資訊，請參閱 [Microsoft Teams 的已知問題](/microsoftteams/known-issues)。||信任的網站|
|17 |**SharePoint Online 和商務用 OneDrive FQDN** <p> 所有在 FQDN 中含有 '\<tenant\>' 的 '.sharepoint.com' 的 FQDN 都必須在您用戶端的 IE 或 Microsoft Edge 信任的網站區域中才能正常運作。除了列 14 列出的跨套件 FQDN、CDN 和遙測，您也必須新增這些端點。||信任的網站|
|18 |**Yammer**  <br> Yammer 僅可於瀏覽器中使用，且必須透過 Proxy 傳遞已驗證的使用者。所有 Yammer FQDN 都必須在用戶端的 IE 或 Microsoft Edge 的信任的網站區域中才能正常運作。||信任的網站|
|19|使用 [Azure AD Connect](/azure/active-directory/hybrid/) 將內部部署使用者帳戶同步處理到 Azure AD。|請參閱[混合式身分識別所需的連接埠和通訊協定](/azure/active-directory/hybrid/reference-connect-ports)、[疑難排解 Azure AD 連線](/azure/active-directory/hybrid/tshoot-connect-connectivity) 和 [Azure AD Connect Health 代理程式安裝](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints)。|僅限外寄伺服器的流量|
|共|[Azure AD Connect](/azure/active-directory/hybrid/) 與中國的 21 ViaNet 將內部部署使用者帳戶同步處理到 Azure AD。|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*。 partner.microsoftonline.cn:443 <p> 另請參閱[針對 Azure AD Connect 的連線問題進行疑難排解](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity)。|僅限外寄伺服器的流量|
| 21|Microsoft Stream (需要 Azure AD 使用者權杖)。 <br> Office 365 全球 (包括 GCC)|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> TCP 通訊埠 443|內送伺服器流量|
|22|在伺服器的新安裝以及使用Active Directory 網域服務 (AD DS) 進行設定時，將 MFA 伺服器用於多重要素驗證要求。|請參閱 [AZURE AD Multi-Factor 驗證服務器快速入門](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)。|僅限外寄伺服器的流量|
|至|Microsoft Graph 變更通知 <p> 開發人員可以利用[變更通知](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0)來訂閱 Microsoft Graph 中的事件。|\*.cloudapp.net <br> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228 <p> 公用雲端：168.63.250.205、52.161.9.202、40.68.103.62、13.89.60.223、23.100.95.104、40.113.95.219、104.214.32.10、168.63.237.145、52.161.110.176、52.174.177.183、13.85.192.59、13.85.192.123、13.86.37.15、13.89.108.233、13.89.104.147、20.44.210.83、20.44.210.146、40.76.162.99、40.76.162.42、40.74.203.28、40.74.203.27、51.104.159.213、51.104.159.181、51.124.75.43、51.124.73.177、51.138.90.7、51.138.90.52、52.139.153.222、52.139.170.157、52.139.170.47、52.142.114.29、、、、、、、52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <p> Microsoft Cloud for US Government：52.244.231.173、52.238.76.151、52.244.250.211、52.238.78.108、52.243.147.249、52.243.148.19、52.243.157.104、52.243.157.105、52.244.33.45、52.244.35.174、52.244.111.156、52.244.111.170 <p> Microsoft Cloud 德國：51.4.231.136、51.5.243.223、51.4.226.154、51.5.244.215、51.4.150.206、51.4.150.235、51.5.147.130、51.5.148.103 <p> 由世紀運作的 Microsoft 雲端中國：139.219.15.33、42.159.154.223、42.159.88.79、42.159.155.77、40.72.155.199、40.72.155.216、40.125.138.23、40.125.136.69、42.159.72.35、42.159.72.47、42.159.180.55、42.159.180.56 <br> TCP 通訊埠 443 <p> 附註：開發人員可以在建立訂閱時指定不同的通訊埠。|內送伺服器流量|
|

## <a name="related-topics"></a>相關主題

[管理 Office 365 端點](managing-office-365-endpoints.md)
  
[監視 Microsoft 365 連線能力](./monitor-connectivity.md)
  
[用戶端連線](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[內容傳遞網路](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP 範圍和服務標記–公用雲端](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP 範圍和服務標記–美國政府雲端](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP 範圍和服務標記–德國雲端](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP 範圍和服務標記–中國雲端](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 公用 IP 空間](https://www.microsoft.com/download/details.aspx?id=53602)
