---
title: '在 Outlook 網頁版中回報垃圾郵件與網路釣魚詐騙 '
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365 具有 Exchange Online 信箱的使用者可以使用網頁型 Outlook （Outlook Web App），將垃圾郵件、非垃圾郵件和網路釣魚郵件提交給 Microsoft 進行分析。
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033681"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="70b2a-103">在 Office 365 的 Outlook 網頁版中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="70b2a-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="70b2a-104">如果您是具有 Exchange Online 信箱的 Office 365 客戶，您可以使用網頁型 Outlook （先前稱為 Outlook Web App）中的內建報告選項，送出誤報（良好的電子郵件，允許錯誤的電子郵件）和網路釣魚郵件至 Exchange Online Protection （EOP）。</span><span class="sxs-lookup"><span data-stu-id="70b2a-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="70b2a-105">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="70b2a-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="70b2a-106">如果您是 Office 365 組織中 Exchange Online 信箱的系統管理員，建議您在 Office 365 安全性 & 規範中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="70b2a-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="70b2a-107">如需詳細資訊，請參閱[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="70b2a-108">系統管理員可以停用或啟用使用者在 Outlook 網頁版中將郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="70b2a-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="70b2a-109">如需詳細資訊，請參閱本主題稍後的在[Outlook 網頁版中停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)一節。</span><span class="sxs-lookup"><span data-stu-id="70b2a-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="70b2a-110">如需向 Microsoft 報告訊息的詳細資訊，請參閱[在 Office 365 中報告訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="70b2a-111">在 Outlook 網頁版中報告垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="70b2a-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="70b2a-112">對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列其中一種方法來報告垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="70b2a-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="70b2a-113">選取郵件，按一下工具列上的 [**垃圾**郵件]，然後選取 [**垃圾**郵件] 或 [**網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/owa-report-junk.png)

   - <span data-ttu-id="70b2a-115">選取一或多封郵件、按一下滑鼠右鍵，然後選取 [**標記為垃圾**郵件]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="70b2a-116">在出現的對話方塊中，按一下 [**報表**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="70b2a-117">如果您變更主意，請按一下 [**不報告**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-117">If you change your mind, click **Don't Report**.</span></span>

   ![報告為垃圾郵件對話方塊](../../media/owa-report-as-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="70b2a-120">選取的郵件會傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="70b2a-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="70b2a-121">若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="70b2a-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="70b2a-122">從網頁型 Outlook 中的 [垃圾郵件] 資料夾報告非垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="70b2a-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="70b2a-123">在 [垃圾郵件] 資料夾中，使用下列其中一種方法來報告垃圾郵件誤報或網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="70b2a-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="70b2a-124">選取郵件，按一下工具列上的 [**非垃圾**郵件]，然後選取 [**不是垃圾**郵件或**網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="70b2a-126">選取一或多封郵件、按一下滑鼠右鍵，然後選取 [**標記為非垃圾**郵件]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="70b2a-127">在出現的對話方塊中，閱讀資訊，然後按一下 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="70b2a-128">如果您變更主意，請按一下 [**不報告**]。</span><span class="sxs-lookup"><span data-stu-id="70b2a-128">If you change your mind, click **Don't Report**.</span></span>

   ![[報告為非垃圾郵件] 對話方塊](../../media/owa-report-as-not-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="70b2a-131">選取的郵件會傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="70b2a-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="70b2a-132">若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="70b2a-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="70b2a-133">在 web 上的 Outlook 中停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="70b2a-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="70b2a-134">根據預設，使用者可以在網頁上的 Outlook 中，將垃圾郵件誤報、錯誤否定和網路釣魚郵件報告給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="70b2a-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="70b2a-135">系統管理員可以在 Exchange Online 中使用網頁型 Outlook 信箱原則，以停用或啟用此功能，但只在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="70b2a-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="70b2a-136">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="70b2a-137">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="70b2a-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="70b2a-138">具體說來，您需要 Exchange Online 中的**收件者原則**或**郵件**收件者角色（預設會指派給**組織管理**和**收件者管理**角色群組）。</span><span class="sxs-lookup"><span data-stu-id="70b2a-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="70b2a-139">如需有關 Exchange Online 中角色群組的詳細資訊，請參閱[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="70b2a-140">每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="70b2a-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="70b2a-141">在預設原則之前，自訂原則會套用至範圍的使用者。</span><span class="sxs-lookup"><span data-stu-id="70b2a-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="70b2a-142">如需有關 Outlook 網頁信箱原則的詳細資訊，請參閱[outlook On Exchange Online 中的 web 信箱原則](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="70b2a-143">若要尋找您的現有 Outlook 信箱原則及垃圾郵件報告狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="70b2a-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="70b2a-144">若要在 Outlook 網頁版中停用或啟用垃圾郵件報告，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="70b2a-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="70b2a-145">本範例會停用預設原則中的垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="70b2a-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="70b2a-146">此範例會在名為 Contoso 管理員的自訂原則中啟用垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="70b2a-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="70b2a-147">如需詳細的語法及參數資訊，請參閱[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="70b2a-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="70b2a-148">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="70b2a-148">How do you know this worked?</span></span>

<span data-ttu-id="70b2a-149">若要確認您是否已成功啟用或停用 Outlook 網頁版中的垃圾郵件報告，請使用下列任何一項步驟：</span><span class="sxs-lookup"><span data-stu-id="70b2a-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="70b2a-150">在 Exchange Online PowerShell 中，執行下列命令，並確認**ReportJunkEmailEnabled**屬性值：</span><span class="sxs-lookup"><span data-stu-id="70b2a-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="70b2a-151">在 web 上的 Outlook 中開啟受影響使用者的信箱，並驗證報告垃圾郵件、非垃圾郵件和網路釣魚郵件可用的選項。</span><span class="sxs-lookup"><span data-stu-id="70b2a-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="70b2a-152">請注意，使用者仍可將郵件標示為垃圾郵件、網路釣魚和非垃圾郵件，但使用者卻無法將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="70b2a-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>
