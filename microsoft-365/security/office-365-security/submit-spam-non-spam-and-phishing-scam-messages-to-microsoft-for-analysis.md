---
title: 手動將郵件提交給 Microsoft 進行分析
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '您和您的使用者可以將假的否定和誤報垃圾郵件提交給 Microsoft 進行分析。 '
ms.openlocfilehash: 77807f710743d98dc2e1564f804b6a67add67def
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529046"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="cb123-103">手動將郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="cb123-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="cb123-104">如果您是 Office 365 組織中 Exchange Online 信箱的系統管理員，建議您在 Office 365 安全性 & 規範中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="cb123-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="cb123-105">如需詳細資訊，請參閱[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="cb123-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="cb123-106">當您組織中的使用者在其收件匣中收到垃圾郵件（垃圾郵件）或網路釣魚郵件時，或是因為郵件標示為垃圾郵件而未收到合法電子郵件時，可能會令人感到沮喪。</span><span class="sxs-lookup"><span data-stu-id="cb123-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="cb123-107">我們不斷微調垃圾郵件篩選器，使其更準確。</span><span class="sxs-lookup"><span data-stu-id="cb123-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="cb123-108">您和您的使用者可以提交誤報（不良電子郵件標記為壞）、誤報（允許錯誤郵件）和網路以進行分析，以協助此程式。</span><span class="sxs-lookup"><span data-stu-id="cb123-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="cb123-109">由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。</span><span class="sxs-lookup"><span data-stu-id="cb123-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="cb123-110">將漏報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb123-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="cb123-111">在 Outlook 和網頁型 Outlook （先前稱為 Outlook Web App）中的使用者可以使用 Microsoft Outlook 的報告訊息增益集，而不是使用下列程式來報告漏報。</span><span class="sxs-lookup"><span data-stu-id="cb123-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="cb123-112">如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="cb123-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="cb123-113">如果您收到的郵件透過應識別為垃圾郵件篩選的垃圾郵件篩選，您可以視需要將郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。</span><span class="sxs-lookup"><span data-stu-id="cb123-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="cb123-114">分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。</span><span class="sxs-lookup"><span data-stu-id="cb123-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="cb123-115">使用下列其中一個收件者建立新的空白電子郵件訊息：</span><span class="sxs-lookup"><span data-stu-id="cb123-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="cb123-116">**垃圾郵件**：`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="cb123-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="cb123-117">**網路釣魚**：`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="cb123-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="cb123-118">將垃圾郵件或網路釣魚郵件拖放到新郵件中。</span><span class="sxs-lookup"><span data-stu-id="cb123-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="cb123-119">這會將垃圾郵件或網路釣魚郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="cb123-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="cb123-120">請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。</span><span class="sxs-lookup"><span data-stu-id="cb123-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="cb123-121">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="cb123-122">請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="cb123-123">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="cb123-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="cb123-124">使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="cb123-125">當您完成時，按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="cb123-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="cb123-126">系統管理員可以使用數種不同的方式封鎖正 misidentified 為垃圾郵件的特定郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="cb123-127">如需詳細資訊，請參閱[在 Office 365 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cb123-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="cb123-128">將誤報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb123-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="cb123-129">您不用使用下列程式來報告誤報，Outlook 和網頁型 Outlook 中的使用者可以使用 Microsoft Outlook 的報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="cb123-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="cb123-130">如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="cb123-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="cb123-131">如果郵件被錯誤地辨識為垃圾郵件，您可以將郵件提交給 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="cb123-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="cb123-132">分析員會評估郵件，並根據分析的結果，可以調整整個服務篩選器以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="cb123-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="cb123-133">`not_junk@office365.microsoft.com`以收件者的身分建立新的空白電子郵件訊息：</span><span class="sxs-lookup"><span data-stu-id="cb123-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="cb123-134">將 misidentified 郵件拖曳並放入新的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="cb123-135">這會將 misidentified 郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="cb123-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="cb123-136">請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。</span><span class="sxs-lookup"><span data-stu-id="cb123-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="cb123-137">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="cb123-138">請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="cb123-139">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="cb123-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="cb123-140">使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="cb123-141">當您完成時，按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="cb123-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="cb123-142">系統管理員有幾種不同的方式可讓特定郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="cb123-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="cb123-143">如需詳細資訊，請參閱[在 Office 365 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cb123-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="cb123-144">建立郵件流程規則，以接收報告給 Microsoft 的郵件副本</span><span class="sxs-lookup"><span data-stu-id="cb123-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="cb123-145">您可以建立郵件流程規則（也稱為傳輸規則），以使用本主題中所述的方法來尋找向 Microsoft 報告的電子郵件訊息，而且您可以設定密件副本收件者接收這些報告的郵件副本。</span><span class="sxs-lookup"><span data-stu-id="cb123-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="cb123-146">您可以在 Exchange 系統管理中心（EAC）和 PowerShell （Office 365 客戶的 Exchange Online PowerShell 中建立郵件流程規則;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。</span><span class="sxs-lookup"><span data-stu-id="cb123-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cb123-147">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="cb123-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cb123-148">您必須先在 Exchange Online 中指派許可權，才能執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="cb123-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="cb123-149">具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。</span><span class="sxs-lookup"><span data-stu-id="cb123-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="cb123-150">如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="cb123-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="cb123-151">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="cb123-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="cb123-152">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cb123-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cb123-153">若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cb123-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cb123-154">如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="cb123-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="cb123-155">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="cb123-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="cb123-156">Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)</span><span class="sxs-lookup"><span data-stu-id="cb123-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="cb123-157">Exchange Online 中的郵件流程規則動作</span><span class="sxs-lookup"><span data-stu-id="cb123-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="cb123-158">使用 EAC 來建立郵件流程規則，以接收報告訊息的副本</span><span class="sxs-lookup"><span data-stu-id="cb123-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="cb123-159">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb123-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="cb123-160">按一下 [**新增** ![加入](../../media/ITPro-EAC-AddIcon.png)圖示]，然後選取 [**建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb123-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="cb123-161">在開啟的 [**新增規則**] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cb123-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="cb123-162">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="cb123-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="cb123-163">例如，向 Microsoft 報告的 Bcc 郵件。</span><span class="sxs-lookup"><span data-stu-id="cb123-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="cb123-164">按一下 [**更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="cb123-164">Click **More Options**.</span></span>

   - <span data-ttu-id="cb123-165">在下列情況下套用**此規則**：選取**收件**\>**位址包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，](../../media/ITPro-EAC-AddIcon.png)按一下 [**新增** ![] 圖示，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="cb123-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="cb123-166">若要編輯專案，請選取它， **Edit** ![然後按一下 [](../../media/ITPro-EAC-EditIcon.png)編輯編輯圖示]。</span><span class="sxs-lookup"><span data-stu-id="cb123-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="cb123-167">若要移除專案，請選取它， **Remove** ![然後按一下 [](../../media/ITPro-EAC-DeleteIcon.png)移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="cb123-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="cb123-168">完成後，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb123-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="cb123-169">**請執行下列**動作：選取 [將收件者**新增** \> **至 Bcc**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="cb123-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="cb123-170">在出現的對話方塊中，尋找並選取您要新增的收件者。</span><span class="sxs-lookup"><span data-stu-id="cb123-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="cb123-171">完成後，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb123-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="cb123-172">您可以進行其他選擇來審核規則、測試規則、在特定時間週期內啟動規則，以及其他設定。</span><span class="sxs-lookup"><span data-stu-id="cb123-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="cb123-173">建議您先測試規則，再加以強制執行。</span><span class="sxs-lookup"><span data-stu-id="cb123-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="cb123-174">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb123-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="cb123-175">使用 PowerShell 建立郵件流程規則，以接收報告訊息的副本</span><span class="sxs-lookup"><span data-stu-id="cb123-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="cb123-176">此範例會建立名為「Bcc 郵件」的新郵件流程規則，該規則會尋找使用本主題中所述方法向 Microsoft 報告的電子郵件訊息，並將使用者 laura@contoso.com 及 julia@contoso.com 新增為 Bcc 收件者。</span><span class="sxs-lookup"><span data-stu-id="cb123-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="cb123-177">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="cb123-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cb123-178">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="cb123-178">How do you know this worked?</span></span>

<span data-ttu-id="cb123-179">若要驗證您是否已設定郵件流程規則以接收報告的郵件副本，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="cb123-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="cb123-180">在 EAC 中，移至 [**郵件流程** \> **規則** \> ] 選取\>規則，然後按一下](../../media/ITPro-EAC-EditIcon.png)[**編輯** ![編輯圖示]，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="cb123-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="cb123-181">在 PowerShell 中，執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="cb123-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="cb123-182">傳送測試郵件至其中一個報告電子郵件地址並確認結果。</span><span class="sxs-lookup"><span data-stu-id="cb123-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
