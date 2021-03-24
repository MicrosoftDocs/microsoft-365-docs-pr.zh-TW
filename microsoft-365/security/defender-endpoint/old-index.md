---
title: 'Windows 10 (威脅防護) '
description: 適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。
keywords: 威脅防護、Microsoft Defender 高級威脅防護、攻擊面減少、下一代保護、端點偵測和回應、自動化調查和回應、microsoft 威脅專家、Microsoft 安全評分的裝置、高級搜尋、網路威脅搜尋、網頁威脅防護
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056844"
---
# <a name="threat-protection"></a>威脅防護
[適用於端點的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。 Defender for Endpoint 可保護端點免受網路威脅、偵測高級攻擊和資料違例、自動化安全性事件，以及改善安全性狀況。

> [!TIP]
> 讓您的使用者能夠輕鬆存取雲端服務和內部部署應用程式，並為所有裝置啟用新式管理功能。 如需詳細資訊，請參閱 [保護您的遠端員工](https://docs.microsoft.com/enterprise-mobility-security/remote-work/)。 

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>威脅 & 弱點管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>攻擊面減少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>下一代保護</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>端點偵測和回應</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>自動化調查和修正</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft 威脅專家</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>集中式設定和管理、APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)**<br>
這項內建的功能使用遊戲變更風險的方法來探索、優先順序和修正端點漏洞及錯誤配置。

- [威脅 & 弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [開始使用](tvm-prerequisites.md)
- [存取您的安全性狀況](tvm-dashboard-insights.md)
- [改善您的安全性狀況並降低風險](tvm-security-recommendation.md)
- [瞭解裝置上的漏洞](tvm-software-inventory.md)

<a name="asr"></a>

**[受攻擊面縮小](overview-attack-surface-reduction.md)**<br>
攻擊面降減功能集可提供堆疊中的第一項防護。 透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。

- [以硬體為基礎的隔離](overview-hardware-based-isolation.md)
- [應用程式控制](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [裝置控制項](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Exploit protection](exploit-protection.md)
- [網路保護](network-protection.md)， [web 保護](web-protection-overview.md)
- [受控資料夾存取權](controlled-folders.md)
- [網路防火牆](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [受攻擊面縮小規則](attack-surface-reduction.md)

<a name="ngp"></a>

**[下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
若要進一步鞏固網路的安全性周邊，Microsoft Defender for Endpoint 會使用下一代保護，以捕捉所有類型的新威脅。

- [行為監控](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [雲端型保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [機器學習](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL 保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [自動化沙箱服務](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[端點偵測及回應](overview-endpoint-detection-response.md)**<br>
端點偵測和回應功能可就地偵測、調查和回應入侵嘗試和主動違例。 使用高級搜尋時，您可以使用查詢型威脅搜尋工具，讓您主動發現違規並建立自訂偵測。

- [提醒](alerts-queue.md)
- [歷史端點資料](investigate-machines.md#timeline)
- [回應 orchestration](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [鑒證集合](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [威脅情報](threat-indicator-concepts.md)
- [Advanced 引爆及 analysis service](respond-file-alerts.md#deep-analysis)
- [進階搜捕](advanced-hunting-overview.md)
    - [自訂偵測](overview-custom-detections.md)

<a name="ai"></a>

**[自動化調查與補救措施](automated-investigations.md)**<br>
除了快速回應高級攻擊之外，Microsoft Defender for Endpoint 還提供自動調查和修正功能，可協助減少提醒數量，以分鐘為單位的規模。

- [自動化調查與補救措施](automated-investigations.md)
- [檢視自動調查的詳細資料和結果](auto-investigation-action-center.md)
- [查看和核准修正動作](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft 威脅專家](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint 的新受管理威脅搜尋服務提供主動的搜尋、優先順序及其他內容和洞察力。 Microsoft 威脅專家會進一步讓安全性運作中心 (SOCs) ，快速且準確地識別及回應威脅。

- [目標攻擊通知](microsoft-threat-experts.md)
- [專家隨選](microsoft-threat-experts.md)
- [設定您的 Microsoft 365 Defender managed 搜尋服務](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[集中式設定和管理、APIs](management-apis.md)**<br>
將 Microsoft Defender for 端點整合到現有的工作流程中。
- [上線](onboard-configure.md)
- [API 和 SIEM 整合](configure-siem.md)
- [公開 APIs](apis-intro.md)
- [角色型存取控制 (RBAC)](rbac.md)
- [報告和趨勢](threat-protection-reports.md)

<a name="integration"></a>
**[與 Microsoft 解決方案整合](threat-protection-integration.md)** <br>
 Microsoft Defender for Endpoint 會直接與各種 Microsoft 解決方案整合，包括：
- Intune
- 適用於 Office 365 的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender
- Azure Defender
- 商務用 Skype
- Microsoft 雲端應用程式安全性

<a name="mtp"></a>
**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 使用 Microsoft 365 Defender 時，Microsoft Defender for Endpoint 和各種 Microsoft 安全性解決方案組成的整合內送和後序性企業防護套件，可共同整合在端點、身分識別、電子郵件和應用程式中，以偵測、預防、調查和自動回應複雜的攻擊。
