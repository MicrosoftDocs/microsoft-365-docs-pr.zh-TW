---
title: Office 365 URL 和 IP 位址範圍
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 摘要：Office 365 需要連線到網際網路。客戶必須可使用 Office 365 方案取得下列端點，包括 Government Community Cloud (GCC)。
hideEdit: true
ms.openlocfilehash: 48be058cb48e99b9b573cc4211561dfe8e5cc6e8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730147"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 位址範圍

Office 365 需具有網際網路的連線能力。使用　Office 365 方案的客戶必須可取得下列端點，包括 Government Community Cloud (GCC)。
  
*Office 365 全球 (+GCC)* | [21 Vianet 提供的 Office 365](urls-and-ip-address-ranges-21vianet.md) | [Office 365 德國](microsoft-365-germany-endpoints.md) | [Office 365 美國政府 DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 美國政府 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**上次更新日期：** 2021 年 5 月 28 日 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [變更記錄訂閱](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**下載：** 一個 [JSON 格式](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)清單中所有必要與選用的目的地。  <br/> | **使用：** 我們的 proxy [PAC 檔案](managing-office-365-endpoints.md#pacfiles) <br/> |

 開始使用[管理 Office 365 端點](managing-office-365-endpoints.md)了解我們針對使用這項資料來管理網路連線的建議。每個月初會視需要使用在作用中的 30 天前發行的新 IP 位址和 URL 來更新端點資料。這項功能可讓尚未自動化更新的使用者在需要新的連線之前完成其程序。如果提出支援向上呈報、安全性事件或其他立即操作需求，在當月期間可能也會更新端點。下面這個頁面上所顯示的資料會從 REST 為基礎的網路服務產生。如果您使用指令碼或網路裝置來存取這些資料，應該直接前往 [Web 服務](microsoft-365-ip-web-service.md)。

下列端點資料列出了從使用者機器到連線至 Office 365 的要求。它不包括從 Microsoft 到客戶網路的網路連線，有時稱為混合式或輸入網路連線。如需詳細資訊，請參閱[其他端點](additional-office365-ip-addresses-and-urls.md)。

端點則被歸類成四個服務區域。前三個服務區域可以個別選取進行連線。第四個服務區域 (稱為 Microsoft 365 Common 與 Office) 的常見相依性，且必須一律具有網路連線能力。

所顯示的資料行為︰

- **識別碼**：資料列的識別碼，也就是端點設定。此 ID 與端點設定的 web 服務所傳回的相同。

- **類別**：顯示端點設定是否分類為「最佳」、「允許」或「預設」。您可以在 [新 Office 365 端點類別](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)中讀取這些類別和在其中管理的指導方針。此欄也會列出網路連線需要哪些端點設定。對於不需要有網路連線的端點設定，我們會在這個欄位中提供附註，表示如果端點設定受到封鎖，將會遺失什麼功能。如果您不包含整個服務區域，視需要列出的端點設定將不需要連線能力。

- **ER**：如果端點設定透過 Azure ExpressRoute 使用 Office 365 路由首碼支援，則這是 [是]。包含所顯示路由首碼的 BGP 社群會對齊所列的服務區域。當 ER 為 [否] 時，表示 ExpressRoute 不支援此端點集合。不過，不應假設 ER 為 [否] 的端點設定不會通告任何路由。

- **地址**：列出端點設定的 FQDN 或萬用字元網域名稱及 IP 位址範圍。請注意，IP 位址範圍為 CIDR 格式，且在指定的網路中可能包含讓多個個別的 IP 位址。
 
- **連接埠**：列出與地址結合以形成網路端點的 TCP 或 UDP 連接埠。您可能會注意到列出不同連接埠的某些 IP 位址範圍中有重複項目。

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>有關 Yammer IP 位址和 URL 的建議，請參閱 Yammer 部落格上的[不建議為 Yammer 使用硬式編碼 IP 位址](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592)。
>

## <a name="related-topics"></a>相關主題
[Office 365 IP 位址和 URL Web 服務中未包含的其他端點](additional-office365-ip-addresses-and-urls.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[一般 Microsoft Stream 端點](/stream/network-overview#general-microsoft-stream-endpoints)
  
[監視 Microsoft 365 連線能力](./monitor-connectivity.md)

[在第三方應用程式系統上的根 CA 和中繼 CA 集合檔](../compliance/encryption-office-365-certificate-chains.md)
  
[用戶端連線](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[內容傳遞網路](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure IP 範圍與服務標籤 - 公用雲端](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure IP 範圍與服務標籤 - 美國政府雲端](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure IP 範圍與服務標籤 - 德國雲端](https://www.microsoft.com/download/details.aspx?id=57064)

[Microsoft Azure IP 範圍與服務標籤 - 中國雲端](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 公用 IP 空間](https://www.microsoft.com/download/details.aspx?id=53602)

[服務名稱和傳輸通訊協定連接埠號碼登錄](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
