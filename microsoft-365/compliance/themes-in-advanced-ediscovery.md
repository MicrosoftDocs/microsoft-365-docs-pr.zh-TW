---
title: 主題-eDiscovery
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
description: 在 [高級 eDiscovery] 中使用主題來組織每個檔中的主要主題，以組織複查集。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: eb008e091cd8c8330d1cdd5b388e252af70922da
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034517"
---
# <a name="themes"></a><span data-ttu-id="5f018-103">佈景主題</span><span class="sxs-lookup"><span data-stu-id="5f018-103">Themes</span></span>

<span data-ttu-id="5f018-104">個人如何撰寫檔？</span><span class="sxs-lookup"><span data-stu-id="5f018-104">How does a person write a document?</span></span> <span data-ttu-id="5f018-105">他們通常會從一或多個想要在檔中傳遞的觀點開始，並使用與創意相符的文字加以撰寫。</span><span class="sxs-lookup"><span data-stu-id="5f018-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="5f018-106">構思的流行越多，與該觀點相關的文字越常見。</span><span class="sxs-lookup"><span data-stu-id="5f018-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="5f018-107">這會告訴人們也會如何使用檔。</span><span class="sxs-lookup"><span data-stu-id="5f018-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="5f018-108">從閱讀檔中瞭解的重要一點是檔嘗試傳遞的想法、哪些創意會出現在何處，以及構思之間的關係。</span><span class="sxs-lookup"><span data-stu-id="5f018-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="5f018-109">這可以擴充為使用者想要使用一組檔的方式。</span><span class="sxs-lookup"><span data-stu-id="5f018-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="5f018-110">他們想要查看哪些構思會出現在集合中，以及哪些檔正在談論這些觀點。</span><span class="sxs-lookup"><span data-stu-id="5f018-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="5f018-111">此外，如果他們找到感興趣的特定檔，他們想要看到討論類似創意的檔。</span><span class="sxs-lookup"><span data-stu-id="5f018-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="5f018-112">「高級 eDiscovery」中的主題功能會嘗試透過分析審閱集中所討論的*主題*，並為審閱集中的檔指派主題，以模仿有關檔的原因。</span><span class="sxs-lookup"><span data-stu-id="5f018-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="5f018-113">在 [Advanced eDiscovery] 中，主題會進一步執行一個步驟，並識別每個檔中的*主要主題*。</span><span class="sxs-lookup"><span data-stu-id="5f018-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="5f018-114">主要主題是顯示在檔中的最常用主題。</span><span class="sxs-lookup"><span data-stu-id="5f018-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="5f018-115">主題如何運作？</span><span class="sxs-lookup"><span data-stu-id="5f018-115">How does Themes work?</span></span>

<span data-ttu-id="5f018-116">Themes 功能會分析具有審閱集中之文字的檔，以分析顯示在審閱集中所有檔的常見主題。</span><span class="sxs-lookup"><span data-stu-id="5f018-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="5f018-117">「高級 eDiscovery」會將這些主題指派給他們顯示的檔。</span><span class="sxs-lookup"><span data-stu-id="5f018-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="5f018-118">它也會以主題所代表檔中所用的字來標出每個主題。</span><span class="sxs-lookup"><span data-stu-id="5f018-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="5f018-119">因為檔可包含各種類型的主體，所以高級 eDiscovery 常常會為檔指派多個主題。</span><span class="sxs-lookup"><span data-stu-id="5f018-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="5f018-120">檔中顯示最醒目的主題是指定為其主要主題。</span><span class="sxs-lookup"><span data-stu-id="5f018-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
