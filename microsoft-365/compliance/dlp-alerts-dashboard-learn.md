---
title: 深入瞭解資料遺失防護警示儀表板
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解資料遺失防護警示和警示儀表板。
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760702"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a><span data-ttu-id="e5a18-103">深入瞭解資料遺失防護警示儀表板</span><span class="sxs-lookup"><span data-stu-id="e5a18-103">Learn about the data loss prevention Alerts dashboard</span></span>

<span data-ttu-id="e5a18-104">當資料遺失防護中的準則 (DLP) 原則與使用者對機密專案所採取的動作相符時，該原則就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="e5a18-104">When the criteria in a Data loss prevention (DLP) policy is matched by the actions a user is taking on a sensitive item, the policy can generate an alert.</span></span> <span data-ttu-id="e5a18-105">這可能會產生大量的警示。</span><span class="sxs-lookup"><span data-stu-id="e5a18-105">This can result in a high volume of alerts.</span></span> <span data-ttu-id="e5a18-106">DLP 警示會收集于警示儀表板中。</span><span class="sxs-lookup"><span data-stu-id="e5a18-106">DLP alerts are collected in the alerts dashboard.</span></span> <span data-ttu-id="e5a18-107">[警示] 儀表板為您提供單一位置，可對原則相符的所有詳細資料執行深入調查。</span><span class="sxs-lookup"><span data-stu-id="e5a18-107">The alerts dashboard gives you a single place to go to perform a deep investigation of all the details regarding the policy match.</span></span>  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a><span data-ttu-id="e5a18-108">工作負載</span><span class="sxs-lookup"><span data-stu-id="e5a18-108">Workloads</span></span>

<span data-ttu-id="e5a18-109">「 [Dlp 警示管理」儀表板](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)的 [Microsoft 365 規範中心](https://compliance.microsoft.com/)，顯示這些工作負載上 dlp 原則的警示：</span><span class="sxs-lookup"><span data-stu-id="e5a18-109">The [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), shows alerts for DLP policies on these workloads:</span></span>

- <span data-ttu-id="e5a18-110">Exchange</span><span class="sxs-lookup"><span data-stu-id="e5a18-110">Exchange</span></span>
- <span data-ttu-id="e5a18-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e5a18-111">SharePoint</span></span>
- <span data-ttu-id="e5a18-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e5a18-112">OneDrive</span></span>
- <span data-ttu-id="e5a18-113">Teams</span><span class="sxs-lookup"><span data-stu-id="e5a18-113">Teams</span></span>
- <span data-ttu-id="e5a18-114">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="e5a18-114">Windows 10 devices</span></span> 

> [!TIP]
> <span data-ttu-id="e5a18-115">使用適用于[小組 dlp](dlp-microsoft-teams.md)之[端點 dlp](endpoint-dlp-learn-about.md)的客戶，將會看到其 endpoint Dlp 原則警示和團隊 dlp 警示管理儀表板中的 dlp 原則警示。</span><span class="sxs-lookup"><span data-stu-id="e5a18-115">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

## <a name="single-alert-and-aggregate-alert"></a><span data-ttu-id="e5a18-116">單一警示和匯總警示</span><span class="sxs-lookup"><span data-stu-id="e5a18-116">Single alert and aggregate alert</span></span>

<span data-ttu-id="e5a18-117">您可以在 DLP 原則中設定兩種警示類型。</span><span class="sxs-lookup"><span data-stu-id="e5a18-117">There are two types of alerts that can be configured in DLP policies.</span></span>

<span data-ttu-id="e5a18-118">**單一事件警示** 一般用於監視低大量的高敏感度事件的原則，例如單一電子郵件，包含10個或更多用戶端在組織外傳送的信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="e5a18-118">**Single-event alerts** are typically used in policies that monitor for highly sensitive events that occur in a low volume, like a single email with 10 or more customer credit card numbers being sent outside your organization.</span></span>

<span data-ttu-id="e5a18-119">**匯總-事件警報** 一般用於監視在一段時間內的較高磁片區中發生之事件的原則。</span><span class="sxs-lookup"><span data-stu-id="e5a18-119">**Aggregate-event alerts** are typically used in policies that monitor for events that occur in a higher volume over a period of time.</span></span> <span data-ttu-id="e5a18-120">例如，當10個個別電子郵件每個具有一個客戶信用卡號碼的電子郵件在您的組織超過48小時之後傳送時，就會觸發匯總警示。</span><span class="sxs-lookup"><span data-stu-id="e5a18-120">For example, an aggregate alert can be triggered when 10 individual emails each with one customer credit card number is sent outside your org over 48 hours.</span></span>

## <a name="types-of-events"></a><span data-ttu-id="e5a18-121">事件種類</span><span class="sxs-lookup"><span data-stu-id="e5a18-121">Types of events</span></span>

<span data-ttu-id="e5a18-122">以下是與警示相關的一些事件。</span><span class="sxs-lookup"><span data-stu-id="e5a18-122">Here are some of the events associated with an alert.</span></span> <span data-ttu-id="e5a18-123">在 UI 中，您可以選擇特定的事件來查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e5a18-123">In the UI, you can choose a particular event to view its details.</span></span> 

### <a name="event-details"></a><span data-ttu-id="e5a18-124">事件詳細資料</span><span class="sxs-lookup"><span data-stu-id="e5a18-124">Event details</span></span>

|<span data-ttu-id="e5a18-125">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-125">Property name</span></span>  |<span data-ttu-id="e5a18-126">描述</span><span class="sxs-lookup"><span data-stu-id="e5a18-126">Description</span></span>  |<span data-ttu-id="e5a18-127">事件種類</span><span class="sxs-lookup"><span data-stu-id="e5a18-127">Event types</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e5a18-128">ID</span><span class="sxs-lookup"><span data-stu-id="e5a18-128">ID</span></span> |<span data-ttu-id="e5a18-129">與事件相關聯的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e5a18-129">unique ID associated with the event</span></span> |<span data-ttu-id="e5a18-130">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-130">all events</span></span> |
|<span data-ttu-id="e5a18-131">位置</span><span class="sxs-lookup"><span data-stu-id="e5a18-131">Location</span></span> |<span data-ttu-id="e5a18-132">偵測到事件的工作負載</span><span class="sxs-lookup"><span data-stu-id="e5a18-132">workload where the event was detected</span></span>|<span data-ttu-id="e5a18-133">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-133">all events</span></span> |
|<span data-ttu-id="e5a18-134">啟用時間</span><span class="sxs-lookup"><span data-stu-id="e5a18-134">time of activity</span></span>     |<span data-ttu-id="e5a18-135">符合 DLP 原則之準則的使用者啟用時間</span><span class="sxs-lookup"><span data-stu-id="e5a18-135">time of the user activity that matched the criteria of the DLP policy</span></span> |

### <a name="impacted-entities"></a><span data-ttu-id="e5a18-136">受影響實體</span><span class="sxs-lookup"><span data-stu-id="e5a18-136">Impacted entities</span></span>

|<span data-ttu-id="e5a18-137">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-137">Property name</span></span> |<span data-ttu-id="e5a18-138">描述</span><span class="sxs-lookup"><span data-stu-id="e5a18-138">Description</span></span>| <span data-ttu-id="e5a18-139">事件種類</span><span class="sxs-lookup"><span data-stu-id="e5a18-139">Event types</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e5a18-140">使用者</span><span class="sxs-lookup"><span data-stu-id="e5a18-140">user</span></span> | <span data-ttu-id="e5a18-141">採取導致原則符合之動作的使用者</span><span class="sxs-lookup"><span data-stu-id="e5a18-141">user who took the action that caused the policy match</span></span> | <span data-ttu-id="e5a18-142">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-142">all events</span></span>|
|<span data-ttu-id="e5a18-143">主機 名</span><span class="sxs-lookup"><span data-stu-id="e5a18-143">hostname</span></span> | <span data-ttu-id="e5a18-144">發生 DLP 原則比對之電腦的主機名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-144">host name of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="e5a18-145">裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-145">device events</span></span>|
|<span data-ttu-id="e5a18-146">IP 位址</span><span class="sxs-lookup"><span data-stu-id="e5a18-146">IP address</span></span> | <span data-ttu-id="e5a18-147">發生 DLP 原則比對之電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e5a18-147">IP address of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="e5a18-148">裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-148">device events</span></span>|
|<span data-ttu-id="e5a18-149">sha1</span><span class="sxs-lookup"><span data-stu-id="e5a18-149">sha1</span></span> |<span data-ttu-id="e5a18-150">檔 SHA-1 雜湊</span><span class="sxs-lookup"><span data-stu-id="e5a18-150">SHA-1 hash of the file</span></span> | <span data-ttu-id="e5a18-151">裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-151">device events</span></span>|
|<span data-ttu-id="e5a18-152">sha256</span><span class="sxs-lookup"><span data-stu-id="e5a18-152">sha256</span></span> | <span data-ttu-id="e5a18-153">檔 SHA-256 雜湊</span><span class="sxs-lookup"><span data-stu-id="e5a18-153">SHA-256 hash of the file</span></span> | <span data-ttu-id="e5a18-154">裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-154">device events</span></span>|
|<span data-ttu-id="e5a18-155">MDATP 裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="e5a18-155">MDATP device ID</span></span> | <span data-ttu-id="e5a18-156">端點裝置 MDATP 識別碼</span><span class="sxs-lookup"><span data-stu-id="e5a18-156">endpoint device MDATP ID</span></span>|
|<span data-ttu-id="e5a18-157">檔案大小</span><span class="sxs-lookup"><span data-stu-id="e5a18-157">file size</span></span> | <span data-ttu-id="e5a18-158">檔案大小</span><span class="sxs-lookup"><span data-stu-id="e5a18-158">size of the file</span></span>| <span data-ttu-id="e5a18-159">SharePoint、OneDrive 和裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-159">SharePoint, OneDrive, and device events</span></span>|
|<span data-ttu-id="e5a18-160">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="e5a18-160">file path</span></span> | <span data-ttu-id="e5a18-161">與 DLP 原則相符相關之專案的絕對路徑</span><span class="sxs-lookup"><span data-stu-id="e5a18-161">the absolute path of the item involved with the DLP policy match</span></span> | <span data-ttu-id="e5a18-162">SharePoint、OneDrive 和裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-162">SharePoint, OneDrive, and devices events</span></span>|
|<span data-ttu-id="e5a18-163">電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="e5a18-163">email recipients</span></span> |<span data-ttu-id="e5a18-164">如果電子郵件是符合 DLP 原則的敏感專案，此欄位會包含該電子郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="e5a18-164">if an email was the sensitive item that matched the DLP policy, this field includes the recipients of that email</span></span>| <span data-ttu-id="e5a18-165">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-165">Exchange events</span></span>|
|<span data-ttu-id="e5a18-166">電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="e5a18-166">email subject</span></span> |<span data-ttu-id="e5a18-167">符合 DLP 原則的電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="e5a18-167">subject of the email that matched the DLP policy</span></span> |<span data-ttu-id="e5a18-168">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-168">Exchange events</span></span>|
|<span data-ttu-id="e5a18-169">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="e5a18-169">email attachments</span></span> | <span data-ttu-id="e5a18-170">符合 DLP 原則之電子郵件中的附件名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-170">names of the attachments in the email that matched the DLP policy</span></span>| <span data-ttu-id="e5a18-171">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-171">Exchange events</span></span>|
|<span data-ttu-id="e5a18-172">網站擁有者</span><span class="sxs-lookup"><span data-stu-id="e5a18-172">site owner</span></span> |<span data-ttu-id="e5a18-173">網站擁有者的名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-173">name of the site owner</span></span>| <span data-ttu-id="e5a18-174">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-174">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="e5a18-175">網站 URL</span><span class="sxs-lookup"><span data-stu-id="e5a18-175">site URL</span></span> |<span data-ttu-id="e5a18-176">已發生 DLP 原則的 SharePoint 或 OneDrive 網站的完整 URL</span><span class="sxs-lookup"><span data-stu-id="e5a18-176">full of the URL of the SharePoint or OneDrive site where the DLP policy match occurred</span></span> |<span data-ttu-id="e5a18-177">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-177">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="e5a18-178">已建立檔</span><span class="sxs-lookup"><span data-stu-id="e5a18-178">file created</span></span> |<span data-ttu-id="e5a18-179">建立符合 DLP 原則的檔案時的時間</span><span class="sxs-lookup"><span data-stu-id="e5a18-179">time of creation of the file that matched the DLP policy</span></span> |<span data-ttu-id="e5a18-180">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-180">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="e5a18-181">上次修改的檔案</span><span class="sxs-lookup"><span data-stu-id="e5a18-181">file last modified</span></span> | <span data-ttu-id="e5a18-182">已變更符合 DLP 原則的檔案的最後時間</span><span class="sxs-lookup"><span data-stu-id="e5a18-182">the last time that the file that matched the DLP policy was changed</span></span> | <span data-ttu-id="e5a18-183">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-183">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="e5a18-184">檔案大小</span><span class="sxs-lookup"><span data-stu-id="e5a18-184">file size</span></span> | <span data-ttu-id="e5a18-185">符合 DLP 原則的檔案大小</span><span class="sxs-lookup"><span data-stu-id="e5a18-185">size of the file that matched the DLP policy</span></span> |<span data-ttu-id="e5a18-186">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-186">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="e5a18-187">檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="e5a18-187">file owner</span></span> |<span data-ttu-id="e5a18-188">符合 DLP 原則的檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="e5a18-188">owner of the file that matched the DLP policy</span></span> |<span data-ttu-id="e5a18-189">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-189">SharePoint and OneDrive events</span></span>|  

### <a name="policy-details"></a><span data-ttu-id="e5a18-190">原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="e5a18-190">Policy details</span></span>

|<span data-ttu-id="e5a18-191">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-191">Property name</span></span> |<span data-ttu-id="e5a18-192">描述</span><span class="sxs-lookup"><span data-stu-id="e5a18-192">Description</span></span> |<span data-ttu-id="e5a18-193">事件種類</span><span class="sxs-lookup"><span data-stu-id="e5a18-193">Event types</span></span> |
|---------|---------|---------|
|<span data-ttu-id="e5a18-194">符合的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="e5a18-194">DLP policy matched</span></span> |<span data-ttu-id="e5a18-195">相符的 DLP 原則名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-195">name of the matched DLP policy</span></span> |<span data-ttu-id="e5a18-196">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-196">all events</span></span>|
|<span data-ttu-id="e5a18-197">符合規則</span><span class="sxs-lookup"><span data-stu-id="e5a18-197">rule matched</span></span> |<span data-ttu-id="e5a18-198">符合的 DLP 原則規則名稱</span><span class="sxs-lookup"><span data-stu-id="e5a18-198">name of the matched DLP policy rule</span></span> |<span data-ttu-id="e5a18-199">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-199">all events</span></span>|
|<span data-ttu-id="e5a18-200">偵測到)  (SIT 的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="e5a18-200">sensitive information types (SIT) detected</span></span>|<span data-ttu-id="e5a18-201">以 DLP 原則相符的一部分偵測到的</span><span class="sxs-lookup"><span data-stu-id="e5a18-201">SITs that were detected as part of the DLP policy match</span></span> |<span data-ttu-id="e5a18-202">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-202">all events</span></span>|
|<span data-ttu-id="e5a18-203">採取的動作</span><span class="sxs-lookup"><span data-stu-id="e5a18-203">actions taken</span></span> |<span data-ttu-id="e5a18-204">導致 DLP 原則相符所採取的動作</span><span class="sxs-lookup"><span data-stu-id="e5a18-204">actions that were taken that caused the DLP policy match</span></span>| <span data-ttu-id="e5a18-205">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-205">all events</span></span>|
|<span data-ttu-id="e5a18-206">侵犯動作</span><span class="sxs-lookup"><span data-stu-id="e5a18-206">violating action</span></span> | <span data-ttu-id="e5a18-207">引發 DLP 警示之端點裝置上的動作</span><span class="sxs-lookup"><span data-stu-id="e5a18-207">action on the endpoint device that raised the DLP alert</span></span>| <span data-ttu-id="e5a18-208">裝置事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-208">device events</span></span> | 
|<span data-ttu-id="e5a18-209">使用者 overrode 原則</span><span class="sxs-lookup"><span data-stu-id="e5a18-209">user overrode policy</span></span> |<span data-ttu-id="e5a18-210">使用者已透過原則提示覆寫原則</span><span class="sxs-lookup"><span data-stu-id="e5a18-210">did the user override the policy via a policy tip</span></span> | <span data-ttu-id="e5a18-211">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-211">all events</span></span>|
|<span data-ttu-id="e5a18-212">使用覆寫對齊</span><span class="sxs-lookup"><span data-stu-id="e5a18-212">use override justification</span></span> |<span data-ttu-id="e5a18-213">使用者為覆寫所提供的原因文字</span><span class="sxs-lookup"><span data-stu-id="e5a18-213">the text of the reason provided by the user for the override</span></span> | <span data-ttu-id="e5a18-214">所有事件</span><span class="sxs-lookup"><span data-stu-id="e5a18-214">all events</span></span>|   

## <a name="see-also"></a><span data-ttu-id="e5a18-215">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5a18-215">See Also</span></span>

- [<span data-ttu-id="e5a18-216">開始使用資料遺失防護警示儀表板</span><span class="sxs-lookup"><span data-stu-id="e5a18-216">Get started with the data loss prevention alert dashboard</span></span>](dlp-alerts-dashboard-get-started.md)
- [<span data-ttu-id="e5a18-217">從資料遺失防護開始的位置</span><span class="sxs-lookup"><span data-stu-id="e5a18-217">Where to start with data loss prevention</span></span>](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)