---
title: 針對勒索軟體建立電子郵件規則
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何建立電子郵件規則來防止勒索軟體。
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926111"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>建立電子郵件規則以防止勒索軟體

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 可防範勒索軟體，避免在 Outlook 中開啟有潛在危險的檔案 ，例如 JavaScript、批次和可執行檔。 若要新增規則來封鎖或警告其他類型的檔案，以提高此保護層級，請遵循下列步驟。

## <a name="try-it"></a>試試看吧！

1. 在系統管理中心， [https://admin.microsoft.com](https://admin.microsoft.com) 選擇系統管理中心 **下的** **Exchange。**
1. 從左側的功能表中，選擇 **郵件流程**。
1. 在規則標上，選擇加號旁邊的箭號 (+) 符號，然後選擇 **建立新規則。**
1. 在新的 **規則** 頁面上，輸入規則的名稱，卷卷至底部，然後選擇更多 **選項**。
1. 在 **Apply this rule if**， select Any **attachment，** and then select **file extension includes these words.**
1. 在 **指定字詞或** 片語下的方塊中，輸入您想要將規則所適用于的副檔名，例如可包含宏的副檔名。 使用加 (+) 符號，一次新增一個。

    閱讀防範勒索軟體 [以深入瞭解檔案類型](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。

1. 向下卷卷以檢查您的清單，**然後選擇確定。**
1. 在新規則 **頁面上** ，選擇 **新增** 條件，然後在執行下列操作下 **選擇條件**。
1. 您有許多規則選項可供選擇，但在此範例中，我們會選擇以郵件通知 **收件者**。
1. 輸入通知的訊息文字，**然後選擇確定。**
1. 選用：在 **新增規則** 頁面上，選擇新增例外，並輸入例外規則的任何詳細資料，例如來自信任的寄件者的郵件。
1. 在新規則頁面上 **，選擇儲存**，然後查看所提供的規則摘要資訊。