---
title: 瞭解 Microsoft Defender for Endpoint 中的威脅智慧概念
description: 為您的組織建立自訂威脅警示，並瞭解 Microsoft Defender for Endpoint 中威脅情報的概念。
keywords: 威脅情報、警示定義、損等標記、ioc
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
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059303"
---
# <a name="understand-threat-intelligence-concepts"></a>了解威脅情報概念

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Advanced cybersecurity 攻擊是由多個複雜的惡意事件、屬性和內容資訊所組成。 識別和決定哪些活動符合可疑的工作可能是一項挑戰性的工作。 您對您的行業所知之已知屬性和反常活動的知識，都是知道何時將觀測行為視為可疑的情況的基礎。

透過 Microsoft Defender for Endpoint，您可以建立自訂威脅警示，可協助您追蹤組織中可能的攻擊活動。 您可以標示可疑的事件，將線索放在一起，並可能停止攻擊鏈。 這些自訂威脅警示只會出現在您的組織中，並會標示您設定它追蹤的事件。

在建立自訂威脅警示之前，請務必瞭解警示定義及威脅 (IOCs) 及其之間的關聯性的概念。

## <a name="alert-definitions"></a>警示定義
警示定義是可共同用於識別可能的 cybersecurity 攻擊的早期線索的內容屬性。 這些指示器通常是攻擊者採取的動作和動作組合，以順利達成攻擊的目標。 監視這些屬性的組合對於在攻擊者的目標達到 vantage 點，並可能影響事件鏈之前很重要。

## <a name="indicators-of-compromise-ioc"></a> (IOC 的折衷標記) 
IOCs 是個別已知的惡意事件，表示網路或裝置已遭破壞。 與警示定義不同的是，這些指示器會被視為遭到破壞的證據。 在攻擊已執行並已到達目標時（例如 exfiltration），通常會出現這種情況。 在取證調查期間，追蹤 IOCs 也很重要。 雖然它可能無法提供干預攻擊鏈的能力，但收集這些指示器可以在建立更好的防禦，以進行未來的潛在攻擊。

## <a name="relationship-between-alert-definitions-and-iocs"></a>警示定義與 IOCs 之間的關係
在 Microsoft Defender for Endpoint 中，警示定義是 IOCs 的容器，它會定義警示，包括在特定 IOC 相符時引發的中繼資料。 各種中繼資料都是以警示定義的一部分提供。 與其他選項一起提供的中繼資料，例如攻擊、嚴重性和描述的警示定義名稱。

每個 IOC 會根據其類型和值來定義具體偵測邏輯，以及其動作，以判斷其的相符方式。 它會系結至特定的警示定義，以定義如何在 Microsoft Defender for Endpoint 主控台上顯示偵測通知。

以下是 IOC 的範例：
- 類型： Sha1
- 值：92cfceb39d57d914ed8b14d0e37643de0797ae56
- 動作：等於

IOCs 具有與警示定義的多對一關聯，讓警示定義可以有許多對應的 IOCs。

## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
[向 SIEM 工具提取偵測](configure-siem.md)| 深入瞭解提取偵測的不同方式。
[在 Microsoft Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)| 瞭解如何在入口網站的 [**設定**] 頁面中啟用 SIEM 整合功能，讓您可以使用及產生必要的資訊來設定支援的 SIEM 工具。
[設定 Splunk 以拉入 Microsoft Defender for Endpoint 偵測](configure-siem.md)| 瞭解如何安裝 REST API 模組化輸入應用程式和其他設定設定，以讓 Splunk 提取 Microsoft Defender for Endpoint 偵測。
[設定 HP ArcSight 以拉入 Microsoft Defender for Endpoint 偵測](configure-arcsight.md)| 瞭解如何安裝 HP ArcSight REST FlexConnector 套件，以及您需要設定 ArcSight 以提取 Microsoft Defender for Endpoint 偵測的檔案。
[Microsoft Defender for Endpoint 偵測欄位](api-portal-mapping.md) | 瞭解哪些資料欄位會公開成為警示 API 的一部分，以及它們如何對應 Microsoft Defender 資訊安全中心。
[使用 REST API 提取 Microsoft Defender for Endpoint 偵測](pull-alerts-using-rest-api.md) | 使用用戶端認證 OAuth 2.0 流程，從使用 REST API 的 Microsoft Defender for Endpoint 提取偵測。
[為 SIEM 工具整合問題疑難排解](troubleshoot-siem.md) | 解決使用 SIEM 整合功能時可能遇到的問題。



## <a name="related-topics"></a>相關主題
- [管理指示器](manage-indicators.md)
