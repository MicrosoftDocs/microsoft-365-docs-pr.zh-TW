---
title: 佈景主題
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078147"
---
# <a name="themes"></a><span data-ttu-id="f1770-102">佈景主題</span><span class="sxs-lookup"><span data-stu-id="f1770-102">Themes</span></span>
<span data-ttu-id="f1770-103">人員如何撰寫文件？</span><span class="sxs-lookup"><span data-stu-id="f1770-103">How does a person write a document?</span></span> <span data-ttu-id="f1770-104">它們通常他們想要傳達，文件中的一或多個想法的開頭，而撰寫使用想法與對齊的文字。</span><span class="sxs-lookup"><span data-stu-id="f1770-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="f1770-105">更普遍的作法是，更加頻繁地執行這個主意相關的字往往。</span><span class="sxs-lookup"><span data-stu-id="f1770-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="f1770-106">這會告知人員如何使用文件以及;若要從閱讀文件取得重要的是文件嘗試傳達，以及哪些想法出現的位置，想法和想法之間的關聯性為何。</span><span class="sxs-lookup"><span data-stu-id="f1770-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="f1770-107">這可以延伸至人員想要使用一組文件的方式。</span><span class="sxs-lookup"><span data-stu-id="f1770-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="f1770-108">他們想要看到設定中有哪些想法與這些概念的相關談的哪一個文件。</span><span class="sxs-lookup"><span data-stu-id="f1770-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="f1770-109">此外，如果發現感興趣的特定文件，他們想要能夠看到討論類似想法的文件。</span><span class="sxs-lookup"><span data-stu-id="f1770-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="f1770-110">佈景主題模組嘗試的模擬人類原因有關文件，來分析 」 佈景主題的 「 檢閱所討論的設定，並將它們指派給文件。</span><span class="sxs-lookup"><span data-stu-id="f1770-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="f1770-111">佈景主題進一步移一個步驟，並識別每個文件的 「 主控項佈景主題 」;亦即會出現最主題。</span><span class="sxs-lookup"><span data-stu-id="f1770-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="f1770-112">佈景主題的運作方式？</span><span class="sxs-lookup"><span data-stu-id="f1770-112">How does Themes work?</span></span>
<span data-ttu-id="f1770-113">佈景主題會分析文件檢閱設剖析出出現在文件的一般佈景主題中的文字。</span><span class="sxs-lookup"><span data-stu-id="f1770-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="f1770-114">然後，它將那些佈景主題指派給他們顯示的文件。</span><span class="sxs-lookup"><span data-stu-id="f1770-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="f1770-115">它也標籤各有使用中的佈景主題的代表配合文件的文字。</span><span class="sxs-lookup"><span data-stu-id="f1770-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="f1770-116">文件可以是多個主題專家的相關，因為在許多情況下，文件會有多個指派給它的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="f1770-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="f1770-117">最顯著出現在文件中的佈景主題會被指定為其主控項的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="f1770-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>