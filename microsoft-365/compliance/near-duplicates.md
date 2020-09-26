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
description: 在管理資料調查時，請在分析資料調查中的證據時，使用接近的重複偵測，以分組類似的檔 (預覽) 。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ce968016e674ec83da536c65361d2075cf9bbb
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285949"
---
# <a name="near-duplicate-detection"></a>近似重複項偵測

請考慮一組要檢查的檔，其中的子集是以相同的範本為基礎，而且基本上是相同的樣板語言，但這裡有一些差異。 如果檢閱者可以識別此子集，請仔細查看其中一項，並檢查其餘部分的差異，但不會遺漏任何唯一的資訊，只是只花一段時間，只需要讓他們讀取所有檔封面以供封面。 接近重複偵測可群組的類似檔，以協助您更有效率地進行審閱程式。

## <a name="how-does-it-work"></a>它的運作方式為何？

當執行接近重複偵測時，系統會分析每個具有文字的檔。 然後，它會比較每個檔，以判斷其相似性是否大於設定的臨界值。 如果是，則會將檔群組在一起。 完成所有檔的比較和群組之後，每個群組中的檔會標示為 "pivot";在 [檢查您的檔] 中，您可以先複查樞紐分析表，並以相同的接近重複集合查看其他檔，並著重于正在審閱中的資料透視與檔之間的差異。
