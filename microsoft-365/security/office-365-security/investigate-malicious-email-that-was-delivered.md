---
title: 尋找並調查已傳遞 Office 365 中的惡意電子郵件
keywords: TIMailData-內嵌圖案，安全性事件事件，ATP PowerShell 電子郵件的惡意程式碼、 危害使用者釣魚程式的電子郵件、 惡意程式碼的電子郵件、 讀取電子郵件標頭、 讀取標頭、 開啟電子郵件標頭
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
ms.openlocfilehash: bf099dfe8fffdc763d42122e466c982bb90b6492
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076823"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="412f3-104">尋找並調查已傳遞 Office 365 中的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="412f3-104">Find and investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="412f3-105">[Office 365 進階威脅防護](office-365-atp.md)可讓您調查放入風險，貴組織的人員的活動，並採取動作來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="412f3-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="412f3-106">例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞。</span><span class="sxs-lookup"><span data-stu-id="412f3-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="412f3-107">您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="412f3-108">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="412f3-108">Before you begin...</span></span>

<span data-ttu-id="412f3-109">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="412f3-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="412f3-110">您的組織有[Office 365 進階威脅防護](office-365-atp.md)，並[將授權指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="412f3-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="412f3-111">[Office 365 稽核記錄](../../compliance/turn-audit-log-search-on-or-off.md)已為您的組織。</span><span class="sxs-lookup"><span data-stu-id="412f3-111">[Office 365 audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="412f3-112">貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。</span><span class="sxs-lookup"><span data-stu-id="412f3-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="412f3-113">請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="412f3-114">您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="412f3-114">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="412f3-115">請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-115">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="412f3-116">某些動作，您也必須具備新預覽角色指派。</span><span class="sxs-lookup"><span data-stu-id="412f3-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="412f3-117">預覽角色權限</span><span class="sxs-lookup"><span data-stu-id="412f3-117">Preview role permissions</span></span>

<span data-ttu-id="412f3-118">若要執行某些動作，例如檢視郵件標頭或下載電子郵件訊息內容，您必須呼叫*預覽*新增至另一個適當的 Office 365 角色群組的新角色。</span><span class="sxs-lookup"><span data-stu-id="412f3-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate Office 365 role group.</span></span> <span data-ttu-id="412f3-119">下表釐清所需的角色和權限。</span><span class="sxs-lookup"><span data-stu-id="412f3-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="412f3-120">活動</span><span class="sxs-lookup"><span data-stu-id="412f3-120">Activity</span></span>  |<span data-ttu-id="412f3-121">角色群組</span><span class="sxs-lookup"><span data-stu-id="412f3-121">Role group</span></span> |<span data-ttu-id="412f3-122">所需的預覽角色？</span><span class="sxs-lookup"><span data-stu-id="412f3-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="412f3-123">使用分析威脅威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="412f3-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="412f3-124">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-124">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="412f3-125">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-125">Security Administrator</span></span> <br> <span data-ttu-id="412f3-126">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="412f3-126">Security Reader</span></span>     | <span data-ttu-id="412f3-127">否</span><span class="sxs-lookup"><span data-stu-id="412f3-127">No</span></span>   |
|<span data-ttu-id="412f3-128">使用檢視的電子郵件，以及預覽標頭和下載隔離區的電子郵件威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="412f3-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="412f3-129">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-129">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="412f3-130">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-130">Security Administrator</span></span> <br><span data-ttu-id="412f3-131">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="412f3-131">Security Reader</span></span>   |       <span data-ttu-id="412f3-132">否</span><span class="sxs-lookup"><span data-stu-id="412f3-132">No</span></span>  |
|<span data-ttu-id="412f3-133">使用威脅總管檢視標頭，並下載傳遞至信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="412f3-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="412f3-134">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-134">Office 365 Global Administrator</span></span> <br><span data-ttu-id="412f3-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="412f3-135">Security Administrator</span></span> <br> <span data-ttu-id="412f3-136">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="412f3-136">Security Reader</span></span> <br> <span data-ttu-id="412f3-137">預覽</span><span class="sxs-lookup"><span data-stu-id="412f3-137">Preview</span></span>   |   <span data-ttu-id="412f3-138">是</span><span class="sxs-lookup"><span data-stu-id="412f3-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="412f3-139">*預覽*是角色並不是角色群組。「 預覽 」 角色必須新增至現有的角色群組，以 Office 365。</span><span class="sxs-lookup"><span data-stu-id="412f3-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="412f3-140">Office 365 全域系統管理員角色指派的 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))，並安全性管理員和安全性讀取者 」 角色指派 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="412f3-140">The Office 365 Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="412f3-141">若要深入了解角色和權限，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-141">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="412f3-142">尋找並刪除可疑的電子郵件的郵件傳遞</span><span class="sxs-lookup"><span data-stu-id="412f3-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="412f3-143">威脅總管是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。</span><span class="sxs-lookup"><span data-stu-id="412f3-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="412f3-144">下列程序著重於使用 Explorer 來尋找並從收件者信箱刪除惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="412f3-144">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

1. <span data-ttu-id="412f3-145">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="412f3-145">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="412f3-146">這會帶您前往安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="412f3-146">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="412f3-147">在左側導覽中，選擇 [**威脅管理，** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="412f3-147">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

    ![總管] 中的傳遞巨集指令與傳遞位置欄位。](../media/ThreatExFields.PNG)

    <span data-ttu-id="412f3-149">您可能會發現新的 [**特殊動作**] 欄。</span><span class="sxs-lookup"><span data-stu-id="412f3-149">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="412f3-150">這項功能的目標是告訴系統管理員處理電子郵件的結果。</span><span class="sxs-lookup"><span data-stu-id="412f3-150">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="412f3-151">[**特殊動作**] 欄可以存取相同的地方**傳遞巨集指令**並**傳遞位置**中。</span><span class="sxs-lookup"><span data-stu-id="412f3-151">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="412f3-152">特殊動作可能會更新威脅總管] 中的電子郵件時間表，這是針對在系統管理員更妥善地進行狩獵體驗新功能的結尾。</span><span class="sxs-lookup"><span data-stu-id="412f3-152">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="412f3-153">若要檢視的電子郵件時間表，按一下 [電子郵件的主旨]，然後按一下 [**電子郵件時間表**。</span><span class="sxs-lookup"><span data-stu-id="412f3-153">To view an email timeline, click on the subject of an email message, and then click **Email timeline**.</span></span> <span data-ttu-id="412f3-154">（它出現在像**摘要**] 或 [**詳細資料**] 面板上的其他標題之間）。</span><span class="sxs-lookup"><span data-stu-id="412f3-154">(It appears among other headings on the panel like **Summary** or **Details**.)</span></span>

    <span data-ttu-id="412f3-155">一旦您開啟電子郵件時間表，您應該會看到會告訴您在該郵件的後續傳遞事件的資料表。</span><span class="sxs-lookup"><span data-stu-id="412f3-155">Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail.</span></span> <span data-ttu-id="412f3-156">在電子郵件沒有進一步事件，您應該會看到指出像**封鎖**結果**釣魚程式**類似的結論與原始傳遞的單一事件。</span><span class="sxs-lookup"><span data-stu-id="412f3-156">In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**.</span></span> <span data-ttu-id="412f3-157">[] 索引標籤也有選項，會匯出整個電子郵件時間表，並這匯出] 索引標籤上的所有詳細資料和電子郵件 （像是主旨、 寄件者、 收件者、 網路和訊息識別碼） 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="412f3-157">The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).</span></span>

    <span data-ttu-id="412f3-158">電子郵件時間表剪下向下上隨機化因為較少的時間所花費的嘗試了解事件發生於由於電子郵件抵達檢查不同的位置。</span><span class="sxs-lookup"><span data-stu-id="412f3-158">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="412f3-159">當多個事件會發生，在或接近，同時在一封電子郵件時，這些事件顯示在 [時間表] 檢視。</span><span class="sxs-lookup"><span data-stu-id="412f3-159">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span> 
    
    <span data-ttu-id="412f3-160">[**特殊動作**] 欄中擷取發生後傳遞至您的郵件部分事件。</span><span class="sxs-lookup"><span data-stu-id="412f3-160">Some events that happen post-delivery to your mail are captured in the **Special actions** column.</span></span> <span data-ttu-id="412f3-161">合併的電子郵件時間表，以及對電子郵件後傳遞的特殊動作的資訊可讓系統管理員深入其原則的運作方式，其中最後已路由傳送電子郵件，，而在某些情況下，最終評估為何。</span><span class="sxs-lookup"><span data-stu-id="412f3-161">Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was.</span></span> 

4. <span data-ttu-id="412f3-162">在 [**檢視**] 功能表中，選擇 [**所有電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="412f3-162">In the **View** menu, choose **All email**.</span></span>

    ![使用 [檢視] 功能表的電子郵件和內容的報告之間選擇](../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    <span data-ttu-id="412f3-164">請注意報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**中顯示的標籤。</span><span class="sxs-lookup"><span data-stu-id="412f3-164">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span>

    ![顯示所有的電子郵件資料的威脅總管](../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    <span data-ttu-id="412f3-166">（根據對貴組織的電子郵件所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。</span><span class="sxs-lookup"><span data-stu-id="412f3-166">(Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)</span></span>
    
6. <span data-ttu-id="412f3-167">在報告中，選擇 [檢視使用者的收件匣中的結束電子郵件**已傳遞**]。</span><span class="sxs-lookup"><span data-stu-id="412f3-167">In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.</span></span>

    ![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. <span data-ttu-id="412f3-169">下方圖表中，檢閱圖表下方的**電子郵件**清單。</span><span class="sxs-lookup"><span data-stu-id="412f3-169">Below the chart, review the **Email** list below the chart.</span></span>

    ![下方圖表中，檢視已偵測到的電子郵件的清單](../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. <span data-ttu-id="412f3-171">在清單中，選擇 [項目來檢視電子郵件訊息的相關詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="412f3-171">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="412f3-172">例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="412f3-172">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span>

    ![您可以檢視項目相關的其他資訊](../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. <span data-ttu-id="412f3-174">之後檢視電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。</span><span class="sxs-lookup"><span data-stu-id="412f3-174">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
10. <span data-ttu-id="412f3-175">使用 **+ 動作**清單將套用的動作，例如**將移至刪除**的項目。</span><span class="sxs-lookup"><span data-stu-id="412f3-175">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="412f3-176">這會從收件者的信箱刪除選取的郵件。</span><span class="sxs-lookup"><span data-stu-id="412f3-176">This deletes the selected messages from the recipients' mailboxes.</span></span>

    ![當您選取一或多個電子郵件時，您可以選擇從數個可用的動作](../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a><span data-ttu-id="412f3-178">處理可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="412f3-178">Dealing with suspicious email messages</span></span>

<span data-ttu-id="412f3-179">惡意攻擊者可能會傳送郵件至組織中的釣魚程式嘗試其認證的人員，以及存取您公司的機密資料。</span><span class="sxs-lookup"><span data-stu-id="412f3-179">Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets.</span></span> <span data-ttu-id="412f3-180">若要協助避免這種情況，您可以使用威脅保護服務在 Office 365 中，包括[Exchange Online Protection](exchange-online-protection-overview.md)和[進階威脅防護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-180">To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="412f3-181">不過，它偶爾會發生的攻擊者所傳送包含連結 (URL) 的電子郵件，只後面的點惡意內容 （例如惡意程式碼）。</span><span class="sxs-lookup"><span data-stu-id="412f3-181">However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware).</span></span> <span data-ttu-id="412f3-182">或者，您在貴組織中的人員而遭入侵，和攻擊時他們已洩露，用來傳送電子郵件給您的組織中的其他人員自己的帳戶可能太晚實現。</span><span class="sxs-lookup"><span data-stu-id="412f3-182">Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization.</span></span> <span data-ttu-id="412f3-183">在處理與這些案例中，您可以從使用者收件匣移除可疑電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="412f3-183">As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes.</span></span> <span data-ttu-id="412f3-184">若要這樣做，您可以使用[威脅總管](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-184">To do that, you can use [Threat Explorer](threat-explorer.md).</span></span>

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a><span data-ttu-id="412f3-185">尋找重新路由傳送的電子郵件後採取的動作</span><span class="sxs-lookup"><span data-stu-id="412f3-185">Finding re-routed email messages after actions are taken</span></span>

<span data-ttu-id="412f3-186">威脅總管提供安全性作業小組與他們需要調查可疑的電子郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="412f3-186">Threat Explorer provides your security operations team with the details they need to investigate suspicious email.</span></span> <span data-ttu-id="412f3-187">您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="412f3-187">Your security operations team can:</span></span>

- [<span data-ttu-id="412f3-188">檢視的電子郵件標頭，並下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="412f3-188">View the email headers and download the email body</span></span>](#view-the-email-headers-and-download-the-email-body) 

- [<span data-ttu-id="412f3-189">請檢查傳遞動作及位置</span><span class="sxs-lookup"><span data-stu-id="412f3-189">Check the delivery action and location</span></span>](#check-the-delivery-action-and-location)

- [<span data-ttu-id="412f3-190">檢視您的電子郵件的時間表</span><span class="sxs-lookup"><span data-stu-id="412f3-190">View the timeline of your email</span></span>](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a><span data-ttu-id="412f3-191">檢視的電子郵件標頭，並下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="412f3-191">View the email headers and download the email body</span></span>

<span data-ttu-id="412f3-192">若要預覽電子郵件標頭，並下載電子郵件內文的內文的能力會威脅總管中的強大功能。</span><span class="sxs-lookup"><span data-stu-id="412f3-192">The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer.</span></span> <span data-ttu-id="412f3-193">必須指派適當[的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="412f3-193">Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned.</span></span> <span data-ttu-id="412f3-194">請參閱[預覽角色權限](#preview-role-permissions)。</span><span class="sxs-lookup"><span data-stu-id="412f3-194">See [Preview role permissions](#preview-role-permissions).</span></span>

<span data-ttu-id="412f3-195">若要存取您的郵件標頭和電子郵件下載選項，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="412f3-195">To access your message header and email download options, follow these steps:</span></span> 

1. <span data-ttu-id="412f3-196">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="412f3-196">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="412f3-197">這會帶您前往安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="412f3-197">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="412f3-198">在左側導覽中，選擇 [**威脅管理，** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="412f3-198">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

3. <span data-ttu-id="412f3-199">按一下 [上威脅總管表格中的主題。</span><span class="sxs-lookup"><span data-stu-id="412f3-199">Click on a subject in the Threat Explorer table.</span></span> 

    <span data-ttu-id="412f3-200">如此會開啟彈出式視窗中，位於這兩個標頭預覽] 和 [電子郵件下載連結。</span><span class="sxs-lookup"><span data-stu-id="412f3-200">This opens the flyout, where both header preview and email download links are positioned.</span></span>

    ![威脅總管彈出式視窗與下載和預覽頁面上的連結。](../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> <span data-ttu-id="412f3-202">這項功能不會顯示的電子郵件永遠不會找到在使用者的信箱，如果已卸除一封電子郵件，就會發生或其傳遞失敗。</span><span class="sxs-lookup"><span data-stu-id="412f3-202">This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed.</span></span> <span data-ttu-id="412f3-203">在已從使用者的信箱已刪除的電子郵件的情況下，系統管理員會看到 「 找不到的郵件 」 錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="412f3-203">In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="412f3-204">請檢查傳遞動作及位置</span><span class="sxs-lookup"><span data-stu-id="412f3-204">Check the delivery action and location</span></span>

<span data-ttu-id="412f3-205">在 [[威脅總管 （和即時偵測的資訊）](threat-explorer.md)，您現在可以**傳遞巨集指令**並**傳遞位置**而不是前者**傳遞狀態**] 欄中的資料行。</span><span class="sxs-lookup"><span data-stu-id="412f3-205">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="412f3-206">這會導致更完整的地方您的電子郵件訊息園地圖片。</span><span class="sxs-lookup"><span data-stu-id="412f3-206">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="412f3-207">組件的這項變更的目標是要讓狩獵更容易安全性作業，但的最終結果知道一眼問題電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="412f3-207">Part of the goal of this change is to make hunting easier for security operations, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="412f3-208">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="412f3-208">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="412f3-209">**傳遞動作**-這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="412f3-209">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="412f3-210">**傳遞位置**-其中這封電子郵件路由傳送結果？</span><span class="sxs-lookup"><span data-stu-id="412f3-210">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="412f3-211">傳遞動作是因為現有的原則或偵測電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="412f3-211">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="412f3-212">以下是可能一封電子郵件可以採取的動作：</span><span class="sxs-lookup"><span data-stu-id="412f3-212">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="412f3-213">**已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="412f3-213">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="412f3-214">**Junked** – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="412f3-214">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="412f3-215">**封鎖**– 任何電子郵件遭到隔離的郵件，會失敗，或者已卸除。</span><span class="sxs-lookup"><span data-stu-id="412f3-215">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="412f3-216">（這是完全無法存取的使用者）。</span><span class="sxs-lookup"><span data-stu-id="412f3-216">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="412f3-217">**取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件程式惡意。</span><span class="sxs-lookup"><span data-stu-id="412f3-217">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="412f3-218">傳遞位置顯示原則，以及執行後續傳遞的偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="412f3-218">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="412f3-219">它會連結到傳遞巨集指令。</span><span class="sxs-lookup"><span data-stu-id="412f3-219">It's linked to a Delivery Action.</span></span> <span data-ttu-id="412f3-220">此欄位已新增至提供深入時找到問題郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="412f3-220">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="412f3-221">以下是傳遞位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="412f3-221">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="412f3-222">**收件匣或資料夾**– 電子郵件是在收件匣或資料夾中 （根據您的電子郵件的規則）。</span><span class="sxs-lookup"><span data-stu-id="412f3-222">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="412f3-223">**在內部或外部**– 信箱不存在於雲端上，但內部。</span><span class="sxs-lookup"><span data-stu-id="412f3-223">**On-prem or external** – The mailbox doesn’t exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="412f3-224">**垃圾郵件資料夾**– 電子郵件是在使用者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="412f3-224">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="412f3-225">**刪除的項目] 資料夾**– 電子郵件是在使用者的已刪除項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="412f3-225">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="412f3-226">**隔離**-隔離區，而不是在使用者信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="412f3-226">**Quarantine** – The email in quarantine, and not in a user’s mailbox.</span></span>

- <span data-ttu-id="412f3-227">**失敗**– 電子郵件無法連到信箱。</span><span class="sxs-lookup"><span data-stu-id="412f3-227">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="412f3-228">**丟棄**– 電子郵件會取得某處遺失，在 [郵件流程。</span><span class="sxs-lookup"><span data-stu-id="412f3-228">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="412f3-229">檢視您的電子郵件的時間表</span><span class="sxs-lookup"><span data-stu-id="412f3-229">View the timeline of your email</span></span>
  
<span data-ttu-id="412f3-230">**電子郵件時間表**] 是能方便狩獵安全性作業小組的威脅總管中的欄位。</span><span class="sxs-lookup"><span data-stu-id="412f3-230">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="412f3-231">當多個事件會發生在或接近同一時間上一封電子郵件時，這些事件顯示在 [時間表] 檢視。</span><span class="sxs-lookup"><span data-stu-id="412f3-231">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="412f3-232">[**特殊動作**] 欄中擷取某些電子郵件發生後傳遞的事件。</span><span class="sxs-lookup"><span data-stu-id="412f3-232">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="412f3-233">合併的電子郵件訊息從時間表資訊拍攝後續傳遞任何特殊動作讓系統管理員深入資訊原則和威脅處理 （例如其中已路由傳送郵件，以及在某些情況下，最終評估已）。</span><span class="sxs-lookup"><span data-stu-id="412f3-233">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="412f3-234">相關主題</span><span class="sxs-lookup"><span data-stu-id="412f3-234">Related topics</span></span>

[<span data-ttu-id="412f3-235">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="412f3-235">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="412f3-236">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="412f3-236">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="412f3-237">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="412f3-237">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

