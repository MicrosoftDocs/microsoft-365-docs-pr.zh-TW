---
title: 設定 Microsoft 威脅防護事件的優先順序
description: 瞭解如何在 Microsoft 威脅防護中依事件佇列設定事件優先順序
keywords: 事件, 佇列, 概覽, 裝置, 身分識別, 使用者, 信箱, 電子郵件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a08ff27d6d33317df9bd4bf61c0c2ee4cf0ee14e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797755"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>設定 Microsoft 威脅防護事件的優先順序

**適用於：**
- Microsoft 威脅防護



Microsoft 威脅防護會套用相關分析，並將來自不同產品的所有相關警示和調查匯總到單一事件。 Microsoft 威脅防護也會觸發活動的獨特警示，這些活動只會在 Microsoft 威脅防護對整個資產和產品套件有端對端可見度時識別為惡意。 如此一來，Microsoft 威脅防護能對攻擊案例進行更廣泛的描述，讓安全性作業分析師了解及處理組織中的複雜威脅。


**事件佇列**顯示由各裝置、使用者和信箱標示的事件集合。 可協助您設定事件優先順序及制定明智的網路安全回應決策。


![事件佇列的影像](../../media/incidents-queue.png) 

根據預設，Microsoft 365 安全中心中的佇列會顯示最近 30 天內發生的事件，最新的事件會顯示在清單頂端，以協助您先查看最新的事件。

事件佇列顯示可自訂的欄，讓您深入了解事故或內含實體的不同特性，協助您根據事件處理的優先順序制定明智的決策。

若要深入瞭解，自動事件命名會產生以警示屬性為基礎的事件名稱，例如受影響的端點數目、受影響的使用者、偵測來源或類別。 這可讓您快速瞭解事件的範圍。

例如：多 *個來源所報告之多個端點上的多階段事件。*

> [!NOTE]
> 在自動事件命名的首展之前，發生的事件，其名稱不會變更。

事件佇列也會顯示多個篩選選項，套用時，可讓您選擇執行環境中所有現有事件的廣泛整理，或決定要專注於特定案例或威脅。 在事件佇列套用篩選可協助判斷哪個事件需要立即處理。 

## <a name="available-filters"></a>可用的篩選

### <a name="status"></a>狀態
您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。

### <a name="severity"></a>嚴重性
事件的嚴重性表示該事件對您的資產造成的影響。 嚴重性級別越高，影響越大，通常會需要立即處理。 

### <a name="assigned-to-owner"></a>已指派給 (擁有者)
您可以選取指派給任何人或指派給您來篩選清單。

### <a name="multiple-alerts"></a>多個警示 
僅篩選查看包含多個警示的事件。 這可能表示終止鏈中較複雜或參與度更高的攻擊。 


### <a name="multiple-service-sources"></a>多個服務來源 
僅篩選查看包含來自不同來源的警示 (Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP) 的事件
### <a name="service-sources"></a>服務來源
透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。 

### <a name="multiple-categories"></a>多個類別 
您可以選擇只查看已對應到終止鏈多個類別且可能會造成更大的危害的事件。 

### <a name="categories"></a>類別
選擇特定類別，以專注於終止鏈中的特定步驟

### <a name="data-sensitivity"></a>資料敏感度
某些攻擊鎖定外洩機密敏感性資料或重要資料。 透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。

>[!NOTE]
>只有在開啟 Microsoft 資訊保護時才適用。


## <a name="next-steps"></a>後續步驟
決定優先順序最高的事件後，便可繼續進行事件的調查工作。
- [調查事件](investigate-incidents.md)


## <a name="related-topics"></a>相關主題
- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
