---
title: Mac 版 Office 中的網路要求
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: 本文說明嘗試到達哪些端點和 URLs Mac 版 Office 應用程式，以及提供的服務。
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688571"
---
# <a name="network-requests-in-office-for-mac"></a>Mac 版 Office 中的網路要求

Mac 版 Office 應用程式提供 macOS 平臺上的原生應用程式體驗。 每個應用程式的設計目的都是在各種案例中運作，包括沒有網路存取可用時的狀態。 當機器連接至網路時，應用程式會自動連接至一系列的 web 型服務，以提供增強的功能。 下列資訊說明應用程式嘗試到達哪些端點和 URLs，以及所提供的服務。 此資訊對於疑難排解網路設定問題及設定網路 proxy 伺服器的原則很有用。 本文中的詳細資料是用於補充[Office 365 URL 和位址範圍文章](urls-and-ip-address-ranges.md)，其中包含執行 Microsoft Windows 之電腦的端點。 除非另有說明，否則本文中的資訊也適用于 Mac 和 Mac 版 Office 2016 的 Office 2019，可從零售商店購買一次，或透過大量授權達成。 

  
本文大部分是詳述網路 URLs、類型，以及該端點所提供之服務或功能說明的表格。 每個 Office 應用程式在其服務和端點使用量上可能會有所不同。 下列應用程式是在下表中定義：
  
- W： Word
- P： PowerPoint
- X： Excel
- O： Outlook
- N： OneNote
   
URL 類型定義如下：
  
- ST： Static-URL 已硬編碼為用戶端應用程式。
    
- SS： Semi-Static-此 URL 是以網頁或重新導向程式的一部分編碼。
    
- CS： Config service-此 URL 會傳回為 Office 設定服務的一部分。

    
## <a name="office-for-mac-default-configuration"></a>Mac 版 Office 預設設定

 **安裝和更新**
  
下列網路端點是用來從 Microsoft 內容傳遞網路 (CDN) 下載 Mac 版 Office 安裝程式。
  
|**URL**|**類型**|**描述**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |聖  <br/> |Microsoft 365安裝入口網站會將連結服務轉寄至最新的安裝套件。  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |秒  <br/> |安裝套件在內容傳遞網路上的位置。  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |秒  <br/> |安裝套件在內容傳遞網路上的位置。  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |聖  <br/> |Microsoft AutoUpdate 的管理控制端點  <br/> |
   
 **第一個應用程式啟動**
  
在第一次啟動 Office 應用程式時會取得下列網路端點。 這些端點為使用者提供增強型 Office 功能，而不論授權類型 (包括大量授權安裝) ，都會聯繫 URLs。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |聖  <br/> |' Flighting ' 設定-允許功能變亮及實驗。  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |聖  <br/> |' Flighting ' 網路設定測試  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |聖  <br/> |' Flighting ' 網路設定測試  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |聖  <br/> |OfficeConfiguration Service-服務端點的主清單。  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Office規則遙測下載-通知用戶端要上傳至遙測服務的資料和事件。  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |Cs  <br/> |OneNote遙測服務  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Office遙測 Upload 報告-"Heartbeart" 和發生在用戶端上的錯誤事件會上傳至遙測服務。  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |Cs  <br/> |OfficeTemplate Service-為使用者提供線上檔範本。  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |Cs  <br/> |Office範本下載-PNG 範本影像儲存體。  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |Cs  <br/> |Office 應用程式的儲存區設定。  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |Office檔 Integration Services 目錄 (服務和端點的清單) 和主領域探索。  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |Cs  <br/> |家用領域探索 v2 的資源 (15.40 和更新版本)   <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft AutoUpdate 資訊清單-檢查是否有可用的更新  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |秒  <br/> |Microsoft Ajax JavaScript 程式庫  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |秒  <br/> |用於 Office 設定和資源的維琪百科應用程式。  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |秒  <br/> |Bing對應 Office 設定和資源的應用程式。  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |秒  <br/> |Office 設定和資源的人員 Graph 應用程式。  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |聖  <br/> |OneNote 的新內容。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |聖  <br/> |OneNote 的新內容。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |秒  <br/> |OneNote 的新圖像。  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |聖  <br/> |應用程式內支援服務。  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |聖  <br/> |電子郵件帳戶偵測服務。  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |聖  <br/> |Outlook搜索  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |聖  <br/> |Microsoft 365 服務的 Outlook 端點。  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |聖  <br/> |Outlook 增益集的圖示。  <br/> |
   
> [!NOTE]
> Office 設定服務充當所有 Microsoft Office 用戶端（而不只是 Mac）的自動探索服務。 在回應中傳回的端點是非靜態的，因為這項變更很少，但仍然可行。 
  
 **登入**
  
登入雲端式儲存體時，會聯繫到下列網路端點。 視您的帳戶類型而定，可能會聯繫到不同的服務。 例如：
  
- **MSA： Microsoft 帳戶** -通常用於消費和零售案例 
    
- **OrgID：組織帳戶** -通常用於商業案例 
    
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |聖  <br/> |Windows授權服務  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft 365登入服務 (OrgID)   <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft 帳戶登入服務 (MSA)   <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |Cs  <br/> |Microsoft 帳戶登入服務協助 (MSA)   <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |秒  <br/> |Microsoft 365登入商標 (OrgID)   <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |儲存體定位器的檔和位置  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |最近使用 (MRU) 檔服務  <br/> |
   
> [!NOTE]
> 若為訂閱型和零售授權，登入都會啟用產品，並可存取雲端資源，例如 OneDrive。 在大量授權安裝中，預設) 使用者仍會收到登入 (，但只有在產品已經啟用時，才需要存取雲端資源。 
  
 **產品啟用**
  
下列網路端點適用于 Microsoft 365 訂閱和零售授權啟用。 具體而言，這不會套用到大量授權安裝。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |Cs  <br/> |Office 授權服務  <br/> |
   
 **新的內容**
  
下列網路端點只適用于 Microsoft 365 訂閱。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |秒  <br/> |何謂「新的 JSON 頁面」內容。  <br/> |
   
 **研究工具**
  
下列網路端點只適用于 Microsoft 365 訂閱。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |Cs  <br/> |研究員 Web 服務  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |Cs  <br/> |研究員靜態內容  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |Cs  <br/> |研究員內容提供者  <br/> |
   
 **智慧查閱**
  
下列網路端點同時適用于 Microsoft 365 訂閱和零售/大量授權啟用。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |Insights Web 服務  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |Cs  <br/> |JQuery 程式庫  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |Cs  <br/> |支援 JavaScript 程式庫  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |Cs  <br/> |Insights 內容提供者  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |Cs  <br/> |Insights 內容提供者  <br/> |
   
 **PowerPoint 設計工具**
  
下列網路端點只適用于 Microsoft 365 訂閱。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |Cs  <br/> |PowerPoint 設計工具 web 服務  <br/> |
   
 **PowerPoint 快速啟動工具**
  
下列網路端點只適用于 Microsoft 365 訂閱。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |Cs  <br/> |PowerPoint快速啟動工具 web 服務  <br/> |
   
 **傳送微笑/Frown**
  
下列網路端點同時適用于 Microsoft 365 訂閱和零售/大量授權啟用。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |Cs  <br/> |傳送微笑服務  <br/> |
   
 **聯絡人支援**
  
下列網路端點同時適用于 Microsoft 365 訂閱和零售/大量授權啟用。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |Cs  <br/> |聯絡人支援服務  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |Cs  <br/> |應用程式內支援服務  <br/> |
   
 **另存為 PDF**
  
下列網路端點同時適用于 Microsoft 365 訂閱和零售/大量授權啟用。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |Cs  <br/> |Word 檔轉換服務 (PDF)   <br/> |
   
 **Office應用程式 (稱為增益集)**
  
當 Office 應用程式增益集受到信任時，下列網路端點會同時適用于 Microsoft 365 訂閱和零售/大量授權啟用。
  
|**URL**|**應用程式**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |Cs  <br/> |Office 應用程式儲存區設定  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |秒  <br/> |維琪百科應用程式資源  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |秒  <br/> |Bing地圖應用程式資源  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |秒  <br/> |人員 Graph 的應用程式資源  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |秒  <br/> |Office重新定向服務  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |秒  <br/> |OfficeJavaScript 文件庫  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |Wx  <br/> |秒  <br/> |Office 應用程式的遙測和報表服務  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |秒  <br/> |Microsoft Ajax JavaScript 程式庫  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |秒  <br/> |Microsoft Ajax JavaScript 程式庫  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |秒  <br/> |OfficeJavaScript 文件庫  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |秒  <br/> |支援資源  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |秒  <br/> |支援資源  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |秒  <br/> |支援資源  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |秒  <br/> |JavaScript 程式庫  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |秒  <br/> |錯誤報表  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |秒  <br/> |字型資源  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |秒  <br/> |遙測服務  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |秒  <br/> |遙測報告  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |秒  <br/> |Microsoft Store資產庫  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |秒  <br/> |維琪百科頁面資源  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |秒  <br/> |維琪百科媒體資源  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |秒  <br/> |維琪百科沙箱框架  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |秒  <br/> |地圖範本  <br/> |
   
 **安全連結**
  
下列網路端點只適用于 Microsoft 365 訂閱的所有 Office 應用程式。
  
|**URL**|**類型**|**描述**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |Cs  <br/> |Microsoft 安全連結服務  <br/> |
   
 **崩潰報告**
  
下列網路端點適用于 Microsoft 365 訂閱和零售/大量授權啟用的所有 Office 應用程式。 當程式意外地損毀時，就會產生報告並傳送至 Watson 服務。
  
|**URL**|**類型**|**描述**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |聖  <br/> |Microsoft 錯誤報表服務  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |聖  <br/> |Office合作 Insights 服務  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>減少網路要求與流量的選項

Mac 版 Office 的預設設定可提供最佳的使用者體驗，也就是功能和保持機器的最新能力。 在某些情況下，您可能想要防止應用程式與網路端點聯繫。 本節討論這樣做的選項。
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>停用 Cloud Sign-In 和 Office Add-Ins
  
大量授權客戶可能會嚴格遵守將檔儲存至雲端架構儲存的原則。 您可以設定下列每個應用程式首選項，以停用 MSA/OrgID 登入，並存取 Office 增益集。
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

如果使用者嘗試存取 Sign-In 函數，將會看到 [網路連線] 不存在的錯誤。 因為此首選項也會封鎖線上產品啟用，它只應該用於大量授權安裝。 具體說來，使用此首選項會使 Office 應用程式無法存取下列端點：
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- 上述「登入」區段中列出的所有端點。
    
- 上的「Smart Lookup」區段中所列的所有端點。
    
- 上的「產品啟用」區段中所列的所有端點。
    
- "Office 應用程式 (中列出的所有端點（稱為增益集) ] 區段）。
    
若要為使用者重新建立完整功能，請將偏好設定為 "2" 或加以移除。
  
> [!NOTE]
> 此首選項需要 Mac 版 Office 組建 15.25 [160726] 或更新版本。 
  
### <a name="telemetry"></a>遙測
  
Mac 版 Office 定期將遙測資訊傳送回 Microsoft。 資料上傳到「結點」端點。 遙測資料可協助工程小組評估每個 Office 應用程式的健康情況及任何未預期的行為。 遙測分為兩種類別：
  
- **心跳** 包含版本和授權資訊。 此資料會在應用程式啟動時立即傳送。 
    
- **使用狀況** 包含有關如何使用應用程式和非致命錯誤的資訊。 此資料每60分鐘傳送一次。 
    
Microsoft 會認真對待您的隱私權。 您可以在中閱讀 Microsoft 的資料收集原則 [https://privacy.microsoft.com](https://privacy.microsoft.com) 。 若要防止應用程式傳送「使用狀況」遙測，可以調整 **SendAllTelemetryEnabled** 首選項。 喜好設定為每個應用程式，而且可以透過 macOS 設定設定檔或從終端手動設定： 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

心跳遙測永遠會傳送，而且無法停用。
  
### <a name="crash-reporting"></a>崩潰報告
  
當發生嚴重的應用程式錯誤時，應用程式會意外終止並將崩潰報告上傳至 ' Watson ' 服務。 崩潰報告包含呼叫堆疊，該呼叫堆疊是應用程式在崩潰之前所處理的步驟清單。 下列步驟可協助工程小組識別失敗的確切功能及原因。
  
在某些情況下，檔的內容會導致應用程式損毀。 如果應用程式將檔識別為原因，它會詢問使用者是否可以傳送檔及呼叫堆疊。 使用者可對此問題做出明智的選擇。 IT 管理員對檔案傳輸的要求非常嚴格，並代表使用者進行決策，永遠不會傳送檔。 下列首選項可以設定為防止傳送檔，並抑制使用者的提示：
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> 如果 **SendAllTelemetryEnabled** 設定為 **FALSE**，則會停用該處理常式的所有崩潰報告。 若要在未傳送流量遙測的情況下啟用故障報告，可以設定下列首選項： ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>更新
  
Microsoft 會定期發行 Mac 版 Office 更新， (通常是每月) 。 我們強烈鼓勵使用者和 IT 系統管理員保持最新的機器，以確保已安裝最新的安全性修正程式。 在 IT 系統管理員想要密切控制及管理電腦更新的情況下，可以設定下列首選項，以避免 AutoUpdate 程式自動偵測及提供產品更新：
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>使用防火牆/Proxy 封鎖要求
  
如果您的組織透過防火牆或 proxy 伺服器封鎖 URLs 的要求，請務必將此檔中所列的 URLs 設定為 [允許]，或是以40X 回應列出的封鎖 (例如403或 404) 。 40X 回應會讓 Office 的應用程式適當地接受無法存取資源的功能，並提供更快的使用者體驗，而不只是放入連線，而是會使用戶端重試。
  
如果您的 proxy 伺服器需要驗證，則407回應會傳回用戶端。 為了獲得最佳的體驗，請確定您使用的是 Mac 版 Office 組建15.27 或更新版本，因為它們包含使用 NTLM 和 Kerberos 伺服器的特定修正。
  
  
## <a name="see-also"></a>另請參閱

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

