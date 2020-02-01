---
title: 佈景主題
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
ms.openlocfilehash: 4387c5e8fc199f0f8642041473d5f28f2f9b401b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601380"
---
# <a name="themes"></a><span data-ttu-id="25777-102">佈景主題</span><span class="sxs-lookup"><span data-stu-id="25777-102">Themes</span></span>

<span data-ttu-id="25777-103">人員如何撰寫文件？</span><span class="sxs-lookup"><span data-stu-id="25777-103">How does a person write a document?</span></span> <span data-ttu-id="25777-104">它們通常他們想要傳達，文件中的一或多個想法的開頭，而撰寫使用想法與對齊的文字。</span><span class="sxs-lookup"><span data-stu-id="25777-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="25777-105">更普遍的作法是，更加頻繁地執行這個主意相關的字往往。</span><span class="sxs-lookup"><span data-stu-id="25777-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="25777-106">這會告知人員如何使用以及文件。</span><span class="sxs-lookup"><span data-stu-id="25777-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="25777-107">若要了解從閱讀文件的重點是文件嘗試傳達，哪些想法出現的位置，以及它們想法之間的關聯性想法。</span><span class="sxs-lookup"><span data-stu-id="25777-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="25777-108">這可以延伸至人員想要使用一組文件的方式。</span><span class="sxs-lookup"><span data-stu-id="25777-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="25777-109">他們想要看到設定中有哪些想法與這些概念的相關談的哪一個文件。</span><span class="sxs-lookup"><span data-stu-id="25777-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="25777-110">此外，如果發現感興趣的特定文件，他們想要能夠看到討論類似想法的文件。</span><span class="sxs-lookup"><span data-stu-id="25777-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="25777-111">進階電子文件中的佈景主題功能會嘗試模仿人類原因的相關文件，藉由分析*佈景主題*所討論的檢閱如何設定和指派給檢閱組中的文件的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="25777-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="25777-112">在 [進階電子文件，佈景主題進一步移一個步驟，並識別每個文件*主控項的佈景主題*。</span><span class="sxs-lookup"><span data-stu-id="25777-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="25777-113">主控項的佈景主題是最常出現在文件中。</span><span class="sxs-lookup"><span data-stu-id="25777-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="25777-114">佈景主題的運作方式？</span><span class="sxs-lookup"><span data-stu-id="25777-114">How does Themes work?</span></span>

<span data-ttu-id="25777-115">佈景主題功能會分析文件檢閱設剖析出常見出現檢閱組中的所有文件的佈景主題中的文字。</span><span class="sxs-lookup"><span data-stu-id="25777-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="25777-116">進階電子文件會將這些佈景主題指派給他們顯示的文件。</span><span class="sxs-lookup"><span data-stu-id="25777-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="25777-117">它也會與使用中的佈景主題的代表配合文件的文字標籤每個佈景主題。</span><span class="sxs-lookup"><span data-stu-id="25777-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="25777-118">因為文件可以包含各種類型的主題，進階電子文件通常會多個主題指派給文件。</span><span class="sxs-lookup"><span data-stu-id="25777-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="25777-119">最顯著出現在文件中的佈景主題會被指定為其主控項的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="25777-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>