---
title: 在 Microsoft 365 Defender 中排列事件的優先順序
description: 瞭解如何在 Microsoft 365 Defender 中篩選事件佇列中的事件
keywords: 事件, 佇列, 概覽, 裝置, 身分識別, 使用者, 信箱, 電子郵件, 事件
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929291"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中排列事件的優先順序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



Microsoft 365 Defender 會進行相關分析，並匯總不同產品的所有相關警示與調查到單一事件。 Microsoft 365 Defender 也會觸發唯一警示，指出只有 Microsoft 365 Defender 具有跨整個財產和產品套件的端對端可見度，才能識別活動為惡意。 此視圖可賦予您的安全性作業分析師更大的攻擊案例，協助他們進一理解並處理整個組織的複雜威脅。


**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。 可協助您設定事件優先順序及制定明智的網路安全回應決策。


![事件佇列的影像](../../media/incidents-queue.png) 

根據預設，Microsoft 365 資訊安全中心的佇列會顯示過去 30 天內發生的事件。 最新的事件位於清單頂端，因此您可以先看到它。

事件佇列公開可自訂的欄，提供您事件或包含實體的不同特性的可見度。 這可協助針對要處理之事件的優先順序，做出明智的決策。

為了一目了然，自動事件命名功能會依據警示屬性產生事件名稱，例如受影響的端點數目、受影響的使用者、偵測來源或類別。 這可讓您快速瞭解事件的範圍。

例如： *多個來源報告之多個端點上的多階段事件。*

> [!NOTE]
> 在推出自動事件命名之前存在的事件不會變更其名稱。

事件佇列也會公開多個篩選選項，當篩選選項適用時，您可以對環境中所有現有的事件執行廣泛的整理，或決定專注于特定案例或威脅。 在事件佇列套用篩選可協助判斷哪個事件需要立即處理。 

## <a name="available-filters"></a>可用的篩選

### <a name="assigned-to"></a>指派給
您可以選擇顯示指派給您的提醒或由自動化處理者。

### <a name="categories"></a>類別
選擇類別以專注于特定的策略、技巧或攻擊元件。 

### <a name="classification"></a>分類
根據相關警示的設定分類來篩選事件。 這些值包括真正的警示、誤報或未設定。

### <a name="data-sensitivity"></a>資料敏感度
某些攻擊鎖定外洩機密敏感性資料或重要資料。 透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。

>[!NOTE]
>只有在開啟 Microsoft 資訊保護時才適用。

### <a name="device-group"></a>裝置群組
根據定義的裝置群組篩選。

### <a name="investigation-state"></a>調查狀態
根據自動化調查的狀態來篩選事件。 

### <a name="multiple-categories"></a>多個類別 
您可以選擇只查看已對應到多個類別的事件，因此可能導致更多損害。 

### <a name="multiple-service-sources"></a>多個服務來源 
篩選以只查看含有不同來源警示的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。

### <a name="os-platform"></a>作業系統平臺
根據作業系統限制事件佇列視圖。

### <a name="service-sources"></a>服務來源
透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。 

### <a name="severity"></a>嚴重性
事件的嚴重性取決於事件會對您的資產造成的影響。 嚴重性越高，影響越大，通常需要最即時的注意。 

### <a name="status"></a>狀態
您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。




## <a name="next-steps"></a>後續步驟
決定優先順序最高的事件後，便可繼續進行事件的調查工作。
- [調查事件](investigate-incidents.md)


## <a name="see-also"></a>另請參閱
- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
