---
title: " (預覽的知識管理概述) "
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Project Cortex 中瞭解知識管理。
ms.openlocfilehash: 27ce6457f2329ccaa4738d6868b4f2051c0c0a51
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988839"
---
# <a name="knowledge-management-overview-preview"></a><span data-ttu-id="d928a-103"> (預覽的知識管理概述) </span><span class="sxs-lookup"><span data-stu-id="d928a-103">Knowledge management Overview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d928a-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="d928a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d928a-105">[如需詳細資訊，請參閱 Project Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="d928a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d928a-106">知識管理使用 Microsoft AI 技術、Microsoft 365、Delve、搜尋及其他元件和服務，在您的 Microsoft 365 環境中建立知識網路。</span><span class="sxs-lookup"><span data-stu-id="d928a-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![知識管理流程](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="d928a-108">其目標是將資訊傳送給使用者，讓他們在日常使用的應用程式中，例如，Outlook、小組和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="d928a-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="d928a-109">例如，使用者會在他們的電子郵件、SharePoint 網站或小組交談中看到不熟悉的字詞，他們想要深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="d928a-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="d928a-110">知識管理使用 AI 來自動搜尋及識別這些 **主題** ，並編譯其相關資訊，例如主題的簡短描述、主題專家、網站、檔案及與其相關的頁面。</span><span class="sxs-lookup"><span data-stu-id="d928a-110">Knowledge management uses AI to automatically searches for and identifies these **topics** , and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="d928a-111">您可以視需要選擇更新主題資訊。</span><span class="sxs-lookup"><span data-stu-id="d928a-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="d928a-112">然後您可以讓使用者使用這些主題，這表示針對 Outlook、小組和 SharePoint 等應用程式中顯示的每個主題實例，文字都會反白顯示。</span><span class="sxs-lookup"><span data-stu-id="d928a-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="d928a-113">使用者可選擇透過主題詳細資料深入瞭解主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-indexing"></a><span data-ttu-id="d928a-114">主題索引</span><span class="sxs-lookup"><span data-stu-id="d928a-114">Topic indexing</span></span>

<span data-ttu-id="d928a-115">知識管理使用 Microsoft AI 技術來識別 Office 365 環境中的 **主題** 。</span><span class="sxs-lookup"><span data-stu-id="d928a-115">Knowledge Management uses Microsoft AI technology to identify **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="d928a-116">主題是一種組織很重要或很重要的片語或字詞。</span><span class="sxs-lookup"><span data-stu-id="d928a-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="d928a-117">組織中有特定的意義，也有相關的資源可協助人員瞭解其內容及找到相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d928a-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="d928a-118">識別主題時，會為其建立 **主題頁面** ，其中包含透過主題編制索引所收集的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="d928a-118">When a topic is identified, a **topic page** is created for it that contains information that was gathered through topic indexing, such as:</span></span>

- <span data-ttu-id="d928a-119">替代名稱和/或縮寫。</span><span class="sxs-lookup"><span data-stu-id="d928a-119">Alternate names and/or acronyms.</span></span>
- <span data-ttu-id="d928a-120">主題的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="d928a-120">A short description of the topic.</span></span>
- <span data-ttu-id="d928a-121">熟悉主題的使用者。</span><span class="sxs-lookup"><span data-stu-id="d928a-121">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="d928a-122">與主題相關的檔案、頁面和網站。</span><span class="sxs-lookup"><span data-stu-id="d928a-122">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="d928a-123">主題探索</span><span class="sxs-lookup"><span data-stu-id="d928a-123">Topic discovery</span></span>
<span data-ttu-id="d928a-124">在 SharePoint 新聞及頁面的內容中提及主題時，您會看到該主題為反白顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="d928a-124">When a topic is mentioned in content on SharePoint news and pages, you'll see it highlighted.</span></span> <span data-ttu-id="d928a-125">從醒目提示中開啟主題摘要。</span><span class="sxs-lookup"><span data-stu-id="d928a-125">Open the topic summary from the highlight.</span></span> <span data-ttu-id="d928a-126">從摘要的標題開啟主題詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d928a-126">Open the topic details from the title of the summary.</span></span> <!--(msg for Efren: not sure if I should use discovery for this; we use discovered in-product for indexing?)--> <span data-ttu-id="d928a-127">您可以自動識別上述主題，也可以使用頁面作者直接參考主題，將其新增至頁面。</span><span class="sxs-lookup"><span data-stu-id="d928a-127">The mentioned topic could be identified automatically or have been added to the page with a direct reference to the topic by the page author.</span></span>

<span data-ttu-id="d928a-128">您也可以透過 Microsoft 搜尋探索主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-128">You can also discover topics through Microsoft Search.</span></span>


## <a name="topic-management"></a><span data-ttu-id="d928a-129">主題管理</span><span class="sxs-lookup"><span data-stu-id="d928a-129">Topic management</span></span>

<span data-ttu-id="d928a-130">主題管理是在您組織的 **主題中心** 完成。</span><span class="sxs-lookup"><span data-stu-id="d928a-130">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="d928a-131">主題中心網站會在安裝期間建立，並作為您組織的知識中心。</span><span class="sxs-lookup"><span data-stu-id="d928a-131">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="d928a-132">它會包含您環境中已發現的所有主題清單，以及這些主題所建立的所有主題頁面。</span><span class="sxs-lookup"><span data-stu-id="d928a-132">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="d928a-133">提供正確許可權的使用者將可以在主題中心執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d928a-133">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="d928a-134">確認或拒絕您租使用者中探索的主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-134">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="d928a-135">在需要時手動建立新的主題 (例如，如果沒有提供足夠的資訊供透過 AI) 探索。</span><span class="sxs-lookup"><span data-stu-id="d928a-135">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="d928a-136">編輯現有的主題頁面。</span><span class="sxs-lookup"><span data-stu-id="d928a-136">Edit existing topic pages.</span></span></br>

<span data-ttu-id="d928a-137">如需詳細資訊，請參閱 [主題中央的使用主題](work-with-topics.md) 。</span><span class="sxs-lookup"><span data-stu-id="d928a-137">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="d928a-138">系統管理控制</span><span class="sxs-lookup"><span data-stu-id="d928a-138">Admin controls</span></span>

<span data-ttu-id="d928a-139">Microsoft 365 系統管理中心中的管理控制可讓您管理您的知識網路。</span><span class="sxs-lookup"><span data-stu-id="d928a-139">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="d928a-140">它們允許 Microsoft 365 全域或 SharePoint 管理員：</span><span class="sxs-lookup"><span data-stu-id="d928a-140">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="d928a-141">控制組織中的哪些使用者可以查看其用戶端應用程式中或 SharePoint 搜尋結果中的主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-141">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="d928a-142">控制將編目哪個 SharePoint 網站來搜尋主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-142">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="d928a-143">將主題探索設定為排除您不想要成為主題的特定字詞。</span><span class="sxs-lookup"><span data-stu-id="d928a-143">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="d928a-144">控制哪些使用者可以確認或拒絕主題中心中的主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-144">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="d928a-145">控制哪些使用者可以在主題中心建立及編輯主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-145">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="d928a-146">請參閱 [管理您的知識網路](topic-experiences-discovery.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d928a-146">See [Manage your knowledge network](topic-experiences-discovery.md) for more information.</span></span> 

## <a name="topic-curation--feedback"></a><span data-ttu-id="d928a-147">主題 curation & 意見反應</span><span class="sxs-lookup"><span data-stu-id="d928a-147">Topic curation & feedback</span></span>

<span data-ttu-id="d928a-148">AI 會持續運作，提供您在環境中發生變更時改進主題的建議。</span><span class="sxs-lookup"><span data-stu-id="d928a-148">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="d928a-149">允許存取權在日常工作中查看主題的使用者，可提供建議以加以改善。</span><span class="sxs-lookup"><span data-stu-id="d928a-149">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="d928a-150">例如，如果使用者查看 [主題] 頁面，並看到不正確或需要新增的資訊，[主題] 頁面上的連結可讓他們直接編輯資訊。</span><span class="sxs-lookup"><span data-stu-id="d928a-150">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to edit the information directly.</span></span> <span data-ttu-id="d928a-151">另一個範例是，如果使用者在 SharePoint 新聞] 頁面上查看醒目提示，您會發現問題，詢問您是否有適當的醒目提示或建議的主題是否適用于您的組織。</span><span class="sxs-lookup"><span data-stu-id="d928a-151">Another example, if a user views a a highlight on a SharePoint news page, you will find questions asking whether or not the highlight is appropriate or the suggested topic is appropriate for your organization.</span></span> <span data-ttu-id="d928a-152">您的回答會協助決定主題摘要和主題詳細資料中顯示的內容。</span><span class="sxs-lookup"><span data-stu-id="d928a-152">Your answer will help determine what's shown on topic summaries and in topic details.</span></span>

<span data-ttu-id="d928a-153">此外，具有適當許可權的使用者可以將相關的 Yammer 交談等專案標記為相關專案，並將其新增至特定主題。</span><span class="sxs-lookup"><span data-stu-id="d928a-153">Additionally, users with proper permissions can tag items such as Yammer conversation that are relevant to a topic, and add them to a specific topic.</span></span> <!--(msg for Efren: changed to Yammer, because we will not have shipped Teams yet)-->


## <a name="see-also"></a><span data-ttu-id="d928a-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d928a-154">See also</span></span>
[<span data-ttu-id="d928a-155">設定知識管理</span><span class="sxs-lookup"><span data-stu-id="d928a-155">Set up knowledge management</span></span>](set-up-topic-experiences.md)</br>
[<span data-ttu-id="d928a-156">主題中心概述</span><span class="sxs-lookup"><span data-stu-id="d928a-156">Topic center overview</span></span>](topic-center-overview.md)
