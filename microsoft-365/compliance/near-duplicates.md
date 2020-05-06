---
title: 接近重複偵測-資料調查
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
description: 在管理資料調查時，請使用接近重複偵測，在分析案例資料時，群組的類似檔。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa451051c008f7a1614661d3bd66129cac6bb4ad
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036428"
---
# <a name="near-duplicate-detection"></a>近似重複項偵測

請考慮一組要檢查的檔，其中的子集是以相同的範本為基礎，而且基本上是相同的樣板語言，但這裡有一些差異。 如果檢閱者可以識別此子集，請仔細查看其中一項，並檢查其餘部分的差異，但不會遺漏任何唯一的資訊，只是只花一段時間，只需要讓他們讀取所有檔封面以供封面。 接近重複偵測可群組的類似檔，以協助您更有效率地進行審閱程式。

## <a name="how-does-it-work"></a>它的運作方式為何？

當執行接近重複偵測時，系統會分析每個具有文字的檔。 然後，它會比較每個檔，以判斷其相似性是否大於設定的臨界值。 如果是，則會將檔群組在一起。 完成所有檔的比較和群組之後，每個群組中的檔會標示為 "pivot";在 [檢查您的檔] 中，您可以先複查樞紐分析表，並以相同的接近重複集合查看其他檔，並著重于正在審閱中的資料透視與檔之間的差異。
