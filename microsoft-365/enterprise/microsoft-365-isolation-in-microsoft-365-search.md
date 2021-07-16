---
title: Microsoft 365 搜尋中的租用戶隔離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，將說明租使用者隔離如何在 Microsoft 365 搜尋中個別租使用者資料的運作方式。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464067"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Microsoft 365 搜尋中的租用戶隔離

SharePoint線上搜尋使用租使用者分隔模型，它會平衡共用資料結構的效率，以防範承租人之間的資訊洩漏。 使用此模型，我們避免搜尋功能：

- 傳回包含其他承租人檔的查詢結果
- 在查詢結果中公開足夠的資訊，訓練有素的使用者可能會推斷其他承租人的相關資訊。
- 顯示其他租使用者的架構或設定
- 將承租人或存放區產生的分析處理資訊與錯誤的承租人混淆
- 使用來自其他租使用者的字典專案

對於每一種租使用者資料類型，我們會在程式碼中使用一或多個保護層級，以防意外洩漏資訊。 最重要的資料具有最多層的保護，可確保單一的缺陷不會導致實際或感覺的資訊洩漏。

## <a name="tenant-separation-for-the-search-index"></a>搜尋索引的承租人分隔

搜尋索引會儲存在磁片上主控索引元件的伺服器上，而承租人則會共用索引檔案。 租使用者的索引檔只對該承租人的查詢可見。 三個獨立的機制會防止資訊洩漏：

- 租使用者識別碼篩選
- 租使用者識別碼字詞的首碼
- ACL 檢查

所有三種機制都必須失敗，搜尋才能將檔返還錯誤的承租人。

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>租使用者識別碼篩選和租使用者識別碼條款前面

搜尋會以租使用者識別碼為全文檢索索引中的每個字詞建立索引首碼。 例如，如果為識別碼為 "*123*" 的承租人編制索引字詞 "*foo*"，全文檢索索引中的專案就是 "*123foo"。*

每個查詢都會轉換成包含租使用者識別碼，使用稱為租使用者識別碼篩選的處理常式。 例如，查詢 "*foo*" 會轉換成 "<*guid*>。*foo**TenantID*： <*guid*> "，其中 <*guid*> 代表執行查詢的承租人。 這項查詢轉換會在每個索引節點內發生，而且查詢和內容處理都不會影響。 因為租使用者識別碼會新增至每個查詢，所以無法透過查看一個承租人中的最佳相符排名來推斷其他承租人中的字詞頻率。

租使用者識別碼字詞的首碼只會出現在全文檢索索引中。 欄位搜尋，例如 "*title： foo*"，移至綜合搜尋索引，其中的字詞不是以租使用者識別碼做為首碼。 相反地，欄位搜尋會加上功能變數名稱。 例如，查詢「*title： foo*」會轉換成「*欄位。 TITLE： foo AND fields。 tenantID*： <*guid*>。」 因為字詞的頻率不會影響綜合搜尋索引中的點擊排名，所以不需要租使用者依字詞首碼來分隔。 對於欄位搜尋（如 "*title： foo*"），租使用者內容分隔取決於租使用者識別碼篩選依查詢轉換。

## <a name="document-access-control-list-checks"></a>檔存取控制清單檢查

搜尋會透過儲存在搜尋索引中的 ACLs，控制對檔的存取。 每個專案都會以特殊 ACL 欄位中的一組字詞編制索引。 ACL 欄位包含每個群組或使用者可以查看檔的一個字詞。 每個查詢都會擴充 (ACE) 字詞的存取控制專案清單，其中一個是驗證使用者所屬的群組。

例如，像 "<*guid*> 的查詢。*FOO 和 tenantID*： "<*guid*>" 變成： "<*guid*>。*foo 和 tenantID*： <*guid* >  *和* (*docACL：* < *ace1* >  *或 docACL*： <*ace2* >  *or docACL*： <*ace3* >  *...*) "

由於使用者和群組識別碼（因此 Ace）是唯一的，因此會為只對某些使用者顯示之檔的承租人提供額外的安全性層級。 這種情況也是特殊的「外部使用者以外的所有人」 ACE 的案例，可將存取權授與租使用者中的一般使用者。 不過，由於 "Everyone" 的 Ace 對於所有承租人都是相同的，所以公用檔的承租人分隔取決於租使用者識別碼篩選。 也支援「拒絕」 Ace。 當與 deny ACE 相符時，查詢充實會新增一個子句，該子句會從結果中移除檔。

在 Exchange Online 搜尋中，索引會分割個別使用者信箱的信箱 ID，而不是租使用者識別碼 (訂閱識別碼) 如 SharePoint Online 中所示。 分割機制與 SharePoint 線上，但沒有 ACL 篩選。
