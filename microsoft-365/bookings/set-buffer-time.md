---
title: 在 Microsoft 預定中設定緩衝時間
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: 設定 Microsoft 預約中約會之前或之後的緩衝時間，以允許清除或重設設備的時間。
ms.openlocfilehash: dceb777f9ddba9f1ddabfee00608813afae57a86
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419368"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>在 Microsoft 預定中設定緩衝時間

您的一些約會可能需要在您與客戶進行設定、清除或重設會議室和設備之後的時間。 或者，如果您正處於客戶約會之間，您可能需要一些時間，以確保您和您的小組可以在約會之間進行移動，而不需等待客戶等候。

您可以在約會開始之前、約會結束或兩者之間設定緩衝時間，讓員工在下一個約會中做好準備。

> [!NOTE]
> 預設會針對具有 Microsoft 365 商務標準、Microsoft 365 A3 或 Microsoft 365 A5 訂閱的客戶，開啟預訂。 預定也可供擁有 Office 365 Enterprise E3 和 Office 365 企業版 E5 的客戶使用，但預設為關閉。 若要開始，請參閱 [取得 Microsoft 預約存取權](get-access.md)。 若要開啟或關閉預約，請參閱 [為您的組織開啟或關閉預訂](turn-bookings-on-or-off.md)。

## <a name="set-buffer-time-defaults"></a>設定緩衝時間預設值

緩衝時間預設值是在 [ **服務詳細資料** ] 頁面的 [預定] 中設定。 就像此頁面上設定的所有服務預設值一樣，您可以為特定預約編輯這些預設值，以符合特定客戶的需求。

您可以在 [**服務詳細資料**] 頁面上的**預設持續時間**選擇器底下找到緩衝時間設定。 在為指定的服務設定之前，您必須選取緩衝時間切換來啟用緩衝時間設定。 這會顯示「 **之前** 」和「 **之後** 」下拉式列，用來挑選每個預約之前和之後保留的預設時間長度，如下所示：

   ![啟用緩衝時間的預約映射](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>緩衝時間及約會時間

為了避免客戶預期與您見面時的困惑，預約會顯示緩衝時間和實際約會時間 (您的客戶預期會在您的行事曆上) 您的行事曆，以及電子郵件確認和提醒給相關人員的時間。 例如，下列為客戶在預約中所看到的預約約會，其中包含15分鐘前的預約緩衝時間。

請注意，事件本身 (在下圖中的左側) 會為實際的客戶約會顯示較亮的陰影，以及緩衝時間的較暗陰影。 約會撥出 (會在您選取事件時開啟) 明確指出約會介於9：12:00 到10：12:00 搭配 Katie，並在約會之前包含15分鐘的緩衝時間，以及約會之後0分鐘。 對員工的確認和提醒類似參照特定的緩衝和約會時間，客戶只會取得參考和提醒，其參考的是9：12:00 至10：12:00 約會時間。

   ![顯示緩衝區時間的預約約會呼叫圖像](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>緩衝時間與可用性

您的客戶不會直接看到，而且無法變更您設定的緩衝時間。 不過，由於緩衝時間是用來計算整體服務持續時間，所以客戶會看到您和您的相關人員，在進行緩衝和定期約會時間時已預約。 只要約會和其緩衝時間有足夠的時間，客戶也只會看到您和您的員工可用性。

舉例來說，具有15分鐘前置約會緩衝時間的一小時約會，至少需要1小時到15分鐘的可用時間區塊。 因此，此服務的約會會在您的行事曆上填滿75分鐘的時間區塊，而且需要75分鐘的時間來進行預訂，而不會發生衝突。
