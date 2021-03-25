---
title: 調查 Office 365 中傳遞的惡意電子郵件，尋找並調查惡意電子郵件
keywords: TIMailData-Inline，Security 事件，事件，ATP PowerShell，電子郵件惡意程式碼，已遭破壞的使用者，電子郵件網路釣魚程式，電子郵件惡意程式碼，讀取電子郵件標題，讀取標頭，開啟電子郵件頭，特殊動作
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 瞭解如何使用威脅調查和回應功能來尋找並調查惡意的電子郵件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2781850eacf8b0fcf4909406aca335f1bbeb0753
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203522"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="99f71-104">調查 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-104">Investigate malicious email that was delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="99f71-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="99f71-105">**Applies to**</span></span>

- [<span data-ttu-id="99f71-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="99f71-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="99f71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99f71-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="99f71-108">[Microsoft Defender For Office 365](defender-for-office-365.md) 可讓您調查讓組織中的人員面臨風險的活動，並採取行動以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="99f71-108">[Microsoft Defender for Office 365](defender-for-office-365.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="99f71-109">例如，如果您是組織的安全性小組的一部分，您可以找出並調查已傳遞的可疑電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="99f71-109">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="99f71-110">您可以使用 [威脅瀏覽器 (或即時偵測) ](threat-explorer.md)來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="99f71-110">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="99f71-111">在 [這裡](remediate-malicious-email-delivered-office-365.md)跳到修正文章。</span><span class="sxs-lookup"><span data-stu-id="99f71-111">Jump to the remediation article [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="99f71-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="99f71-112">Before you begin</span></span>

<span data-ttu-id="99f71-113">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="99f71-113">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="99f71-114">您的組織已將 [Microsoft Defender 用於 Office 365](defender-for-office-365.md) ，而 [授權已指派給使用者](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="99f71-114">Your organization has [Microsoft Defender for Office 365](defender-for-office-365.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="99f71-115">您的組織已開啟[審核記錄](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="99f71-115">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="99f71-116">您的組織有為反垃圾郵件、反惡意程式碼、反網路釣魚等定義的原則。</span><span class="sxs-lookup"><span data-stu-id="99f71-116">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="99f71-117">請參閱 [防禦 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="99f71-117">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="99f71-118">您是全域系統管理員，或您已在安全性 & 合規性中心內指派安全性管理員或搜尋和清除角色。</span><span class="sxs-lookup"><span data-stu-id="99f71-118">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security & Compliance Center.</span></span> <span data-ttu-id="99f71-119">請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="99f71-119">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="99f71-120">在某些動作中，您也必須已指派新的預覽角色。</span><span class="sxs-lookup"><span data-stu-id="99f71-120">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="99f71-121">預覽角色許可權</span><span class="sxs-lookup"><span data-stu-id="99f71-121">Preview role permissions</span></span>

<span data-ttu-id="99f71-122">若要執行某些動作，例如：查看郵件頭或下載電子郵件內容，您必須將名為 *Preview* 的新角色新增至另一個適當的角色群組。</span><span class="sxs-lookup"><span data-stu-id="99f71-122">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="99f71-123">下表說明必要的角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="99f71-123">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="99f71-124">活動</span><span class="sxs-lookup"><span data-stu-id="99f71-124">Activity</span></span>|<span data-ttu-id="99f71-125">角色群組</span><span class="sxs-lookup"><span data-stu-id="99f71-125">Role group</span></span>|<span data-ttu-id="99f71-126">需要預覽角色？</span><span class="sxs-lookup"><span data-stu-id="99f71-126">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="99f71-127">使用威脅瀏覽器 (和即時偵測) 來分析威脅</span><span class="sxs-lookup"><span data-stu-id="99f71-127">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="99f71-128">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-128">Global Administrator</span></span> <p> <span data-ttu-id="99f71-129">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-129">Security Administrator</span></span> <p> <span data-ttu-id="99f71-130">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="99f71-130">Security Reader</span></span>|<span data-ttu-id="99f71-131">否</span><span class="sxs-lookup"><span data-stu-id="99f71-131">No</span></span>|
|<span data-ttu-id="99f71-132">使用威脅瀏覽器 (和即時偵測) 來查看電子郵件的標頭，以及預覽及下載隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-132">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="99f71-133">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-133">Global Administrator</span></span> <p> <span data-ttu-id="99f71-134">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-134">Security Administrator</span></span> <p> <span data-ttu-id="99f71-135">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="99f71-135">Security Reader</span></span>|<span data-ttu-id="99f71-136">否</span><span class="sxs-lookup"><span data-stu-id="99f71-136">No</span></span>|
|<span data-ttu-id="99f71-137">使用威脅瀏覽器來查看標頭、只在電子郵件實體頁面中預覽電子郵件 () 並下載傳送至信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-137">Use Threat Explorer to view headers, preview email (only in the email entity page) and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="99f71-138">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-138">Global Administrator</span></span> <p> <span data-ttu-id="99f71-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="99f71-139">Security Administrator</span></span> <p> <span data-ttu-id="99f71-140">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="99f71-140">Security Reader</span></span> <p> <span data-ttu-id="99f71-141">預覽</span><span class="sxs-lookup"><span data-stu-id="99f71-141">Preview</span></span>|<span data-ttu-id="99f71-142">是</span><span class="sxs-lookup"><span data-stu-id="99f71-142">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="99f71-143">*Preview* 是角色，不是角色群組;預覽角色必須新增至現有的 Office 365 (角色群組中 <https://protection.office.com>) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-143">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365 (at <https://protection.office.com>).</span></span> <span data-ttu-id="99f71-144">移至 [ **許可權**]，然後編輯現有的角色群組，或新增「 **預覽** 」角色所指派的新角色群組。</span><span class="sxs-lookup"><span data-stu-id="99f71-144">Go to **Permissions**, and then either edit an existing role group or add a new role group with the **Preview** role assigned.</span></span>
> <span data-ttu-id="99f71-145">全域系統管理員角色會指派 Microsoft 365 系統管理中心 (<https://admin.microsoft.com>) ，而且安全性管理員和安全性讀取者角色會指派在安全性 & 規範中心 (<https://protection.office.com>) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-145">The Global Administrator role is assigned the Microsoft 365 admin center (<https://admin.microsoft.com>), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span> <span data-ttu-id="99f71-146">若要深入瞭解角色和許可權，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="99f71-146">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="99f71-147">我們瞭解預覽和下載電子郵件是機密的活動，因此會為這些活動啟用審核。</span><span class="sxs-lookup"><span data-stu-id="99f71-147">We understand previewing and downloading email are sensitive activities, and so we auditing is enabled for these.</span></span> <span data-ttu-id="99f71-148">當系統管理員在電子郵件上執行這些動作後，就會產生相同的審計記錄，並可在 Office 365 安全性 & 規範中心 () 中看到 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="99f71-148">Once an admin performs these activities on emails, audit logs are generated for the same and can be seen in the Office 365 Security & Compliance Center (<https://protection.office.com>).</span></span> <span data-ttu-id="99f71-149">移至 **「搜尋**  >  **審核記錄**」搜尋，然後在 [搜尋] 區段中篩選 admin name。</span><span class="sxs-lookup"><span data-stu-id="99f71-149">Go to **Search** > **Audit log search** and filter on the admin name in Search section.</span></span> <span data-ttu-id="99f71-150">篩選的結果會顯示活動 **AdminMailAccess**。</span><span class="sxs-lookup"><span data-stu-id="99f71-150">The filtered results will show activity **AdminMailAccess**.</span></span> <span data-ttu-id="99f71-151">選取要在 [ **詳細資訊** ] 區段中預覽或下載之電子郵件的詳細資訊一列。</span><span class="sxs-lookup"><span data-stu-id="99f71-151">Select a row to view details in the **More information** section about previewed or downloaded email.</span></span>

## <a name="find-suspicious-email-that-was-delivered"></a><span data-ttu-id="99f71-152">尋找已傳遞的可疑電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-152">Find suspicious email that was delivered</span></span>

<span data-ttu-id="99f71-153">威脅瀏覽器是一種強大的報表，可用於多種用途，例如尋找和刪除郵件、識別惡意電子郵件寄件者的 IP 位址，或啟動事件以進一步進行調查。</span><span class="sxs-lookup"><span data-stu-id="99f71-153">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="99f71-154">下列程式著重于使用 Explorer 尋找及刪除收件者信箱中的惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-154">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="99f71-155">瀏覽器中的預設搜尋目前不包含 Zapped 的專案。</span><span class="sxs-lookup"><span data-stu-id="99f71-155">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="99f71-156">這適用于所有的視圖，例如惡意程式碼或網路釣魚視圖。</span><span class="sxs-lookup"><span data-stu-id="99f71-156">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="99f71-157">若要包含 Zapped 的專案，您需要新增 **傳遞動作** 集，並將其新增至包含 **的** 物件。</span><span class="sxs-lookup"><span data-stu-id="99f71-157">To include Zapped items you need to add a **Delivery action** set to include **Removed by ZAP**.</span></span> <span data-ttu-id="99f71-158">如果您包括所有選項，您會看到所有傳遞動作結果，包括 Zapped 專案。</span><span class="sxs-lookup"><span data-stu-id="99f71-158">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="99f71-159">**流覽至威脅瀏覽器**：移至 <https://protection.office.com> 並使用您的 Office 365 的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="99f71-159">**Navigate to Threat Explorer**: Go to <https://protection.office.com> and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="99f71-160">這會帶您前往安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="99f71-160">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="99f71-161">在 [左導覽快速啟動] 中，選擇 [ **威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="99f71-161">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![使用 [傳遞動作] 和 [傳遞位置] 欄位的 Explorer。](../../media/ThreatExFields.PNG)

    <span data-ttu-id="99f71-163">您可能會注意到 [新增 **特殊動作** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="99f71-163">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="99f71-164">這項功能的目的是告知管理員處理電子郵件的結果。</span><span class="sxs-lookup"><span data-stu-id="99f71-164">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="99f71-165">您可以在與 **傳遞動作** 和 **傳遞位置** 相同的地方存取 [**特殊動作**] 欄。</span><span class="sxs-lookup"><span data-stu-id="99f71-165">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="99f71-166">在威脅瀏覽器的電子郵件時程表結束時，可能會更新特殊的動作，這是一項新功能，其目的是讓系統管理員更熟悉搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="99f71-166">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="99f71-167">**威脅瀏覽器中的視圖**：在 [ **視圖** ] 功能表中，選擇 [ **所有電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="99f71-167">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威脅瀏覽器的「查看」功能表，以及電子郵件-惡意程式碼、網路釣魚、提交和所有電子郵件選項，也是內容惡意程式碼。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="99f71-169">*惡意* 代碼視圖目前是預設值，會捕獲偵測到惡意軟體威脅的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-169">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="99f71-170">*網路釣魚* 視圖的運作方式與網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="99f71-170">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="99f71-171">不過， *所有的電子郵件 View 都會* 列出組織收到的每封郵件，是否偵測到威脅。</span><span class="sxs-lookup"><span data-stu-id="99f71-171">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="99f71-172">您可以想像，這是許多資料，這就是為什麼此視圖會顯示要求套用篩選的預留位置。</span><span class="sxs-lookup"><span data-stu-id="99f71-172">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="99f71-173"> (此 view 僅適用于 Office 365 P2 客戶的 Defender。 ) </span><span class="sxs-lookup"><span data-stu-id="99f71-173">(This view is only available for Defender for Office 365 P2 customers.)</span></span>

    <span data-ttu-id="99f71-174">「*提交*」視圖會顯示系統管理員或使用者向 Microsoft 提交的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-174">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="99f71-175">**威脅瀏覽器中的搜尋和篩選**：篩選顯示在搜尋列的頁面頂端，以協助系統管理員進行調查。</span><span class="sxs-lookup"><span data-stu-id="99f71-175">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="99f71-176">請注意，可以同時套用多個篩選，並新增多個逗號分隔值，以縮小搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="99f71-176">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="99f71-177">請記住：</span><span class="sxs-lookup"><span data-stu-id="99f71-177">Remember:</span></span>

    - <span data-ttu-id="99f71-178">篩選器對大多數篩選準則完全符合。</span><span class="sxs-lookup"><span data-stu-id="99f71-178">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="99f71-179">主體篩選使用包含查詢。</span><span class="sxs-lookup"><span data-stu-id="99f71-179">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="99f71-180">URL 篩選器使用或不使用通訊協定 (ex。</span><span class="sxs-lookup"><span data-stu-id="99f71-180">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="99f71-181">HTTPs) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-181">https).</span></span>
    - <span data-ttu-id="99f71-182">URL 網域、URL 路徑及 URL 網域和路徑篩選器不需要使用通訊協定。</span><span class="sxs-lookup"><span data-stu-id="99f71-182">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="99f71-183">每次變更篩選值以取得相關結果時，您必須按一下 [重新整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="99f71-183">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="99f71-184">**高級篩選**：使用這些篩選器，您可以建立複雜的查詢並篩選您的資料集。</span><span class="sxs-lookup"><span data-stu-id="99f71-184">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="99f71-185">按一下 [ *高級篩選* ] 開啟具有選項的浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="99f71-185">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="99f71-186">「高級篩選 ' 是搜尋功能的極佳補充。</span><span class="sxs-lookup"><span data-stu-id="99f71-186">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="99f71-187">在 *收* 件者、*寄件者* 和 *寄件者網域* 上，已引進 boolean **非** 篩選，以允許系統管理員透過排除值來調查。</span><span class="sxs-lookup"><span data-stu-id="99f71-187">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="99f71-188">此選項會出現在 [選取參數不 *包含任何*] 底下。</span><span class="sxs-lookup"><span data-stu-id="99f71-188">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="99f71-189">**不** 會讓系統管理員從其調查中排除警示信箱、預設的回復信箱，而且可用於系統管理員搜尋特定主旨 (主旨 = 「注意」 ) ，收件者可以將收件者可以設定為 *defaultMail \@ contoso.com 的任何* 情況。</span><span class="sxs-lookup"><span data-stu-id="99f71-189">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="99f71-190">這是實際值搜尋。</span><span class="sxs-lookup"><span data-stu-id="99f71-190">This is an exact value search.</span></span>

   ![收件者-' 不含任何的 ' 高級篩選。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="99f71-192">*依小時篩選* 可協助貴組織的安全性小組快速深入。</span><span class="sxs-lookup"><span data-stu-id="99f71-192">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="99f71-193">允許的最短時間為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="99f71-193">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="99f71-194">如果您可以將可疑的動作縮小為時間範圍 (例如，發生3小時前) ，這會限制內容，協助找出問題。</span><span class="sxs-lookup"><span data-stu-id="99f71-194">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![[依小時篩選] 選項，以縮小必須處理的資料安全小組數量，而且其最短工期為30分鐘。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="99f71-196">**威脅瀏覽器中的欄位**：威脅瀏覽器會公開許多安全性相關郵件資訊， *例如傳遞動作*、 *傳遞位置*、 *特殊動作*、 *方向* 性、 *覆寫* 及 *URL 威脅*。</span><span class="sxs-lookup"><span data-stu-id="99f71-196">**Fields in Threat Explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="99f71-197">它也可讓您的組織的安全性小組以更高的確定性進行調查。</span><span class="sxs-lookup"><span data-stu-id="99f71-197">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="99f71-198">*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="99f71-198">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="99f71-199">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="99f71-199">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="99f71-200">**傳遞** -電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="99f71-200">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="99f71-201">**Junked** (已傳遞至垃圾) –將電子郵件傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取垃圾郵件或已刪除的資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-201">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="99f71-202">**封鎖** –隔離、失敗或丟棄的任何電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="99f71-202">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="99f71-203"> (使用者已完全無法存取。 ) </span><span class="sxs-lookup"><span data-stu-id="99f71-203">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="99f71-204">**已取代** 所有惡意附件取代為附件惡意的 .txt 檔案所取代的電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-204">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="99f71-205">**傳遞位置**：可用的傳遞位置篩選器，可協助系統管理員瞭解可疑的惡意郵件如何結束，以及對它採取的動作。</span><span class="sxs-lookup"><span data-stu-id="99f71-205">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="99f71-206">產生的資料可匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="99f71-206">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="99f71-207">可能的傳遞位置如下：</span><span class="sxs-lookup"><span data-stu-id="99f71-207">Possible delivery locations are:</span></span>

    - <span data-ttu-id="99f71-208">**收件匣或資料夾** –電子郵件會根據您的電子郵件規則，在收件匣或特定資料夾中。</span><span class="sxs-lookup"><span data-stu-id="99f71-208">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="99f71-209">**部署或外部** –信箱不存在於雲端中，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="99f71-209">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="99f71-210">[垃圾郵件]**資料夾**–電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="99f71-210">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="99f71-211">[**刪除的郵件] 資料夾**-電子郵件是在使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="99f71-211">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="99f71-212">**隔離** –隔離區中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-212">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="99f71-213">**Failed** -電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-213">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="99f71-214">已 **丟棄**-電子郵件已遺失于郵件流程中的某處。</span><span class="sxs-lookup"><span data-stu-id="99f71-214">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="99f71-215">**方向** 性：此選項可讓您的安全性作業小組以郵件來自的「方向」來篩選，或前往。</span><span class="sxs-lookup"><span data-stu-id="99f71-215">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="99f71-216">方向性值為 *輸入*、 *輸出* 和 *組織內* 的 (，對應至您的組織外寄出的郵件、從您的組織寄出或內部傳送至您的組織內部，分別是) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-216">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="99f71-217">此資訊可協助安全性運作小組發現欺騙和模擬，因為方向性值 (ex 之間不相符。</span><span class="sxs-lookup"><span data-stu-id="99f71-217">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="99f71-218">*輸入*) 和寄件者 (中 *似乎* 是內部網域) 的網域很明顯！</span><span class="sxs-lookup"><span data-stu-id="99f71-218">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="99f71-219">方向性值是分開的，而且可以與郵件追蹤有所不同。</span><span class="sxs-lookup"><span data-stu-id="99f71-219">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="99f71-220">結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="99f71-220">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="99f71-221">**覆寫**：此篩選器會取得出現在 [郵件詳細資料] 索引標籤上的資訊，並使用它來公開允許和封鎖郵件已覆 *寫* 的組織或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="99f71-221">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="99f71-222">此篩選器最重要的一點是它可協助貴組織的安全性小組查看因設定而傳遞的可疑電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="99f71-222">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="99f71-223">這讓他們有機會視需要修改允許和封鎖。</span><span class="sxs-lookup"><span data-stu-id="99f71-223">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="99f71-224">這個篩選的結果集可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="99f71-224">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="99f71-225">威脅瀏覽器覆寫</span><span class="sxs-lookup"><span data-stu-id="99f71-225">Threat Explorer Overrides</span></span>|<span data-ttu-id="99f71-226">其含義</span><span class="sxs-lookup"><span data-stu-id="99f71-226">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="99f71-227">組織原則允許</span><span class="sxs-lookup"><span data-stu-id="99f71-227">Allowed by Org Policy</span></span>|<span data-ttu-id="99f71-228">郵件是透過組織原則所導向的信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-228">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="99f71-229">由組織原則封鎖</span><span class="sxs-lookup"><span data-stu-id="99f71-229">Blocked by Org policy</span></span>|<span data-ttu-id="99f71-230">郵件已封鎖為由組織原則所導向的方式傳遞到信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-230">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="99f71-231">組織原則封鎖的檔擴充</span><span class="sxs-lookup"><span data-stu-id="99f71-231">File extension blocked by Org Policy</span></span>|<span data-ttu-id="99f71-232">從組織原則的導向中，File 遭到封鎖，無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-232">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="99f71-233">使用者原則所允許</span><span class="sxs-lookup"><span data-stu-id="99f71-233">Allowed by User Policy</span></span>|<span data-ttu-id="99f71-234">信箱是使用者原則所導向的信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-234">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="99f71-235">使用者原則封鎖</span><span class="sxs-lookup"><span data-stu-id="99f71-235">Blocked by User Policy</span></span>|<span data-ttu-id="99f71-236">郵件已封鎖由使用者原則所導向的方式傳遞到信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-236">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="99f71-237">**Url 威脅**： [url 威脅] 欄位已包含在電子郵件的 [ *詳細資料* ] 索引標籤中，指出 URL 所呈現的威脅。</span><span class="sxs-lookup"><span data-stu-id="99f71-237">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="99f71-238">URL 所呈現的威脅可以包含 *惡意* 代碼、 *網路釣魚* 或 *垃圾郵件*，而 *不具威脅* 的 url 會在 [威脅] 區段中指出 *無* 威脅。</span><span class="sxs-lookup"><span data-stu-id="99f71-238">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="99f71-239">**電子郵件時程表視圖**：您的安全作業小組可能需要深入瞭解電子郵件詳細資料，以進行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="99f71-239">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="99f71-240">電子郵件時程表可讓系統管理員將電子郵件所採取的動作從傳遞傳遞至傳遞投遞。</span><span class="sxs-lookup"><span data-stu-id="99f71-240">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="99f71-241">若要查看電子郵件時程表，請按一下電子郵件的主旨，然後按一下 [電子郵件時程表]。</span><span class="sxs-lookup"><span data-stu-id="99f71-241">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="99f71-242"> (它會顯示在面板上其他標題（如摘要或詳細資料）。 ) 這些結果可以匯出至試算表。</span><span class="sxs-lookup"><span data-stu-id="99f71-242">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="99f71-243">電子郵件時程表會開啟一個表格，顯示電子郵件的所有傳遞和傳遞後事件。</span><span class="sxs-lookup"><span data-stu-id="99f71-243">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="99f71-244">如果電子郵件上沒有進一步的動作，您應該會看到原始傳遞的單一事件，其狀態為「類似 *網路釣魚*」的結果（如 *封鎖*）。</span><span class="sxs-lookup"><span data-stu-id="99f71-244">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="99f71-245">系統管理員可以匯出整個電子郵件時程表，包括索引標籤上的所有詳細資料，以及電子郵件 (例如，主旨、寄件者、收件者、網路和郵件識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-245">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="99f71-246">電子郵件時程表會在隨機進行分解，因為檢查不同位置所花費的時間較少，以嘗試瞭解自電子郵件到達後發生的事件。</span><span class="sxs-lookup"><span data-stu-id="99f71-246">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="99f71-247">當電子郵件上發生多個事件，或在電子郵件上接近時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="99f71-247">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="99f71-248">**預覽/下載**：威脅瀏覽器可讓您的安全性運作小組提供調查可疑電子郵件所需的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="99f71-248">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="99f71-249">您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="99f71-249">Your security operations team can either:</span></span>

    - <span data-ttu-id="99f71-250">[檢查傳遞動作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="99f71-250">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="99f71-251">[查看您電子郵件的時程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="99f71-251">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="99f71-252">檢查傳遞動作和位置</span><span class="sxs-lookup"><span data-stu-id="99f71-252">Check the delivery action and location</span></span>

<span data-ttu-id="99f71-253">在 [威脅瀏覽器中 (和即時偵測)](threat-explorer.md)中，您現在已有 **傳遞動作** 和 **傳遞位置** 欄，而不是先前傳遞的 [ **狀態** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="99f71-253">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="99f71-254">這會使您的電子郵件成為土地的更完整的畫面。</span><span class="sxs-lookup"><span data-stu-id="99f71-254">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="99f71-255">此變更的一部分目標是讓調查更容易進行安全作業小組，但 net 結果是知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="99f71-255">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="99f71-256">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="99f71-256">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="99f71-257">**傳遞動作** -此電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="99f71-257">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="99f71-258">**傳遞位置** -這封電子郵件會以結果的方式路由傳送？</span><span class="sxs-lookup"><span data-stu-id="99f71-258">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="99f71-259">傳遞動作是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="99f71-259">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="99f71-260">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="99f71-260">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="99f71-261">**傳遞** -電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="99f71-261">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="99f71-262">**Junked** –將電子郵件傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取垃圾郵件或已刪除的資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-262">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="99f71-263">**封鎖** –隔離、失敗或丟棄的任何電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="99f71-263">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="99f71-264"> (使用者已完全無法存取。 ) </span><span class="sxs-lookup"><span data-stu-id="99f71-264">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="99f71-265">**已取代** 所有惡意附件取代為附件惡意的 .txt 檔的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-265">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="99f71-266">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="99f71-266">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="99f71-267">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="99f71-267">It's linked to a Delivery Action.</span></span> <span data-ttu-id="99f71-268">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="99f71-268">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="99f71-269">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="99f71-269">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="99f71-270">**收件匣或資料夾** –電子郵件是在收件匣或資料夾中 (根據您的電子郵件規則) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-270">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="99f71-271">**部署或外部** –信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="99f71-271">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="99f71-272">[垃圾郵件]**資料夾**–電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="99f71-272">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="99f71-273">[**刪除的郵件] 資料夾**-電子郵件是在使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="99f71-273">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="99f71-274">**隔離** –隔離區中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="99f71-274">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="99f71-275">**Failed** -電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="99f71-275">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="99f71-276">**丟** 入–電子郵件會在郵件流程中遺失。</span><span class="sxs-lookup"><span data-stu-id="99f71-276">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="99f71-277">查看您電子郵件的時程表</span><span class="sxs-lookup"><span data-stu-id="99f71-277">View the timeline of your email</span></span>

<span data-ttu-id="99f71-278">**電子郵件時程表** 是威脅瀏覽器中的欄位，可讓您的安全性運作小組更輕鬆進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="99f71-278">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="99f71-279">當電子郵件上發生多個事件或在同一時間關閉時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="99f71-279">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="99f71-280">某些會在 [ **特殊動作** ] 欄中捕獲傳送投遞至電子郵件的事件。</span><span class="sxs-lookup"><span data-stu-id="99f71-280">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="99f71-281">將電子郵件的時程表中的資訊組合在一起，可讓系統管理員深入瞭解原則和威脅處理 (例如郵件路由的位置，以及在某些情況下，最後評估) 。</span><span class="sxs-lookup"><span data-stu-id="99f71-281">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f71-282">在 [這裡](remediate-malicious-email-delivered-office-365.md)跳到修正主題。</span><span class="sxs-lookup"><span data-stu-id="99f71-282">Jump to a remediation topic [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="99f71-283">相關主題</span><span class="sxs-lookup"><span data-stu-id="99f71-283">Related topics</span></span>

[<span data-ttu-id="99f71-284">修復 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="99f71-284">Remediate malicious email delivered in Office 365</span></span>](remediate-malicious-email-delivered-office-365.md)

[<span data-ttu-id="99f71-285">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="99f71-285">Microsoft Defender for Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="99f71-286">保護 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="99f71-286">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="99f71-287">查看 Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="99f71-287">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
