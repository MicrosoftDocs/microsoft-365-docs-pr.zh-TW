---
title: 主題-eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在 Advanced eDiscovery 中使用主題，以在每個檔中尋找主要主題來組織審閱集。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285529"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="35358-103">Advanced eDiscovery 中的主題</span><span class="sxs-lookup"><span data-stu-id="35358-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="35358-104">個人如何撰寫檔？</span><span class="sxs-lookup"><span data-stu-id="35358-104">How does a person write a document?</span></span> <span data-ttu-id="35358-105">他們通常會從一或多個想要在檔中傳遞的觀點開始，並使用與創意相符的文字加以撰寫。</span><span class="sxs-lookup"><span data-stu-id="35358-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="35358-106">構思的流行越多，與該觀點相關的文字越常見。</span><span class="sxs-lookup"><span data-stu-id="35358-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="35358-107">這會告訴人們也會如何使用檔。</span><span class="sxs-lookup"><span data-stu-id="35358-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="35358-108">從閱讀檔中瞭解的重要一點是檔嘗試傳遞的想法、哪些創意會出現在何處，以及構思之間的關係。</span><span class="sxs-lookup"><span data-stu-id="35358-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="35358-109">這可以擴充為使用者想要使用一組檔的方式。</span><span class="sxs-lookup"><span data-stu-id="35358-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="35358-110">他們想要查看哪些構思會出現在集合中，以及哪些檔正在談論這些觀點。</span><span class="sxs-lookup"><span data-stu-id="35358-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="35358-111">此外，如果他們找到感興趣的特定檔，他們想要看到討論類似創意的檔。</span><span class="sxs-lookup"><span data-stu-id="35358-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="35358-112">Advanced eDiscovery 中的 themes 功能會嘗試模仿有關檔的使用方式，方法是分析審閱集中所討論的 *主題*，並為審閱集中的檔指派主題。</span><span class="sxs-lookup"><span data-stu-id="35358-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="35358-113">在 Advanced eDiscovery 中，Themes 會進一步執行一個步驟，並識別每個檔中的 *主要主題*。</span><span class="sxs-lookup"><span data-stu-id="35358-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="35358-114">主要主題是顯示在檔中的最常用主題。</span><span class="sxs-lookup"><span data-stu-id="35358-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="35358-115">主題如何運作？</span><span class="sxs-lookup"><span data-stu-id="35358-115">How does Themes work?</span></span>

<span data-ttu-id="35358-116">主題功能會分析檢閱集內具有文字的文件，以剖析檢閱集內所有文件都有出現的共通主題。</span><span class="sxs-lookup"><span data-stu-id="35358-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="35358-117">進階電子文件探索會對出現這些主題的文件指派這些主題。</span><span class="sxs-lookup"><span data-stu-id="35358-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="35358-118">其也會使用文件中用來代表主題的字詞來標記每個主題。</span><span class="sxs-lookup"><span data-stu-id="35358-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="35358-119">由於文件可以包含不同類型的主題，因此進階電子文件探索往往會對文件指派多個主題。</span><span class="sxs-lookup"><span data-stu-id="35358-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="35358-120">系統會將文件中最常出現的主題指定為其主要主題。</span><span class="sxs-lookup"><span data-stu-id="35358-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
