---
title: Microsoft Defender ATP 中的威脅防護報告
description: 使用威脅防護報告追蹤警示偵測、類別和嚴重性
keywords: 警示偵測、來源、警示（依類別、警示嚴重性、警示分類、判斷）
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 104548314b8ef0ceb15d8d2683dad552233a509f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058696"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的威脅防護報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

「威脅防護」報告提供組織中所產生之提醒的高層級資訊。 此報告包含趨勢資訊，顯示偵測來源、類別、嚴重性、狀態、分類，以及每次的通知決定。

儀表板分為兩個區段：

![威脅防護報告的影像](images/threat-protection-reports.png)

區段 | 說明 
:---|:---
1 | 警示趨勢
2  | 警示摘要

## <a name="alert-trends"></a>警示趨勢
根據預設，警示趨勢會顯示30天期間的警示資訊，最後一整天結束。 若要深入瞭解組織中發生的趨勢，您可以調整顯示的時段，以微調報告期間。 若要調整時段，請從下拉式選項中選取時間範圍：

- 30 天
- 3 個月
- 6 個月
- 自訂

>[!NOTE]
>這些篩選器只適用于警示趨勢區段。 它不會影響「警示摘要」區段。


## <a name="alert-summary"></a>警示摘要
當警示趨勢顯示趨勢警示資訊時，警示摘要會顯示目前日期範圍內的警示資訊。

 警示摘要可讓您向下流覽至已套用對應篩選的特定警示佇列。 例如，按一下 [偵測對應卡] 中的 EDR 列時，會透過結果顯示警示佇列，只顯示來自 EDR 偵測產生的警示。 

>[!NOTE]
>在 [摘要] 區段中反映的資料範圍是在目前日期之前的180天。 例如，如果今天的日期是2019年11月5日，則 [摘要] 區段中的資料將會反映從5月5日開始，2019到11月5日（2019）的數位。<br>
> 在 [趨勢] 區段上套用的篩選不會在 [摘要] 區段上套用。 

## <a name="alert-attributes"></a>警示屬性
報告是由顯示下列警示屬性的卡片所組成：

- **偵測來源**：顯示感應器及偵測技術的相關資訊，這些技術可提供 Microsoft Defender for Endpoint 以觸發提醒的資料。

- **威脅類別**：顯示觸發警示的威脅或攻擊活動類型，指出安全性作業的可能焦點區域。

- **嚴重性**：顯示警示的嚴重性層級，指出組織威脅的整體潛在影響，以及解決這些威脅的回應層級。

- **狀態**：顯示警示的解決狀態，指出手動警示回應的效率，以及自動修正 (啟用) 。 

- **分類 & 判斷**：顯示如何在解決問題時進行分類警示、是否已將郵件分類為實際威脅 (true 警示) 或不正確的偵測 (false 警示) 。 這些卡片也會顯示已解決的警示，可提供更多深入資訊，如找到的實際威脅類型或偵測到的合法活動。


 

## <a name="filter-data"></a>篩選資料

使用提供的篩選，以包含或排除具有特定屬性的警示。

>[!NOTE]
>這些篩選器適用于報告中的 **所有** 卡片。

例如，若要顯示僅限高嚴重性警示的資料：

1. 在 [**篩選 > 嚴重性**] 底下，選取 [**高**]
2. 確定已取消選取 [ **嚴重性** ] 底下的其他所有選項。
3. 選取 **套用**。 

## <a name="related-topic"></a>相關主題
- [裝置健康情況和符合性報告](machine-reports.md)
