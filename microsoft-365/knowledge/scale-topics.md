---
title: 在 Microsoft Viva 主題中管理縮放主題
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: 深入瞭解使用 Viva 主題管理組織中的許多主題的最佳作法。
ms.openlocfilehash: 613c4ed85a62efd22ba104c810420a2d0af015c5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624834"
---
# <a name="manage-topics-at-scale-in-microsoft-viva-topics"></a><span data-ttu-id="bec25-103">在 Microsoft Viva 主題中管理縮放主題</span><span class="sxs-lookup"><span data-stu-id="bec25-103">Manage topics at scale in Microsoft Viva Topics</span></span>

<span data-ttu-id="bec25-104">當您為 SharePoint 網站或整個組織編制 Viva 主題的索引時，可能會產生許多主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-104">When you index your SharePoint sites or your entire organization for Viva Topics, many topics might be generated.</span></span> <span data-ttu-id="bec25-105">發生這種情況時，您會在 [ **管理主題** ] 頁面上看到數以千計的建議主題，知道從何處開始會很困難。</span><span class="sxs-lookup"><span data-stu-id="bec25-105">When this happens and you see thousands of suggested topics on the **Manage topics** page, it can be challenging to know where to start.</span></span> <span data-ttu-id="bec25-106">本文說明 Viva 主題如何協助您優化對搜尋資訊的使用者顯示哪些主題和資訊，甚至在具有大量主題的大型組織中。</span><span class="sxs-lookup"><span data-stu-id="bec25-106">This article describes how Viva Topics helps you optimize which topics and information are shown to users who are searching for information, even in large organizations with large numbers of topics.</span></span>

<span data-ttu-id="bec25-107">首先，會提醒您 [主題的四個階段](manage-topics.md#topic-stages)：</span><span class="sxs-lookup"><span data-stu-id="bec25-107">First, a reminder of the [four stages for topics](manage-topics.md#topic-stages):</span></span>

- <span data-ttu-id="bec25-108">**建議**：AI 已識別主題，並且有足夠的支援資源、關聯和屬性。</span><span class="sxs-lookup"><span data-stu-id="bec25-108">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="bec25-109"> (這些會標示為 UI 中的 **建議主題** 。 ) </span><span class="sxs-lookup"><span data-stu-id="bec25-109">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="bec25-110">已 **確認**：已透過 AI 探索並已驗證的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-110">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="bec25-111">主題驗證會在下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bec25-111">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="bec25-112">知識管理員會確認主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-112">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="bec25-113">知識管理員會在 [**管理主題**] 頁面上 [確認主題](manage-topics.md#confirmed-topics)。</span><span class="sxs-lookup"><span data-stu-id="bec25-113">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="bec25-114">多位使用者確認主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-114">Multiple users confirm a topic.</span></span> <span data-ttu-id="bec25-115">您必須從使用主題卡片上的意見反應機制來投票的使用者，收到兩封正投票的網路。</span><span class="sxs-lookup"><span data-stu-id="bec25-115">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="bec25-116">例如，如果一個使用者投票肯定的正負一個使用者的投票為負值，您仍需要兩個正值投票才能確認該主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-116">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="bec25-117">已 **發佈**：已策劃的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-117">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="bec25-118">手動編輯是為了改善其品質，或是由使用者建立。</span><span class="sxs-lookup"><span data-stu-id="bec25-118">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="bec25-119">**已移除**：已遭拒絕的主題，將不再對檢視器顯示。</span><span class="sxs-lookup"><span data-stu-id="bec25-119">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="bec25-120">您可以在任何狀態中移除主題 (建議、確認或發佈的) 。</span><span class="sxs-lookup"><span data-stu-id="bec25-120">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="bec25-121">移除主題時，會發生下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bec25-121">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="bec25-122">知識管理員會移除一個主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-122">A knowledge manager removes a topic.</span></span> <span data-ttu-id="bec25-123">知識管理員會移除 [ **管理主題** ] 頁面上的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-123">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="bec25-124">多個使用者使用主題卡片上的意見反應機制來強制轉換負值投票。</span><span class="sxs-lookup"><span data-stu-id="bec25-124">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="bec25-125">若要移除的主題，必須從使用者收到兩個否定投票的淨值。</span><span class="sxs-lookup"><span data-stu-id="bec25-125">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="bec25-126">例如，如果一個使用者投票了負數，另一個使用者對某特定主題投票了肯定的，則您仍然需要兩個負的投票來移除該主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-126">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="bec25-127">移除已發佈的主題時，將需要透過主題中心的頁面庫手動刪除策劃詳細資料的頁面。</span><span class="sxs-lookup"><span data-stu-id="bec25-127">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

## <a name="knowledge-manager-role"></a><span data-ttu-id="bec25-128">知識管理員角色</span><span class="sxs-lookup"><span data-stu-id="bec25-128">Knowledge manager role</span></span> 

<span data-ttu-id="bec25-129">當您設定 Viva 主題時，您將會新增一組使用者，他會授與許可權，以查看主題中心中的 [ **管理主題** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bec25-129">When you configure Viva Topics, you'll add a group of users who are granted permissions to see the **Manage topics** page in the topic center.</span></span> <span data-ttu-id="bec25-130">它只會針對保留主題主要 curation 角色的使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="bec25-130">It will appear only for these users who hold the role of primary curation for the topics.</span></span> <span data-ttu-id="bec25-131">他們將可以存取主題的資料，並可以查看他們具有「審閱」和「curate」許可權的所有主題清單。</span><span class="sxs-lookup"><span data-stu-id="bec25-131">They'll have access to data about the topics and will be able to see lists of all topics that they have access to review and curate.</span></span>

<span data-ttu-id="bec25-132">此角色中的員工應具備廣泛的許可權，可讓您查看大量主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-132">Employees in this role should have broad permissions to view a wide array of topics.</span></span> <span data-ttu-id="bec25-133">或者，如果會分割許可權，您可能會想要選取一組使用者，這些使用者代表公司的不同區域，而且可以 curate 其專屬區域。</span><span class="sxs-lookup"><span data-stu-id="bec25-133">Or if permissions are segmented, you might want to select a group of users that represent different areas of the business and can curate for their own areas.</span></span>

<span data-ttu-id="bec25-134">當您第一次查看主題中心的主題時，建議的主題是純粹的 AI 定義。</span><span class="sxs-lookup"><span data-stu-id="bec25-134">When you first review topics in the topic center, suggested topics are purely AI-defined.</span></span> <span data-ttu-id="bec25-135">知識管理員可能會在將 Viva 主題推廣至廣泛的使用者群組之前，先複習每一位。</span><span class="sxs-lookup"><span data-stu-id="bec25-135">Knowledge managers might want to review each one before rolling out Viva Topics to a broad user community.</span></span> <span data-ttu-id="bec25-136">在調整規模時，此方法很少因數以千計的主題而很實用。</span><span class="sxs-lookup"><span data-stu-id="bec25-136">When working at scale, this approach is rarely a practical because of the thousands of topics.</span></span>

<span data-ttu-id="bec25-137">建議的方法是，針對您的初始使用者集合，尋找最相關或最重要的主題，並在 Viva 主題的首展之前，curation 這些主題的重點。</span><span class="sxs-lookup"><span data-stu-id="bec25-137">The recommended approach is to find a balance of the most pertinent or important topics for your initial set of users and focus on curation of those topics before rollout of Viva Topics.</span></span> <span data-ttu-id="bec25-138">開始收集使用者的意見，並允許 crowdsourcing 判斷您的使用者使用方式和貢獻模式，以通知本文中建議的策略。</span><span class="sxs-lookup"><span data-stu-id="bec25-138">Begin to collect feedback from the users and allow crowdsourcing to determine the usage and contribution patterns of your users to inform the strategies suggested in this article.</span></span>

<span data-ttu-id="bec25-139">請務必承認，系統會將 AI 建議和人工策劃的已發佈主題，都識別及顯示給所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bec25-139">It's important to recognize that the system will identify and show both AI-suggested and human-curated published topics to all users.</span></span> <span data-ttu-id="bec25-140">不過，這並不表示每個建議的主題都會顯示給所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="bec25-140">However, this doesn't mean that every suggested topic will be shown to all end users.</span></span> <span data-ttu-id="bec25-141">「安全性設定就地」只會顯示每個員工根據內容本身所設定的許可權所能存取的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-141">The security settings in place will show only the topics that each employee can access based on the permissions that are set on the content itself.</span></span>

<span data-ttu-id="bec25-142">如具備查看「 **管理主題** 」頁面許可權的知識管理員，您可能會看到所列的主題數目超過您的組織和存取層級中的角色。</span><span class="sxs-lookup"><span data-stu-id="bec25-142">As a knowledge manager with permissions to view the **Manage topics** page, you might see a much larger number of topics listed because of your own elevated permissions, depending on your role in the organization and level of access.</span></span> <span data-ttu-id="bec25-143">您也可以存取可讓您查看單一地點所列主題的視圖，而不是使用醒目或搜尋來存取。</span><span class="sxs-lookup"><span data-stu-id="bec25-143">You'll also have access to views that allow you see topics listed in a single location rather than accessing them by using highlights or search.</span></span>

<span data-ttu-id="bec25-144">此外，大部分的使用者可能會看到較小的主題比例，以及更少因許可權所看到的更多主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-144">In addition, there is likely a smaller percentage of topics that will be viewed by most users and a larger set of more topics that will be seen much less frequently due to permissions.</span></span> <span data-ttu-id="bec25-145">因此，請先將任何 curation 的工作重點放在組織中最重要的主題上，並最有可能看到的更廣泛的任務。</span><span class="sxs-lookup"><span data-stu-id="bec25-145">As a result, it is good to first focus any curation tasks on the topics that are the most important for your organization and that are the most likely to be seen more broadly.</span></span>

<span data-ttu-id="bec25-146">本文涵蓋 curation 的幾個策略。</span><span class="sxs-lookup"><span data-stu-id="bec25-146">This article covers a few strategies for curation.</span></span> <span data-ttu-id="bec25-147">這些策略可能意味著知識管理員不會完全策劃較少或較少的常見主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-147">These strategies might mean that the less frequent or less common topics might not be fully curated by knowledge managers.</span></span> <span data-ttu-id="bec25-148">不過，這些建議的主題仍然有用，可提供人員的洞察力或指標，可節省員工時尋找開始點的時間。</span><span class="sxs-lookup"><span data-stu-id="bec25-148">However, these suggested topics remain useful and can provide insight or a pointer to a person, which can save an employee hours of looking for a starting point.</span></span> <span data-ttu-id="bec25-149">允許 crowdsourced 更新主題是有益的，並且提供更多內容和範圍，以提供更少的常見主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-149">Allowing crowdsourced updates to topics is beneficial and provides more content and coverage for the less common topics.</span></span>

<span data-ttu-id="bec25-150">本文提供一些指導方針和最佳作法，以供您習慣于管理和 curation 主題的方法。</span><span class="sxs-lookup"><span data-stu-id="bec25-150">This article provides some guidance and best practices to approach topic management and curation.</span></span>

## <a name="understanding-suggested-topics"></a><span data-ttu-id="bec25-151">瞭解建議的主題</span><span class="sxs-lookup"><span data-stu-id="bec25-151">Understanding suggested topics</span></span>

<span data-ttu-id="bec25-152">透過 AI 探索主題時，這些主題會在 [**管理主題**] 頁面上，以及呈現給使用者的主題卡片中標示為 **建議主題**。</span><span class="sxs-lookup"><span data-stu-id="bec25-152">When topics are discovered by AI, they're marked as a **Suggested Topic**, both on the **Manage topics** page, and in the topic cards that are presented to users.</span></span> <span data-ttu-id="bec25-153">任何尚未標示為已移除的主題都會向使用者顯示，包括已確認、已發佈和建議的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-153">Any topic that hasn't been marked as removed will be shown to users—this includes confirmed, published, and suggested topics.</span></span> <span data-ttu-id="bec25-154">使用者可以使用所有三種狀態的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-154">Topics in all three states are available to end users.</span></span>

<span data-ttu-id="bec25-155">在主題卡片或頁面中，我們會使用各種提示來顯示 AI 產生資訊的方式。</span><span class="sxs-lookup"><span data-stu-id="bec25-155">Within a topic card or page, we use various cues to show how the AI has generated the information.</span></span> <span data-ttu-id="bec25-156">系統會使用各種證據，以新增資源，主要是透過內容本身。</span><span class="sxs-lookup"><span data-stu-id="bec25-156">The system uses a variety of evidence to add the resources, primarily through the content itself.</span></span>

- <span data-ttu-id="bec25-157">[標籤] 顯示主題是建議的主題，並由 Viva 主題所探索。</span><span class="sxs-lookup"><span data-stu-id="bec25-157">Labels show that a topic is suggested and that it was discovered by Viva Topics.</span></span>  

   ![顯示建議主題的範例卡片，包含建議人員和建議資源。](../media/knowledge-management/scale-topics-sample-card-suggested-topic.png)

- <span data-ttu-id="bec25-159">透過指定其來源，以瞭解定義來自哪些卡的資訊。</span><span class="sxs-lookup"><span data-stu-id="bec25-159">Information on the card states where a definition has come from by specifying its source.</span></span>

- <span data-ttu-id="bec25-160">建議人員會透過使用主題證據來匯總已寫入或編輯檔的人員來衍生。</span><span class="sxs-lookup"><span data-stu-id="bec25-160">Suggested people are derived by aggregating people who have written or edited documents with topic evidence.</span></span> <span data-ttu-id="bec25-161">如果人員撰寫的檔具有標題中的主題名稱，而且該檔有許多視圖，可能只需要一個檔才能建立相關的人員。</span><span class="sxs-lookup"><span data-stu-id="bec25-161">If a person writes a document that has a topic name in the title, and that document has many views, it might only require one document to establish the person as related.</span></span> <span data-ttu-id="bec25-162">不過，在許多情況下，較多的證據越好，列出的人員就能處理多份檔。</span><span class="sxs-lookup"><span data-stu-id="bec25-162">However, in many cases more evidence is better, and people who are listed have worked on multiple documents.</span></span>  

   ![顯示建議主題的頁面，包含建議的人員、檔案及頁面。](../media/knowledge-management/scale-topics-sample-page-suggested-topic.png)

- <span data-ttu-id="bec25-164">針對所顯示的檔案及頁面，系統會識別檔中提及主題的次數，但在特定的內容中也必須提及該主題，以識別對特定類型 (例如專案或小組) 相關主題的參照。</span><span class="sxs-lookup"><span data-stu-id="bec25-164">For the files and pages shown, the system identifies how many times the topic has been mentioned in the document, but the topic also must be mentioned in a specific context that identifies the reference to the topic of specific type (such as project or team).</span></span> <span data-ttu-id="bec25-165">這是 AI 的證據的計數。</span><span class="sxs-lookup"><span data-stu-id="bec25-165">This is what counts as evidence for the AI.</span></span> <span data-ttu-id="bec25-166">系統也會考慮主題名稱出現在檔、檔案類型及其他分析功能 (例如 [視圖]) 中的標題。</span><span class="sxs-lookup"><span data-stu-id="bec25-166">The system also considers the occurrence of a topic name in the titles of documents, types of documents, and other analytics features (such as views).</span></span>

   ![橫幅的影像，其為建議主題，而 Microsoft Viva 發現本主題。](../media/knowledge-management/scale-topics-suggested-you-have-access.png)

   ![橫幅的影像，如建議主題及編輯此頁面，以描述您在本主題中的參與。](../media/knowledge-management/scale-topics-suggested-describe-your-involvement.png)

   ![橫幅的影像，如建議主題及編輯此頁面（如果您可以新增與主題相連的人員）。](../media/knowledge-management/scale-topics-suggested-add-people.png)

<span data-ttu-id="bec25-170">這些屬性會示範 AI 已新增的內容，以及 AI 如何進行判斷。</span><span class="sxs-lookup"><span data-stu-id="bec25-170">These attributes demonstrate that the content has been added by AI, and how the AI has made that determination.</span></span>

### <a name="communication"></a><span data-ttu-id="bec25-171">通訊</span><span class="sxs-lookup"><span data-stu-id="bec25-171">Communication</span></span>

<span data-ttu-id="bec25-172">當您與使用者 Viva 主題的相關資訊時，請務必澄清 AI 建議主題和內容及其策劃對等專案之間的差異。</span><span class="sxs-lookup"><span data-stu-id="bec25-172">When communicating to your users about Viva Topics, it's important to clarify the difference between AI-suggested topics and content and their curated equivalents.</span></span>

<span data-ttu-id="bec25-173">做為讀者，您應該以更為重要的眼來查看建議的主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-173">As a reader, you should view suggested topics with a more critical eye.</span></span> <span data-ttu-id="bec25-174">它們不應視為組織真實的權威來源。</span><span class="sxs-lookup"><span data-stu-id="bec25-174">They shouldn't be perceived as authoritative sources of organizational truth.</span></span> <span data-ttu-id="bec25-175">相反地，他們是一種方法，用來存取透過您可以存取之內容所呈現的 tacit 知識。</span><span class="sxs-lookup"><span data-stu-id="bec25-175">Rather, they're a way-finding tool to access tacit knowledge that is presented through the content that you have access to.</span></span> <span data-ttu-id="bec25-176">AI 已發現主題，具有足夠的證據可向您顯示，但其值尚未由人員確認。</span><span class="sxs-lookup"><span data-stu-id="bec25-176">The AI has discovered the topic and has enough evidence to show it to you, but its value hasn't been confirmed by a person.</span></span>

### <a name="crowdsourced-controls"></a><span data-ttu-id="bec25-177">Crowdsourced 控制項</span><span class="sxs-lookup"><span data-stu-id="bec25-177">Crowdsourced controls</span></span>

<span data-ttu-id="bec25-178">建議的主題可以透過 curation 頁面，以及透過主題的 crowdsourced 意見來改進。</span><span class="sxs-lookup"><span data-stu-id="bec25-178">Suggested topics can be improved by curation of the page and through crowdsourced feedback on the topic.</span></span>

<span data-ttu-id="bec25-179">當使用者以建議的主題進行互動時，可能會在 UI 中要求他們一個簡單的問題。</span><span class="sxs-lookup"><span data-stu-id="bec25-179">When users interact with a suggested topic, they might be asked a simple question in the UI.</span></span> <span data-ttu-id="bec25-180">例如： *此主題與頁面有關嗎？*</span><span class="sxs-lookup"><span data-stu-id="bec25-180">For example: *Was this topic relevant to the page?*</span></span> <span data-ttu-id="bec25-181">*此人員是否與主題相關？*</span><span class="sxs-lookup"><span data-stu-id="bec25-181">*Is this person relevant for the topic?*</span></span> <span data-ttu-id="bec25-182">*這種定義是否正確？*</span><span class="sxs-lookup"><span data-stu-id="bec25-182">*Was this definition accurate?*</span></span> <span data-ttu-id="bec25-183">透過對這類問題的意見反應，主題的精確度可以增加，而不需要指定的個人 curate 頁面。</span><span class="sxs-lookup"><span data-stu-id="bec25-183">By using the feedback to such questions, the accuracy of the topics can increase without the need for a named individual to curate the page.</span></span>

<span data-ttu-id="bec25-184">「主題中心」的首頁是另一個位置，可供您收集建議主題的回饋。</span><span class="sxs-lookup"><span data-stu-id="bec25-184">The home page of a topic center is another location where feedback on suggested topics is gathered.</span></span> <span data-ttu-id="bec25-185">在主題中心，使用者可以查看與其相關聯的主題，並提供選擇以確認此關聯或已將其移除的選項。</span><span class="sxs-lookup"><span data-stu-id="bec25-185">In the topic center, a user can see the topics that they have been associated with and are given the option to either confirm this association or have it removed.</span></span>

   ![主題中心的範例顯示使用者的建議主題，以確認或移除與建議主題的連線。](../media/knowledge-management/scale-topics-topic-center-confirm-connections.png)

<span data-ttu-id="bec25-187">當您允許主題的廣泛 crowdsourcing 時，應考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="bec25-187">When you allow broad crowdsourcing of topics, you should consider the following factors:</span></span>

-   <span data-ttu-id="bec25-188">使用者會在主題頁面上看到 [**編輯**] 選項，而且可以像其他現代的 SharePoint 頁面一樣，編輯頁面。</span><span class="sxs-lookup"><span data-stu-id="bec25-188">Users will see the **Edit** option on topic pages and can edit the pages in the same experience as other modern SharePoint pages.</span></span>

-   <span data-ttu-id="bec25-189">有些 **建議的主題** 網頁元件無法移除。</span><span class="sxs-lookup"><span data-stu-id="bec25-189">Some **Suggested Topic** web parts can't be removed.</span></span> <span data-ttu-id="bec25-190">無法移除主題名稱、替代名稱、定義、建議人員和建議資源。</span><span class="sxs-lookup"><span data-stu-id="bec25-190">The topic name, alternate names, definition, suggested people, and suggested resources can't be removed.</span></span>

-   <span data-ttu-id="bec25-191">在 [**管理主題**] 頁面上已發佈為移至 [**已發佈**] 清單的建議或確認主題可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="bec25-191">It can take some time for a suggested or confirmed topic that has been published to be moved to the **Published** list on the **Manage topics** page.</span></span>

    -   <span data-ttu-id="bec25-192">主題出現在搜尋、高光、hashtags 或批註中的預估時間是2小時。</span><span class="sxs-lookup"><span data-stu-id="bec25-192">The estimated time for a topic to appear in search, highlights, hashtags, or annotations is 2 hours.</span></span>

    -   <span data-ttu-id="bec25-193">在大多數情況下，在 [**受管理的主題**] 頁面的 [**已發佈**] 清單中顯示主題的預估時間不會超過24小時。</span><span class="sxs-lookup"><span data-stu-id="bec25-193">The estimated time for a topic to appear in **Published** list on the **Managed topics** page is no more than 24 hours in most cases.</span></span> <span data-ttu-id="bec25-194">您應該會在2小時內看到它們，但由於每24小時有一次完整同步處理，因此不應超過24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="bec25-194">You should see them within 2 hours, but because there's a full sync every 24 hours, the wait shouldn't be longer than 24 hours.</span></span>

-   <span data-ttu-id="bec25-195">使用者可能會將發佈的主題保留為已檢出或編輯狀態。</span><span class="sxs-lookup"><span data-stu-id="bec25-195">It's possible that a user might leave a published topic in a checked-out or editing state.</span></span> <span data-ttu-id="bec25-196">知識管理員可以在主題中心的頁面庫中查看這些內容，也可以捨棄使用者的變更以重新發佈主題，或聯繫該使用者以要求他們檢查主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-196">A knowledge manager can see these in the Pages Library of the topic center and either can discard the user's changes to republish the topic or contact that user to request that they check in the topic.</span></span>

### <a name="topic-visibility-and-content-is-based-on-a-users-permissions"></a><span data-ttu-id="bec25-197">主題可見度和內容是以使用者的許可權為基礎</span><span class="sxs-lookup"><span data-stu-id="bec25-197">Topic visibility and content is based on a user's permissions</span></span>

<span data-ttu-id="bec25-198">當您將建議的主題清單當做知識管理員複查時，請記住，建議主題的內容會根據許可權進行動態。</span><span class="sxs-lookup"><span data-stu-id="bec25-198">When you review the list of suggested topics as a knowledge manager, keep in mind that the contents on a suggested topic will be dynamically based on permissions.</span></span> <span data-ttu-id="bec25-199">建議的內容及向您顯示的使用者可能與向任何使用者或另一個知識管理員呈現的使用者不同。</span><span class="sxs-lookup"><span data-stu-id="bec25-199">The suggested content and people that are shown to you might not be the same as those who are presented to any user or another knowledge manager.</span></span>

<span data-ttu-id="bec25-200">根據查看與主題相關聯之內容的許可權，每一位使用者可能會看到一組不同的建議資源、人員、替代名稱及定義。</span><span class="sxs-lookup"><span data-stu-id="bec25-200">Based on the permissions to view content that is associated with a topic, each user might see a different set of suggested resources, people, alternative names, and definition.</span></span>

## <a name="prioritize-the-topics-for-curation"></a><span data-ttu-id="bec25-201">設定 curation 主題的優先順序</span><span class="sxs-lookup"><span data-stu-id="bec25-201">Prioritize the topics for curation</span></span>

<span data-ttu-id="bec25-202">您可以使用下列策略來識別可能很醒目的主題，因此很適合 curation。</span><span class="sxs-lookup"><span data-stu-id="bec25-202">You can use the following strategies to identify topics that are likely to be prominent, and therefore are good candidates for curation.</span></span> 

### <a name="taxonomies"></a><span data-ttu-id="bec25-203">分類法</span><span class="sxs-lookup"><span data-stu-id="bec25-203">Taxonomies</span></span>

<span data-ttu-id="bec25-204">使用現有的分類可提供使用者可能會很醒目的主題清單。</span><span class="sxs-lookup"><span data-stu-id="bec25-204">Using existing taxonomies can provide a list of topics that are likely to be prominent for users.</span></span> <span data-ttu-id="bec25-205">例如，這些可能是：</span><span class="sxs-lookup"><span data-stu-id="bec25-205">For example, these could be:</span></span>

-   <span data-ttu-id="bec25-206">您的組織提供的產品和服務</span><span class="sxs-lookup"><span data-stu-id="bec25-206">Products and services that your organization provides</span></span>

-   <span data-ttu-id="bec25-207">組織中的 Teams</span><span class="sxs-lookup"><span data-stu-id="bec25-207">Teams in your organization</span></span>

-   <span data-ttu-id="bec25-208">高設定檔專案</span><span class="sxs-lookup"><span data-stu-id="bec25-208">High-profile projects</span></span>

<span data-ttu-id="bec25-209">您也可以在部門或功能層級上使用此方法，讓主題專家瞭解組織的該區域。</span><span class="sxs-lookup"><span data-stu-id="bec25-209">This approach could also be taken on a departmental or functional level, with subject-matter experts who understand that area of your organization.</span></span> <span data-ttu-id="bec25-210">目標不會讓他們審閱選取範圍或所有主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-210">The goal isn't to have them review a selection or all of the topics.</span></span> <span data-ttu-id="bec25-211">相反地，他們會帶來自己的網域專業知識以引導選擇性 curation。</span><span class="sxs-lookup"><span data-stu-id="bec25-211">Rather, they bring their own domain expertise to guide selective curation.</span></span>

### <a name="search"></a><span data-ttu-id="bec25-212">搜尋</span><span class="sxs-lookup"><span data-stu-id="bec25-212">Search</span></span>

<span data-ttu-id="bec25-213">常見的搜尋字詞通常會以主題形式探索。</span><span class="sxs-lookup"><span data-stu-id="bec25-213">Common search terms are often discovered as topics.</span></span> <span data-ttu-id="bec25-214">您可以在 [Microsoft 搜尋中使用上方查詢報告](/sharepoint/view-search-usage-reports)，識別您組織中最常使用的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="bec25-214">By using the [top query reports in Microsoft Search](/sharepoint/view-search-usage-reports), you can identify the most frequent search terms in your organization.</span></span> <span data-ttu-id="bec25-215">如果已探索這些字詞的主題，它們就是 curation 的良好候選人。</span><span class="sxs-lookup"><span data-stu-id="bec25-215">If topics have been discovered for these terms, they're good candidates for curation.</span></span> <span data-ttu-id="bec25-216">這些主題可以在 Microsoft 搜尋中呈現為解答卡。</span><span class="sxs-lookup"><span data-stu-id="bec25-216">These topics can be presented as answer cards in Microsoft Search.</span></span>

<span data-ttu-id="bec25-217">如果您目前使用的是 [Microsoft 搜尋書簽](/microsoftsearch/manage-bookmarks)，請考慮哪些內容可以取代為主題。</span><span class="sxs-lookup"><span data-stu-id="bec25-217">If you're currently using [Microsoft Search bookmarks](/microsoftsearch/manage-bookmarks), consider which of these can be replaced with a topic.</span></span> <span data-ttu-id="bec25-218">書簽答案卡包含標題、描述及 URL。</span><span class="sxs-lookup"><span data-stu-id="bec25-218">A bookmark answer card contains a title, description, and URL.</span></span> <span data-ttu-id="bec25-219">在某些情況下，使用者可以使用主題卡片，而且主題卡片也會顯示資源和人員。</span><span class="sxs-lookup"><span data-stu-id="bec25-219">In some circumstances, a topic card might be more useful to a user, and a topic card also shows resources and people.</span></span>

<span data-ttu-id="bec25-220">在使用者的搜尋體驗中，當使用者搜尋類似 *旅行* 的字詞時，搜尋結果會以 Microsoft 搜尋中的下列優先順序順序顯示：</span><span class="sxs-lookup"><span data-stu-id="bec25-220">In the user's search experience, when a user searches for a term like *travel*, search results are displayed in the following priority order in Microsoft Search:</span></span>

1.  <span data-ttu-id="bec25-221">已發佈或已確認的主題</span><span class="sxs-lookup"><span data-stu-id="bec25-221">Published or confirmed topics</span></span>

2.  <span data-ttu-id="bec25-222">書籤</span><span class="sxs-lookup"><span data-stu-id="bec25-222">Bookmarks</span></span>

3.  <span data-ttu-id="bec25-223">建議的主題</span><span class="sxs-lookup"><span data-stu-id="bec25-223">Suggested topics</span></span>

### <a name="impressions-and-quality-score"></a><span data-ttu-id="bec25-224">印記和品質分數</span><span class="sxs-lookup"><span data-stu-id="bec25-224">Impressions and quality score</span></span>

<span data-ttu-id="bec25-225">「 [印記](manage-topics.md#impressions) 計數」和「 [品質分數](manage-topics.md#quality-score) 」是瞭解主題行為的重要衡量標準。</span><span class="sxs-lookup"><span data-stu-id="bec25-225">The [impressions](manage-topics.md#impressions) count and [quality score](manage-topics.md#quality-score) are important metrics for understanding the behavior of a topic.</span></span> <span data-ttu-id="bec25-226">當只有知識管理員或 IT 小組能夠存取主題時，這些計量值的值將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="bec25-226">The value of these metrics will be limited when only knowledge managers or IT teams have access to topics.</span></span> <span data-ttu-id="bec25-227">向使用者示範群組公開主題將會為這些量值產生更具代表性的資料。</span><span class="sxs-lookup"><span data-stu-id="bec25-227">Exposing topics to a pilot group of users will generate more representative data for these measures.</span></span>

<span data-ttu-id="bec25-228">具有高印象計數的主題可能會更頻繁地進行互動。</span><span class="sxs-lookup"><span data-stu-id="bec25-228">Topics with a high impression count are likely to be more frequently interacted with.</span></span> <span data-ttu-id="bec25-229">這些主題的品質分數可讓您瞭解這些主題的豐富程度。</span><span class="sxs-lookup"><span data-stu-id="bec25-229">The quality score for these topics will give a sense of how rich those topics are.</span></span> <span data-ttu-id="bec25-230">具有高印象計數和低品質分數的主題是 curation 的良好目標。</span><span class="sxs-lookup"><span data-stu-id="bec25-230">Topics with a high impression count and a low quality score are good targets for curation.</span></span>

### <a name="key-terms-from-the-information-architecture-of-larger-organizational-sites"></a><span data-ttu-id="bec25-231">較大型組織網站資訊架構中的重要字詞</span><span class="sxs-lookup"><span data-stu-id="bec25-231">Key terms from the information architecture of larger organizational sites</span></span>

<span data-ttu-id="bec25-232">組織內較大的入口網站可能會在組織其資訊架構和網站流覽其業務單位、產品線、主要專案等方面的主要主題方面有投資時間。</span><span class="sxs-lookup"><span data-stu-id="bec25-232">Larger portal sites within your organization might have invested time in organizing their information architecture and the navigation of their site around key topic areas for their business units, product lines, major projects, and so on.</span></span> <span data-ttu-id="bec25-233">若要查看這些條款及識別及 curating 相關主題，可以協助使用者尋找這些區域的資訊。</span><span class="sxs-lookup"><span data-stu-id="bec25-233">Reviewing these terms and identifying and curating topics for these terms can help users who are looking for information on these areas.</span></span>

### <a name="leverage-internal-knowledge-bases-or-wiki-sites"></a><span data-ttu-id="bec25-234">利用內部知識文庫或 wiki 網站</span><span class="sxs-lookup"><span data-stu-id="bec25-234">Leverage internal knowledge bases or wiki sites</span></span>

<span data-ttu-id="bec25-235">如果您的組織已投資掌握知識文庫或 wiki 網站，這些可提供您初始 curation 工作所使用的主題清單。</span><span class="sxs-lookup"><span data-stu-id="bec25-235">If your organization has invested in knowledge bases or wiki sites, these can provide a list of topics to use for your initial curation efforts.</span></span> <span data-ttu-id="bec25-236">如果是特別大的，請選取最有查看或已編輯的主題做為起始點。</span><span class="sxs-lookup"><span data-stu-id="bec25-236">If they're particularly large, select the most viewed or edited topics as a starting point.</span></span>

## <a name="see-also"></a><span data-ttu-id="bec25-237">請參閱</span><span class="sxs-lookup"><span data-stu-id="bec25-237">See also</span></span>

[<span data-ttu-id="bec25-238">在主題中心中管理主題</span><span class="sxs-lookup"><span data-stu-id="bec25-238">Manage topics in the topic center</span></span>](manage-topics.md)

[<span data-ttu-id="bec25-239">主題中心概觀</span><span class="sxs-lookup"><span data-stu-id="bec25-239">Topic center overview</span></span>](topic-center-overview.md)
