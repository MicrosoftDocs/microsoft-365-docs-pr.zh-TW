---
title: 使用者報告的郵件設定
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083533"
---
# <a name="user-reported-message-settings"></a><span data-ttu-id="084ed-103">使用者報告的郵件設定</span><span class="sxs-lookup"><span data-stu-id="084ed-103">User reported message settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="084ed-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="084ed-104">**Applies to**</span></span>
- [<span data-ttu-id="084ed-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="084ed-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="084ed-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="084ed-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="084ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="084ed-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="084ed-108">在 Microsoft 365 具有 Exchange Online 信箱的組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="084ed-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="084ed-109">當使用者使用各種報告選項報告郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-109">When users report messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="084ed-110">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="084ed-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="084ed-111">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="084ed-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)
- [<span data-ttu-id="084ed-112">報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="084ed-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)
- [<span data-ttu-id="084ed-113">協力廠商報表工具</span><span class="sxs-lookup"><span data-stu-id="084ed-113">Third-party reporting tools</span></span>](#third-party-reporting-tools)

<span data-ttu-id="084ed-114">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="084ed-114">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span> <span data-ttu-id="084ed-115">這些設定以前稱為使用者提交原則。</span><span class="sxs-lookup"><span data-stu-id="084ed-115">These settings were formerly known as the User submissions policy.</span></span>

  > [!NOTE]
  > <span data-ttu-id="084ed-116">如果[Outlook 網頁版中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，則在這裡啟用使用者報告的訊息將會覆寫該設定，並且讓使用者能夠在 Outlook 網頁版中重新報告郵件。</span><span class="sxs-lookup"><span data-stu-id="084ed-116">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user reported messages here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="084ed-117">自訂信箱必要條件</span><span class="sxs-lookup"><span data-stu-id="084ed-117">Custom mailbox prerequisites</span></span>

<span data-ttu-id="084ed-118">使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：</span><span class="sxs-lookup"><span data-stu-id="084ed-118">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="084ed-119">建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="084ed-119">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="084ed-120">請參閱 [使用 EAC 建立郵件流程規則，](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定郵件的 scl 設定為將 scl 設定為 **略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="084ed-120">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="084ed-121">[建立保管庫附件原則](set-up-safe-attachments-policies.md)，其中包含關閉保管庫附件掃描的自訂信箱 (**保管庫附件未知惡意程式碼回應** 區段 \> **off**) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-121">[Create a Safe Attachments policy](set-up-safe-attachments-policies.md) that includes the custom mailbox where Safe Attachments scanning is turned off (**Safe Attachments unknown malware response** section \> **Off**).</span></span>

- <span data-ttu-id="084ed-122">[建立保管庫連結原則](set-up-safe-links-policies.md)，其中包含關閉保管庫連結掃描的自訂信箱 (**選取 [郵件中未知潛在惡意 URLs 的動作**] 區段中的 \> ) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-122">[Create a Safe Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where Safe Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages** section \> **Off**).</span></span>

- <span data-ttu-id="084ed-123">建立包含自訂信箱的 [反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)，其中會關閉惡意程式碼的零小時自動清除 (ZAP)  (**保護設定**] 區段 \> 。) 未選取惡意程式碼的 **自動清除** 功能。</span><span class="sxs-lookup"><span data-stu-id="084ed-123">[Create an anti-malware policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where zero-hour auto purge (ZAP) for malware is turned off (**Protection settings** section \> **Enable zero-hour auto purge for malware** is not selected).</span></span>

- <span data-ttu-id="084ed-124">[建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) ，其中包含的自訂信箱，針對網路釣魚使用的垃圾郵件和 zap 會關閉 (**0 小時自動清除** 區段 \> **已啟用零小時自動清除** ]。 (不會) 選取 ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-124">[Create an anti-spam policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where ZAP for spam and ZAP for phishing are turned off (**Zero-hour auto purge** section \> **Enabled zero-hour auto purge (ZAP)** is not selected).</span></span>

- <span data-ttu-id="084ed-125">停用自訂信箱中的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="084ed-125">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="084ed-126">使用 [[設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)] 以停用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="084ed-126">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="084ed-127">停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至 [垃圾郵件] 資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="084ed-127">After it's disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="084ed-128">在您確認您的信箱符合所有適用的先決條件後，您可以使用本文中的程式來設定使用者認可信箱。</span><span class="sxs-lookup"><span data-stu-id="084ed-128">After you've verified that your mailbox meets all applicable prerequisites, you can use the procedures in this article to configure the user submissions mailbox.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="084ed-129">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="084ed-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="084ed-130">您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="084ed-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="084ed-131">若要直接移至 [ **提交** ] 頁面，請使用 <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="084ed-131">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="084ed-132">若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="084ed-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="084ed-133">**組織管理** 或 **安全性管理員** [Microsoft 365 Defender 入口網站](permissions-microsoft-365-security-center.md)中的許可權。</span><span class="sxs-lookup"><span data-stu-id="084ed-133">**Organization Management** or **Security Administrator** in the [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="084ed-134">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="084ed-134">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="084ed-135">您需要 Exchange Online PowerShell 的存取權。</span><span class="sxs-lookup"><span data-stu-id="084ed-135">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="084ed-136">如果您嘗試使用的帳戶不具備 Exchange Online PowerShell 的存取權，當您指定提交信箱時，您會收到如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="084ed-136">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="084ed-137">在您的網域中指定電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="084ed-137">Specify an email address in your domain</span></span>

  <span data-ttu-id="084ed-138">如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="084ed-138">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="084ed-139">啟用或停用 Exchange Online PowerShell 的存取權</span><span class="sxs-lookup"><span data-stu-id="084ed-139">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="084ed-140">Exchange Online 中的用戶端存取規則</span><span class="sxs-lookup"><span data-stu-id="084ed-140">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="084ed-141">使用 Microsoft 365 Defender 入口網站設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="084ed-141">Use the Microsoft 365 Defender portal to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="084ed-142">在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **威脅** 原則 \> **其他**] 區段 \> **使用者報告的郵件設定** \> **使用者提交**。</span><span class="sxs-lookup"><span data-stu-id="084ed-142">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings** \> **User submissions**.</span></span>

2. <span data-ttu-id="084ed-143">在 [**使用者** 送出] 頁面上，您所看到的內容取決於 [ **Microsoft Outlook 報告**] [訊息] 按鈕設定為 [**關閉**] 或 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="084ed-143">On the **User submissions** page, what you see is determined by whether the **Microsoft Outlook Report Message button** setting is **Off** or **On**:</span></span>

   - <span data-ttu-id="084ed-144">**Microsoft Outlook 報告訊息按鈕** \>**開啟** ![開啟切換 ](../../media/scc-toggle-on.png) ：如果您使用報告訊息增益集、報告中 Outlook 網頁版的報告網路釣魚增益集或內建報告，請選取這個選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="084ed-144">**Microsoft Outlook Report Message button** \> **On** ![Toggle on](../../media/scc-toggle-on.png): Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="084ed-145">**將報告的郵件傳送至**：選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="084ed-145">**Send the reported messages to**: Select one of the following options:</span></span>
       - <span data-ttu-id="084ed-146">**Microsoft**：不使用使用者送出信箱 (所有報告的郵件都會移至 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-146">**Microsoft**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
       - <span data-ttu-id="084ed-147">**Microsoft 和我的組織信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="084ed-147">**Microsoft and my organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="084ed-148">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="084ed-148">Distribution groups are not allowed.</span></span> <span data-ttu-id="084ed-149">使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。</span><span class="sxs-lookup"><span data-stu-id="084ed-149">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
       - <span data-ttu-id="084ed-150">**我的組織信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="084ed-150">**My organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="084ed-151">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="084ed-151">Distribution groups are not allowed.</span></span> <span data-ttu-id="084ed-152">如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="084ed-152">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="084ed-153">除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="084ed-153">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!IMPORTANT]
          >
          > <span data-ttu-id="084ed-154">美國政府組織 (GCC、GCC 高及 DoD) 只能設定 **我的組織的信箱**。</span><span class="sxs-lookup"><span data-stu-id="084ed-154">U.S. Government organizations (GCC, GCC High, and DoD) can only configure **My organization's mailbox**.</span></span> <span data-ttu-id="084ed-155">其他兩個選項會停用。</span><span class="sxs-lookup"><span data-stu-id="084ed-155">The other two options are disabled.</span></span>
          >
          > <span data-ttu-id="084ed-156">如果組織已設定為僅傳送至自訂信箱，將不會傳送報告的郵件以進行重新掃描，而且使用者報告的郵件入口網站將永遠會是空的。</span><span class="sxs-lookup"><span data-stu-id="084ed-156">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

       <span data-ttu-id="084ed-157">不論您選取要 **傳送報告的郵件** 值，都可以使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="084ed-157">Regardless of the value you selected for **Send the reported messages to**, the following settings are available:</span></span>

       - <span data-ttu-id="084ed-158">**讓使用者選擇是否要將其郵件報告給 Microsoft**</span><span class="sxs-lookup"><span data-stu-id="084ed-158">**Let users choose if they want to report their message to Microsoft**</span></span>
       - <span data-ttu-id="084ed-159">**選取 [使用者可使用的報告選項** ] 區段：請至少選取下列選項中的一個：</span><span class="sxs-lookup"><span data-stu-id="084ed-159">**Select reporting options that are available to users** section: Select at least one among the following options:</span></span>
         - <span data-ttu-id="084ed-160">**傳送郵件之前向我提問**</span><span class="sxs-lookup"><span data-stu-id="084ed-160">**Ask me before sending the message**</span></span>
         - <span data-ttu-id="084ed-161">**無條件報告訊息**</span><span class="sxs-lookup"><span data-stu-id="084ed-161">**Always report the message**</span></span>
         - <span data-ttu-id="084ed-162">**從不報告訊息**</span><span class="sxs-lookup"><span data-stu-id="084ed-162">**Never report the message**</span></span>

          > [!CAUTION]
          > <span data-ttu-id="084ed-163">如果您已在使用 Outlook 網頁版信箱原則[的 Outlook 網頁版中停用垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)，但您設定了先前的任何設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集或報告網路釣魚增益集，在 Outlook 網頁版中向 microsoft 報告郵件。</span><span class="sxs-lookup"><span data-stu-id="084ed-163">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configured any of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

     - <span data-ttu-id="084ed-164">**使用者報告經驗區段**</span><span class="sxs-lookup"><span data-stu-id="084ed-164">**User reporting experience section**</span></span>
       - <span data-ttu-id="084ed-165">在 [**報告**] 索引卷 **標** 中：在 [標題] 和 [**訊息**] 方塊中，輸入使用者在使用報告郵件增益集或報表網路釣魚增益集報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="084ed-165">**Before reporting** tab: In the **Title** and **Message body** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="084ed-166">您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-166">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>
       - <span data-ttu-id="084ed-167">在 [**報告**] 索引卷 **標** 中：在 [標題] 和 [**確認訊息**] 方塊中，輸入使用者在使用報告訊息增益集或報表網路釣魚增益集報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="084ed-167">**After reporting** tab: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="084ed-168">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="084ed-168">You can use the variable %type% to include the submission type.</span></span>

       <span data-ttu-id="084ed-169">如頁面上所示，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="084ed-169">As shown on the page, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="084ed-170">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="084ed-170">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="084ed-171">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="084ed-171">Some emails might contain personal or sensitive information.</span></span>

   - <span data-ttu-id="084ed-172">**Microsoft Outlook 報告訊息按鈕** \>**關閉** ![關閉切換 ](../../media/scc-toggle-off.png) ：如果您使用協力廠商報告工具，而不是報告郵件增益集、報告網路釣魚增益集或 Outlook 網頁版中內建的報告，請選取這個選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="084ed-172">**Microsoft Outlook Report Message button** \> **Off** ![Toggle off](../../media/scc-toggle-off.png): Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="084ed-173">選取 [ **使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="084ed-173">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="084ed-174">在出現的方塊中，輸入可接收電子郵件之現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="084ed-174">In the box that appears, enter the email address of an existing Exchange Online mailbox that can receive email.</span></span>

   <span data-ttu-id="084ed-175">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="084ed-175">When you're finished, click **Confirm**.</span></span> <span data-ttu-id="084ed-176">若要清除這些值，請按一下 [**還原**]</span><span class="sxs-lookup"><span data-stu-id="084ed-176">To clear these values, click **Restore**</span></span>

## <a name="third-party-reporting-tools"></a><span data-ttu-id="084ed-177">協力廠商報表工具</span><span class="sxs-lookup"><span data-stu-id="084ed-177">Third-party reporting tools</span></span>

<span data-ttu-id="084ed-178">您可以設定協力廠商郵件報告工具，將報告的郵件傳送至自訂信箱。</span><span class="sxs-lookup"><span data-stu-id="084ed-178">You can configure third-party message reporting tools to send reported messages to the custom mailbox.</span></span> <span data-ttu-id="084ed-179">為此，您可以將 [ **Microsoft Outlook Report Message 按鈕**] 設定為 [**關閉**]，然後將 [**我的組織] 信箱** 設定為您所選擇的 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="084ed-179">You would do this by setting the **Microsoft Outlook Report Message button** setting to **Off** and setting the **My organization's mailbox** to an Office 365 mailbox of your choice.</span></span>

<span data-ttu-id="084ed-180">唯一的需求是原始郵件會包含為。.EML 或。MSG 附件 (在傳送至自訂信箱的郵件中) 壓縮， (不要只將原始郵件轉寄至自訂信箱) 。</span><span class="sxs-lookup"><span data-stu-id="084ed-180">The only requirement is that the original message is included as a .EML or .MSG attachment (not compressed) in the message that's sent to the custom mailbox (don't just forward the original message to the custom mailbox).</span></span>

<span data-ttu-id="084ed-181">郵件格式設定需求會在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="084ed-181">The message formatting requirements are described in the next section.</span></span> <span data-ttu-id="084ed-182">格式設定是選用的，但如果它不遵循指定的格式，則會永遠以網路釣魚提交報告。</span><span class="sxs-lookup"><span data-stu-id="084ed-182">The formatting is optional, but if it does not follow the prescribed format, the reports will always be submitted as phish.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="084ed-183">郵件提交格式</span><span class="sxs-lookup"><span data-stu-id="084ed-183">Message submission format</span></span>

<span data-ttu-id="084ed-184">若要正確識別原始附加郵件，傳送至自訂信箱的郵件需要特定格式。</span><span class="sxs-lookup"><span data-stu-id="084ed-184">To correctly identify the original attached messages, messages that are sent to the custom mailbox require specific formatting.</span></span> <span data-ttu-id="084ed-185">如果郵件未使用此格式，則原始附加郵件會永遠識別為網路釣魚提交。</span><span class="sxs-lookup"><span data-stu-id="084ed-185">If the messages don't use this format, the original attached messages are always identified as phishing submissions.</span></span>

<span data-ttu-id="084ed-186">為了正確識別原始附加郵件，傳送至自訂信箱的郵件必須針對主旨 (信封標題) 使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="084ed-186">For correct identification of the original attached messages, messages that are sent to the custom mailbox need to use the following syntax for the Subject (Envelope Title):</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="084ed-187">其中，SafetyAPIAction 是下列其中一個整數值：</span><span class="sxs-lookup"><span data-stu-id="084ed-187">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="084ed-188">1：垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="084ed-188">1: Junk</span></span>
- <span data-ttu-id="084ed-189">2：非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="084ed-189">2: Not junk</span></span>
- <span data-ttu-id="084ed-190">3：網路釣魚</span><span class="sxs-lookup"><span data-stu-id="084ed-190">3: Phishing</span></span>

<span data-ttu-id="084ed-191">本範例會使用下列值：</span><span class="sxs-lookup"><span data-stu-id="084ed-191">This example uses the following values:</span></span>

- <span data-ttu-id="084ed-192">將郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="084ed-192">The message is being reported as phishing.</span></span>
- <span data-ttu-id="084ed-193">網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="084ed-193">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="084ed-194">寄件者 IP 為167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="084ed-194">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="084ed-195">[寄件者] 位址為 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="084ed-195">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="084ed-196">郵件的主旨行是「測試網路釣魚提交」</span><span class="sxs-lookup"><span data-stu-id="084ed-196">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="084ed-197">未遵循此格式的郵件將無法在提交入口網站中正確顯示。</span><span class="sxs-lookup"><span data-stu-id="084ed-197">Messages that don't follow this format will not display properly in the Submissions portal.</span></span>
