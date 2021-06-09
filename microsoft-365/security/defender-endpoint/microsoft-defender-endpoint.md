---
title: 適用於端點的 Microsoft Defender
description: Microsoft Defender for Endpoint 是企業端點安全性平臺，可協助防禦高級持續性威脅。
keywords: microsoft defender for endpoint 簡介，microsoft defender for endpoint，cybersecurity，advanced persistent 威脅，企業安全性，機器行為感應器，cloud security，analytics，威脅情報，攻擊面降低，下一代保護，自動化調查和修正，Microsoft 威脅專家，安全分數，高級搜尋，Microsoft 365 Defender，網路威脅搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3bab9d0248a2ed8e83807f3c38215e653cba26eb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843551"
---
# <a name="microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> 如需 Windows 10 企業版 Edition 功能和功能的詳細資訊，請參閱[Windows 10 企業版 Edition](https://www.microsoft.com/WindowsForBusiness/buy)。

Microsoft Defender for Endpoint 是一種企業端點安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint 使用 Windows 10 和 Microsoft 強健的雲端服務內建的下列技術組合：

-   **端點行為感應** 器：內嵌于 Windows 10 中，這些感應器會從作業系統收集並處理行為信號，並將此感應器資料傳送至 Microsoft Defender for Endpoint 的私人、隔離的雲端實例。


-   **雲端安全性分析**：利用大量資料、裝置教學和獨特的 Microsoft 光纖在 Windows 生態環境中，企業雲端產品 (（如 Office 365) 及線上資產）都會轉譯成深入、偵測和建議的高級威脅回應。

-   **威脅情報**：由 Microsoft hunters、安全性小組所產生，並由合作夥伴提供的威脅情報擴充，威脅情報可讓 Defender for Endpoint 識別攻擊者工具、技術和程式，並在收集的感應器資料中看到警報時產生警示。

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>威脅 & 弱點管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻擊面減少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>下一代保護</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>端點偵測和回應</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>自動化調查和修正</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 威脅專家</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>集中式設定和管理、APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365後衛</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - 深入瞭解 Defender for Endpoint 中的最新增強功能： [Microsoft defender For endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)中的新功能。
> - Microsoft Defender for Endpoint 在最近的 MITRE 評估中示範業界一流的光學器件和偵測功能。 Read： [來自 MITRE ATT 的 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

<a name="tvm"></a>

**[威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)**<br>
這項內建的功能使用遊戲變更風險的方法來探索、優先順序和修正端點漏洞及錯誤配置。 

<a name="asr"></a>

**[攻擊面縮減](overview-attack-surface-reduction.md)**<br>
攻擊面降減功能集可提供堆疊中的第一項防護。 透過確定設定設定正確，並套用利用緩解技術，這些功能會讓攻擊和利用。 這組功能也包含 [網路保護](network-protection.md) 和 [web 保護](web-protection-overview.md)，可控制對惡意 IP 位址、網域和 URLs 的存取。 

<a name="ngp"></a>

**[新一代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
若要進一步鞏固網路的安全性周邊，Microsoft Defender for Endpoint 會使用下一代保護，以捕捉所有類型的新威脅。

<a name="edr"></a>

**[端點偵測及回應](overview-endpoint-detection-response.md)**<br>
端點偵測和回應功能會就地實施，以偵測、調查和回應可能使其超過前兩個安全性支柱的高級威脅。 「[高級搜尋](advanced-hunting-overview.md)」提供查詢型威脅搜尋工具，可讓您主動發現違規情況並建立自訂偵測。

<a name="ai"></a>

**[自動化調查和修正](automated-investigations.md)**<br>
為了能夠快速回應高級攻擊，Microsoft Defender for Endpoint 提供了自動調查和修正功能，可協助您在規模的情況下以分鐘為單位減少提醒數量。 

<a name="ss"></a>

**[裝置用 Microsoft 安全分數](tvm-microsoft-secure-score-devices.md)**<br>

用於裝置的 Defender 包括 Microsoft 安全分數，可協助您動態評估商業網路的安全性狀態、找出未受保護的系統，並採取建議的動作，以改善組織的整體安全性。

<a name="mte"></a>

**[Microsoft 威脅專家](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint new managed 威脅搜尋服務提供主動的搜尋、優先順序及其他內容與深入深入瞭解，可進一步讓安全性運作中心 (SOCs) 能夠快速且正確地識別及回應威脅。

>[!IMPORTANT]
>Defender for Endpoint 客戶必須套用 Microsoft 威脅專家受管理的威脅搜尋服務，以取得主動目標的攻擊通知，並與專家合作。 按需分配的專家是附加元件服務。 當您接受 Microsoft 威脅專家受管理的威脅搜尋服務後，就會包含目標攻擊通知。<p>
><p>若尚未註冊，且想要體驗其優點，請移至<b>設定</b>> <b>一般</b>> <b>高級功能</b> > <b>Microsoft 威脅專家</b>套用。 一旦接受，您就會獲得目標攻擊通知的優點，並在需要時啟動90天的專家試用。 請與您的 Microsoft 代表聯繫，以取得對需求訂閱的完整專家。

<a name="apis"></a>

**[集中式設定和管理、APIs](management-apis.md)**<br>
將 Microsoft Defender for 端點整合到現有的工作流程中。

<a name="mtp"></a>

**[與 Microsoft 解決方案整合](threat-protection-integration.md)** <br>
Defender for Endpoint 直接與各種 Microsoft 解決方案整合，包括：
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft 雲端應用程式安全性
- 適用於身分識別的 Microsoft Defender
- Microsoft Defender Office
- 商務用 Skype

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
使用 Microsoft 365 defender、defender for Endpoint 及各種 Microsoft security 解決方案，可在內部整合的所有端點、身分識別、電子郵件和應用程式，形成共同作業，以偵測、預防、調查和自動回應複雜的攻擊。


## <a name="related-topic"></a>相關主題
[Microsoft Defender for Endpoint 可協助偵測複雜威脅](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
