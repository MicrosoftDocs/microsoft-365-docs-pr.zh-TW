---
title: 以系統管理員身分尋找及釋出被隔離的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主題說明 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員如何在 Exchange 系統管理中心 (EAC) 尋找、釋出及報告被隔離的郵件。
ms.openlocfilehash: d7ea57f1dc78b21dae713ca1b9861abafacfc53a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599390"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="5b7a0-103">以系統管理員身分尋找及釋出被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="5b7a0-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="5b7a0-104">本主題說明 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員如何在 Exchange 系統管理中心 (EAC) 尋找、釋出及報告被隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-104">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC).</span></span> <span data-ttu-id="5b7a0-105">Office 365 將郵件移至隔離區是因為被判定為垃圾郵件或符合郵件流程規則 (又稱為傳輸規則)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-105">Office 365 directs messages to quarantine either because they were identified as spam or they matched a mail flow rule (also known as a transport rule).</span></span>

<span data-ttu-id="5b7a0-106">您可以使用安全性與合規性中心 (而非 EAC) 來完成任何這類工作；Exchange 系統管理中心 (EAC) 內的隔離入口網站設定為解除委任。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-106">You can use the Security & Compliance Center instead of the EAC to complete any of these tasks as well; the Quarantine portal within the Exchange admin center (EAC) is set to be decommisioned.</span></span> <span data-ttu-id="5b7a0-107">如需詳細資訊，請參閱[在 Office 365 中隔離電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-107">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="5b7a0-108">隔離的郵件會列在 EAC 中的 **[隔離]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-108">Quarantined messages are listed on the **quarantine** page in EAC.</span></span> <span data-ttu-id="5b7a0-109">根據預設，郵件在 **[收到日期]** 欄位中會以從最新到最舊的方式排序。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-109">By default, messages are sorted from newest to oldest on the **RECEIVED** field.</span></span> <span data-ttu-id="5b7a0-110">此外亦會列出每封郵件的 **[寄件者]**、 **[主旨]** 和 **[到期日]** 值。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-110">**SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message.</span></span> <span data-ttu-id="5b7a0-111">您可按一下這些任一欄位的標頭，以進行排序。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-111">You can sort on any of these fields by clicking their headers.</span></span> <span data-ttu-id="5b7a0-112">如果您再按一下欄標頭，就會反轉排序。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-112">If you click a column header a second time, the sort order reverses.</span></span> <span data-ttu-id="5b7a0-113">**[隔離]** 頁面最多可顯示 500 封郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-113">The **quarantine** page displays a maximum of 500 messages.</span></span>

<span data-ttu-id="5b7a0-114">您可以檢視所有隔離之郵件的清單，也可以指定篩選準則來搜尋特定郵件 (如果您有超過 500 封郵件，則篩選也可以協助精簡結果集)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-114">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages).</span></span> <span data-ttu-id="5b7a0-115">在搜尋並找到特定的隔離郵件後，您可以檢視該郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-115">After searching for and locating a specific quarantined message, you can view details about the message.</span></span> <span data-ttu-id="5b7a0-116">您也可以：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-116">You can also:</span></span>

- <span data-ttu-id="5b7a0-117">釋出郵件給一或多個收件者，並選擇性地向 Microsoft 垃圾郵件分析小組報告該郵件為誤判的郵件 (非垃圾郵件)，而該小組會評估和分析此郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-117">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="5b7a0-118">我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-118">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

- <span data-ttu-id="5b7a0-119">釋出郵件並允許該寄件者的所有後續郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-119">Release the message and allow all future messages from that sender.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b7a0-120">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5b7a0-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5b7a0-121">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="5b7a0-122">若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主題中的「隔離」項目。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-122">To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

- <span data-ttu-id="5b7a0-123">您可以在 **[隔離]** 頁面一次釋出或回報多封郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-123">You can release or report multiple messages at once on the **quarantine** page.</span></span> <span data-ttu-id="5b7a0-124">或者，您可以建立遠端 Windows PowerShell 指令碼來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-124">Alternatively you can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="5b7a0-125">使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 指令程式來搜尋郵件，使用 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) 指令程式來釋出郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-125">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

- <span data-ttu-id="5b7a0-126">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-126">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5b7a0-127">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="5b7a0-127">Having problems?</span></span> <span data-ttu-id="5b7a0-128">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-128">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="5b7a0-129">使用進階搜尋來篩選和尋找隔離郵件</span><span class="sxs-lookup"><span data-stu-id="5b7a0-129">Use advanced search to filter and locate quarantined messages</span></span>

<span data-ttu-id="5b7a0-p109">在 Exchange 系統管理中心 (EAC)，您可以使用進階搜尋，根據數個不同條件來篩選隔離的郵件。這些條件可以分開使用，也可以一起使用。搜尋將會提供符合所有篩選準則的郵件清單。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>

1. <span data-ttu-id="5b7a0-133">在 EAC 中瀏覽至 **[保護]** \> **[隔離]**，然後按一下 **[進階搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-133">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>

2. <span data-ttu-id="5b7a0-134">在 **[進階搜尋]** 視窗中，選取下列任意條件組合。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-134">In the **Advanced search** window, select any combination of the following conditions.</span></span> <span data-ttu-id="5b7a0-135">選取關聯的核取方塊，以啟用每個條件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-135">Select the associated check box to enable each condition.</span></span> <span data-ttu-id="5b7a0-136">不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-136">Wildcards aren't supported.</span></span>

   1. <span data-ttu-id="5b7a0-137">**郵件識別碼**：您可以使用此參數來執行特定郵件的目標式搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-137">**Message ID**: You can use this parameter to perform a targeted search for a specific message.</span></span> <span data-ttu-id="5b7a0-138">例如，如果組織中的某位使用者傳送了郵件或者他是郵件的預定收件者，但郵件未到達目的地，則您可使用郵件追蹤功能搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-138">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature.</span></span> <span data-ttu-id="5b7a0-139">如需詳細資訊，請參閱 [執行訊息追蹤和檢視結果](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-139">For details, see [Run a Message Trace and View Results](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results).</span></span> <span data-ttu-id="5b7a0-140">如果您發現郵件已傳送到隔離區 (或許因為該郵件符合了某個規則或被視為垃圾郵件)，指定其郵件識別碼，即可在隔離區中輕鬆找到此郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-140">If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID.</span></span> <span data-ttu-id="5b7a0-141">務必包括完整的郵件識別碼字串。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-141">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="5b7a0-142">這可能包括角括號 (\<\>)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-142">This might include angle brackets (\<\>).</span></span>

   2. <span data-ttu-id="5b7a0-143">**寄件者電子郵件地址**：指定寄送郵件人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-143">**Sender email address**: Specify the email address of the person who sent the message.</span></span>

   3. <span data-ttu-id="5b7a0-144">**收件者電子郵件地址**：指定郵件預定收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-144">**Recipient email address**: Specify the email address of the intended recipient of the message.</span></span>

   4. <span data-ttu-id="5b7a0-145">**主旨**：指定郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-145">**Subject**: Specify the subject line text of the message.</span></span>

   5. <span data-ttu-id="5b7a0-146">**已接收**：您可以選取郵件是由隔離區在過去 24 小時 ( **今天**)、過去 48 小時 (**最近 2 天**)、過去一週 (**最近 7 天**) 內接收，也可以選取隔離區接收郵件的自訂時間間隔。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-146">**Received**: You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span>

   6. <span data-ttu-id="5b7a0-147">**過期**：您可以選取郵件將在未來 24 小時 ( **今天**)、未來 48 小時 ( **未來 2 天**)、未來一週 ( **未來 7 天**) 內從隔離區刪除，也可以選取從隔離區刪除郵件的自訂時間間隔。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-147">**Expires**: You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="5b7a0-148">根據預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而符合郵件流程規則的隔離郵件會根據您在預設內容篩選原則中設定的保留期，最多保留在隔離區 30 天。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-148">By default, spam-quarantined messages are kept in quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="5b7a0-149">超過這段時間後，Office 365 就會刪除郵件，而無法擷取。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-149">After this period of time Office 365 deletes the messages and they are not retrievable.</span></span> <span data-ttu-id="5b7a0-150">符合郵件流程規則的隔離郵件無法設定保留期限。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-150">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="5b7a0-151">不過，您可以透過內容篩選原則的 **[保留垃圾郵件的天數]** 設定，縮短垃圾郵件隔離郵件的保留期限。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-151">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="5b7a0-152">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-152">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   7. <span data-ttu-id="5b7a0-153">**類型** 您可指定是要搜尋被識別為 **[垃圾郵件]** 的隔離郵件，或是搜尋符合某個郵件流程規則 (**傳輸規則**) 的郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-153">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a mail flow rule (**Transport rule**).</span></span>

3. <span data-ttu-id="5b7a0-154">按一下 **[確定]**，開始執行進階搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-154">Click **OK** to start running the advanced search.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b7a0-155">若要清除搜尋準則並檢視隔離中的所有郵件，請清除 **[進階搜尋]** 視窗中的所有核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-155">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span>

<span data-ttu-id="5b7a0-p113">搜尋郵件後，符合您指定之準則的結果會顯示在使用者介面中。EAC 中最多可以顯示 500 封郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span>

## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="5b7a0-158">檢視特定隔離郵件的詳細資料</span><span class="sxs-lookup"><span data-stu-id="5b7a0-158">View details about a specific quarantined message</span></span>

<span data-ttu-id="5b7a0-159">在 **[隔離]** 頁面找到特定隔離郵件之後，您即可檢視其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-159">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span>

1. <span data-ttu-id="5b7a0-160">在 **[隔離]** 頁面中，選取特定郵件，畫面右邊的詳細資料窗格中會顯示該郵件的屬性摘要。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-160">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span>

   <span data-ttu-id="5b7a0-161">**[郵件狀態]** 值如下：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-161">The **Message status** values are as follows:</span></span>

   - <span data-ttu-id="5b7a0-162">**類型**：指出郵件被識別為 **[垃圾郵件]** 或是符合某個郵件流程規則 (**傳輸規則)**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-162">**Type**: Denotes whether the message has been identified as **Spam** or matched a mail flow rule (**Transport rule**).</span></span>

   - <span data-ttu-id="5b7a0-163">**到期**：將從隔離刪除此郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-163">**Expires**: The date when the message will be deleted from the quarantine.</span></span>

   <span data-ttu-id="5b7a0-164">**[郵件詳細資料]** 值如下：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-164">The **Message details** values are as follows:</span></span>

   - <span data-ttu-id="5b7a0-165">**寄件者**：傳送郵件之人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-165">**Sender**: The email address of the person who sent the message.</span></span>

   - <span data-ttu-id="5b7a0-166">**主旨**：郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-166">**Subject**: The subject line text of the message.</span></span>

   - <span data-ttu-id="5b7a0-167">**收到日期**：隔離收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-167">**Received**: The date on which the message was received by the quarantine.</span></span>

   - <span data-ttu-id="5b7a0-168">**大小**：郵件的大小，單位為 KB，如果郵件大小超過 999 KB 則為 MB。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-168">**Size**: The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span>

   - <span data-ttu-id="5b7a0-169">**檢視郵件標頭**：按一下此連結可開啟 **[郵件標頭]** 對話方塊，以便您檢視郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-169">**View message header**: Click this link to open the **message header** dialog box, which lets you view the message header text.</span></span> <span data-ttu-id="5b7a0-170">You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span><span class="sxs-lookup"><span data-stu-id="5b7a0-170">You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span></span> <span data-ttu-id="5b7a0-171">Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span><span class="sxs-lookup"><span data-stu-id="5b7a0-171">Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span>

    > [!TIP]
    > <span data-ttu-id="5b7a0-172">如需服務所插入之特定反垃圾郵件郵件標頭欄位的相關資訊，請參閱[反垃圾郵件訊息標頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-172">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

   - <span data-ttu-id="5b7a0-173">**檢閱電子郵件** 按一下此連結以檢閱郵件文字。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-173">**Preview email message** Click this link to review the text of the message.</span></span>

2. <span data-ttu-id="5b7a0-174">如果您按兩下隔離郵件，則會開啟 **[隔離郵件]** 視窗並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-174">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span>

   - <span data-ttu-id="5b7a0-175">**已釋出**：已釋出其郵件的所有電子郵件地址清單 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-175">**Released to**: A list of all email addresses to whom the message has been released, if any.</span></span>

   - <span data-ttu-id="5b7a0-176">**尚未釋出**：尚未釋出其郵件的所有電子郵件地址清單 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-176">**Not yet released to**: A list of all email addresses to whom the message has not been released, if any.</span></span> <span data-ttu-id="5b7a0-177">You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span><span class="sxs-lookup"><span data-stu-id="5b7a0-177">You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span>

   - <span data-ttu-id="5b7a0-178">**郵件識別碼**：在郵件標頭中找到的網際網路郵件識別碼 (也稱為用戶端識別碼)。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-178">**Message ID**: The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span>

   <span data-ttu-id="5b7a0-179">按一下 **[關閉]** 返回主要隔離窗格。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-179">Click **Close** to return to the main quarantine pane.</span></span>

## <a name="release-messages-from-quarantine"></a><span data-ttu-id="5b7a0-180">從隔離區釋出郵件</span><span class="sxs-lookup"><span data-stu-id="5b7a0-180">Release messages from quarantine</span></span>

<span data-ttu-id="5b7a0-181">如果您想要將郵件釋出給收件者，您可以：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-181">If you want to release messages to recipients, your options are:</span></span>

- [<span data-ttu-id="5b7a0-182">釋出隔離的郵件並允許該寄件者的後續郵件</span><span class="sxs-lookup"><span data-stu-id="5b7a0-182">Release a quarantined message and allow future messages from the sender</span></span>](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [<span data-ttu-id="5b7a0-183">釋出隔離的郵件給特定收件者，而不將其回報為誤判</span><span class="sxs-lookup"><span data-stu-id="5b7a0-183">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [<span data-ttu-id="5b7a0-184">釋出一或多個隔離的郵件給所有收件者</span><span class="sxs-lookup"><span data-stu-id="5b7a0-184">Release one or more quarantined messages to all recipients</span></span>](#release-one-or-more-quarantined-messages-to-all-recipients)

- [<span data-ttu-id="5b7a0-185">釋出一或多個隔離的郵件給所有收件者並將其回報為誤判</span><span class="sxs-lookup"><span data-stu-id="5b7a0-185">Release one or more quarantined messages to all recipients and report false positives</span></span>](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="5b7a0-186">釋出隔離的郵件並允許該寄件者的後續郵件</span><span class="sxs-lookup"><span data-stu-id="5b7a0-186">Release a quarantined message and allow future messages from the sender</span></span>

1. <span data-ttu-id="5b7a0-187">在 EAC 中瀏覽至 **[保護]** \> **[隔離]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-187">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="5b7a0-188">按一下選取郵件，然後按一下 **[釋出郵件]** 圖示，如以下螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-188">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span>

   ![顯示隔離頁面，其中會反白顯示發行訊息圖示，並顯示發行選項](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   <span data-ttu-id="5b7a0-190">從下拉式清單中按一下 **[釋出選取的郵件並允許寄件者]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-190">Click **Release selected message and allow sender** from the drop-down list.</span></span>

3. <span data-ttu-id="5b7a0-191">**[釋出郵件並允許寄件者]** 對話方塊即會開啟。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-191">The **release message and allow sender** dialog box opens.</span></span> <span data-ttu-id="5b7a0-192">您可以選擇是否要向 Microsoft 回報郵件，然後按一下 **[釋出並允許]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-192">Optionally, you can choose to report the message to Microsoft, then click **release and allow**.</span></span> <span data-ttu-id="5b7a0-193">郵件將會釋出給所有該郵件的收件者，並允許該寄件者的所有後續郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-193">The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed.</span></span> <span data-ttu-id="5b7a0-194">然而，如果該郵件因為郵件流程規則或封鎖的寄件者而被隔離，則寄件者後續郵件仍會持續封鎖。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-194">However, if this message was quarantined because of a mail flow rule or blocked sender, the sender will continue to be blocked for future messages.</span></span>

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="5b7a0-195">釋出隔離的郵件給特定收件者，而不將其回報為誤判</span><span class="sxs-lookup"><span data-stu-id="5b7a0-195">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>

1. <span data-ttu-id="5b7a0-196">在 EAC 中瀏覽至 **[保護]** \> **[隔離]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-196">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="5b7a0-197">選取郵件並按一下 **[釋出郵件]** 圖示，接著在下拉式清單中按一下 **[將郵件釋出給特定收件者]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-197">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span>

3. <span data-ttu-id="5b7a0-198">在 **[釋出郵件]** 對話方塊中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5b7a0-198">In the **release message** dialog box, select one of the following options:</span></span>

   - <span data-ttu-id="5b7a0-p117">**將郵件釋出給所有收件者** 如果您選取此選項，請注意，您只能將郵件釋出給同一位收件者一次。如果收件者先前已收到郵件，系統不會再將郵件釋出給該名收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-p117">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

   - <span data-ttu-id="5b7a0-201">**將郵件釋出給指定的收件者** 選取郵件釋出的目標收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-201">**Release message to specified recipients** Select the recipient(s) to whom the message can be released.</span></span> <span data-ttu-id="5b7a0-202">由於您只能將郵件釋出給每位收件者一次，因此唯有能當做釋出目標的收件者會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-202">Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list.</span></span> <span data-ttu-id="5b7a0-203">您可以選擇多位收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-203">Multi-selection is supported.</span></span> <span data-ttu-id="5b7a0-204">完成收件者選擇後，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-204">After making your recipient selections, click **add**.</span></span>

4. <span data-ttu-id="5b7a0-205">按一下 **[釋出]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-205">Click **release**.</span></span>

<span data-ttu-id="5b7a0-206">如果按一下 **[重新整理** ![重新整理圖示](../media/ITPro-EAC-RefreshIcon.gif)] 來重新整理資料，然後按兩下郵件，則會看到郵件已釋出到目標收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-206">If you click **Refresh** ![Refresh Icon](../media/ITPro-EAC-RefreshIcon.gif) to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span>

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="5b7a0-207">釋出一或多個隔離的郵件給所有收件者</span><span class="sxs-lookup"><span data-stu-id="5b7a0-207">Release one or more quarantined messages to all recipients</span></span>

1. <span data-ttu-id="5b7a0-208">在 EAC 中瀏覽至 **[保護]** \> **[隔離]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-208">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="5b7a0-209">按一下選取郵件，或使用 Shift 鍵選取多封郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-209">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="5b7a0-210">然後按一下 **[釋出郵件]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-210">Then click the **Release Message** icon.</span></span>

3. <span data-ttu-id="5b7a0-211">從下拉式清單中按一下 **[釋出選取的郵件至所有收件者]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-211">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span>

4. <span data-ttu-id="5b7a0-212">警告對話方塊隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-212">The warning dialog box opens.</span></span> <span data-ttu-id="5b7a0-213">如果您想要繼續，請閱讀警告並選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-213">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="5b7a0-214">如果您選取此選項，請注意，您只能將郵件釋出給同一位收件者一次。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-214">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="5b7a0-215">如果收件者先前已收到郵件，系統不會再將郵件釋出給該名收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-215">If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="5b7a0-216">釋出一或多個隔離的郵件給所有收件者並將其回報為誤判</span><span class="sxs-lookup"><span data-stu-id="5b7a0-216">Release one or more quarantined messages to all recipients and report false positives</span></span>

1. <span data-ttu-id="5b7a0-217">在 EAC 中瀏覽至 **[保護]** \> **[隔離]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-217">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="5b7a0-218">按一下選取郵件，或使用 Shift 鍵選取多封郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-218">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="5b7a0-219">然後按一下 **[釋出郵件]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-219">Then click the **Release Message** icon.</span></span>

3. <span data-ttu-id="5b7a0-220">從下拉式清單中按一下 **[釋出選取的郵件並將其回報為誤判]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-220">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span>

4. <span data-ttu-id="5b7a0-221">警告對話方塊隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-221">The warning dialog box opens.</span></span> <span data-ttu-id="5b7a0-222">如果您想要繼續，請閱讀警告並選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-222">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="5b7a0-223">如果您選取此選項，請注意，您只能將郵件釋出給同一位收件者一次。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-223">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="5b7a0-224">如果收件者先前已收到郵件，系統不會再將郵件釋出給該名收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-224">If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

   <span data-ttu-id="5b7a0-225">當您選擇此動作時，系統會將郵件釋出給所有尚未收到該郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-225">When you choose this option, the message will be released to all recipients who have not yet received it.</span></span> <span data-ttu-id="5b7a0-226">如果這是垃圾郵件隔離郵件，則也會向 Microsoft 垃圾郵件分析小組進行回報，該小組會評估和分析此郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-226">If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="5b7a0-227">我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-227">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

> [!TIP]
> <span data-ttu-id="5b7a0-228">按照[如何協助確保郵件不會被標示為垃圾郵件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步驟，協助確保郵件不會被標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-228">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span>

<span data-ttu-id="5b7a0-229">如果按一下 **[重新整理** ![重新整理圖示](../media/ITPro-EAC-RefreshIcon.gif)] 圖示來重新整理資料，然後按兩下郵件，則會看到郵件已釋出到目標收件者。</span><span class="sxs-lookup"><span data-stu-id="5b7a0-229">If you click the **Refresh**![Refresh Icon](../media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5b7a0-230">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5b7a0-230">For more information</span></span>

[<span data-ttu-id="5b7a0-231">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="5b7a0-231">Quarantine FAQ</span></span>](quarantine-faq.md)
