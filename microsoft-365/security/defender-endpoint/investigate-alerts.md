---
title: 調查 Microsoft Defender for Endpoint 警示
description: 使用調查選項來取得有關警示的詳細資料、其意義，以及如何解決。
keywords: 調查，調查，裝置，裝置，警示佇列，儀表板，IP 位址，檔案，送出、提交、深入分析、時程表、搜尋、網域、URL、IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 8b3b864e716957c24893d2097249440b0a90f10a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186098"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>調查 Microsoft Defender for Endpoint 中的警示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

調查影響網路的警示，瞭解其含義及解決方法。

選取 [警示] 佇列中的警示，以移至 [警示] 頁面。 此視圖包含提醒標題、受影響的資產、詳細資料側窗格及警示案例。

在 [警示] 頁面中，選取 [警示案例] 樹狀目錄中的受影響資產或任何實體，以開始調查。 [詳細資料] 窗格會自動填入有關您所選取之專案的詳細資訊。 若要查看您可以在這裡查看的資訊類型，請閱讀 [Microsoft Defender For Endpoint 中的審閱警示](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)。

## <a name="investigate-using-the-alert-story"></a>使用警示案例調查

警示案例會詳細說明觸發警示的原因、之前與之後發生的相關事件，以及其他相關實體。

實體是可按一下的，而每個非警示的實體都會使用該實體的卡片右側的展開圖示展開。 焦點中的實體會由該實體卡片左側的藍色點線表示，而且標題中的警示會先開始。

展開實體以快速查看詳細資料。 選取實體會將詳細資料窗格的內容切換至此實體，並可讓您複查進一步的資訊，以及管理該實體。 在實體卡片 *右邊選取 [...]* ，會顯示該實體所有可用的動作。 當該實體處於焦點中時，這些相同動作會出現在詳細資料窗格中。

> [!NOTE]
> 「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。

![警示案例的範例，具有專注的警示和部分擴充的卡片](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>從詳細資料窗格採取動作

當您選取相關實體時，詳細資料窗格會變更，以顯示所選實體類型的相關資訊，並提供歷史資訊，以直接從警示頁面對此實體 **採取動作** 。

完成調查後，請回到您已開始的警示，將警示的狀態標示為 [ **已解決** ]，然後將其歸類為 **False 警示** 或 **True 警示**。 分類提醒可協助調整這項功能，以提供更真實的警示及不太虛假的警示。

如果您將其歸類為 true 警示，您也可以選取判斷，如下圖所示。

![詳細資料窗格中含有已解析之警示和確定下拉式展開功能的程式碼片段](images/alert-details-resolved-true.png)

如果您遇到的是與企業營運相關的預警，請建立抑制規則，以避免未來出現這種類型的警示。

![在詳細資料窗格中高亮顯示隱藏規則的動作和分類](images/alert-false-suppression-rule.png)

> [!TIP]
> 如果您遇到上述任何問題，請使用 🙂 按鈕提供意見反應或開啟支援票證。


## <a name="related-topics"></a>相關主題
- [查看和組織 Microsoft Defender for Endpoint 警示佇列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查與 Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 [Defender for Endpoint Devices] 清單中的裝置](investigate-machines.md)
- [調查與 Defender for Endpoint alert 相關聯的 IP 位址](investigate-ip.md)
- [調查與 Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
- [調查 Endpoint for Endpoint 中的使用者帳戶](investigate-user.md)


