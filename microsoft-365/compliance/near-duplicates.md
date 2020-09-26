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
# <a name="near-duplicate-detection"></a><span data-ttu-id="b43c8-103">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="b43c8-103">Near duplicate detection</span></span>

<span data-ttu-id="b43c8-104">請考慮一組要檢查的檔，其中的子集是以相同的範本為基礎，而且基本上是相同的樣板語言，但這裡有一些差異。</span><span class="sxs-lookup"><span data-stu-id="b43c8-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="b43c8-105">如果檢閱者可以識別此子集，請仔細查看其中一項，並檢查其餘部分的差異，但不會遺漏任何唯一的資訊，只是只花一段時間，只需要讓他們讀取所有檔封面以供封面。</span><span class="sxs-lookup"><span data-stu-id="b43c8-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="b43c8-106">接近重複偵測可群組的類似檔，以協助您更有效率地進行審閱程式。</span><span class="sxs-lookup"><span data-stu-id="b43c8-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="b43c8-107">它的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="b43c8-107">How does it work?</span></span>

<span data-ttu-id="b43c8-108">當執行接近重複偵測時，系統會分析每個具有文字的檔。</span><span class="sxs-lookup"><span data-stu-id="b43c8-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="b43c8-109">然後，它會比較每個檔，以判斷其相似性是否大於設定的臨界值。</span><span class="sxs-lookup"><span data-stu-id="b43c8-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="b43c8-110">如果是，則會將檔群組在一起。</span><span class="sxs-lookup"><span data-stu-id="b43c8-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="b43c8-111">完成所有檔的比較和群組之後，每個群組中的檔會標示為 "pivot";在 [檢查您的檔] 中，您可以先複查樞紐分析表，並以相同的接近重複集合查看其他檔，並著重于正在審閱中的資料透視與檔之間的差異。</span><span class="sxs-lookup"><span data-stu-id="b43c8-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
