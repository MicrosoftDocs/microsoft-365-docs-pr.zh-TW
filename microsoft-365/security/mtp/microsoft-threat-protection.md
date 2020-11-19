---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一個協同的威脅防護解決方案，其設計目的是為了保護裝置、身分識別、資料和應用程式
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 573f30dc3d8a43a337a4333dbaf05baf916857fa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357896"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender？ 您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 Defender 是一種整合的後續企業防護套件，其可在端點、身分識別、電子郵件和應用程式中共同協調偵測、預防、調查和回應，以提供複雜攻擊的整合式防護。

透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合每一種產品接收及決定威脅的完整範圍和影響，以結合威脅。如何進入環境、受到影響的內容，以及目前對組織的影響。 Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。  


<center><h2>Microsoft 365 Defender 服務</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender 身分識別</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>請參閱《 [Microsoft 365 Defender 互動指南》](https://aka.ms/MTP-Interactive-Guide)。


Microsoft 365 Defender 套件可保護： 
- **使用 Microsoft defender For endpoint 的端點** -microsoft Defender for endpoint 是一個整合的端點平臺，可提供預防性防護、破壞性偵測、自動調查和回應。 
- **電子郵件與共同作業與 Microsoft defender For office 365** -office 365 的 defender 針對電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅進行保護。 
- **使用 Microsoft defender 身分識別與 AZURE AD 身分識別保護** 的身分識別： microsoft Defender for Identity 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的內幕程式列動。 
- **使用 Microsoft Cloud app security 的應用程式** -Microsoft cloud app security 是一種完整的跨 SaaS 解決方案，對您的雲端應用程式帶來深入的可見度、強資料控制及增強威脅防護。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 獨特的跨產品層將個別套件元件擴充為下列專案：
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


Microsoft 365 Defender 跨產品功能包括： 
- **跨產品單一窗格的玻璃** -中央視圖所有偵測資訊、受影響資產、自動執行的動作，以及 [security.microsoft.com](https://security.microsoft.com)中單一窗格中的相關證據。 
- **結合的事件佇列** -若要協助安全性專業人員著重于確保完整攻擊範圍的重要因素，請將受影響的資產和自動修正動作組合在一起，並及時出現。 
- **對威脅的自動回應** -重要威脅資訊可在 Microsoft 365 Defender 產品間即時共用，以協助停止攻擊的產生。 例如，如果在 Microsoft Defender for Endpoint 所保護的端點上偵測到惡意檔案，則會指示 Office 365 的 Defender 可掃描並移除所有電子郵件中的檔案。 整個 Microsoft 365 安全套件會封鎖檔案。
- **受到損害的裝置、使用者身分識別及信箱的自我修復** -Microsoft 365 DEFENDER 使用 AI 功能的自動動作和行動裝置，將受影響的資產修正回安全狀態。 Microsoft 365 Defender 利用套件產品的自動修正功能，確保與事件相關的所有受影響資產都會在可能的情況下自動修正。
- **跨產品威脅搜尋** -安全小組可以透過透過各種保護產品所收集的原始資料來建立自己的自訂查詢，利用其獨特的組織知識來尋找損害的跡象。 Microsoft 365 Defender 提供以查詢為基礎的存取權，可對30天的歷史原始信號進行存取，並在端點和 Microsoft Defender for Office 365 資料中提供警示資料。 


## <a name="get-started"></a>開始使用
若要在 Microsoft 365 security center 中啟用服務，必須符合 microsoft 365 Defender 授權需求，才能在 [security.microsoft.com](https://security.microsoft.com)上啟用服務。 如需詳細資訊，請參閱：
- [授權需求](prerequisites.md#licensing-requirements)
- [開啟 Microsoft 365 Defender](mtp-enable.md)
