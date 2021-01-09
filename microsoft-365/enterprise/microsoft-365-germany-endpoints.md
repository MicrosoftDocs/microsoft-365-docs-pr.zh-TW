---
title: 德國的 Office 365 端點
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
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
description: 在本文中，您將會發現在德國使用 Office 365 之客戶可以到達的端點。
hideEdit: true
ms.openlocfilehash: 7c4a65780892d6e257c1c03832cd640bdd4573f3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787912"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany 端點

 *適用版本： Office 365 系統管理員*

Office 365 需要連接至網際網路。 下列端點應可供使用 **Office 365 德國** 方案的客戶使用。
  
 **Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md)  | [21 Vianet 提供的 Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 德國* |  [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**上次更新日期：** 2021 年 1 月 4 日 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**下載：** 一個 [JSON 格式](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)清單中所有必要與選用的目的地。  <br/> |

請從 [管理 Office 365 端點](managing-office-365-endpoints.md) 開始，以瞭解如何使用此資料來管理網路連線的建議。 端點資料會在每月開始時更新，並以新的 IP 位址和 URLs 在使用中之前發佈30天。 這樣一來，客戶就可以在需要新的連線之前，尚未有自動更新，就能完成他們的處理常式。 如果需要解決支援上報、安全性事件或其他立即運作需求，也可以在當月期間更新端點。 您可以一直參考 [變更記錄訂閱](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。

以下顯示在此頁面上的資料都是由 REST web 服務所產生。 如果您使用腳本或網路裝置來存取此資料，您應該直接前往 [Web 服務](microsoft-365-ip-web-service.md) 。

以下的端點資料會列出從使用者電腦到 Office 365 的連線需求。 不包括從 Microsoft 到客戶網路的網路連線，有時也稱為混合式或輸入的網路連線。

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳化​​」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](https://aka.ms/pnc)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點設定透過 Azure ExpressRoute 使用 Office 365 路由首碼支援，則這是 [是]。包含所顯示路由首碼的 BGP 社群會對齊所列的服務區域。當 ER 為 [否] 時，表示 ExpressRoute 不支援此端點集合。不過，不應假設 ER 為 [否] 的端點設定不會通告任何路由。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

