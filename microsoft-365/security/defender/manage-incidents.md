---
title: 在 Microsoft 365 Defender 中管理事件
description: 了解如何指派及更新狀態
keywords: 事件, 警示, 相關警示, 指派, 更新, 狀態, 管理, 分類, Microsoft, 365, m365
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
ms.openlocfilehash: 72d368cd92739e191dcb292000b8429a472aa981
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498442"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中管理事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



管理事件對確保控制及解決威脅至關重要。 在 Microsoft 365 Defender 中，您有權管理裝置、使用者和信箱上的事件。 


您可以從 **[事件佇列]** 選取事件來管理事件。 

您可以編輯事件名稱、解決事件、設定其分類及判斷。 您也可以將事件指派給自己、新增事件標籤和註解。

在調查時，若您要將警示從某事件移到另一個事件，也可以從 [警示] 索引標籤執行此動作，以建立包含所有相關警示的較大或較小事件。

## <a name="edit-incident-name"></a>編輯事件名稱
事件會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別）自動指派名稱。 這可讓您快速瞭解事件的範圍。

例如：多 *個來源所報告之多個端點上的多階段事件。*

您可以修改事件名稱，以更符合您偏好的命名慣例。

> [!NOTE]
> 在自動事件命名功能的展示中，已存在的事件將保留其名稱。



## <a name="assign-incidents"></a>指派事件
如果尚未指派事件，您可以選取 **[指派給我]** 將事件指派給自己。 這樣做不僅表示您承擔該事件的擁有權，還包括所有與該事件相關的警示。

## <a name="set-status-and-classification"></a>設定狀態和分類
### <a name="incident-status"></a>事件狀態
您可以在調查進行的過程中變更事件的狀態來將事件分類 (例如：**作用中** 或 **已解決**)。 這可協助您組織及管理小組回應事件的方式。

例如，您的 SOC 分析師可檢閱當天的緊急 **作用中** 事件，並決定是否將該事件指派給自己進行調查。

如果事件已修補，您的 SOC 分析師可將事件設為 **已解決**。 解決事件將會自動關閉屬於該事件且仍開啟的所有警報。 

### <a name="classification-and-determination"></a>分類及判斷
您可以選擇不要設定分類，或決定將事件指定為 true 或 false。 這樣做可協助小組查看模式及深入瞭解。 

## <a name="add-comments"></a>新增註解
您可以新增註解及檢視與事件相關的歷史活動，以查看先前所做的變更。

對警示進行變更或新增註解時，便會記錄在 [註解和記錄] 區段中。

新增的註解會立即顯示在窗格中。

## <a name="add-incident-tags"></a>新增事件標籤
您可以將自訂標記新增至事件，例如標示具有共同特性的事件群組。 您可以稍後篩選包含特定標籤的所有事件的事件佇列。
