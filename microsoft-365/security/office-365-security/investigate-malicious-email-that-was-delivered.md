---
title: '尋找和調查已傳遞 Office 365 中的惡意電子郵件、 修復，補救、 修復， '
keywords: TIMailData-內嵌圖案，安全性事件事件，ATP PowerShell 電子郵件的惡意程式碼、 危害使用者釣魚程式的電子郵件、 惡意程式碼的電子郵件、 讀取電子郵件標頭、 讀取標頭、 開啟電子郵件標頭
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威脅調查及回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 5fe9e06a582d72b46c4f90f13aee283050a06253
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088702"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="7ddb3-104">調查並修復 Office 365 中已傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="7ddb3-104">Investigate and remediate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="7ddb3-105">[Office 365 進階威脅防護](office-365-atp.md)可讓您調查放入風險，貴組織的人員的活動，並採取動作來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="7ddb3-106">例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="7ddb3-107">您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7ddb3-108">開始之前...</span><span class="sxs-lookup"><span data-stu-id="7ddb3-108">Before you begin...</span></span>

<span data-ttu-id="7ddb3-109">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="7ddb3-110">您的組織有[Office 365 進階威脅防護](office-365-atp.md)，並[將授權指派給使用者](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="7ddb3-111">[Office 365 稽核記錄](../../compliance/turn-audit-log-search-on-or-off.md)已為您的組織。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-111">[Office 365 audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="7ddb3-112">貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="7ddb3-113">請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="7ddb3-114">您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-114">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7ddb3-115">請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-115">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="7ddb3-116">某些動作，您也必須具備新預覽角色指派。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="7ddb3-117">預覽角色權限</span><span class="sxs-lookup"><span data-stu-id="7ddb3-117">Preview role permissions</span></span>

<span data-ttu-id="7ddb3-118">若要執行某些動作，例如檢視郵件標頭或下載電子郵件訊息內容，您必須呼叫*預覽*新增至另一個適當的 Office 365 角色群組的新角色。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate Office 365 role group.</span></span> <span data-ttu-id="7ddb3-119">下表釐清所需的角色和權限。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="7ddb3-120">活動</span><span class="sxs-lookup"><span data-stu-id="7ddb3-120">Activity</span></span>  |<span data-ttu-id="7ddb3-121">角色群組</span><span class="sxs-lookup"><span data-stu-id="7ddb3-121">Role group</span></span> |<span data-ttu-id="7ddb3-122">所需的預覽角色？</span><span class="sxs-lookup"><span data-stu-id="7ddb3-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ddb3-123">使用分析威脅威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="7ddb3-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="7ddb3-124">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-124">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7ddb3-125">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-125">Security Administrator</span></span> <br> <span data-ttu-id="7ddb3-126">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="7ddb3-126">Security Reader</span></span>     | <span data-ttu-id="7ddb3-127">否</span><span class="sxs-lookup"><span data-stu-id="7ddb3-127">No</span></span>   |
|<span data-ttu-id="7ddb3-128">使用檢視的電子郵件，以及預覽標頭和下載隔離區的電子郵件威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="7ddb3-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="7ddb3-129">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-129">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7ddb3-130">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-130">Security Administrator</span></span> <br><span data-ttu-id="7ddb3-131">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="7ddb3-131">Security Reader</span></span>   |       <span data-ttu-id="7ddb3-132">否</span><span class="sxs-lookup"><span data-stu-id="7ddb3-132">No</span></span>  |
|<span data-ttu-id="7ddb3-133">使用威脅總管檢視標頭，並下載傳遞至信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="7ddb3-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="7ddb3-134">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-134">Office 365 Global Administrator</span></span> <br><span data-ttu-id="7ddb3-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7ddb3-135">Security Administrator</span></span> <br> <span data-ttu-id="7ddb3-136">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="7ddb3-136">Security Reader</span></span> <br> <span data-ttu-id="7ddb3-137">預覽</span><span class="sxs-lookup"><span data-stu-id="7ddb3-137">Preview</span></span>   |   <span data-ttu-id="7ddb3-138">是</span><span class="sxs-lookup"><span data-stu-id="7ddb3-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="7ddb3-139">*預覽*是角色並不是角色群組。「 預覽 」 角色必須新增至現有的角色群組，以 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="7ddb3-140">Office 365 全域系統管理員角色指派的 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))，並安全性管理員和安全性讀取者 」 角色指派 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-140">The Office 365 Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="7ddb3-141">若要深入了解角色和權限，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-141">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="7ddb3-142">尋找並刪除可疑的電子郵件的郵件傳遞</span><span class="sxs-lookup"><span data-stu-id="7ddb3-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="7ddb3-143">威脅總管是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="7ddb3-144">下列程序著重於使用 Explorer 來尋找並從收件者的信箱刪除惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-144">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

1. <span data-ttu-id="7ddb3-145">**瀏覽至威脅總管**： 移至[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-145">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="7ddb3-146">這會帶您前往安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-146">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="7ddb3-147">在左的導覽快速-啟動中，選擇 [**威脅管理** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-147">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![總管] 中的傳遞巨集指令與傳遞位置欄位。](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. <span data-ttu-id="7ddb3-149">**威脅總管中的檢視**： 在 [**檢視**] 功能表中，選擇 [**所有電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-149">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威脅總管檢視] 功能表中，與電子郵件-惡意程式碼、 釣魚程式、 送出資料及所有的電子郵件選項，也內容-惡意程式碼。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="7ddb3-151">*惡意程式碼*檢視目前預設值，並會擷取電子郵件在偵測到惡意程式碼威脅。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-151">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="7ddb3-152">釣魚程式相同的方式運作的*釣魚程式*檢視。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-152">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="7ddb3-153">不過，*所有電子郵件*] 檢視會列出每個組織中，所收到的郵件是否或未偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-153">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="7ddb3-154">您可以想像，這會是大量資料，這就是為什麼這個檢視會顯示套用要求篩選器的預留位置。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-154">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="7ddb3-155">（此檢視是僅供 ATP P2 客戶）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-155">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="7ddb3-156">*提交*] 檢視會顯示所有的郵件提交系統管理員或使用者回報給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-156">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="7ddb3-157">**搜尋和威脅總管中的篩選**： 篩選顯示在頁面頂端的可協助系統管理員在其調查中的 [搜尋] 列中。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-157">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="7ddb3-158">請注意，多個篩選可以套用在相同的時間，並新增至篩選器來縮小搜尋多個以逗號分隔值。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-158">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="7ddb3-159">請記得：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-159">Remember:</span></span>
    - <span data-ttu-id="7ddb3-160">篩選器完全符合在大部分的篩選條件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-160">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="7ddb3-161">主旨篩選會使用包含查詢。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-161">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="7ddb3-162">URL 篩選器的運作或者沒有通訊協定 (ex。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-162">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="7ddb3-163">https)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-163">https).</span></span>
    - <span data-ttu-id="7ddb3-164">URL 網域上、 URL 路徑及 URL 的網域和路徑篩選不需要一種通訊協定來篩選。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-164">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="7ddb3-165">每次變更篩選值，以取得相關的結果，您必須按一下 [重新整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-165">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="7ddb3-166">**進階篩選**： 使用這些篩選器，您可以建立複雜的查詢，並篩選您的資料集。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-166">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="7ddb3-167">按一下 [*進階篩選*] 開啟彈出式選項。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-167">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="7ddb3-168">進階篩選是另一項絕佳搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-168">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="7ddb3-169">布林值**不可**篩選具有已引進*收件者*、*寄件者*和*寄件者網域*以允許系統管理員来調查藉由排除值。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-169">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="7ddb3-170">此選項會出現在*不包含*的 selection 參數。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-170">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="7ddb3-171">**不**會讓系統管理員排除警示的信箱，預設回覆信箱從其調查，也很適合其中系統管理員搜尋特定主題的情況下 (主旨 ="注意 」) 其中收件者可以設定成 [*無 defaultMail@contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-171">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail@contoso.com*.</span></span> <span data-ttu-id="7ddb3-172">這是實際值搜尋。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-172">This is an exact value search.</span></span>

   ![收件者-'不包含' 進階篩選器。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="7ddb3-174">*篩選由小時*可協助貴組織的安全性小組快速向下切入。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-174">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="7ddb3-175">最短的允許的時間期間是 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-175">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="7ddb3-176">如果您可以縮小時間範圍可疑採取動作 （例如它發生 3 小時前），這會限制內容，並協助找出問題。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-176">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

  ![篩選時數] 選項來縮小的量資料安全性小組必須處理程序，以及其最短的持續時間是 30 分鐘。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="7ddb3-178">**威脅總管] 中的欄位**： 威脅總管公開*傳遞巨集指令*、*傳遞位置*、*特殊巨集指令*、*方向*、*會覆寫*，以及*URL 威脅*等更多的安全性相關的郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-178">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="7ddb3-179">它也可讓貴組織的安全性小組，以調查以較高的確實方式。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-179">It also allows your organization's security team to investigate with a higher certainty.</span></span> 

    <span data-ttu-id="7ddb3-180">*傳遞動作*是因為現有的原則或偵測電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-180">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7ddb3-181">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-181">Here are the possible actions an email can take:</span></span>
    - <span data-ttu-id="7ddb3-182">**已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-182">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="7ddb3-183">**Junked** （已傳遞至垃圾郵件） – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除的資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-183">**Junked** (Delivered to junk)– email was sent to either user’s junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="7ddb3-184">**封鎖**– 任何電子郵件遭到隔離的郵件，會失敗，或者已卸除。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-184">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7ddb3-185">（這是完全無法存取的使用者）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-185">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="7ddb3-186">**取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件已惡意</span><span class="sxs-lookup"><span data-stu-id="7ddb3-186">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="7ddb3-187">**傳遞位置**： 傳遞位置篩選器是可用以協助系統管理員了解其中可疑惡意郵件結束延展及在其上所採取的行動。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-187">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="7ddb3-188">產生的資料可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-188">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="7ddb3-189">可能的傳遞位置如下：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-189">Possible delivery locations are:</span></span>
    - <span data-ttu-id="7ddb3-190">**收件匣或資料夾**– 電子郵件是在收件匣] 或 [特定的資料夾，根據您的電子郵件規則。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-190">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="7ddb3-191">**在內部或外部**– 信箱定域機組中不存在，但內部。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-191">**On-prem or external** – The mailbox doesn’t exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="7ddb3-192">**垃圾郵件資料夾**– 電子郵件是在使用者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-192">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="7ddb3-193">**刪除的項目] 資料夾**– 電子郵件是在使用者的已刪除項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-193">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="7ddb3-194">**隔離**-隔離區，而不是在使用者信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-194">**Quarantine** – The email in quarantine, and not in a user’s mailbox.</span></span>
    - <span data-ttu-id="7ddb3-195">**失敗**– 電子郵件無法連到信箱。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-195">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="7ddb3-196">**丟棄**– 電子郵件的某處遺失，在 [郵件流程。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-196">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="7ddb3-197">**Directionality**： 此選項可讓您的安全性作業小組，以篩選 '' 的郵件來自，或方向將要。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-197">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="7ddb3-198">Directionality 值是*輸入*、*輸出*中，與*組織內部*（對應至郵件進入從您組織外部、 傳送超出您的組織，或傳送在內部到您組織中，分別）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-198">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="7ddb3-199">這項資訊可以幫助瓶頸詐騙及模擬，安全性作業小組，因為方向不相符的值 （例如。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-199">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="7ddb3-200">*輸入*)，以及 （哪一個*出現*的內部網域） 將會明顯的寄件者網域 ！</span><span class="sxs-lookup"><span data-stu-id="7ddb3-200">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="7ddb3-201">Directionality 值不同，且可以與不同，郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-201">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="7ddb3-202">結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-202">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7ddb3-203">**會覆寫**： 此篩選採用資訊會出現在郵件的詳細資料] 索引標籤上，使用它來公開其中組織，或使用者原則，允許與封鎖的郵件都已*覆寫*。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-203">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="7ddb3-204">關於此篩選器的重點是它可以協助貴組織的安全性小組，請參閱多少可疑的電子郵件已傳遞因為組態。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-204">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="7ddb3-205">這可以讓它們修改機會允許與封鎖視。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-205">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="7ddb3-206">此篩選器的此結果集可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-206">This result set of this filter can be exported to spreadsheet.</span></span>

|<span data-ttu-id="7ddb3-207">威脅總管] 中覆寫</span><span class="sxs-lookup"><span data-stu-id="7ddb3-207">Threat Explorer Overrides</span></span>  | <span data-ttu-id="7ddb3-208">及其所代表的意義</span><span class="sxs-lookup"><span data-stu-id="7ddb3-208">What they mean</span></span>  |
|---------|---------|
|<span data-ttu-id="7ddb3-209">允許組織原則</span><span class="sxs-lookup"><span data-stu-id="7ddb3-209">Allowed by Org Policy</span></span>     |   <span data-ttu-id="7ddb3-210">郵件已允許入信箱，因為組織原則所導入。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-210">Mail was allowed into the mailbox as directed by the organization policy.</span></span>       |
|<span data-ttu-id="7ddb3-211">封鎖的組織原則</span><span class="sxs-lookup"><span data-stu-id="7ddb3-211">Blocked by Org policy</span></span>      |  <span data-ttu-id="7ddb3-212">依照指示組織原則所傳遞到信箱已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-212">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>    |
|<span data-ttu-id="7ddb3-213">Org 原則所封鎖的副檔名</span><span class="sxs-lookup"><span data-stu-id="7ddb3-213">File extension blocked by Org Policy</span></span>     | <span data-ttu-id="7ddb3-214">在傳遞至信箱已封鎖檔案類型為導向的組織原則。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-214">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>        |
|<span data-ttu-id="7ddb3-215">允許使用者原則</span><span class="sxs-lookup"><span data-stu-id="7ddb3-215">Allowed by User Policy</span></span>     | <span data-ttu-id="7ddb3-216">郵件已允許入信箱，因為使用者原則所導入。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-216">Mail was allowed into the mailbox as directed by the user policy.</span></span>        |
|<span data-ttu-id="7ddb3-217">封鎖的使用者原則</span><span class="sxs-lookup"><span data-stu-id="7ddb3-217">Blocked by User Policy</span></span>     | <span data-ttu-id="7ddb3-218">依照指示使用者原則所傳遞到信箱已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-218">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>        |

<span data-ttu-id="7ddb3-219">**URL 威脅**： URL 威脅欄位已包含在電子郵件給指出 URL 所呈現的威脅的 [*詳細資料*] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-219">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="7ddb3-220">URL 所呈現的威脅可以包含*惡意程式碼*、*釣魚程式*或*垃圾郵件*，並*沒有威脅*與 URL 會像是*無*威脅] 區段中。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-220">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="7ddb3-221">**電子郵件 [時間表] 檢視**： 安全性作業小組可能需要太深-探討調查的電子郵件詳細資料來進一步。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-221">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="7ddb3-222">電子郵件時間表可讓系統管理員來檢視在傳遞至後續傳遞電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-222">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="7ddb3-223">若要檢視的電子郵件時間表，按一下主旨的電子郵件訊息，，，然後按一下 [電子郵件時間表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-223">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="7ddb3-224">（它出現在像摘要] 或 [詳細資料] 面板上的其他標題之間）。這些結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-224">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7ddb3-225">顯示所有傳遞和電子郵件的後續傳遞事件的資料表會開啟電子郵件時間表。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-225">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="7ddb3-226">如果沒有電子郵件上的沒有進一步動作，您應該會看到原始傳遞表示結果，例如*封鎖*，與 verdict 像*釣魚程式*的單一事件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-226">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="7ddb3-227">系統管理員可以匯出整個電子郵件時間表，包括所有的詳細資料] 索引標籤和電子郵件 （例如，主旨、 寄件者、 收件者、 網路和訊息識別碼）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-227">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="7ddb3-228">電子郵件時間表剪下向下上隨機化因為較少的時間所花費的嘗試了解事件發生於由於電子郵件抵達檢查不同的位置。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-228">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="7ddb3-229">當多個事件會發生，在或接近，同時在一封電子郵件時，這些事件顯示在 [時間表] 檢視。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-229">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="7ddb3-230">**預覽 / 下載**： 威脅總管提供安全性作業小組他們需要調查可疑的電子郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-230">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="7ddb3-231">您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-231">Your security operations team can either:</span></span>

    - <span data-ttu-id="7ddb3-232">[請檢查傳遞動作及位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-232">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="7ddb3-233">[檢視您的電子郵件的時間表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-233">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

    ##### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="7ddb3-234">請檢查傳遞動作及位置</span><span class="sxs-lookup"><span data-stu-id="7ddb3-234">Check the delivery action and location</span></span>

    <span data-ttu-id="7ddb3-235">在 [[威脅總管 （和即時偵測的資訊）](threat-explorer.md)，您現在可以**傳遞巨集指令**並**傳遞位置**而不是前者**傳遞狀態**] 欄中的資料行。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-235">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="7ddb3-236">這會導致更完整的地方您的電子郵件訊息園地圖片。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-236">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="7ddb3-237">組件的這項變更的目標是要讓調查安全性作業小組，更容易，但最終結果知道一眼問題電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-237">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

    <span data-ttu-id="7ddb3-238">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-238">Delivery Status is now broken out into two columns:</span></span>

    - <span data-ttu-id="7ddb3-239">**傳遞動作**-這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="7ddb3-239">**Delivery action** - What is the status of this email?</span></span>

    - <span data-ttu-id="7ddb3-240">**傳遞位置**-其中這封電子郵件路由傳送結果？</span><span class="sxs-lookup"><span data-stu-id="7ddb3-240">**Delivery location** - Where was this email routed as a result?</span></span>

    <span data-ttu-id="7ddb3-241">傳遞動作是因為現有的原則或偵測電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-241">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7ddb3-242">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-242">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="7ddb3-243">**已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-243">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

    - <span data-ttu-id="7ddb3-244">**Junked** – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-244">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

    - <span data-ttu-id="7ddb3-245">**封鎖**– 任何電子郵件遭到隔離的郵件，會失敗，或者已卸除。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-245">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7ddb3-246">（這是完全無法存取的使用者）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-246">(This is completely inaccessible by the user.)</span></span>

    - <span data-ttu-id="7ddb3-247">**取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件程式惡意。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-247">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
    <span data-ttu-id="7ddb3-248">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-248">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="7ddb3-249">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-249">It's linked to a Delivery Action.</span></span> <span data-ttu-id="7ddb3-250">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-250">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="7ddb3-251">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="7ddb3-251">Here are the possible values of delivery location:</span></span>

    - <span data-ttu-id="7ddb3-252">**收件匣或資料夾**– 電子郵件是在收件匣或資料夾中 （根據您的電子郵件的規則）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-252">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

    - <span data-ttu-id="7ddb3-253">**在內部或外部**– 信箱不存在於雲端上，但內部。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-253">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

    - <span data-ttu-id="7ddb3-254">**垃圾郵件資料夾**– 電子郵件是在使用者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-254">**Junk folder** – The email is in a user's Junk folder.</span></span>

    - <span data-ttu-id="7ddb3-255">**刪除的項目] 資料夾**– 電子郵件是在使用者的已刪除項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-255">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

    - <span data-ttu-id="7ddb3-256">**隔離**-隔離區，而不是在使用者信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-256">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

    - <span data-ttu-id="7ddb3-257">**失敗**– 電子郵件無法連到信箱。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-257">**Failed** – The email failed to reach the mailbox.</span></span>

    - <span data-ttu-id="7ddb3-258">**丟棄**– 電子郵件會取得某處遺失，在 [郵件流程。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-258">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

     ##### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="7ddb3-259">檢視您的電子郵件的時間表</span><span class="sxs-lookup"><span data-stu-id="7ddb3-259">View the timeline of your email</span></span>
  
     <span data-ttu-id="7ddb3-260">**電子郵件時間表**] 是能方便狩獵安全性作業小組的威脅總管中的欄位。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-260">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="7ddb3-261">當多個事件會發生在或接近同一時間上一封電子郵件時，這些事件顯示在 [時間表] 檢視。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-261">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="7ddb3-262">[**特殊動作**] 欄中擷取某些電子郵件發生後傳遞的事件。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-262">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="7ddb3-263">合併的電子郵件訊息從時間表資訊拍攝後續傳遞任何特殊動作讓系統管理員深入資訊原則和威脅處理 （例如其中已路由傳送郵件，以及在某些情況下，最終評估已）。</span><span class="sxs-lookup"><span data-stu-id="7ddb3-263">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a><span data-ttu-id="7ddb3-264">相關主題</span><span class="sxs-lookup"><span data-stu-id="7ddb3-264">Related topics</span></span>

[<span data-ttu-id="7ddb3-265">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="7ddb3-265">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="7ddb3-266">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="7ddb3-266">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="7ddb3-267">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="7ddb3-267">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
