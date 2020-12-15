---
title: 主題體驗安全性和隱私權
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何規劃 Microsoft 365 的安全性和隱私權主題。
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668120"
---
# <a name="topic-experiences-security-and-privacy"></a><span data-ttu-id="fb6ff-103">主題體驗安全性和隱私權</span><span class="sxs-lookup"><span data-stu-id="fb6ff-103">Topic experiences security and privacy</span></span>

<span data-ttu-id="fb6ff-104">主題經驗使用 Microsoft 365 的現有內容安全性功能及知識網路控制項，來控制向組織中的使用者顯示的 AI 產生的內容。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-104">Topic experiences uses existing content security features in Microsoft 365, along with knowledge network controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="fb6ff-105">這是 Microsoft 365 安全性設定的組合， (網站、檔案及資料夾的許可權) 和主題經驗決定指定的使用者可以在主題中看到的內容的系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and topic experiences admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="fb6ff-106">設定知識網路不會修改組織中內容的任何現有的存取控制。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-106">Setting up the knowledge network does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="fb6ff-107">使用者只會看到他們已有權存取的內容。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="fb6ff-108">本文說明主題在安全性的角度上的運作方式，以及知識管理員和知識管理員用來控制主題可見度的選項。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-108">This article describes how topic experiences works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="fb6ff-109">如您 [規劃的主題經驗](plan-topic-experiences.md)，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-109">Read this article as part of your [planning for topic experiences](plan-topic-experiences.md).</span></span>

<span data-ttu-id="fb6ff-110">您應熟悉主題的 [經驗](knowledge-management-overview.md)、 [主題中心](topic-center-overview.md)，以及如何 [使用主題中心的主題](work-with-topics.md) ，再閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-110">You should be familiar with [Topic experiences](knowledge-management-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](work-with-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="fb6ff-111">使用者可以在主題中看到的內容</span><span class="sxs-lookup"><span data-stu-id="fb6ff-111">What users can see in topics</span></span>

<span data-ttu-id="fb6ff-112">若要查看主題，使用者必須：</span><span class="sxs-lookup"><span data-stu-id="fb6ff-112">To see topics, a user must:</span></span>

- <span data-ttu-id="fb6ff-113">有主題經驗的授權</span><span class="sxs-lookup"><span data-stu-id="fb6ff-113">Have a Topic Experiences license</span></span>
- <span data-ttu-id="fb6ff-114">是 [主題檢視器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [投稿人或知識管理員](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="fb6ff-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="fb6ff-115">這兩個專案可讓使用者查看主題中心的存取權，並允許他們查看醒目提示和主題卡片。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="fb6ff-116">主題參與者此外，還擁有主題的 [建立和編輯](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) 許可權，而且知識管理員可以確認或移除主題。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="fb6ff-117">第一次探索一個主題時，知識管理員可以在主題中心看到該主題。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="fb6ff-118">根據主題的完整性與相關性，主題檢視器可能會顯示主題卡片中所述的主題，也可能看不到。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="fb6ff-119">主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="fb6ff-120">「AI」所新增之主題中的資訊僅對存取來源內容的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="fb6ff-121">由主題投稿人或知識管理員手動新增或編輯的文字，可供每個可以查看該主題的人看到。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="fb6ff-122">主題檢視器和參與者可以在主題中心看到已確認及已發佈的主題清單，但特定人員可以查看的主題詳細資料，取決於他們對來源材質所擁有的許可權，以及是否已手動編輯該主題。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="fb6ff-123">下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="fb6ff-124">主題專案</span><span class="sxs-lookup"><span data-stu-id="fb6ff-124">Topic item</span></span>|<span data-ttu-id="fb6ff-125">使用者可以看到的內容</span><span class="sxs-lookup"><span data-stu-id="fb6ff-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="fb6ff-126">主題名稱</span><span class="sxs-lookup"><span data-stu-id="fb6ff-126">Topic name</span></span>|<span data-ttu-id="fb6ff-127">使用者可以查看主題中心所有主題的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-127">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="fb6ff-128">某些主題若具有對使用者的關聯性很低，可能會看不到。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-128">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="fb6ff-129">主題描述</span><span class="sxs-lookup"><span data-stu-id="fb6ff-129">Topic description</span></span>|<span data-ttu-id="fb6ff-130">只有對來源內容有許可權的使用者才可以看到 AI 產生的描述。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="fb6ff-131">所有使用者皆可看到手動輸入或編輯的描述。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="fb6ff-132">多人</span><span class="sxs-lookup"><span data-stu-id="fb6ff-132">People</span></span>|<span data-ttu-id="fb6ff-133">所有使用者皆可看到已鎖定的人員。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="fb6ff-134">建議的人員只對具有來源內容許可權的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="fb6ff-135">檔案</span><span class="sxs-lookup"><span data-stu-id="fb6ff-135">Files</span></span>|<span data-ttu-id="fb6ff-136">只有具有來源內容許可權的使用者才能看到檔案。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="fb6ff-137">頁面</span><span class="sxs-lookup"><span data-stu-id="fb6ff-137">Pages</span></span>|<span data-ttu-id="fb6ff-138">只有具有來源內容許可權的使用者才能看到頁面。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="fb6ff-139">網站</span><span class="sxs-lookup"><span data-stu-id="fb6ff-139">Sites</span></span>|<span data-ttu-id="fb6ff-140">只有具有來源內容許可權的使用者才能看到網站。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="best-practices"></a><span data-ttu-id="fb6ff-141">最佳做法</span><span class="sxs-lookup"><span data-stu-id="fb6ff-141">Best practices</span></span>

<span data-ttu-id="fb6ff-142">主題經驗根據使用者對內容的現有許可權，向使用者呈現資訊。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-142">Topic experiences presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="fb6ff-143">Microsoft 365 提供各種方式，以確保將敏感內容限制于適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-143">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="fb6ff-144">除了標準小組或網站許可權之外，您還可以使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 或 [資料遺失防護](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 來限制存取內容和 [存取權](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) ，以定期查看使用者對機密資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-144">Beyond standard team or site permissions, you can use [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) or [data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to restrict access to content and [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="fb6ff-145">建議您使用這些工具，以確保您的內容許可權已在組織內適當地設定。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-145">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="fb6ff-146">然後，主題經驗可以為您的使用者提供有用且適當的資訊。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-146">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="fb6ff-147">如果您想要從主題體驗完全排除的主題，您也可以：</span><span class="sxs-lookup"><span data-stu-id="fb6ff-147">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="fb6ff-148">[從主題探索中排除敏感的 SharePoint 網站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-148">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="fb6ff-149">這些網站中的內容將不會出現在主題經驗中。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-149">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="fb6ff-150">[依名稱排除主題](topic-experiences-discovery.md#exclude-topics-by-name)。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-150">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="fb6ff-151">明確排除的主題不會出現在主題經驗中。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-151">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="fb6ff-152">讓知識管理員移除主題中心的主題。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-152">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="fb6ff-153">此外，我們建議採用下列最佳作法：</span><span class="sxs-lookup"><span data-stu-id="fb6ff-153">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="fb6ff-154">招聘組織中不同區域的知識經理。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-154">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="fb6ff-155">具有各種專業知識的知識管理員和透過 AI 所使用之基礎內容的存取權，可協助您為使用者 curate 最有用的知識，以及移除機密資訊（如果找到的話）。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-155">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="fb6ff-156">設定要求變更的工作流程。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-156">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="fb6ff-157">知識管理員或小組或網站擁有者應該有一個程式，可讓使用者在組織內啟動新的專案時，或發現具有不適當權限設定的內容時，要求排除主題或網站。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-157">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="fb6ff-158">在建立主題描述時，請注意物件和資訊的靈敏度。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-158">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="fb6ff-159">對於不具備主題來源內容之許可權的使用者，可能會看到這些描述。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-159">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="fb6ff-160">雖然您可以變更個別主題頁面的許可權，以縮小對特定使用者群組的存取權，但由於需要很高的管理工作，所以不建議使用這種方法。</span><span class="sxs-lookup"><span data-stu-id="fb6ff-160">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb6ff-161">也請參閱</span><span class="sxs-lookup"><span data-stu-id="fb6ff-161">See also</span></span>

[<span data-ttu-id="fb6ff-162">為小組設定三層保護</span><span class="sxs-lookup"><span data-stu-id="fb6ff-162">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="fb6ff-163">規劃主題經驗</span><span class="sxs-lookup"><span data-stu-id="fb6ff-163">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="fb6ff-164">設定主題經驗</span><span class="sxs-lookup"><span data-stu-id="fb6ff-164">Set up topic experiences</span></span>](set-up-topic-experiences.md)
