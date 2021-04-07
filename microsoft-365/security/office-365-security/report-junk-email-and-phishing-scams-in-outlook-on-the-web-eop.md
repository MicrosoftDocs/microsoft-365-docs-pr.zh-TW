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
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615206"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="67cae-103">在 Exchange Online 中，在 Outlook 網頁版中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="67cae-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67cae-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="67cae-104">**Applies to**</span></span>
- [<span data-ttu-id="67cae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="67cae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="67cae-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="67cae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67cae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67cae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="67cae-108">在使用 [混合式新式驗證](../../enterprise/hybrid-modern-auth-overview.md)的 Exchange online 或內部部署信箱中具有信箱的 Microsoft 365 組織中，您可以提交誤報 (已標示為垃圾郵件的適當電子郵件) 、false 不利 (允許的電子郵件) ，以及網路釣魚郵件至 Exchange Online PROTECTION (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="67cae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67cae-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="67cae-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67cae-110">為了獲得最佳的使用者提交經驗，我們建議使用報告訊息和報告網路釣魚增益集。請參閱 [enable The Report Message 增益集](./enable-the-report-message-add-in.md) 及 [啟用報告網路釣魚增益集](./enable-the-report-phish-add-in.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="67cae-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="67cae-111">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="67cae-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="67cae-112">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="67cae-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="67cae-113">系統管理員可以停用或啟用使用者在 Outlook 網頁版中將郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="67cae-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="67cae-114">如需詳細資訊，請參閱本文稍後的在 [網頁版 Outlook 中停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 一節。</span><span class="sxs-lookup"><span data-stu-id="67cae-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="67cae-115">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="67cae-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="67cae-116">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="67cae-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="67cae-117">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="67cae-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="67cae-118">在 web 上的 Outlook 中停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="67cae-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="67cae-119">根據預設，使用者可以在網頁上的 Outlook 中，將垃圾郵件誤報、錯誤否定和網路釣魚郵件報告給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="67cae-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="67cae-120">系統管理員可以在 Exchange Online PowerShell 中設定 web 信箱原則上的 Outlook，以防止使用者向 Microsoft 報告垃圾郵件誤報和垃圾郵件漏報。</span><span class="sxs-lookup"><span data-stu-id="67cae-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="67cae-121">您無法停用使用者將網路釣魚郵件報告給 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="67cae-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67cae-122">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="67cae-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67cae-123">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="67cae-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="67cae-124">您必須先在 Exchange Online 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="67cae-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="67cae-125">具體而言，您需要 **收件者原則** 或 **郵件** 收件者角色，預設會指派給 **組織管理** 和 **收件者管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="67cae-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="67cae-126">如需有關 Exchange Online 中角色群組的詳細資訊，請參閱 exchange online 中 [的許可權](/exchange/permissions-exo/permissions-exo) 及 [修改 exchange online 中的角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="67cae-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="67cae-127">每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="67cae-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="67cae-128">在預設原則之前，自訂原則會套用至範圍的使用者。</span><span class="sxs-lookup"><span data-stu-id="67cae-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="67cae-129">如需有關 Outlook 網頁信箱原則的詳細資訊，請參閱 [outlook On Exchange Online 中的 web 信箱原則](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="67cae-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="67cae-130">停用垃圾郵件報告時，並不會移除將郵件標示為垃圾郵件的功能，也不會移除 Outlook 網頁版中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="67cae-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="67cae-131">選取 [垃圾郵件] 資料夾中的郵件，然後按一下 [不是垃圾郵件] 中的 [**不** 是垃圾郵件] 會 \> 將郵件傳回收件匣</span><span class="sxs-lookup"><span data-stu-id="67cae-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="67cae-132">在任何其他電子郵件資料夾中選取郵件，然後按一下 [**垃圾** \> 郵件]，仍然會將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="67cae-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="67cae-133">您無法再使用的是將郵件報告給 Microsoft 的選項。</span><span class="sxs-lookup"><span data-stu-id="67cae-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="67cae-134">使用 Exchange Online PowerShell 在 web 上的 Outlook 中停用或啟用垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="67cae-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="67cae-135">若要尋找您的現有 Outlook 信箱原則及垃圾郵件報告狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67cae-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="67cae-136">若要在 Outlook 網頁版中停用或啟用垃圾郵件報告，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="67cae-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="67cae-137">本範例會停用預設原則中的垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="67cae-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="67cae-138">此範例會在名為 Contoso 管理員的自訂原則中，啟用垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="67cae-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="67cae-139">如需詳細的語法及參數資訊，請參閱 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 和 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="67cae-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="67cae-140">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="67cae-140">How do you know this worked?</span></span>

<span data-ttu-id="67cae-141">若要確認您是否已成功啟用或停用 Outlook 網頁版中的垃圾郵件報告，請使用下列任何一項步驟：</span><span class="sxs-lookup"><span data-stu-id="67cae-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="67cae-142">在 Exchange Online PowerShell 中，執行下列命令，並確認 **ReportJunkEmailEnabled** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="67cae-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="67cae-143">在網頁上的 Outlook 中開啟受影響使用者的信箱，在 [收件匣] 中選取一封郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67cae-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="67cae-144">在 web 上的 Outlook 中開啟受影響使用者的信箱，選取 [垃圾郵件] 資料夾中的郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67cae-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="67cae-145"><sup>\*</sup> 使用者可以在仍報告郵件時隱藏提示來報告郵件。</span><span class="sxs-lookup"><span data-stu-id="67cae-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="67cae-146">若要在 Outlook 網頁版中檢查此設定：</span><span class="sxs-lookup"><span data-stu-id="67cae-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="67cae-147">按一下 [ **設定** ![ 網頁上的 outlook] 圖示，以 ](../../media/owa-settings-icon.png) \> **查看所有 outlook 設定** \> **垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="67cae-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="67cae-148">在 [ **報告** ] 區段中，確認值： [傳送 **報告前請先詢問我**]。</span><span class="sxs-lookup"><span data-stu-id="67cae-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![網頁版 Outlook 垃圾郵件報告設定](../../media/owa-junk-email-reporting-options.png)