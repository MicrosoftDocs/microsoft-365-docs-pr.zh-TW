---
title: 使用) 線上 Office 365 內容傳遞網路 (CDN SharePoint
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: 瞭解如何使用 Office 365 內容傳遞網路 (CDN) ，以加速 SharePoint 的線上資產的傳遞。
ms.openlocfilehash: e6cce93be0e8d893d68ae8bcdb15fde325a2cb59
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169553"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online

您可以使用內建的 Office 365 內容傳遞網路 (CDN) 來主控靜態資產，為您的 SharePoint網頁提供更佳的效能。 Office 365 CDN 透過將靜態資產快取到更靠近提出要求之瀏覽器的位置 (這有助於加速下載以及減少延遲)，藉此改善效能。 此外，Office 365 CDN 使用[HTTP/2 通訊協定](https://en.wikipedia.org/wiki/HTTP/2)，以提升壓縮和 HTTP 流水線。 Office 365 CDN 服務包含在 SharePoint Online 訂閱的一部分。

> [!NOTE]
> Office 365 CDN 僅可用於 **實際** 執行 (全球) 雲端的承租人。 美國政府、中國和德國雲彩中的承租人目前不支援 Office 365 CDN。

Office 365 CDN 是由可讓您在多個位置或 _來源_ 主控靜態資產的多個 CDN 組成，並透過全球高速網路提供資產。 根據您要在 Office 365 CDN 中主控的內容類型而定，您可以新增 **公用** 來源、**私人** 來源或兩者。 請參閱 [選擇是否每個來源都應該是公開或私人](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 的，如需公開和私人來源之間差異的詳細資訊。

![Office 365 CDN 概念圖表](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 概念圖表")

如果您已熟悉 cdn 的運作方式，您只需要完成少數幾個步驟即可啟用租使用者的 Office 365 CDN。 本主題說明如何進行。 如需如何開始主控靜態資產的詳細資訊，請參閱。

> [!TIP]
> 有其他可與 Office 365 搭配特殊的使用情形搭配使用的 Microsoft 主控 cdn，但不會在本主題中討論，因為它們超出 Office 365 CDN 的範圍。 如需詳細資訊，請參閱 [其他 Microsoft cdn](content-delivery-networks.md#other-microsoft-cdns)。

 **回到 [Office 365 的網路規劃和效能調整](./network-planning-and-performance.md)。**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>在 SharePoint Online 中使用 Office 365 CDN 的概覽

若要為您的組織設定 Office 365 CDN，請遵循下列基本步驟：

+ [規劃 Office 365 的部署 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [決定要在 CDN 上主控的靜態資產](use-microsoft-365-cdn-with-spo.md#CDNAssets)。
  + [決定您要儲存資產的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。 此位置可以是 SharePoint 網站、文件庫或資料夾，也稱為 _來源_。
  + [選擇每個原產地應為 public 或 private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。 您可以新增公用及私人類型的多個來源。

+ 使用 PowerShell 或 SharePoint 線上 CLI 設定及設定 CDN

  + [使用 SharePoint Online 管理命令介面來設定及設定 CDN](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [使用 PnP 設定及設定 CDN PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [使用 Office 365 CLI 安裝及設定 CDN](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  當您完成此步驟後，您將會有：

  + 已為您的組織啟用 CDN。
  + 新增您的來源，將每個原產地識別為 public 或 private。

當您完成設定之後，您可以依下列方式[管理 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) ：
  
+ 新增、更新及移除資產
+ 新增及移除來源
+ 設定 CDN 原則
+ 如有必要，停用 CDN

最後，請參閱[使用您的 CDN 資產](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)，以瞭解從公用和私人來源存取您的 CDN 資產。

請參閱[疑難排解 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) ，以取得解決常見問題的指導。

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>規劃 Office 365 的部署 CDN

在您部署 Office 365 租使用者的 Office 365 CDN 之前，您應該考慮下列因素做為規劃程式的一部分。

  + [決定要在 CDN 上裝載的靜態資產](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [決定您要儲存資產的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [選擇每個原產地應該是公用還是私人](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>決定要在 CDN 上裝載的靜態資產

一般說來，Cdn 對於主控 _靜態資產_ 或不經常變更的資產會最為有效。 合理的經驗法則是找出符合部分或所有條件的檔案：

+ 內嵌在頁面中的靜態檔案 (像是腳本和影像) 可能會對頁面載入時間產生重大的增量影響
+ 類似可執行檔和安裝檔案的大型檔案
+ 支援用戶端程式代碼的資源庫

例如，重複要求的小型檔案（如網站影像和腳本）可大幅改善網站轉譯效能，並在您將 SharePoint 線上網站新增至 CDN 原始時，以增量方式減少其負載。 您可以從 CDN 下載較大的檔案，例如安裝可執行檔，對 SharePoint Online 網站上的負載產生積極效能的影響，以及後續的負載，即使不經常存取，也是如此。

每個檔案的效能提升都取決於許多因素，包括用戶端接近最接近的 CDN 端點、本機網路上的暫時性情況等等。 許多靜態檔案都很小，而且可以從 Office 365 中下載的時間不到一秒。 不過，網頁上可能會包含許多內嵌檔案，且累計下載時間為數秒。 從 CDN 提供這些檔案可大幅減少整體頁面載入時間。 請參閱[CDN 提供什麼效能提升？](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)範例。

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>決定您要儲存資產的位置

CDN 會從稱為 _來源_ 的位置提取資產。 來源可以是可透過 URL 存取的 SharePoint 網站、文件庫或資料夾。 當您為組織指定來源時，具有極大的彈性。 例如，您可以指定多個來源或單一原始位置，以放置所有的 CDN 資產。 您可以選擇同時包含組織的公開來源或私人來源。 大多陣列織會選擇實現兩者的組合。

您可以為您的來源建立新的容器，例如資料夾或文件庫，以及新增您要從 CDN 提供的檔案。 如果您有一組特定的資產可供 CDN 使用，而且想要將一組 CDN 資產限制為僅限容器中的檔案，這是一種很好的方法。

您也可以將現有的網站集合、網站、文件庫或資料夾設定為來源，使該容器中的所有合格資產都可以從 CDN 中取得。 在您將現有的容器新增為來源之前，請務必確定您已知道其內容和許可權，這樣就不會無意公開資產給匿名存取或未經授權的使用者。

您可以定義 _CDN 原則_，以從 CDN 中排除來源的內容。 CDN 原則會透過諸如 _檔案類型_ 和 _網站分類_ 等屬性，將資產公開或私人來源，套用至您在原則中指定 (私人或公開) 的 CdnType 的所有來源。 例如，如果您新增包含多個子網站之網站的私人來源，您可以定義一個原則，以排除標示為 **機密** 的網站，這樣就不會從 CDN 提供該分類所套用之網站的內容。 原則會套用至您已新增至 CDN 之 _所有_ 私人來源的內容。
  
請記住，來源數量越高，CDN 服務處理要求所需時間的影響就會越大。 建議您盡可能限制來源數量。
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>選擇每個原產地應該是公用還是私人

當您識別來源時，請指定是否應該 _公開_ 或 _私密_。 公用來源中 CDN 資產的存取權是匿名的，而私人來源的 CDN 內容則是透過動態產生的權杖來保護，以獲得較高的安全性。 不論您選擇哪個選項，當您負責管理 CDN 時，Microsoft 都會執行所有繁重的動作。 此外，您還可以在您設定 CDN 並識別來源後，再變更您的想法。

公用和私人選項都提供類似的效能提升，但各項都有獨特的屬性和優點。

Office 365 CDN 內的 **公開** 來源可以匿名方式存取，且具有資產 URL 的任何人都可以存取主控資產。 因為對公用來源中內容的存取是匿名的，您應該只使用公用來源來快取非敏感性的一般內容，例如 JavaScript 檔案、指令碼、圖示和影像。

Office 365 內的 **私人** 來源 CDN 提供使用者內容的私人存取，例如 SharePoint 線上文件庫、網站和專有圖像。 存取私人來源中的內容是以動態產生的標記來保護，所以只有具有原始文件庫或儲存位置許可權的使用者可以存取私人來源中的內容。 Office 365 CDN 中的私人來源只能用於 SharePoint 線上內容，而且您只能透過從您的 SharePoint Online 租使用者重新導向，存取私人來源中的資產。

您可以深入瞭解如何[使用私人](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)來源中的資產，對私人來源中的資產 CDN 存取權如何運作。

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>在公用來源中主控資產的屬性與優點
  
+ 公用來源中公開的資產可供任何人匿名存取。
    > [!IMPORTANT]
    > 您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。

+ 如果您移除公用來源中的資產，該資產可持續從快取的30天內可用;不過，我們會在15分鐘內使 CDN 的資產連結無效。

+ 當您主控樣式表單 (CSS 檔案) 公用來源中，您可以使用相對路徑，並在程式碼中 URIs。 這表示您可以參照背景圖像的位置，以及與呼叫它之資產所在位置相關的其他物件。

+ 雖然您可以建立公用來源的 URL，但是請務必小心，並確定您使用頁面內容屬性，並遵循執行此動作的指導方針。 原因是，如果無法存取 CDN，URL 將不會自動解析為您的組織在您的 SharePoint 線上中，可能會造成損毀的連結及其他錯誤。 URL 也會變更，原因是它不應該只是硬編碼為目前的值。

+ Public 來源包含的預設檔案類型為： .css，eot，.gif，.ico，jpeg，.jpg，.js，.map，.png，ttf，，woff 和 woff2。 您可以指定其他檔案類型。

+ 您可以設定原則，以排除已由您指定之網站分類所識別的資產。 例如，您可以選擇排除標記為「機密」或「限制」的所有資產，即使這些資產是允許的檔案類型，而且位於公用來源。

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>主控資產私人來源的屬性與優點

+ 私人來源僅可用於 SharePoint 線上資產。

+ 如果使用者具有存取容器的許可權，則使用者只能存取其私人來源中的資產。 禁止匿名存取這些資產。

+ 私人來源中的資產必須從 SharePoint Online 租使用者參考。 對私人 CDN 資產的直接存取無法運作。

+ 如果您移除私人來源中的資產，該資產可能會持續從快取的一小時內可用;不過，我們會在移除資產的15分鐘內，使 CDN 中的資產連結無效。

+ 私人來源所包含的預設檔案類型為 .gif、.ico、jpeg、.jpg、.js 及 .png。 您可以指定其他檔案類型。

+ 就像公開來源一樣，您可以設定原則，以排除已透過網站分類識別的資產，即使您使用萬用字元包含資料夾或文件庫中的所有資產也是一樣。

如需有關如何使用 Office 365 CDN 的詳細資訊，請參閱一般 CDN 概念，以及您可以搭配 Office 365 租使用者使用的其他 Microsoft cdn，請參閱[Content 傳遞網路](content-delivery-networks.md)。

### <a name="default-cdn-origins"></a>預設 CDN 來源

除非另有指定，否則 Office 365 會在您啟用 Office 365 CDN 時，為您設定某些預設來源。 如果您最初選擇不進行布建，您可以在完成安裝後新增這些來源。 除非您瞭解忽略預設來源設定的結果，並有特定原因要執行此操作，否則您應允許在啟用 CDN 時建立這些結果。
  
預設私人 CDN 來源：
  
+ \*/userphoto.aspx
+ \*/siteassets

預設公用 CDN 來源：
  
+ \*/masterpage
+ \*/style 程式庫
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ 是預設公用來源，已新增至2017年12月 Office 365 CDN 服務。 此來源必須存在，CDN 中的 SharePoint 架構解決方案才能正常運作。 如果您已在2017年12月之前啟用 Office 365 CDN，或在啟用 CDN 時略過預設值的設定，則可以手動新增此來源。 如需詳細資訊，請參閱[我的用戶端網頁元件或 SharePoint 架構解決方案無法運作](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>使用 SharePoint 線上管理命令介面來設定及設定 Office 365 CDN

本節中的程式需要您使用 SharePoint 線上管理命令介面，連線至 SharePoint 線上。 如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

完成下列步驟，以使用 SharePoint 線上管理命令介面，來設定和設定 CDN，以在 SharePoint 線上中主控您的資產。

<details>
  <summary>按一下以展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>讓您的組織使用 Office 365 CDN

變更租使用者 CDN 設定之前，您應該先在 Office 365 租使用者中取得私人 CDN 設定的目前狀態。 使用 SharePoint 線上管理命令介面連線租使用者：

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

現在使用 **SPOTenantCdnEnabled 指令程式**，從承租人中取得 CDN 狀態設定：

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

指定 CdnType 的 CDN 狀態會輸出至螢幕。

使用 **SPOTenantCdnEnabled 指令程式** 可讓您的組織使用 Office 365 CDN。 您可以讓組織同時使用公用來源、私人來源或同時使用這兩者。 您也可以設定 CDN 在啟用時略過預設來源的設定。 您可以隨時依照本主題所述新增這些來源。
  
在 Windows PowerShell 中 SharePoint Online：

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

例如，若要讓您的組織同時使用公用和私人來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

若要讓您的組織同時使用公用和私人來源，但略過設定預設來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

如需啟用 Office 365 CDN 時預設提供的來源相關資訊，請參閱[預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)，以及略過設定預設來源的潛在影響。

若要讓您的組織使用公用來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

若要讓您的組織使用私人來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

如需此 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>變更要包含在 Office 365 CDN (選用) 的檔案類型清單。

> [!TIP]
> 當您使用 **SPOTenantCdnPolicy** 指令程式來定義檔案類型時，會覆寫目前定義的清單。 如果您想要將其他檔案類型新增至清單，請先使用 Cmdlet 來找出已允許的檔案類型，並將其包含在清單中，以及新的檔案類型。
  
使用 **SPOTenantCdnPolicy 指令程式**，定義可由 CDN 中的公開和私人來源主控的靜態檔案類型。 根據預設，允許一般資產類型，例如 .css、.gif、.jpg 及 .js。

在 Windows PowerShell 中 SharePoint Online：

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

例如，若要啟用 CDN 以主控 .css 及 .png 檔案，您可以輸入下列命令：

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

若要查看 CDN 目前允許的檔案類型，請使用 **SPOTenantCdnPolicies** Cmdlet：

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

如需這些 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 和 [SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)。

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>變更您想要從 Office 365 CDN 中排除的網站分類清單 (選用) 

> [!TIP]
> 當您使用 **SPOTenantCdnPolicy** 指令程式排除網站分類時，會覆寫目前定義的清單。 如果您想要排除其他網站分類，請先使用 Cmdlet 來找出已排除的分類，然後將其新增至新的分類。

您可以使用 **SPOTenantCdnPolicy 指令程式** 來排除您不想讓 CDN 使用的網站分類。 根據預設，不會排除任何網站分類。

在 Windows PowerShell 中 SharePoint Online：

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

若要查看目前限制的網站分類，請使用 **SPOTenantCdnPolicies** Cmdlet：

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

將傳回的屬性為 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 及 _ExcludeIfNoScriptDisabled_。

_IncludeFileExtensions_ 屬性包含將從 CDN 提供的副檔名清單。

> [!NOTE]
> 預設副檔名在 public 和 private 之間是不同的。

_ExcludeRestrictedSiteClassifications_ 屬性包含您要從 CDN 中排除的網站分類。 例如，您可以排除標記為 **機密** 的網站，以便不會從 CDN 提供套用該分類之網站的內容。

_ExcludeIfNoScriptDisabled_ 屬性會根據網站層級 _NoScript_ 屬性設定，從 CDN 中排除內容。 根據預設，會將 _NoScript_ 屬性設定為 _新式_ 網站 **啟用**，並針對 _傳統_ 網站 **停用**。 這取決於您的租使用者設定。

如需這些 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 和 [SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)。

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>新增資產來源

使用 **SPOTenantCdnOrigin 指令程式** 來定義原點。 您可以定義多個來源。 來源是指向包含您要由 CDN 主控的資產的 SharePoint 文件庫或資料夾的 URL。
  
> [!IMPORTANT]
> 您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_Path_ 的值是包含資產之文件庫或資料夾的相對路徑。 除了相對路徑之外，您還可以使用萬用字元。 來源支援在 URL 前面加上萬用字元。 這可讓您建立跨越多個網站的來源。 例如，若要將所有網站的所有資產都納入 CDN 中的公開來源，請輸入下列命令：

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 萬用字元修飾符 * **/** 只能在路徑的開頭使用，而且會比對指定之 url 底下的所有 URL 段。
+ 路徑可以指向文件庫、資料夾或網站。 例如，路徑 _*/site1_ 會比對網站底下的所有文件庫。

您可以使用特定的相對路徑來新增原點。 您無法使用完整路徑新增原點。

在這個範例中，會在特定網站上新增 siteassets 程式庫的私人來源：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

在這個範例中，會在網站集合的網站資產庫中新增 _folder1_ 資料夾的私人來源：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

如果路徑中有空格，您可以使用雙引號括住路徑，也可以使用 URL 編碼 %20 取代空格。 下列範例會在網站集合的 [網站資產] 文件庫中新增 _資料夾 1_ 資料夾的私人來源：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

> [!NOTE]
> 在 [私人來源] 中，從來源共用的資產必須先發行主要版本，才能從 CDN 中存取。
  
當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>範例：針對線上 SharePoint 設定主版頁面和樣式庫的公開來源

一般來說，當您啟用 Office 365 CDN 時，會預設為您設定這些來源。 不過，如果您想要手動啟用它們，請遵循下列步驟。
  
+ 使用 **SPOTenantCdnOrigin 指令程式** ，將樣式庫定義為公用來源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ 使用 **SPOTenantCdnOrigin 指令程式** ，將主版頁面定義為公用來源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>範例：針對線上 SharePoint 設定網站資產、網站頁面及發佈影像的私人來源

+ 使用 **SPOTenantCdnOrigin 指令程式** ，將「網站資產」資料夾定義為專用來源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ 使用 **SPOTenantCdnOrigin 指令程式** ，將「網站頁面」資料夾定義為專用來源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 使用 **SPOTenantCdnOrigin 指令程式** ，將 [發佈影像] 資料夾定義為專用來源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>範例：設定 SharePoint Online 之網站集合的私人來源

使用 **SPOTenantCdnOrigin 指令程式** ，將網站集合定義為私人來源。 例如：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。
  
當您執行此命令之後，系統會同步處理整個資料中心的設定。 您可能會看到如 SharePoint 線上租使用者連接至 CDN 服務時，應為 _待處理_ 郵件。 這最多可能需要15分鐘。

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>管理 Office 365 CDN

設定 CDN 後，您可以在更新內容或需要變更時變更設定，如本節所述。
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>新增、更新或移除 Office 365 中的資產 CDN

完成設定步驟之後，您就可以新增資產，並隨時更新或移除現有的資產。 您只需對您識別為原產地的資料夾或 SharePoint 文件庫中的資產進行變更。 如果您新增資產，可立即透過 CDN 取得。 不過，如果您更新資產，最多需要15分鐘的時間，新的副本才能傳播並變得可用於 CDN。
  
如果您需要取得原始位置，您可以使用 **SPOTenantCdnOrigins** Cmdlet。 如需如何使用此 Cmdlet 的詳細資訊，請參閱 [SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>從 Office 365 中移除原點 CDN

您可以移除您識別為原產地的資料夾或 SharePoint 程式庫的存取權。 若要這麼做，請使用 **SPOTenantCdnOrigin** Cmdlet。

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>在 Office 365 中修改原點 CDN

您無法修改您已建立的來源。 請改為移除原始位置，然後新增一個新的位置。 如需詳細資訊，請參閱[從 Office 365 中移除原點 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)並[為資產新增原產地](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>停用 Office 365 CDN

使用 **SPOTenantCdnEnabled 指令程式** 來停用您組織的 CDN。 如果您已啟用 CDN 的公開和私人來源，則需要執行 Cmdlet 兩次，如下列範例所示。
  
若要停用 CDN 中的公開來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

若要停用 CDN 中的私人來源，請輸入下列命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

如需此 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>使用 PnP PowerShell 設定及設定 Office 365 CDN

本節中的程式需要您使用 PnP PowerShell 連線至 SharePoint 線上。 如需相關指示，請參閱 [PnP PowerShell 快速](https://github.com/SharePoint/PnP-PowerShell#getting-started)入門。

完成下列步驟，以使用 PnP PowerShell 在 SharePoint 線上中設定和設定 CDN 主控資產。

<details>
  <summary>按一下以展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>讓您的組織使用 Office 365 CDN

變更租使用者 CDN 設定之前，您應該先在 Office 365 租使用者中取得私人 CDN 設定的目前狀態。 使用 PnP 連線至您的承租人 PowerShell:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

現在使用 **PnPTenantCdnEnabled 指令程式**，從承租人中取得 CDN 狀態設定：

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

指定 CdnType 的 CDN 狀態會輸出至螢幕。

使用 **PnPTenantCdnEnabled 指令程式** 可讓您的組織使用 Office 365 CDN。 您可以讓組織同時使用公用來源、私人來源或兩者同時使用。 您也可以設定 CDN 在啟用時略過預設來源的設定。 您可以隨時依照本主題所述新增這些來源。
  
PnP PowerShell:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

例如，若要讓您的組織同時使用公用和私人來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

若要讓您的組織同時使用公用和私人來源，但略過設定預設來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

如需啟用 Office 365 CDN 時預設提供的來源相關資訊，請參閱[預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)，以及略過設定預設來源的潛在影響。

若要讓您的組織使用公用來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

若要讓您的組織使用私人來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

如需此 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>變更要包含在 Office 365 CDN (選用) 的檔案類型清單。

> [!TIP]
> 當您使用 **PnPTenantCdnPolicy** 指令程式來定義檔案類型時，會覆寫目前定義的清單。 如果您想要將其他檔案類型新增至清單，請先使用 Cmdlet 來找出已允許的檔案類型，並將其包含在清單中，以及新的檔案類型。
  
使用 **PnPTenantCdnPolicy 指令程式**，定義可由 CDN 中的公開和私人來源主控的靜態檔案類型。 根據預設，允許一般資產類型，例如 .css、.gif、.jpg 及 .js。

PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

例如，若要啟用 CDN 以主控 .css 及 .png 檔案，您可以輸入下列命令：

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

若要查看 CDN 目前允許的檔案類型，請使用 **PnPTenantCdnPolicies** Cmdlet：

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

如需這些 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 和 [PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>變更您想要從 Office 365 CDN 中排除的網站分類清單 (選用) 

> [!TIP]
> 當您使用 **PnPTenantCdnPolicy** 指令程式排除網站分類時，會覆寫目前定義的清單。 如果您想要排除其他網站分類，請先使用 Cmdlet 來找出已排除的分類，然後將其新增至新的分類。

您可以使用 **PnPTenantCdnPolicy 指令程式** 來排除您不想讓 CDN 使用的網站分類。 根據預設，不會排除任何網站分類。

PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

若要查看目前限制的網站分類，請使用 **PnPTenantCdnPolicies** Cmdlet：

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

將傳回的屬性為 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 及 _ExcludeIfNoScriptDisabled_。

_IncludeFileExtensions_ 屬性包含將從 CDN 提供的副檔名清單。

> [!NOTE]
> 預設副檔名在 public 和 private 之間是不同的。

_ExcludeRestrictedSiteClassifications_ 屬性包含您要從 CDN 中排除的網站分類。 例如，您可以排除標記為 **機密** 的網站，以便不會從 CDN 提供套用該分類之網站的內容。

_ExcludeIfNoScriptDisabled_ 屬性會根據網站層級 _NoScript_ 屬性設定，從 CDN 中排除內容。 根據預設，會將 _NoScript_ 屬性設定為 _新式_ 網站 **啟用**，並針對 _傳統_ 網站 **停用**。 這取決於您的租使用者設定。

如需這些 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 和 [PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>新增資產來源

使用 **PnPTenantCdnOrigin 指令程式** 來定義原點。 您可以定義多個來源。 來源是指向包含您要由 CDN 主控的資產的 SharePoint 文件庫或資料夾的 URL。
  
> [!IMPORTANT]
> 您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_Path_ 的值是包含資產之文件庫或資料夾的相對路徑。 除了相對路徑之外，您還可以使用萬用字元。 來源支援在 URL 前面加上萬用字元。 這可讓您建立跨越多個網站的來源。 例如，若要將所有網站的所有資產都納入 CDN 中的公開來源，請輸入下列命令：

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 萬用字元修飾符 * **/** 只能在路徑的開頭使用，而且會比對指定之 url 底下的所有 URL 段。
+ 路徑可以指向文件庫、資料夾或網站。 例如，路徑 _*/site1_ 會比對網站底下的所有文件庫。

您可以使用特定的相對路徑來新增原點。 您無法使用完整路徑新增原點。

本範例會在特定網站上新增網站資產庫的私人來源：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

在這個範例中，會在網站集合的網站資產庫中新增 _folder1_ 資料夾的私人來源：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

如果路徑中有空格，您可以使用雙引號括住路徑，也可以使用 URL 編碼 %20 取代空格。 下列範例會在網站集合的 [網站資產] 文件庫中新增 _資料夾 1_ 資料夾的私人來源：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

> [!NOTE]
> 在 [私人來源] 中，從來源共用的資產必須先發行主要版本，才能從 CDN 中存取。
  
當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>範例：針對線上 SharePoint 設定主版頁面和樣式庫的公開來源

一般來說，當您啟用 Office 365 CDN 時，會預設為您設定這些來源。 不過，如果您想要手動啟用它們，請遵循下列步驟。
  
+ 使用 **PnPTenantCdnOrigin 指令程式** ，將樣式庫定義為公用來源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ 使用 **PnPTenantCdnOrigin 指令程式** ，將主版頁面定義為公用來源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>範例：針對線上 SharePoint 設定網站資產、網站頁面及發佈影像的私人來源

+ 使用 **PnPTenantCdnOrigin 指令程式** ，將「網站資產」資料夾定義為專用來源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ 使用 **PnPTenantCdnOrigin 指令程式** ，將「網站頁面」資料夾定義為專用來源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 使用 **PnPTenantCdnOrigin 指令程式** ，將 [發佈影像] 資料夾定義為專用來源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

當您執行此命令之後，系統會同步處理整個資料中心的設定。 這最多可能需要15分鐘。

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>範例：設定 SharePoint Online 之網站集合的私人來源

使用 **PnPTenantCdnOrigin 指令程式** ，將網站集合定義為私人來源。 例如：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。
  
當您執行此命令之後，系統會同步處理整個資料中心的設定。 您可能會看到如 SharePoint 線上租使用者連接至 CDN 服務時，應為 _待處理_ 郵件。 這最多可能需要15分鐘。

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>管理 Office 365 CDN

設定 CDN 後，您可以在更新內容或需要變更時變更設定，如本節所述。
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>新增、更新或移除 Office 365 中的資產 CDN

完成設定步驟之後，您就可以新增資產，並隨時更新或移除現有的資產。 您只需對您識別為原產地的資料夾或 SharePoint 文件庫中的資產進行變更。 如果您新增資產，可立即透過 CDN 取得。 不過，如果您更新資產，最多需要15分鐘的時間，新的副本才能傳播並變得可用於 CDN。
  
如果您需要取得原始位置，您可以使用 **PnPTenantCdnOrigin** Cmdlet。 如需如何使用此 Cmdlet 的詳細資訊，請參閱 [PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>從 Office 365 中移除原點 CDN

您可以移除您識別為原產地的資料夾或 SharePoint 程式庫的存取權。 若要這麼做，請使用 **PnPTenantCdnOrigin** Cmdlet。

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>在 Office 365 中修改原點 CDN

您無法修改您已建立的來源。 請改為移除原始位置，然後新增一個新的位置。 如需詳細資訊，請參閱[從 Office 365 中移除原點 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)並[為資產新增原產地](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>停用 Office 365 CDN

使用 **PnPTenantCdnEnabled 指令程式** 來停用您組織的 CDN。 如果您已啟用 CDN 的公開和私人來源，則需要執行 Cmdlet 兩次，如下列範例所示。
  
若要停用 CDN 中的公開來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

若要停用 CDN 中的私人來源，請輸入下列命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

如需此 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>使用 Office 365 CLI 設定及設定 Office 365 CDN

本節中的程式需要您已安裝[Office 365 CLI](https://aka.ms/o365cli)。 接下來，使用[登](https://pnp.github.io/office365-cli/cmd/login/)入命令連線到您的 Office 365 租使用者。

完成這些步驟，使用 Office 365 CLI，設定和設定 CDN 以在 SharePoint 線上內主控您的資產。

<details>
  <summary>按一下以展開</summary>

### <a name="enable-the-office-365-cdn"></a>啟用 Office 365 CDN

您可以使用[spo CDN 組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)命令，管理承租人中 Office 365 CDN 的狀態。

若要在租使用者執行中啟用 Office 365 Public CDN：

```cli
spo cdn set --type Public --enabled true
```

若要啟用 Office 365 SharePoint CDN，請執行：

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>查看 Office 365 的目前狀態 CDN

若要檢查特定類型的 Office 365 CDN 是否已啟用或已停用，請使用[spo CDN get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)命令。

若要檢查是否已啟用 Office 365 公用 CDN，請執行：

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>View Office 365 CDN 來源

若要查看目前設定的 Office 365 Public CDN 來源執行：

```cli
spo cdn origin list --type Public
```

當您啟用 Office 365 CDN 時，請參閱[預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)，以取得預設會布建之來源的詳細資訊。

### <a name="add-an-office-365-cdn-origin"></a>在原始位置新增 Office 365 CDN

> [!IMPORTANT]
> 在設定為公用來源的 SharePoint 文件庫中，絕對不應將被視為敏感的資源放入組織中。

使用[spo cdn 原始的 add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/)命令來定義 CDN 原始位置。 您可以定義多個來源。 來源是指向包含您要由 CDN 主控的資產的 SharePoint 文件庫或資料夾的 URL。

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

其中 `path` 是包含資產之資料夾的相對路徑。 除了相對路徑之外，您還可以使用萬用字元。

若要將所有網站的 **主版頁面圖庫** 中的所有資產都包含為公用來源，請執行：

```cli
spo cdn origin add --type Public --origin */masterpage
```

若要設定特定網站集合的私人來源，請執行：

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> 在新增 CDN 原點之後，最多可能需要15分鐘的時間，您才可以透過 CDN 服務來取得檔案。 您可以使用 [spo cdn 原始清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，確認是否已啟用特定來源。

### <a name="remove-an-office-365-cdn-origin"></a>移除 Office 365 CDN 來源

使用[spo cdn 原始移除](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/)命令移除指定 CDN 類型的 CDN 原點。

若要從 CDN 設定移除公用來源，請執行：

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> 移除 CDN 原始檔不會影響與該來源相符的任何文件庫中儲存的檔案。 如果這些資產已使用 SharePoint URL 參考，SharePoint 會自動切換回指向文件庫的原始 URL。 不過，如果資產已使用公用 CDN URL 參照，則移除該來源會中斷連結，您必須手動加以變更。

### <a name="modify-an-office-365-cdn-origin"></a>修改 Office 365 CDN 來源

無法修改現有的 CDN 原點。 相反地，您應該使用命令移除先前定義的 CDN 原點 `spo cdn origin remove` ，然後使用命令新增一個 `spo cdn origin add` 。

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>變更要包含在 Office 365 中的檔案類型 CDN

根據預設，下列檔案類型會包含在 CDN： _.css、eot、.gif、.ico、jpeg、.jpg、.js、.map、.png、svg、ttf、woff 及 woff2_。 如果您需要在 CDN 中包含其他檔案類型，您可以使用[spo CDN 原則組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)命令變更 CDN 設定。

> [!NOTE]
> 變更檔案類型的清單時，會覆寫目前定義的清單。 如果您想要包含其他檔案類型，請先使用 [spo cdn 原則清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，找出目前設定的檔案類型。

若要將 _JSON_ 檔案類型新增至公用 CDN 所包含之檔案類型的預設清單，請執行：

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>變更您要從 Office 365 中排除的網站分類清單 CDN

使用[spo cdn 原則組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)命令，排除您不想讓 CDN 使用的網站分類。 根據預設，不會排除任何網站分類。

> [!NOTE]
> 變更排除的網站分類清單時，會覆寫目前定義的清單。 若要排除其他分類，請先使用 [spo cdn 原則清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 命令，找出目前設定的分類。

若要從公用 CDN 中排除歸類為 _HBI_ 的網站，請執行

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>停用 Office 365 CDN

若要停用 Office 365 CDN 使用 `spo cdn set` 命令，例如：

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>使用您的 CDN 資產

現在，您已啟用 CDN 和設定的來源及原則，您可以開始使用 CDN 資產。

本節將協助您瞭解如何在 SharePoint 頁面和內容中使用 CDN URLs，以便 SharePoint 將公用和私人來源資產的要求重新導向至 CDN。

+ [更新 CDN 資產的連結](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [使用公用來源中的資產](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [使用私人來源的資產](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

如需如何使用 CDN 主控用戶端網頁元件的詳細資訊，請參閱[從 Office 365 CDN (Hello World part 4) 的用戶端網頁元件](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)。

> [!NOTE]
> 如果您將 _ClientSideAssets_ 資料夾新增到 **私人** CDN 來源清單中，則 CDN 主控的自訂網頁元件將無法轉譯。 SPFX 網頁元件使用的檔案只能利用 public CDN，而 ClientSideAssets 資料夾是公用 CDN 的預設來源。 

### <a name="updating-links-to-cdn-assets"></a>更新 CDN 資產的連結

若要使用您已新增至來源的資產，您只需以原始檔案的路徑來更新原始檔案的連結。

+ 編輯包含您已新增至來源之資產連結的頁面或內容。 您也可以使用其中一種方法，在 [輸入網站或網站集合] 中全域搜尋和取代連結，如果您想要在任何位置更新指定資產的連結。
+ 針對來源中資源的每個連結，將路徑取代為 CDN 原始檔案中的檔案。 您可以使用相對路徑。
+ 儲存頁面或內容。

例如，請考慮您已複製到文件庫資料夾 _/site/CDN_origins/public/_ 的影像 _/site/SiteAssets/images/image.png_。 若要使用 CDN 資產，請將原始路徑取代為來源路徑的圖像檔案位置，讓新的 URL _/site/CDN_origins/public/image.png_。

如果您想要使用完整的 URL 來代替相對路徑，請建立如下的連結：

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 一般說來，您不應該直接對 CDN 中的資產 URLs 硬編碼。 不過，您可以視需要，以手動方式為公用來源中的資產建立 URLs。 如需詳細資訊，請參閱[Hardcoding CDN URLs 的公開資產](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)。

若要瞭解如何驗證資產是否已從 CDN 提供，請參閱[如何確認資產是否正由 CDN 所服務？](use-microsoft-365-cdn-with-spo.md#CDNConfirm) [疑難排解 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)。

### <a name="using-assets-in-public-origins"></a>使用公用來源中的資產

SharePoint Online 中的 **發佈功能** 會自動將儲存在公用來源中的資產 URLs 重寫至其 CDN 對等專案，如此才能從 CDN 服務（而非 SharePoint）提供資產。

如果您的來源位於啟用發佈功能的網站中，且您想要將其轉移至 CDN 的資產屬於下列其中一個類別，則 SharePoint 會為來源中的資產自動重新寫入 URLs，但前提是 CDN 原則未排除該資產。

以下是 SharePoint 發佈功能會自動重新寫入連結的概覽：

+ 傳統發佈頁面 HTML 回應中的 IMG/LINK/CSS URLs
  + 這包括網頁的 HTML 內容中作者所新增的影像
+ 圖片庫幻燈片] 網頁元件影像 URLs
+ SPList REST API (RenderListDataAsStream) 結果中的影像欄位
  + 使用新屬性 _ImageFieldsToTryRewriteToCdnUrls_ 提供以逗號分隔的欄位清單
  + 支援 hyperlink 欄位及 PublishingImage 欄位
+ SharePoint 影像轉譯

下圖說明 SharePoint 接收公用來源中包含資產之頁面的要求時的工作流程。

![工作流程圖表：從公用來源取回 Office 365 CDN 資產](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "工作流程：從公用來源取回 Office 365 CDN 資產")

> [!TIP]
> 如果您想要對頁面上的特定 URLs 停用自動重新寫入，您可以取出頁面並新增查詢字串參數 **？NoAutoReWrites = true** 表示您要停用的每個連結的結尾。

#### <a name="constructing-cdn-urls-for-public-assets"></a>構造公開資產的 CDN URLs

如果公開來源未啟用 _發佈_ 功能，或資產並非 CDN 服務之自動重新寫入功能所支援的連結類型之一，則可以手動構造 URLs 至資產 CDN 位置，並在內容中使用這些 URLs。

> [!NOTE]
> 您無法對私人來源中的資產進行硬編碼或構建 CDN URLs，因為在要求資源時，會產生表單最後一個區段所要求的訪問權杖。 您可以建立公用 CDN 的 url，而 url 不應該是強制編碼的，因為它可能會變更。

若是公開 CDN 資產，URL 格式會如下所示：

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

將 **TenantHostName** 取代為您的租使用者名稱。 範例：

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> 頁面內容屬性應該用來建立前置詞，而不是硬編碼 " https://publiccdn.sharepointonline.com "。 URL 可能會變更，而且不應該是硬式編碼。 如果您使用的顯示範本與傳統的 SharePoint 線上，您可以使用顯示範本中的屬性 "window._spPageCoNtextInfo publicCdnBaseUrl" 來輸入 URL 的首碼。 如果您要 SPFx 現代及傳統 SharePoint 的網頁元件，您可以使用屬性「pageCoNtext legacyPageCoNtext publicCdnBaseUrl」。 這將會提供前置詞，以便在變更後，您的實施會與其一起更新。 SPFx 的範例中，URL 可以使用 the the legacyPageCoNtext the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the 請參閱在第[1 賽季效能系列](https://aka.ms/sppnp-perfvideos)的[用戶端程式代碼中使用 CDN](https://youtu.be/IH1RbQlbhIA) 。


### <a name="using-assets-in-private-origins"></a>使用私人來源的資產

若要使用私人來源的資產，不需要進行其他設定。 SharePoint線上針對私人來源中的資產自動重寫 URLs，因此這些資產的要求永遠會從 CDN 服務。 您無法手動建立 URLs 以 CDN 私人來源中的資產，因為這些 URLs 包含在要求資產時 SharePoint 線上才能自動產生的權杖。

存取私人來源資產的方法是根據原始的使用者權限，以使用者權限來保護，並在下列各節中說明的忠告。 使用者必須至少具有對 CDN 呈現內容之來源的 **讀取** 許可權。

下圖說明 SharePoint 收到來自私人來源之資產的頁面要求時的工作流程。

![工作流程圖表：從私人來源取回 Office 365 CDN 資產](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "工作流程：從私人來源取回 Office 365 CDN 資產")

#### <a name="token-based-authorization-in-private-origins"></a>私人來源中以權杖為基礎的授權

Office 365 CDN 中的私人來源資產的存取權是由 SharePoint 線上所產生的權杖所授。 已有權存取原始位置所指定之資料夾或文件庫的使用者，會自動授與允許使用者根據其許可權層級存取該檔案的權杖。 這些存取權杖在產生後會有效30到90分鐘，以協助防止權杖重新顯示攻擊。

當存取權杖產生之後，SharePoint 線上傳回自訂 URI 至包含兩個授權參數的用戶端，將會 _吃_ (edge authorization token) 和 _oat_ (來源授權權杖) 。 每個權杖的結構是 _以時段格式「>__< ' 安全簽名」 >< 的到期時間_。 例如：

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> 擁有該權杖的任何人都可以存取 CDN 中的資源。 不過，包含這些存取權杖的 URLs 只會透過 HTTPS 共用，除非使用者在權杖到期之前明確共用該 URL，否則無法存取未授權使用者的資產。

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>私人來源的資產不支援專案層級許可權

請務必注意，SharePoint Online 不支援私人來源資產的專案層級許可權。 例如，對於位於的檔案 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` ，使用者會在發生下列情況時，具有檔案的有效存取權：

|使用者  |權限  |有效的存取  |
|---------|---------|---------|
|使用者1     |可以存取 folder1         |可從 CDN 存取 image1.jpg         |
|使用者 2     |無權存取 folder1         |無法存取 CDN 中的 image1.jpg         |
|使用者 3     |無權存取 folder1，但會授與在線上 SharePoint 中存取 image1.jpg 的明確許可權。         |可以直接從線上 SharePoint 存取資產 image1.jpg，但不能從 CDN 中存取。         |
|使用者 4     |可以存取 folder1，但已明確拒絕 SharePoint 線上中 image1.jpg 的存取權         |無法從 SharePoint 線上存取資產，但是可以從 CDN 存取資產，但不需要存取 SharePoint 線上中的檔案         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>疑難排解 Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>如何確認資產是否由 CDN 所服務？

在將 CDN 資產的連結新增至頁面後，您可以流覽至頁面、在圖像呈現及檢查影像 URL 後，以滑鼠右鍵按一下此頁面，以確認資產是否正在從 CDN 服務。

您也可以使用瀏覽器的開發人員工具，查看頁面上每個資產的 URL，或使用協力廠商網路追蹤工具。

> [!NOTE]
> 如果您使用 Fiddler 等網路工具在從 SharePoint 頁面轉譯資產之外測試資產，您必須手動將 referer 標頭 "referer： `https://yourdomain.sharepoint.com` " 新增至 GET 要求，其中 URL 是您 SharePoint Online 租使用者的根 url。

您無法在網頁瀏覽器中直接測試 CDN URLs，因為您必須具有來自于 SharePoint 線上的 referer。 不過，如果您將 CDN 資產 URL 新增至 SharePoint 頁面，然後在瀏覽器中開啟該頁，您就會看到頁面上所呈現的 CDN 資產。

如需使用 Microsoft Edge 瀏覽器中的開發人員工具的詳細資訊，請參閱[Microsoft Edge 開發人員工具](/microsoft-edge/devtools-guide)。

若要觀看[SharePoint 開發人員模式和做法](https://aka.ms/sppnp-videos)中所主控的簡短影片 YouTube 通道示範如何驗證您的 CDN 是否正常運作，請參閱[驗證您的 CDN 使用狀況，並確保最佳的網路連線能力](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)。

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>為何無法使用來自新原始來源的資產？
新的來源中的資產不會立即可供使用，因為註冊透過 CDN 傳播，而且資產要從來源上傳至 CDN 儲存區。 CDN 中的資產可用時間取決於多少資產和檔案大小。

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>我的用戶端網頁元件或 SharePoint 架構方案無法運作

當您為公用來源啟用 Office 365 CDN 時，CDN 服務會自動建立下列預設來源：

+ */MASTERPAGE
+ */STYLE 程式庫
+ */CLIENTSIDEASSETS

如果缺少 */clientsideassets 原創，SharePoint 架構方案將會失敗，而且不會產生警告或錯誤訊息。 此來源可能遺失，CDN 因為 _NoDefaultOrigins_ 參數設定為 **$true**，或是已手動刪除來源。

您可以使用下列 PowerShell 命令來查看存在哪些來源：

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

您也可以使用 Office 365 CLI 進行檢查：

```cli
spo cdn origin list
```

若要在 PowerShell: 中新增原點

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

若要在 Office 365 CLI 中新增原點：

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>使用 Office 365 CDN 時，我需要哪些 PowerShell 模組和 CLI shell？

您可以選擇使用 **SharePoint 線上管理命令** 介面 PowerShell 模組或 **Office 365 CLI** 的 Office 365 CDN。

+ [開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [安裝 Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>另請參閱

[內容傳遞網路](./content-delivery-networks.md)

[Office 365 的網路規劃和效能調整](./network-planning-and-performance.md)

[SharePoint效能數列-Office 365 CDN 的影片系列](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
