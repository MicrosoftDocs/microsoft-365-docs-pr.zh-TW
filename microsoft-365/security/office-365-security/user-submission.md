---
title: 為使用者提交的垃圾郵件和網路釣魚郵件指定信箱
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
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.openlocfilehash: a3a175c3815c6750086526ec92d097fb7cbcefa3
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43922660"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a><span data-ttu-id="8faa0-103">在 Office 365 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱</span><span class="sxs-lookup"><span data-stu-id="8faa0-103">Specify a mailbox for user submissions of spam and phishing messages in Office 365</span></span>

<span data-ttu-id="8faa0-104">在使用 Exchange Online 信箱的 Office 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="8faa0-104">In Office 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="8faa0-105">當使用者使用各種報告選項提交郵件時，您可以使用此信箱來攔截郵件（只傳送至自訂信箱），或接收郵件的副本（傳送至自訂信箱和 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="8faa0-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="8faa0-106">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="8faa0-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="8faa0-107">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="8faa0-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="8faa0-108">[Outlook 網頁版中的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前稱為 Outlook web App）</span><span class="sxs-lookup"><span data-stu-id="8faa0-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="8faa0-109">您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="8faa0-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="8faa0-110">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統[管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8faa0-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8faa0-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8faa0-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8faa0-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="8faa0-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8faa0-113">若要直接移至 [**使用者報送**] 頁面<https://protection.office.com/userSubmissionsReportMessage>，請使用。</span><span class="sxs-lookup"><span data-stu-id="8faa0-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="8faa0-114">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8faa0-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8faa0-115">若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8faa0-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8faa0-116">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="8faa0-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8faa0-117">若要設定使用者提交的信箱，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8faa0-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8faa0-118">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8faa0-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="8faa0-119">使用安全性 & 規範中心設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="8faa0-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="8faa0-120">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則** \> ]**使用者報送**。</span><span class="sxs-lookup"><span data-stu-id="8faa0-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="8faa0-121">在出現的 [**使用者提交**] 頁面中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8faa0-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="8faa0-122">**啟用 outlook 的報告郵件功能（建議）**：如果您在網頁型 outlook 中使用報表訊息增益集或內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8faa0-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="8faa0-123">**自訂使用者確認訊息**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="8faa0-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="8faa0-124">在出現的 [**自訂確認訊息**] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8faa0-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="8faa0-125">**提交之前**：在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告郵件增益集」報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="8faa0-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8faa0-126">您可以使用變數% type% 來包含提交類型（垃圾郵件、非垃圾郵件網路釣魚等等）。</span><span class="sxs-lookup"><span data-stu-id="8faa0-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="8faa0-127">如前文所述，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="8faa0-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="8faa0-128">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="8faa0-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="8faa0-129">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="8faa0-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="8faa0-130">**提交後**：按一下![[展開](../../media/scc-expand-icon.png)圖示]。</span><span class="sxs-lookup"><span data-stu-id="8faa0-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="8faa0-131">在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告訊息增益集」報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="8faa0-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8faa0-132">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="8faa0-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="8faa0-133">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8faa0-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="8faa0-134">若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原**回來]。</span><span class="sxs-lookup"><span data-stu-id="8faa0-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="8faa0-135">**將報告的郵件傳送至**：進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="8faa0-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="8faa0-136">**Microsoft （建議使用）**：不使用使用者提交信箱（所有報告的郵件都會移至 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="8faa0-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="8faa0-137">**Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8faa0-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     - <span data-ttu-id="8faa0-138">**自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8faa0-138">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     <span data-ttu-id="8faa0-139">完成後，請按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="8faa0-139">When you're finished, click **Confirm**.</span></span>

     ![將報告的郵件傳送至 Microsoft 和自訂信箱](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="8faa0-141">**停用 Outlook 的報告郵件功能**：如果您使用協力廠商的報表工具，而不是在 web 上的 Outlook 中使用協力廠商的報表工具或內建的報表，請選取這個選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8faa0-141">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="8faa0-142">選取 [**使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="8faa0-142">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="8faa0-143">在出現的方塊中，輸入現有信箱的電子郵件地址，或您要建立之信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8faa0-143">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="8faa0-144">完成後，請按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="8faa0-144">When you're finished, click **Confirm**.</span></span>

     ![使用協力廠商工具將報告的郵件傳送至自訂信箱](../../media/user-submission-disable-outlook-report-message.png)
