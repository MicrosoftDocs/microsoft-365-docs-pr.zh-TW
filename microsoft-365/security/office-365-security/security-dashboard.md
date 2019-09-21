---
title: 安全性儀表板概觀
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: 使用新的安全性儀表板來檢閱 Office 365 威脅保護狀態，並檢視，然後對安全性提醒。
ms.openlocfilehash: 8f86aa654c79bac2409d64b43d0cf7bb563c1412
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077362"
---
# <a name="security-dashboard"></a>安全性儀表板

## <a name="overview"></a>概觀

[安全性&amp;合規性中心](../../compliance/go-to-the-securitycompliance-center.md)可讓您的組織管理的資料保護和合規性。 安全性儀表板假設您具備必要權限，可讓您檢閱您威脅保護的狀態，以及檢視並處理安全性提醒。 
  
請觀看影片，概略了解，然後閱讀本篇文章以了解更多。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
根據貴組織的 Office 365 訂用帳戶包含內容，安全性儀表板包含數個 widget，例如威脅管理摘要、 威脅保護狀態、 全域每週的威脅偵測、 惡意程式碼，以及更多]，如所述下列各節。
  
若要檢視中的 [安全性儀表板， [Office 365 安全性&amp;合規性中心](../../compliance/go-to-the-securitycompliance-center.md)，請移至**威脅管理** \> **儀表板**。
  
> [!NOTE]
> 您必須是 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者若要檢視安全性儀表板。 某些 widget 需要其他權限才能檢視。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="threat-management-summary"></a>威脅管理摘要

威脅管理摘要] 小工具會告訴您一眼防止威脅保護您的組織已方式，過去七 （7） 天。

![安全性儀表板-威脅管理摘要] 小工具](../media/SecDash-ThreatMgmtSummary.png)

您會看到的威脅管理摘要中的資訊取決於您的訂閱所包含的內容。 下表說明會包含 Office 365 E3 和 Office 365 E5 哪些資訊。


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|已封鎖的惡意程式碼訊息<br/>封鎖的網路釣魚郵件<br>由使用者報告的郵件<br><br><br><br> |已封鎖的惡意程式碼訊息<br>封鎖的網路釣魚郵件<br>由使用者報告的郵件<br>零時差惡意程式碼遭到封鎖<br>偵測到的進階網路釣魚郵件<br>惡意 Url 封鎖 |

若要檢視或存取威脅管理摘要] 小工具，您必須檢視進階威脅防護報告的權限。 若要深入了解，請參閱[檢視 ATP 報告需要哪些權限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="threat-protection-status"></a>威脅保護狀態

威脅保護狀態] 小工具顯示與趨勢和詳細資料檢視的釣魚程式和惡意程式碼威脅保護效率。 

![威脅保護狀態] 小工具](../media/tpswidget.png)

詳細資料取決於您的 Office 365 訂閱是否包含[Exchange Online Protection](exchange-online-protection-eop.md) (EOP)，或者沒有[Office 365 進階威脅防護](office-365-atp.md)(ATP)。


|如果您的訂閱包含...] |您會看到這些詳細資料 |
|---------|---------|
|EOP，但不是 Office 365 ATP     |偵測到並由 EOP 封鎖惡意電子郵件<br> 請參閱[威脅保護狀態報表 (EOP)](../../compliance/view-email-security-reports.md#threat-protection-status-report)。| |
|Office 365 ATP |惡意內容和惡意電子郵件偵測並封鎖由 EOP 和 Office 365 ATP<br>彙總的數唯一的電子郵件與反惡意程式碼引擎、[零時差自動清除](zero-hour-auto-purge.md)，並 ATP 功能 （包括[安全連結](atp-safe-links.md)、[安全附件](atp-safe-attachments.md)及[ATP 防網路釣魚](atp-anti-phishing.md)） 封鎖惡意內容的詳細資訊。<br>請參閱[威脅保護狀態報表 (ATP)](view-reports-for-atp.md#threat-protection-status-report)。 | 

若要檢視或存取威脅保護狀態] 小工具，您必須檢視進階威脅防護報告的權限。 若要深入了解，請參閱[檢視 ATP 報告需要哪些權限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="global-weekly-threat-detections"></a>全域每週的威脅偵測
 
全域每週的威脅偵測] 小工具顯示多少威脅所電子郵件中偵測到過去七 （7） 天。

![全域每週威脅偵測小工具](../media/globalweeklythreatdetections.png)

下表所述，會計算度量資訊：

|評量  |計算方式  |
|---------|---------|
|已掃描的郵件 |掃描電子郵件數量乘以收件者數目 |
|停止的威脅  |電子郵件被識別為包含惡意程式碼收件者數目乘以數目 |
|封鎖的[ATP](office-365-atp.md) |封鎖的 ATP 乘上的收件者的電子郵件訊息的數目 |
|在傳遞後移除 |移除[零時差自動清除](zero-hour-auto-purge.md)乘上的收件者的郵件數目 |

## <a name="malware"></a>惡意程式碼

惡意程式碼 widget 過去七 （7） 天顯示有關惡意程式碼趨勢和惡意程式碼家庭類型的詳細資料。

![惡意程式碼趨勢和家庭類型](../media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>深入資訊

深入了解不僅呈現關鍵問題，您應檢閱，它們也包含要考慮的建議與動作。 

![智慧深入解析](../media/smartinsights.png)

例如，您可能會看到網路釣魚電子郵件會被傳遞，因為某些使用者已停用其垃圾郵件] 選項。 若要深入了解觀點的運作方式，請參閱[報表和深入了解 Office 365 安全性&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)。
  
## <a name="threat-investigation-and-response"></a>威脅調查及回應

如果您的組織訂閱包含[Office 365 進階威脅防護計劃 2](office-365-ti.md)，安全性儀表板會有一個區段，包括進階的威脅調查及回應工具。 貴組織的安全性小組可以了解新興行銷活動、 調查威脅及管理事件，以使用本節中的資訊。 
  
![威脅情報可協助您了解財經貴組織的攻擊](../media/threatintelwidget.png)
  
  
## <a name="trends"></a>趨勢

安全性儀表板底部附近會摘要說明您組織的電子郵件流程趨勢**趨勢**] 區段。 報表會提供電子郵件分類為垃圾郵件、 惡意程式碼、 網路釣魚企圖和良好的電子郵件的相關資訊。 按一下 [在報告中檢視的詳細的資訊的磚。 
  
![趨勢節摘要列出組織的電子郵件流程趨勢](../media/trends.png)
  
而且，如果貴組織的 Office 365 訂用帳戶包含[Office 365 進階威脅防護計劃 2](office-365-ti.md)，您也必須**最近的威脅管理通知**報表在此] 區段中，可讓您的安全性小組，以檢視並採取動作高優先順序安全性提醒。 

若要檢視或存取已傳送和接收電子郵件] 小工具，您必須檢視進階威脅防護報告的權限。 若要深入了解，請參閱[檢視 ATP 報告需要哪些權限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

若要檢視或存取最近的威脅管理通知] 小工具，您必須檢視警示的權限。 若要深入了解，請參閱[檢視警示所需的 RBAC 權限](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。
  
## <a name="related-topics"></a>相關主題

[檢視安全性中的電子郵件安全性報告&amp;合規性中心](../../compliance/view-email-security-reports.md)
  
[檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 威脅調查及回應](office-365-ti.md)
  

