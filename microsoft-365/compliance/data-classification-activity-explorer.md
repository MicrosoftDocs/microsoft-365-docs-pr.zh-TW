---
title: 開始使用活動總管
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活動總管透過讓您查看和篩選使用者對套用標籤的內容執行的操作，來完善資料分類功能。
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114005"
---
# <a name="get-started-with-activity-explorer"></a>開始使用活動總管

[資料分類概述](data-classification-overview.md)和[內容瀏覽器](data-classification-content-explorer.md)索引標籤可讓您深入瞭解已發現及已標示的內容，以及內容的位置。 活動總管透過讓您監視對已套用標籤的內容執行的工作，從而完善此功能套件。 活動瀏覽器提供已標示內容的活動歷史視圖。 活動資訊收集自 Microsoft 365 的整合審計記錄檔，並在活動資源管理器 UI 中進行轉換和使用。 

![預留位置螢幕擷取畫面概觀活動總管](../media/data-classification-activity-explorer-1.png)

有超過 30 個不同的篩選可使用，其中包括：

- 日期範圍
- 活動類型
- 位置
- 使用者
- 敏感度標籤
- 保留標籤
- 檔案路徑
- DLP 原則



## <a name="prerequisites"></a>必要條件

每個存取並使用資料分類的帳戶，都必須有從下列其中一個訂閱中指派的授權：

- Microsoft 365 (E5)
- Office 365 (E5)
- 進階合規性 (E5) 附加元件
- 進階威脅情報 (E5) 附加元件
- Microsoft 365 E5/A5 資訊保護和控管
- Microsoft 365 E5/A5 合規性

### <a name="permissions"></a>權限

 若要存取 [活動流覽] 索引標籤，必須明確指派任何其中一個角色群組的成員資格或明確授與該角色的帳戶。

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365 角色群組**

- 全域管理員
- 合規性系統管理員
- 安全性系統管理員
- 合規性資料管理員

**Microsoft 365 角色**

- 合規性系統管理員
- 安全性系統管理員

## <a name="activity-types"></a>活動類型

活動 explorer 會從多個活動來源收集審計記錄檔的活動資訊。 如需詳細資訊，請參閱活動瀏覽器 [中可用](data-classification-activity-explorer-available-events.md)的標記事件。

**敏感度標籤活動** 和 **保留標記活動**，來自 Office 原生應用程式、Azure 資訊保護增益集、SharePoint 線上、Exchange Online (敏感度標籤只) 和 OneDrive。 部分範例如下：

- 已套用標籤
- 已變更標籤 (升級、降級或移除)
- 自動加上標籤模擬
- 檔案讀取 

**Azure 資訊保護 (AIP) 掃描器和 AIP 用戶端**

- 套用保護
- 變更保護
- 已移除保護
- 探索的檔案 

活動 explorer 也會收集 **DLP 原則** 比對來自 Exchange Online 的事件、SharePoint 線上、OneDrive、Teams 聊天與通道 (預覽) 、內部部署 SharePoint 資料夾與文件庫，以及內部部署檔案共用，以及透過 **端點資料遺失防護 Windows 10 DLP (** 裝置的) 裝置。 Windows 10 裝置的一些事件範例是檔案：

- 刪除
- 創作
- 複製到剪貼簿
- 修改時間
- 讀
- 列印的
- 重新命名的
- 複製到網路共用
- unallowed 應用程式存取 

瞭解您機密標示內容所採取的動作，是您可以查看是否已放入的控制項，例如 [資料遺失防護](dlp-learn-about-dlp.md) 是否有效。 如果無效，或者如果您發現一些意外情況 (例如大量加上`highly confidential`標籤並降級為`general`的項目)，則可以管理各種原則並採取新動作來限制不需要的行為。

> [!NOTE]
> 活動總管目前未監視 Exchange Online 的保留活動。

## <a name="see-also"></a>另請參閱

- [了解敏感度標籤](sensitivity-labels.md)
- [瞭解保留原則和保留標籤](retention.md)
- [了解敏感性資訊類型](sensitive-information-type-learn-about.md)
- [了解資料分類](data-classification-overview.md)
