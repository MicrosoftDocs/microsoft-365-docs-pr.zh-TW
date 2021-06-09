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
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="18840-103">Advanced eDiscovery 接近重複偵測</span><span class="sxs-lookup"><span data-stu-id="18840-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="18840-104">請考慮一組要檢查的檔，其中的子集是以相同的範本為基礎，而且基本上是相同的樣板語言，但這裡有一些差異。</span><span class="sxs-lookup"><span data-stu-id="18840-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="18840-105">如果檢閱者可以識別此子集，請仔細查看其中一項，並檢查其餘部分的差異，但不會遺漏任何唯一的資訊，只是只花一段時間，只需要讓他們讀取所有檔封面以供封面。</span><span class="sxs-lookup"><span data-stu-id="18840-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="18840-106">近似重複項偵測會將文字類似的文件分組在一起，以協助您提升檢閱程序的效率。</span><span class="sxs-lookup"><span data-stu-id="18840-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="18840-107">它如何運作？</span><span class="sxs-lookup"><span data-stu-id="18840-107">How does it work?</span></span>

<span data-ttu-id="18840-108">在執行近似重複項偵測時，系統會剖析每份有文字的文件。</span><span class="sxs-lookup"><span data-stu-id="18840-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="18840-109">然後將每份文件兩兩比較，以判斷其相似性是否大於所設定的閾值。</span><span class="sxs-lookup"><span data-stu-id="18840-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="18840-110">如果是，便會將這些文件分組在一起。</span><span class="sxs-lookup"><span data-stu-id="18840-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="18840-111">比較完所有文件並加以分組後，每個群組的文件會標示為「樞紐」；在檢閱您的文件時，您可以先檢閱樞紐，並檢閱相同近似重複項集合中的其他文件，重點則放在樞紐與受檢閱文件的差異。</span><span class="sxs-lookup"><span data-stu-id="18840-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
