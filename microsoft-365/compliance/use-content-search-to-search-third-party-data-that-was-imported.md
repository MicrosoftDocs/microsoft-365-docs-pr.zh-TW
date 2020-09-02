---
title: 使用內容搜尋來搜尋協力廠商匯入的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用內容搜尋電子檔探索工具來搜尋從協力廠商資料來源匯入至 Microsoft 365 中信箱的專案，方法是建立查詢。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324569"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="bffa5-103">使用內容搜尋來搜尋自訂夥伴連接器匯入的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="bffa5-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="bffa5-104">您可以使用安全性 & 合規性中心的 [內容搜尋 eDiscovery 工具](content-search.md) ，在協力廠商資料來源中搜尋從 Microsoft 365 匯入信箱的專案。</span><span class="sxs-lookup"><span data-stu-id="bffa5-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="bffa5-105">您可以建立查詢來搜尋所有匯入的協力廠商資料項目，也可以建立查詢來搜尋特定的協力廠商資料項目。</span><span class="sxs-lookup"><span data-stu-id="bffa5-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="bffa5-106">此外，您也可以建立查詢型保留原則或以查詢為基礎的 eDiscovery 保留，以保留協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="bffa5-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="bffa5-107">如需使用協力廠商資料匯入協力廠商資料的詳細資訊，以及您可以匯入至 Microsoft 365 的協力廠商資料類型清單，請參閱在 [Office 365 中使用協力廠商資料的合作](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="bffa5-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bffa5-108">本文中的指導方針只適用于自訂夥伴連接器匯入的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="bffa5-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="bffa5-109">本文不適用於使用 Microsoft 規範中心內 [協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors) 匯入的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="bffa5-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="bffa5-110">建立查詢以搜尋所有協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="bffa5-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="bffa5-111">若要搜尋 (或保留狀態) 您已匯入至 Office 365 的協力廠商資料類型，您可以  `kind:externaldata` 在 [關鍵字] 方塊中使用「內容搜尋」或 [建立查詢型保留] 的 [郵件屬性-值] 組。</span><span class="sxs-lookup"><span data-stu-id="bffa5-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="bffa5-112">例如，若要搜尋從任何協力廠商資料來源匯入的專案，並在匯入專案的 Subject 屬性中包含 "contoso" 一詞，您可以使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="bffa5-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="bffa5-113">上一個關鍵字查詢範例包含 subject 屬性。</span><span class="sxs-lookup"><span data-stu-id="bffa5-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="bffa5-114">如需可包含在關鍵字查詢中的協力廠商資料項目的其他屬性清單，請參閱使用 [協力廠商在 Office 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md#more-information)一節中的「其他資訊」一節。</span><span class="sxs-lookup"><span data-stu-id="bffa5-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="bffa5-115">建立查詢以搜尋並保留協力廠商資料時，您也可以使用條件來縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="bffa5-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="bffa5-116">如需建立內容搜尋查詢的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="bffa5-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="bffa5-117">建立查詢以搜尋特定類型的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="bffa5-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="bffa5-118">除了搜尋所有類型的協力廠商資料之外，您可以使用下列郵件 *屬性：值* 組合，在內容搜尋的關鍵字方塊中，建立只搜尋協力廠商資料的指定類型的查詢：</span><span class="sxs-lookup"><span data-stu-id="bffa5-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="bffa5-119">例如，若要在 Subject 屬性中搜尋包含 "contoso" 一詞的 Facebook 資料，您可以使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="bffa5-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="bffa5-120">下表列出您可以搜尋的協力廠商資料類型，以及用於郵件屬性的值，  `itemclass:` 以特別搜尋該類型的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="bffa5-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="bffa5-121">查詢語法不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="bffa5-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="bffa5-122">**協力廠商資料類型**</span><span class="sxs-lookup"><span data-stu-id="bffa5-122">**Third-party data type**</span></span>|<span data-ttu-id="bffa5-123">**屬性值 `itemclass:`**</span><span class="sxs-lookup"><span data-stu-id="bffa5-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bffa5-124">目的</span><span class="sxs-lookup"><span data-stu-id="bffa5-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="bffa5-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="bffa5-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="bffa5-126">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="bffa5-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="bffa5-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="bffa5-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="bffa5-128">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="bffa5-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="bffa5-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="bffa5-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="bffa5-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="bffa5-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="bffa5-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="bffa5-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="bffa5-132">Axs 預留位置</span><span class="sxs-lookup"><span data-stu-id="bffa5-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="bffa5-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="bffa5-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="bffa5-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="bffa5-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="bffa5-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="bffa5-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="bffa5-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="bffa5-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="bffa5-137">黑 莓</span><span class="sxs-lookup"><span data-stu-id="bffa5-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="bffa5-138">BlackBerry 通話記錄</span><span class="sxs-lookup"><span data-stu-id="bffa5-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="bffa5-139">BlackBerry 信使</span><span class="sxs-lookup"><span data-stu-id="bffa5-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="bffa5-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="bffa5-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="bffa5-141">BlackBerry 短信</span><span class="sxs-lookup"><span data-stu-id="bffa5-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="bffa5-142">彭博</span><span class="sxs-lookup"><span data-stu-id="bffa5-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="bffa5-143">Bloomberg Message</span><span class="sxs-lookup"><span data-stu-id="bffa5-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="bffa5-144">Bloomberg 訊息</span><span class="sxs-lookup"><span data-stu-id="bffa5-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="bffa5-145">Box</span><span class="sxs-lookup"><span data-stu-id="bffa5-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="bffa5-146">Cisco IM &amp; 顯示伺服器</span><span class="sxs-lookup"><span data-stu-id="bffa5-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="bffa5-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="bffa5-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="bffa5-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="bffa5-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="bffa5-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="bffa5-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="bffa5-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="bffa5-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="bffa5-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="bffa5-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="bffa5-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="bffa5-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="bffa5-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="bffa5-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="bffa5-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="bffa5-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="bffa5-155">Google +</span><span class="sxs-lookup"><span data-stu-id="bffa5-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="bffa5-156">Google 交談</span><span class="sxs-lookup"><span data-stu-id="bffa5-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="bffa5-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="bffa5-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="bffa5-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="bffa5-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="bffa5-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="bffa5-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="bffa5-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="bffa5-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="bffa5-161">IBM 連線</span><span class="sxs-lookup"><span data-stu-id="bffa5-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="bffa5-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="bffa5-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="bffa5-163">ICE Chat</span><span class="sxs-lookup"><span data-stu-id="bffa5-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="bffa5-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="bffa5-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="bffa5-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="bffa5-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="bffa5-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="bffa5-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="bffa5-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="bffa5-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="bffa5-168">Irc</span><span class="sxs-lookup"><span data-stu-id="bffa5-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="bffa5-169">搖擺</span><span class="sxs-lookup"><span data-stu-id="bffa5-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="bffa5-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="bffa5-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="bffa5-171">Jxta</span><span class="sxs-lookup"><span data-stu-id="bffa5-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="bffa5-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="bffa5-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="bffa5-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="bffa5-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="bffa5-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="bffa5-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="bffa5-175">構思對齊</span><span class="sxs-lookup"><span data-stu-id="bffa5-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="bffa5-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="bffa5-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="bffa5-177">Msn</span><span class="sxs-lookup"><span data-stu-id="bffa5-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="bffa5-178">Myspace</span><span class="sxs-lookup"><span data-stu-id="bffa5-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="bffa5-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="bffa5-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="bffa5-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="bffa5-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="bffa5-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="bffa5-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="bffa5-182">樞紐</span><span class="sxs-lookup"><span data-stu-id="bffa5-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="bffa5-183">Qq</span><span class="sxs-lookup"><span data-stu-id="bffa5-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="bffa5-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="bffa5-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="bffa5-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="bffa5-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="bffa5-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="bffa5-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="bffa5-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="bffa5-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="bffa5-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="bffa5-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="bffa5-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="bffa5-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="bffa5-190">交響樂</span><span class="sxs-lookup"><span data-stu-id="bffa5-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="bffa5-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="bffa5-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="bffa5-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="bffa5-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="bffa5-193">Tor</span><span class="sxs-lookup"><span data-stu-id="bffa5-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="bffa5-194">TTT</span><span class="sxs-lookup"><span data-stu-id="bffa5-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="bffa5-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="bffa5-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="bffa5-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="bffa5-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="bffa5-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="bffa5-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="bffa5-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="bffa5-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="bffa5-199">Winny</span><span class="sxs-lookup"><span data-stu-id="bffa5-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="bffa5-200">雅虎！</span><span class="sxs-lookup"><span data-stu-id="bffa5-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="bffa5-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="bffa5-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="bffa5-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="bffa5-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="bffa5-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="bffa5-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
