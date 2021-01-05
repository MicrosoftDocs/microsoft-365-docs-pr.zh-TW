---
title: Office 365 美國政府 DOD 端點
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 需要連接至網際網路。 下列端點應可供使用 Office 365 美國政府 DoD 方案的客戶使用。
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 39f48b152f46ab12b1e96cf8869a0fd8050d1c35
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751636"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 美國政府 DoD 端點

*適用版本： Office 365 系統管理員*

 Office 365 需要連接至網際網路。 下列端點應可供使用 Office 365 美國政府 DoD 方案的客戶使用。
  
 **Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md) | [21 Vianet 提供的 Office 365](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 德國](microsoft-365-germany-endpoints.md) |  *Office 365 美國政府 DoD* | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**上次更新：** 01/04/2021- ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**下載：** [JSON 格式](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)的完整清單 <br/> |

 請從 [管理 Office 365 端點](managing-office-365-endpoints.md) 開始，以瞭解如何使用此資料來管理網路連線的建議。 端點資料會在每月開始時更新，並以新的 IP 位址和 URLs 在使用中之前發佈30天。 這樣一來，客戶就可以在需要新的連線之前，尚未有自動更新，就能完成他們的處理常式。 如果需要解決支援上報、安全性事件或其他立即運作需求，也可以在當月期間更新端點。 以下顯示在此頁面上的資料都是由 REST web 服務所產生。 如果您使用腳本或網路裝置來存取此資料，您應該直接前往 [Web 服務](microsoft-365-ip-web-service.md) 。

以下的端點資料會列出從使用者電腦到 Office 365 的連線需求。 不包括從 Microsoft 到客戶網路的網路連線，有時也稱為混合式或輸入的網路連線。 如需詳細資訊，請參閱 [未包含在 web 服務中的其他端點](additional-office365-ip-addresses-and-urls.md)。 

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳化​​」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](https://aka.ms/pnc)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點集是透過 Azure ExpressRoute 與 Office 365 路由首碼一起支援，則為 **[是]** 。 包含路由首碼的 BGP 群組，會與所列的服務區域對齊。 當 ER 為 **No** 時，這表示此端點組不支援 ExpressRoute。 不過，不應假設在 ER 為 **no** 的端點集未宣告任何路由。 如果您打算使用 Azure AD Connect，請閱讀 [特殊考慮區段](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) ，以確保您具有適當的 Azure ad connect 設定。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
本表附註：

- 安全與合規性中心 (SCC) 為 Office 365 提供 Azure ExpressRoute 的支援。 這同樣適用于透過 SCC 公開的許多功能，例如報告、審核、高級 eDiscovery、整合 DLP 和資料管理。 兩個特定功能（PST 匯入和 eDiscovery 匯出）目前不支援只有 Office 365 路由篩選器的 Azure ExpressRoute，因為它們對 Azure Blob 儲存區有相依的依賴性。 若要使用這些功能，您需要使用任何可支援的 Azure 連線選項（包括網際網路連線或 azure 公用路由篩選器的 Azure ExpressRoute），以個別的方式連接至 Azure Blob 儲存。 您必須評估這兩種功能的建立這類連線能力。 Office 365 資訊保護小組已注意到這項限制，而且目前正致力於為 Office 365 提供 Azure ExpressRoute 的支援，這些功能限制于 Office 365 的路由篩選器。

- Microsoft 365 應用程式的其他選用端點未列出，而且不需要讓使用者啟動 Microsoft 365 應用程式以供企業應用程式和編輯檔。 選用端點主控于 Microsoft 資料中心，不會處理、傳送或儲存客戶資料。 建議您將這些端點的使用者連線導向預設的網際網路出局周邊。
