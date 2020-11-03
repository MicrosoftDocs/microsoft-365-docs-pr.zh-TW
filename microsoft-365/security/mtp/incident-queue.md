---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中排定事件佇列中的事件優先順序
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846709"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>設定 Microsoft 365 Defender 中的事件優先順序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



Microsoft 365 Defender 會套用關聯性分析，並將不同產品的所有相關警示和調查彙集到一個事件中。 Microsoft 365 defender 也會觸發唯一的警示，可在 Microsoft 365 Defender 跨整個房地產及產品套件的端對端可視性時，識別出惡意的活動。 如此一來，Microsoft 365 Defender narrates 更廣泛的攻擊案例，讓安全性作業分析員能夠瞭解並處理整個組織中的複雜威脅。


**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。 可協助您設定事件優先順序及制定明智的網路安全回應決策。


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
篩選僅查看包含不同來源之警示的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 
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
