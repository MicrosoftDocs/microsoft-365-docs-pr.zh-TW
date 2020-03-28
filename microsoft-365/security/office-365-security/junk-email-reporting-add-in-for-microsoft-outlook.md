---
title: 安裝和使用 Microsoft Outlook 的垃圾郵件回報增益集
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 瞭解如何安裝和使用 Microsoft 垃圾郵件回報增益集來向 Microsoft 報告垃圾郵件、非垃圾郵件和網路釣魚郵件。
ms.openlocfilehash: e39fb2f4ecba806c2d26d989fbbe6ddec137adc1
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033877"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="d9a5b-103">在 Office 365 中安裝及使用 Microsoft Outlook 的垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="d9a5b-104">如果您目前並未使用垃圾郵件回報增益集，則建議您改為[報告訊息增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="d9a5b-105">Microsoft Outlook 的垃圾郵件回報增益集可讓使用者提交誤報（已標記為垃圾郵件的良好電子郵件）、誤報（允許不良電子郵件）和網路釣魚郵件至 Exchange Online Protection （EOP）。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d9a5b-106">如果您的組織未使用 EOP，則您的垃圾郵件報告提交不會影響您的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="d9a5b-107">本主題說明如何安裝和使用垃圾郵件回報增益集。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d9a5b-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d9a5b-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d9a5b-109">若要安裝垃圾郵件回報增益集，請參閱本主題稍後的[安裝垃圾郵件回報增益集](#install-the-junk-email-reporting-add-in)一節。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="d9a5b-110">垃圾郵件回報增益集可與下列 Outlook 版本搭配使用：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="d9a5b-111">Outlook 2013 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d9a5b-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="d9a5b-112">Office 365 專業增強版隨附的 Outlook</span><span class="sxs-lookup"><span data-stu-id="d9a5b-112">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="d9a5b-113">如需向 Microsoft 報告訊息的詳細資訊，請參閱[在 Office 365 中報告訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="d9a5b-114">使用垃圾郵件回報增益集來報告垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="d9a5b-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="d9a5b-115">對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列任何一種方法來報告垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="d9a5b-116">選取郵件或開啟郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-116">Select the message or open the message.</span></span> <span data-ttu-id="d9a5b-117">在功能區的 [**首頁**] 或 [**訊息**] 索引標籤中，按一下 [**垃圾郵件**]，然後選取 [**報告為垃圾郵件**] 或 [**報表為網路**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="d9a5b-119">在郵件上按一下滑鼠右鍵，選取 [**垃圾**郵件]，然後選取 [**報告為垃圾**郵件] 或 [**報表為網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![從滑鼠右鍵按一下報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="d9a5b-121">選取多封郵件，以滑鼠右鍵按一下，然後選取 [**報告為垃圾**郵件] 或 [**報表為網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![從右擊報告多個垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="d9a5b-123">在出現的對話方塊中，閱讀資訊，然後按一下 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="d9a5b-124">如果您變更主意，請按一下 [**不報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-124">If you change your mind, click **Don't Report**.</span></span>

   ![報告為垃圾郵件對話方塊](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="d9a5b-p104">選取的郵件會傳送至 Microsoft 進行分析，然後移至 [垃圾郵件] 資料夾。若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="d9a5b-129">使用垃圾郵件回報增益集來報告垃圾郵件資料夾中的非垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="d9a5b-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="d9a5b-130">在 [垃圾郵件] 資料夾中，使用下列任何一種方法來報告垃圾郵件誤報或網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="d9a5b-131">選取郵件或開啟郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-131">Select the message or open the message.</span></span> <span data-ttu-id="d9a5b-132">在功能區的 [**首頁**] 或 [**訊息**] 索引標籤中，按一下 [**非垃圾郵件**]，然後選取 [**報告為非垃圾郵件**] 或 [**報表為網路**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![從 [垃圾郵件] 資料夾中的功能區報告不是垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="d9a5b-134">在郵件上按一下滑鼠右鍵，按一下 [**垃圾**郵件]，然後選取 [**報告為非垃圾郵件**] 或 [**報表為網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![在 [垃圾郵件] 資料夾中，以滑鼠右鍵按一下不報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="d9a5b-136">選取多封郵件，以滑鼠右鍵按一下，然後選取 [**報告為非垃圾郵件**] 或 [**報表為網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![在 [垃圾郵件] 資料夾中，以滑鼠右鍵按一下不限垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="d9a5b-138">在出現的對話方塊中，閱讀資訊，然後按一下 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="d9a5b-139">如果您變更主意，請按一下 [**不報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-139">If you change your mind, click **Don't Report**.</span></span>

   ![[報告為非垃圾郵件] 對話方塊](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="d9a5b-p107">選取的郵件會傳送至 Microsoft 進行分析，然後移至 [垃圾郵件] 資料夾。若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="d9a5b-144">安裝垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="d9a5b-145">您必須具備安裝增益集之電腦的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="d9a5b-146">移至<https://www.microsoft.com/download/details.aspx?id=18275>並下載適用于您的 Office 版本的 .msi 檔案，以供您尋找的位置：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="d9a5b-147">**32**位：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="d9a5b-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="d9a5b-148">**64**位：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="d9a5b-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="d9a5b-149">針對 Outlook 2013 或更新版本，唯一的必要條件是 Microsoft .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="d9a5b-150">在 Windows 10 中，您不會從下載安裝 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="d9a5b-151">使用安裝精靈安裝垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="d9a5b-152">在您的電腦上，關閉 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="d9a5b-153">在 Windows 10 中，確認已啟用 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="d9a5b-154">如需相關指示，請參閱[Enable the .Net Framework 3.5 In Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="d9a5b-155">找到您已下載的 .msi 檔案，然後按兩下它。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="d9a5b-156">在 **[歡迎使用 Microsoft 垃圾郵件回報增益集安裝程式]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="d9a5b-157">閱讀授權合約，如果您同意條款，請按一下 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="d9a5b-158">當精靈完成時，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="d9a5b-159">請啟動 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-159">Start Outlook.</span></span>

<span data-ttu-id="d9a5b-p110">請在 Outlook 功能區上尋找 **[垃圾郵件]** 按鈕。您現在可以選取 [收件匣] 中的垃圾郵件並按一下 **[回報垃圾郵件]** 按鈕，即可向 Microsoft 回報垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="d9a5b-p111">選擇 **[垃圾郵件]** 旁的向下箭號取得更多選項，例如您要向 Microsoft 回報網路釣魚詐騙郵件時使用的 **[回報為網路釣魚]**。在您的垃圾郵件資料夾中，如果電子郵件誤報為垃圾郵件，您也可以選取 **[回報非垃圾郵件]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="d9a5b-164">使用無訊息模式安裝垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="d9a5b-165">在您的電腦上，關閉 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="d9a5b-166">在 Windows 10 中執行下列命令，以安裝 .NET Framework 2.0：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="d9a5b-167">若要在沒有任何使用者互動的情況下安裝增益集，請開啟命令提示字元，並使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="d9a5b-168">`MaxMessageSelection`指定您可以為單一提交選取的郵件數目上限。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="d9a5b-169">有效的值介於1到50。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="d9a5b-170">預設值為 15。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-170">The default value is 15.</span></span>

   - <span data-ttu-id="d9a5b-171">`BccEmailAddress`指定將接收所有使用者提交之複本的其他密件副本收件者。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="d9a5b-172">預設值為空白（沒有其他的密件副本收件者）。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="d9a5b-173">本範例會從指定的路徑，使用預設設定，從指定的路徑安裝64位版本的增益集。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="d9a5b-174">此範例會從指定的路徑，使用下列其他設定，安裝32位版本的增益集：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="d9a5b-175">單一提交可選取最多20封郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="d9a5b-176">junkreports@contoso.com 和 hollyd@treyresearch.net 接收所有提交的密件副本副本。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d9a5b-177">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d9a5b-177">How do you know this worked?</span></span>

<span data-ttu-id="d9a5b-178">若要確認您是否已成功安裝垃圾郵件回報增益集，請在 Outlook 中執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="d9a5b-179">選取郵件或開啟郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-179">Select the message or open the message.</span></span> <span data-ttu-id="d9a5b-180">在功能區的 [**首頁**] 或 [**訊息**] 索引標籤中，按一下 [**垃圾郵件**]，然後確認下列選項可供使用：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="d9a5b-181">**報告為垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-181">**Report as Junk**</span></span>
  - <span data-ttu-id="d9a5b-182">**以網路釣魚報告**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="d9a5b-183">**垃圾報告選項**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="d9a5b-184">**報告垃圾資訊線上說明**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-184">**Report Junk Online Help**</span></span>

  ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="d9a5b-186">以滑鼠右鍵按一下郵件，選取 [**垃圾**郵件]，然後確認下列選項可供使用：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="d9a5b-187">**報告為垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-187">**Report as Junk**</span></span>
  - <span data-ttu-id="d9a5b-188">**以網路釣魚報告**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="d9a5b-189">**垃圾報告選項**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="d9a5b-190">**報告垃圾資訊線上說明**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-190">**Report Junk Online Help**</span></span>

  ![從滑鼠右鍵按一下報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="d9a5b-192">選取多封郵件，以滑鼠右鍵按一下，並確認下列選項可供使用：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="d9a5b-193">**報告為垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-193">**Report as Junk**</span></span>
  - <span data-ttu-id="d9a5b-194">**以網路釣魚報告**</span><span class="sxs-lookup"><span data-stu-id="d9a5b-194">**Report as Phishing**</span></span>

  ![從右擊報告多個垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="d9a5b-196">在 [**垃圾郵件**] 資料夾中執行先前的動作，並確認先前的**垃圾**申報選項現在**不是垃圾**郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![從 [垃圾郵件] 資料夾中的功能區報告不是垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![在 [垃圾郵件] 資料夾中，以滑鼠右鍵按一下不報告垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![在 [垃圾郵件] 資料夾中，以滑鼠右鍵按一下不限垃圾郵件或網路釣魚電子郵件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="d9a5b-200">解除安裝垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="d9a5b-201">在您關閉 Outlook 後，請使用下列任何程式卸載垃圾郵件回報增益集：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="d9a5b-202">**控制台**：按下 Windows 鍵 + R。在開啟的 [**執行**] 對話方塊中`control appwiz.cpl` ，輸入，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="d9a5b-203">在清單中尋找並選取**Microsoft 垃圾郵件回報增益集**，然後按一下 [**卸載**]。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="d9a5b-204">**Windows Installer 封裝**：尋找或下載適當的 .msi 檔案，然後按兩下該檔案。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="d9a5b-205">**32**位：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="d9a5b-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="d9a5b-206">**64**位：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="d9a5b-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="d9a5b-207">在出現的對話方塊中，選取 [**移除 Outlook 的 Microsoft 垃圾郵件回報增益集**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="d9a5b-208">**無訊息模式**：尋找或下載適當的 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="d9a5b-209">在 [命令提示字元] 視窗\<中\> ，將 PathToFile 取代為 .msi 檔案的位置，然後執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="d9a5b-210">**32**位：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="d9a5b-211">**64**位：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="d9a5b-212">當您在卸載後開啟 Outlook 時，[垃圾郵件]、[非垃圾郵件] 和 [網路釣魚報告] 選項都應該消失。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="d9a5b-213">疑難排解垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="d9a5b-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="d9a5b-214">在新增垃圾郵件報告 Add-In 後，您可能會遇到 Outlook 的問題。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="d9a5b-215">本節說明您可能會遇到的問題，以及解決這些問題的秘訣。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="d9a5b-216">使用者疑難排解</span><span class="sxs-lookup"><span data-stu-id="d9a5b-216">Troubleshooting for users</span></span>

<span data-ttu-id="d9a5b-217">您會遇到下列一或多項問題：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="d9a5b-218">按一下 **[回報垃圾郵件]** 沒有作用</span><span class="sxs-lookup"><span data-stu-id="d9a5b-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="d9a5b-219">選取電子郵件後，Outlook 停止回應</span><span class="sxs-lookup"><span data-stu-id="d9a5b-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="d9a5b-220">由於「無法傳遞」回覆，回報的垃圾郵件無法傳遞</span><span class="sxs-lookup"><span data-stu-id="d9a5b-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="d9a5b-221">若要修正此問題，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="d9a5b-222">關閉並重新啟動 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="d9a5b-223">建立及傳送測試郵件，並確認收件者收到郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="d9a5b-224">如果問題仍然存在，請與您的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="d9a5b-225">如需其他可用於將郵件提交至 Microsoft 的方法，請參閱[將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="d9a5b-226">管理員的疑難排解</span><span class="sxs-lookup"><span data-stu-id="d9a5b-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="d9a5b-227">問題：不斷出現錯誤訊息，詢問使用者是否要聯繫其系統管理員</span><span class="sxs-lookup"><span data-stu-id="d9a5b-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="d9a5b-228">驗證或將登錄`LoggingLevel`機碼設定為 "Verbose" 值：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="d9a5b-229">**32 位 Outlook on 32 Bit Windows**：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="d9a5b-230">**32 位 Outlook on 64 Bit Windows**：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="d9a5b-231">**64 位 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="d9a5b-232">重新開機 Outlook，並要求使用者在看到錯誤訊息時向後報告回來。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="d9a5b-233">收集下列位置中的記錄資訊：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="d9a5b-234">連絡 Exchange Online Protection 技術支援人員，並提供這項記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="d9a5b-235">問題：選取的使用者在報告郵件時，不會收到確認提示，而且現在想要回復提示</span><span class="sxs-lookup"><span data-stu-id="d9a5b-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="d9a5b-236">`ConfirmReportJunk`建立登錄機碼 wih 值為 "True"：</span><span class="sxs-lookup"><span data-stu-id="d9a5b-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="d9a5b-237">重新開機 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d9a5b-237">Restart Outlook.</span></span>
