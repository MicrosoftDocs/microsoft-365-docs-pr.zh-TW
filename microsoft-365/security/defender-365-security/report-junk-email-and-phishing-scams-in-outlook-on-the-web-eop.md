---
title: 在 web 上的 Outlook 中報告垃圾郵件和網路釣魚電子郵件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Outlook 網頁版 Outlook 中內建的垃圾郵件、非垃圾郵件和網路釣魚電子郵件報告選項，在 Exchange Online 中) 的 Outlook Web App (，以及如何為使用者停用這些報告選項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1233b85ad213091ac84ac6f7e8eb93d9145af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059827"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="f1557-103">在 Exchange Online 中，在 Outlook 網頁版中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="f1557-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1557-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="f1557-104">**Applies to**</span></span>
- [<span data-ttu-id="f1557-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f1557-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f1557-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="f1557-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f1557-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1557-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f1557-108">在包含 Exchange Online 信箱的 Microsoft 365 組織中，您可以在 Outlook 網頁版 Outlook 中使用內建的報告選項， (之前稱為 Outlook Web App) 若要提交誤報 (良好的電子郵件) 、誤報 (不良電子郵件允許) 和網路釣魚郵件到 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="f1557-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1557-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="f1557-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1557-110">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="f1557-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f1557-111">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f1557-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="f1557-112">系統管理員可以停用或啟用使用者在 Outlook 網頁版中將郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="f1557-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="f1557-113">如需詳細資訊，請參閱本文稍後的在 [網頁版 Outlook 中停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 一節。</span><span class="sxs-lookup"><span data-stu-id="f1557-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="f1557-114">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="f1557-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f1557-115">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f1557-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f1557-116">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="f1557-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="f1557-117">在 Outlook 網頁版中報告垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="f1557-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="f1557-118">對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列其中一種方法來報告垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="f1557-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f1557-119">選取郵件，按一下工具列上的 [ **垃圾** 郵件]，然後選取 [ **垃圾** 郵件] 或 [ **網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/owa-report-junk.png)

   - <span data-ttu-id="f1557-121">選取一或多封郵件、按一下滑鼠右鍵，然後選取 [ **標記為垃圾** 郵件]。</span><span class="sxs-lookup"><span data-stu-id="f1557-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="f1557-122">在出現的對話方塊中，按一下 [ **報表**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="f1557-123">如果您變更主意，請按一下 [ **不報告**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="f1557-124">垃圾</span><span class="sxs-lookup"><span data-stu-id="f1557-124">Junk</span></span>|<span data-ttu-id="f1557-125">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="f1557-125">Phishing</span></span>|
   |:---:|:---:|
   |![報告為垃圾郵件對話方塊](../../media/owa-report-as-junk-dialog.png)|![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="f1557-128">選取的郵件會傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="f1557-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f1557-129">若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="f1557-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="f1557-130">從網頁型 Outlook 中的 [垃圾郵件] 資料夾報告非垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="f1557-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="f1557-131">在 [垃圾郵件] 資料夾中，使用下列其中一種方法來報告垃圾郵件誤報或網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="f1557-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f1557-132">選取郵件，按一下工具列上的 [ **非垃圾** 郵件]，然後選取 [ **不是垃圾** 郵件或 **網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![從功能區報告不是垃圾郵件或沒有網路釣魚電子郵件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="f1557-134">選取一或多封郵件、按一下滑鼠右鍵，然後選取 [ **標記為非垃圾** 郵件]。</span><span class="sxs-lookup"><span data-stu-id="f1557-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="f1557-135">在出現的對話方塊中，閱讀資訊，然後按一下 [ **報告**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f1557-136">如果您變更主意，請按一下 [ **不報告**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="f1557-137">非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="f1557-137">Not Junk</span></span>|<span data-ttu-id="f1557-138">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="f1557-138">Phishing</span></span>|
   |:---:|:---:|
   |![[報告為非垃圾郵件] 對話方塊](../../media/owa-report-as-not-junk-dialog.png)|![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="f1557-141">選取的郵件會傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="f1557-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f1557-142">若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="f1557-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f1557-143">在 web 上的 Outlook 中停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="f1557-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="f1557-144">根據預設，使用者可以在網頁上的 Outlook 中，將垃圾郵件誤報、錯誤否定和網路釣魚郵件報告給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="f1557-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="f1557-145">系統管理員可以在 Exchange Online PowerShell 中設定 web 信箱原則上的 Outlook，以防止使用者向 Microsoft 報告垃圾郵件誤報和垃圾郵件漏報。</span><span class="sxs-lookup"><span data-stu-id="f1557-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="f1557-146">您無法停用使用者將網路釣魚郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="f1557-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1557-147">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="f1557-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1557-148">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f1557-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f1557-149">您必須先在 Exchange Online 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="f1557-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="f1557-150">具體而言，您需要 **收件者原則** 或 **郵件** 收件者角色，預設會指派給 **組織管理** 和 **收件者管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="f1557-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="f1557-151">如需有關 Exchange Online 中角色群組的詳細資訊，請參閱 exchange online 中 [的許可權](/exchange/permissions-exo/permissions-exo) 及 [修改 exchange online 中的角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="f1557-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="f1557-152">每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f1557-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="f1557-153">在預設原則之前，自訂原則會套用至範圍的使用者。</span><span class="sxs-lookup"><span data-stu-id="f1557-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="f1557-154">如需有關 Outlook 網頁信箱原則的詳細資訊，請參閱 [outlook On Exchange Online 中的 web 信箱原則](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="f1557-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="f1557-155">停用垃圾郵件報告時，並不會移除將郵件標示為垃圾郵件的功能，也不會移除 Outlook 網頁版中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f1557-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="f1557-156">選取 [垃圾郵件] 資料夾中的郵件，然後按一下 [不是垃圾郵件] 中的 [**不** 是垃圾郵件] 會 \> 將郵件傳回收件匣</span><span class="sxs-lookup"><span data-stu-id="f1557-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="f1557-157">在任何其他電子郵件資料夾中選取郵件，然後按一下 [**垃圾** \> 郵件]，仍然會將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f1557-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="f1557-158">您無法再使用的是將郵件報告給 Microsoft 的選項。</span><span class="sxs-lookup"><span data-stu-id="f1557-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f1557-159">使用 Exchange Online PowerShell 在 web 上的 Outlook 中停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="f1557-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="f1557-160">若要尋找您的現有 Outlook 信箱原則及垃圾郵件報告狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f1557-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="f1557-161">若要在 Outlook 網頁版中停用或啟用垃圾郵件報告，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f1557-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="f1557-162">本範例會停用預設原則中的垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="f1557-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="f1557-163">此範例會在名為 Contoso 管理員的自訂原則中，啟用垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="f1557-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="f1557-164">如需詳細的語法及參數資訊，請參閱 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 和 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f1557-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f1557-165">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="f1557-165">How do you know this worked?</span></span>

<span data-ttu-id="f1557-166">若要確認您是否已成功啟用或停用 Outlook 網頁版中的垃圾郵件報告，請使用下列任何一項步驟：</span><span class="sxs-lookup"><span data-stu-id="f1557-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="f1557-167">在 Exchange Online PowerShell 中，執行下列命令，並確認 **ReportJunkEmailEnabled** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="f1557-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="f1557-168">在網頁上的 Outlook 中開啟受影響使用者的信箱，在 [收件匣] 中選取一封郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f1557-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="f1557-169">在 web 上的 Outlook 中開啟受影響使用者的信箱，選取 [垃圾郵件] 資料夾中的郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f1557-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="f1557-170"><sup>\*</sup> 使用者可以在仍報告郵件時隱藏提示來報告郵件。</span><span class="sxs-lookup"><span data-stu-id="f1557-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="f1557-171">若要在 Outlook 網頁版中檢查此設定：</span><span class="sxs-lookup"><span data-stu-id="f1557-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="f1557-172">按一下 [ **設定** ![ 網頁上的 outlook] 圖示，以 ](../../media/owa-settings-icon.png) \> **查看所有 outlook 設定** \> **垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="f1557-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="f1557-173">在 [ **報告** ] 區段中，確認值： [傳送 **報告前請先詢問我**]。</span><span class="sxs-lookup"><span data-stu-id="f1557-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![網頁版 Outlook 垃圾郵件報告設定](../../media/owa-junk-email-reporting-options.png)