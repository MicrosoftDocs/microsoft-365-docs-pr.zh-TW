---
title: 設定搜尋和分析設定
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
description: ''
ms.openlocfilehash: cce056f1dcc0225da13612ffbd9985af3eb4ce9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596220"
---
# <a name="configure-search-and-analytics-settings"></a>設定搜尋和分析設定

## <a name="near-duplicates-and-email-threading"></a>近似重複項目和電子郵件執行緒

在這個區段中，您可以設定的參數重複資料偵測，接近重複資料偵測和電子郵件執行緒。

- 啟用/停用： 包含重複資料偵測，接近重複資料偵測和電子郵件執行緒分析流程如果已啟用的一部分。 因為他們建置彼此，您必須啟用所有的這些或全部予以停用。

- 臨界值： 如果超出臨界值的兩個文件相似性層級，它們會放置在接近重複的設定相同。

- 根據預設隱藏重複項目： 使用預設設定如果開啟此設定時，會套用篩選器來隱藏重複的文件。 可以在設定必要的工作以手動方式移除篩選。

- 字詞的最小值/最大數目： 近似重複項目和電子郵件執行緒會僅在執行最小的數字和最字詞數目上限至少要有的文件。
如需詳細資訊，請參閱[接近重複資料偵測](near-duplicates.md)和[電子郵件執行緒](email-threading.md)。

## <a name="themes"></a>佈景主題

在這個區段中，您可以設定的佈景主題的參數。

- 啟用/停用： 包括叢集一部分分析流程如果已啟用的佈景主題。
- 以動態方式動態調整的佈景主題數目上限： 在某些情況下，沒有足夠的文件，以產生所需的佈景主題數目。 如果開啟此設定，然後而不是嘗試強制所需的數目上限的佈景主題，系統會調整佈景主題的數目上限以動態方式。
- 佈景主題數目上限： 所需的佈景主題數目
- 包含佈景主題中的數字： 啟用時，產生的佈景主題時，它會包括中的數字。  

## <a name="optical-character-recognition-ocr"></a>光學字元辨識 (OCR)

時開啟此設定，將會 ingested 成工作集，讓他們可以是可搜尋的映像上執行 OCR。

## <a name="ignore-text"></a>忽略的文字

有某些敘述性文字會降低品質的分析，例如冗長的免責聲明，新增至特定的電子郵件，不論電子郵件的內容，其中的執行個體。 如果您知道這種情況下，您可以藉由指定的文字 （支援 RegEx） 和其分析從排除此文字應該如包含文字的模組。