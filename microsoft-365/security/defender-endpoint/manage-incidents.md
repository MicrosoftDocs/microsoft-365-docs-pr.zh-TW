---
title: 管理 Microsoft Defender for Endpoint 事件
description: 指派事件、更新其狀態或設定其分類，以管理事件。
keywords: 事件、管理、指派、狀態、分類、true 警示、錯誤警示
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c86b53abf54788740c8c78cb0ecf9251b10ea8f7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842335"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>管理 Microsoft Defender for Endpoint 事件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

管理事件是每個 cybersecurity 作業的重要部分。 您可以從 [ **事件] 佇列** 或 [ **事件管理] 窗格** 中選取事件，以管理事件。 


從 [ **事件] 佇列** 中選取事件，會顯示 **事件管理窗格** ，您可以在其中開啟「事件」頁面以取得詳細資訊。


![事件管理窗格的影像](images/atp-incidents-mgt-pane-updated.png)

您可以指派事件給您自己、變更狀態和分類、重新命名或批註，以追蹤其進度。

> [!TIP]
> 更深入瞭解時，系統會根據受影響的端點數目、受影響的使用者、偵測來源或類別等警示屬性，自動產生事件名稱。 這可讓您快速瞭解事件的範圍。
>
> 例如：多 *個來源所報告之多個端點上的多階段事件。*
>
> 自動事件命名的首次展示中已存在的事件，會保留其名稱。
>


![事件詳細資料頁面的影像](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>指派事件
若尚未指派事件，您可以選取 [ **指派給我** ] 指派給您自己的事件。 這樣做不僅表示您承擔該事件的擁有權，還包括所有與該事件相關的警示。

## <a name="set-status-and-classification"></a>設定狀態和分類
### <a name="incident-status"></a>事件狀態
您可以在調查進行的過程中變更事件的狀態來將事件分類 (例如：**作用中** 或 **已解決**)。 這可協助您組織及管理小組回應事件的方式。

例如，SoC 分析員可以查看一天的緊急 **主動** 事件，並決定將其指派給自己進行調查。

或者，您的 SoC 分析員可能會將事件 **設定為已** 修正的事件。 

### <a name="classification"></a>分類
您可以選擇不要設定分類，或決定將事件指定為 true 或 false。 這樣做可協助小組查看模式及深入瞭解。

### <a name="add-comments"></a>新增註解
您可以新增註解及檢視與事件相關的歷史活動，以查看先前所做的變更。

對警示進行變更或新增註解時，便會記錄在 [註解和記錄] 區段中。

新增的註解會立即顯示在窗格中。



## <a name="related-topics"></a>相關主題
- [事件佇列](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [查看及組織事件佇列](view-incidents-queue.md)
- [調查事件](investigate-incidents.md)
