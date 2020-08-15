---
title: 了解記錄
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解可協助您在 Microsoft 365 中實施記錄管理解決方案的記錄。
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685439"
---
# <a name="learn-about-records"></a>了解記錄

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

在 Microsoft 365 中管理記錄可協助組織遵守公司政策、法律或法規義務，同時降低風險和法律責任。

當內容標示為記錄時：

- 根據[允許或封鎖的動作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)，對項目施加限制。

- 關於項目的其他活動會予以記錄。

- 在項目保留期結束時將其刪除時，您會有處置證明。

使用[保留標籤](retention.md#retention-labels)將內容標記為記錄。 您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。

透過使用保留標籤來將內容標記為記錄，您可以在 Microsoft 365 環境中實作單一且一致的管理記錄策略。

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>比較允許或封鎖動作的限制

使用下表來找出由於套用標準保留標籤，對內容施加的限制，以及將內容標示為記錄的保留標籤。 

標準保留標籤的設定可保留資料，而不會將內容標示為記錄。

>[!NOTE] 
> 為了完整起見，表格包含鎖定和解除鎖定記錄的欄，這適用於 SharePoint 和 OneDrive，但不適用 Exchange。 鎖定和解除鎖定記錄的功能會使用[記錄版本設定](record-versioning.md)，其不支援 Exchange 項目。 因此，針對標示為記錄的所有 Exchange 項目，行為會對應到**記錄 - 鎖定**欄，而**記錄 - 解除鎖定**則不相關。


|動作| 保留標籤 |記錄 - 鎖定| 記錄 - 解除鎖定|
|:-----|:-----|:-----|:-----|:-----|
|編輯內容|允許 | **封鎖** | 允許|
|編輯內容，包括重新命名|已允許 |已允許 | 已允許|
|刪除|允許 <sup>1</sup> |**封鎖** | **封鎖**|
|複製|已允許 |已允許 | 已允許|
|在容器內移動 <sup>2</sup>|已允許 |已允許 | 已允許|
|在容器間移動 <sup>2</sup>|允許 |如果從未解除鎖定則允許 | 允許|
|開啟/讀取|已允許 |已允許 | 已允許|
|變更標籤|允許 |允許 - 僅限容器系統管理員 | 允許 - 僅限容器系統管理員|
|移除標籤|允許 |允許 - 僅限容器系統管理員 | 允許 - 僅限容器系統管理員|

註腳：

<sup>1</sup> OneDrive 和 Exchange 透過將複本保留在安全的位置但由 SharePoint 鎖定而支援。

使用者嘗試刪除 SharePoint 中的加標籤文件時會看見的訊息：

![無法從 SharePoint 中刪除項目的訊息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> 容器包括 SharePoint 文件庫和 Exchange 信箱。

## <a name="next-steps"></a>後續步驟

如果您還未有保留標籤可用以記錄管理，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

若要將內容標示為記錄，請參閱 [使用保留標籤宣告記錄](declare-records.md)。
