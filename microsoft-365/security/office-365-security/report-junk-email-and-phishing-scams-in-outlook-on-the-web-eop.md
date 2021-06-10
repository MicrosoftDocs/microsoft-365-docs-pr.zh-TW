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
description: 系統管理員可以深入瞭解 Outlook 網頁 (Outlook Web App Exchange Online) 的內建垃圾郵件、非垃圾郵件和網路釣魚電子郵件報告選項，以及如何為使用者停用這些報告選項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788304"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="0c760-103">在 Exchange Online 中的網頁 Outlook 中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="0c760-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0c760-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="0c760-104">**Applies to**</span></span>
- [<span data-ttu-id="0c760-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0c760-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0c760-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="0c760-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0c760-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c760-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0c760-108">在使用[混合式新式驗證](../../enterprise/hybrid-modern-auth-overview.md)的 Exchange Online 或內部部署信箱中使用信箱的 Microsoft 365 組織，您可以提交誤報) 的 (誤報電子郵件、false 不利 (允許不良電子郵件) ，以及網路釣魚郵件 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="0c760-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c760-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="0c760-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c760-110">建議使用者提交的報告訊息增益集或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="0c760-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="0c760-111">如需詳細資訊，請參閱[Enable The Report Message Or report](./enable-the-report-message-add-in.md)information the 增益集。由於無法使用[使用者提交原則](./user-submission.md)，因此建議您不要在 Outlook 內建報告經驗。</span><span class="sxs-lookup"><span data-stu-id="0c760-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="0c760-112">如果您是組織中 Exchange Online 信箱的系統管理員，建議您在安全性 & 規範中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="0c760-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0c760-113">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="0c760-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="0c760-114">系統管理員可以停用或啟用使用者將郵件報告給 Microsoft 的 Outlook 網頁上的功能。</span><span class="sxs-lookup"><span data-stu-id="0c760-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="0c760-115">如需詳細資訊，請參閱本文稍後的在 Outlook 的 web 區段中[停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)。</span><span class="sxs-lookup"><span data-stu-id="0c760-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="0c760-116">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="0c760-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="0c760-117">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="0c760-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="0c760-118">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="0c760-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="0c760-119">在 web 上的 Outlook 停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="0c760-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="0c760-120">根據預設，使用者可以將垃圾郵件誤報、漏報和網路釣魚郵件報告給 Microsoft，以在 web 上的 Outlook 進行分析。</span><span class="sxs-lookup"><span data-stu-id="0c760-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="0c760-121">系統管理員可以在 Exchange Online PowerShell 中的網頁信箱原則上設定 Outlook，以防止使用者向 Microsoft 報告垃圾郵件誤報和垃圾郵件的漏報。</span><span class="sxs-lookup"><span data-stu-id="0c760-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="0c760-122">您無法停用使用者將網路釣魚郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="0c760-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c760-123">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="0c760-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0c760-124">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0c760-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0c760-125">您必須在 Exchange Online 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="0c760-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="0c760-126">具體而言，您需要 **收件者原則** 或 **郵件** 收件者角色，預設會指派給 **組織管理** 和 **收件者管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="0c760-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="0c760-127">如需 Exchange Online 中角色群組的詳細資訊，請參閱 Exchange Online 中 Exchange Online 及[修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups)中[的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="0c760-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="0c760-128">每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="0c760-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="0c760-129">在預設原則之前，自訂原則會套用至範圍的使用者。</span><span class="sxs-lookup"><span data-stu-id="0c760-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="0c760-130">如需有關網頁信箱原則 Outlook 的詳細資訊，請參閱[Exchange Online 中的 Outlook 網頁信箱原則](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="0c760-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="0c760-131">停用垃圾郵件報告時，並不會移除將郵件標示為垃圾郵件的功能，也不會移除網頁 Outlook 中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="0c760-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="0c760-132">選取 [垃圾郵件] 資料夾中的郵件，然後按一下 [不是垃圾郵件] 中的 [**不** 是垃圾郵件] 會 \> 將郵件傳回收件匣</span><span class="sxs-lookup"><span data-stu-id="0c760-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="0c760-133">在任何其他電子郵件資料夾中選取郵件，然後按一下 [**垃圾** \> 郵件]，仍然會將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0c760-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="0c760-134">您無法再使用的是將郵件報告給 Microsoft 的選項。</span><span class="sxs-lookup"><span data-stu-id="0c760-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="0c760-135">使用 Exchange Online PowerShell 在網頁 Outlook 上停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="0c760-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="0c760-136">若要在 web 信箱原則上尋找現有的 Outlook，以及垃圾郵件報告的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0c760-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="0c760-137">若要停用或啟用網頁 Outlook 中的垃圾郵件報告，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0c760-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="0c760-138">本範例會停用預設原則中的垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="0c760-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="0c760-139">此範例會在名為 Contoso 管理員的自訂原則中，啟用垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="0c760-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="0c760-140">如需詳細的語法及參數資訊，請參閱 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 和 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="0c760-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0c760-141">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="0c760-141">How do you know this worked?</span></span>

<span data-ttu-id="0c760-142">若要確認您是否已成功啟用或停用網頁 Outlook 中的垃圾郵件報告，請使用下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="0c760-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="0c760-143">在 Exchange Online PowerShell 中，執行下列命令，並確認 **ReportJunkEmailEnabled** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="0c760-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="0c760-144">在網頁的 Outlook 中開啟受影響使用者的信箱，在 [收件匣] 中選取郵件，然後按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c760-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="0c760-145">在 web 上的 Outlook 中開啟受影響使用者的信箱，選取 [垃圾郵件] 資料夾中的郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c760-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="0c760-146"><sup>\*</sup> 使用者可以在仍報告郵件時隱藏提示來報告郵件。</span><span class="sxs-lookup"><span data-stu-id="0c760-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="0c760-147">若要在 web 上的 Outlook 中檢查此設定：</span><span class="sxs-lookup"><span data-stu-id="0c760-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="0c760-148">按一下 ![ [網站設定] 圖示上的 [設定 Outlook]， ](../../media/owa-settings-icon.png) \> **查看 [所有 Outlook 設定** \> **垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0c760-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="0c760-149">在 [ **報告** ] 區段中，確認值： [傳送 **報告前請先詢問我**]。</span><span class="sxs-lookup"><span data-stu-id="0c760-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook 網頁垃圾郵件報告設定](../../media/owa-junk-email-reporting-options.png)
