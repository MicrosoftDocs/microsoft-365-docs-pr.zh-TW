---
title: 調查 Office 365 中傳遞的惡意電子郵件，尋找並調查惡意電子郵件
keywords: TIMailData-Inline，Security 事件，事件，ATP PowerShell，電子郵件惡意程式碼，已遭破壞的使用者，電子郵件網路釣魚程式，電子郵件惡意程式碼，讀取電子郵件標題，讀取標頭，開啟電子郵件頭，特殊動作
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
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
description: 瞭解如何使用威脅調查和回應功能來尋找並調查惡意的電子郵件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7677c1741a173c0528504f0fad67439608845f64
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842937"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="cde57-104">調查 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-104">Investigate malicious email that was delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cde57-105">[Microsoft Defender For Office 365](office-365-atp.md) 可讓您調查讓組織中的人員面臨風險的活動，並採取行動以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="cde57-105">[Microsoft Defender for Office 365](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="cde57-106">例如，如果您是組織的安全性小組的一部分，您可以找出並調查已傳遞的可疑電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="cde57-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="cde57-107">您可以使用 [威脅瀏覽器 (或即時偵測) ](threat-explorer.md)來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cde57-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cde57-108">在 [這裡](remediate-malicious-email-delivered-office-365.md)跳到修正文章。</span><span class="sxs-lookup"><span data-stu-id="cde57-108">Jump to the remediation article [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cde57-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="cde57-109">Before you begin</span></span>

<span data-ttu-id="cde57-110">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="cde57-110">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="cde57-111">您的組織已將 [Microsoft Defender 用於 Office 365](office-365-atp.md) ，而 [授權已指派給使用者](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cde57-111">Your organization has [Microsoft Defender for Office 365](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="cde57-112">您的組織已開啟[審核記錄](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="cde57-112">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="cde57-113">您的組織有為反垃圾郵件、反惡意程式碼、反網路釣魚等定義的原則。</span><span class="sxs-lookup"><span data-stu-id="cde57-113">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="cde57-114">請參閱 [防禦 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="cde57-114">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="cde57-115">您是全域系統管理員，或您已在安全性與合規性中心內指派安全性管理員或搜尋和清除角色 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="cde57-115">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cde57-116">請參閱 [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cde57-116">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="cde57-117">在某些動作中，您也必須已指派新的預覽角色。</span><span class="sxs-lookup"><span data-stu-id="cde57-117">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="cde57-118">預覽角色許可權</span><span class="sxs-lookup"><span data-stu-id="cde57-118">Preview role permissions</span></span>

<span data-ttu-id="cde57-119">若要執行某些動作，例如：查看郵件頭或下載電子郵件內容，您必須將名為 *Preview* 的新角色新增至另一個適當的角色群組。</span><span class="sxs-lookup"><span data-stu-id="cde57-119">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="cde57-120">下表說明必要的角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="cde57-120">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="cde57-121">活動</span><span class="sxs-lookup"><span data-stu-id="cde57-121">Activity</span></span>|<span data-ttu-id="cde57-122">角色群組</span><span class="sxs-lookup"><span data-stu-id="cde57-122">Role group</span></span>|<span data-ttu-id="cde57-123">需要預覽角色？</span><span class="sxs-lookup"><span data-stu-id="cde57-123">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="cde57-124">使用威脅瀏覽器 (和即時偵測) 來分析威脅</span><span class="sxs-lookup"><span data-stu-id="cde57-124">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="cde57-125">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-125">Global Administrator</span></span> <br> <span data-ttu-id="cde57-126">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-126">Security Administrator</span></span> <br> <span data-ttu-id="cde57-127">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="cde57-127">Security Reader</span></span>|<span data-ttu-id="cde57-128">否</span><span class="sxs-lookup"><span data-stu-id="cde57-128">No</span></span>|
|<span data-ttu-id="cde57-129">使用威脅瀏覽器 (和即時偵測) 來查看電子郵件的標頭，以及預覽及下載隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-129">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="cde57-130">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-130">Global Administrator</span></span> <br> <span data-ttu-id="cde57-131">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-131">Security Administrator</span></span> <br><span data-ttu-id="cde57-132">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="cde57-132">Security Reader</span></span>|<span data-ttu-id="cde57-133">否</span><span class="sxs-lookup"><span data-stu-id="cde57-133">No</span></span>|
|<span data-ttu-id="cde57-134">使用威脅瀏覽器來查看標頭，並下載傳送至信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-134">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="cde57-135">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-135">Global Administrator</span></span> <br><span data-ttu-id="cde57-136">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="cde57-136">Security Administrator</span></span> <br> <span data-ttu-id="cde57-137">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="cde57-137">Security Reader</span></span> <br> <span data-ttu-id="cde57-138">預覽</span><span class="sxs-lookup"><span data-stu-id="cde57-138">Preview</span></span>|<span data-ttu-id="cde57-139">是</span><span class="sxs-lookup"><span data-stu-id="cde57-139">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="cde57-140">*Preview* 是角色，不是角色群組;預覽角色必須新增至 Office 365 的現有角色群組。</span><span class="sxs-lookup"><span data-stu-id="cde57-140">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="cde57-141">全域系統管理員角色會指派 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) ，而且安全性管理員和安全性讀取者角色會指派在安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-141">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="cde57-142">若要深入瞭解角色和許可權，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cde57-142">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-suspicious-email-that-was-delivered"></a><span data-ttu-id="cde57-143">尋找已傳遞的可疑電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-143">Find suspicious email that was delivered</span></span>

<span data-ttu-id="cde57-144">威脅瀏覽器是一種強大的報表，可用於多種用途，例如尋找和刪除郵件、識別惡意電子郵件寄件者的 IP 位址，或啟動事件以進一步進行調查。</span><span class="sxs-lookup"><span data-stu-id="cde57-144">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="cde57-145">下列程式著重于使用 Explorer 尋找及刪除收件者信箱中的惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-145">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="cde57-146">瀏覽器中的預設搜尋目前不包含 Zapped 的專案。</span><span class="sxs-lookup"><span data-stu-id="cde57-146">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="cde57-147">這適用于所有的視圖，例如惡意程式碼或網路釣魚視圖。</span><span class="sxs-lookup"><span data-stu-id="cde57-147">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="cde57-148">若要包含 Zapped 的專案，您需要將 ' 傳遞動作 ' 設定為包含「包含」（由 ZAP 移除）。</span><span class="sxs-lookup"><span data-stu-id="cde57-148">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="cde57-149">如果您包括所有選項，您會看到所有傳遞動作結果，包括 Zapped 專案。</span><span class="sxs-lookup"><span data-stu-id="cde57-149">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="cde57-150">**流覽至威脅瀏覽器** ：移至 [https://protection.office.com](https://protection.office.com) 並使用您的 Office 365 的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cde57-150">**Navigate to Threat Explorer** : Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="cde57-151">這會帶您前往安全性與 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="cde57-151">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="cde57-152">在 [左導覽快速啟動] 中，選擇 [ **威脅管理** \> **瀏覽器** ]。</span><span class="sxs-lookup"><span data-stu-id="cde57-152">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![使用 [傳遞動作] 和 [傳遞位置] 欄位的 Explorer。](../../media/ThreatExFields.PNG)

    <span data-ttu-id="cde57-154">您可能會注意到 [新增 **特殊動作** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="cde57-154">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="cde57-155">這項功能的目的是告知管理員處理電子郵件的結果。</span><span class="sxs-lookup"><span data-stu-id="cde57-155">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="cde57-156">您可以在與 **傳遞動作** 和 **傳遞位置** 相同的地方存取 [ **特殊動作** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="cde57-156">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="cde57-157">在威脅瀏覽器的電子郵件時程表結束時，可能會更新特殊的動作，這是一項新功能，其目的是讓系統管理員更熟悉搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="cde57-157">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="cde57-158">**威脅瀏覽器中的視圖** ：在 [ **視圖** ] 功能表中，選擇 [ **所有電子郵件** ]。</span><span class="sxs-lookup"><span data-stu-id="cde57-158">**Views in Threat Explorer** : In the **View** menu, choose **All email**.</span></span>

    ![威脅瀏覽器的「查看」功能表，以及電子郵件-惡意程式碼、網路釣魚、提交和所有電子郵件選項，也是內容惡意程式碼。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="cde57-160">*惡意* 代碼視圖目前是預設值，會捕獲偵測到惡意軟體威脅的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-160">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="cde57-161">*網路釣魚* 視圖的運作方式與網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="cde57-161">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="cde57-162">不過， *所有的電子郵件 View 都會* 列出組織收到的每封郵件，是否偵測到威脅。</span><span class="sxs-lookup"><span data-stu-id="cde57-162">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="cde57-163">您可以想像，這是許多資料，這就是為什麼此視圖會顯示要求套用篩選的預留位置。</span><span class="sxs-lookup"><span data-stu-id="cde57-163">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="cde57-164"> (此 view 僅適用于 Office 365 P2 客戶的 Defender。 ) </span><span class="sxs-lookup"><span data-stu-id="cde57-164">(This view is only available for Defender for Office 365 P2 customers.)</span></span>

    <span data-ttu-id="cde57-165">「 *提交* 」視圖會顯示系統管理員或使用者向 Microsoft 提交的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-165">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="cde57-166">**威脅瀏覽器中的搜尋和篩選** ：篩選顯示在搜尋列的頁面頂端，以協助系統管理員進行調查。</span><span class="sxs-lookup"><span data-stu-id="cde57-166">**Search and filter in Threat Explorer** : Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="cde57-167">請注意，可以同時套用多個篩選，並新增多個逗號分隔值，以縮小搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="cde57-167">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="cde57-168">記得：</span><span class="sxs-lookup"><span data-stu-id="cde57-168">Remember:</span></span>

    - <span data-ttu-id="cde57-169">篩選器對大多數篩選準則完全符合。</span><span class="sxs-lookup"><span data-stu-id="cde57-169">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="cde57-170">主體篩選使用包含查詢。</span><span class="sxs-lookup"><span data-stu-id="cde57-170">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="cde57-171">URL 篩選器使用或不使用通訊協定 (ex。</span><span class="sxs-lookup"><span data-stu-id="cde57-171">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="cde57-172">HTTPs) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-172">https).</span></span>
    - <span data-ttu-id="cde57-173">URL 網域、URL 路徑及 URL 網域和路徑篩選器不需要使用通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cde57-173">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="cde57-174">每次變更篩選值以取得相關結果時，您必須按一下 [重新整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="cde57-174">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="cde57-175">**高級篩選** ：使用這些篩選器，您可以建立複雜的查詢並篩選您的資料集。</span><span class="sxs-lookup"><span data-stu-id="cde57-175">**Advanced filters** : With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="cde57-176">按一下 [ *高級篩選* ] 開啟具有選項的浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="cde57-176">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="cde57-177">「高級篩選 ' 是搜尋功能的極佳補充。</span><span class="sxs-lookup"><span data-stu-id="cde57-177">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="cde57-178">在 *收* 件者、 *寄件者* 和 *寄件者網域* 上，已引進 boolean **非** 篩選，以允許系統管理員透過排除值來調查。</span><span class="sxs-lookup"><span data-stu-id="cde57-178">A boolean **NOT** filter has been introduced on *Recipient* , *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="cde57-179">此選項會出現在 [選取參數不 *包含任何* ] 底下。</span><span class="sxs-lookup"><span data-stu-id="cde57-179">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="cde57-180">**不** 會讓系統管理員從其調查中排除警示信箱、預設的回復信箱，而且可用於系統管理員搜尋特定主旨 (主旨 = 「注意」 ) ，收件者可以將收件者可以設定為 *defaultMail \@ contoso.com 的任何* 情況。</span><span class="sxs-lookup"><span data-stu-id="cde57-180">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="cde57-181">這是實際值搜尋。</span><span class="sxs-lookup"><span data-stu-id="cde57-181">This is an exact value search.</span></span>

   ![收件者-' 不含任何的 ' 高級篩選。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="cde57-183">*依小時篩選* 可協助貴組織的安全性小組快速深入。</span><span class="sxs-lookup"><span data-stu-id="cde57-183">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="cde57-184">允許的最短時間為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="cde57-184">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="cde57-185">如果您可以將可疑的動作縮小為時間範圍 (例如，發生3小時前) ，這會限制內容，協助找出問題。</span><span class="sxs-lookup"><span data-stu-id="cde57-185">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![[依小時篩選] 選項，以縮小必須處理的資料安全小組數量，而且其最短工期為30分鐘。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="cde57-187">**威脅瀏覽器中的欄位** ：威脅瀏覽器會公開許多安全性相關郵件資訊， *例如傳遞動作* 、 *傳遞位置* 、 *特殊動作* 、 *方向* 性、 *覆寫* 及 *URL 威脅* 。</span><span class="sxs-lookup"><span data-stu-id="cde57-187">**Fields in threat explorer** : Threat Explorer exposes a lot more security-related mail information such as *Delivery action* , *Delivery location* , *Special action* , *Directionality* , *Overrides* , and *URL threat*.</span></span> <span data-ttu-id="cde57-188">它也可讓您的組織的安全性小組以更高的確定性進行調查。</span><span class="sxs-lookup"><span data-stu-id="cde57-188">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="cde57-189">*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="cde57-189">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="cde57-190">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="cde57-190">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="cde57-191">**傳遞** -電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="cde57-191">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="cde57-192">**Junked** (已傳遞至垃圾) –將電子郵件傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取垃圾郵件或已刪除的資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-192">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="cde57-193">**封鎖** –隔離、失敗或丟棄的任何電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="cde57-193">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="cde57-194"> (使用者已完全無法存取。 ) </span><span class="sxs-lookup"><span data-stu-id="cde57-194">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="cde57-195">**已取代** 所有惡意附件取代為附件惡意的 .txt 檔案所取代的電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-195">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="cde57-196">**傳遞位置** ：可用的傳遞位置篩選器，可協助系統管理員瞭解可疑的惡意郵件如何結束，以及對它採取的動作。</span><span class="sxs-lookup"><span data-stu-id="cde57-196">**Delivery location** : The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="cde57-197">產生的資料可匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="cde57-197">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="cde57-198">可能的傳遞位置如下：</span><span class="sxs-lookup"><span data-stu-id="cde57-198">Possible delivery locations are:</span></span>

    - <span data-ttu-id="cde57-199">**收件匣或資料夾** –電子郵件會根據您的電子郵件規則，在收件匣或特定資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cde57-199">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="cde57-200">**部署或外部** –信箱不存在於雲端中，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="cde57-200">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="cde57-201">[垃圾郵件] **資料夾** –電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cde57-201">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="cde57-202">[ **刪除的郵件] 資料夾** -電子郵件是在使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cde57-202">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="cde57-203">**隔離** –隔離區中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-203">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="cde57-204">**Failed** -電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-204">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="cde57-205">已 **丟棄** -電子郵件已遺失于郵件流程中的某處。</span><span class="sxs-lookup"><span data-stu-id="cde57-205">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="cde57-206">**方向** 性：此選項可讓您的安全性作業小組以郵件來自的「方向」來篩選，或前往。</span><span class="sxs-lookup"><span data-stu-id="cde57-206">**Directionality** : This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="cde57-207">方向性值為 *輸入* 、 *輸出* 和 *組織內* 的 (，對應至您的組織外寄出的郵件、從您的組織寄出或內部傳送至您的組織內部，分別是) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-207">Directionality values are *Inbound* , *Outbound* , and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="cde57-208">此資訊可協助安全性運作小組發現欺騙和模擬，因為方向性值 (ex 之間不相符。</span><span class="sxs-lookup"><span data-stu-id="cde57-208">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="cde57-209">*輸入* ) 和寄件者 (中 *似乎* 是內部網域) 的網域很明顯！</span><span class="sxs-lookup"><span data-stu-id="cde57-209">*Inbound* ), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="cde57-210">方向性值是分開的，而且可以與郵件追蹤有所不同。</span><span class="sxs-lookup"><span data-stu-id="cde57-210">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="cde57-211">結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="cde57-211">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="cde57-212">**覆寫** ：此篩選器會取得出現在 [郵件詳細資料] 索引標籤上的資訊，並使用它來公開允許和封鎖郵件已覆 *寫* 的組織或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="cde57-212">**Overrides** : This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="cde57-213">此篩選器最重要的一點是它可協助貴組織的安全性小組查看因設定而傳遞的可疑電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="cde57-213">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="cde57-214">這讓他們有機會視需要修改允許和封鎖。</span><span class="sxs-lookup"><span data-stu-id="cde57-214">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="cde57-215">這個篩選的結果集可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="cde57-215">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="cde57-216">威脅瀏覽器覆寫</span><span class="sxs-lookup"><span data-stu-id="cde57-216">Threat Explorer Overrides</span></span>|<span data-ttu-id="cde57-217">其含義</span><span class="sxs-lookup"><span data-stu-id="cde57-217">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="cde57-218">組織原則允許</span><span class="sxs-lookup"><span data-stu-id="cde57-218">Allowed by Org Policy</span></span>|<span data-ttu-id="cde57-219">郵件是透過組織原則所導向的信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-219">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cde57-220">由組織原則封鎖</span><span class="sxs-lookup"><span data-stu-id="cde57-220">Blocked by Org policy</span></span>|<span data-ttu-id="cde57-221">郵件已封鎖為由組織原則所導向的方式傳遞到信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-221">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cde57-222">組織原則封鎖的檔擴充</span><span class="sxs-lookup"><span data-stu-id="cde57-222">File extension blocked by Org Policy</span></span>|<span data-ttu-id="cde57-223">從組織原則的導向中，File 遭到封鎖，無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-223">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cde57-224">使用者原則所允許</span><span class="sxs-lookup"><span data-stu-id="cde57-224">Allowed by User Policy</span></span>|<span data-ttu-id="cde57-225">信箱是使用者原則所導向的信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-225">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="cde57-226">使用者原則封鎖</span><span class="sxs-lookup"><span data-stu-id="cde57-226">Blocked by User Policy</span></span>|<span data-ttu-id="cde57-227">郵件已封鎖由使用者原則所導向的方式傳遞到信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-227">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="cde57-228">**Url 威脅** ： [url 威脅] 欄位已包含在電子郵件的 [ *詳細資料* ] 索引標籤中，指出 URL 所呈現的威脅。</span><span class="sxs-lookup"><span data-stu-id="cde57-228">**URL threat** : The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="cde57-229">URL 所呈現的威脅可以包含 *惡意* 代碼、 *網路釣魚* 或 *垃圾郵件* ，而 *不具威脅* 的 url 會在 [威脅] 區段中指出 *無* 威脅。</span><span class="sxs-lookup"><span data-stu-id="cde57-229">Threats presented by a URL can include *Malware* , *Phish* , or *Spam* , and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="cde57-230">**電子郵件時程表視圖** ：您的安全作業小組可能需要深入瞭解電子郵件詳細資料，以進行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="cde57-230">**Email timeline view** : Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="cde57-231">電子郵件時程表可讓系統管理員將電子郵件所採取的動作從傳遞傳遞至傳遞投遞。</span><span class="sxs-lookup"><span data-stu-id="cde57-231">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="cde57-232">若要查看電子郵件時程表，請按一下電子郵件的主旨，然後按一下 [電子郵件時程表]。</span><span class="sxs-lookup"><span data-stu-id="cde57-232">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="cde57-233"> (它會顯示在面板上其他標題（如摘要或詳細資料）。 ) 這些結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="cde57-233">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="cde57-234">電子郵件時程表會開啟一個表格，顯示電子郵件的所有傳遞和傳遞後事件。</span><span class="sxs-lookup"><span data-stu-id="cde57-234">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="cde57-235">如果電子郵件上沒有進一步的動作，您應該會看到原始傳遞的單一事件，其狀態為「類似 *網路釣魚* 」的結果（如 *封鎖* ）。</span><span class="sxs-lookup"><span data-stu-id="cde57-235">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked* , with a verdict like *Phish*.</span></span> <span data-ttu-id="cde57-236">系統管理員可以匯出整個電子郵件時程表，包括索引標籤上的所有詳細資料，以及電子郵件 (例如，主旨、寄件者、收件者、網路和郵件識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-236">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="cde57-237">電子郵件時程表會在隨機進行分解，因為檢查不同位置所花費的時間較少，以嘗試瞭解自電子郵件到達後發生的事件。</span><span class="sxs-lookup"><span data-stu-id="cde57-237">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="cde57-238">當電子郵件上發生多個事件，或在電子郵件上接近時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="cde57-238">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="cde57-239">**預覽/下載** ：威脅瀏覽器可讓您的安全性運作小組提供調查可疑電子郵件所需的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cde57-239">**Preview / download** : Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="cde57-240">您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="cde57-240">Your security operations team can either:</span></span>

    - <span data-ttu-id="cde57-241">[檢查傳遞動作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="cde57-241">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="cde57-242">[查看您電子郵件的時程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="cde57-242">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="cde57-243">檢查傳遞動作和位置</span><span class="sxs-lookup"><span data-stu-id="cde57-243">Check the delivery action and location</span></span>

<span data-ttu-id="cde57-244">在 [威脅瀏覽器中 (和即時偵測)](threat-explorer.md)中，您現在已有 **傳遞動作** 和 **傳遞位置** 欄，而不是先前傳遞的 [ **狀態** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="cde57-244">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="cde57-245">這會使您的電子郵件成為土地的更完整的畫面。</span><span class="sxs-lookup"><span data-stu-id="cde57-245">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="cde57-246">此變更的一部分目標是讓調查更容易進行安全作業小組，但 net 結果是知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="cde57-246">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="cde57-247">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="cde57-247">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="cde57-248">**傳遞動作** -此電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="cde57-248">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="cde57-249">**傳遞位置** -這封電子郵件會以結果的方式路由傳送？</span><span class="sxs-lookup"><span data-stu-id="cde57-249">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="cde57-250">傳遞動作是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="cde57-250">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="cde57-251">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="cde57-251">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="cde57-252">**傳遞** -電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="cde57-252">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="cde57-253">**Junked** –將電子郵件傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取垃圾郵件或已刪除的資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-253">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="cde57-254">**封鎖** –隔離、失敗或丟棄的任何電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="cde57-254">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="cde57-255"> (使用者已完全無法存取。 ) </span><span class="sxs-lookup"><span data-stu-id="cde57-255">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="cde57-256">**已取代** 所有惡意附件取代為附件惡意的 .txt 檔的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-256">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="cde57-257">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="cde57-257">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="cde57-258">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="cde57-258">It's linked to a Delivery Action.</span></span> <span data-ttu-id="cde57-259">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="cde57-259">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="cde57-260">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="cde57-260">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="cde57-261">**收件匣或資料夾** –電子郵件是在收件匣或資料夾中 (根據您的電子郵件規則) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-261">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="cde57-262">**部署或外部** –信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="cde57-262">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="cde57-263">[垃圾郵件] **資料夾** –電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cde57-263">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="cde57-264">[ **刪除的郵件] 資料夾** -電子郵件是在使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cde57-264">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="cde57-265">**隔離** –隔離區中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cde57-265">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="cde57-266">**Failed** -電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="cde57-266">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="cde57-267">**丟** 入–電子郵件會在郵件流程中遺失。</span><span class="sxs-lookup"><span data-stu-id="cde57-267">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="cde57-268">查看您電子郵件的時程表</span><span class="sxs-lookup"><span data-stu-id="cde57-268">View the timeline of your email</span></span>

<span data-ttu-id="cde57-269">**電子郵件時程表** 是威脅瀏覽器中的欄位，可讓您的安全性運作小組更輕鬆進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="cde57-269">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="cde57-270">當電子郵件上發生多個事件或在同一時間關閉時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="cde57-270">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="cde57-271">某些會在 [ **特殊動作** ] 欄中捕獲傳送投遞至電子郵件的事件。</span><span class="sxs-lookup"><span data-stu-id="cde57-271">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="cde57-272">將電子郵件的時程表中的資訊組合在一起，可讓系統管理員深入瞭解原則和威脅處理 (例如郵件路由的位置，以及在某些情況下，最後評估) 。</span><span class="sxs-lookup"><span data-stu-id="cde57-272">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cde57-273">在 [這裡](remediate-malicious-email-delivered-office-365.md)跳到修正主題。</span><span class="sxs-lookup"><span data-stu-id="cde57-273">Jump to a remediation topic [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cde57-274">相關主題</span><span class="sxs-lookup"><span data-stu-id="cde57-274">Related topics</span></span>

[<span data-ttu-id="cde57-275">修復 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="cde57-275">Remediate malicious email delivered in Office 365</span></span>](remediate-malicious-email-delivered-office-365.md)

[<span data-ttu-id="cde57-276">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cde57-276">Microsoft Defender for Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="cde57-277">保護 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="cde57-277">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="cde57-278">查看 Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="cde57-278">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
