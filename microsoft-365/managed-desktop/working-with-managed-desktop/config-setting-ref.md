---
title: 針對 Microsoft 受管理的桌上型電腦的組態設定參考 （英文)
description: 在 Microsoft 受管理的桌上型電腦中的組態設定的設定類別
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051094"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>可設定的設定參考 （英文)-Microsoft 受管理的桌上型電腦

本主題將列出客戶能設定 Microsoft 受管理的桌上型電腦設定類別。每個設定類別包含在需求、 最佳做法，以及如何自訂設定類別的資訊。 

## <a name="desktop-background-picture"></a>桌面背景圖片
您可以在組織中自訂 Microsoft 受管理的桌上型電腦裝置桌面背景圖片。您可能會使用此公司品牌或行銷套用 

### <a name="requirements"></a>需求

桌面背景圖片必須符合下列需求：
- 圖片檔案格式-.jpg、 jpeg 或.png
- 檔案位置-信任安全 http (https) 位置上的主機。 
- 不允許-不支援 Http 及檔案共用 (unc) 位置。 

### <a name="customize-and-deploy-desktop-background-picture"></a>自訂及部署桌面背景圖片

**若要新增自訂桌面背景圖片**
1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. **可設定**工作區中選取 [**桌面背景圖片**]。 
4. 輸入您想要使用的圖片的位置。 
5. 選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。 

## <a name="browser-start-pages"></a>瀏覽器開始頁面
當您的使用者啟動 Microsoft Edge 個別索引標籤中開啟瀏覽器起始頁面。如果您想要讓您開啟一組他們常用的站台的使用者更容易，新增每個網站的瀏覽器起始頁面。 

### <a name="requirements"></a>需求

您必須提供的完整的網域名稱 (FQDN) 的內部網路或網際網路網站的瀏覽器啟動頁面。如果設定內部網站，可讓使用者知道只允許存取這些網站連線至在 office 中的內部網路或時使用 VPN 連線。 

### <a name="customize-and-deploy-browser-start-pages"></a>自訂及部署瀏覽器開始頁面

**若要新增的瀏覽器開始頁面**
1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. **可設定**工作區中選取 [**瀏覽器啟動頁面**。 
4. 選取 [**新增起始畫面**。
5. 在**新增瀏覽器啟動] 頁面上**，輸入您要使用的網站的 URL，然後選取**新增起始畫面**。 
6. 重複步驟 1-5 其他瀏覽器啟動頁面。 
7. 選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。

## <a name="enterprise-mode-site-list-location"></a>企業模式的網站清單位置

如果您有特定的網站與您知道有 Microsoft Edge 的相容性問題的應用程式，您可以使用企業模式的網站] 清單中，讓網站會自動開啟使用 Internet Explorer 11。此外，如果您知道您的內部網路網站未移至 Microsoft 邊緣正常運作，您可以設定若要開啟 [自動使用 Internet Explorer 11 的所有內部網路網站。使用企業模式表示您可以繼續為預設瀏覽器中使用 Microsoft Edge 時也確保您的應用程式在 Internet Explorer 11 繼續運作。企業模式網站清單上的詳細資訊，請參閱[企業模式及企業模式網站清單](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。 

您可以指定 https:// 位置或內部共用您主控您企業模式的網站清單的位置。 

### <a name="requirements"></a>需求

企業模式網站清單檔案必須符合下列需求：
- 檔案格式-符合[檔案需求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 檔案
- 檔案位置上內部 https 位置的主機檔案。 
- 不允許使用-like *//sharename*、 內部檔案共用上主控不允許

### <a name="best-practices"></a>最佳做法

下列最佳作法被提供可協助客戶做出現代化其 IT 基礎結構的決策：
- **選擇的網站數目有限**– Microsoft 受管理的桌上型電腦使用慣用的瀏覽器 Microsoft Edge 增進貴組織的整體安全性與使用者的使用性。這份清單中的大部分網站需要將不會包含相同數目的安全性功能的瀏覽器的舊版本的舊版的 web 應用程式。 
- **考慮替代**– 考慮不同的網站或不需要較舊的瀏覽器的 web 應用程式。或者，請考慮以便其可以使用較新的瀏覽器更新網站。較新的瀏覽器使用的最新技術並協助增進安全性。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>自訂及部署企業網站模式] 清單位置

**新增企業網站模式] 清單位置**

1.  登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2.  [**設定**] 下選取 [**可設定**]。
3.  **可設定**工作區中選取 [**企業模式的網站清單位置**]。 
4.  輸入您的網站清單的 https 位置。 
5.  選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。

## <a name="trusted-sites"></a>受信任的網站

信任的網站可讓您自訂安全性區域的外部網路，或站台可使用的針對不同站台。安全性區域包括： 
- 區域 1 – 近端內部網路區域
- 區域 2 – 信任的網站] 區域
- 區域 3 – 網際網路區域
- 區域 4 – 限制的網站] 區域

### <a name="requirements"></a>需求

提供內部網路或網際網路網站的每一個受信任的網站的完整的網域名稱 (FQDN)。 

### <a name="customize-and-deploy-trusted-sites"></a>自訂及部署受信任的網站

**新增信任的網站**

1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. **可設定**工作區中選取 [**信任的網站**，並再選取 [**新增信任的網站**。 
4. 在 [**新增信任的網站**上輸入 URL，並選擇 [安全性區域，然後選取 [**新增信任的網站**。 
5. 針對每一個您想要新增信任的網站重複步驟 1 到 4。 
6. 選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。

**若要移除信任的網站**

1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. **可設定**工作區中選取 [**信任的網站**。 
4. 選取您要刪除的網站，然後選取 [**刪除**。 
5. 針對每一個您想要刪除信任的網站重複步驟 1 到 4。 
6. 選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。

## <a name="proxy"></a>Proxy
您可以為組織管理網路 proxy 設定。新增 proxy 伺服器與連接埠號碼，然後再新增 [proxy 網站例外狀況。Microsoft 受管理的桌上型電腦包含一組的預設 proxy 例外狀況所需的操作的服務。僅限可藉由 Microsoft 受管理的桌上型電腦服務修改預設排除清單。 如需詳細資訊，請參閱[Microsoft 受管理的桌上型電腦的網路組態](../get-ready/network.md)。 

您在 Microsoft 受管理的桌上型電腦入口網站中新增的 proxy 網站例外會新增至 Microsoft 受管理的桌上型電腦服務所含的預設 proxy 例外。 

> [!NOTE]
> 更新的預設 proxy 例外狀況清單一律透過客戶部署排列優先順序。這表示如果沒有預設 proxy 例外狀況清單的部署，會暫停分段的部署。  

### <a name="requirements"></a>需求

Proxy 伺服器和 proxy 網站例外狀況都必須符合下列需求：
- 必須是有效的伺服器位址和連接埠號碼
- Url 必須是有效的 http 網站 

### <a name="customize-and-deploy-proxies"></a>自訂及部署 proxy

**若要新增 proxy 個別網站例外狀況**

1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. **可設定**工作區中選取 [ **Proxy**]。 
4. 輸入您 proxy 伺服器的**位址**及**連接埠號碼**，然後選取 [**新增 proxy 例外狀況**。 
5. 輸入有效的 http 網站的 URL，然後選取 [**新增 proxy 例外狀況**。 
6. 針對每一個您想要新增信任的網站重複步驟 1-5。 
7. 選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。

## <a name="additional-resources"></a>其他資源
- [組態設定概觀 （英文)](config-setting-overview.md) 
- [部署組態設定](config-setting-deploy.md)