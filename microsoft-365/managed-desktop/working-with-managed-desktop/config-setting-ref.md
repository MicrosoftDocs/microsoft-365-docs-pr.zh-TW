---
title: Microsoft 受管理電腦的組態設定參考
description: Microsoft 受管理電腦中的組態設定的設定類別
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 296602422cf4d590ae17335d7a0bbbc939d929ed
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278316"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>可設定的設定參照-Microsoft 受管理的電腦

本主題列出客戶可以使用 Microsoft 受管理的電腦設定的設定類別。 每個設定類別包含需求、 最佳作法，以及如何自訂 [設定] 類別的資訊。 

## <a name="desktop-background-picture"></a>桌面背景圖片
您可以在組織中自訂 Microsoft 受管理的電腦裝置的桌面背景圖片。 您可以使用此方式套用公司品牌或行銷資料。 

### <a name="requirements"></a>需求

為桌面背景圖片，必須符合這些需求：
- 圖片檔案格式的.jpg、 jpeg 或.png
- 檔案位置-信任安全 http (https) 位置上的主機。 
- 不支援不允許-Http 和檔案共用 (unc) 位置。 

### <a name="customize-and-deploy-desktop-background-picture"></a>自訂及部署桌面背景圖片

**若要新增自訂的桌面背景圖片**
1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在 [**可設定**工作區中，選取 [**桌面背景圖片**。 
4. 輸入您想要使用的圖片的位置。 
5. 選取**階段部署**，以儲存變更，並將其部署至測試群組。 

## <a name="browser-start-pages"></a>瀏覽器開始頁面
當使用者啟動 Microsoft Edge 中個別索引標籤開啟瀏覽器啟動頁面。 如果您想要讓方便您的使用者開啟一群使用者經常使用的網站，新增每個網站的瀏覽器啟動頁面。 

### <a name="requirements"></a>需求

您必須提供的完整的網域名稱 (FQDN) 的內部網路或網際網路網站的瀏覽器啟動頁面。 如果設定內部網站，讓使用者知道要在 office 中的內部網路連線時或使用 VPN 連線連線時，只允許這些網站的存取權。 

### <a name="customize-and-deploy-browser-start-pages"></a>自訂及部署瀏覽器開始頁面

**若要新增在瀏覽器啟動頁面**
1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在 [**可設定**工作區中，選取 [**瀏覽器啟動頁面**。 
4. 選取 [**新增起始頁面**。
5. 在 [**新增] 瀏覽器啟動] 頁面上**，輸入您要使用的網站 URL，然後選取 [**新增起始頁面**。 
6. 重複步驟 1 到 5 的其他瀏覽器啟動頁面。 
7. 選取**階段部署**，以儲存變更，並將其部署至測試群組。

## <a name="enterprise-mode-site-list-location"></a>企業模式網站清單位置

如果您有特定的網站和應用程式，您知道有 Microsoft Edge 的相容性問題，您可以使用企業模式網站清單，以便網站會自動開啟使用 Internet Explorer 11。 此外，如果您知道您的內部網路網站不移至 Microsoft Edge 中正常運作，您可以設定所有的內部網路網站，若要開啟 [自動使用 Internet Explorer 11。 使用企業模式表示您可以繼續使用 Microsoft Edge 作為預設的瀏覽器，同時也確保您的應用程式，繼續在 Internet Explorer 11 上工作。 如需有關企業模式網站清單的詳細資訊，請參閱[企業模式和企業模式網站清單](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。 

您可以指定 https:// 位置或您主控您的企業模式網站清單的內部共用的位置。 

### <a name="requirements"></a>需求

對於企業模式網站清單檔案，必須符合這些需求：
- 檔案格式的 XML 檔案符合[檔案需求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- 檔案位置-內部 https 位置上的主機檔案。 
- 不允許-裝載內部檔案共用，例如 *//sharename*，不允許

### <a name="best-practices"></a>最佳做法

這些最佳作法提供可協助客戶做出決策至現代化其 IT 基礎結構：
- **選擇網站數目有限**– Microsoft 受管理的電腦會使用為慣用的瀏覽器 Microsoft Edge，以提升貴組織的整體安全性和使用者的可用性。 在此清單中的大部分網站是需要較舊版本的瀏覽器中，將不會包含相同數目的安全性功能的舊版 web 應用程式 url。 
- **考慮替代**– 考慮不同的網站或不需要較舊的瀏覽器的 web 應用程式。 或者，請考慮更新網站，以便其可以使用較新的瀏覽器。 較新的瀏覽器使用的最新技術，並協助增進安全性。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>自訂及部署企業網站模式] 清單位置

**若要新增企業網站模式] 清單位置**

1.  登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2.  在 [**設定**] 下選取 [**可設定**]。
3.  在 [**可設定**工作區中，選取**企業模式網站清單位置**。 
4.  輸入您的網站清單的 https 位置。 
5.  選取**階段部署**，以儲存變更，並將其部署至測試群組。

## <a name="trusted-sites"></a>信任的網站

受信任的網站可讓您自訂安全性區域，或其中一個站台可用於，不同的站台。 安全性區域包含： 
- 區域 1 – 近端內部網路區域
- 區域 2 – 受信任的網站] 區域
- 區域 3 – 網際網路區域
- 區域 4 – 限制的網站] 區域

### <a name="requirements"></a>需求

內部網路或網際網路網站的每個受信任的網站提供的完整的網域名稱 (FQDN)。 

### <a name="customize-and-deploy-trusted-sites"></a>自訂及部署信任的網站

**若要新增信任的網站**

1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在 [**可設定**工作區中，選取 [**信任的網站**，，，然後選取 [**新增信任的網站**。 
4. 在 [**新增信任的網站**]，輸入的 URL，選擇 [安全性區域，，然後選取 [**新增信任的網站**。 
5. 針對每個您想要新增信任的網站重複步驟 1 到 4。 
6. 選取**階段部署**，以儲存變更，並將其部署至測試群組。

**若要移除信任的網站**

1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在 [**可設定**工作區中，選取 [**信任的網站**。 
4. 選取您要刪除的網站，然後選取 [**刪除**。 
5. 針對每個您想要刪除的信任網站重複步驟 1 到 4。 
6. 選取**階段部署**，以儲存變更，並將其部署至測試群組。

## <a name="proxy"></a>Proxy
您可以管理組織的網路 proxy 設定。 新增您的 proxy 伺服器和連接埠號碼，然後再新增 [您的 proxy 站台例外狀況。 Microsoft 受管理的電腦包含一組的預設 proxy 的例外狀況所需的操作的服務。 Microsoft 受管理的電腦服務可能只修改預設排除清單。  如需詳細資訊，請參閱 < <b0>Microsoft 受管理電腦的網路組態</b0>。 

您在 Microsoft 受管理電腦入口網站中新增的 proxy 站台例外狀況會新增至預設的 proxy 例外狀況隨附於 Microsoft 受管理的電腦服務。 

> [!NOTE]
> 一律優先順序透過客戶部署更新的預設 proxy 例外狀況清單。 這表示如果沒有預設 proxy 例外狀況清單的部署，將會暫停分段的部署。  

### <a name="requirements"></a>需求

Proxy 伺服器和 proxy 網站例外狀況，必須符合這些需求：
- 必須是有效的伺服器位址及連接埠號碼
- Url 必須是有效的 http 網站 

### <a name="customize-and-deploy-proxies"></a>自訂及部署 proxy

**若要新增個別的 proxy 站台例外狀況**

1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在 [**可設定**工作區中，選取 [ **Proxy**]。 
4. 輸入您 proxy 伺服器的**位址**和**連接埠號碼**，然後選取 [**新增 proxy 例外狀況**。 
5. 輸入有效的 http 網站的 URL，然後選取 [**新增 proxy 例外狀況**。 
6. 針對每個您想要新增信任的網站重複步驟 1-5。 
7. 選取**階段部署**，以儲存變更，並將其部署至測試群組。

## <a name="additional-resources"></a>其他資源
- [組態設定概觀](config-setting-overview.md) 
- [部署組態設定](config-setting-deploy.md)
