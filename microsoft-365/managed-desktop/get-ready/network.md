---
title: Microsoft 受管理的電腦的網路設定
description: 如何設定代理和必要的端點
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 076d2fe17be8d557d55d432eda637e4ba74a0121
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339391"
---
#  <a name="network-configuration-for-microsoft-managed-desktop"></a>Microsoft 受管理的電腦的網路設定

<!--Proxy config -->


## <a name="proxy-configuration"></a>Proxy 設定

Microsoft 受管理的電腦是雲端管理的服務。 Microsoft 受管理的電腦服務必須能夠達到一組端點。 本節列出 Microsoft 受管理的電腦服務各方面需要允許的端點。 

客戶可以透過防火牆或 proxy 直接傳送所有信任的 Microsoft 365 網路要求，以優化其網路，略過驗證及所有其他的封包層級檢查或處理。 這會降低延遲和您的周邊容量需求。 

此外，為了 Microsoft 受管理的電腦雲端式服務的優化效能，這些端點需要客戶用戶端瀏覽器和其 edge 網路中的裝置進行特殊處理。 這些裝置包括防火牆、SSL 中斷及檢查、資料包檢查裝置和資料遺失防護系統。

### <a name="proxy-requirement"></a>Proxy 需求

Proxy 或防火牆必須支援 TLS 1.2。 否則，您可能必須停用通訊協定偵測。

### <a name="endpoints-allowed-that-are-necessary-for-microsoft-managed-desktop"></a>允許 Microsoft 受管理的電腦所需的端點

Microsoft 受管理的電腦會使用 Azure 入口網站來主控其網頁主控台。 下列 URLs 必須位於 proxy 和防火牆的允許清單上，以便 Microsoft 受管理的電腦裝置可以與 Microsoft 服務通訊。  

Microsoft 受管理的電腦 URL 用於服務于客戶 API 執行的任何專案。 您必須確定您的公司網路一定可以存取此 URL。

Microsoft 服務  | 允許清單上的 URLs 必要專案 
--- | ---
Microsoft 受管理的電腦 | prod-mwaas-services-customerapi.azurewebsites.net
取得說明 | \*。 support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com
快速助手 | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*。 lync.com
Microsoft 支援及修復小幫手 | \*。 apibasic.diagnostics.office.com  <br>\*。 api.diagnostics.office.com
 

### <a name="endpoints-allowed-used-by-other-microsoft-products"></a>其他 Microsoft 產品所允許使用的端點

有來自數個 Microsoft 產品的 URLs 需要位於允許的清單中，以便 Microsoft 受管理的電腦裝置可以與這些 Microsoft 服務通訊。 使用連結查看每個產品的完整清單。 

Microsoft 服務 | 文件
--- | ---
Windows 10 企業版包括商務 Windows 更新 | [管理 Windows 10 的連接端點，版本1803](/windows/privacy/manage-windows-1803-endpoints)<br><br>[管理 Windows 10 版本1809的連接端點](/windows/privacy/manage-windows-1809-endpoints)<br><br>[管理 Windows 10 的連接端點，版本1903](/windows/privacy/manage-windows-1903-endpoints)<br><br>[管理 Windows 10 的連接端點，版本2004](/windows/privacy/manage-windows-2004-endpoints)
傳遞最佳化 | [設定 Windows 10 更新的傳遞優化](/windows/deployment/update/waas-delivery-optimization)
Microsoft 365 | [Microsoft 365URL 與 IP 位址範圍](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | [混合式識別所需的埠和通訊協定](/azure/active-directory/hybrid/reference-connect-ports) 和 Active Directory [網域服務埠需求](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | [Intune 網路設定需求](/intune/network-bandwidth-use)<br>[Microsoft Intune 的網路端點](/mem/intune/fundamentals/intune-endpoints)
適用於端點的 Microsoft Defender | [Microsoft Defender for Endpoint 需求](/windows/security/threat-protection/windows-defender-atp/configure-proxy-internet-windows-defender-advanced-threat-protection#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server)
Windows Autopilot | [WindowsAutopilot 網路需求](/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)

Microsoft 服務  | 允許清單上的 URLs 必要專案 | 檔來源
--- | --- | ---
Windows更新商務用 (WUfB)  | update.microsoft.com<br>\*。 update.microsoft.com<br>download.windowsupdate.com<br>\*。 download.windowsupdate.com<br>download.microsoft.com<br>\*。 download.microsoft.com<br>windowsupdate.com<br>\*。 windowsupdate.com<br>ntservicepack.microsoft.com<br>wustat.windows.com<br>login.live.com <br>mp.microsoft.com<br>\*。 mp.microsoft.com | [Windows商務防火牆及 proxy 需求的更新](https://support.microsoft.com/help/3084568/can-t-download-updates-from-windows-update-from-behind-a-firewall-or-p)
傳遞最佳化 | \*。 do.dsp.mp.microsoft.com<br>\*。 dl.delivery.mp.microsoft.com <br>\*。 emdl.ws.microsoft.com<br>\*。 download.windowsupdate.com <br>\*。 windowsupdate.com   | [Windows更新 proxy 需求](https://support.microsoft.com/help/3175743/proxy-requirements-for-windows-update)
商務用 Microsoft Store | login.live.com <br>account.live.com <br>clientconfig.passport.net <br>wustat.windows.com <br>\*。 windowsupdate.com <br>\*。 wns.windows.com <br>\*。 hotmail.com <br>\*。 outlook.com <br>\*。 microsoft.com <br>\*。 msftncsi.com/ncsi.txt   | [Microsoft Store 允許清單](https://support.microsoft.com/help/2778122/using-authenticated-proxy-servers-together-with-windows-8)
Microsoft 365 | \*。 office365.com<br>\*。 office.com<br>\*。 office.net<br>\*。 live.com<br>\*。 portal.cloudappsecurity.com<br>\*。 portal.cloudappsecurity.com<br>\*。 us.portal.cloudappsecurity.com<br>\*。 eu.portal.cloudappsecurity.com<br>\*。 us2.portal.cloudappsecurity.com<br><tenant>.onmicrosoft.com<br>account.office.net<br>agent.office.net<br>apc.delve.office.com<br>aus.delve.office.com<br>can.delve.office.com<br>delve.office.com<br>eur.delve.office.com<br>gbr.delve.office.com<br>home.office.com<br>ind.delve.office.com<br>jpn.delve.office.com<br>kor.delve.office.com<br>lam.delve.office.com<br>nam.delve.office.com<br>admin.microsoft.com<br>outlook.office365.com<br>suite.office.net<br>webshell.suite.office.com<br>www.office.com<br>\*。 aria.microsoft.com<br>browser.pipe.aria.microsoft.com<br>mobile.pipe.aria.microsoft.com<br>portal.microsoftonline.com<br>clientlog.admin.microsoft.com<br>nexus.officeapps.live.com<br>nexusrules.officeapps.live.com<br>amp.azure.net<br>\*。 o365weve.com<br>auth.gfx.ms<br>appsforoffice.microsoft.com<br>assets.onestore.ms<br>az826701.vo.msecnd.net<br>c.microsoft.com<br>c1.microsoft.com<br>client.hip.live.com<br>contentstorage.osi.office.net<br>dgps.support.microsoft.com<br>docs.microsoft.com<br>groupsapi-<br>rod.outlookgroups.ms<br>groupsapi2-prod.outlookgroups.ms<br>groupsapi3-prod.outlookgroups.ms<br>groupsapi4-prod.outlookgroups.ms<br>msdn.microsoft.com<br>platform.linkedin.com<br>products.office.com<br>prod.msocdn.com<br>r1.res.office365.com<br>r4.res.office365.com<br>res.delve.office.com<br>shellprod.msocdn.com<br>support.content.office.net<br>support.microsoft.com<br>support.office.com<br>technet.microsoft.com<br>templates.office.com<br>video.osi.office.net<br>videocontent.osi.office.net<br>videoplayercdn.osi.office.net<br>\*。 manage.office.com<br>\*。 protection.office.com<br>manage.office.com<br>Protection.office.com<br>diagnostics.office.com | [Microsoft 365URL 與 IP 位址範圍](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | api.login.microsoftonline.com<br>api.passwordreset.microsoftonline.com<br>autologon.microsoftazuread-sso.com<br>becws.microsoftonline.com<br>clientconfig.microsoftonline-p.net <br>companymanager.microsoftonline.com <br>device.login.microsoftonline.com <br>hip.microsoftonline-p.net <br>hipservice.microsoftonline.com <br>login.microsoft.com<br>login.microsoftonline.com <br>logincert.microsoftonline.com <br>loginex.microsoftonline.com<br>login-us.microsoftonline.com <br>login.microsoftonline-p.com <br>login.windows.net <br>nexus.microsoftonline-p.com <br>passwordreset.microsoftonline.com <br>provisioningapi.microsoftonline.com<br>stamp2.login.microsoftonline.com<br>\*。 msappproxy.net<br>ccs.login.microsoftonline.com<br>ccs-sdf.login.microsoftonline.com<br>accounts.accesscontrol.windows.net<br>secure.aadcdn.microsoftonline-p.com<br>\*。 phonefactor.net<br>account.activedirectory.windowsazure.com<br>secure.aadcdn.microsoftonline-p.com<br>graph.microsoft.com | [混合式識別所需的埠和通訊協定](/azure/active-directory/connect/active-directory-aadconnect-ports) 和 Active Directory [網域服務埠需求](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | login.microsoftonline.com<br>portal.manage.microsoft.com<br>m.manage.microsoft.com<br>sts.manage.microsoft.com<br>Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com<br>fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fef.msua01.manage.microsoft.com<br>fef.msua02.manage.microsoft.com<br>fef.msua04.manage.microsoft.com<br>fef.msua05.manage.microsoft.com<br>fef.msua06.manage.microsoft.com<br>fef.msua07.manage.microsoft.com<br>fef.msub01.manage.microsoft.com<br>fef.msub02.manage.microsoft.com<br>fef.msub03.manage.microsoft.com<br>fef.msub05.manage.microsoft.com<br>fef.msuc01.manage.microsoft.com<br>fef.msuc02.manage.microsoft.com<br>fef.msuc03.manage.microsoft.com<br>fef.msuc05.manage.microsoft.com |  [Intune 網路設定需求](/intune/network-bandwidth-use)
商務用 OneDrive | onedrive.com <br> <br>\*。 onedrive.com <br>onedrive.live.com <br>login.live.com <br>spoprod-a.akamaihd.net <br>\*。 mesh.com <br>p.sfx.ms <br>\*。 microsoft.com <br>fabric.io <br>\*。 crashlytics.com <br>vortex.data.microsoft.com <br>https://posarprodcssservice.accesscontrol.windows.net <br>redemptionservices.accesscontrol.windows.net  <br>token.cp.microsoft.com/ <br>tokensit.cp.microsoft-tst.com/ <br>\*。 office.com <br>\*。 officeapps.live.com <br>\*。 aria.microsoft.com <br>\*。 mobileengagement.windows.net <br>\*。 branch.io <br>\*。 adjust.com <br>\*。 servicebus.windows.net <br>vas.samsungapps.com <br>odc.officeapps.live.com <br>login.windows.net <br>login.microsoftonline.com <br>\*。 files.1drv.com <br>\*。 onedrive.live.com <br>\*.\*.onedrive.live.com <br>storage.live.com <br>\*。 storage.live.com <br>\*.\*.storage.live.com <br>\*。 groups.office.live.com <br>\*。 groups.photos.live.com <br>\*。 groups.skydrive.live.com <br>favorites.live.com <br>oauth.live.com <br>photos.live.com <br>skydrive.live.com <br>api.live.net <br>apis.live.net <br>docs.live.net <br>\*。 docs.live.net <br>policies.live.net <br>\*。 policies.live.net <br>settings.live.net <br>\*。 settings.live.net <br>skyapi.live.net <br>snapi.live.net <br>\*。 livefilestore.com <br>\*.\*.livefilestore.com <br>storage.msn.com <br>\*。 storage.msn.com <br>\*. * storage.msn.com | [OneDrive 所需的 URLs 和埠](/onedrive/required-urls-and-ports)
Microsoft Defender 進階威脅防護 (ATP) | \ * oms.opinsights.azure.com <br>\*。 blob.core.windows.net <br>\*。 azure-automation.net <br>\*。 ods.opinsights.azure.com <br>winatp-gw-cus.microsoft.com <br>winatp-gw-eus.microsoft.com <br>winatp-gw-neu.microsoft.com <br>winatp-gw-weu.microsoft.com <br>winatp-gw-uks.microsoft.com <br>winatp-gw-ukw.microsoft.com <br>winatp-gw-aus.microsoft.com <br>winatp-gw-aue.microsoft.com | [Windows DefenderATP 端點](/windows/security/threat-protection/windows-defender-atp/configure-server-endpoints-windows-defender-advanced-threat-protection)
取得說明 | \*。 support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com <br>rave.office.net | 
快速助手 | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*。 lync.com | 
SharePoint Online  | \*.sharepoint.com <br>\ * svc.ms  <br>\<tenant\>.sharepoint.com  <br>\<tenant\>-my.sharepoint.com  <br>\<tenant\>-files.sharepoint.com  <br>\<tenant\>-myfiles.sharepoint.com <br>\*。 sharepointonline.com  <br>cdn.sharepointonline.com  <br>static.sharepointonline.com  <br>spoprod-a.akamaihd.net  <br>publiccdn.sharepointonline.com  <br>privatecdn.sharepointonline.com | [Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)
商務用 OneDrive | admin.onedrive.com  <br>officeclient.microsoft.com <br>odc.officeapps.live.com  <br>skydrive.wns.windows.com <br>g.live.com <br>oneclient.sfx.ms <br>\*。 log.optimizely.com  <br>click.email.microsoftonline.com  <br>ssw.live.com  <br>storage.live.com |  [Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Microsoft Teams | \*。 teams.skype.com  <br>\*。 teams.microsoft.com  <br>teams.microsoft.com <br>\*。 asm.skype.com <br>\ * cc.skype.com  <br>\*。 conv.skype.com  <br>\*。 dc.trouter.io  <br>\*。 msg.skype.com  <br>prod.registrar.skype.com  <br>prod.tpc.skype.com <br>\*。 broker.skype.com <br>\*.config。 skype.com  <br>\*。 pipe.skype.com  <br>\*。 pipe.aria.microsoft.com  <br>config.edge.skype.com  <br>pipe.skype.com  <br>s-0001.s-msedge.net  <br>s-0004.s-msedge.net  <br>scsinstrument-ss-us.trafficmanager.net  <br>scsquery-ss- <br>us.trafficmanager.net  <br>scsquery-ss-eu.trafficmanager.net  <br>scsquery-ss-asia.trafficmanager.net <br>\*。 msedge.net <br>compass-ssl.microsoft.com  <br>feedback.skype.com <br>\*。 secure.skypeassets.com  <br>mlccdnprod.azureedge.net  <br>videoplayercdn.osi.office.net <br>\*。 mstea.ms | [Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Power BI | maxcdn.bootstrapcdn.com <br>ajax.aspnetcdn.com <br>netdna.bootstrapcdn.com <br>cdn.optimizely.com <br>google-analytics.com <br>\*。 mktoresp.com <br>\*.aadcdn.microsoftonline-p.com <br>\*。 msecnd.com <br>\*。 localytics.com <br>ajax.aspnetcdn.com <br>\*。 localytics.com <br>\*。 virtualearth.net <br>platform.bing.com <br>powerbi.microsoft.com <br>c.microsoft.com <br>app.powerbi.com <br>\*。 powerbi.com <br>dc.services.visualstudio.com <br>support.powerbi.com <br>powerbi.uservoice.com <br>go.microsoft.com <br>c1.microsoft.com <br>\*。 azureedge.net |[Power BI & Express Route](/power-bi/service-admin-power-bi-expressroute) 
OneNote | apis.live.net <br>www.onedrive.com <br>login.microsoft.com  <br>www.onenote.com <br>\*。 onenote.com <br>\*。 msecnd.net <br>\*。 microsoft.com <br>\*。 office.net <br>cdn.onenote.net <br>site-cdn.onenote.net <br>cdn.optimizely.com <br>Ajax.aspnetcdn.com <br>officeapps.live.com <br>\\onenote.com <br>\*cdn.onenote.net <br>contentstorage.osi.office.net <br>\*onenote.officeapps.live.com <br>\*。 microsoft.com | [Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦 (本文的網路](network.md)設定) 
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
