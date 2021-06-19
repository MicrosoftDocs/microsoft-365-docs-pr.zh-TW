---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中篩選事件佇列中的事件
keywords: 事件，佇列，概述，裝置，身分識別，使用者，信箱，電子郵件，事件，分析，回應
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
ms.openlocfilehash: 1240fbb8fb24b7231733db25e9a1859b2a84fd41
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022728"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>設定 Microsoft 365 Defender 中的事件優先順序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Microsoft 365 Defender 會將關聯性分析和匯總相關的警示和自動調查套用到事件中。 Microsoft 365 Defender 也會針對 Microsoft 365 Defender 跨整個產品套件的端對端 visibility，，針對只識別為惡意的活動，觸發唯一警示。 這種觀點可讓您的安全性分析更廣泛的攻擊案例，以協助他們更好地瞭解及處理整個組織中的複雜威脅。

[ **事件] 佇列** 顯示跨裝置、使用者和信箱建立的事件集合。 可協助您設定事件優先順序及制定明智的網路安全回應決策。 

您可以從事件中取得事件佇列 **& 警示 >** Microsoft 365 Defender 入口網站 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的事件。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

**最新的 [事件及警示**] 區段會顯示過去24小時所收到的警示和事件數目圖表。

根據預設，Microsoft 365 Defender 入口網站中的事件佇列會顯示過去六個月所看到的事件。 最近的事件是在清單頂端，您可以先查看此專案。

事件佇列具有可自訂的欄 (選取 **[選擇欄** ]) ，可讓您深入瞭解事件或受影響的實體的不同特性。 這可協助您作出有關分析的事件優先順序決定。

如需更深入的洞察力，自動事件命名功能會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別），產生事件名稱。 這可讓您快速瞭解事件的範圍。

例如：多 *個來源所報告之多個端點上的多階段事件。*

> [!NOTE]
> 在自動事件命名的首展之前，發生的事件，其名稱不會變更。

事件佇列也會公開多種篩選選項，當套用此選項時，您可以對環境中的所有現有事件執行大量的掃描，也可以決定將重點放在特定案例或威脅上。 在事件佇列套用篩選可協助判斷哪個事件需要立即處理。 

## <a name="available-filters"></a>可用的篩選

您可以從預設的事件佇列中，選取 [ **篩選** ] 以查看篩選窗格，您可以從該窗格中查看篩選的事件集。 範例如下。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件佇列之篩選窗格的範例":::

此表列出可用的篩選器名稱。

| 篩選名稱 | 描述 |
|:-------|:-----|
| 指派給 | 您可以選擇顯示指派給您或「自動化」所處理的警示。 |
| 類別 | 選擇 [類別]，以著重顯示特定的戰術、技術或攻擊元件。 |
| 分類 | 根據相關警示的設定分類來篩選事件。 其值包括 true 警示、false 警示或未設定。 |
| 資料敏感度 | 某些攻擊鎖定外洩機密敏感性資料或重要資料。 透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。 <br><br> 只有在開啟 Microsoft 資訊保護時才適用。|
| 裝置群組 | 依定義的裝置群組篩選。 |
| 調查狀態 | 依自動調查的狀態來篩選事件。  |
| 多個類別 | 您可以選擇只查看已對應至多個類別的事件，進而可能造成更大的損毀。 |
| 多個服務來源  | 篩選，只會查看包含不同來源之警示的事件， (Microsoft defender for Endpoint，Microsoft Cloud App Security，microsoft defender for Identity，microsoft defender for Office 365) 。 |
| 作業系統平臺 | 依作業系統限制事件佇列查看。 |
| 服務來源 | 透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。 |
| 嚴重性 | 事件的嚴重性是指它可對資產造成的影響。 嚴重性越高，影響就越大，而且通常需要最直接的注意。 |
| 狀態 | 您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。 |
|||

## <a name="save-defined-filters-as-urls"></a>將定義的篩選儲存為 URLs

在 [事件] 佇列中設定有用的篩選後，您可以將瀏覽器索引標籤的 URL 做成書簽，或是將它儲存為網頁上的連結、Word 檔或您選擇的位置。 這可讓您點擊存取事件佇列的主要視圖，例如：

- 新的事件
- 高嚴重性事件
- 未指派的事件
- 高嚴重性、未指派的事件
- 指派給我的事件
- 指派給我和 Microsoft Defender for Endpoint 的事件
- 具有特定標記或標記的事件
- 具有特定威脅類別的事件
- 具有特定相關威脅的事件
- 具有特定參與者的事件

在您將有用的篩選視圖編譯並儲存為 URLs 之後，您可以使用它快速處理及設定佇列中的事件 [優先順序，以](manage-incidents.md) 進行後續分析。

## <a name="next-steps"></a>後續步驟

決定需要最高優先順序的事件後，請選取它，然後：

- [管理](manage-incidents.md) 事件的屬性，以供標記、指派、立即解決誤報和批註的事件。
- 開始進行 [調查](investigate-incidents.md)。

## <a name="see-also"></a>另請參閱
- [事件概觀](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [調查事件](investigate-incidents.md)
