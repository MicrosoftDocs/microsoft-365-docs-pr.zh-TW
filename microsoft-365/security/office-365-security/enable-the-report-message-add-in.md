---
title: 啟用報告訊息增益集
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何為個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的 [報告訊息] 增益集。
ms.openlocfilehash: 13721317c33cf207f27cd8b98fb6d32864651847
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864993"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="e8646-103">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="e8646-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="e8646-104">如果您是使用 Exchange Online 信箱的 Microsoft 365 組織中的系統管理員，建議您在安全性 & 合規性中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="e8646-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e8646-105">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e8646-106">「Outlook」和「outlook」 (上的「outlook」和「Outlook」的報告訊息和報告網路增益集（以前稱為 Outlook Web App）) 可讓使用者輕鬆報告誤報， (適當的電子郵件標記為壞的) 或 false 的電子郵件， (錯誤的電子郵件允許 Microsoft 及其子公司進行分析。</span><span class="sxs-lookup"><span data-stu-id="e8646-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="e8646-107">Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="e8646-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="e8646-108">例如，如果人員報告大量已使用報告訊息增益集標記為垃圾郵件的郵件，您組織的安全性小組可能需要調整 [反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e8646-109">您可以安裝報告訊息或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="e8646-110">如果您想要讓使用者僅報告網路釣魚郵件，請在您的組織中部署報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="e8646-111">如需詳細資訊，請參閱 [Enable The Report 仿冒增益集](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="e8646-112">報告郵件增益集提供的選項可報告垃圾郵件和網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="e8646-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="e8646-113">系統管理員可以為組織啟用「報告訊息增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="e8646-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="e8646-114">如果您是個人使用者，您可以[自行啟用 [報告訊息] 增益集](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="e8646-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="e8646-115">如果您是全域系統管理員或 Exchange Online 系統管理員，且 Exchange 設定成使用 OAuth 驗證，您可以 [為組織啟用報告訊息增益集](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="e8646-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="e8646-116">[報告訊息] 增益集現可透過[集中式部署](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)提供。</span><span class="sxs-lookup"><span data-stu-id="e8646-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8646-117">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e8646-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8646-118">報告訊息增益集可與大多數 Microsoft 365 訂閱及下列產品搭配使用：</span><span class="sxs-lookup"><span data-stu-id="e8646-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="e8646-119">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="e8646-119">Outlook on the web</span></span>
  - <span data-ttu-id="e8646-120">Outlook 2013 SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="e8646-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e8646-121">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8646-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e8646-122">Outlook 隨附于適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="e8646-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="e8646-123">內部部署 Exchange 組織中的信箱無法使用報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e8646-124">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="e8646-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="e8646-125">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e8646-126">您的現有網頁瀏覽器應該使用報表訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="e8646-127">不過，如果您注意到增益集無法使用或如預期般運作，請嘗試其他瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="e8646-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e8646-128">若為組織安裝，必須設定組織使用 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="e8646-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e8646-129">如需詳細資訊，請參閱 [判斷是否集中式部署的增益集可為您的組織運作](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e8646-130">管理員必須是全域系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e8646-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e8646-131">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="e8646-132">自行取得報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="e8646-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="e8646-133">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e8646-134">若要直接移至報告訊息增益集，請移至 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="e8646-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e8646-135">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-135">Click **GET IT NOW**.</span></span>

   ![報告訊息 - 立即取得](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e8646-137">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e8646-138">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="e8646-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e8646-139">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="e8646-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e8646-140">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8646-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告訊息增益集圖示](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e8646-142">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8646-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 的網頁報告訊息增益集圖示](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e8646-144">若要瞭解如何使用增益集，請參閱 [use The Report Message 增益集](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="e8646-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="e8646-145">為貴組織取得和啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="e8646-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e8646-146">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="e8646-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e8646-147">在 Microsoft 365 系統管理中心中，移至 [ **設定]，& 增益集** ] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> ，然後按一下 [ **部署 Add-In**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-147">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e8646-149">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e8646-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="e8646-150">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-150">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="e8646-152">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊，輸入 **報告訊息**，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="e8646-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e8646-153">在結果清單中，尋找 [ **報告訊息** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![選取增益集搜尋結果](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="e8646-155">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="e8646-156">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="e8646-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e8646-157">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="e8646-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e8646-158">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="e8646-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="e8646-159">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="e8646-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="e8646-160">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="e8646-160">**Just me**</span></span>

   - <span data-ttu-id="e8646-161">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="e8646-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e8646-162">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="e8646-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e8646-163">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e8646-164">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="e8646-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![設定增益集頁面](../../media/configure-add-in.png)

   <span data-ttu-id="e8646-166">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="e8646-167">在出現的 [ **部署報告郵件** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="e8646-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e8646-168">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e8646-168">After you read the information, click **Next**.</span></span>

   ![部署報告郵件頁面](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="e8646-170">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e8646-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![宣告增益集頁面](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="e8646-172">了解如何使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="e8646-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="e8646-173">已指派增益集的人員會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="e8646-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="e8646-174">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8646-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告訊息增益集圖示](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e8646-176">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8646-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 的網頁報告訊息增益集圖示](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e8646-178">當您通知使用者關於 [報告訊息] 增益集時，請包含[使用報告訊息增益集](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。</span><span class="sxs-lookup"><span data-stu-id="e8646-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e8646-179">檢閱或編輯報告訊息增益集的設定</span><span class="sxs-lookup"><span data-stu-id="e8646-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e8646-180">在 Microsoft 365 系統管理中心中，移至上的 [ **服務] & 增益集** ] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 。</span><span class="sxs-lookup"><span data-stu-id="e8646-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e8646-182">尋找並選取 **報告訊息** 增益集。</span><span class="sxs-lookup"><span data-stu-id="e8646-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e8646-183">在顯示的 [ **編輯報告訊息** ] 浮出視窗中，視組織的需要複查及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="e8646-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e8646-184">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="e8646-184">When you're finished, click **Save**.</span></span>

   ![報告訊息增益集的設定](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e8646-186">查看和審閱報告的郵件</span><span class="sxs-lookup"><span data-stu-id="e8646-186">View and review reported messages</span></span>

<span data-ttu-id="e8646-187">若要查看使用者向 Microsoft 報告的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="e8646-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e8646-188">使用系統管理提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="e8646-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e8646-189">如需詳細資訊，請參閱 [View user 報送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="e8646-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="e8646-190">建立郵件流程規則 (也稱為傳輸規則) 傳送報告郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="e8646-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e8646-191">如需相關指示，請參閱 [使用郵件流程規則來查看您的使用者向 Microsoft 報告的內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="e8646-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
