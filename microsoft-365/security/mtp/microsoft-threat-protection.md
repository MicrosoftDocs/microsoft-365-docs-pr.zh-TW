---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一個協調的威脅防護解決方案，專門用來保護裝置、身分識別、資料與應用程式
keywords: Microsoft 威脅防護、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930567"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 Defender 是一套整合的預先和入侵後企業防護套件，可原生協調端點、身分識別、電子郵件和應用程式之間的偵測、防止、調查及回應，以提供整合式防護，防範複雜的攻擊。

使用整合式 Microsoft 365 Defender 解決方案，安全性專業人員可以整合每項產品收到的威脅訊號，並判斷威脅的完整範圍和影響;進入環境後的影響，以及目前對組織的影響。 Microsoft 365 Defender 會採取自動動作來防止或停止受攻擊和自我攻擊的信箱、端點和使用者身分識別。  


<center><h2>Microsoft 365 Defender 服務</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>端點的 Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365 的 Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender 的身分識別</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App 安全性</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 互動式指南

在這個互動式指南中，您將瞭解如何使用 Microsoft 365 Defender 保護貴組織。 您將瞭解 Microsoft 365 Defender 如何協助偵測安全性風險、調查組織攻擊，並自動防止有害活動。

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender 套件保護： 
- **具有 Microsoft Defender for Endpoint** 的端點 - Microsoft Defender for Endpoint 是一個針對預防保護、外泄後偵測、自動化調查及回應的一個統一端點平臺。 
- **使用 Microsoft Defender for Office 365** 執行電子郵件和共同合作 - Office 365 的 Defender 可保護貴組織免受電子郵件訊息、URL 連結和 (和共同) 所造成的惡意威脅。 
- 身分識別與 **Azure AD 身分** 保護之 Microsoft Defender 的身分識別 - Microsoft Defender for Identity 會使用 Active Directory 訊號來識別、偵測和調查進一步威脅、身分識別已盜用，以及針對貴組織所導向的惡意 Insider 動作。 
- **具有 Microsoft Cloud App** 安全性的應用程式 - Microsoft Cloud App 安全性是一種全方位的跨 SaaS 解決方案，為雲端應用程式提供深入可見度、強大的資料控制，以及增強的威脅防護。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 的唯一跨產品層強化了個別套件元件，
- 透過訊號分享和自動動作協助防範攻擊，並協調整個套件的緊急回應
- 將警示、可疑事件和已影響資產的資料加入至'事件'，以旁白來自安全性小組之產品警示、行為及內容的完整攻擊案例
- 透過自動化修復，觸發因應受威脅資產自行入侵的自動化因應措施
- 讓安全小組能跨端點和 Office 資料執行詳細且有效的威脅搜尋

![事件概觀頁面的影像](../../media/overview-incident.png) <br>
跨產品事件 (概觀) 

![警示佇列的影像](../../media/incident-list.png)<br>
跨套件產品的所有相關警示會相互關聯成單一事件 (警示) 

![事件佇列的影像](../../media/advanced-hunting.png)<br>
在電子郵件和端點原始資料上方進行查詢搜尋


Microsoft 365 Defender 的跨產品功能包括： 
- **跨產品單** 一窗格的玻璃 -集中式查看所有資訊，用於偵測、影響資產、採取自動化動作，以及單一佇列的相關證據，以及資料 [security.microsoft.com。](https://security.microsoft.com) 
- **結合事件** 佇列 - 確保完整攻擊範圍、受影響資產和自動化補救動作會分組並及時出現，協助安全性專業人員專注于關鍵。 
- **威脅的** 自動回應 - Microsoft 365 Defender 產品之間會即時分享重大威脅資訊，協助停止攻擊的進度。 例如，如果偵測到由 Microsoft Defender for Endpoint 保護的端點上偵測到惡意檔案，就會指示 Office 365 的 Defender 掃描並移除所有電子郵件訊息中的檔案。 整個 Microsoft 365 安全性套件一看到就會封鎖該檔案。
- 針對遭到入侵的裝置、使用者身分識別及信箱自行修復 **-** Microsoft 365 Defender 會使用 AI 支援的自動動作和劇本，將受到影響的資產修復回安全狀態。 Microsoft 365 Defender 運用套件產品的自動修復功能，以確保與事件相關的所有影響資產都會在可能的情況下自動修復。
- **搜尋跨產品** 威脅 - 安全性團隊可以運用其獨特的組織知識，針對各種保護產品收集的原始資料建立自訂查詢，以尋找入侵符號。 Microsoft 365 Defender 提供查詢型存取，可存取 30 天歷史原始訊號，並跨端點和 Microsoft Defender 警示 Office 365 資料的資料。 


## <a name="get-started"></a>快速入門
您必須先符合 Microsoft 365 Defender 授權需求，才能在 Microsoft 365 資訊安全中心啟用[security.microsoft.com。](https://security.microsoft.com) 詳細資訊請參閱：
- [授權需求](prerequisites.md#licensing-requirements)
- [開啟 Microsoft 365 Defender](mtp-enable.md)
