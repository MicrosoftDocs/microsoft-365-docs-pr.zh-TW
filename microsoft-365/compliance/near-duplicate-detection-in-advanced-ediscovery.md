---
title: 接近重複偵測-eDiscovery
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
description: 在 Advanced eDiscovery 中分析案例資料時，使用接近的重複偵測，以群組的類似檔進行群組。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286019"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Advanced eDiscovery 接近重複偵測

請考慮一組要檢查的檔，其中的子集是以相同的範本為基礎，而且基本上是相同的樣板語言，但這裡有一些差異。 如果檢閱者可以識別此子集，請仔細查看其中一項，並檢查其餘部分的差異，但不會遺漏任何唯一的資訊，只是只花一段時間，只需要讓他們讀取所有檔封面以供封面。 近似重複項偵測會將文字類似的文件分組在一起，以協助您提升檢閱程序的效率。

## <a name="how-does-it-work"></a>它如何運作？

在執行近似重複項偵測時，系統會剖析每份有文字的文件。 然後將每份文件兩兩比較，以判斷其相似性是否大於所設定的閾值。 如果是，便會將這些文件分組在一起。 比較完所有文件並加以分組後，每個群組的文件會標示為「樞紐」；在檢閱您的文件時，您可以先檢閱樞紐，並檢閱相同近似重複項集合中的其他文件，重點則放在樞紐與受檢閱文件的差異。
