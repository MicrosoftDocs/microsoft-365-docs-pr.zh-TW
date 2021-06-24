---
title: 調查 Microsoft 365 Defender 中的事件
description: 調查與裝置、使用者和信箱相關的事件。
keywords: 事件，事件，分析，回應，機器，裝置，使用者，身分識別，郵件，電子郵件，信箱，調查，圖形，證據
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105353"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

Microsoft 365 Defender 會將所有相關的警示、資產、調查和證據，全部從您的裝置、使用者和信箱匯總到事件中，讓您全面瞭解攻擊的整體廣度。

在事件內，您會分析影響網路的警示、瞭解其含義，以及對照證據來設計有效的修復計畫。

## <a name="initial-investigation"></a>初始調查

深入瞭解詳細資料之前，請先查看事件的屬性與摘要。

您可以從選取 [核取記號] 欄開始選取該事件。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="從核取記號欄中選取事件的範例":::

當您這麼做時，會開啟摘要窗格，其中會顯示事件的重要資訊（例如嚴重性），以及[MITRE ATT&CK &trade; ](https://attack.mitre.org/)類別的事件。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="事件摘要窗格的範例":::

您可以從這裡選取 [ **開啟 incident] 頁面**。 這會開啟此事件的主頁面，您可以在此找到更多摘要資訊和索引標籤，以取得提醒、裝置、使用者、調查和證據。

您也可以從事件佇列中選取事件名稱，以開啟事件的主版頁面。

## <a name="summary"></a>摘要

[ **摘要** ] 頁面可讓您查看有關事件的最重要注意事項。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 security center 中的事件摘要頁面範例":::

「攻擊類別」可讓您直觀和數值的方式，顯示攻擊如何對 kill 鏈進行的進展。 與其他 Microsoft 安全性產品一樣，Microsoft 365 Defender 會對應至[MITRE ATT&CK &trade; ](https://attack.mitre.org/) framework。

範圍區段會顯示屬於此事件中影響最大的資產清單。 如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。

提醒時程表會提供 sneak，以即時查看警示的發生順序，以及這些警示連結至此事件的原因。

和 last-「證據」區段會摘要說明事件中包含多少不同的專案以及其修復狀態，所以您可以立即識別您是否需要任何動作。

這項功能可讓您瞭解應注意的事件最重要特性，以協助您進行事件的初始診斷。

## <a name="alerts"></a>警示

您可以在 [ **警示** ] 索引標籤上，查看與該事件相關之警示的警示佇列及其他相關資訊，例如：

- 嚴重性。
- 警示中所涉及的實體。
-  (microsoft defender for Identity、microsoft defender for Endpoint、microsoft defender for Office 365) 的警示來源。
- 連結在一起的原因。

以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="事件提醒頁面的範例":::

依預設，提醒會以時間順序排列，以讓您瞭解事件隨時間的播放方式。 當您在事件內選取警示時，Microsoft 365 Defender 會顯示針對整體事件內容的警示資訊。 

您可以看到警示的事件，哪些其他觸發的警示會導致目前的警示，以及攻擊中所涉及的所有受影響實體和活動，包括檔案、使用者和信箱。

以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="事件中警示詳細資料頁面的範例":::

此事件提醒頁面包含下列區段：

- 警示案例，包含發生狀況的摘要
- 相關的事件及警示
- 摘要詳細資料

瞭解如何在 [調查提醒](investigate-alerts.md)中使用警示佇列及警示頁面。

## <a name="devices"></a>裝置

[ **裝置** ] 索引標籤會列出與該事件相關的所有裝置。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="事件的裝置頁面範例":::

您可以選取裝置的核取記號，以查看裝置、目錄資料、作用中警示及已登入使用者的詳細資料。 選取裝置的名稱，以查看 Microsoft Defender for 端點裝置庫存中的裝置詳細資料。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender 端點的裝置頁面範例":::

在 [裝置] 頁面上，您可以收集裝置的其他相關資訊，例如其所有警示、時程表及安全性建議。 例如，在 [ **時程表** ] 索引標籤中，您可以在機器時程表中向內移動，並以時間順序查看機器上所觀察到的所有事件和行為，並與所引發的警示交錯。

> [!TIP]
> 您可以在裝置頁面上執行手動掃描。 在 [Microsoft 365 安全性中心] 中，選擇 [**端點] > 裝置庫存**]。 選取具有警示的裝置，然後執行防病毒掃描。 在 [ **裝置庫存** ] 頁面上追蹤並顯示的動作（例如防病毒掃描）。 若要深入瞭解，請參閱[執行 Microsoft Defender 防毒軟體掃描裝置](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。

## <a name="users"></a>使用者

[ **使用者** ] 索引標籤會列出已識別為屬於該事件或與其相關之所有使用者。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

您可以為使用者選取核取記號，以查看使用者帳戶威脅、公開和連絡人資訊的詳細資料。 選取使用者名稱以查看其他使用者帳戶詳細資料。

瞭解如何在 [調查使用者](investigate-users.md)中查看其他使用者資訊及管理事件的使用者。


## <a name="mailboxes"></a>信箱

[ **信箱** ] 索引標籤會列出已識別為屬於該事件或與其相關的所有信箱。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="事件的信箱頁面範例":::

您可以選取信箱的核取記號，以查看作用中的警示清單。 選取信箱名稱，以查看 Microsoft Defender for Office 365 的 Explorer 頁面上的其他信箱詳細資料。

## <a name="investigations"></a>調查

[ **調查** ] 索引標籤會列出此事件中的警示所觸發的所有 [自動調查](m365d-autoir.md) 。 調查會執行修正動作，或等候分析員的動作核准，視您如何設定自動調查，以在 Microsoft Defender for Endpoint 和 Defender for Office 365 中執行。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="事件的調查頁面範例":::

選取調查以流覽至其詳細資料頁面，以取得調查和修正狀態的完整資訊。 如果有任何動作出于調查的一部分而待核准，它們就會出現在 [ **擱置的動作記錄** ] 索引標籤中。採取動作做為事件修復的一部分。

此外，還會顯示一個 **調查圖表** 索引標籤：

- 組織中受影響資產的警示連接。
- 哪些實體與哪些警示相關，以及如何成為攻擊本文的一部分。
- 事件的警示。

調查圖表可協助您透過連線屬於攻擊一部分相關資產（如使用者、裝置和信箱）的不同可疑實體，快速瞭解攻擊的完整範圍。 

如需詳細資訊，請參閱[Microsoft 365 Defender 中的自動化調查和回應](m365d-autoir.md)。

## <a name="evidence-and-response"></a>證據與回應

[ **證據與回應** ] 索引標籤會顯示事件中的警示中所有支援的事件及可疑的實體。 以下為範例。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="事件的證據與回應頁面範例":::

Microsoft 365 Defender 會自動調查警示中的所有事件支援事件和可疑實體，以提供重要電子郵件、檔案、程式、服務、IP 位址等相關資訊。 這可協助您快速偵測並封鎖事件中的潛在威脅。

每個分析的實體都會以判定為序 (惡意、可疑、清除) 和修正狀態。 這可協助您瞭解整個事件的修復狀態，以及可以採取的後續步驟。

## <a name="next-steps"></a>後續步驟

視需要：

- [調查事件的警示](investigate-alerts.md)
- [調查事件的使用者](investigate-users.md)

## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)

