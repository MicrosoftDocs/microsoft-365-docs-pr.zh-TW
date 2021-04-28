---
title: 報告 Outlook 中的誤報和漏報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 瞭解如何在 Outlook 中報告誤報和漏報，並啟用報告訊息和報告網路釣魚增益集。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065149"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="90f5d-103">報告 Outlook 中的誤報和漏報</span><span class="sxs-lookup"><span data-stu-id="90f5d-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90f5d-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="90f5d-104">**Applies to**</span></span>
- [<span data-ttu-id="90f5d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="90f5d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90f5d-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="90f5d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="90f5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90f5d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="90f5d-108">如果您是使用 Exchange Online 信箱的 Microsoft 365 組織中的系統管理員，建議您在安全性 & 合規性中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="90f5d-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="90f5d-109">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="90f5d-110">在使用混合式新式驗證的 Exchange Online 或內部部署信箱中具有信箱的 Microsoft 365 組織中，您可以提交誤報 (已標示為垃圾郵件的良好電子郵件) 和 false 負片 () Exchange Online Protection (EOP) 的電子郵件和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="90f5d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="90f5d-111">使用報告郵件功能之前需要記住的事項</span><span class="sxs-lookup"><span data-stu-id="90f5d-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="90f5d-112">為了獲得最佳的使用者提交經驗，請使用報告訊息增益集或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="90f5d-113">請注意，此增益集適用于所有平臺上的 Outlook：在網頁、iOS、Android 和桌面。</span><span class="sxs-lookup"><span data-stu-id="90f5d-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="90f5d-114">如果您是 Exchange Online 信箱組織中的系統管理員，請使用安全性 & 規範中心中的提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="90f5d-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="90f5d-115">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="90f5d-116">您可以設定為將郵件直接傳送到 Microsoft、您指定的信箱，或兩者皆傳送。</span><span class="sxs-lookup"><span data-stu-id="90f5d-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="90f5d-117">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="90f5d-118">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="90f5d-119">使用報告郵件功能</span><span class="sxs-lookup"><span data-stu-id="90f5d-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="90f5d-120">報告垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="90f5d-120">Report junk and phishing messages</span></span>

<span data-ttu-id="90f5d-121">對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列方法來報告垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="90f5d-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="90f5d-122">按一下所選郵件右上角的 [ **其他動作** ] 省略號，按一下下拉式功能表中的 [ **報告郵件** ]，然後選取 [ **垃圾** 郵件] 或 [ **網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f5d-123">![報告郵件-更多動作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f5d-124">![報告郵件-垃圾郵件和網路釣魚](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="90f5d-125">選取的郵件會傳送至 Microsoft 進行分析，並：</span><span class="sxs-lookup"><span data-stu-id="90f5d-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="90f5d-126">移至 [垃圾郵件] 資料夾（如果已舉報為垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="90f5d-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="90f5d-127">已刪除，如果已報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="90f5d-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="90f5d-128">報告非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="90f5d-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="90f5d-129">按一下所選郵件右上角的 [ **其他動作** ] 省略號，按一下下拉式功能表中的 [ **報告郵件** ]，然後按一下 [ **非垃圾** 郵件]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f5d-130">![報告郵件-更多動作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f5d-131">![報告訊息-不是垃圾郵件](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="90f5d-132">選取的郵件會傳送至 Microsoft 進行分析，然後移至 [收件匣] 或任何其他指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="90f5d-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="90f5d-133">啟用報告訊息和報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="90f5d-134">「Outlook」和「Outlook」 (上的「outlook」和「Outlook」的報告訊息和報告網路增益集（以前稱為 Outlook Web App）) 可讓使用者輕鬆報告誤報， (正確的電子郵件會標示為壞的) 或 false 的電子郵件， (錯誤的電子郵件可供 Microsoft 及其公司的分析使用。</span><span class="sxs-lookup"><span data-stu-id="90f5d-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="90f5d-135">Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="90f5d-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="90f5d-136">例如，假設有人使用「報告網路釣魚增益集」報告許多郵件。</span><span class="sxs-lookup"><span data-stu-id="90f5d-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="90f5d-137">此資訊會顯示在安全性儀表板及其他報告中。</span><span class="sxs-lookup"><span data-stu-id="90f5d-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="90f5d-138">貴組織的安全性小組可以使用此資訊來表示可能需要更新防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="90f5d-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="90f5d-139">您可以安裝報告訊息或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="90f5d-140">如果您想要讓使用者報告垃圾郵件和網路釣魚郵件，請在您的組織中部署報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="90f5d-141">如需詳細資訊，請參閱 Enable the Report Message 增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="90f5d-142">報告郵件增益集提供的選項可報告垃圾郵件和網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="90f5d-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="90f5d-143">系統管理員可以為組織啟用「報告訊息增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="90f5d-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="90f5d-144">報告網路釣魚增益集提供的選項可報告僅網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="90f5d-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="90f5d-145">系統管理員可以為組織啟用「報告網路釣魚增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="90f5d-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="90f5d-146">如果您是個別的使用者，您可以為自己啟用增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="90f5d-147">f 您是全域系統管理員或 Exchange Online 系統管理員，且 Exchange 設定成使用 OAuth 驗證，您可以為組織啟用報告訊息增益集和報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="90f5d-148">這兩個增益集現在均可透過 [集中式部署](../../admin/manage/centralized-deployment-of-add-ins.md)使用。</span><span class="sxs-lookup"><span data-stu-id="90f5d-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90f5d-149">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="90f5d-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90f5d-150">報告訊息增益集和報告網路釣魚增益集均可搭配大多數 Microsoft 365 訂閱和下列產品使用：</span><span class="sxs-lookup"><span data-stu-id="90f5d-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="90f5d-151">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="90f5d-151">Outlook on the web</span></span>
  - <span data-ttu-id="90f5d-152">Outlook 2013 SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="90f5d-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="90f5d-153">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90f5d-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="90f5d-154">Outlook 隨附于適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="90f5d-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="90f5d-155">適用于 iOS 和 Android 的 Outlook 應用程式</span><span class="sxs-lookup"><span data-stu-id="90f5d-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="90f5d-156">在內部部署 Exchange 組織中，這兩種增益集不能用於共用信箱或信箱。</span><span class="sxs-lookup"><span data-stu-id="90f5d-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="90f5d-157">您的現有網頁瀏覽器應該同時搭配報告訊息和報告網路釣魚增益集。不過，如果您注意到增益集無法使用或如預期般運作，請嘗試其他瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="90f5d-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="90f5d-158">若為組織安裝，必須設定組織使用 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="90f5d-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="90f5d-159">如需詳細資訊，請參閱 [判斷是否集中式部署的增益集可為您的組織運作](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="90f5d-160">管理員必須是全域系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90f5d-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="90f5d-161">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="90f5d-162">取得報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="90f5d-163">取得您自己的增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="90f5d-164">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="90f5d-165">若要直接移至報告訊息增益集，請移至 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="90f5d-166">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-166">Click **GET IT NOW**.</span></span>

   ![報告訊息 - 立即取得](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="90f5d-168">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="90f5d-169">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="90f5d-170">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="90f5d-171">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="90f5d-172">![Outlook 的報告訊息增益集圖示](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="90f5d-173">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="90f5d-174">![網頁型 Outlook 報告訊息增益集圖示](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="90f5d-175">取得組織的增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="90f5d-176">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="90f5d-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="90f5d-177">在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **增益集** ] 頁面，網址為 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="90f5d-178">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="90f5d-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="90f5d-179">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="90f5d-181">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="90f5d-182">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-182">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="90f5d-184">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊，輸入 **報告訊息**，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="90f5d-185">在結果清單中，尋找 [ **報告訊息** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![選取增益集搜尋結果](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="90f5d-187">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="90f5d-188">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="90f5d-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90f5d-189">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="90f5d-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="90f5d-190">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="90f5d-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="90f5d-191">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="90f5d-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="90f5d-192">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="90f5d-192">**Just me**</span></span>

   - <span data-ttu-id="90f5d-193">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="90f5d-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="90f5d-194">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="90f5d-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="90f5d-195">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="90f5d-196">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="90f5d-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![設定增益集頁面](../../media/configure-add-in.png)

   <span data-ttu-id="90f5d-198">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="90f5d-199">在出現的 [ **部署報告郵件** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="90f5d-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="90f5d-200">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-200">After you read the information, click **Next**.</span></span>

   ![部署報告郵件頁面](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="90f5d-202">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![宣告增益集頁面](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="90f5d-204">檢閱或編輯報告訊息增益集的設定</span><span class="sxs-lookup"><span data-stu-id="90f5d-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="90f5d-205">在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **增益集** ] 頁面，網址為 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="90f5d-206">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="90f5d-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="90f5d-208">尋找並選取 **報告訊息** 增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="90f5d-209">在顯示的 [ **編輯報告訊息** ] 浮出視窗中，視組織的需要複查及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="90f5d-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="90f5d-210">完成後，點擊 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-210">When you're finished, click **Save**.</span></span>

   ![報告訊息增益集的設定](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="90f5d-212">取得報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="90f5d-213">取得您自己的增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="90f5d-214">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="90f5d-215">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="90f5d-216">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="90f5d-217">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="90f5d-218">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="90f5d-219">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-219">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告網路釣魚增益集圖示](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="90f5d-221">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="90f5d-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="90f5d-222">![網頁型 Outlook 報告網路釣魚增益集圖示](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="90f5d-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="90f5d-223">取得組織的增益集</span><span class="sxs-lookup"><span data-stu-id="90f5d-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="90f5d-224">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="90f5d-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="90f5d-225">在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **增益集** ] 頁面，網址為 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="90f5d-226">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="90f5d-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="90f5d-227">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="90f5d-229">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="90f5d-230">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-230">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="90f5d-232">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊中的 [ **報告網路釣魚**]，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="90f5d-233">在結果清單中，尋找 [ **報告網路釣魚** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="90f5d-234">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="90f5d-235">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="90f5d-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90f5d-236">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="90f5d-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="90f5d-237">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="90f5d-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="90f5d-238">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="90f5d-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="90f5d-239">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="90f5d-239">**Just me**</span></span>

   - <span data-ttu-id="90f5d-240">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="90f5d-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="90f5d-241">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="90f5d-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="90f5d-242">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="90f5d-243">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="90f5d-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="90f5d-244">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="90f5d-245">在出現的 [ **部署報告網路釣魚** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="90f5d-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="90f5d-246">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="90f5d-247">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="90f5d-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="90f5d-248">查看或編輯報表網路釣魚增益集的設定</span><span class="sxs-lookup"><span data-stu-id="90f5d-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="90f5d-249">在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **增益集** ] 頁面，網址為 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="90f5d-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="90f5d-250">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="90f5d-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="90f5d-251">尋找並選取 **報告網路釣魚** 增益集。</span><span class="sxs-lookup"><span data-stu-id="90f5d-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="90f5d-252">在 [ **編輯報告的網路釣魚** ] 浮出控制項中，視您的組織而定，會顯示、審閱及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="90f5d-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="90f5d-253">完成後，點擊 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="90f5d-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="90f5d-254">查看和審閱報告的郵件</span><span class="sxs-lookup"><span data-stu-id="90f5d-254">View and review reported messages</span></span>

<span data-ttu-id="90f5d-255">若要查看使用者向 Microsoft 報告的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="90f5d-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="90f5d-256">使用系統管理提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="90f5d-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="90f5d-257">如需詳細資訊，請參閱 [View user 報送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="90f5d-258">建立郵件流程規則 (也稱為傳輸規則) 傳送報告郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="90f5d-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="90f5d-259">如需相關指示，請參閱 [使用郵件流程規則來查看您的使用者向 Microsoft 報告的內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="90f5d-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>