---
title: Office 365 的網路和移轉規劃
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 本文包含對 Office 365 之網路規劃、測試及遷移之相關資訊的連結。
ms.openlocfilehash: aed8bacd4dc08aa6d77ad0c530e721ac9d383bf5
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149103"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 的網路和移轉規劃

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

本文包含網路規劃與測試以及移轉至 Office 365 的相關資訊連結。
  
在首次部署或移轉至 Office 365 前，您可使用這些主題的資訊來預估您需要的頻寬，然後測試並確認您有足夠頻寬可部署或移轉至 Office 365。

本文是 [Office 365 的網路規劃與效能調整](./network-planning-and-performance.md)的一部分。

如需針對 Microsoft 365 和其他 Microsoft 雲端平臺及服務優化網路的步驟，請參閱[Microsoft 雲端網路，以取得 Enterprise 架構師](../solutions/cloud-architecture-models.md)海報。
   
## <a name="estimate-network-bandwidth-requirements"></a>預估網路頻寬需求
<a name="EstimateBandwidthRequirements"> </a>

使用 Office 365 可能會增加貴組織的網際網路電路使用量。 請務必確定目前的頻寬是否足以負荷 Office 365 完整部署後的估計增加量，並且至少預留 20% 的頻寬，以因應極度忙碌時期。
  
若要估計頻寬，請依照下列步驟操作︰
  
1. 評估會使用每個網際網路出口的用戶端數量。 盡可能地讓我們的多兆位元網路處理連線。 
    
2. 決定哪些 Office 365 服務與功能可供用戶端使用。 您可能需要一組人員搭配不同的服務或使用設定檔。
    
3. 針對由用戶端組成的試驗群組測量網路使用狀況。 請確保試驗用戶端能代表組織中屬於各種不同設定檔及地理位置的人員。 您可以對照我們舊的計算機，在您的[Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)和[Microsoft Teams](/microsoftteams/prepare-network)或在我們自己的網路上執行的[案例研究](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)，以交叉檢查您的結果。 
    
4. 從試驗群組的測量結果推算整個組織的需求，然後重新測試以驗證估計值，再變更您的網路設定。
    
## <a name="test-your-existing-network"></a>測試您現有的網路
<a name="calculators"> </a>

 **網路工具：** 測試及驗證您的網際網路頻寬，以判斷下載、上傳和延遲限制。 這些工具會協助您確定用於移轉及完整部署後的網路能力。 
    
- [Microsoft 遠端連線能力分析器](https://go.microsoft.com/fwlink/p/?LinkId=517243)：測試您 Exchange Online 環境的連線能力。
    
- 使用 [Microsoft Office 365 支援服務及修復小幫手](https://diagnostics.office.com/#/Download?env=SOC)修正 Outlook 與 Office 365 問題。 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Office 365 的網路規劃和移轉效能改善最佳作法
<a name="BestPractices"> </a>

如需改善 Office 365 體驗的詳細資訊，請進一步閱讀這些最佳做法。
  
1. 您想立即開始協助您的使用者嗎？ 如果您在使用包含 SharePoint Online、Exchange Online 和 Lync Online 等 Office 365 產品時網路運作不順暢，請參閱[在網路緩慢的情況下使用 Office 365 的最佳做法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 本文含有大量 TechNet 及 Support.office.com 的連結，內容介紹如何最佳化您的 Office 365 體驗，並包含輕鬆自訂網頁的方法，以及如何設定 Internet Explorer 以享受最佳 Office 365 體驗等資訊。 
    
2. 請閱讀 [Office 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)，了解安全管理 Office 365 流量以及可能獲取最佳效能的連線原則。 本文將協助您了解以安全方式最佳化 Office 365 的網路連線能力的最新指引。 
    
3. 謹慎管理 Windows Updates 排程來改善郵件移轉效能。 您可以批次更新用戶端電腦，確定所有用戶端電腦已在移轉至 Office 365 前更新，以管制網路頻寬的使用。 如需詳細資訊，請參閱[針對 Office 365 手動更新及設定電腦以取得最新更新](https://support.microsoft.com/gp/office-2013-365-update)。
    
4. 有些組織將 Office 365 放置在不受信任網際網路服務的網路流量上，然而，Office 365 網路流量在被視為受信任的網際網路服務而允許略過大部分的篩選和掃描時可以達到最佳效能。 這通常包括移除如 Proxy 使用者驗證和封包檢查等輸出處理，以及確保本機出口至網際網路使用正確的網路位址轉譯 (NAT) 和擁有足夠的頻寬能力可以處理增加的網路需求。 如需有關設定您的網路，將您網路中的 Office 365 視為受信任網際網路服務進行處理的其他指引，請參閱[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。
    
1. 務必閱讀[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。 移往 Office 365 的其他流量會導致輸出 Proxy 連線的增加以及 TLS/SSL 安全流量的增加。
    
2. 如果您的輸出 Proxy 需要使用者驗證，您可能會遇到連線速度緩慢或喪失連線能力的狀況。 略過 Office 365 網域的驗證需求可以減少這項負擔。
    
3. 如果您有大量的共用行事曆和信箱，可能會看見從 Outlook 至 Exchange 的連線數目增加。 例如，Outlook 用戶端可能會針對每個使用中的共用行事曆，開啟最多兩個額外連線。 在此情況下，請確定出口 Proxy 可以處理連線，或針對 Outlook 對 Office 365 的連線來略過 Proxy。
    
4. 決定公用 IP 位址的支援裝置數目上限，以及如何平衡多個 IP 位址的負載。 如需詳細資訊，請參閱 [Office 365 的 NAT 支援](nat-support-with-microsoft-365.md)。
    
5. 如果您正在檢查您網路上電腦的輸出連線，針對 Office 365 網域略過此篩選可以改善連線能力及效能。 此外，略過輸出檢查通常不需要單一網際網路出口，而且會啟用 Office 365 的本機網際網路出口目的地為網路的需求。
    
6. 有些客戶會發現內部網路設定可能會影響效能。 如傳輸單元最大值 (MTU) 的大小、網路自動交涉或自動偵測以及網際網路的次佳路由等設定都是要經常查看的地方。
    
## <a name="network-planning-reference-for-office-365"></a>Office 365 的網路規劃參考
<a name="NetReference"> </a>

下列主題包含詳細的 Office 365 網路參考資訊。
  
- [管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [內容傳遞網路](content-delivery-networks.md)
    
- [Office 365 的外部網域名稱系統記錄](external-domain-name-system-records.md)
    
- [Office 365 服務中的 IPv6 支援](ipv6-support.md)
    
- [Office 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)
    
- [規劃連線到 Office 365 服務的網路裝置](plan-for-network-devices.md)
    
- [Office 365 服務的設定指南](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)