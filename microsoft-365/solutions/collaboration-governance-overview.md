---
title: Microsoft 365 中的共同作業管理
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 瞭解如何在 Microsoft 365 群組、小組、SharePoint 及 Yammer 中管理相關的功能。
ms.openlocfilehash: cdef9a4f939c20b34bf32efb5a258deddd885d0e
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662521"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a><span data-ttu-id="c1f51-103">Microsoft 365 中的共同作業管理</span><span class="sxs-lookup"><span data-stu-id="c1f51-103">Overview of collaboration governance in Microsoft 365</span></span>

<span data-ttu-id="c1f51-104">Microsoft 365 有一套豐富的工具，可實施組織可能需要的任何控管功能。</span><span class="sxs-lookup"><span data-stu-id="c1f51-104">Microsoft 365 has a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="c1f51-105">本文將引導 IT 專業人員要求適當的問題，以判斷其控管需求，以及如何根據組織設定檔來符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="c1f51-105">This article guides IT Pros to ask the right questions to determine their requirements for governance and how to meet them based on their organizational profile.</span></span>

## <a name="what-are-microsoft-365-groups"></a><span data-ttu-id="c1f51-106">何謂 Microsoft 365 群組？</span><span class="sxs-lookup"><span data-stu-id="c1f51-106">What are Microsoft 365 groups?</span></span>

<span data-ttu-id="c1f51-107">我們知道目前的組織使用不同的工具集。</span><span class="sxs-lookup"><span data-stu-id="c1f51-107">We know that organizations today are using a diverse tool set.</span></span> <span data-ttu-id="c1f51-108">使用團隊聊天的開發人員小組、主管電子郵件，以及透過企業社交的整個組織。</span><span class="sxs-lookup"><span data-stu-id="c1f51-108">There's the team of developers using team chat, the executives sending email, and the entire organization connecting over enterprise social.</span></span> <span data-ttu-id="c1f51-109">因為每個群組都是唯一的，且具有自身的功能需求和工作樣式，所以使用多個協同作業工具。</span><span class="sxs-lookup"><span data-stu-id="c1f51-109">Multiple collaboration tools are in use because every group is unique and has their own functional needs and work style.</span></span> <span data-ttu-id="c1f51-110">有些只會使用電子郵件，有些人會主要在聊天中生活。</span><span class="sxs-lookup"><span data-stu-id="c1f51-110">Some will use only email while others will live primarily in chat.</span></span> 

<span data-ttu-id="c1f51-111">如果使用者感覺其所提供的工具不符合其需求，他們就可能會下載其最愛的使用者應用程式，以支援其案例。</span><span class="sxs-lookup"><span data-stu-id="c1f51-111">If users feel the IT-provided tools do not fit their needs, they will likely download their favorite consumer app which supports their scenarios.</span></span> <span data-ttu-id="c1f51-112">雖然此程式可讓使用者快速開始，但在組織中有多個登入、難於共用，而且沒有任何單一位置可供查看內容時，可讓整個組織的使用者體驗變得令人沮喪。</span><span class="sxs-lookup"><span data-stu-id="c1f51-112">Although this process allows users to get started quickly, it leads to a frustrating user experience across the organization with multiple logins, difficulty sharing, and no single place to view content.</span></span> <span data-ttu-id="c1f51-113">這個概念稱為「陰影 IT」，並對組織帶來極大的風險。</span><span class="sxs-lookup"><span data-stu-id="c1f51-113">This concept is referred to as “Shadow IT” and poses a significant risk to organizations.</span></span> <span data-ttu-id="c1f51-114">它可減少統一管理使用者存取、確保安全性和服務合規性需求的能力。</span><span class="sxs-lookup"><span data-stu-id="c1f51-114">It reduces the ability to uniformly manage user access, ensure security, and service compliance needs.</span></span>

<span data-ttu-id="c1f51-115">Microsoft 365 群組、小組和 Yammer 等服務可讓使用者，並提供共同作業所需的工具，以降低陰影的風險。</span><span class="sxs-lookup"><span data-stu-id="c1f51-115">Services such as Microsoft 365 groups, Teams, and Yammer empower users and reduces the risk of shadow IT by providing the tools needed to collaborate.</span></span> <span data-ttu-id="c1f51-116">Microsoft 365 群組可讓您選擇您想要共同作業的一組人員，並輕鬆地設定要共用之人員的資源集合。</span><span class="sxs-lookup"><span data-stu-id="c1f51-116">Microsoft 365 groups lets you choose a set of people with whom you wish to collaborate, and easily set up a collection of resources for those people to share.</span></span> <span data-ttu-id="c1f51-117">新增成員至群組時，會自動授與群組所提供之所有資產的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="c1f51-117">Adding members to the group automatically grants the needed permissions to all assets provided by the group.</span></span> <span data-ttu-id="c1f51-118">兩個小組和 Yammer 都使用 Microsoft 365 群組來管理其成員資格。</span><span class="sxs-lookup"><span data-stu-id="c1f51-118">Both Teams and Yammer use Microsoft 365 groups to manage their membership.</span></span>

![顯示 Microsoft 365 群組和相關服務的圖表](../media/microsoft-365-groups-hub-spoke.png)

<span data-ttu-id="c1f51-120">Microsoft 365 群組包含各種控管控制項，包括到期原則、命名慣例和封鎖的字詞原則，以協助您管理組織中的群組。</span><span class="sxs-lookup"><span data-stu-id="c1f51-120">Microsoft 365 Groups includes a variety of governance controls, including an expiration policy, naming conventions, and a blocked words policy, to help you manage groups in your organization.</span></span> <span data-ttu-id="c1f51-121">如需詳細資訊，請參閱 [規劃組織及生命週期管理的 microsoft 365 群組和 Microsoft 團隊](plan-organization-lifecycle-governance.md) 。</span><span class="sxs-lookup"><span data-stu-id="c1f51-121">See [Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams](plan-organization-lifecycle-governance.md) for details.</span></span>

## <a name="technical-architecture"></a><span data-ttu-id="c1f51-122">技術架構</span><span class="sxs-lookup"><span data-stu-id="c1f51-122">Technical architecture</span></span>

<span data-ttu-id="c1f51-123">Microsoft 365 支援三種主要通訊方法：</span><span class="sxs-lookup"><span data-stu-id="c1f51-123">There are three main communication methods supported by Microsoft 365:</span></span>

- <span data-ttu-id="c1f51-124">Outlook：透過使用共用群組收件匣和行事曆的電子郵件進行協同作業</span><span class="sxs-lookup"><span data-stu-id="c1f51-124">Outlook: collaboration through email with a shared group inbox and calendar</span></span>
- <span data-ttu-id="c1f51-125">Microsoft 小組：一種持續聊天的工作區，您可以在其中以特定子群組為基礎的各種主題，進行非正式、即時的交談</span><span class="sxs-lookup"><span data-stu-id="c1f51-125">Microsoft Teams: a persistent-chat-based workspace where you can have informal, real-time, conversations around a variety of topics, organized by specific sub-groups</span></span>
- <span data-ttu-id="c1f51-126">Yammer：共同作業的企業社交體驗</span><span class="sxs-lookup"><span data-stu-id="c1f51-126">Yammer: enterprise social experience for collaboration</span></span>

> [!NOTE]
> <span data-ttu-id="c1f51-127">透過其他團隊合作應用程式建立新的群組（例如，SharePoint、Planner 或 Stream），將會建立具有 Outlook 收件匣的群組，以及連接到小組的功能。</span><span class="sxs-lookup"><span data-stu-id="c1f51-127">Creating a new group via other teamwork applications - such as SharePoint, Planner or Stream - will create a group with an Outlook inbox and the ability to connect to Teams.</span></span>

<span data-ttu-id="c1f51-128">根據建立群組的位置，會自動布建特定資源，例如：</span><span class="sxs-lookup"><span data-stu-id="c1f51-128">Depending on where a group is created, certain resources are provisioned automatically, such as:</span></span>
- <span data-ttu-id="c1f51-129">[收件](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) 匣-群組成員之間的電子郵件交談。</span><span class="sxs-lookup"><span data-stu-id="c1f51-129">[Inbox](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) - For email conversations between group members.</span></span> <span data-ttu-id="c1f51-130">此收件匣具有電子郵件地址，可以設定為接受來自群組以外的人員，甚至是組織外的郵件，與傳統的通訊群組清單非常類似。</span><span class="sxs-lookup"><span data-stu-id="c1f51-130">This inbox has an email address and can be set to accept messages from people outside the group and even outside your organization, much like a traditional distribution list.</span></span>
 - <span data-ttu-id="c1f51-131">行事[曆](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)–用於排程與群組相關的事件</span><span class="sxs-lookup"><span data-stu-id="c1f51-131">[Calendar](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – For scheduling events related to the group</span></span>
- <span data-ttu-id="c1f51-132">[SharePoint 小組網站](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) –中央存放庫，提供與群組相關的資訊、連結和內容。</span><span class="sxs-lookup"><span data-stu-id="c1f51-132">[SharePoint team site](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – A central repository for information, links and content relating to your group</span></span>
- <span data-ttu-id="c1f51-133">[OneNote 筆記本](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) –用於收集創意、調查和資訊</span><span class="sxs-lookup"><span data-stu-id="c1f51-133">[OneNote notebook](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – For gathering ideas, research, and information</span></span>
- <span data-ttu-id="c1f51-134">[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) –用於指派及管理群組成員中的專案工作</span><span class="sxs-lookup"><span data-stu-id="c1f51-134">[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – For assigning and managing project tasks among your group members</span></span>
- <span data-ttu-id="c1f51-135">[Yammer 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) –具有交談及共用資訊的常見位置</span><span class="sxs-lookup"><span data-stu-id="c1f51-135">[Yammer group](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – A common place to have conversations and share information</span></span>
- <span data-ttu-id="c1f51-136">小組– Microsoft 365 中的聊天工作區</span><span class="sxs-lookup"><span data-stu-id="c1f51-136">Teams – A chat-based workspace in Microsoft 365</span></span>
- <span data-ttu-id="c1f51-137">Stream-影片傳送服務</span><span class="sxs-lookup"><span data-stu-id="c1f51-137">Stream - A video streaming service</span></span>

> [!NOTE]
> <span data-ttu-id="c1f51-138">透過 Yammer 或小組建立新的 Office 365 群組時，群組不會出現在 Outlook 或通訊錄中，因為這些使用者之間的主要通訊會在各自的用戶端中發生。</span><span class="sxs-lookup"><span data-stu-id="c1f51-138">When a new Office 365 Group is created via Yammer or Teams, the group isn't visible in Outlook or the address book because the primary communication between those users happens in their respective clients.</span></span> <span data-ttu-id="c1f51-139">Yammer 群組無法連線至團隊。</span><span class="sxs-lookup"><span data-stu-id="c1f51-139">Yammer groups cannot be connected to Teams.</span></span>

## <a name="collaboration-options"></a><span data-ttu-id="c1f51-140">協同作業選項</span><span class="sxs-lookup"><span data-stu-id="c1f51-140">Collaboration options</span></span>

<span data-ttu-id="c1f51-141">在 Microsoft 365 內有多個地方共同作業和進行交談。</span><span class="sxs-lookup"><span data-stu-id="c1f51-141">There are multiple places to collaborate and have conversations within Microsoft 365.</span></span> <span data-ttu-id="c1f51-142">瞭解開始交談的位置可協助您定義通訊策略。</span><span class="sxs-lookup"><span data-stu-id="c1f51-142">Understanding where to start a conversation can help you define a strategy for communication.</span></span>

![圖表顯示何時使用團隊、Yammer 和 Outlook](../media/inner-loop-outer-loop.png)

- <span data-ttu-id="c1f51-144">小組：以聊天為基礎的工作區 (高速度共同作業) –內環</span><span class="sxs-lookup"><span data-stu-id="c1f51-144">Teams: chat-based workspace (high velocity collaboration) – inner loop</span></span>
  - <span data-ttu-id="c1f51-145">專為與您每天使用的人員共同作業</span><span class="sxs-lookup"><span data-stu-id="c1f51-145">Built for collaboration with the people you work with every day</span></span>
  - <span data-ttu-id="c1f51-146">以單一體驗將資訊放在使用者的手邊</span><span class="sxs-lookup"><span data-stu-id="c1f51-146">Puts information at the fingertips of users in a single experience</span></span>
  - <span data-ttu-id="c1f51-147">新增索引標籤、連接器和 bot</span><span class="sxs-lookup"><span data-stu-id="c1f51-147">Add tabs, connectors and bots</span></span>
  - <span data-ttu-id="c1f51-148">即時聊天、音訊/視訊會議、記錄的會議</span><span class="sxs-lookup"><span data-stu-id="c1f51-148">Live chat, audio/video conferencing, recorded meetings</span></span>

- <span data-ttu-id="c1f51-149">Yammer：跨組織 (enterprise 社交) –外部迴圈</span><span class="sxs-lookup"><span data-stu-id="c1f51-149">Yammer: connect across the org (enterprise social) – outer loop</span></span>
  - <span data-ttu-id="c1f51-150">業務部的社區，其共同共同感興趣或專業知識的人員跨職能群組，但不一定要在日常運作中協同運作。</span><span class="sxs-lookup"><span data-stu-id="c1f51-150">Communities of practice - Cross-functional groups of people who share a common interest or expertise but are not necessarily working together on a day-to-day basis</span></span>
  - <span data-ttu-id="c1f51-151">領導能力，學習社區，以角色為基礎的社區</span><span class="sxs-lookup"><span data-stu-id="c1f51-151">Leadership connection, learning communities, role-based communities</span></span>

- <span data-ttu-id="c1f51-152">信箱和行事曆 (電子郵件型共同作業) </span><span class="sxs-lookup"><span data-stu-id="c1f51-152">Mailbox and calendar (email-based collaboration)</span></span>
  - <span data-ttu-id="c1f51-153">用於與一組人員進行目標通訊</span><span class="sxs-lookup"><span data-stu-id="c1f51-153">Use for targeted communication with a group of people</span></span>
  - <span data-ttu-id="c1f51-154">與其他群組成員的會議共用行事曆</span><span class="sxs-lookup"><span data-stu-id="c1f51-154">Shared calendar for meetings with other group members</span></span>
 
<span data-ttu-id="c1f51-155">每個群組都取得連線的 SharePoint 小組網站，讓使用者可以共用內容、建立自訂頁面和作者新聞。</span><span class="sxs-lookup"><span data-stu-id="c1f51-155">Every group gets a connected SharePoint team site where users can share content, create customized pages and author news.</span></span> <span data-ttu-id="c1f51-156">您也可以 [將現有的 SharePoint 小組網站連線到新的 Microsoft 365 群組](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)。</span><span class="sxs-lookup"><span data-stu-id="c1f51-156">You can also [connect existing SharePoint team sites to new Microsoft 365 groups](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview).</span></span>

## <a name="illustrations"></a><span data-ttu-id="c1f51-157">插圖</span><span class="sxs-lookup"><span data-stu-id="c1f51-157">Illustrations</span></span>

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a><span data-ttu-id="c1f51-158">適用於 IT 結構設計師的 Microsoft 365 中的Microsoft Teams 和相關生產力服務</span><span class="sxs-lookup"><span data-stu-id="c1f51-158">Microsoft Teams and related productivity services in Microsoft 365 for IT architects</span></span>
<span data-ttu-id="c1f51-159">使用 Microsoft Teams 領導，Microsoft 365 中生產力服務的邏輯架構。</span><span class="sxs-lookup"><span data-stu-id="c1f51-159">The logical architecture of productivity services in Microsoft 365, leading with Microsoft Teams.</span></span>

|<span data-ttu-id="c1f51-160">**項目**</span><span class="sxs-lookup"><span data-stu-id="c1f51-160">**Item**</span></span>|<span data-ttu-id="c1f51-161">**描述**</span><span class="sxs-lookup"><span data-stu-id="c1f51-161">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1f51-162">[![Teams 邏輯架構海報的縮圖影像](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf)</span><span class="sxs-lookup"><span data-stu-id="c1f51-162">[![Thumb image for Teams logical architecture poster](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf)</span></span> <br/> <span data-ttu-id="c1f51-163">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c1f51-163">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)</span></span>  <br><span data-ttu-id="c1f51-164">更新日期：2019 年 4 月</span><span class="sxs-lookup"><span data-stu-id="c1f51-164">Updated April 2019</span></span>   |<span data-ttu-id="c1f51-165">Microsoft 提供一套生產力服務，共同合作來提供資料管理、安全性和法規遵循功能的共同作業體驗。</span><span class="sxs-lookup"><span data-stu-id="c1f51-165">Microsoft provides a suite of productivity services that work together to provide collaboration experiences with data governance, security, and compliance capabilities.</span></span> <br/> <br/><span data-ttu-id="c1f51-166">這系列的圖例可為企業結構設計師提供生產力服務邏輯架構使用 Microsoft Teams 引導的檢視。</span><span class="sxs-lookup"><span data-stu-id="c1f51-166">This series of illustrations provides a view into the logical architecture of productivity services for enterprise architects, leading with Microsoft Teams.</span></span>|


### <a name="groups-in-microsoft-365-for-it-architects"></a><span data-ttu-id="c1f51-167">適用於 IT 結構設計師的 Microsoft 365 中的群組</span><span class="sxs-lookup"><span data-stu-id="c1f51-167">Groups in Microsoft 365 for IT Architects</span></span>
<span data-ttu-id="c1f51-168">對於 Microsoft 365 中的群組，IT 結構設計師需要知道的事項</span><span class="sxs-lookup"><span data-stu-id="c1f51-168">What IT architects need to know about groups in Microsoft 365</span></span>

|<span data-ttu-id="c1f51-169">**項目**</span><span class="sxs-lookup"><span data-stu-id="c1f51-169">**Item**</span></span>|<span data-ttu-id="c1f51-170">**描述**</span><span class="sxs-lookup"><span data-stu-id="c1f51-170">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1f51-171">[![群組資訊圖的縮圖影像](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="c1f51-171">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span> <br/> <span data-ttu-id="c1f51-172">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c1f51-172">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span> <br> <span data-ttu-id="c1f51-173">更新日期：2019 年 6 月</span><span class="sxs-lookup"><span data-stu-id="c1f51-173">Updated June 2019</span></span>|<span data-ttu-id="c1f51-174">這些圖例會詳細說明不同類型的群組、如何建立及管理群組，以及一些控管建議。</span><span class="sxs-lookup"><span data-stu-id="c1f51-174">These illustrations detail the different types of groups, how these are created and managed, and a few governance recommendations.</span></span>|

## <a name="conference-sessions"></a><span data-ttu-id="c1f51-175">會議會話</span><span class="sxs-lookup"><span data-stu-id="c1f51-175">Conference sessions</span></span>

<span data-ttu-id="c1f51-176">觀看這些會議會話，以深入瞭解 Microsoft 365 群組和小組的管理。</span><span class="sxs-lookup"><span data-stu-id="c1f51-176">Watch these conference sessions to learn more about governance for Microsoft 365 Groups and Teams.</span></span>

<span data-ttu-id="c1f51-177">**基礎**</span><span class="sxs-lookup"><span data-stu-id="c1f51-177">**Fundamentals**</span></span>

<span data-ttu-id="c1f51-178">深入瞭解 Microsoft 365 群組中的基礎和新創新，包括規模的管理和控管，以及驅動使用狀況和採用方式的最佳作法，以及自助服務。</span><span class="sxs-lookup"><span data-stu-id="c1f51-178">Learn the fundamentals and new innovations in Microsoft 365 Groups, including management and governance at scale, best practices for driving usage and adoption, and self-service.</span></span>

- [<span data-ttu-id="c1f51-179">接納 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c1f51-179">Embrace Microsoft 365 Groups</span></span>](https://myignite.techcommunity.microsoft.com/sessions/81553)

<span data-ttu-id="c1f51-180">**管理**</span><span class="sxs-lookup"><span data-stu-id="c1f51-180">**Governance**</span></span>

<span data-ttu-id="c1f51-181">瞭解如何設定您的群組到期生命週期、命名原則、分類標籤、與外部來賓的共同作業，以及管理群組建立許可權。</span><span class="sxs-lookup"><span data-stu-id="c1f51-181">Learn how to set up your groups expiry lifecycle, naming policies, classification labels, collaboration with external guests, and manage group creation permissions.</span></span>

- [<span data-ttu-id="c1f51-182">使用 Office 365 群組轉換共同作業及抵制陰影</span><span class="sxs-lookup"><span data-stu-id="c1f51-182">Transform collaboration and fight shadow IT with Office 365 groups</span></span>](https://myignite.techcommunity.microsoft.com/sessions/81554)

<span data-ttu-id="c1f51-183">**客戶範例**</span><span class="sxs-lookup"><span data-stu-id="c1f51-183">**Customer example**</span></span>

<span data-ttu-id="c1f51-184">請參閱幕後的範例，說明 Microsoft 365 群組、SharePoint、小組和 Yammer 如何共同運作，以提供全球協同作業平臺。</span><span class="sxs-lookup"><span data-stu-id="c1f51-184">See a behind-the-scenes example of how Microsoft 365 Groups, SharePoint, Teams, and Yammer work together to provide a global collaboration platform.</span></span>

- [<span data-ttu-id="c1f51-185">使用 Office 365 群組、SharePoint、小組和 Yammer 尋找共同作業的最擅長點</span><span class="sxs-lookup"><span data-stu-id="c1f51-185">Finding your collaboration sweet spot with Office 365 Groups, SharePoint, Teams, and Yammer</span></span>](https://myignite.techcommunity.microsoft.com/sessions/84289)