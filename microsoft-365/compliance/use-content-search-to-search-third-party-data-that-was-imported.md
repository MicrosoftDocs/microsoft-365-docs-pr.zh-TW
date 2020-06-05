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
description: 使用內容搜尋 eDiscovery 工具，從協力廠商資料來源搜尋從 Microsoft 365 匯入信箱的專案。 您可以建立查詢來搜尋所有匯入的專案，或建立查詢以搜尋特定的協力廠商資料類型。 本文列出您可以在關鍵字查詢中使用的值，以搜尋您可以匯入至 Microsoft 365 的協力廠商資料類型。
ms.openlocfilehash: c494f4bbb13919f9a980f227093d291c148e9afe
ms.sourcegitcommit: 86705d15231c987be2fcf5a295b9b6239fc46077
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44566667"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="c924d-105">使用內容搜尋來搜尋自訂夥伴連接器匯入的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="c924d-105">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="c924d-106">您可以使用安全性 & 合規性中心的[內容搜尋 eDiscovery 工具](content-search.md)，在協力廠商資料來源中搜尋從 Microsoft 365 匯入信箱的專案。</span><span class="sxs-lookup"><span data-stu-id="c924d-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="c924d-107">您可以建立查詢來搜尋所有匯入的協力廠商資料項目，也可以建立查詢來搜尋特定的協力廠商資料項目。</span><span class="sxs-lookup"><span data-stu-id="c924d-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="c924d-108">此外，您也可以建立查詢型保留原則或以查詢為基礎的 eDiscovery 保留，以保留協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c924d-108">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="c924d-109">如需使用協力廠商資料匯入協力廠商資料的詳細資訊，以及您可以匯入至 Microsoft 365 的協力廠商資料類型清單，請參閱在[Office 365 中使用協力廠商資料的合作](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="c924d-109">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c924d-110">本文中的指導方針只適用于自訂夥伴連接器匯入的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c924d-110">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="c924d-111">本文不適用於使用 Microsoft 規範中心內[協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors)匯入的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c924d-111">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="c924d-112">建立查詢以搜尋所有協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="c924d-112">Creating a query to search all third-party data</span></span>

<span data-ttu-id="c924d-113">若要搜尋（或保留）您已匯入至 Office 365 的協力廠商資料類型，您可以 `kind:externaldata` 在內容搜尋的 [關鍵字] 方塊中，或在建立查詢型保留時，使用 [關鍵字] 屬性-值對。</span><span class="sxs-lookup"><span data-stu-id="c924d-113">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="c924d-114">例如，若要搜尋從任何協力廠商資料來源匯入的專案，並在匯入專案的 Subject 屬性中包含 "contoso" 一詞，您可以使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="c924d-114">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="c924d-115">上一個關鍵字查詢範例包含 subject 屬性。</span><span class="sxs-lookup"><span data-stu-id="c924d-115">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="c924d-116">如需可包含在關鍵字查詢中的協力廠商資料項目的其他屬性清單，請參閱使用[協力廠商在 Office 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md#more-information)一節中的「其他資訊」一節。</span><span class="sxs-lookup"><span data-stu-id="c924d-116">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="c924d-117">建立查詢以搜尋並保留協力廠商資料時，您也可以使用條件來縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c924d-117">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="c924d-118">如需建立內容搜尋查詢的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="c924d-118">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="c924d-119">建立查詢以搜尋特定類型的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="c924d-119">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="c924d-120">除了搜尋所有類型的協力廠商資料之外，您可以使用下列郵件*屬性：值*組合，在內容搜尋的關鍵字方塊中，建立只搜尋協力廠商資料的指定類型的查詢：</span><span class="sxs-lookup"><span data-stu-id="c924d-120">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="c924d-121">例如，若要在 Subject 屬性中搜尋包含 "contoso" 一詞的 Facebook 資料，您可以使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="c924d-121">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="c924d-122">下表列出您可以搜尋的協力廠商資料類型，以及用於郵件屬性的值， `itemclass:` 以特別搜尋該類型的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c924d-122">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="c924d-123">查詢語法不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="c924d-123">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="c924d-124">**協力廠商資料類型**</span><span class="sxs-lookup"><span data-stu-id="c924d-124">**Third-party data type**</span></span>|<span data-ttu-id="c924d-125">**屬性值 `itemclass:`**</span><span class="sxs-lookup"><span data-stu-id="c924d-125">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c924d-126">目的</span><span class="sxs-lookup"><span data-stu-id="c924d-126">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="c924d-127">American Idol</span><span class="sxs-lookup"><span data-stu-id="c924d-127">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="c924d-128">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="c924d-128">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="c924d-129">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="c924d-129">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="c924d-130">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="c924d-130">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="c924d-131">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c924d-131">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="c924d-132">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c924d-132">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="c924d-133">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c924d-133">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="c924d-134">Axs 預留位置</span><span class="sxs-lookup"><span data-stu-id="c924d-134">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="c924d-135">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c924d-135">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="c924d-136">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="c924d-136">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="c924d-137">Bearshare</span><span class="sxs-lookup"><span data-stu-id="c924d-137">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="c924d-138">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="c924d-138">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="c924d-139">黑 莓</span><span class="sxs-lookup"><span data-stu-id="c924d-139">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="c924d-140">BlackBerry 通話記錄</span><span class="sxs-lookup"><span data-stu-id="c924d-140">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="c924d-141">BlackBerry 信使</span><span class="sxs-lookup"><span data-stu-id="c924d-141">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="c924d-142">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="c924d-142">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="c924d-143">BlackBerry 短信</span><span class="sxs-lookup"><span data-stu-id="c924d-143">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="c924d-144">彭博</span><span class="sxs-lookup"><span data-stu-id="c924d-144">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="c924d-145">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="c924d-145">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="c924d-146">Bloomberg 訊息</span><span class="sxs-lookup"><span data-stu-id="c924d-146">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="c924d-147">Box</span><span class="sxs-lookup"><span data-stu-id="c924d-147">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="c924d-148">Cisco IM &amp; 顯示伺服器</span><span class="sxs-lookup"><span data-stu-id="c924d-148">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="c924d-149">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c924d-149">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="c924d-150">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c924d-150">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="c924d-151">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="c924d-151">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="c924d-152">Facebook</span><span class="sxs-lookup"><span data-stu-id="c924d-152">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="c924d-153">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c924d-153">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="c924d-154">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c924d-154">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="c924d-155">Flickr</span><span class="sxs-lookup"><span data-stu-id="c924d-155">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="c924d-156">Gnutella</span><span class="sxs-lookup"><span data-stu-id="c924d-156">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="c924d-157">Google +</span><span class="sxs-lookup"><span data-stu-id="c924d-157">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="c924d-158">Google 交談</span><span class="sxs-lookup"><span data-stu-id="c924d-158">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="c924d-159">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="c924d-159">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="c924d-160">HipChat</span><span class="sxs-lookup"><span data-stu-id="c924d-160">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="c924d-161">Hopster</span><span class="sxs-lookup"><span data-stu-id="c924d-161">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="c924d-162">HubConnex</span><span class="sxs-lookup"><span data-stu-id="c924d-162">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="c924d-163">IBM 連線</span><span class="sxs-lookup"><span data-stu-id="c924d-163">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="c924d-164">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="c924d-164">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="c924d-165">ICE 聊天</span><span class="sxs-lookup"><span data-stu-id="c924d-165">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="c924d-166">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="c924d-166">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="c924d-167">Instagram</span><span class="sxs-lookup"><span data-stu-id="c924d-167">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="c924d-168">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c924d-168">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="c924d-169">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="c924d-169">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="c924d-170">Irc</span><span class="sxs-lookup"><span data-stu-id="c924d-170">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="c924d-171">搖擺</span><span class="sxs-lookup"><span data-stu-id="c924d-171">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="c924d-172">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="c924d-172">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="c924d-173">Jxta</span><span class="sxs-lookup"><span data-stu-id="c924d-173">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="c924d-174">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c924d-174">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="c924d-175">MFTP</span><span class="sxs-lookup"><span data-stu-id="c924d-175">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="c924d-176">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="c924d-176">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="c924d-177">構思對齊</span><span class="sxs-lookup"><span data-stu-id="c924d-177">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="c924d-178">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="c924d-178">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="c924d-179">Msn</span><span class="sxs-lookup"><span data-stu-id="c924d-179">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="c924d-180">Myspace</span><span class="sxs-lookup"><span data-stu-id="c924d-180">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="c924d-181">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="c924d-181">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="c924d-182">OpenNap</span><span class="sxs-lookup"><span data-stu-id="c924d-182">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="c924d-183">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c924d-183">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="c924d-184">樞紐</span><span class="sxs-lookup"><span data-stu-id="c924d-184">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="c924d-185">Qq</span><span class="sxs-lookup"><span data-stu-id="c924d-185">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="c924d-186">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c924d-186">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="c924d-187">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c924d-187">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="c924d-188">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="c924d-188">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="c924d-189">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c924d-189">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="c924d-190">SoftEther</span><span class="sxs-lookup"><span data-stu-id="c924d-190">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="c924d-191">Squawker</span><span class="sxs-lookup"><span data-stu-id="c924d-191">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="c924d-192">交響樂</span><span class="sxs-lookup"><span data-stu-id="c924d-192">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="c924d-193">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c924d-193">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="c924d-194">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="c924d-194">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="c924d-195">Tor</span><span class="sxs-lookup"><span data-stu-id="c924d-195">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="c924d-196">TTT</span><span class="sxs-lookup"><span data-stu-id="c924d-196">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="c924d-197">Twitter</span><span class="sxs-lookup"><span data-stu-id="c924d-197">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="c924d-198">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="c924d-198">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="c924d-199">Vimeo</span><span class="sxs-lookup"><span data-stu-id="c924d-199">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="c924d-200">WinMX</span><span class="sxs-lookup"><span data-stu-id="c924d-200">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="c924d-201">Winny</span><span class="sxs-lookup"><span data-stu-id="c924d-201">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="c924d-202">雅虎！</span><span class="sxs-lookup"><span data-stu-id="c924d-202">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="c924d-203">Yammer</span><span class="sxs-lookup"><span data-stu-id="c924d-203">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="c924d-204">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c924d-204">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="c924d-205">YouTube</span><span class="sxs-lookup"><span data-stu-id="c924d-205">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
