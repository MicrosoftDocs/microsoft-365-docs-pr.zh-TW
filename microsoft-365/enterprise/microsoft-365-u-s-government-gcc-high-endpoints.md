---
title: Office 365美國政府 GCC 高端點
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: 在本文中，您會發現使用 Office 365 美國政府 GCC 高方案的客戶可以存取端點。
hideEdit: true
ms.openlocfilehash: da721d7d0a8965c4dea9bc812df755f19e69ea55
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730159"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365美國政府 GCC 高端點

 *適用于： Office 365 系統管理員*

Office 365 需要連接至網際網路。 下列端點應可供使用 Office 365 美國政府 GCC 高方案的客戶使用。
  
 **Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md) | [21 Vianet 提供的 Office 365](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 德國](microsoft-365-germany-endpoints.md)  |  [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) | *Office 365 美國政府 GCC High* |
  
|||
|:-----|:-----|
|**上次更新：** 05/28/2021- ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**下載：** [JSON 格式](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)的完整清單 <br/> |

 從[管理 Office 365 端點](managing-office-365-endpoints.md)開始，以了解我們針對在使用此資料管理網路連線能力方面的建議。 端點資料會在每個月初根據需要進行更新，並在上線前 30 天發布新的 IP 位址和 URL。  這樣一來，客戶就可以在需要新的連線之前，尚未有自動更新，就能完成他們的處理常式。 如果需要解決支援升級、安全性事件或其他即時操作需求，則還可以在該月內更新端點。  本頁下方顯示的資料全部來自基於 REST 的 Web 服務。 如果您正使用指令碼或網路裝置來存取本資料，您應直接前往 [Web 服務](microsoft-365-ip-web-service.md)。

下列端點資料列出使用者的電腦到 Office 365 的連線需求。這不包括從 Microsoft 到客戶網路的網路連線，有時稱為混合式或輸入網路連線。

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點集是透過 Azure ExpressRoute （具有 Office 365 路由首碼）支援，則為 **[是]** 。 包含路由首碼的 BGP 群組，會與所列的服務區域對齊。 當 ER 為 **No** 時，這表示此端點組不支援 ExpressRoute。 不過，不應假設在 ER 為 **no** 的端點集未宣告任何路由。 如果您打算使用 Azure AD 連線，請閱讀[特殊考慮區段](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)，以確保您具有適當的 Azure ad 連線設定。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

本表附註：

- 安全與合規性中心 (SCC) 為 Office 365 提供 Azure ExpressRoute 的支援。 這同樣適用于透過 SCC 公開的許多功能，例如報告、審核、Advanced eDiscovery、整合 DLP 和資料管理。 這兩項特定功能（PST 匯入和 eDiscovery 匯出）目前不支援只有 Office 365 路由篩選器的 azure ExpressRoute，因為它們在 azure Blob 儲存體上有相依性。 若要使用這些功能，您需要使用任何可支援的 Azure 連線選項（包括網際網路連線或 azure 公用路由篩選器的 Azure ExpressRoute），以個別的方式連接至 Azure Blob 儲存體。 您必須評估這兩種功能的建立這類連線能力。 Office 365 資訊保護小組意識到這種限制，而且目前正致力於對 Azure ExpressRoute 提供支援，Office 365 限制為 Office 365 這兩種功能的路由篩選器。

- 沒有列出的 Microsoft 365 Apps 企業版還有其他選用端點，使用者無法啟動 Microsoft 365 Apps 企業版應用程式和編輯檔。 選用端點主控于 Microsoft 資料中心，不會處理、傳送或儲存客戶資料。 建議您將這些端點的使用者連線導向預設的網際網路出局周邊。