---
title: 新版 Microsoft Edge
description: 說明如何部署及更新新的 Edge browser
keywords: 瀏覽器、Microsoft 受管理的電腦、Microsoft 365、服務、檔
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822247"
---
# <a name="new-microsoft-edge-app"></a>新 Microsoft Edge 應用程式

新的[Microsoft Edge 瀏覽器](https://www.microsoft.com/edge)提供世界一流的效能，在您流覽時，會有更多隱私權、更高生產力和更多的價值。 Microsoft 受管理的電腦提供在您的環境中部署新 Edge browser 的公開預覽。

## <a name="initial-deployment"></a>初始部署

若要將您的 Microsoft 受管理的電腦裝置遷移至新的 Microsoft Edge 瀏覽器，請透過 Microsoft 受管理的電腦入口網站，將 IT 支援票證檔。 當您為票證進行檔案時，我們會將 Edge 穩定通道部署到測試群組，然後在每個後續的部署群組中每隔24小時部署一次。 若要暫停部署，請 file 另一個票證要求作業保留。

[測試通道](/deployedge/microsoft-edge-channels#beta-channel)也可在組織中要求代表驗證的要求。 Microsoft 受管理的電腦會依照測試和第一個群組的需要部署應用程式，這樣，除了穩定通道之外，所有使用者都有 Beta 通道。 對於任何需要存取 Beta 通道的其他使用者，請將其新增至 **新式的 Workplace Edge Beta 使用者** 群組，並將其從公司入口網站進行安裝。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge 的更新

Microsoft 受管理的電腦部署 Microsoft Edge 的[穩定通道](/deployedge/microsoft-edge-channels#stable-channel)，它會每六周自動更新一次。 「Microsoft Edge 產品群組」會[逐步](/deployedge/microsoft-edge-update-progressive-rollout)展開穩定通道上的更新，以確保客戶獲得最佳的體驗。 

測試和第一個群組中的裝置會部署 [Beta 通道](/deployedge/microsoft-edge-channels#beta-channel) 至組織內的代表驗證。 此通道完全受支援，且每六周大約會以新功能自動更新。

為了確保 Microsoft Edge 能夠正確地更新，請勿修改 Microsoft Edge[更新原則](/deployedge/microsoft-edge-update-policies)。



## <a name="settings-managed-by-microsoft-managed-desktop"></a>由 Microsoft 受管理的電腦管理設定

Microsoft 受管理的電腦已建立一組預設原則，以保護瀏覽器的 Microsoft Edge。 預設瀏覽器設定如下：

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 擴充

Microsoft 受管理的電腦裝置上 Microsoft Edge 的安全性基準會設定兩個原則，以停用所有的 Chrome 副檔名及安全的使用者。 若要在您的環境中啟用及部署擴充功能，請參閱您管理的設定。 

#### <a name="extension-installation-blocklist"></a>擴充安裝 blocklist
**預設值：** 所有

Microsoft 受管理的電腦設定此原則，以防止在受管理的端點上安裝 Chrome 擴充功能。 有與 Chromium 延伸模組相關的已知風險，包括資料遺失防護、隱私權及可能危及裝置的其他威脅。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>允許未以系統管理員許可權安裝的使用者層級原生郵件主機 () 

**預設值：** 禁用

停用此原則之後，Microsoft Edge 只會使用系統層級上安裝的原生郵件主機。 原生郵件主機是 Chrome extensions 的一部分，可讓瀏覽器與使用者端點的其他部分互動，以建立各種安全性考慮。  

### <a name="secure-sockets-layer-tlsssl"></a>安全通訊端層 (TLS/SSL) 

#### <a name="minimum-tls-version"></a>最低 TLS 版本

**預設值：** 支援的最小 TLS 1。2

如果您想要使用較不安全的 TLS 1.1，您可以將要求歸檔以進行此作業。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>允許使用者從 [SSL 警告] 頁面繼續。

**預設值：** 禁用

建議您不要啟用此設定，因為它可讓使用者透過 TSL 錯誤來訪問網站。

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>設定 Windows Defender SmartScreen

**預設值：** 啟用

預設為啟用，以協助保護使用者。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender網站的 SmartScreen 提示

**預設值：** 啟用

[！附注] 建議您不要停用此設定，因為這樣可讓使用者忽略警告，並繼續進行可能惡意的網站。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>避免繞過下載的 Windows Defender SmartScreen 警告

**預設值：** 啟用

建議您不要停用此設定，因為這樣可讓使用者忽略警告，並完成未驗證的下載。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>預設 Adobe Flash 設定

**預設值：** 禁用

因為有相關的安全性風險，所以不建議使用 Flash。 如果您仍然有依賴 Flash 的進程，請設定 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 原則，為需要它的網站啟用 Flash。 如果您無法保留允許的網站清單以使用 Flash，請提交變更要求，以變更值以 **按一下 [播放**]，這可讓使用者選擇適當的時間來執行 flash。

### <a name="password-manager"></a>密碼管理員

#### <a name="enable-saving-passwords-to-the-password-manager"></a>啟用將密碼儲存至密碼管理員

**預設值：** 禁用

密碼管理員預設為停用。 如果您已啟用這項功能，請歸檔支援要求和我們的服務工程師可以在您的環境中啟用此設定。 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Microsoft Edge 的 Internet Explorer 模式
Microsoft Edge 的 IE 模式可讓您輕鬆地在單一瀏覽器中使用貴組織所需的所有網站。 它會針對與 Chromium 轉譯引擎相容的網站使用整合的 Chromium 引擎，並使用 Internet Explorer 11 (IE11) 的 Trident MSHTML 引擎，以取得 IE 功能上沒有相關性的網站。 [深入了解](/DeployEdge/edge-ie-mode) 

Microsoft 受管理的電腦預設會啟用裝置的 Internet Explorer 模式 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer 模式整合
**預設值：** Internet Explorer 模式

依預設，裝置會設定為使用 Internet Explorer 模式，但您可以將其設定為在獨立的 Internet Explorer 11 視窗中開啟網站。 若要變更此行為，請歸檔支援要求。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>將網站新增至 Enterprise 模式網站清單
若要在 Internet Explorer 模式中開啟網站，您必須將它們包含在 [ [Enterprise 網站] 清單](/DeployEdge/edge-ie-mode-sitelist)中。 維護和部署 Enterprise 網站清單是您的責任。 如需詳細資訊，請參閱[使用設定 Enterprise 模式網站清單原則設定](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>其他設定

#### <a name="enable-site-isolation-for-every-site"></a>針對每個網站啟用網站隔離

**預設值：** 啟用

啟用此原則時，使用者將無法選擇每個網站在自己的處理中執行的預設行為。

#### <a name="supported-authentication-schemes"></a>支援的驗證架構

**預設值：** NTLM、協商

Microsoft 受管理的電腦不支援基本或摘要驗證架構。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>在第一次執行時自動匯入另一個瀏覽器的資料和設定

**預設值：** 從預設瀏覽器自動匯入所有支援的資料類型和設定 

套用此原則之後，初次執行體驗將會略過 [匯入] 區段，最小化使用者互動。 不論此設定為何，當第一次執行時，就會自動遷移舊版 Microsoft Edge 的瀏覽器資料。 


## <a name="settings-you-manage"></a>您管理的設定

您可以使用 Microsoft Intune 中的 [系統管理範本] 設定檔，部署先前未述的任何 Microsoft Edge 設定。 如需詳細資訊，請參閱[使用 Microsoft Intune 設定 Microsoft Edge 原則設定](/deployedge/configure-edge-with-intune)。 如果您想要評估目前未包含在 intune Microsoft Edge 系統管理範本中的原則，您可以在 intune 中使用 Windows 10 裝置的自訂設定。

### <a name="enabling-specific-chrome-extensions"></a>啟用特定的 Chrome 副檔名

系統管理範本提供使用 Microsoft Intune 來部署特定 Chrome extensions 的設定。 您可以在 [**電腦設定 >] Microsoft Edge > 分機 > 允許安裝特定的分機**] 中找到它。

### <a name="install-extensions-silently"></a>無訊息安裝分機

您也可以使用系統管理範本，設定 Microsoft Edge 以安裝分機，而不會提醒使用者。 您可以在 [電腦設定 > Microsoft Edge > 分機] 中找到它， **> 控制以無訊息方式安裝的分機** 號碼。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge 更新原則
為了確保 Microsoft Edge 能夠正確地更新，請勿修改 Microsoft Edge[更新原則](/deployedge/microsoft-edge-update-policies)。

### <a name="other-common-enterprise-policies"></a>其他常見的企業原則

Microsoft Edge 提供很多其他的原則。 以下是一些較為常見的專案：
 
- [設定 Enterprise 網站清單和 IE 模式的網站](/deployedge/edge-ie-mode-sitelist)
- [設定啟動、首頁及新的索引標籤頁面設定](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [設定衝浪遊戲設定](/deployedge/microsoft-edge-policies#allowsurfgame)
- [設定 proxy 伺服器設定](/deployedge/microsoft-edge-policies#proxy-server)
