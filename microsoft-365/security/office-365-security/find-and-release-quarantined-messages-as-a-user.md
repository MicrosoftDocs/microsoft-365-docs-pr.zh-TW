---
title: 以 Office 365 使用者身分尋找及釋出隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 身為 Office 365 使用者，您可以使用下列兩種方法之一，來管理您已隔離垃圾郵件的訊息：直接回覆傳送給您的垃圾郵件通知 (如果您的系統管理員設定了此功能的話)，或者使用安全性與合規性中心的垃圾郵件隔離功能。
ms.openlocfilehash: c912c19571cde31c39f4ca3f44c7628ba8b29526
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970459"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="4e49f-103">以 Office 365 使用者身分尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="4e49f-103">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="4e49f-104">身為 Office 365 使用者，您可以使用下列兩種方法之一，來管理應該要傳送給您卻傳送至隔離的郵件：[直接回覆傳送給您的垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md) (如果您的系統管理員設定了此功能的話)，或者使用安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4e49f-104">As an Office 365 user, you can manage messages that were sent to quarantine instead of sent to you in one of two ways: by [responding to spam notifications sent to you directly](use-spam-notifications-to-release-and-report-quarantined-messages.md) (if your admin has set this up), or by using the Security &amp; Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="4e49f-105">如果您是系統管理員，您可以為組織中的其他人[管理隔離的郵件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-105">If you're an admin, you can [manage quarantined messages](manage-quarantined-messages-and-files.md) for other people in your organization.</span></span>

## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a><span data-ttu-id="4e49f-106">檢視傳送至隔離區而非傳送給您的郵件</span><span class="sxs-lookup"><span data-stu-id="4e49f-106">View messages that were sent to quarantine instead of to you</span></span>

1. <span data-ttu-id="4e49f-107">使用您的公司或學校帳戶登入 Office 365，並[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-107">Sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) using your work or school account.</span></span>

2. <span data-ttu-id="4e49f-108">展開左側的 [威脅管理]\*\*\*\*，依序選擇 [檢閱]\*\*\*\* 與 [隔離]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e49f-108">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4e49f-109">若要直接移至安全性與合規性中心的 [隔離]\*\*\*\* 頁面，請使用這個 URL：> [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="4e49f-109">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

<span data-ttu-id="4e49f-110">根據預設，安全性與合規性中心會顯示所有因被視為垃圾郵件而遭到隔離的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="4e49f-110">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="4e49f-111">郵件會依據接收的 [日期]\*\*\*\*，從最新排到最舊。</span><span class="sxs-lookup"><span data-stu-id="4e49f-111">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="4e49f-112">系統也會顯示每封郵件的 [寄件者]\*\*\*\*、[主旨]\*\*\*\* 與到期日 (位於 [到期]\*\*\*\* 底下)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-112">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="4e49f-113">您可以按一下對應的欄標題來依該欄位排序；再按一下欄標題則可將排序順序倒轉。</span><span class="sxs-lookup"><span data-stu-id="4e49f-113">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="4e49f-114">您可以檢視含有所有隔離郵件的清單，或者使用篩選來搜尋特定郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-114">You can view a list of all quarantined messages, or you can search for specific messages by filtering.</span></span> <span data-ttu-id="4e49f-115">您只能夠對最多 100 封郵件執行大量作業；如果您擁有的郵件超過 100 封，進行篩選也有助於減少結果集。</span><span class="sxs-lookup"><span data-stu-id="4e49f-115">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="4e49f-116">您可以選擇下拉式清單中的選項，根據單一隔離原因快速篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-116">You can quickly filter messages for a single quarantine reason by choosing an option from the drop-down list.</span></span> <span data-ttu-id="4e49f-117">選項包括：</span><span class="sxs-lookup"><span data-stu-id="4e49f-117">Options include:</span></span>

- <span data-ttu-id="4e49f-118">識別為垃圾郵件的郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-118">Mail identified as spam.</span></span> <span data-ttu-id="4e49f-119">系統會根據預設顯示這些受隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-119">These quarantined messages are shown by default.</span></span>

- <span data-ttu-id="4e49f-120">識別為大宗郵件的郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-120">Mail identified as bulk mail.</span></span>

<span data-ttu-id="4e49f-121">當您找到特定隔離郵件後，請按一下郵件來檢視其詳細資料並採取動作。</span><span class="sxs-lookup"><span data-stu-id="4e49f-121">After you find a specific quarantined message, click the message to view details about it, and take actions.</span></span> <span data-ttu-id="4e49f-122">您可以將郵件釋出至您的信箱、預覽郵件、下載郵件，或是從隔離中立即刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-122">You can release the message to your mailbox, preview the message, download the message, or delete the message from quarantine immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="4e49f-123">您必須在 Office 365 中擁有系統管理員權限，才能處理傳送給其他使用者的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-123">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users.</span></span>

## <a name="to-filter-and-find-quarantined-messages"></a><span data-ttu-id="4e49f-124">篩選並尋找隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="4e49f-124">To filter and find quarantined messages</span></span>

<span data-ttu-id="4e49f-125">如果您擁有很多隔離的項目，您可以透過篩選，將數量減少至可管理的狀態。</span><span class="sxs-lookup"><span data-stu-id="4e49f-125">If you have a lot of quarantined items, you can reduce the number to a manageable set by filtering them.</span></span>

1. <span data-ttu-id="4e49f-126">在 [隔離]\*\*\*\* 頁面上，選擇您想要檢視 [垃圾郵件]\*\*\*\* 或 [大宗郵件]\*\*\*\* 的受隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-126">On the **Quarantine** page, choose whether you want to view **spam** or **bulk** quarantined messages.</span></span>

2. <span data-ttu-id="4e49f-127">在 [結果排序依據]\*\*\*\* 底下，透過設定一或多個合適篩選來選擇任何條件組合 (您無法在此時使用萬用字元)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-127">Under **Sort results by**, choose any combination of conditions by setting the appropriate filter or filters (you can't use wildcards at this time).</span></span> <span data-ttu-id="4e49f-128">有數種條件可供您選擇，包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="4e49f-128">There are several conditions you can choose, including the following:</span></span>

   - <span data-ttu-id="4e49f-129">**郵件識別碼**：當您知道郵件識別碼時，使用這個選項來選取特定郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-129">**Message ID** Use this to select a specific message when you know the message ID.</span></span>

     <span data-ttu-id="4e49f-130">例如，如果組織中的某位使用者傳送了特定郵件或者他是郵件的預定收件者，但郵件未到達目的地，則您可使用郵件追蹤功能搜尋郵件 (請參閱[安全性與合規性中心內的郵件追蹤](message-trace-scc.md))(英文版)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-130">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](message-trace-scc.md)).</span></span> <span data-ttu-id="4e49f-131">如果您發現郵件已傳送到隔離區 (或許因為該郵件符合了某個郵件流程規則或被視為垃圾郵件)，指定其郵件識別碼，即可在隔離區中輕鬆找到此郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-131">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its Message ID.</span></span> <span data-ttu-id="4e49f-132">務必包括完整的郵件識別碼字串。</span><span class="sxs-lookup"><span data-stu-id="4e49f-132">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="4e49f-133">這可能包括角括號 (\<\>)，例如：</span><span class="sxs-lookup"><span data-stu-id="4e49f-133">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="4e49f-134">**寄件者電子郵件地址**：選擇依單一寄件者電子郵件地址來篩選。</span><span class="sxs-lookup"><span data-stu-id="4e49f-134">**Sender email address** Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="4e49f-135">**收件者電子郵件地址**：選擇做為篩選依據的單一收件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4e49f-135">**Recipient email address** Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="4e49f-136">**主旨**：輸入您要尋找之電子郵件地址的主旨。</span><span class="sxs-lookup"><span data-stu-id="4e49f-136">**Subject** Enter the subject of an email address you want to find.</span></span>

   - <span data-ttu-id="4e49f-137">**日期範圍**：您可以選擇根據郵件受到隔離的日期來進行篩選。</span><span class="sxs-lookup"><span data-stu-id="4e49f-137">**Date range** You can choose to filter by the date the message was sent to quarantine.</span></span> <span data-ttu-id="4e49f-138">您可以指定某個日期或一個日期範圍，包括時間。</span><span class="sxs-lookup"><span data-stu-id="4e49f-138">You can specify the date or a date range, including the time.</span></span>

   - <span data-ttu-id="4e49f-139">**到期日**：若要依到期日篩選，請選擇 **[進階篩選]**。</span><span class="sxs-lookup"><span data-stu-id="4e49f-139">**Expiration date** To filter by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="4e49f-140">您可以選取將於未來 24 小時 ([今天]\*\*\*\*)、未來 48 小時 ([未來 2 天]\*\*\*\*)、未來一週 ([未來 7 天]\*\*\*\*) 內從隔離刪除的郵件，或者，您可以選取自訂的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="4e49f-140">You can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="4e49f-141">根據預設，垃圾郵件與大宗郵件會在隔離中保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="4e49f-141">By default, spam and bulk messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="4e49f-142">不過您可以設定此時間，而您的系統管理員可能也已經設定了不同的隔離保留期間。</span><span class="sxs-lookup"><span data-stu-id="4e49f-142">However, this time period is configurable and your admin might have set a different quarantine retention period.</span></span> <span data-ttu-id="4e49f-143">當 Office 365 從隔離中刪除某封郵件後，您就無法復原該郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-143">When Office 365 deletes a message from quarantine, you can't get it back.</span></span>

## <a name="view-details-for-a-specific-message"></a><span data-ttu-id="4e49f-144">檢視特定郵件的詳細資料</span><span class="sxs-lookup"><span data-stu-id="4e49f-144">View details for a specific message</span></span>

<span data-ttu-id="4e49f-145">選取郵件後，您會在頁面右側的窗格中看到該郵件屬性的摘要。</span><span class="sxs-lookup"><span data-stu-id="4e49f-145">After you select a message, you'll see a summary of the message properties in a pane on the right side of the page.</span></span>

- <span data-ttu-id="4e49f-146">**郵件識別碼**：郵件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="4e49f-146">**Message ID:** The unique identifier for the message.</span></span>

- <span data-ttu-id="4e49f-147">**寄件者地址**：傳送郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="4e49f-147">**Sender Address:** Who sent the message.</span></span>

- <span data-ttu-id="4e49f-148">**接收時間**：收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="4e49f-148">**Received:** The date the message was received.</span></span>

- <span data-ttu-id="4e49f-149">**主旨**：郵件 [主旨] 列中的文字。</span><span class="sxs-lookup"><span data-stu-id="4e49f-149">**Subject:** The text of the Subject line in the message.</span></span>

- <span data-ttu-id="4e49f-150">**隔離原因**：顯示是否將郵件識別為 **[垃圾郵件]** 或 **[大量]**。</span><span class="sxs-lookup"><span data-stu-id="4e49f-150">**Quarantine reason:** Shows if a message has been identified as **Spam** or **Bulk**.</span></span>

- <span data-ttu-id="4e49f-151">**到期**：將從隔離刪除此郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="4e49f-151">**Expires:** The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="4e49f-152">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-152">**Released to:** All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="4e49f-153">**尚未釋出給：** 該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-153">**Not yet released to:** All email addresses (if any) to which the message has not been released.</span></span> <span data-ttu-id="4e49f-154">如果想要將郵件釋出到您的信箱，您可以選擇 [釋出]\*\*\*\* (下一節將詳細說明如何釋出郵件)。</span><span class="sxs-lookup"><span data-stu-id="4e49f-154">You can choose **Release** if you want to release the message to your mailbox (more about releasing messages in the next section).</span></span>

<span data-ttu-id="4e49f-155">您可以選擇下列其中一個選項，以取得有關郵件的更多詳細資料：</span><span class="sxs-lookup"><span data-stu-id="4e49f-155">You can get even more details about the message by choosing one of the following options:</span></span>

- <span data-ttu-id="4e49f-156">**檢視郵件標頭**：選擇此項目來查看郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="4e49f-156">**View message header** Choose this to see the message header text.</span></span> <span data-ttu-id="4e49f-157">若要深入分析標頭，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器]\*\*\*\* 來移至遠端連線分析程式 (如果您想在不離開 Office 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟])。</span><span class="sxs-lookup"><span data-stu-id="4e49f-157">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose Open in a new tab if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="4e49f-158">將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]。</span><span class="sxs-lookup"><span data-stu-id="4e49f-158">Paste the message header onto the page in the Message Header Analyzer section, and choose Analyze headers.</span></span>

- <span data-ttu-id="4e49f-159">**預覽郵件**：讓您查看郵件內文文字的原始版本或 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="4e49f-159">**Preview message** Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="4e49f-160">在 HTML 檢視中會停用連結。</span><span class="sxs-lookup"><span data-stu-id="4e49f-160">In the HTML view, links are disabled.</span></span>

## <a name="manage-your-quarantined-messages"></a><span data-ttu-id="4e49f-161">管理隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="4e49f-161">Manage your quarantined messages</span></span>

<span data-ttu-id="4e49f-162">選取了單一郵件或一組郵件後，您會有多種方式可以管理受到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-162">After you select a message or group of messages, you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="4e49f-163">不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="4e49f-163">Do nothing.</span></span> <span data-ttu-id="4e49f-164">如果您選擇不執行任何動作，該郵件會在到期後由 Office 365 自動刪除。</span><span class="sxs-lookup"><span data-stu-id="4e49f-164">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="4e49f-165">請記得，當 Office 365 從隔離中刪除某封郵件後，您就無法復原該郵件。</span><span class="sxs-lookup"><span data-stu-id="4e49f-165">Remember, when Office 365 deletes a message from quarantine, you can't get it back.</span></span>

- <span data-ttu-id="4e49f-166">**釋出郵件**：釋出隔離的郵件 (或一組郵件)，將郵件傳送到您的信箱。</span><span class="sxs-lookup"><span data-stu-id="4e49f-166">**Release message** Release a quarantined message (or set of messages) so that the message is sent to your mailbox.</span></span> <span data-ttu-id="4e49f-167">釋出郵件時，您可以選擇是否要將該郵件回報給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="4e49f-167">When you release a message, you have the option to report the message to Microsoft for analysis.</span></span>

    <span data-ttu-id="4e49f-168">選擇回報郵件時 (也稱為將郵件回報為誤判)，系統會將該郵件回報給 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="4e49f-168">When you choose to report a message, also called reporting a message as a false positive, the message is reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="4e49f-169">該小組會評估並分析誤判的郵件，且根據分析結果，可能會調整適用於全服務的垃圾郵件內容篩選規則，以允許這些郵件通過。</span><span class="sxs-lookup"><span data-stu-id="4e49f-169">The team evaluates and analyzes false positive messages, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow these messages through.</span></span>

- <span data-ttu-id="4e49f-170">**從隔離中移除**：立即將郵件從隔離中刪除而不釋出到信箱。</span><span class="sxs-lookup"><span data-stu-id="4e49f-170">**Remove from quarantine** Deletes the message immediately from quarantine without releasing the message to your mailbox.</span></span>
