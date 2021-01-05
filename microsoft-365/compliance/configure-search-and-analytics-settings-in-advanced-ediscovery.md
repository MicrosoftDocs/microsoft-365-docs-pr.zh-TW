---
title: 設定搜尋及分析設定-高級電子檔探索
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-mar2020
description: 設定案例中套用至所有審閱集的高級 eDiscovery 設定。 這包括分析和光學字元辨識的設定。
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751300"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>在高級電子檔探索中設定搜尋及分析設定

您可以設定每個高級 eDiscovery 案例的設定，以控制下列功能。

- 接近重複專案和電子郵件執行緒

- 佈景主題

- 自動產生的複查集查詢

- 忽略文字

- 光學字元辨識

若要設定案例的搜尋及分析設定：

1. 在 [ **高級電子** 檔探索] 頁面上，選取案例。

2. 在 [ **設定** ] 索引標籤的 [ **搜尋 & 分析**] 底下，按一下 [ **選取**]。

   [案例設定] 頁面隨即顯示。 這些設定會套用至案例中的所有複查集。

   ![設定高級 eDiscovery 案例的分析和搜尋設定](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>接近重複專案和電子郵件執行緒

在本節中，您可以設定重複偵測、接近重複偵測和電子郵件執行緒的參數。 如需詳細資訊，請參閱 [近期重複偵測](near-duplicate-detection-in-advanced-ediscovery.md) 和 [電子郵件執行緒](email-threading-in-advanced-ediscovery.md)。

- **接近重複/電子郵件執行緒：** 開啟時，當您對檢查集中的資料執行分析時，會在工作流程中包含重複偵測、重複偵測和電子郵件執行緒。

- **檔和電子郵件相似性臨界值：** 如果兩個檔的相似性層級超過臨界值，這兩個檔會放在相同的接近重複的集合中。

- **最小/文字數目上限：** 這些設定會指定接近重複專案和電子郵件執行緒分析，只會在至少具有至少字數最少的檔上執行，最多的字數目。

## <a name="themes"></a>佈景主題

在本節中，您可以為主題設定參數。 如需詳細資訊，請參閱 [Themes](themes-in-advanced-ediscovery.md)。

- **主題：** 開啟時，當您對複查集內的資料執行分析時，會以工作流程的一部分來執行主題聚簇。

- **主題數目上限：** 指定當您對複查集內的資料執行分析時，可產生的主題數目上限。

- **在主題中包含編號：** 開啟時，會在產生主題時包含識別主題) 的數位 (。 

- **動態調整主題數目上限：** 在某些情況下，審閱集中的檔可能不足以產生所需的主題數目。 啟用此設定時，「高級 eDiscovery」會動態調整主題的數目上限，而不是嘗試強制執行主題的最大數目。

## <a name="review-set-query"></a>審閱集合查詢

如果您選取 [在 **分析後自動建立用於審閱已儲存的搜尋** ] 核取方塊，則會有「高級 eDiscovery autogenerates 複查集」查詢（命名 **為待複查** 

![進行中的審閱自動產生查詢](../media/AeDForReviewQuery.png)

此查詢基本上會篩選出評審集中的重複專案。 這可讓您檢查審閱集中的唯一專案。 只有在您為案例中的複查集執行分析時，才會建立此查詢。 如需詳細資訊，請參閱關於複查集查詢的資訊，請參閱 [在審閱集中查詢資料](review-set-search.md)。

## <a name="ignore-text"></a>忽略文字

在某些情況下，有些文字會降低分析品質，例如在電子郵件中加入的冗長免責聲明，不論電子郵件的內容為何。 如果您知道應該忽略的文字，您可以指定文字字串及分析功能 (接近重複的電子郵件執行緒、主題及相關性) 應排除的文字，以將其排除在分析之外。 也支援使用正則運算式 (RegEx) 為略過的文字。 

## <a name="optical-character-recognition-ocr"></a>光學字元辨識 (OCR) 

開啟此設定時，會在圖像檔案上執行 OCR 處理。 在下列情況下，會執行 OCR 處理：

- 當保管人和 [非 custodial 資料來源](non-custodial-data-sources.md) 新增至案例時。 在高級索引處理常式期間會執行 OCR 處理。 這表示會在集合搜尋中傳回符合搜尋準則的映射檔中的文字。

- 當其他資料 (源的內容未與保管人相關聯並新增至非 custodial 資料來源中的案例時) 會新增至審閱集。

將資料新增至審閱集合之後，就可以檢查、搜尋、標記和分析影像文字。 您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。 如需詳細資訊，請參閱：

- [進階的監管人資料索引](indexing-custodian-data.md)

- [將搜尋結果新增至檢閱集](add-data-to-review-set.md#optical-character-recognition)

- [支援的圖像檔案類型](supported-filetypes-ediscovery20.md#image)
