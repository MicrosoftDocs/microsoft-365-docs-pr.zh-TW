---
title: Office 365 德國端點
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
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
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: 在本文中，您會發現可供使用德國 Office 365 的客戶使用的端點。
hideEdit: true
ms.openlocfilehash: 27d7b3c895cb3a8cae148262ce3962f03fb417aa
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925809"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany 端點

 *適用于： Office 365 系統管理員*

Office 365 需要連接至網際網路。 下列端點應可供使用 **Office 365 德國** 方案的客戶使用。

> [!NOTE]
> 針對在德國的新 Microsoft 365 資料中心區域轉換的客戶，端點將會變更。
> 如需其他資訊，請參閱[從 Microsoft Cloud Deutschland 遷移至新的德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)。
  
 **Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md)  | [21 Vianet 提供的 Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 德國* |  [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
**上次更新：** 12/01/2020- ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**下載：** 一個 [JSON 格式](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)清單中所有必要與選用的目的地。

從[管理 Office 365 端點](managing-office-365-endpoints.md)開始，以了解我們針對在使用此資料管理網路連線能力方面的建議。 端點資料會在每個月初根據需要進行更新，並在上線前 30 天發布新的 IP 位址和 URL。  這樣一來，客戶就可以在需要新的連線之前，尚未有自動更新，就能完成他們的處理常式。 如果需要解決支援升級、安全性事件或其他即時操作需求，則還可以在該月內更新端點。  您可以一直參考 [變更記錄訂閱](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。

本頁下方顯示的資料全部來自基於 REST 的 Web 服務。 如果您正使用指令碼或網路裝置來存取本資料，您應直接前往 [Web 服務](microsoft-365-ip-web-service.md)。

以下的端點資料會列出從使用者電腦連線至 Office 365 的需求。 不包括從 Microsoft 到客戶網路的網路連線，有時也稱為混合式或輸入的網路連線。

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳化​​」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點設定透過 Azure ExpressRoute 使用 Office 365 路由首碼支援，則這是 [是]。包含所顯示路由首碼的 BGP 社群會對齊所列的服務區域。當 ER 為 [否] 時，表示 ExpressRoute 不支援此端點集合。不過，不應假設 ER 為 [否] 的端點設定不會通告任何路由。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

