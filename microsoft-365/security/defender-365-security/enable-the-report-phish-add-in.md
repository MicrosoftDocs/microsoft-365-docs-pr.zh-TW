---
title: 啟用報表網路釣魚增益集
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: 瞭解如何為個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的報表網路釣魚增益集。
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059620"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="6081d-103">啟用報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="6081d-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="6081d-104">如果您是使用 Exchange Online 信箱的 Microsoft 365 組織中的系統管理員，建議您在安全性 & 合規性中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="6081d-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6081d-105">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="6081d-106">「Outlook」和「Outlook」 (上的「outlook」和「Outlook」的報告訊息和報告網路增益集（以前稱為 Outlook Web App）) 可讓使用者輕鬆報告誤報， (正確的電子郵件會標示為壞的) 或 false 的電子郵件， (錯誤的電子郵件可供 Microsoft 及其公司的分析使用。</span><span class="sxs-lookup"><span data-stu-id="6081d-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="6081d-107">Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="6081d-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="6081d-108">例如，假設有人使用「報告網路釣魚增益集」報告許多郵件。</span><span class="sxs-lookup"><span data-stu-id="6081d-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="6081d-109">此資訊會顯示在[安全性儀表板](security-dashboard.md)及其他報告中。</span><span class="sxs-lookup"><span data-stu-id="6081d-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="6081d-110">貴組織的安全性小組可以使用此資訊來表示可能需要更新防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="6081d-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="6081d-111">您可以安裝報告訊息或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="6081d-112">如果您想要讓使用者報告垃圾郵件和網路釣魚郵件，請在您的組織中部署報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="6081d-113">如需詳細資訊，請參閱 [Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="6081d-114">報告網路釣魚增益集提供的選項可報告僅網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="6081d-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="6081d-115">系統管理員可以為組織啟用「報告網路釣魚增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="6081d-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="6081d-116">如果您是個別的使用者，您可以 [為自己啟用報告網路釣魚增益集](#get-the-report-phishing-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="6081d-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="6081d-117">如果您是全域系統管理員或 Exchange Online 系統管理員，且 Exchange 設定成使用 OAuth 驗證，您可以 [為組織啟用報告網路釣魚增益集](#get-and-enable-the-report-phishing-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="6081d-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="6081d-118">現在，您可以透過 [集中式部署](../../admin/manage/centralized-deployment-of-add-ins.md)來使用報表網路釣魚 Add-In。</span><span class="sxs-lookup"><span data-stu-id="6081d-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6081d-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="6081d-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6081d-120">報告網路釣魚增益集會與大部分的 Microsoft 365 訂閱及下列產品搭配運作：</span><span class="sxs-lookup"><span data-stu-id="6081d-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="6081d-121">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="6081d-121">Outlook on the web</span></span>
  - <span data-ttu-id="6081d-122">Outlook 2013 SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6081d-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="6081d-123">Mac 版 Outlook 2016 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6081d-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="6081d-124">Outlook 隨附于適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="6081d-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="6081d-125">適用于 iOS 和 Android 的 Outlook 應用程式</span><span class="sxs-lookup"><span data-stu-id="6081d-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="6081d-126">在內部部署 Exchange 組織中，共用信箱或信箱無法使用報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="6081d-127">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="6081d-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6081d-128">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="6081d-129">您的現有網頁瀏覽器應該使用報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="6081d-130">不過，如果您注意到增益集無法使用或如預期般運作，請嘗試其他瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="6081d-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="6081d-131">若為組織安裝，必須設定組織使用 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="6081d-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="6081d-132">如需詳細資訊，請參閱 [判斷是否集中式部署的增益集可為您的組織運作](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="6081d-133">管理員必須是全域系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6081d-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="6081d-134">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="6081d-135">取得您自己的報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="6081d-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="6081d-136">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="6081d-137">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="6081d-138">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="6081d-139">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="6081d-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="6081d-140">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="6081d-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="6081d-141">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="6081d-141">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告網路釣魚增益集圖示](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="6081d-143">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="6081d-143">In Outlook on the web, the icon looks like this:</span></span>

  ![網頁型 Outlook 報告網路釣魚增益集圖示](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="6081d-145">取得及啟用組織的報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="6081d-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="6081d-146">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="6081d-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="6081d-147">在 Microsoft 365 系統管理中心中，移至 [**設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> ，如果看不到 [**載入** 宏] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="6081d-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="6081d-148">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6081d-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="6081d-150">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6081d-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="6081d-151">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-151">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="6081d-153">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊中的 [ **報告網路釣魚**]，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="6081d-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="6081d-154">在結果清單中，尋找 [ **報告網路釣魚** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="6081d-155">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="6081d-156">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="6081d-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6081d-157">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="6081d-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="6081d-158">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="6081d-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="6081d-159">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="6081d-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="6081d-160">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="6081d-160">**Just me**</span></span>

   - <span data-ttu-id="6081d-161">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="6081d-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="6081d-162">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="6081d-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="6081d-163">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="6081d-164">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="6081d-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="6081d-165">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="6081d-166">在出現的 [ **部署報告網路釣魚** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="6081d-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="6081d-167">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6081d-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="6081d-168">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6081d-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="6081d-169">瞭解如何使用報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="6081d-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="6081d-170">已指派增益集的人員會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="6081d-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="6081d-171">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="6081d-171">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告網路釣魚增益集圖示](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="6081d-173">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="6081d-173">In Outlook on the web, the icon looks like this:</span></span>

  ![網頁型 Outlook 報告網路釣魚增益集圖示](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="6081d-175">查看或編輯報表網路釣魚增益集的設定</span><span class="sxs-lookup"><span data-stu-id="6081d-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="6081d-176">在 Microsoft 365 系統管理中心中，移至 [**設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> ，如果看不到 [**載入** 宏] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="6081d-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="6081d-177">尋找並選取 **報告網路釣魚** 增益集。</span><span class="sxs-lookup"><span data-stu-id="6081d-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="6081d-178">在 [ **編輯報告的網路釣魚** ] 浮出控制項中，視您的組織而定，會顯示、審閱及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="6081d-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="6081d-179">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="6081d-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="6081d-180">查看和審閱報告的郵件</span><span class="sxs-lookup"><span data-stu-id="6081d-180">View and review reported messages</span></span>

<span data-ttu-id="6081d-181">若要查看使用者向 Microsoft 報告的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="6081d-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="6081d-182">使用系統管理提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="6081d-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="6081d-183">如需詳細資訊，請參閱 [View user 報送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="6081d-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="6081d-184">建立郵件流程規則 (也稱為傳輸規則) 傳送報告郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="6081d-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="6081d-185">如需相關指示，請參閱 [使用郵件流程規則來查看您的使用者向 Microsoft 報告的內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6081d-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
