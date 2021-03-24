---
title: 在 Microsoft Defender for Endpoint 中檢查提醒
description: 檢查警示資訊，包含詳細說明的警示案例，以及階層每個步驟的詳細資料。
keywords: 事件，事件，機器，裝置，使用者，警示，警示，調查，圖形，證據
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057328"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中檢查提醒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Microsoft Defender for Endpoint 中的 [警示] 頁面會透過結合與所選警示相關的攻擊信號和警示，提供完整的警示內容，以建立詳細的警示案例。

快速進行會審、調查，並對影響組織的警示採取有效的動作。 瞭解它們的觸發原因，以及其對一個位置的影響。 若要深入瞭解，請參閱本概述。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>提醒入門

在 [Defender for Endpoint] 中選取警示的名稱時，會將您置於警示頁面上。 在 [警示] 頁面上，所有的資訊都會顯示在所選警示的內容中。 每個提醒頁面包含4個區段：

1. **提醒標題** 會顯示警示的名稱，而且可以提醒您，不論您在頁面上選取的是哪一個警示已開始您目前的調查。
2. [**受影響資產**](#review-affected-assets) 列出此警示所影響的裝置和使用者卡，以供進一步資訊和動作使用。
3. **警示案例** 會顯示與該警示相關的所有實體，並以樹狀檢視互連。 當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點中的警示。 警示案例中的實體可展開和按一下，以提供額外的資訊，並可讓您在警示頁面的內容中採取動作，以加速回應。 使用警示案例開始您的調查。 瞭解如何 [調查 Microsoft Defender For Endpoint 中的通知](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。
4. [ **詳細資料] 窗格** 會先顯示選取警示的詳細資料，以及與此警示相關的詳細資料和動作。 如果您選取預警案例中的任何受影響的資產或實體，詳細資料窗格會變更，以提供所選物件的上下文資訊和動作。

請注意警示的偵測狀態。 
- 已避免-已避免嘗試的可疑動作。 例如，檔案不是寫入磁片或執行。
![阻止顯示威脅的警示頁面](images/detstat-prevented.png)
- 封鎖-已執行可疑行為，然後遭到封鎖。 例如，已執行某個進程，但由於後來出現可疑行為，所以處理常式已終止。
![已封鎖顯示威脅的警示頁面](images/detstat-blocked.png)
- 偵測–偵測到攻擊，而且可能仍在使用中。
![偵測到顯示威脅的警示頁面](images/detstat-detected.png)




您也可以在警示的詳細資料窗格中查看 *自動調查詳細資料* ，以查看已採取的動作，以及讀取建議動作的警示描述。

![[詳細資料] 窗格中 [警示描述] 和 [自動調查] 區段已反白顯示的程式碼片段](images/alert-air-and-alert-description.png)

警示開啟時，詳細資料窗格中提供的其他資訊包括 MITRE 技巧、來源及其他上下文詳細資料。




## <a name="review-affected-assets"></a>審閱受影響的資產

選取「受影響的資產」區段中的裝置或使用者卡片，會在詳細資料窗格中切換到裝置或使用者的詳細資料。

- **對於裝置**，詳細資料窗格會顯示裝置本身的相關資訊，例如 Domain、作業系統和 IP。 也可以使用作用中的警示及該裝置上登入的使用者。 您可以透過隔離裝置、限制應用程式執行或執行防病毒掃描，立即採取行動。 或者，您也可以收集調查套件、啟動自動調查，或是移至 [裝置] 頁面，以從裝置的查看角度進行調查。

   ![選取裝置時的詳細資料窗格片段](images/device-page-details.png)

- **針對使用者**，詳細資料窗格會顯示詳細的使用者資訊，例如使用者的 SAM 名稱和 SID，以及此使用者執行的登入類型，以及與其相關的任何警示和事件。 您可以選取 [ *開啟使用者] 頁面* ，繼續從該使用者的觀點進行調查。

   ![選取使用者時詳細資料窗格的程式碼片段](images/user-page-details.png)


## <a name="related-topics"></a>相關主題

- [查看和組織事件佇列](view-incidents-queue.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
