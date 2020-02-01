---
title: 管理 Microsoft 威脅防護中的事件
description: 了解如何指派及更新狀態
keywords: 事件, 警示, 相關警示, 指派, 更新, 狀態, 管理, 分類, Microsoft, 365, m365
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
ms.openlocfilehash: 46904323a1ec8f969355931f8b69a3ed0ebf4519
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600210"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>管理 Microsoft 威脅防護中的事件

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

管理事件對確保控制及解決威脅至關重要。 在 Microsoft 威脅防護中，您可管理裝置、使用者和信箱的事件。 


您可以從 **[事件佇列]** 選取事件來管理事件。 

您可以編輯事件名稱、解決事件、設定其分類及判斷。 您也可以將事件指派給自己、新增事件標籤和註解。

在調查時，若您要將警示從某事件移到另一個事件，也可以從 [警示] 索引標籤執行此動作，以建立包含所有相關警示的較大或較小事件。

## <a name="edit-incident-name"></a>編輯事件名稱
根據預設，系統會為事件指派一個編號。 您可以修改事件名稱，以更符合您偏好的命名慣例。
 
## <a name="assign-incidents"></a>指派事件
如果尚未指派事件，您可以選取 **[指派給我]** 將事件指派給自己。 這樣做不僅表示您承擔該事件的擁有權，還包括所有與該事件相關的警示。

## <a name="set-status-and-classification"></a>設定狀態和分類
### <a name="incident-status"></a>事件狀態
您可以在調查進行的過程中變更事件的狀態來將事件分類 (例如：**作用中**或**已解決**)。 這可協助您組織及管理小組回應事件的方式。

例如，您的 SOC 分析師可檢閱當天的緊急**作用中**事件，並決定是否將該事件指派給自己進行調查。

如果事件已修補，您的 SOC 分析師可將事件設為**已解決**。 解決事件將會自動關閉屬於該事件且仍開啟的所有警報。 

### <a name="classification-and-determination"></a>分類及判斷
您可以選擇不要設定分類，或決定將事件指定為 true 或 false。 這樣做可協助小組查看模式及深入瞭解。 

## <a name="add-comments"></a>新增註解
您可以新增註解及檢視與事件相關的歷史活動，以查看先前所做的變更。

對警示進行變更或新增註解時，便會記錄在 [註解和記錄] 區段中。

新增的註解會立即顯示在窗格中。

## <a name="add-incident-tags"></a>新增事件標籤
您可以為事件新增自訂標籤，例如使用常見特性來標記一組事件。 您可以稍後篩選包含特定標籤的所有事件的事件佇列。

