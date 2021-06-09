---
title: 報告 Microsoft Bookings 的資訊
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 瞭解您可以如何查看您的預約活動的4個月檢視
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887222"
---
# <a name="reporting-info-for-bookings"></a>用於預定的報告資訊

您現在可以在 TSV 檔中看到您的預約行事曆的四個月檢視。 TSV 檔會顯示四個月的資料，但是您可以在一年的整個課程中，選取不同的四個月週期。

此約會層級資訊可用於在您的預定行事曆周圍顯示客戶活動。 TSV 檔案是以 tab 分隔的值檔。 您可以使用任何文字編輯器或試算表程式（例如 Excel）來查看或編輯此類檔案。

## <a name="see-four-months-of-booking-activity"></a>請參閱四個月的預約活動

1. 在 [預約行事曆] 儀表板中，選取 [將 **更多資料匯出為 TSV**]。

:::image type="content" source="../media/bookings-activities.png" alt-text="螢幕擷取畫面：預定活動的4個月":::

1. 使用新名稱儲存檔案，並指定 .xls 或 .xlsx 格式。

1. 開啟檔案，以查看您的預定行事曆的四個月檢視。

1. 選擇報告的日期，然後選取 [ **匯出**]。

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="螢幕擷取畫面：挑選時間範圍，並將資料匯出至 TSV 檔案。":::

1. 下載的報表除了包含現有欄位之外，還包含一組新的欄位。

報告包含下欄欄位。

 - **日期及時間**
- **客戶名稱**
- **客戶電子郵件**
- **客戶電話**
- **客戶位址**
- **員工**
- **服務**
- **位置**
- **Duration (分鐘)**
- **事件種類**

改進的報表現在包含下欄欄位。

- **定價類型**   在建立服務時，為服務設定的預設價格類型。
- **Price**   與所選定價類型相對應的價格。
- **幣種**   為商務用的貨幣類型設定。
- **Cc 出席**   者  將要接收預約電子郵件通知的收件者。 這可以在建立預約時從 Teams 應用程式指定。
- **簽署的出席者計數**   有多少客戶預約了群組預約服務。
- **已啟用文字通知**  客戶是否可以接收簡訊與文字相關的通知。
- **自訂欄位**   在此欄位中會組合與單一預約相關的所有問題和解答。
- **預約識別碼**   這有助於識別相同的群組服務預訂。
