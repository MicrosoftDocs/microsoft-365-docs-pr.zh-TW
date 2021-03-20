---
title: Microsoft 受管理電腦的可設定參考
description: 設定 Microsoft Managed Desktop 中的可設定類別
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917701"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>可設定的設定參考-Microsoft 受管理的電腦

本主題列出客戶可以使用 Microsoft Managed Desktop 設定的設定類別。 每個設定類別都包含需求的資訊、最佳作法，以及如何自訂設定類別。 

## <a name="desktop-background-picture"></a>桌面背景圖片
您可以為組織中的 Microsoft 受管理桌面裝置自訂桌面背景圖片。 您可以使用此應用來套用公司品牌或行銷材料。 

### <a name="requirements"></a>需求

您必須符合這些需求，才能取得桌面背景圖片：
- 圖片檔案格式-.jpg、jpeg 或 .png
- 檔案位置-主機在受信任的安全 HTTP (HTTPs) 位置。 
- 不允許-不支援 (unc) 位置的 Http 與檔案共用。 

### <a name="customize-and-deploy-desktop-background-picture"></a>自訂及部署桌面背景圖片

**新增自訂桌面背景圖片**
1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中，選取 [ **桌面背景圖片**]。 
4. 輸入您想要使用的圖片位置。 
5. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。 

## <a name="browser-start-pages"></a>瀏覽器開始頁面
當使用者啟動 Microsoft Edge 時，瀏覽器起始頁面會在個別的索引標籤中開啟。 如果您想要讓使用者輕鬆地開啟一組經常使用的網站，請為每個網站新增瀏覽器開始頁面。 

### <a name="requirements"></a>需求

您必須為瀏覽器開始頁面提供內部網路或網際網路網站的完整功能變數名稱 (FQDN) 。 如果已設定內部網站，請讓使用者知道，當在辦公室或使用 VPN 連線時，連線至內部網路時，允許存取這些網站。 

### <a name="customize-and-deploy-browser-start-pages"></a>自訂及部署瀏覽器開始頁面

**新增瀏覽器開始頁面**
1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中，選取 [ **Browser start pages**]。 
4. 選取 [ **新增開始頁面**]。
5. 在 [ **新增瀏覽器開始] 頁面** 上，輸入您要使用之網站的 URL，然後選取 [ **新增開始頁面**]。 
6. 重複步驟1-5 以取得其他瀏覽器開始頁面。 
7. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。

## <a name="enterprise-mode-site-list-location"></a>企業模式網站清單位置

如果您有與 Microsoft Edge 相容性問題的特定網站和應用程式，您可以使用企業模式網站清單，讓網站自動使用 Internet Explorer 11 開啟。 此外，如果您知道內部網路網站不會與 Microsoft Edge 正確搭配使用，您可以設定所有內部網路網站，以自動開啟使用 Internet Explorer 11。 使用企業模式意味著您可以繼續使用 Microsoft Edge 做為您的預設瀏覽器，同時也可以確保您的應用程式繼續在 Internet Explorer 11 上運作。 如需企業模式網站清單的詳細資訊，請參閱 [Enterprise mode And Enterprise Mode Site lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。 

您可以指定 HTTPs://位置或存放您的企業模式網站清單所在內部共用的位置。 

### <a name="requirements"></a>需求

企業模式網站清單檔案必須符合下列需求：
- 檔案格式-符合[檔需求](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 檔案
- 檔案位置-主機檔案在內部 HTTPs 位置上。 
- 不允許-不允許在內部檔案共用（如 *//sharename*）上裝載

### <a name="best-practices"></a>最佳做法

提供這些最佳作法，以協助客戶決定讓其 IT 基礎結構現代化：
- **選擇有限的網站數目** – Microsoft 受管理的桌面會使用 microsoft Edge 做為首選瀏覽器，以提升貴組織和使用者可用性的整體安全性。 此清單中的大部分網站適用于舊版 web 應用程式，需要舊版本的瀏覽器，不會包含任何的安全性功能。 
- **請考慮** 其他的網站，或不需要舊版瀏覽器的 web 應用程式。 或者，請考慮更新網站，使其可使用較新的瀏覽器。 較新的瀏覽器使用最新的技術，協助改善安全性。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>自訂及部署企業網站模式清單位置

**新增 enterprise site mode 清單位置**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中，選取 [ **企業模式網站清單位置**]。 
4. 為您的網站清單輸入 HTTPs 位置。 
5. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。

## <a name="trusted-sites"></a>信任的網站

「信任的網站」可讓您自訂安全性區域，或為不同的網站使用網站。 安全性區域包括： 
- Zone 1 –本機內部網路區域
- 區域2–信任的網站區域
- 區域3–網際網路區域
- 區域4–受限制的網站區域

### <a name="requirements"></a>需求

為每個受信任的網站提供內部網路或網際網路網站的完整功能變數名稱 (FQDN) 。 

### <a name="customize-and-deploy-trusted-sites"></a>自訂及部署信任的網站

**新增信任的網站**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中選取 [ **信任的網站**]，然後選取 [ **新增信任的網站**]。 
4. 在 [ **新增信任的網站**] 上，輸入 URL、選擇安全性區域，然後選取 [ **新增信任的網站**]。 
5. 針對您要新增的每個信任網站，重複步驟1-4。 
6. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。

**移除信任的網站**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中，選取 [ **信任的網站**]。 
4. 選取您要刪除的網站，然後選取 [ **刪除**]。 
5. 針對每個您想要刪除的信任網站，重複步驟1-4。 
6. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。

## <a name="proxy"></a>代理
您可以管理組織的網路 proxy 設定。 新增 proxy 伺服器及埠號碼，然後新增 proxy 網站例外狀況。 Microsoft 受管理的桌面包含一組預設 proxy 例外，供服務運作所需。 預設的排除清單可能只會由 Microsoft Managed Desktop 服務修改。  如需詳細資訊，請參閱 [Microsoft Managed Desktop 的網路](../get-ready/network.md)設定。 

您在 Microsoft 管理的桌面入口網站中新增的 proxy 網站例外狀況會新增至 Microsoft Managed Desktop service 隨附的預設 proxy 例外狀況。 

> [!NOTE]
> 更新預設 proxy 例外狀況清單時，總會優先于客戶部署。 這表示如果有預設 proxy 例外清單的部署，您的分段部署會暫停。  

### <a name="requirements"></a>需求

Proxy 伺服器及 proxy 網站例外必須符合這些需求：
- 必須是有效的伺服器位址及埠號碼
- URLs 必須是有效的 HTTP 網站 

### <a name="customize-and-deploy-proxies"></a>自訂及部署代理伺服器

**新增個別 proxy 網站例外狀況**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/) ，並流覽至 [ **裝置** ] 功能表
2. 尋找 [Microsoft 受管理的桌面] 區段，選取 [ **設定**]。
3. 在 [ **設定** 工作區] 中，選取 **Proxy**。 
4. 輸入 proxy 伺服器的 **位址** 與 **埠號碼** ，然後選取 [ **新增 proxy 例外** 狀況]。 
5. 輸入有效的 HTTP 網站 URL，然後選取 [ **新增 proxy 例外** 狀況]。 
6. 針對您要新增的每個信任網站，重複步驟1-5。 
7. 選取 [ **階段部署** ] 以儲存變更，並將變更部署至測試群組。

## <a name="additional-resources"></a>其他資源
- [可設定的設定概述](config-setting-overview.md) 
- [部署可設定的設定](config-setting-deploy.md)