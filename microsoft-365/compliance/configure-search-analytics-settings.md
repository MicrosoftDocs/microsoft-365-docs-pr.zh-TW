---
title: 設定搜尋與分析設定-資料調查
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
description: 瞭解如何在管理資料調查時，設定搜尋及分析設定，例如接近重複專案、電子郵件執行緒及主題。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527349"
---
# <a name="configure-search-and-analytics-settings"></a>設定搜尋和分析設定

## <a name="near-duplicates-and-email-threading"></a>接近重複專案和電子郵件執行緒

在本節中，您可以設定重複偵測、接近重複偵測和電子郵件執行緒的參數。

- 啟用/停用：在分析流程中包含重複偵測、接近重複偵測，以及在分析流程中的電子郵件執行緒（如果已啟用）。 因為它們彼此上建立，您必須全部啟用或全部停用。

- 臨界值：如果兩個檔的相似性層級超過臨界值，它們就會放在相同的接近重複的集合中。

- 依預設隱藏重複：如果啟用此設定，則預設會在工作集中套用隱藏重複檔案的篩選器。 如有必要，可在工作集內手動移除篩選。

- 最小/最大文字數目：接近重複專案和電子郵件執行緒只會在至少具有最少字數的檔上執行，最多隻會在文字的最大數目。

如需詳細資訊，請參閱[近期重複偵測](near-duplicates.md)和[電子郵件執行緒](email-threading.md)。

## <a name="themes"></a>佈景主題

在本節中，您可以為主題設定參數。

- 啟用/停用：在分析流程中包含主題叢集（如果已啟用）。

- 動態調整主題數目上限：在某些情況下，沒有足夠的檔來產生所需的主題數目。 如果開啟此設定，而不是嘗試強制所需的主題數目上限，系統就會自動調整主題的最大數目。

- 主題數目上限：所需的主題數目。

- 在主題中包含編號：啟用時，它會在產生主題時包含數位。  

## <a name="optical-character-recognition-ocr"></a>光學字元辨識（OCR）

開啟此設定時，會在 ingested 至工作集的影像上執行 OCR，使其可供搜尋。

## <a name="ignore-text"></a>忽略文字

在某些情況下，有些文字會降低 analytics 的品質，例如，即使電子郵件的內容，也會新增至特定電子郵件的冗長免責聲明。 如果您知道這種情況，您可以指定文字（支援 RegEx）以及應排除文字的模組，即可從分析中排除此文字。
