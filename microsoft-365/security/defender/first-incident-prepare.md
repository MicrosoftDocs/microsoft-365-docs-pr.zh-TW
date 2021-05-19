---
title: 為第一個事件準備安全性狀況
description: 針對 Microsoft 365 Defender 中的第一個事件，設定 Microsoft 365 租使用者的安全性狀況。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4fc124bf8787d5880d78a4f5208bd66329da07a0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539032"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>為第一個事件準備安全性狀況

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

為事件處理做好準備時，應從不同類型的安全性事件中，設定組織網路的足夠保護。 若要降低安全性事件的風險，國家標準和技術協會 (NIST) 建議多種安全性作法，包括風險評估、強化主機安全性、安全地設定網路，以及防止惡意程式碼。 

Microsoft 365Defender 可協助您解決事件防護的幾個層面： 

- 實施 [零信任](https://docs.microsoft.com/security/zero-trust/) 架構
- 使用[Microsoft 安全分數](microsoft-secure-score.md)指派分數來判斷您的安全性狀況
- 透過[威脅和弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)中的漏洞評估來防止威脅
- 瞭解最新的安全性威脅，以做好準備

## <a name="step-1-implement-zero-trust"></a>步驟 1. 實現零信任

「[零信任](https://docs.microsoft.com/security/zero-trust/)」是整合的安全性理念和端對端策略，可考慮任何現代環境的複雜性質，包括行動工作力和使用者、裝置、應用程式及資料（可能位於何處）。 透過提供單一的玻璃窗格，以一致的方式管理所有的偵測，Microsoft 365 Defender 可讓安全性作業小組輕鬆地執行零信任的[指導原則](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust)。 

Microsoft 365 的元件會顯示已執行之規則的破壞，該規則會將 Microsoft Defender for Endpoint (MDE) 或其他行動安全性廠商整合為資訊來源，以針對裝置合規性原則和裝置型條件式存取原則的資訊來源，以建立零信任的條件存取原則。 

裝置風險會直接影響該裝置的使用者可存取的資源。 根據特定準則，「拒絕存取資源」是零信任和 Microsoft 365 Defender 的主要主題，提供判斷信任層級準則所需的資訊。 例如，Microsoft 365 Defender 可透過威脅和弱點管理頁面提供裝置的軟體版本層級，而條件式存取原則會限制具有過時或易受攻擊版本的裝置。

「自動化」是實施及維護零信任環境的重要部分，同時也減少了可能會造成事件回應 (紅外) 事件的警示數目。 Microsoft 365 Defender 的元件可以是自動化的，例如，[修正動作](m365d-autoir.md) (稱為 Microsoft 365 安全性中心) 的事件調查、通知動作，甚至是在[ServiceNow](https://microsoft.service-now.com/sp/)中建立支援票證。

## <a name="step-2-determine-your-organizations-security-posture"></a>步驟 2. 決定組織的安全性狀況

接下來，組織可以在 Microsoft 365 Defender 中使用[Microsoft 安全評分](microsoft-secure-score.md)，以判斷您目前的安全性狀況，並考慮改進的建議。 分數越高，組織採取的安全性建議和改善動作就越好。 安全分數建議可跨不同的產品進行，並可讓組織提升其分數甚至更高。 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft security center 中 Microsoft Secure 得分的範例":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>步驟 3. 評估貴組織的弱點洩密

防止事件可以協助簡化安全性作業，以著重于不斷進行重要及重要的安全性事件。 軟體弱點通常是攻擊的 preventable 進入點，可導致資料竊取、資料遺失或商務運作中斷。 如果不進行任何攻擊，安全性作業必須盡力達成並維護組織中可接受的 [漏洞公開](../defender-endpoint/tvm-exposure-score.md) 等級。

若要檢查您的軟體修補進度，請造訪您可以從 Microsoft 365 defender 透過 [**其他資源**] 索引標籤存取的 Endpoint for Endpoint 中的 [威脅和弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)頁面。

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft security center 中威脅和弱點頁面的範例"::: 
 
## <a name="4-understand-emerging-threats"></a>4. 瞭解新興威脅

在 Microsoft 365 的安全性中心使用[威脅分析](threat-analytics.md)，以維持目前安全性威脅環境的最新狀態。 專家 Microsoft 安全性調查程式會建立報告，以詳細描述最新的網路威脅，讓您瞭解它們對 Microsoft 365 訂閱、裝置和使用者有何影響。 這些報告可以包含：

- 作用中的威脅演員及其活動
- 常見和新的攻擊技術
- 嚴重弱點
- 常見的攻擊面
- 流行惡意程式碼

「威脅分析」也會查看您的設定和警示，以判斷您所在的風險以及是否有適用于報告的活動警示。

您可以執行新興威脅的建議，以加強安全性狀況，並將攻擊面降至最低。

在排程中的時間，定期檢查 Microsoft 365 安全性中心的 [[威脅分析](threat-analytics.md)] 區段。

## <a name="next-step"></a>下一步

[![步驟1：瞭解如何會審和分析事件](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

瞭解如何 [會審和分析事件](first-incident-analyze.md)。

## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
