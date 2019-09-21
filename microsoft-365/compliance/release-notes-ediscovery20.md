---
title: 進階電子文件的版本資訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文包含 release notes for 進階電子文件。
ms.openlocfilehash: f3d26b1c84746581ccf32e1d4aada079fc21dfb3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078180"
---
# <a name="release-notes-for-advanced-ediscovery"></a>進階電子文件的版本資訊

進階電子文件的公開預覽程式是搶先即將推出的功能和更新的方式。 若要搶先使用最新功能，剛建立，並使用進階電子文件探索案例中安全性 & 合規性中心。 請參閱[建立新的案例](create-new-ediscovery-case.md)。

## <a name="known-issues"></a>已知問題

**Microsoft Forms**

- 在進階電子文件中使用 「 搜尋 」 工具來搜尋 custodian 信箱時，將無法搜尋資料對應在 2019 年 1 月 31 日之前建立的表單。 建立要用於搜尋此日期之後的表單。

- 即使刪除建立表單的使用者表單，建立由使用者仍然可以收到回應。 不過，這些回應 （發生之後 custodian 信箱已刪除） 的相對應的資料不會搜尋在進階電子文件中使用 「 搜尋 」 工具來搜尋 custodian 信箱時。
 
**Microsoft Sway**

- 在進階電子文件中使用 「 搜尋 」 工具來搜尋 custodian 信箱時，如果使用者編輯 sway 剛之前的擁有者的使用者帳戶的刪除 sway，則這些變更可能不是可供搜尋。 Sway 區塊變更 sway，只要該函數會收到已刪除帳戶的訊號。 不過，沒有小型機率之前收到此訊號，是否可以編輯 sway。

## <a name="issues-fixed-in-this-release"></a>在此版本修正的問題

- DCR： 例外處理未編製索引的項目和孤立的項目
- DCR： 保留通知
- 在 eDiscovery DCR: Custodians

## <a name="whats-new"></a>新功能

- **安全性 & 合規性中心中的 Redesigned 導覽**– 進階電子文件有新的外觀與風格。 使用進階電子文件管理多個案例的工作流程。

- **專案管理**– 沒有其他支援新案例的類型。 您也可以選取並儲存您最近和最愛的情況。 追蹤及監視活動內及其的情況下，使用新的儀表板。

- **Custodian 管理**-新增和移除案例內的資料 custodians 使用者。

- **Exchange、 OneDrive 及 microsoft Teams 整合**– 自動將使用者的目前信箱、 OneDrive for Business 帳戶及 Microsoft Teams 網站新增至案例。 

- **Custodian 通訊**– 傳送和管理您的組織代表的合法持有通知。

- **Custodian 入口網站**-新的入口網站的存取其 active custodians 保留通知。

- **深編製索引**– 重新編目已局部編製索引項目依需求。

- **錯誤修復**– 修復或下載處理錯誤;這包含大型檔案類型、 密碼保護檔案，以及更多的補救支援。 

- **若要搜尋的增強功能**– 建立由識別 custodians 及/或位置的搜尋。

- **檢閱設定**– 管理、 追蹤及靜態的稽核設定的文件。

- **檢閱**– 使用原生、 文字和附近原生檢視檢閱文件新增至您檢閱組。

- **Redact，加上標籤，並加上註解**– Redact 文字、 套用標記，以及當您檢閱文件註釋。
  
- **分析供電檢閱**– 利用進階電子文件探索分析得以尋找、 搜尋及 cull 檢閱集合內的結果。

- **工作**– 長時間執行程序的追蹤狀態。

- **新增稽核的活動**– 追蹤和檢視新的稽核進階電子文件的活動。
