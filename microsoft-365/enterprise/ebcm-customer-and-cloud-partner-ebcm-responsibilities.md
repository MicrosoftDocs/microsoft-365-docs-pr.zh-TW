---
title: 客戶與雲端合作夥伴企業商務持續性責任
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 在服務事件期間做了什麼，讓您可以更好地準備商務持續性計劃。
ms.openlocfilehash: c74bb83352f87faf0bb7f50e8aec4ac813516d3c
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031078"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>企業商務持續性管理客戶與雲端合作夥伴責任

為您的使用者取得 Microsoft 365 雲端服務，是貴組織與 Microsoft 之間的合作夥伴關係。 Microsoft 提供服務，而您負責與用戶端端點連線、管理身分識別和存取權以及這些服務的使用方式。 雙方有共同責任，例如身分識別和目錄基礎結構。 本文涵蓋您需要注意的一些重要項目，讓您在發生服務事件時保持商務運作，並且協助設定 Microsoft 在服務事件期間可以做什麼的期望。

## <a name="transparency-during-service-incidents"></a>服務事件期間的透明度

Microsoft 身為信任的合作夥伴，會建置高度復原雲端服務，並且遵循結構化程序，在發生服務事件時加以解決。 發生服務事件時，Microsoft 了解**及時**、**鎖定目標**且**高度可用**的通訊對客戶很重要。

## <a name="timely"></a>及時
Microsoft 會藉由更新 Microsoft 365 管理入口網站上的租用戶特定服務健康情況儀表板 (SHD)，告知 Microsoft 365 系統管理員。 服務事件更新一般是以每小時的頻率提供。 如果需要不同的頻率，我們會在 SHD 通訊文章中向您通知變更。

## <a name="targeted"></a>鎖定目標
在大部分情況下，當我們的監視系統偵測到問題時，我們可以識別受影響的客戶群體，從單一客戶到區域，並將必要通訊導向給這些客戶。 這可協助您了解對業務需要知道的事項，而不會被不影響您的雜訊通知導致分心。 例如，如果某個特定信箱資料庫受到影響，我們就能準確地識別哪些客戶有使用者在受影響的基礎結構上，並將我們的通訊範圍提供給他們。 如果您不清楚事件的影響範圍，我們會將通訊延伸到可能受影響的最廣大客戶群組。

## <a name="highly-avaliable"></a>高度可用
Microsoft 為客戶可以使用的服務狀態通訊保留多個通道。

- 如果系統管理中心或系統管理中心內的服務健康狀態儀表板無法使用，您可以使用我們的[備份網站](https://status.office365.com/)來監控服務狀態。
- 我們會維護 Twitter 帳戶 [@MSFT365Status](https://twitter.com/msft365status?lang=en)，在這個帳戶回應影響的報告，並且張貼關於 SHD 影響事件的更新。
- Microsoft 365 租用戶系統管理員的系統管理 App 可讓您在外出時，與貴組織的 Microsoft 365 服務狀態連線。 租用戶系統管理員將能夠從他們的行動裝置檢視服務健康狀況資訊及維護狀態的更新。 如需詳細資訊，請造訪[系統管理 App 常見問題集](https://docs.microsoft.com/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide)。
- [Microsoft 365 服務通訊 API](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) 可讓您存取服務通訊，您就可以更輕易地監控您的環境。 您可以連線至 API、接收即時服務健康狀態資料，以及將資訊發佈在內部儀表板上，向企業使用者通知事件。 在內部散佈資訊可以在中斷期間降低服務台流量。
- 對於重大事件，Microsoft 會將後續事件檢閱 (PIR) 發佈到系統管理中心內的 SHD。 PIR 包含重要事件資訊，可協助您了解中斷的本質。 它通常包含下列區段：
    - 使用者影響
    - 影響範圍
    - 事件開始結束日期和時間
    - 根本原因
    - 採取的動作
    - 後續步驟
- 您可以在 Microsoft 365 訊息中心中取得輔助通訊，例如近期變更、新功能或計劃維護的通知。
- 如需詳細資訊，請參閱[服務健康狀態與持續性指南](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)，深入了解不同的通訊通道和如何監視服務健康狀態。
 
提供 Microsoft 365 雲端服務的存取權，是貴組織與 Microsoft 之間的合作夥伴關係。 下圖摘要了 Microsoft 與客戶之間在服務事件和一般作業期間的責任權衡方式。

![客戶與 Microsoft 的責任權衡方式](media/ebcm/responsibilities.png)

## <a name="your-environment---service-continuity"></a>您的環境 - 服務持續性
當您考慮持續性計劃時，請注意可能會影響貴組織的事件，以及它的整體通訊能力。 在較高的層級上，有三個因素會影響您的企業。

### <a name="people"></a>人員
請考量會影響您的工作人力的事件，例如自然災害或流感。 這個項目經常被忽視，因為如果您的工作人力大範圍散佈，它的本質看似不會有大規模影響。 但是，如果大部分的工作人力都離線，您的企業還能繼續運作嗎？ 您要如何緩解這個問題？

### <a name="location"></a>位置
許多組織需要員工位於特定實體或網路位置，才能連線至企業系統與雲端服務。  
Microsoft 發佈[網路連線原則](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)，引導企業執行設定與雲端資源網路連線的最佳做法。 最佳化的範例包括實作分割通道 VPN，允許來自使用者網路的直接連線，而不是透過 VPN 通道。  雖然這些連線原則對於維護低延遲連線很重要，但是服務復原需要替代方法，針對一般共同作業連線至公司資源。

### <a name="systems"></a>系統
許多共同作業解決方案都與系統相依，例如公司廣域網路 (WAN)。 當這些系統無法使用時，貴組織會如何回應？
這個圖形呈現可能會影響多個區域的問題。 隨附的表格提供要考量的範例

![卞氏圖表](media/ebcm/venn-diagram.png)

您的持續性計劃應考量每個區域。 例如：如果您需要使用者在公司網路上，但是現在有暴風雪，這些使用者要如何取得關鍵資源的存取權？ 如果大雪阻止使用者進辦公室，而且需要服務工程師才能連線到公司網路，對於他們在家持有公司筆記型電腦是否有原則管制？
