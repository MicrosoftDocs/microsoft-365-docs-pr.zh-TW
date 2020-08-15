---
title: 內容傳遞網路
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: 使用此資訊瞭解 Office 365 如何使用內容傳遞網路 (Cdn) 以提升效能。
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688438"
---
# <a name="content-delivery-networks-cdns"></a>內容傳遞網路（CDNs）

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Cdn 有助於保持 Office 365 快速且可靠的使用者。 雲端服務（例如 Office 365）會使用 Cdn 快取靜態資產，以快取靜態資產，以加速下載速度，並降低感覺到的使用者延遲。 本主題中的資訊可協助您瞭解內容傳遞網路 (Cdn) 以及 Office 365 的使用方式。

## <a name="what-exactly-is-a-cdn"></a>CDN 的確切情況為何？

CDN 是地理位置分散的網路，包含由高速骨幹絡所連接之資料中心的 proxy 和檔案伺服器。 Cdn 是用來減少網站或服務中一組指定檔案和物件的延遲和載入時間。 CDN 可能具有數千個端點，可提供來自任何位置之傳入要求的最佳服務。

Cdn 通常是用來為網站或服務（如 javascript 檔案、圖示及影像）提供更快速的一般內容下載，也可以提供使用者內容的私人存取權，例如 SharePoint 線上文件庫中的檔案、流式媒體檔及自訂程式碼。

Cdn 是大多數 enterprise 雲端服務所使用。 雲端服務（例如 Office 365）有成千上萬的客戶下載混合的專有內容 (例如電子郵件) 和一般內容 (例如，) 一次的圖示。 更有效率的方式是讓每個人使用的影像（像是圖示）盡可能接近使用者的電腦。 在每個大都市區域中（或甚至是全球的每個主要網際網路中樞）都可以建立 CDN 資料中心，而不是每個雲端服務，因此有些 Cdn 是共用的。

## <a name="how-do-cdns-make-services-work-faster"></a>Cdn 如何讓服務運作速度更快？

以網站影像和圖示重新下載等一般物件，可以佔用網路頻寬，可更好地用來下載重要的個人內容，例如電子郵件或檔。 由於 Office 365 使用包含 Cdn 的架構，因此可以從更接近用戶端電腦的伺服器下載圖示、腳本及其他一般內容，使下載速度更快。 這表示更快速存取您的個人內容，該內容會安全地儲存于 Office 365 資料中心。

Cdn 協助您以數種方式改善雲端服務的效能：

- Cdn 將網路和檔案下載無償的一部分從雲端服務中移出，以釋放雲端服務資源，以服務使用者內容和其他服務，方法是減少對靜態資產要求的服務。
- Cdn 是專門構建的功能，可透過實施高效能網路和檔案伺服器，以及利用更新的網路通訊協定（例如 [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) ）來提供低延遲的檔案存取，並以極高的壓縮方式和要求多工。
- CDN 網路使用許多全域分散式端點，讓內容可以盡可能接近使用者。

## <a name="the-office-365-cdn"></a>Office 365 CDN

內建 Office 365 內容傳遞網路 (CDN) 可讓 Office 365 管理員為其組織 SharePoint 線上頁面提供更好的效能，其方式是快取靜態資產，使其更接近要求的瀏覽器，以加速下載並減少延遲時間。 Office 365 CDN 使用 [HTTP/2 通訊協定](https://en.wikipedia.org/wiki/HTTP/2) ，以提升壓縮及下載速度。

> [!NOTE]
> Office 365 CDN 只適用于世界) 雲端的 **實際** 執行 (中的承租人。 美國政府、中國和德國雲彩中的承租人目前不支援 Office 365 CDN。

Office 365 CDN 是由可讓您在多個位置或_來源_主控靜態資產的多個 CDN 組成，並透過全球高速網路提供資產。 根據您要在 Office 365 CDN 中主控的內容類型而定，您可以新增**公用**來源、**私人**來源或兩者。

![Office 365 CDN 概念圖表](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 概念圖表")

Office 365 CDN 內**公用**來源中的內容可透過匿名方式存取，並且可供具有託管資產 URL 的任何人存取。 因為對公用來源中內容的存取是匿名的，您應該只使用公用來源來快取非敏感性的一般內容，例如 javascript 檔案、指令碼、圖示和影像。 預設會使用 Office 365 CDN 來從公開來源下載一般資源資產，例如 Office 365 用戶端應用程式。

Office 365 CDN 內的**私人**來源可提供使用者內容的私人存取權，例如 SharePoint 線上文件庫、網站和專有影像。 對私人來源中內容的存取會使用動態產生的權杖來保護，使得它只能供具有原始文件庫或儲存位置權限的使用者存取。 Office 365 CDN 中的私人來源僅能用於 SharePoint Online 內容，並且您只能透過從您的 SharePoint Online 租用戶重新導向來存取資產。

Office 365 CDN 服務包含在 SharePoint Online 訂閱的一部分。

如需如何使用 Office 365 CDN 的詳細資訊，請參閱 [使用 office 365 content 傳遞網路與 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。

若要觀看一系列簡短影片，以提供有關使用 Office 365 CDN 的概念性和 HOWTO 資訊，請造訪 [SharePoint 開發人員模式和慣例 YouTube 通道](https://aka.ms/sppnp-videos)。

## <a name="other-microsoft-cdns"></a>其他 Microsoft Cdn

雖然不是 Office 365 CDN 的一部分，但您可以在 Office 365 租使用者中使用這些 Cdn，以存取屬於 Office 365 CDN 範圍之外的 SharePoint 開發庫、自訂程式碼和其他用途。

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>從第 3 2020 季度開始，SharePoint 線上將開始在 Azure CDN 上快取影片，以支援改善的播放和可靠性。 流行影片將會從最接近使用者的 CDN 端點流向。 此資料將保留在 Microsoft 365 合規性界限內。 這是所有承租人的免費服務，且不需要任何客戶行動可供設定。

您可以使用 **AZURE cdn** 來部署您自己的 CDN 實例，以裝載自訂網頁元件、文件庫及其他資源資產，這可讓您將存取金鑰套用至 cdn 儲存區，以及對 cdn 設定進行更好的控制。 使用 Azure CDN 不是免費的，需要 Azure 訂閱。

如需如何設定 Azure CDN 實例的詳細資訊，請參閱 [快速入門：整合 azure storage account With AZURE cdn](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)。

如需 Azure CDN 如何用來主控 SharePoint 網頁元件的範例，請參閱 [將您的 SharePoint 用戶端網頁元件部署至 AZURE CDN](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)。

如需 Azure CDN PowerShell 模組的相關資訊，請參閱 [使用 PowerShell 管理 AZURE cdn](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell)。

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft 的 **AJAX cdn** 是一種唯讀的 cdn，可提供許多流行的開發文件庫，包括 jQuery (和其所有其他文件庫) 、ASP.NET Ajax、啟動、Knockout.js 及其他。
  
若要在專案中包含這些腳本，只需以 CDN 位址的參照取代這些已公開可用之文件庫的任何參照，而不需將其包含在專案本身內。 例如，使用下列程式碼連結到 jQuery：

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

如需如何使用 Microsoft Ajax CDN 的詳細資訊，請參閱 [Microsoft AJAX cdn](https://docs.microsoft.com/aspnet/ajax/cdn/overview)。

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Office 365 如何使用 CDN 的內容？

不論您為 Office 365 租使用者設定什麼 CDN，基本資料檢索程式都是相同的。

1. 您的用戶端 (瀏覽器或 Office 用戶端應用程式) 要求來自 Office 365 的資料。

2. Office 365 您可以直接將資料傳回給用戶端，如果資料是 CDN 所主控之一組內容的一部分，就會將用戶端重新導向至 CDN URL。

    a. 如果資料已經快取到 _公用_ 來源，您的用戶端將直接從最近的 CDN 位置下載資料至用戶端。

    b. 如果資料已經快取到 _私人_ 來源中，則 CDN 服務會檢查您的 Office 365 使用者帳戶在原始位置的許可權。 如果您有許可權，SharePoint 線上會以自動方式產生自訂 URL，此 URL 由 CDN 和兩個存取權杖中的資產路徑組成，並傳回用戶端的自訂 URL。 您的用戶端會使用自訂 URL，直接從最近的 CDN 位置將資料下載至用戶端。

3. 如果資料未在 CDN 上快取，則 CDN 節點會從 Office 365 要求資料，然後在用戶端下載資料後，快取資料一段時間。

CDN 會將最接近的資料中心輸出至使用者的瀏覽器，並使用重新導向從那裡下載所要求的資料。 CDN 重新導向是快速的，可節約使用者許多下載時間。

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>我應該如何設定我的網路，讓 Cdn 最適合搭配 Office 365 運作？

最小化網路上用戶端與 CDN 端點之間的延遲是確保最佳效能的主要考慮。 您可以使用 [管理 Office 365 端點](managing-office-365-endpoints.md) 中所述的最佳作法，以確保網路設定允許用戶端瀏覽器直接存取 CDN，而不是透過中央 PROXY 路由 cdn 流量，以避免引入不必要的延遲。

您也可以閱讀 [office 365 網路連線原則](https://aka.ms/o365networkingprinciples) ，以瞭解優化 Office 365 網路效能背後的概念。

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Office 365 所使用的所有 Cdn 清單是否列出？

Office 365 所使用的 Cdn 永遠都可能變更，而且在許多情況下，事件中所設定的多個 CDN 夥伴無法使用。 Office 365 使用的主要 Cdn 包括：

|CDN  |Company  |Usage  |連結  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |公用來源中的一般資產，SharePoint 私人來源中的使用者內容         |[使用 Office 365 內容傳遞網路與 SharePoint 線上](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |微軟         |自訂程式碼，SharePoint 架構解決方案         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (唯讀)      |微軟         |適用于 Ajax、jQuery、ASP.NET、啟動、Knockout.js 等的常見文件庫。         |[Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>CDN 提供了哪些效能提升功能？

在評估直接從 Office 365 下載之資料與從特定 CDN （如您的承租人相關的位置）與從特定 CDN 下載的資料之間，有許多因素會有許多因素，例如，您的承租人所提供的頁面上的資產數量，以及網路延遲及頻寬的暫時性變更。 不過，簡單的 A/B 測試可協助顯示特定檔案的下載時間差異。

下列螢幕擷取畫面說明 Office 365 的原生檔案位置與 [Microsoft Ajax 內容傳遞網路](https://docs.microsoft.com/aspnet/ajax/cdn/overview)上主控的相同檔案之間的下載速度差異。 這些螢幕擷取畫面位於 Internet Explorer 11 開發人員工具的 [ **網路** ] 索引標籤中。 這些螢幕擷取畫面顯示熱門文件庫 jQuery 上的延遲。 若要開啟此畫面，請在 Internet Explorer 中按 **F12** ，然後選取 [ **網路** ] 索引標籤，該索引標籤會以 Wi-Fi 圖示 symbolized。
  
![F12 網路的螢幕擷取畫面](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
這個螢幕擷取畫面會顯示上傳至主版頁面圖庫的文件庫，位於 SharePoint 線上網站本身。 上傳文件庫所需的時間是1.51 秒。
  
![載入時間為 1.51 秒的螢幕擷取畫面](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
第二個螢幕擷取畫面顯示的是 Microsoft CDN 所傳遞的同一個檔案。 這段時間的延遲大約是496毫秒。 這是一種大量改進，會顯示整秒的 shaved，以下載該物件的總時間。
  
![載入時間為 469 毫秒的螢幕擷取畫面](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>資料是否安全？

我們非常小心謹慎，以保護執行您公司的資料。 儲存在 Office 365 CDN 中的資料會在傳輸和靜止時加密，存取 Office 365 中的資料 SharePoint CDN 是由 Office 365 使用者許可權和權杖授權所保護。 Office 365 SharePoint CDN 中的資料要求必須從您的 Office 365 租使用者 (重新導向) ，否則不會產生授權權杖。

為了確保您的資料仍然安全，我們建議您不要將使用者內容或其他敏感性資料儲存在公用 CDN 中。 因為存取公用 CDN 的資料是匿名的，所以 public Cdn 只應該用來主控一般內容，例如 web 腳本檔案、圖示、圖像及其他非機密資產。

> [!NOTE]
> 協力廠商 CDN 提供者可能具有與 Office 365 信任中心所述的承諾不同的隱私權和符合性標準。 透過 CDN 服務快取的資料可能不符合 DPT) 中的 Microsoft 資料處理 (字詞，而且可能位於 Office 365 信任中心的相容性界限內。

如需有關 Office 365 CDN 提供者隱私權和資料保護的深入資訊，請造訪下列專案：  

- 深入瞭解[Microsoft 信任中心](https://www.microsoft.com/trustcenter)的 Office 365 隱私權和資料保護
- 深入瞭解[Akamai 隱私權信任中心](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)的 Akamai 隱私權和資料保護
- 深入瞭解[Azure 信任中心](https://azure.microsoft.com/overview/trusted-cloud/)azure 隱私權和資料保護

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>如何在所有的協力廠商服務中保護我的網路？

利用一組廣泛的合作夥伴服務，可讓 Office 365 在使用 Office 365 時，擴充和滿足可用性需求，同時增強使用者體驗。 協力廠商服務 Office 365 會同時包含憑證吊銷清單;例如 crl.microsoft.com 或 sa.symcb.com，以及 Cdn;例如 r3.res.outlook.com。 Office 365 所產生的每一個 CDN FQDN 是 Office 365 的自訂 FQDN。 如果您是在 Office 365 要求傳送至 FQDN，您可以確信 CDN 提供者可以控制該位置的 FQDN 和基礎內容。
  
若客戶想要將 Microsoft 或 Office 365 資料中心的要求與目標為協力廠商的要求分開，我們已撰寫 [管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)的指導方針。

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>是否有所有利用 Cdn 的 Fqdn 清單？

Fqdn 清單，以及如何利用 Cdn 隨時間而變更的方式。 請參閱《發行的 [Office 365 URLs 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkID=293744) 」頁面，以取得利用 cdn 的最新 fqdn 的最新狀態。

您也可以使用 [office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md) ，要求目前的 Office 365 URLs 和以 CSV 或 JSON 格式格式化的 IP 位址範圍。

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>我是否可以在本機網路上使用自己的 CDN 及快取內容？

我們不斷尋找新的方法來支援客戶的需求，而且目前探索使用快取 proxy 解決方案和其他內部部署 CDN 解決方案。

雖然這不是 Office 365 CDN 的一部分，但您也可以使用 **AZURE CDN** 來裝載自訂網頁元件、文件庫及其他資源資產，這可讓您將存取金鑰套用至 cdn 儲存區，並對 cdn 設定進行更好的控制。 使用 Azure CDN 不是免費的，需要 Azure 訂閱。 如需如何設定 Azure CDN 實例的詳細資訊，請參閱 [快速入門：整合 azure storage account With AZURE cdn](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)。

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>我使用的是 Office 365 的 Azure ExpressRoute，是否會變更專案？

[Azure ExpressRoute For office 365](azure-expressroute.md) ，提供與公用網際網路隔離之 office 365 基礎結構的專用連線。 這表示用戶端仍需要透過非 ExpressRoute 連線進行連線，以連接至 Cdn，以及未明確包含 ExpressRoute 所支援之服務清單中的其他 Microsoft 基礎結構。 如需如何路由傳送特定流量的詳細資訊（例如發 Cdn 的要求），請參閱 [Office 365 網路流量管理](routing-with-expressroute.md)。

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>我可以搭配使用 Cdn 與 SharePoint Server 內部部署嗎？

使用 Cdn 只會在 SharePoint Online 內容中有意義，而且應避免 SharePoint 伺服器。 這是因為地理位置的所有優點都不會保留為 true，如果伺服器位於內部部署或同時關閉。 此外，如果有網路連接至其所主控的伺服器上，則可以在未使用網際網路連線的情況下使用該網站，因此無法取得 CDN 檔案。 否則，您應該使用 CDN （如果您的網站所需的文件庫和檔案可用且穩定）。
  
您可以使用下列短連結返回這裡：[https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>另請參閱

[Office 365 網路連線原則](https://aka.ms/o365networkingprinciples)

[評估 Office 365 的網路連線能力](assessing-network-connectivity.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[使用 Office 365 內容傳遞網路與 SharePoint 線上](use-microsoft-365-cdn-with-spo.md)

[Microsoft 信任中心](https://www.microsoft.com/trustcenter)

[調整 Office 365 效能](tune-microsoft-365-performance.md)
