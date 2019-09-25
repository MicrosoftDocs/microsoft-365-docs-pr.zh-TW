---
title: 使用内容搜索搜索导入 Office 365 的第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用内容搜索电子数据展示工具搜索从第三方数据源导入 Office 365 中的邮箱的项目。 您可以创建查询以搜索所有导入的项目，也可以创建查询以搜索特定的第三方数据类型。 本文列出了可用于关键字查询的值，以搜索可导入 Office 365 的第三方数据类型。
ms.openlocfilehash: 2d531557054398be4ca963a9b09943f1bf583d10
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077438"
---
# <a name="use-content-search-to-search-third-party-data-imported-to-office-365"></a><span data-ttu-id="c7894-105">使用内容搜索搜索导入 Office 365 的第三方数据</span><span class="sxs-lookup"><span data-stu-id="c7894-105">Use Content Search to search third-party data imported to Office 365</span></span>

<span data-ttu-id="c7894-106">您可以使用安全&合规性中心中[的内容搜索电子数据展示工具](content-search.md)搜索从第三方数据源导入 Office 365 中的邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="c7894-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="c7894-107">您可以创建查询以搜索所有导入的第三方数据项，也可以创建查询以搜索特定的第三方数据项。</span><span class="sxs-lookup"><span data-stu-id="c7894-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="c7894-108">此外，您还可以创建基于查询的 Office 365 保留策略或基于查询的 eDiscovery 保留，以在 Office 365 中保留第三方数据。</span><span class="sxs-lookup"><span data-stu-id="c7894-108">Also, you can also create a query-based Office 365 retention policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="c7894-109">有关导入第三方数据以及可以导入 Office 365 的第三方数据类型列表的详细信息，请参阅[与合作伙伴合作以在 Office 365 中存档第三方数据。](work-with-partner-to-archive-third-party-data.md)</span><span class="sxs-lookup"><span data-stu-id="c7894-109">For more information about importing third-party data and a list of the third-party data types that you can import to Office 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="c7894-110">创建查询以搜索所有第三方数据</span><span class="sxs-lookup"><span data-stu-id="c7894-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="c7894-111">要搜索（或置于保留状态）已导入 Office 365 的任何类型的第三方数据，可以在关键字框中使用`kind:externaldata`消息属性值对进行内容搜索或创建基于查询的保留时。</span><span class="sxs-lookup"><span data-stu-id="c7894-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="c7894-112">例如，要搜索从任何第三方数据源导入的项，并在导入项的 Subject 属性中包含单词"contoso"，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="c7894-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="c7894-113">前面的关键字查询示例包括主题属性。</span><span class="sxs-lookup"><span data-stu-id="c7894-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="c7894-114">有关可以包含在关键字查询中的第三方数据项的其他属性的列表，请参阅[在 Office 365 中与合作伙伴合作存档第三方数据](work-with-partner-to-archive-third-party-data.md#more-information)中的"详细信息"部分。</span><span class="sxs-lookup"><span data-stu-id="c7894-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="c7894-115">创建查询以搜索和保存第三方数据时，还可以使用条件来缩小搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="c7894-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="c7894-116">有关创建内容搜索查询的详细信息，请参阅[关键字查询和内容搜索的搜索条件。](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="c7894-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="c7894-117">创建查询以搜索特定类型的第三方数据</span><span class="sxs-lookup"><span data-stu-id="c7894-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="c7894-118">您可以使用以下消息*属性：* 内容搜索关键字框中的值对，创建仅搜索指定类型第三方数据的查询，而不是搜索所有类型的第三方数据：</span><span class="sxs-lookup"><span data-stu-id="c7894-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="c7894-119">例如，要搜索"主题"属性中包含单词"contoso"的 Facebook 数据，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="c7894-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="c7894-120">下表列出了可以搜索的第三方数据类型，以及用于`itemclass:`消息属性以专门搜索该类型第三方数据的值。</span><span class="sxs-lookup"><span data-stu-id="c7894-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="c7894-121">查询语法不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c7894-121">The query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="c7894-122">**第三方数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7894-122">**Third-party data type**</span></span>|<span data-ttu-id="c7894-123">**`itemclass:`属性值**</span><span class="sxs-lookup"><span data-stu-id="c7894-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7894-124">目的</span><span class="sxs-lookup"><span data-stu-id="c7894-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="c7894-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="c7894-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="c7894-126">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="c7894-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="c7894-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="c7894-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="c7894-128">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="c7894-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="c7894-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c7894-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="c7894-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c7894-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="c7894-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c7894-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="c7894-132">Axs 占位符</span><span class="sxs-lookup"><span data-stu-id="c7894-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="c7894-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c7894-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="c7894-134">集市之声</span><span class="sxs-lookup"><span data-stu-id="c7894-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="c7894-135">熊股</span><span class="sxs-lookup"><span data-stu-id="c7894-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="c7894-136">比特托伦特</span><span class="sxs-lookup"><span data-stu-id="c7894-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="c7894-137">黑 莓</span><span class="sxs-lookup"><span data-stu-id="c7894-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="c7894-138">黑莓通话记录</span><span class="sxs-lookup"><span data-stu-id="c7894-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="c7894-139">黑莓信使</span><span class="sxs-lookup"><span data-stu-id="c7894-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="c7894-140">黑莓 PIN</span><span class="sxs-lookup"><span data-stu-id="c7894-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="c7894-141">黑莓短信</span><span class="sxs-lookup"><span data-stu-id="c7894-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="c7894-142">彭博</span><span class="sxs-lookup"><span data-stu-id="c7894-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="c7894-143">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="c7894-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="c7894-144">彭博消息</span><span class="sxs-lookup"><span data-stu-id="c7894-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="c7894-145">Box</span><span class="sxs-lookup"><span data-stu-id="c7894-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="c7894-146">思科&amp;IM 状态服务器</span><span class="sxs-lookup"><span data-stu-id="c7894-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="c7894-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c7894-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="c7894-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c7894-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="c7894-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="c7894-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="c7894-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="c7894-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="c7894-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c7894-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="c7894-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c7894-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="c7894-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="c7894-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="c7894-154">努格泰拉</span><span class="sxs-lookup"><span data-stu-id="c7894-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="c7894-155">谷歌+</span><span class="sxs-lookup"><span data-stu-id="c7894-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="c7894-156">谷歌对话</span><span class="sxs-lookup"><span data-stu-id="c7894-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="c7894-157">转到MyPC</span><span class="sxs-lookup"><span data-stu-id="c7894-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="c7894-158">嘻哈聊天</span><span class="sxs-lookup"><span data-stu-id="c7894-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="c7894-159">霍普斯特</span><span class="sxs-lookup"><span data-stu-id="c7894-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="c7894-160">胡伯康奈斯</span><span class="sxs-lookup"><span data-stu-id="c7894-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="c7894-161">IBM 连接</span><span class="sxs-lookup"><span data-stu-id="c7894-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="c7894-162">IBM 同时</span><span class="sxs-lookup"><span data-stu-id="c7894-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="c7894-163">ICE 聊天</span><span class="sxs-lookup"><span data-stu-id="c7894-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="c7894-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="c7894-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="c7894-165">因斯塔格拉姆</span><span class="sxs-lookup"><span data-stu-id="c7894-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="c7894-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c7894-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="c7894-167">投资边缘</span><span class="sxs-lookup"><span data-stu-id="c7894-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="c7894-168">Irc</span><span class="sxs-lookup"><span data-stu-id="c7894-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="c7894-169">摇摆</span><span class="sxs-lookup"><span data-stu-id="c7894-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="c7894-170">JiveApi 保留</span><span class="sxs-lookup"><span data-stu-id="c7894-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="c7894-171">Jxta</span><span class="sxs-lookup"><span data-stu-id="c7894-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="c7894-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c7894-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="c7894-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="c7894-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="c7894-174">微软UC</span><span class="sxs-lookup"><span data-stu-id="c7894-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="c7894-175">心灵对齐</span><span class="sxs-lookup"><span data-stu-id="c7894-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="c7894-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="c7894-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="c7894-177">Msn</span><span class="sxs-lookup"><span data-stu-id="c7894-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="c7894-178">Myspace</span><span class="sxs-lookup"><span data-stu-id="c7894-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="c7894-179">近地天体网络</span><span class="sxs-lookup"><span data-stu-id="c7894-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="c7894-180">开纳普</span><span class="sxs-lookup"><span data-stu-id="c7894-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="c7894-181">兴趣</span><span class="sxs-lookup"><span data-stu-id="c7894-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="c7894-182">樞紐</span><span class="sxs-lookup"><span data-stu-id="c7894-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="c7894-183">Qq</span><span class="sxs-lookup"><span data-stu-id="c7894-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="c7894-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7894-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="c7894-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c7894-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="c7894-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="c7894-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="c7894-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c7894-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="c7894-188">软埃瑟</span><span class="sxs-lookup"><span data-stu-id="c7894-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="c7894-189">斯夸克</span><span class="sxs-lookup"><span data-stu-id="c7894-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="c7894-190">交响乐</span><span class="sxs-lookup"><span data-stu-id="c7894-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="c7894-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c7894-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="c7894-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="c7894-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="c7894-193">Tor</span><span class="sxs-lookup"><span data-stu-id="c7894-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="c7894-194">TTT</span><span class="sxs-lookup"><span data-stu-id="c7894-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="c7894-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="c7894-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="c7894-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="c7894-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="c7894-197">维梅奥</span><span class="sxs-lookup"><span data-stu-id="c7894-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="c7894-198">温MX</span><span class="sxs-lookup"><span data-stu-id="c7894-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="c7894-199">温尼</span><span class="sxs-lookup"><span data-stu-id="c7894-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="c7894-200">雅虎！</span><span class="sxs-lookup"><span data-stu-id="c7894-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="c7894-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="c7894-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="c7894-202">黄色夹克</span><span class="sxs-lookup"><span data-stu-id="c7894-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="c7894-203">Youtube</span><span class="sxs-lookup"><span data-stu-id="c7894-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
