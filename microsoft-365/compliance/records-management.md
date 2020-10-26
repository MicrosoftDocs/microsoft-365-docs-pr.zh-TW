---
title: Microsoft 365 中的記錄管理
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 使用 Microsoft 365 中的記錄管理，您可以將保留時間表套用到管理保留、記錄聲明和處置的檔案計畫中。
ms.openlocfilehash: e6e72a14d0d3e22823c8341145f64721831586f9
ms.sourcegitcommit: 095b1f52f2e73e8d44195916984efeb0908c2ad8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48755562"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>深入瞭解 Microsoft 365 中的記錄管理

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

所有類型的組織都需要記錄管理解決方案，用來管理其公司資料間的法規、法務及業務關鍵記錄。 Microsoft 365 中的記錄管理可幫助組織管理其法律義務，提供展現法規遵循的能力，並提高不再需要保留、不再具有價值或商業用途不再需要的項目一般處置的效率。

請使用下列功能以支援 Microsoft 365 中的記錄管理解決方案：

- **標籤內容做為記錄**。 建立並設定保留標籤，以便將內容標示為[記錄](#records)，讓使用者自行套用或透過辨識敏感性資訊、關鍵字、或內容類型而自動套用。

- **使用檔案計劃來移轉和管理您的保留需求**。 透過使用[檔案計劃](file-plan-manager.md)，您可以將現有的保留計劃帶入 Microsoft 365，或是建立新的保留方案以增強管理功能。

- **使用保留標籤以便設置保留和刪除的設定值**。 依照各種因素，包括建立的日期或最近一次修改的日期，使用保留期間和動作設定[保留標籤](retention.md#retention-labels)。

- 利用[事件型保留](event-driven-retention.md)，**當事件發生時開始不同的保留期間**。

- 使用[處置檢閱](disposition.md#disposition-reviews)和[記錄刪除](disposition.md#disposition-of-records)證明來**檢閱並驗證處置**。

- 使用[匯出選項](disposition.md#filter-and-export-the-views)來**匯出所有已處置項目的相關資訊**。

- 為組織中的記錄管理員功能**設定特定權限**，以讓其[具有適當權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

藉由使用這些功能，您可以將組織的保留排程和需求整合成一份記錄管理解決方案，以便管理保留、紀錄聲明和處置，以支援完整的內容生命週期。

除了線上文件，您可能會發現，收聽記錄管理的[網路研討會錄音檔](https://aka.ms/MIPC/Video-RecordsManagementWebinar)，並下載隨附的[常見問題投影片組](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)是很實用的。

## <a name="records"></a>記錄

當内容被宣告為記錄時：

- 根據[允許或封鎖的動作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)，對項目施加限制。

- 關於項目的其他活動會予以記錄。

- 在項目保留期結束時將其刪除時，您會有處置證明。

您可以使用 [保留標籤](retention.md#retention-labels) 將內容標示為 **記錄**或**監管記錄**(目前在預覽)。 下一章節將說明兩個二者之間的差異。 您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用至您想要標記為記錄或監管記錄的內容。

透過使用保留標籤來宣告記錄，您可以實施單一且一致的管理記錄策略在您的 Microsoft 365 環境中管理記錄。

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>比較允許或封鎖動作的限制

使用下表格來找出由於套用標準保留標籤，而對內容施加的限制，以及將內容標示為記錄或監管記錄的保留標籤。 

標準的保留標籤具有保留設定和動作，但不能將內容標示為記錄或監管記錄。

>[!NOTE] 
> 為了完整起見，表格包含鎖定和解除鎖定記錄的欄，這適用於 SharePoint 和 OneDrive，但不適用 Exchange。 鎖定和解除鎖定記錄的功能會使用[記錄版本設定](record-versioning.md)，其不支援 Exchange 項目。 因此，針對標示為記錄的所有 Exchange 項目，行為會對應到**記錄 - 鎖定**欄，而**記錄 - 解除鎖定**則不相關。


|動作| 保留標籤 |記錄 - 鎖定| 記錄 - 解除鎖定| 監管記錄 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|編輯內容|允許 | **封鎖** | 允許 | **封鎖**|
|編輯內容，包括重新命名|已允許 |已允許 | 允許| **封鎖**|
|刪除|允許 <sup>1</sup> |**封鎖** |**封鎖**| **封鎖**|
|複製|已允許 |已允許 | 已允許| 已允許|
|在容器內移動 <sup>2</sup>|已允許 |已允許 | 已允許| 已允許|
|在容器間移動 <sup>2</sup>|允許 |如果從未解除鎖定則允許 | 允許| **封鎖**|
|開啟/讀取|已允許 |已允許 | 已允許| 已允許|
|變更標籤|允許 |允許 - 僅限容器系統管理員 | 允許 - 僅限容器系統管理員| **封鎖**
|移除標籤|允許 |允許 - 僅限容器系統管理員 | 允許 - 僅限容器系統管理員| **封鎖**

註腳：

<sup>1</sup> OneDrive 和 Exchange 透過將複本保留在安全的位置但由 SharePoint 鎖定而支援。

使用者嘗試刪除 SharePoint 中的加標籤文件時會看見的訊息：

![無法從 SharePoint 中刪除項目的訊息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

<sup>2</sup> 容器包括 SharePoint 文件庫和 Exchange 信箱。

>[!IMPORTANT] 
> 監管記錄最重要的差異是，當它套用到內容之後，沒有人 (甚至全域系統管理員)，可以移除標籤。 
>
> 此外，針對監管記錄設定的保留標籤具有下列系統管理員限制：
> - 儲存標籤後，保留期間就無法縮短，僅可以延長。
> - 自動標籤原則不支援這些標籤，而且必須使用[保留標籤原則](create-apply-retention-labels.md)來套用。 
> 
> 由於這些動作無法逆轉，請先確認您有必要使用監管記錄，再針對保留標籤選取此選項。 為了防止意外的設定，預設不提供此選項，必須先用 PowerShell 啟動。 [使用保留標籤宣告記錄](declare-records.md)中包含所有説明。

## <a name="next-steps"></a>後續步驟

請參照[開始使用記錄管理](get-started-with-records-management.md)。

若要將內容標示為記錄，請參閱[使用保留標籤宣告記錄](declare-records.md)。
