---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中篩選事件佇列中的事件
keywords: 事件, 佇列, 概覽, 裝置, 身分識別, 使用者, 信箱, 電子郵件, 事件
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
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500997"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>設定 Microsoft 365 Defender 中的事件優先順序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



Microsoft 365 Defender 會套用關聯性分析，並將不同產品的所有相關警示和調查彙集到一個事件中。 Microsoft 365 defender 也會觸發唯一的警示，可在 Microsoft 365 Defender 跨整個房地產及產品套件的端對端可視性時，識別出惡意的活動。 此視圖讓安全性分析分析員成為廣泛的攻擊案例，可協助他們更好地瞭解及處理整個組織中的複雜威脅。


**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。 可協助您設定事件優先順序及制定明智的網路安全回應決策。


![事件佇列的影像](../../media/incidents-queue.png) 

根據預設，Microsoft 365 security center 中的佇列會顯示過去30天內看到的事件。 最近的事件是在清單頂端，您可以先查看此專案。

事件佇列公開可自訂的欄，可讓您深入瞭解事件或所包含之實體的不同特性。 這可協助您作出決定要處理之事件優先順序的相關決定。

如需更深入的洞察力，自動事件命名功能會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別），產生事件名稱。 這可讓您快速瞭解事件的範圍。

例如：多 *個來源所報告之多個端點上的多階段事件。*

> [!NOTE]
> 在自動事件命名的首展之前，發生的事件，其名稱不會變更。

事件佇列也會公開多種篩選選項，當套用此選項時，您可以對環境中的所有現有事件執行大量的掃描，也可以決定將重點放在特定案例或威脅上。 在事件佇列套用篩選可協助判斷哪個事件需要立即處理。 

## <a name="available-filters"></a>可用的篩選

### <a name="assigned-to"></a>指派給
您可以選擇顯示指派給您或「自動化」所處理的警示。

### <a name="categories"></a>類別
選擇 [類別]，以著重顯示特定的戰術、技術或攻擊元件。 

### <a name="classification"></a>分類
根據相關警示的設定分類來篩選事件。 其值包括 true 警示、false 警示或未設定。

### <a name="data-sensitivity"></a>資料敏感度
某些攻擊鎖定外洩機密敏感性資料或重要資料。 透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。

>[!NOTE]
>只有在開啟 Microsoft 資訊保護時才適用。

### <a name="device-group"></a>裝置群組
依定義的裝置群組篩選。

### <a name="investigation-state"></a>調查狀態
依自動調查的狀態來篩選事件。 

### <a name="multiple-categories"></a>多個類別 
您可以選擇只查看已對應至多個類別的事件，進而可能造成更大的損毀。 

### <a name="multiple-service-sources"></a>多個服務來源 
篩選，只會查看包含不同來源之警示的事件， (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。

### <a name="os-platform"></a>作業系統平臺
依作業系統限制事件佇列查看。

### <a name="service-sources"></a>服務來源
透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。 

### <a name="severity"></a>嚴重性
事件的嚴重性是指它可對資產造成的影響。 嚴重性越高，影響就越大，而且通常需要最直接的注意。 

### <a name="status"></a>狀態
您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。




## <a name="next-steps"></a>後續步驟
決定優先順序最高的事件後，便可繼續進行事件的調查工作。
- [調查事件](investigate-incidents.md)


## <a name="see-also"></a>另請參閱
- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
