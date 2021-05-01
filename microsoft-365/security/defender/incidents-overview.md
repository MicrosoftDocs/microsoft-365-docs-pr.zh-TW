---
title: Microsoft 365 Defender 中的事件
description: 調查 Microsoft 365 安全性中心內的裝置、使用者和信箱所看到的事件。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
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
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114279"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 中的事件是組成攻擊之故事的相關警示和相關資料的集合。 

Microsoft 365 服務和應用程式會在偵測到可疑或惡意事件或活動時建立警示。 個別警示可提供關於已完成或進行中攻擊的重要線索。 不過，攻擊一般會針對不同類型的實體（例如裝置、使用者和信箱）採用各種技術。 其結果是針對您租使用者中的多個實體的多個警示。 

因為 piecing 個別警示共同取得攻擊的方式可能會是挑戰性和費時，所以 Microsoft 365 Defender 會自動將警示及其相關資訊匯總到事件中。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何將實體中的事件與事件產生關聯":::

請在 Microsoft 365 Defender (4 分鐘) 中觀看事件的這一小段簡介。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

將相關警示分組到事件中，可讓您全面瞭解攻擊。 例如，您可以看到：

- 攻擊的開始位置。
- 使用的戰術。
- 攻擊進入您租使用者的距離。
- 攻擊的範圍，例如影響的裝置、使用者和信箱數目。 
- 所有與攻擊相關聯的資料。

若[啟用](m365d-enable.md)，Microsoft 365 Defender 可以透過自動化和人工智慧來自動調查和解決提醒。 您也可以執行其他修復步驟，以解決攻擊。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 安全性中心的事件及警示

您可以在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 security center 中的 [事件] 頁面":::

選取 [事件名稱] 會顯示事件摘要，並可讓您存取具有其他資訊的索引標籤。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 security center 中的事件摘要頁面範例":::

事件的其他索引標籤如下：

- 警示 

  與該事件相關的所有提醒，以及其資訊。

- 裝置

  已識別為屬於事件一部分或與其相關的所有裝置。

- 使用者

  已識別為屬於該事件或與其相關的所有使用者。

- 信箱

  已識別為屬於事件一部分或與其相關的所有信箱。

- 調查

  事件中的警示所觸發的所有自動調查。

- 證據與回應

  事件中警示中所有支援的事件及可疑的實體。

以下是事件與其資料之間的關係，以及 Microsoft 365 security center 中事件的索引標籤。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="在 Microsoft 365 安全中心的事件索引標籤上，事件及其資料的關聯性":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender 的事件回應工作流程範例

以下是以「Microsoft 365 安全性中心」回應 Microsoft 365 中的事件的範例工作流程。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 的事件回應工作流程範例":::

在事件佇列中，針對分析和解決方式，識別最高優先順序的事件，讓他們可以進行回應。 這是下列專案的組合：

- 透過篩選和排序事件佇列來判斷最高優先順序事件的[會審](incident-queue.md)。
- 透過修改其標題、將其指派給分析員，以及新增標記和批註來[管理](manage-incidents.md)事件。

1. 針對每個事件，開始 [攻擊和警示分析](investigate-incidents.md)：
 
   a. 請查看事件摘要，瞭解其範圍和嚴重性，以及會影響哪些實體 ([ **摘要** ] 索引標籤) 中。

   b. 開始分析警示，以瞭解其來源、範圍和嚴重性 (**警示** ] 索引標籤) 。

   c. 如有需要，請在 [ **裝置**]、[ **使用者**] 和 [ **信箱** ] 索引標籤)  (，收集受影響裝置、使用者和信箱的資訊。

   d. 請參閱「**調查**」索引標籤) 中 Microsoft 365 Defender 如何自動解決某些警示 (。
   
   e. 如有需要，請使用事件資料組中的資訊，以取得 (**證據與回應** ] 索引標籤) 的詳細資訊。

2. 在分析之後或過程中執行包容，以減少攻擊和 eradication 安全性威脅的任何其他影響。

3. 盡可能將租使用者資源還原為事件之前所用的狀態，從攻擊復原。

4. [解決](manage-incidents.md#resolve-incident) 事件，並在進行事件後學習需要一些時間，以進行下列作業：

   - 瞭解攻擊的類型及其影響。
   - 調查 [威脅分析](threat-analytics.md) 中的攻擊，以及安全性攻擊趨勢的安全性社區。
   - 召回您用來解決事件的工作流程，並視需要更新您的標準工作流程、流程、原則及行動行動。
   - 決定是否需要在安全性設定中進行變更，並加以實施。

如果您是新的安全性分析，請參閱 [回應第一個事件的簡介](incidents-overview.md) 以取得其他資訊，並逐步執行範例事件。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender 的安全性操作範例

以下是 Microsoft 365 Defender 的安全性運作範例。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender 的安全性操作範例":::

每個任務可以包含：

- [管理](manage-incidents.md) 事件
- 檢查 [自動調查和回應 (AIR) ](m365d-action-center.md) 動作
- 查看最新的 [威脅分析](threat-analytics.md)
- [回應](investigate-incidents.md) 事件

每月任務可以包含：

- 檢查 [空中設定](m365d-configure-auto-investigation-response.md)
- 檢查 [安全分數](microsoft-secure-score-improvement-actions.md) 和 [威脅 & 弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 向您的 IT 安全性管理階層報告

每個季度的工作可以包含向首席資訊安全性監察官 (CISO) 中的安全性結果的報告及簡報。

每年的工作可以包含執行重大事件或破壞練習，以測試您的員工、系統和程式。 

您可以使用每日、每月、每季及每年的工作來更新或修改程式、原則及安全性設定。

## <a name="next-steps"></a>後續步驟

[ **事件** ] 頁面的 [事件] 佇列會列出最近的事件。 在這裡，您可以：

- 根據嚴重性及其他因素，查看應 [優先](incident-queue.md) 考慮哪些事件。 
- [管理事件](manage-incidents.md)，包括重新命名、指派、分類，以及新增事件管理工作流程的標記和批註。
- 執行事件的 [分析](investigate-incidents.md) 。
