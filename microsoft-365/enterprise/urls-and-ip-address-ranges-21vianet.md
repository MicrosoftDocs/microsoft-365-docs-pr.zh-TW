---
title: 21Vianet 運作的 Office 365 的 URL 和 IP 位址範圍
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/29/2021
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
ms.openlocfilehash: ed9b6fdbef1ca121ccf53b635768ebdaab89763a
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418043"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a><span data-ttu-id="376a3-103">21Vianet 運作的 Office 365 的 URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="376a3-103">URLs and IP address ranges for Office 365 operated by 21Vianet</span></span>

 <span data-ttu-id="376a3-104">*適用於：21Vianet 運作的 Office 365 - 小型企業系統管理員，21Vianet 運作的 Office 365 - 系統管理員*</span><span class="sxs-lookup"><span data-stu-id="376a3-104">*Applies To: Office 365 operated by 21Vianet - Small Business Admin, Office 365 operated by 21Vianet - Admin*</span></span>

<span data-ttu-id="376a3-105">**摘要**：下列端點 (FQDN、 連接埠、URL、IPv4 和 IPv6 前置字元) 適用於 21Vianet 運作的 Office 365，且專門針對只使用這些計畫為組織提供生產力服務所設計。</span><span class="sxs-lookup"><span data-stu-id="376a3-105">**Summary**: The following endpoints (FQDNs, ports, URLs, IPv4, and IPv6 prefixes) apply to Office 365 operated by 21 Vianet and are designed to deliver productivity services to organizations using only these plans.</span></span>
  
 <span data-ttu-id="376a3-106">**Office 365 端點：** [全球 (包括 GCC)](urls-and-ip-address-ranges.md)  | *21 Vianet 提供的 Office 365* | [Office 365 德國](microsoft-365-germany-endpoints.md) |  [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="376a3-106">**Office 365 endpoints:** [Worldwide (including GCC)](urls-and-ip-address-ranges.md)  | *Office 365 operated by 21 Vianet* | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="376a3-107">**上次更新：** 03/29/2021- ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="376a3-107">**Last updated:** 03/29/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>|<span data-ttu-id="376a3-108">**下載：** 一個 [JSON 格式](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)清單中所有必要與選用的目的地。</span><span class="sxs-lookup"><span data-stu-id="376a3-108">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> |

<span data-ttu-id="376a3-109">從[管理 Office 365 端點](managing-office-365-endpoints.md)開始，以了解我們針對在使用此資料管理網路連線能力方面的建議。</span><span class="sxs-lookup"><span data-stu-id="376a3-109">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data.</span></span> <span data-ttu-id="376a3-110">端點資料會在每個月初根據需要進行更新，並在上線前 30 天發布新的 IP 位址和 URL。 </span><span class="sxs-lookup"><span data-stu-id="376a3-110">Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active.</span></span> <span data-ttu-id="376a3-111">這讓尚未進行自動更新的客戶，能在需要新連線前完成該程序。 </span><span class="sxs-lookup"><span data-stu-id="376a3-111">This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required.</span></span> <span data-ttu-id="376a3-112">如果需要解決支援升級、安全性事件或其他即時操作需求，則還可以在該月內更新端點。 </span><span class="sxs-lookup"><span data-stu-id="376a3-112">Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements.</span></span> <span data-ttu-id="376a3-113">本頁下方顯示的資料全部來自基於 REST 的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="376a3-113">The data shown on this page below is all generated from the REST-based web services.</span></span> <span data-ttu-id="376a3-114">如果您正使用指令碼或網路裝置來存取本資料，您應直接前往 [Web 服務](microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="376a3-114">If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="376a3-p102">下列端點資料列出使用者的電腦到 Office 365 的連線需求。這不包括從 Microsoft 到客戶網路的網路連線，有時稱為混合式或輸入網路連線。</span><span class="sxs-lookup"><span data-stu-id="376a3-p102">Endpoint data below lists requirements for connectivity from a user’s machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span>

<span data-ttu-id="376a3-p103">端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="376a3-p103">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="376a3-120">所顯示的資料行為︰</span><span class="sxs-lookup"><span data-stu-id="376a3-120">Data columns shown are:</span></span>

- <span data-ttu-id="376a3-p104">**識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。</span><span class="sxs-lookup"><span data-stu-id="376a3-p104">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="376a3-p105">**類別**：顯示端點設定是否分類為「最佳」、「允許」或「預設」。您可以在 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。</span><span class="sxs-lookup"><span data-stu-id="376a3-p105">**Category**: Shows whether the endpoint set is categorized as “Optimize”, “Allow”, or “Default”. You can read about these categories and guidance for management of them at [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="376a3-p106">**ER**：如果端點設定透過 Azure ExpressRoute 使用 Office 365 路由首碼支援，則這是 [是]。包含所顯示路由首碼的 BGP 社群會對齊所列的服務區域。當 ER 為 [否] 時，表示 ExpressRoute 不支援此端點集合。不過，不應假設 ER 為 [否] 的端點設定不會通告任何路由。</span><span class="sxs-lookup"><span data-stu-id="376a3-p106">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="376a3-p107">**地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="376a3-p107">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="376a3-p108">**連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。</span><span class="sxs-lookup"><span data-stu-id="376a3-p108">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]