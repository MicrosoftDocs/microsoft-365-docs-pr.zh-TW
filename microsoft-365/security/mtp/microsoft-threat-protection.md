---
title: Microsoft 威脅防護
description: Microsoft 威脅防護是一種協同的威脅防護解決方案，其設計目的是為了保護裝置、身分識別、資料和應用程式
keywords: Microsoft 威脅防護簡介，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: afeef8de09e0ee7a727372041791871712ca4e0d
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560892"
---
# <a name="microsoft-threat-protection"></a>Microsoft 威脅防護

適用於：****
- Microsoft 威脅防護



Microsoft 威脅防護是一種整合的後續企業防護套件，其可在端點、身分識別、電子郵件和應用程式中共同協調偵測、預防、調查和回應，以提供複雜攻擊的整合式防護。

透過整合的 Microsoft 威脅防護解決方案，安全性專業人員可以結合上述威脅，讓每一種產品收到並決定威脅的完整範圍和影響;如何進入環境、受到影響的內容，以及目前對組織的影響。 Microsoft 威脅防護會自動採取動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。  


<center><h2>Microsoft 威脅防護服務</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender 高級威脅防護</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365 高級威脅防護</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure 高級威脅防護</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>請查看此[Microsoft 威脅防護互動指南](https://aka.ms/MTP-Interactive-Guide)。


Microsoft 威脅防護套件可保護： 
- **使用 Microsoft DEFENDER atp 的端點**-MICROSOFT defender atp 是一種整合的端點平臺，可提供預防性防護、入侵後偵測、自動調查和回應。 
- **電子郵件與共同作業與 office 365 atp** -OFFICE 365 atp 會保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。 
- **使用 AZURE atp 和 AZURE AD 身分識別保護**的身分識別-azure Atp 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、受損身分識別和惡意有問必答動作。 
- **使用 Microsoft Cloud app security 的應用程式**-Microsoft cloud app security 是一種完整的跨 SaaS 解決方案，對您的雲端應用程式帶來深入的可見度、強資料控制及增強威脅防護。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 威脅防護獨特的跨產品層將個別套件元件擴充為下列專案：
- 協助防範攻擊，並透過信號共用和自動動作協調整個套件的防禦回應
- 將提醒上的資料、可疑的事件及受影響的資產加入「事件」，針對安全性小組的產品警示、行為和內容敘述完整的攻擊案例
- 透過自動修復觸發對受影響資產的自我修復，以自動化安全回應
- 讓安全性小組能夠跨端點和 Office 資料執行詳細且有效的威脅搜尋

![事件的影像概述頁面](../../media/overview-incident.png) <br>
跨產品的事件 (綜述) 

![警示佇列的影像](../../media/incident-list.png)<br>
套件產品間所有相關的警示，與單一事件 (提醒] 查看) 

![事件佇列的影像](../../media/advanced-hunting.png)<br>
電子郵件和端點原始資料上方的查詢式搜尋


Microsoft 威脅防護跨產品的功能包括： 
- **跨產品單一窗格的玻璃**-中央視圖所有偵測資訊、受影響資產、自動執行的動作，以及[security.microsoft.com](https://security.microsoft.com)中單一窗格中的相關證據。 
- **結合的事件佇列**-若要協助安全性專業人員著重于確保完整攻擊範圍的重要因素，請將受影響的資產和自動修正動作組合在一起，並及時出現。 
- **對威脅的自動回應**-在 Microsoft 威脅防護產品間即時共用重要威脅資訊，以協助停止攻擊的進展。 例如，如果在 Microsoft Defender ATP 保護的端點上偵測到惡意檔案，則會指示 Office 365 ATP 掃描並移除所有電子郵件中的檔案。 整個 Microsoft 365 安全套件會封鎖檔案。
- **受到損害的裝置、使用者身分識別及信箱的自我修復**-Microsoft 威脅防護使用 AI 功能的自動動作和行動裝置，將受影響的資產修正回安全狀態。 Microsoft 威脅防護利用套件產品的自動修正功能，確保與事件相關的所有受影響資產都會在可能的情況下自動修正。
- **跨產品威脅搜尋**-安全小組可以透過透過各種保護產品所收集的原始資料來建立自己的自訂查詢，利用其獨特的組織知識來尋找損害的跡象。 Microsoft 威脅防護會提供以查詢為基礎的存取權，可存取30天之歷史原始信號，以及跨端點和 Office 365 ATP 資料發出警示資料。 


## <a name="get-started"></a>開始使用
您必須先符合 microsoft 威脅防護授權的需求，才能在 Microsoft 365 security center 中啟用服務，請[security.microsoft.com](https://security.microsoft.com)。 如需詳細資訊，請參閱：
- [授權需求](prerequisites.md#licensing-requirements)
- [開啟 Microsoft 威脅防護](mtp-enable.md)
