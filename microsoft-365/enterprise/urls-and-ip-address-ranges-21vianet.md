---
title: 21Vianet 運作的 Office 365 的 URL 和 IP 位址範圍
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/28/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: 本文列出在中國的世紀運作時，Office 365 的 URLs 和 IP 位址範圍。
hideEdit: true
ms.openlocfilehash: dae2b5feb4fbf7fc3e9bdd2419e2d114b5507ee8
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597067"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>21Vianet 運作的 Office 365 的 URL 和 IP 位址範圍

 *適用於：21Vianet 運作的 Office 365 - 小型企業系統管理員，21Vianet 運作的 Office 365 - 系統管理員*

**摘要**：下列端點 (FQDN、 連接埠、URL、IPv4 和 IPv6 前置字元) 適用於 21Vianet 運作的 Office 365，且專門針對只使用這些計畫為組織提供生產力服務所設計。
  
 **Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md)  | *21 Vianet 提供的 Office 365* | [Office 365 德國](microsoft-365-germany-endpoints.md) |  [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**上次更新：** 08/28/2020- ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**下載：** 一個 [JSON 格式](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)清單中所有必要與選用的目的地。  <br/> |

請從 [管理 Office 365 端點](managing-office-365-endpoints.md) 開始，以瞭解如何使用此資料來管理網路連線的建議。 端點資料會在每月開始時以所需方式更新，並提供新的 IP 位址，並在作用中預先發行30天的 URLs。 這可讓尚無自動更新的客戶完成其程式，然後才需要新的連線能力。 如果需要解決支援上報、安全性事件或其他立即運作需求，也可以在當月期間更新端點。 以下顯示在此頁面上的資料都是由 REST web 服務所產生。 如果您使用腳本或網路裝置來存取此資料，您應該直接前往 [Web 服務](microsoft-365-ip-web-service.md) 。

下列端點資料列出使用者的電腦到 Office 365 的連線需求。這不包括從 Microsoft 到客戶網路的網路連線，有時稱為混合式或輸入網路連線。

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](https://aka.ms/pnc)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點設定透過 Azure ExpressRoute 使用 Office 365 路由首碼支援，則這是 [是]。包含所顯示路由首碼的 BGP 社群會對齊所列的服務區域。當 ER 為 [否] 時，表示 ExpressRoute 不支援此端點集合。不過，不應假設 ER 為 [否] 的端點設定不會通告任何路由。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


