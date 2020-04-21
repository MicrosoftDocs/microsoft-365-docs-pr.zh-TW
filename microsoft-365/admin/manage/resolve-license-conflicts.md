---
title: 解決授權衝突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 瞭解如何解決與 Microsoft 365 for business 訂閱的授權衝突。
ms.openlocfilehash: 51f87c055402d9e6e3bd732a99abf2c155887290
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628085"
---
# <a name="resolve-license-conflicts"></a>解決授權衝突

建議您先購買訂閱所需的授權，再建立新的使用者。 如此一來，就能在建立使用者帳戶時，將授權指派給新的使用者。 如果您已經將所有授權指派給使用者，但其中有部分授權已過期，或是您嘗試移除已經指派給某位使用者的授權，將會發生授權衝突。 如需詳細資訊，請參閱[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。
  
## <a name="how-do-i-view-license-conflicts"></a>如何查看授權衝突？

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">授權</a>] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">授權</a>] 頁面。

::: moniker-end


2. 檢查 [**狀態**] 欄，以取得與衝突相關的資訊。 如果發生衝突，您會看到一則警告訊息，指出一或多個使用者需要有效的授權。

    > [!NOTE]
    > 如果沒有衝突，您就不會看到 [**狀態**] 欄。

## <a name="how-do-i-resolve-license-conflicts"></a>如何解決授權衝突？

您可以從[購買更多授權](../../commerce/licenses/buy-licenses.md)或[從不再需要授權的使用者中移除](remove-licenses-from-users.md)授權，來解決授權衝突。 您可以選擇性地[刪除使用者帳戶以釋出授權](../add-users/delete-a-user.md)。
  
## <a name="related-articles"></a>相關文章 

[將授權指派給使用者](assign-licenses-to-users.md)
  
[從使用者移除授權](remove-licenses-from-users.md)
