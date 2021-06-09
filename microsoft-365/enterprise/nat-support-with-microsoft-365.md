---
title: Office 365 的 NAT 支援
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: 本文提供如何大致接近您組織中使用 NAT 的每個 IP 位址的用戶端數目的詳細資料。
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688250"
---
# <a name="nat-support-with-office-365"></a>Office 365 的 NAT 支援

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

先前，指導方針建議您應使用每個 IP 位址的 Exchange 用戶端數目上限，以連接至 Office 365，每個網路埠大約2000個用戶端。
  
## <a name="why-use-nat"></a>為何要使用 NAT？

透過使用 NAT，公司網路上的數以千計人員可以「共用」一些可公開路由傳送的 IP 位址。
  
大部分公司網路都使用 private (RFC1918) IP 位址空間。 私人位址空間是由網際網路指派的號碼核證機關 (IANA) 所指派，且僅適用于不直接與全球網際網路直接路由傳送的網路。
  
若要在私人 IP 位址空間上提供對裝置的網際網路存取，組織會使用閘道技術（如防火牆和 proxy），以提供網路位址轉譯 (NAT) 或埠位址轉譯 (PAT) 服務。 這些閘道會使來自內部裝置的流量成為網際網路 (包括 Office 365) 似乎來自一或多個可公開路由傳送的 IP 位址。 來自內部裝置的每個輸出連線會轉換為公用 IP 位址上的不同來源 TCP 埠。 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>為什麼您需要讓許多連線同時 Office 365 開啟？

Outlook 可以在有增益集、共用行事曆、信箱等 ) 的情況下，開啟八個或更多的連線 (。 因為在 Windows 的 NAT 裝置上最多可使用64000埠，所以在埠耗盡之前，最多可以有8000個使用者的 IP 位址。 請注意，如果客戶使用的是非 Windows OS 型裝置的 nat，可用埠總數取決於所使用的 nat 裝置或軟體。 在此案例中，埠數目上限可能小於64000。 埠的可用性也會受到其他因素的影響，例如 Windows 限制4000埠以供自身使用，可減少60000的可用埠總數。 可能有其他應用程式（例如 Internet Explorer）可以同時連接，但需要額外的埠。
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>使用 Office 365 計算單一公用 IP 位址後支援的裝置數目上限

若要判斷單一公用 IP 位址後裝置的數目上限，您應該監視網路流量，以判斷每個用戶端的流量峰值埠使用量。 此外，埠使用量的峰值因素應該用於 (最少 4) 。 
  
 **使用下列公式計算每個 IP 位址支援的裝置數目：**
  
單一公用 IP 位址後支援的裝置數目上限 = (64000-限制的埠) / (峰值埠使用量 + 峰值因數) 
  
 **例如，如果下列條件成立：**
  
- **限制的埠：** 作業系統的4000

- **流量峰值埠消耗：** 每台裝置6個

- **峰值因素：** 4

然後，單一公用 IP 位址後支援的裝置數目上限 = (64000-4000) / (6 + 4) = 6000
  
隨著 Office 365 主控套件的發行，包含在2011年9月的更新中 Microsoft Office Outlook 2007 的更新，或 Microsoft Outlook 2010 的11月2011，或更新版本，從 Outlook (的連線數目 Office Outlook Outlook 2007 （含 Service pack 2）和) 2010 Exchange 到，都是2。 您必須在不同的作業系統、使用者行為等方面加以考慮，以判斷您的網路在高峰時所需的最小和最大端口數目。
  
如果您想要支援單一公用 IP 位址後的更多裝置，請遵循所述的步驟來評估可支援的裝置數目上限：
  
監視網路流量，以決定每個用戶端的流量峰值埠使用量。 您應該收集下列資料：
  
- 從多個位置
    
- 從多個裝置
    
- 在多次
    
使用上述公式，計算其環境中可支援的每個 IP 位址的最大使用者數。
  
將用戶端負載散佈到其他公用 IP 位址的方法有多種。 可用的策略取決於公司閘道解決方案的功能。 最簡單的解決方法是劃分使用者位址空間，並以靜態方式將多個 IP 位址指派給每個閘道。 許多閘道裝置所提供的另一種方式是使用 IP 位址集區的能力。 位址集區的優點是，在您的使用者群成長時，會有更大的動態，也不需要調整。
  
## <a name="see-also"></a>另請參閱

[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 端點常見問題集](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) (機器翻譯)
