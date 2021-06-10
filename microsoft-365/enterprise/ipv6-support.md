---
title: Office 365 服務中的 IPv6 支援
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 摘要：說明 Microsoft Office 365 元件及 Office 365 政府產品中的 IPv6 支援。
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909679"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 服務中的 IPv6 支援

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Office 365 同時支援 IPv6 和 IPv4;不過，使用 IPv6 並不會完全啟用所有的 Office 365 功能。 這表示您必須同時使用 IPv4 和 IPv6 以連接至 Office 365。 若要將輸出的流量篩選為 Office 365，可在本文[Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)中找到 Office 365 所支援之 IPv6 位址的完整清單。 在設定網路並允許適當的 IPv6 位址之後，您可以從 Microsoft 下載中心下載[Office 365 IPv6 測試方案](https://go.microsoft.com/fwlink/?LinkId=293447)。
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Office 365 訂閱服務中的 IPv6 支援

### <a name="exchange-online-and-ipv6"></a>Exchange Online 和 IPv6

如果您用來連線至 Exchange Online 的程式支援 IPv6，則在有線網路和無線網路上預設會使用 IPv6。 如果您想要控制 Exchange Online 的通訊，請使用[Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)中的 ip 位址範圍。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint線上及 IPv6

 **Office 365 政府版 G1/G3/G4/K1** 如果您用來連線至 SharePoint Online 的程式支援 IPv6，則預設會嘗試使用 IPv6。
  
 **公用多租使用者雲端** Microsoft 可在您的要求 IPv6 線上 SharePoint。 您需要為組織的 DNS 基礎結構提供 CIDR 表示的 IP 位址。 請記住，其他組織無法共用此 DNS 基礎結構，因此無法為您的租使用者啟用 IPv6。 啟用 IPv6 之後，如果您用來連線到 SharePoint Online 的程式支援 IPv6，則預設會使用 IPv6。
  
如果您用來連線至 SharePoint Online 的程式支援 IPv6，則在有線網路和無線網路上的預設 IPv6 都會使用。 如果您想要控制 SharePoint 線上的通訊，請使用[Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)中的 ip 位址範圍。
  
 **Office 365 政府版 G1/G3/G4/K1** 如果您用來連線至 SharePoint Online 的程式支援 IPv6，則預設會嘗試使用 IPv6。
  
### <a name="skype-for-business-and-ipv6"></a>商務用 Skype 和 IPv6

請注意商務用 Skype 中不支援 IPv6，且無法再啟用。

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 和 IPV6

Microsoft Teams直接路由只支援 IPv4。 Microsoft Teams 服務及用戶端支援 IPv4 和 IPv6。 如果您想要控制 Microsoft Teams 的通訊，請使用[Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)中的 ip 位址範圍。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 和 IPv6

Exchange Online Protection (EOP) 支援 IPv6 如果傳輸是透過傳輸層安全性通訊協定進行。 針對 EOP 範圍，使用[Office 365 URLs 及 IP 位址範圍](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6 對 Office 365 政府產品的支援

Office 365IPv6 對政府產品的支援，Office 遵循管理和預算 (OMB) 備忘錄，以供高層和代理商的首席資訊官，以及聯邦政府採用網際網路通訊協定第6版 (IPv6 備忘錄。 [Microsoft Office 365 政府](https://go.microsoft.com/fwlink/p/?LinkId=325414)是一項多承租人服務，可將政府資料儲存在隔離的社區雲端中。 與其他 Office 365 的產品一樣，它還提供生產力與共同作業服務，包括 Exchange Online、商務用 Skype、SharePoint 線上及 Microsoft 365 Apps 企業版。 

Microsoft Office 365 的政府產品只適用于2013和更新版本。 如需 Office 365 政府產品的詳細資訊，請參閱[為政府： A US 政府社群雲端宣佈 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=325414)。 Arm 規章中的國際流量 (ITAR) 是一組美國政府規定，可控制如何匯出及匯入 [美國 Munitions 清單 (USML) ](https://go.microsoft.com/fwlink/p/?LinkId=325415)上的國防相關文章和服務。 

適用于企業的 Microsoft Office 365 會為 Microsoft 生產力解決方案提供專屬的主機服務，以支援美國聯邦機關的安全性、隱私權和法規遵從性需求。 (FISMA) 認證和商業實體受制于 ITAR。
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>使用 IPv6 和 Office 365 時的考慮事項

建議您不要停用 IPv6。 如需詳細資訊，請參閱本 [指南文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 若要決定網路上使用的 IP 版本，請考慮下列各項：
  
- 如果在命令提示字元處顯示的 **IPConfig** 命令包含名為「IPv6 Address "或" 暫時性 IPv6 address "的列，表示您在環境中已 IPv6。

- 如果所有的 IPv6 位址開頭都是 "fe80"，且對應至名稱為「Link-Local IPv6 Address "的列，則您的環境中不會有 IPv6。

這些考慮可能適用于您的網路：
  
- 公用訂閱服務不支援透過信用卡以信用卡進行購買 IPv6。 這不適用於政府社群雲端 (GCC) ，因為政府已 Enterprise 合約 (的 EA) 授權。

- IPv6 不支援某些 Rights Management Services (RMS) 案例。

- IPv6 不支援 BlackBerry® Enterprise Server (be) ，因為 BlackBerry 不支援 IPv6。

- 如果您使用 Active Directory Federation Services (AD fs) 搭配 Office 365，則不支援使用 IPv6 來公佈您的 ad fs 網路端點至 Office 365。 使用 Exchange Online 時，不應在 AD FS DNS 專案中包含 AAAA 記錄。 

您可以使用下列短連結返回這裡：[https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>另請參閱

[IPv6 學習藍圖](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 生存指南](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)